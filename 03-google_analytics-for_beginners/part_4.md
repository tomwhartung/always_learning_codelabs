# 03-google_analytics-for_beginners/part_4.md

Notes for Part 4 of the Digital Analytics for Beginners class at the Analytics Academy.

# Part 4. Basic Campaign and Conversion Tracking

## 4.1 Basic Campaign and Conversion Tracking

This section has a video.
Notes are based on the transcript: https://support.google.com/analytics/answer/6383005?hl=en

### 4.1.1 How to track a marketing campaign

- Marketing campaigns can be a combination of one or more of these techniques:
  - Text ads on search engine results
  - Banner ads on content sites
  - Social media
  - Email campaigns
- Google Analytics can use "campaign tagging" to track campaigns
  - Campaign tags are added to URLs used in online marketing and advertising
  - Google extracts information from these tags and associates them with users and their behaviors
- Example: Google Store sends a monthly email containing links to the Store
  - Adding an "email" campaign tag to these links enables identifying when users click on them
- Campaign tags:
  - Medium: the mechanism, e.g., "email", "cpc", "social"
  - Source: where user is from, depends on medium e.g., "google" or "yahoo" for cpc, or "newsletter" for email
  - Campaign: name of marketing campaign, e.g., "2015-Back-to-School" or "2017-Holiday-Sale"
  - Content: can differentiate between versions of a promotion, e.g., "v1-10dollars-off" or "v2-nopromo"
  - Term: keyword used with paid search engines (bing or yahoo, AdWords covered separately)
- URL Builder tool allows for adding these easily

## 4.2 Tracking campaigns with the URL Builder

This section has a video.
Notes are based on the transcript: https://support.google.com/analytics/answer/6385286?hl=en

### 4.2.1 Tracking campaigns with the URL Builder

- URL Builder: https://ga-dev-tools.appspot.com/campaign-url-builder/
- Fill in URL of site
- Required fields: campaign, source, and medium
- Optional fields: term, content, and name
- All names: case-sensitive, spaces replaced with '_',
- Be sure to use consistent medium names, e.g., "display" for banner ads, "email" for email
- Click "Generate URL" at the bottom
- Copy-and-paste URL
- May be best to use a spreadsheet for complicated campaigns
- Test each URL in an incognito window before deploying and see results in under the Real Time option
  - Acquisition -> Campaigns -> All Campaigns
  - Use filter to find campaign (type campaign name into filter/search bar)
  - Click on campaign name to see source and medium data
  - To see other tags, add "ad content" as a secondary dimension
- Analyzing this data is covered in an advanced class

### 4.2.2 Complete the activity: 3/3

## 4.3 Basic Campaign and Conversion Tracking

This section has a video.
Notes are based on the transcript: https://support.google.com/analytics/answer/6383000?hl=en

### 4.3.1 How to set up Goals in Analytics

- Business goals: actions that you want users to take on the site
  - Conversion: signing up for a newsletter, purchasing a product, watching a video, downloading a pdf, etc.
- Google Analytics goals: created in Google Analytics
  - Tracks conversions and conversion-related metrics
  - Conversion rate: Percentage of users who convert
- Goal Funnel: visualization of the steps needed to accomplish a goal
  - Can optionally set up a goal funnel when creating Google Analytics goals
  - Helps identify where people are dropping off in the process
- Required: must be an administrator on the view
- Maximum of 20 goals per view
- Define business goals, use them to create Google Analytics goals
- Example goal setup: user reaches Google Store chekout confirmation page
  - Does not track revenue, only checkout confirmations
  - Funnel visualization: to learn where users are dropping out of the process
- Goal Setup: Steps
  - Admin -> Views -> Goals
  - New Goal: May look different for different business types
  - Choose template: Buy Merchandise
  - Name goal: "Checkout complete"
  - Goal slot ID: numbered from 1 to 20, default is next available slot
  - Set the Goal type:
    - Destination: user reaches a specific page
    - Duration: of the user's session
    - Pages or screens: number of pages user views per session
    - Events: specific actions, covered in advanced class



## 4.4 Basic Campaign and Conversion Tracking

This section has a video.
Notes are based on the transcript: https://support.google.com/analytics/answer/6382975?hl=en

### 4.4.1 How to use Analytics with AdWords

## 4.5 Basic Campaign and Conversion Tracking

This section has a video.

### 4.5.1 Google Analytics for Beginners Wrap-Up

## 4.6 Assessment 4


