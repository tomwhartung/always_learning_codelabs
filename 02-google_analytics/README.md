# 02-google_analytics/README.md

# References

- Test the download and rendering speed of your site: http://www.webpagetest.org/
- Home page of MDN's User Timing API: https://developer.mozilla.org/en-US/docs/Web/API/User_Timing_API
- Home page of MDN's Navigation Timing API: https://developer.mozilla.org/en-US/docs/Web/API/Navigation_timing_API
- About google's `analytics.js` javascript library: https://developers.google.com/analytics/devguides/collection/analyticsjs/
- Debug version of `analytics.js`: https://developers.google.com/analytics/devguides/collection/analyticsjs/debugging
- About using `analytics.js` to measure timings: https://developers.google.com/analytics/devguides/collection/analyticsjs/user-timings

# Steps

## Sections 1-2: Setup

- Downloaded sample code into `downloads` directory

## Section 3 - Before you begin

### Asset performance considerations

CSS: A concern because they block rendering of all subsequent assets

- Concerns:
  - If not in the html, must be downloaded
  - Must be parsed before rendering can resume
- Advice:
  - Place all critical sheets in the head
  - Load all noncritical sheets asynchronously later

Javascript: A concern because it blocks parsing and construction of the DOM

- Concerns:
  - If not in the html, must be downloaded
  - Code in script tags must be executed before moving on to the next tag
- Advice:
  - Place script tags just before the closing body tag

Web fonts: May want to block rendering until fonts are loaded

- Concerns:
  - May load quickly for you but slowly for many users
- Advice:
  - Measure and use real data for making decisions about the use of fonts

Images: May take the longest to load

- Concern:
  - It is important to spot correlations between use of images and load time
- Advice:
  - Try to optimize after understanding where the problem areas lie

## Section 4 - Step 0: Viewing the demo page

After deleting the introductory comments in the downloaded code file:

- `downloads/performance-analytics-master/00-start/index.html`

it matches the demo code in the page for this step, so there is no need to copy-and-paste.

Running the python SimpleHTTPServer alleviates the need to download and run
the Web Server for Chrome:

```
golcl
cd 02-google_analytics/downloads/performance-analytics-master/00-start
python -m SimpleHTTPServer
```

Access the page at: http://localhost:8000/

## Section 5 - Step 1: Measuring when the CSS is done blocking

- "CSS blocks the rendering of DOM elements as well as the execution of scripts that come after it in the DOM."
- Use `performance.mark('css:unblock');` from MDN's User Timing API to learn when CSS is done blocking
- Reloading page takes a long time, because an image is missing
- Console output, once it finally stops loading:
  - CSS unblock 69.19999999692664

## Section 6 - Step 2: Measuring when web fonts are active

- "update the main document to use `webfont.js` to load the fonts"
  - Update code in `index.html`
  - Note: code calls `performance.mark('fonts:active');`
- Create promise to log message to console when fonts are loaded
  - Update code in `perf-analytics.js`

## Section 7 - Step 3: Measuring when images are visible

- Modern browsers have a preload scanner
  - Before constructing the DOM, it scans the HTML looking for assets it can download immediately
- When the image is added to the DOM:
  - if it is present, then it becomes visible immediately,
  - else it fires an `onload` event when it becomes visible
- Must add timing marks for both cases:
  - Call performance.mark in a script tag that appears in the DOM after all img tags (covers case when preload scanner loaded image)
  - Call performance.mark when the onload event fires for each image (covers case when image is loaded after appearing n DOM)
- `performance.measure` always uses the last timing mark set
  - Using the last timing mark allows us to determine when all images are visible on the page

## Section 8 - Step 4: Measuring when JavaScript has finished executing

- Add call to `performance.mark('js:execute');` after the last script tag without the `async` attribute in `index.html`
- Add function `function measureJavaSciptExecutionTime` , to calculate the duration, to `perf-analytics.js`

## Section 9 - Step 5: Handling unsupporting browsers

- Use feature detection to deal with this
- Before using the `performance.mark()` method, test for it, to ensure it's available
- Make these changes in `index.html`:
  - Include this before calling `performance.mark`:
  - `<script>window.__perf = window.performance && performance.mark;</script>`
  - Before calling `performance.mark`, ensure `__perf` is set:
  - `<img onload="__perf && performance.mark('img:visible')" src="...`
- Make these changes in `perf-analytics.js`:
  - Update function measureDuration to check `window.__perf` before doing anything
  - Update function measureWebfontPerfAndFailures to check for `window.Promise` before calling it

## Section 10 - Step 6: Capturing these measurements in Google Analytics

- Page must have the Google Analytics tracking snippet
  - Update `index.html` with the tracking snippet
- Must also include google's `analytics.js` javascript library
  - Code snippet for this step uses the debug version, `analytics)debug.js`
- To send timing data to Google Analytics:
  - `ga('send', 'timing', timingCategory, timingVar, timingValue);`
- Update function `measureDuration` in `perf-analytics.js` to:
  - Ensure the new `window.__perf` variable is set (see the last step)
  - Return a value rounded to an integer
- Update function `measureCssUnblockTime` in `perf-analytics.js` to:
  - Log the css unblock time only if there's a value
  - Call the `ga` function to log the timing data - instead of logging it to the console
- Update function `measureWebfontPerfAndFailures` in `perf-analytics.js` to:
  - Log the css unblock time only if there's a value
  - Call the `ga` function to log the timing data - instead of logging it to the console
- Update function `measureImagesVisibleTime` in `perf-analytics.js` to:
  - Log the css unblock time only if there's a value
  - Call the `ga` function to log the timing data - instead of logging it to the console
- Update function `measureJavaSciptExecutionTime` in `perf-analytics.js` to:
  - Log the css unblock time only if there's a value
  - Call the `ga` function to log the timing data - instead of logging it to the console
- Update function `measureWebfontPerfAndFailures` in `perf-analytics.js` to:
  - Call the `ga` function to log an error loading the fonts, rather than log it to the console
  - I.e., replace the `console.log` statement in the `catch` clause to the following:
  - `ga('send', 'event', 'Fonts', 'error');`
