Geoblocking
===========

Control who can access your website based on their geographical location with iGelGiz's Geoblocking feature. This powerful tool allows you to restrict access from entire countries, helping you manage regional content rights, comply with local regulations, reduce targeted attacks, or simply focus your website on your intended audience.

Accessing Geoblocking Settings
------------------------------
1.  In your WordPress admin dashboard, navigate to **iGelGiz**.
2.  Click on the **Geoblocking** tab.

.. image:: /img/geoblocking.png
   :alt: Geoblocking Settings
   :width: 600px
   :align: center

Available Options
-----------------

.. _enable-geoblocking:

Enable Geoblocking
~~~~~~~~~~~~~~~~~~
*   **What it does:** Activates the geoblocking functionality. When enabled, visitors from countries on your blocklist will be denied access to your site.
*   **Configuration:**
    *   Check the box labeled: "Block visitors from specified countries."
*   **Why it's great for you:**
    *   **Targeted Audience:** Ensure your content is primarily viewed by visitors from regions you serve.
    *   **Compliance:** Help meet legal or licensing requirements that restrict content distribution to certain geographical areas.
    *   **Security:** Block traffic from countries known for high levels of malicious activity or spam.

.. _blocked-country-codes:

Blocked Country Codes
~~~~~~~~~~~~~~~~~~~~~
*   **What it does:** This is where you specify which countries should be blocked.
*   **Configuration:**
    *   In the text area labeled "Blocked Country Codes," enter a comma-separated list of **ISO 3166-1 alpha-2 country codes**. These are standard two-letter codes (e.g., `CN` for China, `RU` for Russia, `KP` for North Korea).
    *   Make sure to use the correct uppercase two-letter codes.
*   **Why it's great for you:**
    *   **Precise Control:** Block specific countries based on your needs.
    *   **Easy to Use:** Standard country codes make it simple to create your list.
*   **Example:** To block visitors from China, Russia, and Iran, you would enter: `CN,RU,IR`
*   **Finding Country Codes:** You can easily find ISO 3166-1 alpha-2 codes with a quick web search (e.g., "ISO country codes").

.. _message-for-blocked-countries:

Message for Blocked Countries
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~
*   **What it does:** Allows you to set a custom message that will be displayed to visitors attempting to access your site from a blocked country.
*   **Configuration:**
    *   Enter your message in the text area labeled "Message for Blocked Countries."
*   **Why it's great for you:**
    *   **Informative:** Clearly communicates to the visitor why they cannot access the site.
    *   **Manages Expectations:** Can direct users to alternative resources if applicable or simply state the access restriction.

Saving Settings
---------------
After configuring your geoblocking rules, click the **"Save Plugin Settings"** button to apply them.

**How Geoblocking Works (Simplified):**
When a visitor tries to access your site, iGelGiz attempts to determine their country of origin based on their IP address using a third-party geolocation service. If their country is on your blocklist, they will be denied access and shown your custom message. The results of these lookups are temporarily cached to improve performance for subsequent visits from the same IP.

**Important Considerations:**
*   **Accuracy:** IP-based geolocation is generally reliable but not 100% foolproof. Users employing VPNs or proxies might bypass these restrictions or be misidentified.
*   **Legitimate Users:** Be mindful not to inadvertently block legitimate users or services (like search engine bots, though they are typically not blocked by this feature as it targets end-user access).

Geoblocking gives you an effective way to tailor your website's accessibility to a global audience, enhancing security and ensuring compliance where needed.
