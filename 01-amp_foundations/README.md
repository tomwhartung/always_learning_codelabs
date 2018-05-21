# 01-amp_foundations/README.md

# References

- AMP Validation: https://www.ampproject.org/docs/fundamentals/validate
- Valid CSS: https://www.ampproject.org/docs/design/responsive/style_pages

# Steps

## Steps 1-3: Setup

Download the sample code, unpack it, and check it out in a browser.


```
cd 01-amp_foundations
cd downloads/accelerated-mobile-pages-foundations-master
mv  ~/Downloads/accelerated-mobile-pages-foundations-master.zip .
unzip accelerated-mobile-pages-foundations-master.zip
python -m SimpleHTTPServer
```

- Access in browser: http://localhost:8000/article.html

## Step 4: Build a regular HTML page

```
cp article.html article.amp.html
vi article.amp.html
```

### Step 4.1: Add amp project js file

- Add the AMP js library at the end of the `<head.` tag:
  - `<script async src="https://cdn.ampproject.org/v0.js"></script>`
- Access in browser: http://localhost:8000/article.amp.html

### Step 4.2: Inspect in developer tools

- Inspect in chrome's developer tools
- Access in browser: http://localhost:8000/article.amp.html#development=1
  - Note AMP validation errors in the developer tools' console
- Click on the mobile view icon in developer tools (at the top, second from the left)

## Step 5: Resolve validation errors

### Charset required:

- Add this line to just after the `head` tag:
  - `<meta charset="utf-8" />`

### AMP files are required to have a `<link rel=canonical>` tag:

- Add this line to just after the `meta` tag just added:
  - `<link rel="canonical" href="/article.amp.html">`

### AMP attribute required:

- Add `⚡` or `amp` to the `html` tag, as in the following line:
  - `<html ⚡ lang="en">`

### Viewport required

- Add this line to just after the `meta` tag added previously:
  - `<meta name="viewport" content="width=device-width,minimum-scale=1,initial-scale=1">`

### External stylesheets

- Replace the `link` tag for the external style sheet, i.e.,
  - `<link href="base.css" rel="stylesheet" />`
- with the following style opening and closing tags containing the contents of the `base.css` file
  - `<style amp-custom>`
  - `[entire contents of base.css]`
  - `</style>`

### Third-Party JavaScript

- Remove the following line (there is actually no javascript in the file!):
  - `<script type="text/javascript" src="base.js"></script>`

### The AMP CSS boilerplate

- Add the following line to just before the closing `</head>` tag:
  - <style amp-boilerplate>body{-webkit-animation:-amp-start 8s steps(1,end) 0s 1 normal both;-moz-animation:-amp-start 8s steps(1,end) 0s 1 normal both;-ms-animation:-amp-start 8s steps(1,end) 0s 1 normal both;animation:-amp-start 8s steps(1,end) 0s 1 normal both}@-webkit-keyframes -amp-start{from{visibility:hidden}to{visibility:visible}}@-moz-keyframes -amp-start{from{visibility:hidden}to{visibility:visible}}@-ms-keyframes -amp-start{from{visibility:hidden}to{visibility:visible}}@-o-keyframes -amp-start{from{visibility:hidden}to{visibility:visible}}@keyframes -amp-start{from{visibility:hidden}to{visibility:visible}}</style><noscript><style amp-boilerplate>body{-webkit-animation:none;-moz-animation:none;-ms-animation:none;animation:none}</style></noscript>

### The amp-img tag

- Replace the `<img ...` tag with the following `<amp-img ...` tag:
  - `<amp-img src="mountains.jpg"></amp-img>`
- **Note:** this fixes one error but causes two new errors, and the image has disappeared!
- To fix these errors, continue with the next section

### Layout System

- Add the following `width` and `height` attributes to the `amp-img` tag:
  - `width="266" height="150"`
- **Note:** this fixes the remaining errors!
- However the image does not look that great in the web view
- Add the following `layout` attribute to the `amp-img` tag:
  - `layout="responsive"`

### AMP validation successful.

- Verify the developer tools console contains the message: "AMP validation successful."




