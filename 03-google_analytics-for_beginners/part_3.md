# 03-google_analytics-for_beginners/part_3.md

Notes for Part 3 of the Digital Analytics for Beginners class at the Analytics Academy.

# Part 3. Basic Reporting

## 3.1 Audience reports

This section has a video.

### 3.1.1 Audience reports overview

- Click Audience in the left nav to see characteristics of the site's users
  - Location, language, technology used to access site
  - Also: age, gender, loyalty, and interests
- Active users - in the last: 1, 7, 14, and 28 days
  - Site reach or stickyness: how well site encourages people to return
- Demographics: age and gender
- Interests: users' preferred web content, such as technology, music, travel, or tv
- Are you reaching the right people?
- Gain insights into possible marketing strategies
- To enable:
  - Admin -> Property tab -> Property Settings -> Turn on "Enable Demographics and Interest Reports"

### 3.1.2 Complete the activity:

### 3.1.2.1 First try (WTF?!?)

- 2/3 (Oops, did not notice questions were about a specific date range)
- Their "correct" answer to question 2 seems wrong to me!
- None of the suggested answers to question 3 is right, so I picked the closest

**Note:** did not notice that we were supposed to look at a specific date range, i.e.:

- "Use the dates of Aug 1 2015 - Aug 31 2015 to answer the following questions:"

### 3.1.2.2 Second try (After feeling ok about the "Complete the activity" exercise in the third section)

- 3/3: Much easier now that I have the date range set correctly!

## 3.2 Acquisition reports

This section has a video.

### 3.2.1 Acquisition reports overview

- Click Acquisition in the left nav to compare performance of different marketing channels
  - Discover which sources give the highest quality traffic and conversions
- Tracking code identifies: traffic medium, source, and marketing campaign name
- Traffic Mediums [sic]:
  - Organic: from non-paid search (google or other search engine)
  - CPC: cost per click - from paid search campaign
  - Referral: from link on another site (NOT a search engine)
  - Email: from email marketing campaign
  - (none): from "Direct" source - user typed url into browser address bar
- Source: more information, for example:
  - Referral: source is referring site
  - Organic: source is name of search engine
- Demo Account -> Acquisition -> All Traffic -> Source/Medium report for August, 2015 (no data??)
  - More users does not imply the best traffic
  - Traffic should be high quality: users engage or complete a conversion
  - Bounce rate: can help measure quality of traffic
  - Comparison view -> Bounce Rate metric, compared to site average
- Filter for traffic from google
  - Notice that traffic from google search has lower bounce rate -> higher quality traffic
- Demo Account -> Acquisition -> All Traffic -> Channels report
  - Lists the channels, Direct, Organic search, Referral, etc.
  - Click into channel to see more specific information
  - Can create custom channel groupings in Google Analytics (covered in advanced class)
- Demo Account -> Acquisition -> All Traffic -> Referrals report
  - Click into the referring site to see which pages have the link to my site
  - Add secondary dimension "landing page" (type into text box) to see what page they are coming to

### 3.2.2 Complete the activity

### 3.2.2.1 First try (WTF?!?)

Question 1: **WTF:** Data in the Demo Acct is all zeros in the Acquisition -> All Traffic -> Source/Medium report?!?
- Even for extended date range (Aug. 1, 2015 - May 25, 2018) ?!?
- Correct answer is "youtube.com"

Question 3: **WTF:** None of the suggested answers match what I am seeing ?!?
- Correct answer is "/permissions/using-the-logo.html"

### 3.2.2.2 Second try (After feeling ok about the "Complete the activity" exercise in the third section)

Question 1: Filter by "referral" and sort by New Users (User values are all zeroes?!?)
Question 2: Sort by New Users
Question 3:
1. Sort by Sessions
1. **NOTE:** Answer is not necessarily at the top, only **above** the other options?!?
1. Primary dimension: Source, filter by "google.com" - Bzzt.
1. Tried several things, not seeing any of the options listed!!

## 3.3 Behavior reports

This section has a video.

### 3.3.1 Behavior reports overview

- Click Behavior in the left nav to see how users interact on the site
- Total Pageviews: number of times a user loaded a page on your website
- Behavior -> Site Content -> All Pages, scroll down to data table
  - By default shows the URI - part of the URL after the domain name
  - Click on Page Title to see the page titles instead
  - Measures of engagement include: Avg. time spent on page, Bounce rate
  - Sort by these columns to find low- and high-performing pages
- Behavior -> Site Content -> Content Drilldown report
  - Groups pages according to directory structure
  - Click on directory to drill down into pages within the directory
  - Pie chart view: makes it easy to see which sections are getting the most hits
- Behavior -> Site Content -> Landing Pages report
  - Pages that are first viewed in a session
- Behavior -> Site Content -> Exit Pages report
  - Pages that are viewed last in a session
  - Review periodically for possible issues, e.g., at checkout
- Behavior -> Site Content -> Events reports
  - How users interact with specific elements, e.g., download video, want to see more
  - Covered in an advanced class

### 3.3.2 Complete the activity: 3/3 (Finally, felt like I was seeing the right data!)

## 3.4 Assessment 3:


- Geographical: IP Address gives continent, sub-continent, country, city of user
  - Geographic heat map at top
  - Click on Users pull down, above and to the left of the map to change metrics
  - E.g., New Sessions can help identify new sources of visitors
  - Also: table below can help, e.g., identify regions with unrealized potential:
  - E.g., Large audience but low performance (many visits but they do not stay long)
  - E.g., High bounce rate: consider translating ad or site
- Behavior reports:
  - New vs. Returning: Acquisition, Behavior, Conversions
  - Over time, can reveal how audience is shifting
- Technology: Browser and OS, Network
  - High Bounce Rate: can help identify possible issues with site on certain browsers
- Mobile: Overview and Devices
  - Can help determine whether site is sufficiently optimized for mobile devices
