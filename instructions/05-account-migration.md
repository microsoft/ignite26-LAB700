# Exercise 5: Migrate the Account records

In this exercise, you map the Salesforce **Account** object to the existing Dynamics 365 `account` table, deploy the schema changes, run the migration, and validate the result on the dashboard.

> **Note:** The mapping, solution, and migration screens in this exercise change data in your Dynamics 365 environment. Run them only against the non-production target provided for this lab.

## Task 1: Generate and review the Account mapping

The **Mapping Workbench** is where you generate and review the field mappings between Salesforce and Dynamics 365, so you share every mapping detail of Account before any data moves.

1. In the left navigation, select **Mapping** to open the **Mapping Workbench**.

1. Review the toolbar buttons in the **Generate & Review Mappings** card, such as **Auto-Generate Mappings**, **Load Mappings**, **Preflight Check**, **Templates**, **Reuse Hub**, **Annotations**, **Export**, **Import**, **History**, and **Global Picklists**.

    ![Mapping Workbench with the empty state and toolbar](../img/d365a-mapping-main01.png "Mapping Workbench - No mappings yet")

    > **Note:** The workbench shows **No Mappings Yet** until you generate mappings.

1. In the toolbar, select **Auto-Generate Mappings** to create field mappings for the objects that are in scope.

    ![Mapping Workbench while the mappings are being generated](../img/d365a-mapping-autogen01.png "Mapping Workbench - Generating mappings")

1. When generation finishes, review the **Readiness overview** and the **Table mappings** list, and then confirm that only **Account** and **Contact** are mapped to existing tables.

    > **Important:** All other tables must stay out of scope for this migration. If another table appears in the list, return to Exercise 2 and move it to out of scope.

1. In the **Account → account** row, select **Open details** to open the **Account mapping details**.

    ![Table mappings list with the Account row and the Open details button highlighted](../img/d365a-mapping-acctmap01.png "Table mappings - Account")

1. On the **Field mappings** tab, filter the field types by **Picklist**, and then review the two existing fields and the new picklist field.

    ![Account mapping details with the field mappings filtered by picklist](../img/d365a-mapping-acctfields01.png "Account mapping details - Picklist fields")

1. Open the new picklist field, and then notice that Activate automatically created values where it found no match.

    ![Choice configuration for the industry picklist field with automatically created values](../img/d365a-mapping-picklist01.png "Field mapping - Choice configuration")

1. Check every field that shows an alert, and then increase the **Max length** of the text fields so that the migration does not truncate data.

    ![Field mappings list with alerts on the billing address and description fields](../img/d365a-mapping-maxlen01.png "Field mappings - Fields with alerts")

    ![Field mapping dialog with the Max length field highlighted](../img/d365a-mapping-maxlen02.png "Field mapping - Max length")

1. Filter on **owner**, and then select the option to move the **Owner ID** field out of scope.

    ![Field mappings filtered on owner with the move out of scope action highlighted](../img/d365a-mapping-owner01.png "Field mappings - Owner field out of scope")

    > **Why this matters:** In this lab you do not map the users, so the owner lookup cannot be resolved during migration.

1. Explore the other tabs of the **Account mapping details**, starting with **Dataverse table design**.

    ![Account mapping details, Dataverse table design tab](../img/d365a-mapping-tabdesign01.png "Account mapping details - Dataverse table design")

1. Select the **Filter** tab to see the record filter, and then select the **Duplicates** tab and the **Dependencies** tab.

    ![Account mapping details, Filter tab with the record filter](../img/d365a-mapping-tabfilter01.png "Account mapping details - Filter")

    ![Account mapping details, Dependencies tab with the related tables](../img/d365a-mapping-tabdeps01.png "Account mapping details - Dependencies")

1. Close the details, and then select **Preflight Check** in the toolbar to confirm that no blocking issues remain before migration.

    ![Mapping Workbench after the preflight check with the readiness overview](../img/d365a-mapping-preflight01.png "Mapping Workbench - Preflight check")

===

## Task 2: Deploy the Account schema changes

Account already exists in Dynamics 365, but some fields are new or changed, so you select Account and deploy those changes before you migrate.

1. In the left navigation, select **Solution** to open the **Dynamics Solution Generator**.

1. At the top of the page, review the tiles for **Objects Selected**, **Total Fields**, **New Tables**, **Missing Columns**, and **Already in Dynamics**.

    ![Solution generator summary tiles and the Resync with Dynamics button](../img/d365a-solution-main01.png "Solution generator - Summary")

1. In the **Missing Columns** table, select the check box in the **Account** row.

    ![Missing Columns table with the Account row selected](../img/d365a-solution-acctselect01.png "Solution generator - Account selected")

    > **Note:** The **Missing Columns** table lists Dynamics tables that exist but lack some Salesforce columns. Selecting a table adds its missing columns so the rest can migrate too.

1. Scroll down to the **Generate & Deploy** section, and then review the solution settings.

    - **Solution Name:** `IgniteLab`
    - **Version:** keep the default value
    - **Publisher Prefix:** `lab`
    - **Solution Type:** `Unmanaged`

    ![Generate and Deploy section with the solution name, version, publisher prefix, and type](../img/d365a-solution-deploy01.png "Solution generator - Generate & Deploy")

1. Select **Import to Dynamics** to import the solution into your connected Dynamics 365 environment.

    ![Solution imported successfully message and the migration contract in Already in Dynamics](../img/d365a-solution-import01.png "Solution generator - Import completed")

1. Confirm that the message **Solution imported successfully** appears and that **Already in Dynamics** shows the Account contract status as **Verified**.

    > **Why this matters:** The **Migration** page stays blocked until the solution import is complete and the migration contract exists.

===

## Task 3: Run the Account migration

The **Migration** page runs the data transfer for all mapped objects, so you review the settings, validate the mapping, and then start the run.

1. In the left navigation, select **Migration** to open the **Data Migration** page.

1. In **Migration Settings**, select **Preserve Audit Fields** to keep the original Salesforce timestamps and user attribution.

    ![Migration settings with the Preserve Audit Fields options](../img/d365a-migrate-audit01.png "Migration Settings - Preserve Audit Fields")

1. Select **Created On**, **Created By (custom field)**, **Modified On**, and **Modified By (custom field)**, and leave the native **Created By** and **Modified By** options cleared.

    ![Preserve Audit Fields with the custom field options selected](../img/d365a-migrate-audit02.png "Migration Settings - Audit field options")

    > **Note:** To preserve the native **Created By** and **Modified By** values you must map the users first. In this lab you store them in custom fields and update **Created On**.

    > **Why this matters:** The native **Created By** and **Modified By** values use a slower one-by-one transfer, so select them only when you need that history.

1. Scroll down to the **Start Migration** section, and then confirm that **Account** is the only object selected in **Objects to Migrate**.

    ![Start Migration section with the Account object selected](../img/d365a-migrate-start01.png "Data Migration - Start Migration")

1. Select **Validate** to check the mapping before the run, and then confirm that the validation passes.

    ![Validation passed with the list of checks](../img/d365a-migrate-validate01.png "Data Migration - Validation passed")

1. Select **Start Migration (1 object)**, review the **Migration Preview**, and then select the consent check box and **Confirm & Start Migration**.

    ![Migration preview and data migration consent](../img/d365a-migrate-consent01.png "Data Migration - Migration preview and consent")

1. Monitor **Current migration** until the status shows as complete.

    ![Current migration running with the migration runs list](../img/d365a-migrate-run01.png "Data Migration - Migration in progress")

===

## Task 4: Validate the migrated Account records

The **Dashboard** compares record counts and samples field values, so you can confirm that the migration is complete and accurate.

1. In the left navigation, select **Dashboard** to open the **Dashboard** page.

1. In **Refresh Dashboard**, leave **Skip count reconciliation** and **Skip field sampling** cleared, and then select **Refresh** to reconcile counts and sample fields.

    ![Dashboard with the overall migration progress and Refresh Dashboard options](../img/d365a-dashboard-refresh01.png "Dashboard - Refresh")

1. In the **Summary** and **Count Reconciliation** sections, locate the **Account** row, and then confirm that **SF Count** and **Dynamics After** are the same and that the status is **Matched**.

    ![Dashboard summary and count reconciliation for Account](../img/d365a-dashboard-acctresult01.png "Dashboard - Account count reconciliation")

1. In Dynamics 365 Sales, open the **Accounts** list, and then spot-check a few migrated records against Salesforce.

    ![Dynamics 365 Sales Active Accounts list with the migrated accounts](../img/d365a-dashboard-acctverify01.png "Dynamics 365 Sales - Migrated accounts")

**Checkpoint:** The Account count in Dynamics 365 matches Salesforce, and the sampled fields match.
