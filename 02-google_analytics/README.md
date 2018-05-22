# 02-google_analytics/README.md

# References

- Test the download and rendering speed of your site: http://www.webpagetest.org/

# Steps

## Steps 1-2: Setup

- Downloaded sample code into `downloads` directory

## Step 3 - Before you begin

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

## Step 4 - Step 0: Viewing the demo page

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




