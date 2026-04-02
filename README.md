# 🛠️ Xmartlabs Toolkit | Out-of-Pocket: Hardware Edition

Welcome to the [**Out-of-Pocket: Hardware Edition**](https://www.outofpocket.health/hackathon-hardware-edition) Hackathon!

As a proud sponsor, [**Xmartlabs**](https://xmartlabs.com/) is dedicated to helping teams bridge the gap between innovative health hardware and scalable, compliant software ecosystems. We know that in a hackathon, time is your most scarce resource.

This repository provides OOTB tools and SDKs designed by Xmartlabs to accelerate your development, handling the heavy lifting of device connectivity and data integration so you can focus on solving critical healthcare infrastructure problems.

## 🚀 Getting Started

To get the most out of these two sessions, we recommend:
1. **Forking this repo** to your team's organization.
2. **Reviewing the Tools below** to identify how they fit your project.
3. **Checking the `examples/` folder** for quick-start scripts and implementation guides.

## 🧰 Our Toolkit

| Tool | What it is | Best For... | Quick Start |
| :--- | :--- | :--- | :--- |
| **VytalLink** | Mobile app that connects your wearable devices and health apps (Apple Health, Google Fit) to AI assistants like ChatGPT and Claude. | Let AI assistants read your health info safely, privately, and only when you want them to. | [Deep Dive](tools/vytallink/README.md) |
| **UX & Accessibility Skills** | principles of user experience design combined with foundational accessibility guidelines (e.g., usability, clarity, WCAG basics). | Teams aiming to create equitable experiences for a broad audience. | [Deep Dive](skills/) |

## 🔍 Tooling Deep Dive

### ⌚ Vytallink
Vytallink simplifies the chaos of the wearable ecosystem. Instead of building separate integrations for Apple Health, Garmin Connect, Oura, and others, you integrate with Vytallink once and receive standardized data via API or webhooks.

* **Website:** [vytallink.xmartlabs.com](https://vytallink.xmartlabs.com/)
* **Implementation Guide:** See [`tools/vytallink`](tools/vytallink)

#### 💡 Ideas to get you started:

1.  **Personal Health Insights:**
    Connect wearable data (sleep, heart rate, activity) to an LLM to ask natural language questions like "Why was my sleep worse this week?" or "How does my activity affect my resting heart rate?"
2.  **Personalized Fitness Coaching:**
    Use natural language to get AI-driven recommendations based on wearable data, such as "What workout should I do today based on my recovery and sleep?" or "Am I improving my cardiovascular fitness?".

### 🤖 UX & Accessibility Skills

These are **Claude Code skills** — plug-and-play AI assistants you can drop into your project to get expert-level UX, accessibility, and healthcare design guidance without leaving your editor.

> **How to use them:** Copy the `SKILL.md` file from the skill folder into your project and load it into [Claude Code](https://claude.ai/code). The skill will give Claude the knowledge and procedures to assist you at that specific task.

| Skill | What it is | When to use it |
| :--- | :--- | :--- |
| **[accessibility-xl](skills/accessibility-xl/SKILL.md)** | Xmartlabs accessibility audit procedure based on WCAG 2.2 Level AA, Core Web Vitals, and UX/UI best practices. | Whenever you need to check contrast ratios, alt text, keyboard navigation, screen reader support, or audit any design for accessibility compliance before handoff. |
| **[ux-healthcare](skills/ux-healthcare/SKILL.md)** | Expert UX design guide for healthcare digital products, covering compliance (HIPAA, WCAG, ADA), user types, and 10 healthcare-specific design principles. | Anytime you're designing or reviewing a patient portal, clinical tool, health app, telemedicine platform, or any product used by patients, caregivers, or clinicians. |
| **[ux-prompt-library](skills/ux-prompt-library/SKILL.md)** | UX/UI prompt assistant using the RACE framework for microcopy, wireframe layout, user flows, and UX research — plus a full Figma Make prompting guide. | When you want better outputs from AI tools: writing microcopy, planning wireframes, mapping user flows, writing usability test scripts, or prototyping in Figma Make. |

## 🆘 Support & Resources
* **Slack:** Join the `#support-xmartlabs` channel for direct technical support from our engineers.
* **On-Site Mentors:** Look for the **Xmartlabs** t-shirts on the event floor! We are here to help you debug and architect your solutions.
* **Xmartlabs Website:** [xmartlabs.com](https://xmartlabs.com/)

---
*Good luck, and let's build something that actually fixes healthcare!*
