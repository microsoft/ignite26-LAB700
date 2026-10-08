# Attendee instructions

## Lab 700: Accelerate Salesforce migration with Dynamics 365 Activate

In this lab, you use Dynamics 365 Activate to explore a Salesforce org, review the target Dynamics 365 environment, and migrate the **Account** and **Contact** objects. Follow the exercises in order, and compare each step with your own screen.

### Before you begin

- Use the Dynamics 365 Activate URL and the credentials provided in your lab environment.
- Use the **D365 Activate Demo** project.
- Expect small differences in counts, because the numbers in the screenshots come from the demo project.

### Exercises

| # | Exercise | What you do |
|---|----------|-------------|
| 1 | [Review the project configuration](01-configuration.md) | Confirm the Salesforce and Dynamics connections and learn the migration workflow. |
| 2 | [Explore Salesforce discovery](02-salesforce-discovery.md) | Review objects, flows, Apex, Lightning UI, usage, packages, integrations, licenses, and security. |
| 3 | [Inspect the Account object](03-account-object-details.md) | Review the Account wave, complexity, record types, dependencies, and fields. |
| 4 | [Review Dynamics, process, and user mapping](04-dynamics-and-user-mapping.md) | Review the target environment, business processes, and user matching. |
| 5 | [Migrate the Account records](05-account-migration.md) | Map Account, generate the migration contract, run the migration, and validate the result. |
| 6 | [Migrate the Contact records](06-contact-migration.md) | Inspect Contact's volume, required fields, and parent lookups, confirm the target table, and migrate and validate the records. |

### Conventions

- **Bold** text is the name of an item on screen that you select or review.
- Notes explain why a step matters, and **Important** notes tell you what not to select.
- Screenshots are stored in [`img/`](../img) and follow the pattern `d365a-<area>-<page><number>.png`. Screenshots used only by the Contact exercise are in [`img/contact/`](../img/contact).
- A line with `===` marks a page break when the files are loaded into Skillable.
