---
layout: docs_page
title: Platform Release Notes
excerpt: Summary of changes to the Okta Platform since Release 2017.20
---

## Release 2017.22

### Advance Notice: API Rate Limit Improvements

We are making org-wide rate limits more granular, and treating authenticated end-user interactions separately. More granular rate limits lessen the likelihood of calls to one URI impacting another. Treating authenticated end-user interactions separately lessens the chances of one user's request impacting another. We’re also providing a transition period so you can see what these changes look like in your Okta system log before enforcing them:

#### Preview Orgs

1. We enforce new rate limits for new preview orgs. For these new orgs, the API calls exceeding the new rate limits return an HTTP 429 error.

2. At the end of May, we'll enforce these new rate limits for all preview orgs. Instead of alerts in your System Log, the API calls exceeding the new rate limits will return an HTTP 429 error.

#### Production Orgs

1. As of May 8, we have enabled a System Log alert which lets you know if you have exceeded any of the new API rate limits:

    ```
    Warning: requests for url pattern <url-pattern> have reached 
    a threshold of <number> requests per <time-duration>. Please 
    be warned these rate limits will be enforced in the near future.
    ```

2. As of mid-May, we've started enforcing these new rate limits for all newly created orgs. For these new orgs, instead of alerts in your System log, the API calls exceeding the new rate limits return an HTTP 429 error.

3. In early June, we'll enforce these new rate limits for all orgs, and instead of alerts in your System Log, the API calls exceeding the new rate limits will return an HTTP 429 error.

For a full description of the new rate limits, see [API Rate Limit Improvements](https://support.okta.com/help/articles/Knowledge_Article/API-Rate-Limit-Improvements).<!-- OKTA-110472 -->

<!-- ### Platform New Features -->

### Platform Bugs Fixed

* OIDC/OAuth2 requests failed to respect default SAML IdP configuration. (OKTA-127155)
* Using password type grant flow for an Active Directory user sometimes results in malformed response instead of access token. (OKTA-121082)

### Does Your Org Have This Change Yet?

To verify the current release for an org, click the **Admin** button and check the footer of the Dashboard page.

{% img release_notes/version_footer.png alt:"Release Number in Footer" %}

### Looking for Something Else?

* [Platform Release Note Index](platform-release-notes2016-index.html)
* For changes outside the Okta platform, see the [Product Release Notes](https://help.okta.com/en/prev/Content/Topics/ReleaseNotes/preview.htm).

