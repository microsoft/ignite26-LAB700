# Attendee instructions

## Lab 700: Accelerate Salesforce migration with Dynamics 365 Activate

In this lab, you use Dynamics 365 Activate to create a migration project, explore a Salesforce org, review the target Dynamics 365 environment, and migrate the **Account** and **Contact** objects. Follow the exercises in order, and compare each step with your own screen.

### Before you begin

- Open Dynamics 365 Activate at `https://migrate.dynamics.cloud.microsoft/signup`, and use the credentials provided in your lab environment.
- Create your own workspace and project in Exercise 1, and use the connection values that your facilitator provides for Salesforce and Dynamics 365.
- Expect small differences in counts, because the numbers in the screenshots come from the lab Salesforce org.

### Exercises

| # | Exercise | What you do |
|---|----------|-------------|
| 1 | [Create your workspace, project, and connections](01-configuration.md) | Create a project, choose storage, connect Salesforce and Dynamics 365, and run discovery. |
| 2 | [Explore Salesforce discovery](02-salesforce-discovery.md) | Review objects, flows, Apex, Lightning UI, usage, packages, integrations, licenses, and security, and limit the scope to Account and Contact. |
| 3 | [Inspect the Account and Contact objects](03-account-object-details.md) | Review the Account complexity, record types, dependencies, and fields, and compare it with Contact. |
| 4 | [Review Dynamics and user mapping](04-dynamics-and-user-mapping.md) | Review the target environment and the user matching. |
| 5 | [Migrate the Account records](05-account-migration.md) | Map Account, deploy the schema changes, run the migration, and validate the result. |
| 6 | [Migrate the Contact records](06-contact-migration.md) | Inspect Contact, confirm the target table, and migrate and validate the records. |

### Conventions

- **Bold** text is the name of an item on screen that you select or review.
- Notes explain why a step matters, and **Important** notes tell you what not to select.
- Screenshots are stored in [`img/`](../img) and follow the pattern `d365a-<area>-<page><number>.png`.
- A line with `===` marks a page break when the files are loaded into Skillable.
