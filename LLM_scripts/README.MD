## Required Helper & Automation (Important)

LLM integrations in Home Assistant **do not pass `device_id` values to scripts**.  
Because of this limitation, an LLM-triggered script cannot know **which View Assist satellite** was used to issue the voice command.

To solve this (in ~99% of real-world cases), this repository uses a simple and reliable workaround:

### How it works

1. A **Text Helper (`input_text`)** is used to store the `device_id` of the **last active View Assist satellite**.
2. An **automation** updates this helper whenever any selected assist satellite enters the `listening` state.
3. All LLM scripts then read this helper to know **which satellite to control or navigate**.

This approach avoids:
- Tight coupling to any specific LLM integration  
- Token-heavy function schemas (as seen in some LLM integrations)
- Compatibility issues across different AI providers

---

### Step 1: Create the Text Helper

Create a Text Helper in Home Assistant:

**Settings → Devices & Services → Helpers → Create Helper → Text**

Example:
- **Name:** Last Used Satellite Device ID  
- **Entity ID:** `input_text.last_used_satellite_device_id`

---

### Step 2: Import the Automation Blueprint

Use the button below to import the automation that keeps this helper updated:

[![Open your Home Assistant instance and show the blueprint import dialog with a specific blueprint pre-filled.](https://my.home-assistant.io/badges/blueprint_import.svg)](https://my.home-assistant.io/redirect/blueprint_import/?blueprint_url=https://github.com/relust/View-Assist-ro-support/blob/main/LLM_scripts/blueprint-set_last_active_satellite.yaml)

After importing:
- Select **one or more `assist_satellite` entities**
- Select the **Text Helper** created above

---

### Result

With this helper + automation in place:
- LLM scripts can reliably target the **last active View Assist satellite**
- Navigation scripts (weather, dashboards, views, etc.) behave consistently
- The solution remains **LLM-agnostic and future-proof**

This automation is a **required dependency** for all LLM script blueprints in this repository.
