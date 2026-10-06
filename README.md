## Before you're done

This repo has been created for your Microsoft Ignite 2026 session. Here's how to get it ready.

**Easiest path — use the agent (recommended):**

- Open GitHub Copilot Chat and say `help me initialize repo`. The agent will walk you through getting the README populated.
- When you're ready to publish, say `help me finalize repo`. The agent will clean up unused folders, validate everything, and remove this "Before you're done" section and other extra stuff that attendees don't need to see.
- Curious how it works? Read the [agent workflow](.github/AGENT-WORKFLOW.md).

**Doing it manually?**

Fill in the sections below yourself, then:

- Delete any placeholder folders you don't need (`data/`, `infra/`, etc.)
- Delete this "Before you're done" section
- Delete `.github/agents/`, `.github/tests/`, `.github/copilot-instructions.md`, and `.github/AGENT-WORKFLOW.md` — these are template tooling, not part of your published repo

**Folder conventions:**

- Attendee step-by-step guidance goes in `instructions/`. If you use MkDocs or a docs site instead, put it in `docs/` and link to it from this README.
- Reference material and background reading go in `docs/`.
- You can add a `.devcontainer/` folder if needed.

---

<a name="start-building"></a>

<p align="center">
<img src="img/banner-ignite-26.png" alt="Microsoft Ignite 2026" width="100%"/>
</p>

# [Microsoft Ignite 2026](https://ignite.microsoft.com)

## 🔥 LAB700: Accelerate Salesforce Migration with Dynamics 365 Activate
### Session description

In this hands-on lab, you use Dynamics 365 Activate (preview) to plan and run a Salesforce-to-Dynamics 365 Sales migration. You review what the tool discovers in a connected Salesforce org, including objects, Apex, Lightning UI, usage, licenses, and the security model, and you see how it assesses each object by business priority, complexity, and recommended migration wave. You then follow the AI-guided workflow for the Account object: map it to the existing Dynamics 365 table, generate the migration contract, run the migration, and validate the results on the dashboard. By following the step-by-step instructions, you learn how Activate speeds up migration while keeping the process transparent, flexible, and easy to repeat.



### 🚀 Getting started

#### In a guided session

If you're following along during a live session:

1. Open the attendee guidance in [`instructions/`](instructions/README.md).
2. Follow the step-by-step instructions with your session facilitator.

#### On your own

If you're learning at your own pace:

1. Clone this repository
2. Open the attendee guidance in [`instructions/`](instructions/README.md).
3. Follow the step-by-step instructions at your own pace.

### 🎯 Learning outcomes

By the end of this session, you will be able to:

- Explain how Dynamics 365 Activate discovers and assesses a Salesforce org, and how its connect, discover, map, and migrate workflow guides a migration to Dynamics 365.
- Migrate Salesforce Account records to Dynamics 365 by mapping the object, generating the migration contract, running the migration, and validating the results.
- Apply the benefits of AI-guided migration, such as wave recommendations, complexity scoring, and replacement suggestions, when you plan customer engagements.

### 💻 Technologies used

- Dynamics 365 Activate (preview)
- Salesforce Sales Cloud
- Dynamics 365 Sales
- Microsoft Dataverse
- Salesforce to Dynamics 365 migration

### 📦 Session resources

- [Delivery deck](https://github.com/microsoft/ignite26-LAB700/tree/main/docs/LAB-700.pptx)
- Session recording: Not available

### 📚 Continue your learning

Pick your next step based on your learning style:

| Resource | What you'll get |
|----------|-----------------|
| **[Ignite 2026 Next Steps](https://aka.ms/ignite26-next-steps)** | Additional session repos and materials from Microsoft Ignite 2026 |
| **[Microsoft AI Skills Navigator](https://aka.ms/ignite26-asn)** | Discover AI skills, learning paths, and resources for your next step |
| **[Microsoft Learn](https://aka.ms/ignite26-learn)** | Official documentation and guided learning paths on these topics |
| **[Microsoft Foundry Community](https://aka.ms/MicrosoftFoundryDiscord-Ignite26)** | Connect with other learners and experts in our Discord community |

### 🌟 Microsoft Learn MCP Server

<!-- Remove this section if the Microsoft Learn MCP Server is not relevant to the session. -->

The Microsoft Learn MCP Server gives your AI agent direct access to Microsoft's official documentation — grounded, up-to-date answers about the topics in this session.

**GitHub Copilot CLI** — Install with:

```shell
copilot plugin install microsoftdocs/mcp
```

**VS Code** — One-click install:  
[![Install in VS Code](https://img.shields.io/badge/VS_Code-Install_Microsoft_Learn_MCP-0098FF?style=flat-square&logo=visualstudiocode&logoColor=white)](https://vscode.dev/redirect/mcp/install?name=microsoft-learn&config=%7B%22type%22%3A%22http%22%2C%22url%22%3A%22https%3A%2F%2Flearn.microsoft.com%2Fapi%2Fmcp%22%7D)

For more information, visit the [Learn MCP Server repo](https://aka.ms/learnmcp).

### 👥 Content owners

<table>
<tr>
    <td align="center"><a href="https://github.com/bambooo-310">
        <img src="https://github.com/bambooo-310.png" width="100px;" alt="Bharat Bambhaniya"/><br />
        <sub><b>Bharat Bambhaniya</b></sub></a><br />
            <a href="https://github.com/bambooo-310" title="talk">📢</a>
    </td>
    <td align="center"><a href="https://github.com/prateekmicrosoft">
        <img src="https://github.com/prateekmicrosoft.png" width="100px;" alt="Prateek Srivastava"/><br />
        <sub><b>Prateek Srivastava</b></sub></a><br />
            <a href="https://github.com/prateekmicrosoft" title="talk">📢</a>
    </td>
</tr></table>

### ⚖️ Trademarks

This project may contain trademarks or logos for projects, products, or services. Authorized use of Microsoft trademarks or logos is subject to and must follow [Microsoft's Trademark & Brand Guidelines](https://www.microsoft.com/legal/intellectualproperty/trademarks/usage/general). Use of Microsoft trademarks or logos in modified versions of this project must not cause confusion or imply Microsoft sponsorship.

Any use of third-party trademarks or logos are subject to those third-party's policies.
