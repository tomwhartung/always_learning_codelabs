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

## 4.3 Using Goals to measure business objectives

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
- **Note:** must be an administrator on the view
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
  - Destination: only goal that supports a funnel
  - Destination URL: of "Order Complete" confirmation page
    - Do NOT use entire URL, use regex: "/SubmitOrder"
  - Goal Value (optional): toggle to "On" and type in amount; use only if a constant value makes sense
    - Leave this off for now
  - Goal Funnel: Switch to "On" to enable adding steps
    - Each step represents an action
    - Find a unique part in the URL for each action
    - Set Required to "Yes" as appropriate
  - Save -> goal appears in the list
- To see Goal metrics:
  - Reporting view -> Conversions -> Goals -> Overview
  - Goal data: also visible in Audience and Acquisition reports
- Funnel visualization:
  - Conversions -> Funnel Visualization report
  - Look for sudden drop-off in users, might be indicative of an issue
- Analytics Solutions Gallery offers many Goals built by other users

### 4.3.2 Complete the activity: 3/3 (on second try)

## 4.4 Basic Campaign and Conversion Tracking

This section has a video.
Notes are based on the transcript: https://support.google.com/analytics/answer/6382975?hl=en

### 4.4.1 How to use Analytics with AdWords

- AdWords: Google's advertising system
- Google Store bids on keywords such as "Google t-shirt" and "Google clothing"
- Linking Google Analytics with Adwords enables:
  - Viewing AdWords click and cost data along with site engagement data in Google Analytics
  - Creating remarketing lists in Analytics for use in AdWords
  - Importing Analytics goals and transactions into AdWords as conversions
  - Viewing Analytics site engagement data in AdWords
- **Note:** Same email account must be an administrator of both accounts
- Process:
  - Analytics -> Select account and property -> Property section -> AdWords linking
  - Click on New link group -> AdWords accounts automatically appear -> Pick one -> Continue
  - Fill in Link Group Title
  - Select view -> Select "Link accounts"
- Auto-tagging: automatically add a special campaign tag to your AdWords URLs
  - Required to get specific AdWords dimensions into Google Analytics
- Available AdWords dimensions:
  - Query match type: how an AdWords keyword is matched to a user search query
  - Ad Group: ad group associated with the keyword or creative
  - Destination URL: AdWords destination URL
  - Ad Format: whether is a text ad, display ad, or video
  - Ad Distribution Network: network used to deliver your ad
  - Placement Domain: domain where your ad was displayed
  - AdWords Customer ID: unique ID of your AdWords account
- This data allows fine-tuning keywords
- Acquisitions reports -> Campaigns-> All Campaigns
  - Campaign Names are from AdWords
  - Can show data for desktop, mobile, and tablets
  - CPC: Average cost per click
- Behavior reports: see user engagement
- Conversions reports: conversion rate and goal completions
- Acquisitions -> AdWords -> Keywords report
  - Look for keywords with a high bounce rate - find a better synonym
  - Look for keywords with a high conversion rate - increase bid
  - Examine using Device Category as a second dimension to see if different words are better on different devices
- Acquisitions -> AdWords -> Bid adjustments report
  - Automatically adjust bid based on device, location, or time of day
  - E.g., increase bids during a sale, or when a mobile device is close to a business location
  - Remarketing: covered in an advanced class

### 4.4.2 Complete the activity: 3/3

## 4.5 Basic Campaign and Conversion Tracking

This section has a video.
Notes are based on the transcript: https://support.google.com/analytics/answer/6382986?hl=en

### 4.5.1 Google Analytics for Beginners Wrap-Up

Topics covered:

- Benefits of digital analysis for businesses
- How Google Analytics works
- How to set up an account, install the tracking code, and set up views of data
- How to read overview and full reports
- How to set up dashboards and shortcuts
- How to understand Audience, Acquisition, and Behavior reports
- How to set up campaign tracking, goals, and measure conversions
- How to link AdWords and Analytics accounts

How to handle some typical use cases:

- Top performing pages for new users:
  - Behavior -> Site Content -> All Pages
  - Add secondary dimension of User Type
- Ineffective landing pages:
  - Behavior -> Site Content -> Landing Pages
  - Sort by Bounce Rate
  - If running campaigns: add secondary dimension of campaign or source/medium
- Understanding how device type affects results
  - Acquisition -> Campaigns -> All Campaigns
  - Add secondary dimension of Device Category
- Optimizing campaigns for specific localities
  - Audience -> Geo -> Location
  - Conversions pull-down (on the right side of the data table's heading) -> select goal
  - Sort by Goal Conversion Rate

"Happy analyzing!"

## 4.6 Assessment 4: 10/10 (After four tries)


