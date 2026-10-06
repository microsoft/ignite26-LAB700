# Exercise 2: Explore Salesforce discovery

In this exercise, you review what Dynamics 365 Activate discovered in the connected Salesforce org. You visit each page under **SF Discovery** so you know what the tool assessed before you migrate any data.

> **Note:** The numbers in the screenshots come from the demo project. Your counts can differ slightly, but the pages and layout are the same.

## Task 1: Open SF Discovery and review the overview

The **SF Discovery** overview is the starting point for every discovery category, and it summarizes what was assessed.

1. In the left navigation, select **SF Discovery** to expand its sub-pages.

1. Under **SF Discovery**, select **Overview** to display the **Discovery Results** page.

1. On the **Discovery Results** page, review the category cards, such as **Objects & Relationships**, **Flows & Automation**, and **Apex Code**.

    ![SF Discovery overview with the discovery category cards](../img/d365a-sfdisco-ovw01.png "SF Discovery - Overview")

1. Scroll down to review the remaining category cards.

    ![SF Discovery overview, remaining category cards](../img/d365a-sfdisco-ovw02.png "SF Discovery - Overview, continued")

    > **Important:** Do not select **Refresh** or **Export Report** in this lab, because they re-run discovery or generate files.

===

## Task 2: Review objects and relationships

The **Objects** page is the most important discovery page for the Account migration, because it scores every Salesforce object by business priority and complexity.

1. Under **SF Discovery**, select **Objects** to open **Objects & Relationships**.

1. At the top of the page, review the summary tiles for total objects, custom objects, high business priority, high complexity, relationships, and recommended skips.

    ![Objects and Relationships summary tiles and filters](../img/d365a-sfdisco-objects01.png "SF Discovery - Objects summary")

1. Under the tabs, notice the **In scope**, **Out of scope**, and **All** filters, which control which objects the list shows.

    > **Note:** Changing these filters changes only the view, not the migration scope.

1. Scroll down to the **Wave 1** group, and then locate the **Opportunity**, **Account**, and **Contact** rows.

    ![Wave 1 object list showing Opportunity, Account, and Contact with priority and complexity scores](../img/d365a-sfdisco-objects02.png "SF Discovery - Objects, Wave 1")

    > **Why this matters:** Activate recommends migration waves from business priority and complexity, so high-priority objects such as Account are loaded first.

1. Continue scrolling to review the remaining objects in the list.

    ![Object list, further down the page](../img/d365a-sfdisco-objects03.png "SF Discovery - Objects, continued")

    ![Object list, further down the page](../img/d365a-sfdisco-objects04.png "SF Discovery - Objects, continued")

===

## Task 3: Review flows, Apex, and business processes

These pages show the automation in Salesforce that has no direct one-to-one equivalent in Dynamics 365, which helps you plan what must be rebuilt.

1. Under **SF Discovery**, select **Flows** to open **Flows & Automation**.

1. On the **Flows** page, review the message and the migration analysis tiles.

    ![Flows page showing no flows found and the migration analysis tiles](../img/d365a-sfdisco-flows01.png "SF Discovery - Flows")

    ![Flows page, migration waves guide](../img/d365a-sfdisco-flows02.png "SF Discovery - Flows, continued")

    > **Note:** This demo org has no flows, so the page reports **No Flows Found**.

1. Under **SF Discovery**, select **Apex** to open the **Apex Code** page.

1. On the **Apex** page, review the tiles for custom classes, test classes, custom triggers, lines of code, and average complexity.

    ![Apex page summary tiles and filter bar](../img/d365a-sfdisco-apex01.png "SF Discovery - Apex")

1. Scroll down to review the class and trigger lists.

    ![Apex classes and triggers lists](../img/d365a-sfdisco-apex02.png "SF Discovery - Apex, classes")

    ![Apex code complexity details](../img/d365a-sfdisco-apex03.png "SF Discovery - Apex, details")

    ![Apex code complexity details, continued](../img/d365a-sfdisco-apex04.png "SF Discovery - Apex, continued")

1. Under **SF Discovery**, select **Business Processes** to open **Business Process Automation**.

1. On the **Business Processes** page, review the counts for workflow rules, affected objects, and Power Automate candidates.

    ![Business Process Automation page with workflow rule counts](../img/d365a-sfdisco-bizproc01.png "SF Discovery - Business Processes")

    ![Business Process Automation migration recommendations](../img/d365a-sfdisco-bizproc02.png "SF Discovery - Business Processes, continued")

===

## Task 4: Review Lightning UI and usage analysis

The **Lightning UI** and **Usage & Tech Debt** pages help you decide what to rebuild and what to leave behind.

1. Under **SF Discovery**, select **Lightning UI** to open **Lightning UI Components**.

1. On the **Lightning UI** page, review the tiles for pages found, components, native Dynamics 365 coverage, and zero-code coverage.

    ![Lightning UI Components summary tiles](../img/d365a-sfdisco-lightning01.png "SF Discovery - Lightning UI")

1. Scroll down to the **Lightning Components → D365 Recommendations** table to see the AI-recommended Dynamics 365 replacement for each component.

    ![Lightning components to Dynamics 365 recommendations table](../img/d365a-sfdisco-lightning02.png "SF Discovery - Lightning UI, recommendations")

    > **Note:** AI-generated content can be incorrect, so always review recommendations before you use them.

    ![Lightning UI recommendations, continued](../img/d365a-sfdisco-lightning03.png "SF Discovery - Lightning UI, continued")

    ![Lightning UI recommendations, continued](../img/d365a-sfdisco-lightning04.png "SF Discovery - Lightning UI, continued")

1. Under **SF Discovery**, select **Usage & Tech Debt** to open **Usage Analysis & Tech Debt Reduction**.

1. On the **Usage & Tech Debt** page, review the number of objects and fields that you could skip, such as empty or unused objects.

    ![Usage Analysis and Tech Debt Reduction summary](../img/d365a-sfdisco-usage01.png "SF Discovery - Usage & Tech Debt")

    ![Objects recommended to skip](../img/d365a-sfdisco-usage02.png "SF Discovery - Usage & Tech Debt, objects to skip")

    ![Usage analysis, continued](../img/d365a-sfdisco-usage03.png "SF Discovery - Usage & Tech Debt, continued")

    ![Usage analysis, continued](../img/d365a-sfdisco-usage04.png "SF Discovery - Usage & Tech Debt, continued")

    > **Why this matters:** Skipping unused objects reduces migration time and avoids carrying tech debt into Dynamics 365.

===

## Task 5: Review packages, picklists, and integrations

These pages cover shared configuration that Account and other objects depend on.

1. Under **SF Discovery**, select **ISV Packages** to display the installed Salesforce packages.

    ![ISV Packages summary and first package card](../img/d365a-sfdisco-isv01.png "SF Discovery - ISV Packages")

    ![ISV Packages, further down the page](../img/d365a-sfdisco-isv02.png "SF Discovery - ISV Packages, continued")

    ![ISV Packages, further down the page](../img/d365a-sfdisco-isv03.png "SF Discovery - ISV Packages, continued")

    ![ISV Packages, further down the page](../img/d365a-sfdisco-isv04.png "SF Discovery - ISV Packages, continued")

1. Under **SF Discovery**, select **Global Picklists** to display the shared value sets and how many values each one holds.

    ![Global Picklists summary and value set table](../img/d365a-sfdisco-picklist01.png "SF Discovery - Global Picklists")

    ![Global Picklists, continued](../img/d365a-sfdisco-picklist02.png "SF Discovery - Global Picklists, continued")

1. Under **SF Discovery**, select **Integrations** to display connected apps, external client apps, and other external connections.

    ![Integrations and External Connections summary](../img/d365a-sfdisco-integr01.png "SF Discovery - Integrations")

    ![Integrations, continued](../img/d365a-sfdisco-integr02.png "SF Discovery - Integrations, continued")

    > **Note:** A count of zero for connected apps can mean none exist or that the discovery user lacks permission, so treat it as "none found" rather than a confirmed absence.

===

## Task 6: Review languages, licenses, and the security model

These pages tell you which languages, currencies, licenses, and security structures you must recreate in Dynamics 365.

1. Under **SF Discovery**, select **Languages & Currency** to review the languages, translations, and currencies in use.

    ![Languages and Currency discovery](../img/d365a-sfdisco-locale01.png "SF Discovery - Languages & Currency")

    ![Languages and Currency, continued](../img/d365a-sfdisco-locale02.png "SF Discovery - Languages & Currency, continued")

1. Under **SF Discovery**, select **Licenses** to review active users, license types, and license usage.

    ![Licenses and User Assignments summary](../img/d365a-sfdisco-license01.png "SF Discovery - Licenses")

    ![Licenses table](../img/d365a-sfdisco-license02.png "SF Discovery - Licenses, continued")

    ![Licenses, continued](../img/d365a-sfdisco-license03.png "SF Discovery - Licenses, continued")

    ![Licenses, continued](../img/d365a-sfdisco-license04.png "SF Discovery - Licenses, continued")

1. Under **SF Discovery**, select **Security Model** to review roles, profiles, permission sets, and record types.

    ![Security Model summary and Dynamics migration summary](../img/d365a-sfdisco-security01.png "SF Discovery - Security Model")

    ![Security Model, continued](../img/d365a-sfdisco-security02.png "SF Discovery - Security Model, continued")

    > **Why this matters:** The **Dynamics Migration Summary** estimates how many Dynamics 365 security roles and business units you need to create.

**Checkpoint:** You have visited every page under **SF Discovery** without changing any settings.
