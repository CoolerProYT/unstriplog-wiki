<script setup>
import CraftingGui from './components/CraftingGui.vue'
</script>

# Bark Item

Bark is the default item that drops when stripping a log/wood. A bark item can have many variants depending on [Bark Type Config](/bark-type-config). All vanilla log/wood have their own bark type by default, and modded log/wood share the default bark that has no type unless defined in configs.

## Obtaining
It can be obtained by stripping wood/log, but depending on [Common Config](/common-config) and [Unstrip Detailed Config](/unstrip-detailed-config), it might not drop anything or may drop another item instead of bark.

## Usage
With the default config, bark can be used to unstrip all modded log. For vanilla log/wood, there is typed bark for each type of wood/log.

It can be used as furnace fuel and has a burn time of 150.

Bark can also be used to craft paper:

<CraftingGui
slot_1="mod:bark"
slot_2="mod:bark"
slot_3=""
slot_4=""
slot_5=""
slot_6=""
slot_7=""
slot_8=""
slot_9=""
output="minecraft:paper"
output_count="1"
/>