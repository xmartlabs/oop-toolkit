# 🛠️ Xmartlabs Toolkit | Out-of-Pocket: Hardware Edition

Welcome to the [**Out-of-Pocket: Hardware Edition**](https://www.outofpocket.health/hackathon-hardware-edition) Hackathon!

As a proud sponsor, [**Xmartlabs**](https://xmartlabs.com/) is dedicated to helping teams bridge the gap between innovative health hardware and scalable, compliant software ecosystems. We know that in a hackathon, time is your most scarce resource.

This repository provides OOTB tools and SDKs designed by Xmartlabs to accelerate your development, handling the heavy lifting of device connectivity and data integration so you can focus on solving critical healthcare infrastructure problems.

---

## 🚀 Getting Started

To get the most out of these two sessions, we recommend:
1. **Forking this repo** to your team's organization.
2. **Reviewing the Tools below** to identify how they fit your project.
3. **Checking the `examples/` folder** for quick-start scripts and implementation guides.

---

## 🧰 Our Toolkit

| Tool | What it is | Best For... | Quick Start |
| :--- | :--- | :--- | :--- |
| **VytalLink** | Mobile app that connects your wearable devices and health apps (Apple Health, Google Fit) to AI assistants like ChatGPT and Claude. | Let AI assistants read your health info safely, privately, and only when you want them to. | [Deep Dive](tools/vytallink/README.md) |
| **RN SDK** |  |  | [Link](#react-native-sdk) |

---

## 🔍 Tooling Deep Dive

### ⌚ Vytallink
Vytallink simplifies the chaos of the wearable ecosystem. Instead of building separate integrations for Apple Health, Garmin Connect, Oura, and others, you integrate with Vytallink once and receive standardized data via API or webhooks.

* **Website:** [vytallink.xmartlabs.com](https://vytallink.xmartlabs.com/)
* **Implementation Guide:** See [`tools/vytallink`](tools/vytallink)

#### 💡 Ideas to get you started:

1.  **Personal Health Insights:**
    Connect wearable data (sleep, heart rate, activity) to an LLM to ask natural language questions like “Why was my sleep worse this week?” or “How does my activity affect my resting heart rate?”
2.  **Personalized Fitness Coaching:**
    Use natural language to get AI-driven recommendations based on wearable data, such as “What workout should I do today based on my recovery and sleep?” or “Am I improving my cardiovascular fitness?”.

---

### 📶 React Native SDK
[TBD]

* **Documentation:** See `/examples/rn-sdk/README.md`
* **Boilerplate App:** Check `/examples/rn-sdk/react-native-starter`

#### 💡 Ideas to get you started:

1.  **Custom Adherence Sensor Integration:**
    [TBD]
2.  **Diagnostic Device Data Transfer:**
    [TBD]

---

## 🆘 Support & Resources
* **Slack:** Join the `#support-xmartlabs` channel for direct technical support from our engineers.
* **On-Site Mentors:** Look for the **Xmartlabs** t-shirts on the event floor! We are here to help you debug and architect your solutions.
* **Xmartlabs Website:** [xmartlabs.com](https://xmartlabs.com/)

---
*Good luck, and let's build something that actually fixes healthcare!*
