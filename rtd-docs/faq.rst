Frequently Asked Questions (FAQ)
================================

Here are answers to some common questions about the iGelGiz plugin.

.. contents::
   :local:
   :depth: 1

General
-------
Q: I've enabled a feature, but it doesn't seem to be working. What should I do?
   A: First, ensure you've saved the settings after making changes. Second, clear ALL caches: your WordPress caching plugin(s), server-side caches (if any), and your browser cache. Some features, like Hotlink Protection, depend on server configuration (Apache for ``.htaccess``). If issues persist, check the Activity Log (if Verbose Logging is enabled) for any relevant entries. Refer to the :doc:`troubleshooting` guide for more detailed steps.

Q: I accidentally blocked myself or a legitimate user/bot. How can I fix this?
   A:
    *   **Rate Limiting/Bot Detection:** If you're blocked by IP, you can add your IP to the "Whitelisted IP Addresses" under the "Rate Limiting" tab. You might need to access your site from a different IP address or network temporarily to make this change, or wait for the temporary block to expire (usually a few minutes).
    *   **User Agent Blocking:** If a legitimate bot is blocked, review your "Banned User Agent Strings" list and remove or refine the entry that's causing the block.
    *   **Geoblocking:** If a country is mistakenly blocked, remove its code from the "Blocked Country Codes" list.

Q: Will iGelGiz slow down my website?
   A: iGelGiz is designed to be lightweight. Most features have minimal impact on site performance. Features like extensive "Verbose Logging" on a very high-traffic site, or the initial API call for "Geoblocking" for new IPs, could have a minor impact. Generally, the plugin is optimized for performance. If you notice a slowdown, check the :doc:`troubleshooting` section.

Q: How often is the pre-defined list of bad User Agents updated?
   A: The list of bad User Agents, especially for AI crawlers, is updated with plugin updates as new threats emerge and are identified. Ensure your plugin is kept up to date to benefit from the latest definitions.

Q: Can I use iGelGiz with a Content Delivery Network (CDN)?
   A: Yes, iGelGiz generally works well with CDNs. However, be mindful of how IP detection works. Most CDNs (like Cloudflare) add an HTTP header (e.g., `HTTP_CF_CONNECTING_IP`, `HTTP_X_FORWARDED_FOR`) with the original visitor's IP. iGelGiz attempts to use these common headers to get the correct IP for features like Rate Limiting and Geoblocking. Ensure your CDN is configured to pass the original visitor IP correctly.

Features
--------
Q: Does Hotlink Protection work on Nginx servers?
   A: The Hotlink Protection feature in iGelGiz primarily works by adding rules to the ``.htaccess`` file, which is specific to Apache web servers (and compatible servers like LiteSpeed). For Nginx, you would need to manually add equivalent Nginx rewrite rules to your server configuration. iGelGiz does not automatically configure Nginx.

Q: Is the "Right-Click Mitigation" foolproof for protecting content?
   A: No, it's not foolproof. It's a deterrent for casual users. Determined individuals can still access content by disabling JavaScript, using browser developer tools, or taking screenshots. For stronger image protection, consider watermarking or other server-side solutions in addition to iGelGiz's features.

Q: How accurate is Geoblocking?
   A: Geoblocking relies on an IP-to-location database service. While generally accurate, these services are not 100% infallible. There can be occasional misidentifications, especially for users near borders or those using VPNs/proxies. The accuracy depends on the third-party service used for IP lookup.

Q: Will "Disable RSS Feeds" affect my email newsletter if it uses RSS?
   A: Yes, if your email newsletter service pulls content directly from your site's RSS feeds, disabling them will break that functionality. Consider if you have any services relying on your RSS feeds before enabling this option.
