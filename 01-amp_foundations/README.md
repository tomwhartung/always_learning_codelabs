# 01-amp_foundations/README.md

# References

- AMP Validation: https://www.ampproject.org/docs/fundamentals/validate

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

### Step 5.1: Add amp project js file






