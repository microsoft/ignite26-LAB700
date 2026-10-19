# Exercise 1: Create your workspace, project, and connections

In this exercise, you sign up for Dynamics 365 Activate, create a workspace and a migration project, choose where migration data is staged, and connect your Salesforce and Dynamics 365 environments. You then start discovery, which every later exercise builds on.

> **Note:** Use the credentials and connection values provided in your lab environment. Never enter customer credentials or production secrets in this lab.

## Task 1: Create a workspace

A **workspace** groups the migration projects of one team, so you create it before your first project.

1. In your browser, go to `https://migrate.dynamics.cloud.microsoft/signup`.

    ![Dynamics 365 Activate sign-up page with the Sign up button](../img/d365a-setup-signup01.png "Sign-up page")

1. Select **Sign up**, and then sign in with your lab account if you are prompted.

1. On the **Tell us about your Dynamics 365 initiative** form, confirm that **Project type** is **Legacy System Migration** and **Legacy source** is **Salesforce**.

    ![Workspace form with project type, legacy source, and target workloads](../img/d365a-setup-workspace01.png "Workspace form - Project and target workloads")

1. In **Workspace**, enter **Ignite Lab 700** as the **Name** and as the **Description**, and then review **Account type**, **Region**, and **Purpose**.

    ![Workspace form with the account type, region, and purpose fields](../img/d365a-setup-workspace02.png "Workspace form - Workspace details")

    > **Note:** If your account already belongs to a workspace, the form shows a **Workspace Found** message and skips this step, as in the screenshot. Select **Dynamics 365 Activate** to continue to that workspace, and use its name wherever this lab says **Ignite Lab 700**.

1. Select **Dynamics 365 Activate** to create the workspace and open the **Migration Projects** page.

===

## Task 2: Create a project

A **project** holds the connection to one Salesforce org and one Dynamics 365 environment, so every migration starts with a new project.

1. On the **Migration Projects** page, confirm that the **Workspace** list shows your workspace.

    ![Migration Projects page with the workspace list and the New Project button](../img/d365a-setup-projects01.png "Migration Projects page")

1. Select **New Project** to open the **Create New Project** dialog.

    ![Create New Project dialog before any values are entered](../img/d365a-setup-newproject01.png "Create New Project dialog")

1. In **Project Name**, enter **Ignite Lab 700 SFDC Migrate**, and then confirm that **Workspace** shows your lab workspace.

    ![Create New Project dialog with the project name and workspace entered](../img/d365a-setup-newproject02.png "Create New Project dialog - Completed")

1. Select **Create Project**, and then confirm that the project selector in the top bar shows your new project.

    ![Welcome page with the new project selected and the Start New Migration button](../img/d365a-setup-newproject03.png "New project selected")

    > **Important:** Do not use a name or identifier that contains credentials or customer information.

===

## Task 3: Explore bring your own storage

Migration data passes through a temporary staging location while records move from Salesforce to Dynamics 365, and you decide who owns that location.

1. On the welcome page, select **Start New Migration** to open the **Start New Migration** dialog.

    ![Start New Migration dialog with the storage, Salesforce, and Dynamics sections](../img/d365a-cfg-startmigration01.png "Start New Migration dialog")

1. Expand **Configure storage (BYOS)**, and then read the choices **Microsoft-managed storage (default)** and **Use my own Azure Storage account**.

    ![Configure storage section with the Microsoft-managed and own storage options](../img/d365a-cfg-byos01.png "Configure storage (BYOS)")

1. Keep **Microsoft-managed storage** selected, and do not enter a Storage SAS URL.

| Option | Why it makes sense |
|--------|--------------------|
| Microsoft-managed | You do not provision Azure Storage or manage SAS access, so you can concentrate on discovery, mapping, and migration. |
| Bring your own storage | You control the staging account, access, and lifecycle policies, but you must own the configuration, permissions, and operations. |

**Checkpoint:** Your new project is selected, **Microsoft-managed** storage is selected, and no storage credentials are saved.

===

## Task 4: Connect Salesforce and run discovery

Discovery reads the metadata of your Salesforce org, so you connect it first.

1. In the **Start New Migration** dialog, expand **Connect to Salesforce**.

    ![Connect to Salesforce section with the login URL, consumer key, and consumer secret fields](../img/d365a-cfg-sfconnect01.png "Connect to Salesforce")

1. Enter the **Login URL**, **Consumer Key / Client ID**, and **Consumer Secret / Client Secret** that your facilitator provided.

    > **Note:** Use `https://test.salesforce.com` or your sandbox **My Domain** URL for a sandbox org.

1. Select **Try Connection**, and then wait until **Connect to Salesforce** shows **Connected**.

1. After the Dynamics 365 connection is set up in the next task, select **SF Discovery** in the left navigation, and then select **Start Discovery** to begin reading your Salesforce metadata.

    ![SF Discovery page with the No Active Discovery message and the Start Discovery button](../img/d365a-sfdisco-start01.png "SF Discovery - Start Discovery")

1. Wait while the **Fetching Discovery Data** panel completes each category, such as **Objects**, **Flows**, and **Apex**.

    ![Discovery progress panel listing the categories that are being fetched](../img/d365a-sfdisco-progress01.png "SF Discovery - In progress")

    > **Why this matters:** You can open other pages while discovery runs, and the counts in the left navigation fill in as each category finishes.

1. When discovery finishes, confirm that the **SF Discovery** badge in the left navigation shows a total count and that every category card shows **View** instead of **Discover**.

    ![Discovery overview after discovery completes, with the AI-Enhanced Analysis banner](../img/d365a-sfdisco-ovw01.png "SF Discovery - Completed")

1. In the **AI-Enhanced Analysis** banner, read the message, and then select **Enable AI Analysis** to get AI recommendations for Flows, Apex, and Lightning components.

    > **Important:** AI analysis shares discovery metadata, such as object, flow, and class names and code, with Azure OpenAI. Treat that metadata as potentially sensitive, and use only the approved lab org.

1. Wait until the banner reports that AI analysis is complete.

    ![AI analysis in progress message](../img/d365a-sfdisco-aiprogress01.png "AI analysis in progress")

===

## Task 5: Connect Dynamics 365 and run discovery

Dynamics 365 is the migration target, so Activate also needs to read its tables and columns.

1. In the left navigation, select **Configuration**, and then select **Edit Connection**.

1. In the dialog, expand **Connect to Dynamics**, and then review the **Environment URL**, **Tenant ID**, **Client ID (App Registration)**, and **Client Secret Value** fields.

    ![Connect to Dynamics section with empty environment URL and application credential fields](../img/d365a-cfg-dynconnect01.png "Connect to Dynamics")

1. Enter the **Environment URL**, **Tenant ID**, **Client ID**, and **Client Secret Value** that your facilitator provided, and then select **Connect to Dynamics**.

    > **Important:** Confirm that the environment is your assigned non-production target before you continue.

1. When the message **Successfully connected to Dynamics** appears, select **Go to Dynamics Discovery** to start discovery of the Dynamics 365 environment.

    ![Successful Dynamics connection message with the Go to Dynamics Discovery button](../img/d365a-cfg-dynconnect02.png "Dynamics connected")

1. In the left navigation, select **Configuration**, and then confirm that the **Project Configured** card shows both the Salesforce and Dynamics environments.

    ![Configuration page showing the project configured with both connections](../img/d365a-cfg-overview01.png "Project Configured")

1. In the **Migration Workflow** panel, read the four stages: **Connect**, **Discover**, **Map**, and **Migrate**.

    > **Why this matters:** The left navigation follows these four stages from top to bottom, so you can work through the tool in order.

**Checkpoint:** Both connections show as connected, Salesforce discovery and AI analysis are complete, and Dynamics discovery is running or complete.
