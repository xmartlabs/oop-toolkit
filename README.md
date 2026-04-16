# Xmartlabs Toolkit | Out-of-Pocket: Hardware Edition

Welcome to the [Out-of-Pocket: Hardware Edition](https://www.outofpocket.health/hackathon-hardware-edition) Hackathon!

[Xmartlabs](https://xmartlabs.com/) is sponsoring this event. Hackathons move fast, so we built these tools to cut setup time for teams working with health hardware and software.

This repository has tools and building blocks you can combine based on your use case. They handle device connectivity and data integration, so you spend less time on plumbing and more time on your product.

## Our Toolkit

| Tool | What it is | Best For... | Quick Start |
| :--- | :--- | :--- | :--- |
| **VytalLink** | Mobile app + MCP interface that connects wearable health data to AI agents. Reads from Apple Health and Health Connect; exposes it via MCP. | Teams that need health data in their AI agent without building device integrations from scratch. | [Deep Dive](tools/vytallink/README.md) |
| **Python Toolkit** | Python toolkit that can be used as a library to integrate these capabilities into your own applications. | Teams building custom backends, automations, or prototypes on top of VytalLink capabilities. | [GitHub Repo](https://github.com/xmartlabs/vytallink-health-kit) |
| **Reusable Agent Skills** | Reusable agent skills designed following best practices in UX, accessibility, and interaction design. | Teams that want stronger product decisions, better prompts, and more usable healthcare experiences. | [Deep Dive](skills/) |

## Tooling Deep Dive

### Vytallink
Vytallink simplifies the chaos of the wearable ecosystem. Instead of building separate integrations for Apple Health, Garmin Connect, Oura, and others, you integrate with Vytallink once and receive standardized data via API or webhooks.

* **Website:** [vytallink.xmartlabs.com](https://vytallink.xmartlabs.com/)
* **Implementation Guide:** See [`tools/vytallink`](tools/vytallink)

#### Ideas to get you started:

1.  **Personal Health Insights:**
    Connect wearable data (sleep, heart rate, activity) to an LLM to ask natural language questions like "Why was my sleep worse this week?" or "How does my activity affect my resting heart rate?"
2.  **Personalized Fitness Coaching:**
    Use natural language to get AI-driven recommendations based on wearable data, such as "What workout should I do today based on my recovery and sleep?" or "Am I improving my cardiovascular fitness?".

### UX & Accessibility Skills

These are reusable AI coding skills for Claude Code, Cursor, Windsurf, or any AI-powered coding tool. Install any skill with a single command:

```bash
npx skills add https://github.com/xmartlabs/oop-toolkit/tree/main/skills/<skill-name>
```

Each skill gives Claude the context and procedures to help with a specific UX, accessibility, or healthcare design task.

| Skill | What it is | When to use it |
| :--- | :--- | :--- |
| **[accessibility-xl](skills/accessibility-xl/SKILL.md)** | Xmartlabs accessibility audit procedure based on WCAG 2.2 Level AA, Core Web Vitals, and UX/UI best practices. | Whenever you need to check contrast ratios, alt text, keyboard navigation, screen reader support, or audit any design for accessibility compliance before handoff. |
| **[ux-healthcare](skills/ux-healthcare/SKILL.md)** | Expert UX design guide for healthcare digital products, covering compliance (HIPAA, WCAG, ADA), user types, and 10 healthcare-specific design principles. | Anytime you're designing or reviewing a patient portal, clinical tool, health app, telemedicine platform, or any product used by patients, caregivers, or clinicians. |
| **[ux-prompt-library](skills/ux-prompt-library/SKILL.md)** | UX/UI prompt assistant using the RACE framework for microcopy, wireframe layout, user flows, and UX research — plus a full Figma Make prompting guide. | When you want better outputs from AI tools: writing microcopy, planning wireframes, mapping user flows, writing usability test scripts, or prototyping in Figma Make. |

To install all skills at once:

```bash
npx skills add https://github.com/xmartlabs/oop-toolkit/tree/main/skills
```

## Support & Resources
* **Slack:** Join the `#support-xmartlabs` channel for direct technical support from our engineers.
* **On-Site Mentors:** Look for the **Xmartlabs** t-shirts on the event floor! We are here to help you debug and architect your solutions.
* **Xmartlabs Website:** [xmartlabs.com](https://xmartlabs.com/)

---
*Good luck, and let's build something that actually fixes healthcare!*
