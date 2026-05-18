# BallisticNG Ship Stat Converter

<img width="1252" height="741" alt="bng_frontend_to_xml_converter_v1_6_1" src="https://github.com/user-attachments/assets/00714ff2-3854-465d-9ab6-71cf21f80a31" />

Frontend ship stat to BallisticNG XML converter for custom ship tuning and prefab stat generation.

## What it does

This tool converts simple frontend ship stats into BallisticNG backend XML stat values.

Frontend values:

- Acceleration
- Speed
- Handling
- Shield
- Firepower

The converter generates backend prefab stat values that can be copied into the BallisticNG Unity ingame ship stats workflow.

## Current version

v1.6.1

## How it works

The converter uses the official Base Ship Stats sheet as the source for its baseline logic.

Frontend stats are treated as player facing summary values. BallisticNG uses many backend XML fields to create actual ship behavior, so one frontend value can control multiple XML fields.

The converter uses this rule structure:

- Speed uses official lookup baselines
- Acceleration uses official lookup baselines
- Handling, Steer, and Grip use official lookup baselines
- Shield uses an exact official lookup table
- Firepower uses an exact official lookup table
- Rebound Feel and Track Alignment are manual feel presets
- Refinement Profile applies optional second pass tuning
- Template defaults are preserved for fields that are not frontend driven

If one frontend value has one clear backend value, the converter uses it directly.

If multiple official ships share the same frontend value but use different backend values, the converter uses an average as a balanced custom ship baseline.

If no official ship exists for a frontend value, the converter uses a controlled extrapolated value.

## Refinement profiles

Refinement Profile is an optional second pass tuning layer.

The baseline conversion is based on official stock ship data. Refinement profiles are custom tuning offsets, not official stock data.

Available profiles:

- Default baseline
- Agile lightweight
- Heavy utility
- High speed specialist
- Drift focused
- Stable beginner friendly
- Combat focused

Refinement profiles are useful when the baseline stat values are correct, but the ship needs a clearer behavior identity.

## Important note

This is a custom tuning tool. It is designed to create predictable custom ship stats, not to perfectly recreate every official stock ship.

Always test generated values in Unity and in game.

## Usage

Open `index.html` in a browser.

Enter frontend stat values.

Choose optional feel controls and a refinement profile.

Copy or download the generated XML snippet.

Import or paste the generated XML values into the BallisticNG Unity ingame ship stats workflow.

## Files

- `index.html`  
  Main converter tool.


Initial converter with frontend inputs, XML preview, copy, and download.
Open `index.html` in a browser, enter frontend stats, then copy or download the generated XML snippet.
