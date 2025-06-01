Troubleshooting
===============

This section provides guidance on common issues you might encounter while using the iGelGiz plugin and how to resolve them.

General Troubleshooting Steps
-----------------------------

Before diving into specific issues, try these general steps:

1.  **Clear Caches:**
    *   **Plugin Cache:** If you are using any caching plugins (e.g., WP Rocket, LiteSpeed Cache, W3 Total Cache), clear all caches.
    *   **Server Cache:** If your hosting provider uses server-level caching (e.g., Varnish, Memcached), try clearing that as well.
    *   **Browser Cache:** Clear your web browser's cache and cookies, or try accessing your site in an incognito/private browsing window.

2.  **Check for Plugin Conflicts:**
    *   Temporarily deactivate all other plugins except iGelGiz.
    *   Test if the issue persists.
    *   If the issue is resolved, reactivate your other plugins one by one, testing after each activation, to identify the conflicting plugin.

3.  **Check for Theme Conflicts:**
    *   Temporarily switch to a default WordPress theme (e.g., Twenty Twenty-One, Twenty Twenty-Two).
    *   Test if the issue persists. If it's resolved, the issue lies within your theme.

4.  **Ensure Plugin is Updated:**
    *   Make sure you are running the latest version of iGelGiz. Check for updates under **Dashboard > Updates** or **Plugins**.

5.  **Check PHP Version:**
    *   iGelGiz requires a minimum PHP version (as specified in the plugin details). Ensure your server meets this requirement. You can usually check your PHP version via your hosting control panel or by using a plugin like "Display PHP Version."

6.  **Enable WordPress Debugging:**
    *   To get more detailed error messages, you can enable WordPress debugging. Add the following lines to your `wp-config.php` file (before `/* That's all, stop editing! Happy publishing. */`):
      .. code-block:: php

         define( 'WP_DEBUG', true );
         define( 'WP_DEBUG_LOG', true );
         define( 'WP_DEBUG_DISPLAY', false );
         @ini_set( 'display_errors', 0 );
    *   This will log errors to a `wp-content/debug.log` file, which can provide clues. Remember to disable debugging on a live site after troubleshooting.

7.  **Check Activity Log:**
    *   If you have Verbose Logging enabled in iGelGiz (under Form Protection settings), check the "Activity Log" tab for any relevant entries that might indicate what the plugin is doing or blocking.

Specific Issues
---------------

.. _issue-feature-not-working:

A Feature Doesn't Seem to Be Working
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~
*   **Symptom:** You've enabled a feature in iGelGiz settings, saved it, but it doesn't appear to have any effect on the frontend of your site.
*   **Solutions:**
    1.  **Save Settings:** Double-check that you clicked the "Save Plugin Settings" button after enabling the feature.
    2.  **Caching:** This is the most common culprit. Aggressively clear all levels of caching as described in "General Troubleshooting Steps."
    3.  **JavaScript Errors:** Some features rely on JavaScript. Open your browser's developer console (usually by pressing F12) and check the "Console" tab for any JavaScript errors. These errors might prevent iGelGiz's scripts from running.
    4.  **.htaccess (for Hotlink Protection):** Hotlink protection requires an Apache server and writeable `.htaccess` file.
        *   Ensure your `DOCUMENT_ROOT/.htaccess` file is writable by WordPress.
        *   Check if other plugins or manual `.htaccess` rules are conflicting.
        *   After saving settings, check your `.htaccess` file to see if iGelGiz rules were added.
    5.  **Plugin/Theme Conflict:** Follow the conflict checking steps above.

.. _issue-blocked-legitimate-user:

Accidentally Blocked Yourself or a Legitimate User/Bot
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~
*   **Symptom:** You, a user, or a service (like a search engine bot) is being blocked from accessing the site or parts of it.
*   **Solutions:**
    *   **Rate Limiting:**
        *   If blocked by IP, add your IP address or the legitimate service's IP to the "Whitelisted IP Addresses" under the "Rate Limiting" tab.
        *   You might need to access your site from a different IP/network temporarily or wait for the temporary block (usually a few minutes) to expire to make this change.
    *   **User Agent Blocking:**
        *   Review the "Banned User Agent Strings" list under the "User Agent Blocking" tab. If a legitimate bot's User Agent string (or a part of it) is in the list, remove or refine that entry.
        *   Be cautious with broad User Agent strings.
    *   **Geoblocking:**
        *   Check the "Blocked Country Codes" list under the "Geoblocking" tab. If a country is mistakenly blocked, remove its code.
        *   Note that IP-to-location services are not always 100% accurate. A user near a border might occasionally be misidentified.
    *   **Form Protection (Honeypot):**
        *   Rarely, a legitimate user might trigger the honeypot if their browser extensions or actions mimic bot behavior. If this is reported, check the Activity Log for details. There isn't a direct whitelist for the honeypot, but ensuring the user isn't using aggressive script blockers or form-filling tools might help.

.. _issue-site-slowdown:

Website Seems Slower After Activating iGelGiz
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~
*   **Symptom:** Your website's loading speed has noticeably decreased after activating iGelGiz or enabling certain features.
*   **Solutions:**
    1.  **Verbose Logging:** If "Verbose Logging" is enabled (under Form Protection settings), especially on a high-traffic site, it can contribute to database load. Consider disabling it if not actively debugging, or clear logs periodically.
    2.  **Geoblocking API Calls:** The geoblocking feature makes an external API call to determine a visitor's country. While results are cached, the initial call for a new IP adds a small overhead. On very high-traffic sites with many new visitors, this could be a factor.
    3.  **Feature-Specific Impact:** Most features are lightweight. However, if you have extremely long lists for User Agent Blocking or complex regex (if that were an option, which it isn't by default), it could theoretically add processing time.
    4.  **Server Resources:** Ensure your hosting server has adequate resources (CPU, memory).
    5.  **Conflict Check:** A conflict with another plugin could manifest as a performance issue.

.. _issue-htaccess-not-writable:

Hotlink Protection or Other .htaccess Features Not Working
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~
*   **Symptom:** Hotlink protection rules are not being applied.
*   **Solutions:**
    1.  **Server Type:** iGelGiz's `.htaccess` modifications are for Apache servers. If you are on Nginx, LiteSpeed (with Apache compatibility), or IIS, these rules won't work directly. You'd need to translate them to your server's configuration format manually.
    2.  **File Permissions:** Ensure your root `.htaccess` file is writable by the web server/PHP process. WordPress needs this to update the file.
    3.  **Conflicting Rules:** Other plugins or manual entries in `.htaccess` might conflict with or override iGelGiz's rules. Check the order and syntax of rules in your `.htaccess` file. iGelGiz rules are usually added within `# BEGIN iGelGiz` and `# END iGelGiz` markers.
    4.  **`AllowOverride` Directive (Apache):** Ensure the `AllowOverride` directive in your Apache configuration (e.g., `httpd.conf` or virtual host config) is set to `All` or at least includes `FileInfo` or `Indexes` for the directory where WordPress is installed. This allows `.htaccess` files to function. You might need to contact your host for this.

If you've gone through these steps and are still facing issues, please refer to the :doc:`support` section.
