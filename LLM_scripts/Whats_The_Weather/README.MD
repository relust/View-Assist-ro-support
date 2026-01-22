This blueprint creates a **Home Assistant script** for LLMs to navigate the last active View Assist satellite to the weather dashboard view.

## Key Points

- **LLM must verbally provide weather info** (temperature, wind, humidity, etc.) in **TTS-friendly format** (e.g., "-5.5 °C" → "minus five point five degrees").
- The script **only updates the visual interface** via `view_assist.navigate` and does not generate speech.
- Navigation targets the **last active satellite** stored in a helper `input_text` entity.

## Setup

1. **Create a helper** `input_text.last_used_satellite_device_id` to store the last active View Assist satellite.
2. Import the script blueprint:

[![Open your Home Assistant instance and show the blueprint import dialog with a specific blueprint pre-filled.](https://my.home-assistant.io/badges/blueprint_import.svg)](https://my.home-assistant.io/redirect/blueprint_import/?blueprint_url=https://github.com/relust/View-Assist-ro-support/blob/main/LLM_scripts/Whats_The_Weather/blueprint-whats_the_weather_llm_script.yaml)
# View Assist - What's the Weather - LLM Script

3. Configure the inputs:
   - `Weather view path` → default: `/view-assist/weather`
   - `Last active satellite input_text` → your `input_text` helper
   - `LLM Description` → used by the LLM to understand the script's purpose

4. **Create an automation** to update the helper with the last active satellite whenever needed


[![Open your Home Assistant instance and show the blueprint import dialog with a specific blueprint pre-filled.](https://my.home-assistant.io/badges/blueprint_import.svg)](https://my.home-assistant.io/redirect/blueprint_import/?blueprint_url=https://github.com/relust/View-Assist-ro-support/blob/main/LLM_scripts/blueprint-set_last_active_satellite.yaml)


5. Then instruct the LLM to execute the script it if weather info is requested.
