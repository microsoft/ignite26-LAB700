# Exercise 2: Explore Salesforce discovery

In this exercise, you review what Dynamics 365 Activate discovered in the connected Salesforce org, and you limit the migration scope to the two objects that you migrate later. You visit each page under **SF Discovery** so you know what the tool assessed before you migrate any data.

> **Note:** The numbers in the screenshots come from the lab Salesforce org. Your counts can differ slightly, but the pages and layout are the same.

## Task 1: Open SF Discovery and review the overview

The **SF Discovery** overview is the starting point for every discovery category, and it summarizes what was assessed.

1. In the left navigation, select **SF Discovery** to expand its sub-pages.

1. Under **SF Discovery**, select **Overview** to display the **Salesforce Discovery** page.

1. Review the category cards, such as **Objects & Relationships**, **Flows & Automation**, and **Apex Code**.

    ![SF Discovery overview with the discovery category cards](../img/d365a-sfdisco-ovw03.png "SF Discovery - Overview")

1. Scroll down to review the remaining category cards.

    ![SF Discovery overview, remaining category cards](../img/d365a-sfdisco-ovw02.png "SF Discovery - Overview, continued")

    > **Important:** Do not select **Refresh** or **Export Report** in this lab, because they re-run discovery or generate files.

===

## Task 2: Review objects and limit the migration scope

The **Objects** page is the most important discovery page for the migration, because it scores every Salesforce object by business priority and complexity.

1. Under **SF Discovery**, select **Objects** to open **Discovery Results**.

1. At the top of the page, review the **Assessment Complete** bar and the summary counts for objects, fields, custom objects, standard objects, relationships, and objects that Activate recommends ignoring.

    ![Discovery Results page with the assessment bar, summary counts, and filters](../img/d365a-sfdisco-objects01.png "SF Discovery - Objects summary")

1. In **Objects & Complexity**, notice the filters for tier, risk, tags, and priority score, the search box, and the **Hide Ignored** button, which control which objects the list shows.

1. Review the first rows, such as **Opportunity** and **Account**. Each row shows the business priority, a complexity score, a risk label, and the recommended **Wave**.

    > **Why this matters:** Activate recommends migration waves from business priority and complexity, so high-priority objects are loaded first.

1. At the top of the page, set **Business Area** to **Platform** to show **Account**, **Contact**, and **Product2**.

    ![Objects page filtered to the Platform business area, showing Account, Contact, and Product2 with an Ignore button on each row](../img/d365a-sfdisco-scope01.png "Filter the objects by the Platform business area")

    > **Why this matters:** Every object stays in scope until you select **Ignore** on it. Ignored objects are skipped in mapping and migration, and you can bring one back with **Opt-in**.

1. Leave **Account** and **Contact** as they are, and select **Ignore** on every other object that is still in scope, starting with **Product2**. Change **Business Area** to **Sales**, **Service**, **Activities**, and **Other** to reach the remaining objects. Select **Hide Ignored** so that each object leaves the list after you ignore it.

    ![Objects page filtered to the Sales business area with Hide Ignored selected, showing the objects that are still in scope and their Ignore buttons](../img/d365a-sfdisco-scope02.png "Ignore the remaining in-scope objects")

    > **Important:** Do not select **Ignore** on **Account** or **Contact**. If you ignore one by mistake, select **Opt-in** on its row to bring it back.

1. Set **Business Area** back to **All** (or select **Clear filters**), and then confirm that only **Account** and **Contact** remain in the list and that the summary shows 2 objects.

    ![Objects page with Business Area set to All, showing only Account and Contact after the other objects are ignored](../img/d365a-sfdisco-scope03.png "Only Account and Contact remain in scope")

    > **Why this matters:** Account and Contact are the two objects you work with in the mapping and migration exercises, so every other object is out of scope and is not mapped or migrated.

===

## Task 3: Review flows, Apex, and business processes

These pages show the automation in Salesforce that has no direct one-to-one equivalent in Dynamics 365, which helps you plan what must be rebuilt.

1. Under **SF Discovery**, select **Flows** to open **Flows & Automation**.

1. On the **Flows** page, review the summary tiles and the list of flows.

    ![Flows page with the summary tiles and the flow list](../img/d365a-sfdisco-flows01.png "SF Discovery - Flows")

1. Scroll down, and then expand a flow to read the AI-recommended migration approach and the reasoning behind it.

    ![Flow details with the AI-recommended migration approach](../img/d365a-sfdisco-flows02.png "SF Discovery - Flows, AI recommendation")

    ![Migration analysis and recommended migration order for flows](../img/d365a-sfdisco-flows03.png "SF Discovery - Flows, migration waves")

    > **Note:** AI recommends a migration approach and explains the reasoning behind the recommendation. Always review recommendations before you act on them.

1. Under **SF Discovery**, select **Apex** to open the **Apex Code** page, and then review the tiles for classes, triggers, lines of code, and complexity.

    ![Apex page summary tiles and filter bar](../img/d365a-sfdisco-apex01.png "SF Discovery - Apex")

1. Scroll down to review the Apex classes, including the AI-recommended Dynamics 365 alternative for each class.

    ![Apex classes with AI migration approach](../img/d365a-sfdisco-apex02.png "SF Discovery - Apex, classes")

1. Continue scrolling to review the Apex triggers.

    ![Apex triggers list](../img/d365a-sfdisco-apex03.png "SF Discovery - Apex triggers")

1. Under **SF Discovery**, select **Business Processes** to open **Business Process Automation**, and then review the counts for workflow rules, affected objects, and Power Automate candidates.

    ![Business Process Automation page with workflow rule counts and recommendations](../img/d365a-sfdisco-bizproc01.png "SF Discovery - Business Processes")

1. Scroll down to review the Dynamics 365 agents and the migration recommendations.

    ![Business Process Automation, agent recommendations](../img/d365a-sfdisco-bizproc02.png "SF Discovery - Business Processes, agent recommendations")

1. Scroll down to **Workflow Rules Details**, and then select a rule to expand it in the process builder.

    ![Workflow rules table](../img/d365a-sfdisco-bizproc03.png "SF Discovery - Business Processes, rules")

    ![Workflow rule visualization in the process builder](../img/d365a-sfdisco-bizproc04.png "SF Discovery - Business Processes, process builder")

===

## Task 4: Review Lightning UI and usage analysis

The **Lightning UI** and **Usage & Tech Debt** pages help you decide what to rebuild and what to leave behind.

1. Under **SF Discovery**, select **Lightning UI** to open **Lightning UI Components**, and then review the tiles for pages found, components, native Dynamics 365 coverage, and zero-code coverage.

    ![Lightning UI Components summary tiles](../img/d365a-sfdisco-lightning01.png "SF Discovery - Lightning UI")

1. Scroll down to the **Lightning Components → D365 Recommendations** table to see the AI-recommended Dynamics 365 replacement for each component.

    ![Lightning components to Dynamics 365 recommendations table](../img/d365a-sfdisco-lightning02.png "SF Discovery - Lightning UI, recommendations")

    ![Lightning UI recommendations, continued](../img/d365a-sfdisco-lightning03.png "SF Discovery - Lightning UI, continued")

    > **Note:** AI-generated content can be incorrect, so always review recommendations before you use them.

1. Under **SF Discovery**, select **Usage & Tech Debt** to open **Usage Analysis & Tech Debt Reduction**, and then review the number of objects and fields that you could skip.

    ![Usage Analysis and Tech Debt Reduction summary](../img/d365a-sfdisco-usage01.png "SF Discovery - Usage & Tech Debt")

    ![Objects recommended to skip](../img/d365a-sfdisco-usage02.png "SF Discovery - Usage & Tech Debt, objects to skip")

    ![Usage analysis, continued](../img/d365a-sfdisco-usage03.png "SF Discovery - Usage & Tech Debt, continued")

    > **Why this matters:** Skipping unused objects reduces migration time and avoids carrying tech debt into Dynamics 365.

===

## Task 5: Review packages, picklists, and integrations

These pages cover shared configuration that other objects depend on.

1. Under **SF Discovery**, select **ISV Packages** to display the installed Salesforce packages.

    ![ISV Packages summary and first package card](../img/d365a-sfdisco-isv01.png "SF Discovery - ISV Packages")

    ![ISV Packages, further down the page](../img/d365a-sfdisco-isv02.png "SF Discovery - ISV Packages, continued")

    ![ISV Packages, further down the page](../img/d365a-sfdisco-isv03.png "SF Discovery - ISV Packages, continued")

1. Under **SF Discovery**, select **Global Picklists** to display the shared value sets and how many values each one holds.

    ![Global Picklists summary](../img/d365a-sfdisco-picklist01.png "SF Discovery - Global Picklists")

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

1. Under **SF Discovery**, select **Security Model** to review roles, profiles, permission sets, and record types.

    ![Security Model summary and Dynamics migration summary](../img/d365a-sfdisco-security01.png "SF Discovery - Security Model")

    ![Security Model, continued](../img/d365a-sfdisco-security02.png "SF Discovery - Security Model, continued")

    ![Security Model, continued](../img/d365a-sfdisco-security03.png "SF Discovery - Security Model, continued")

    > **Why this matters:** The **Dynamics Migration Summary** estimates how many Dynamics 365 security roles and business units you need to create.

**Checkpoint:** You visited every page under **SF Discovery**, and only **Account** and **Contact** are in scope.
