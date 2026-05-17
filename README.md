# BallisticNG Ship Stat Converter

Frontend ship stat to BallisticNG XML converter for custom ship tuning and prefab stat generation.

## What it does

This tool converts simple frontend ship stats into BallisticNG XML stat values.

The frontend values are:

- Acceleration
- Speed
- Handling
- Shield
- Firepower

The converter outputs backend prefab stat XML values that can be copied into the BallisticNG Unity ingame ship stats workflow.

## Conversion logic

The converter uses lookup tables and formulas based on observed stock ship examples.

Current rule structure:

- Speed uses a lookup table
- Acceleration uses a lookup table
- Shield uses a lookup table
- Firepower uses a lookup table
- Grip uses a Handling based preset table
- Steer values use formulas
- Engine Power, Gravity, Camera, Character, and most 2280 values use default template values

## Notes

This is a house conversion system based on stock ship patterns. It is designed to create predictable custom ship stats, not to perfectly recreate every stock ship.

Always test generated values in Unity and in game.

## Usage

Open `index.html` in a browser, enter frontend stats, then copy or download the generated XML snippet.
