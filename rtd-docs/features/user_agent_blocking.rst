User Agent Blocking
===================

Take precise control over who and what can access your website with iGelGiz's User Agent Blocking feature. This allows you to block requests based on their "User Agent" string, a piece of information browsers and bots send to identify themselves. It's particularly effective against known bad bots, content scrapers, and even unwanted AI crawlers.

Accessing User Agent Blocking Settings
--------------------------------------
1.  In your WordPress admin dashboard, navigate to **iGelGiz**.
2.  Click on the **User Agent Blocking** tab.

.. image:: /img/user_agent_blocking.png
   :alt: User Agent Blocking Settings
   :width: 600px
   :align: center

Available Options
-----------------

.. _enable-user-agent-banning:

Enable User Agent Banning
~~~~~~~~~~~~~~~~~~~~~~~~~
*   **What it does:** When checked, this activates the blocking mechanism. Any incoming request whose User Agent string matches an entry in your banned list will be denied access.
*   **Configuration:**
    *   Check the box labeled: "Blocks requests from User Agents matching the list below."
*   **Why it's great for you:**
    *   **Targeted Defense:** Specifically block known nuisances without affecting legitimate traffic.
    *   **Content Protection:** A key tool in preventing your unique content from being scraped or used by AI models without your consent.

.. _banned-user-agent-strings:

Banned User Agent Strings
~~~~~~~~~~~~~~~~~~~~~~~~~
*   **What it does:** This is where you define the list of User Agent strings that should be blocked.
*   **Configuration:**
    *   Enter User Agent strings into the text area labeled "Banned User Agent Strings," with **one entry per line**.
    *   You can use partial strings (e.g., `BadBot`) or full User Agent strings. If a request's User Agent *contains* any string from this list, it will be blocked.
    *   **Pre-filled List:** iGelGiz comes with a helpful, pre-defined list of common bad bots and AI/LLM crawlers (such as `GPTBot`, `Google-Extended`, `ClaudeBot`, `PerplexityBot`, `Bytespider`, `AhrefsBot`, `SemrushBot`, and many others). This list is regularly reviewed and updated with new plugin versions.
*   **Why it's great for you:**
    *   **Stop AI Scrapers:** Protect your valuable content from being ingested by AI language models for training purposes if you don't want it to be.
    *   **Block Known Bad Bots:** Easily block common spambots, scrapers, and vulnerability scanners.
    *   **Customizable:** Add any specific User Agents you identify as problematic for your site.
    *   **Reduce Server Load:** Blocking unwanted bots can free up server resources.
*   **Caution:** Be careful not to accidentally block legitimate search engine crawlers (like `Googlebot`, `Bingbot`) unless you have a specific reason to do so, as this can negatively impact your site's SEO. The default list is curated to avoid blocking major beneficial bots.

.. _message-for-blocked-user-agents:

Message for Blocked User Agents
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~
*   **What it does:** Customize the message that is shown to a visitor (or bot) whose request is blocked due to a matching User Agent.
*   **Configuration:**
    *   Enter your desired message in the text area labeled "Message for Blocked User Agents."
*   **Why it's great for you:**
    *   **Clear Communication:** Provides a reason for the access denial.
    *   **Deterrent:** Can discourage persistent bots if they receive a clear block message.

Saving Settings
---------------
Ensure you click the **"Save Plugin Settings"** button after making changes to this section.

User Agent Blocking empowers you to be the gatekeeper of your website, selectively denying access to undesirable bots and crawlers. This is an essential feature for modern website owners looking to protect their content, especially from the ever-growing landscape of AI data collection.
