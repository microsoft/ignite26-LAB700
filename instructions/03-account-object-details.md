# Exercise 3: Inspect the Account and Contact objects

In this exercise, you open the Salesforce **Account** object in the discovery results and review its complexity, record types, dependencies, and fields. You then compare it with **Contact**, the other object you migrate. Both objects are migrated in the last two exercises, so you need to know what they contain first.

## Task 1: Open the Account details

The object details panel combines the scoring, volume, and field analysis for a single object, so you can judge how risky its migration is.

1. In the left navigation, select **SF Discovery**, and then select **Objects**.

1. In the list, locate the **Account** row, and then select the arrow at the left of the row to expand its details.

    > **Why this matters:** Expanding a row is a read-only action, and it does not change the scope of the migration.

1. In the row header, confirm the **Platform** business area and the **Critical Tier** tag, and then note the **priority** score, the complexity score, and the **Wave 1** tag.

1. Review **Volume & Freshness**, **Engagement**, and **Tier Reasoning** to see how much data Account holds and why Activate ranks it as critical.

    ![Account row expanded, showing volume and freshness, engagement, tier reasoning, and complexity reasoning](../img/d365a-sfdisco-acctdetail01.png "Account details - expanded row")

1. Review **Complexity Reasoning** and **Record Types** to see how fields, relationships, picklists, special fields, and record types add to the complexity.

    > **Note:** Review parent lookups and record types before you load Account, because Contact and other objects depend on it.

===

## Task 2: Review Account relationships and fields

The expanded Account row shows how many relationships Account has and which fields hold data, which drives your mapping decisions later.

1. In the expanded **Account** row, review **Complexity Reasoning** and **Record Types**. Note that Account has 6 relationships and 2 record types.

    > **Note:** Account's lookups, such as the parent account and the record type, drive the load order, so Account is migrated before the objects that depend on it, such as Contact.

1. Scroll down in the expanded row to **Compound Field Groups**, and then note that **BillingAddress** and **ShippingAddress** are not migrated directly; Activate maps their component columns instead.

1. Continue to the fields table, and then review the **Field Label**, **API Name**, **Type**, **Fill Rate**, and **Properties** columns. The **Properties** column flags fields such as **Lookup**, **Required**, and **Picklist**.

    ![Account fields table with fill rates and properties](../img/d365a-sfdisco-acctfields01.png "Account details - Fields table")

    > **Why this matters:** Fields that are rarely populated are candidates to skip, which reduces the work in the mapping stage.

1. Select the arrow at the left of the **Account** row to collapse it.

    > **Important:** Do not select **Ignore** on Account, because it would move Account out of the migration scope.

===

## Task 3: Compare with the Contact object

Contact looks up to Account, so the two objects have to be loaded in the right order.

1. In the **Objects** list, locate the **Contact** row, and then compare its **Business priority**, **Complexity**, and wave with the Account row.

1. Expand the **Contact** row, and then compare the number of relationships in its **Complexity Reasoning** with Account to see how the two objects connect.

    > **Note:** You review the Contact details in full in Exercise 6: [Migrate the Contact records](06-contact-migration.md).

**Checkpoint:** The Account row is collapsed, and you can describe the complexity, record types, and field population of Account.
