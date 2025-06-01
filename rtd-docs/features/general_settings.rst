General Settings (Core Content Shield)
======================================

The "General Settings" tab in iGelGiz provides fundamental protections for your site's content and user experience. These settings are designed to be easy to configure and offer a first line of defense against common vulnerabilities and annoyances.

Accessing General Settings
--------------------------
1.  In your WordPress admin dashboard, navigate to **iGelGiz**.
2.  Click on the **General Settings** tab.

Available Options
-----------------

.. _prevent-content-framing:

Prevent Content Framing
~~~~~~~~~~~~~~~~~~~~~~~
*   **What it does:** This feature prevents other websites from embedding your site's pages within an ``<iframe>`` or ``<frame>``. This is a crucial security measure to protect against "clickjacking" attacks, where an attacker overlays invisible elements on your site's content embedded on their malicious page, tricking users into performing actions they didn't intend.
*   **How it works:** It adds an ``X-Frame-Options: DENY`` HTTP header to your site's responses.
*   **Configuration:**
    *   Check the box labeled: "Stop other sites from embedding your content within iframes or frames. This helps prevent clickjacking."
*   **When to use it:** It's highly recommended to keep this enabled for most websites to enhance security.
*   **Potential Conflicts:** Very rarely, if you legitimately need to embed parts of your site on another domain you control, this might interfere. In such specific cases, you might need to adjust server-level configurations (outside of this plugin) for more granular control, but for general security, enabling this is best practice.

.. _email-address-protection:

Email Address Protection
~~~~~~~~~~~~~~~~~~~~~~~~
*   **What it does:** This feature automatically obscures email addresses displayed on your site's pages and posts, making it significantly harder for spam bots to harvest them.
*   **How it works:** It converts email addresses into a format that is readable by humans and browsers but difficult for many automated email scrapers to recognize.
*   **Configuration:**
    *   Check the box labeled: "Protect email addresses displayed on your site from being harvested by spam bots."
*   **When to use it:** Enable this if you display email addresses publicly on your site and want to reduce spam.
*   **User Experience:** For users, the email addresses will still appear normal and clickable (if they are links). The protection happens in the background.

.. _disable-rss-feeds:

Disable RSS Feeds
~~~~~~~~~~~~~~~~~
*   **What it does:** This option completely turns off your website's RSS feeds (e.g., ``yourdomain.com/feed/``, comment feeds, category feeds, etc.).
*   **How it works:** When a request is made to an RSS feed URL, iGelGiz will intercept it and return a 404 Not Found error, effectively making the feed unavailable.
*   **Configuration:**
    *   Check the box labeled: "Turn off all RSS feeds (e.g., /feed/) on your site. This can help prevent content scraping via feeds."
*   **When to use it:**
    *   If you don't want your content to be easily syndicated or scraped by automated tools that rely on RSS feeds.
    *   If you don't use RSS feeds for any specific purpose (e.g., email marketing integrations, feed readers).
*   **Considerations:** Disabling RSS feeds means users and services cannot subscribe to your content updates via standard feed readers. If you have a legitimate use case for RSS feeds, keep this option disabled.

.. _right-click-mitigation:

Right-Click Mitigation
~~~~~~~~~~~~~~~~~~~~~~
*   **What it does:** This feature disables the browser's default right-click context menu on your website.
*   **How it works:** It uses JavaScript to prevent the context menu from appearing when a user right-clicks.
*   **Configuration:**
    *   Check the box labeled: "Prevent users from opening the browser's right-click context menu. This can deter casual content copying."
*   **When to use it:** If you want to deter casual users from easily copying text or saving images directly via the right-click menu.
*   **Limitations:**
    *   This is **not a foolproof** content protection method. Users can still access content through browser developer tools, by disabling JavaScript, or by taking screenshots.
    *   It can sometimes be frustrating for users who legitimately use right-click for browser functions (e.g., "Open link in new tab," "Print").
*   **Recommendation:** Use this feature judiciously. It's more of a deterrent than a strong security measure.

.. _prevent-pinterest-pinning:

Prevent Pinterest Pinning
~~~~~~~~~~~~~~~~~~~~~~~~~
*   **What it does:** This feature allows you to control whether images from your site can be pinned to Pinterest. You can either block pinning entirely or allow it but specify a custom message that Pinterest should display.
*   **How it works:** It adds a ``<meta name="pinterest" content="nopin" description="Your custom message here" />`` tag to the ``<head>`` section of your site's HTML.
*   **Configuration:**
    1.  **Enable/Disable:** Check the box "Stop users from pinning images from your site to Pinterest." to activate the "nopin" functionality.
    2.  **Custom Message:** In the text area below the checkbox, you can customize the message that Pinterest will display if someone attempts to pin an image. The default message is: "Pinning images from this site to Pinterest is not allowed. If you have any questions, please contact the site owner. Thank you for your understanding."
*   **When to use it:**
    *   If you have copyrighted images or content that you do not want shared on Pinterest.
    *   If you want to provide specific instructions or context when users try to pin your images.
*   **Note:** This relies on Pinterest respecting the "nopin" meta tag.

Saving Settings
---------------
After making any changes to these options, scroll to the bottom of the page and click the **"Save Plugin Settings"** button to apply them.
