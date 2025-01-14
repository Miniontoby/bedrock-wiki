---
title: Block Tags
category: General
nav_order: 3
mentions:
    - SirLich
    - yanasakana
    - aexer0e
    - SmokeyStack
    - MedicalJewel105
    - Luthorius
    - Chikorita-Lover
    - victorsigma
    - TheItsNameless
    - QuazChick
---

Block tags can be used to ensure that a block meets certain conditions.

## Applying Tags

Block tags can be applied in the same way as items - in the block's `components` - as seen below:

<CodeHeader>BP/blocks/tree_stump.json</CodeHeader>

```json
{
  "format_version": "1.20.30",
  "minecraft:block": {
    "description": {
      "identifier": "wiki:tree_stump",
      "menu_category": {
        "category": "nature"
      }
    },
    "components": {
      "tag:wood": {},
      "tag:my_lovely_tag": {},
      "tag:wiki:very_useless": {}
    }
  }
}
```

## Testing for Tags

Tags can be queried with:

-   `q.all_tags`
-   `q.any_tag`

:::warning EXPERIMENTAL
The following query functions require experimental Molang features to be enabled.
:::

-   `q.block_has_all_tags`
-   `q.block_has_any_tag`
-   `q.block_neighbor_has_all_tags`
-   `q.block_neighbor_has_any_tag`
-   `q.relative_block_has_all_tags`
-   `q.relative_block_has_any_tag`

Example of an item querying a block's tags:

<CodeHeader>BP/items/custom_pickaxe.json</CodeHeader>

```json
{
  "format_version": "1.20.30",
  "minecraft:item": {
    "description": {
      "identifier": "wiki:custom_pickaxe",
      "menu_category": {
        "category": "equipment",
        "group": "itemGroup.name.pickaxe"
      }
    },
    "components": {
      "minecraft:digger": {
        "use_efficiency": true,
        "destroy_speeds": [
          {
            "speed": 5,
            "block": {
              "tags": "q.any_tag('custom_ore', 'stone', 'metal')"
            }
          }
        ]
      }
    }
  }
}
```

## Lists of Block Tags

### Vanilla Tags

Vanilla tags can be applied to custom blocks, and some vanilla blocks are tagged internally. This kind of tag doesn't give blocks vanilla features. The only usage of it is to tag blocks to make them have the same tags as the vanilla blocks for queries or tests.
| Tag | Vanilla Usage |
| ------------------------- | ---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| wood | Oak Trapdoor, Spruce Trapdoor, Birch Trapdoor, Jungle Trapdoor, Acacia Trapdoor, Dark Oak Trapdoor, Oak Door, Spruce Door, Birch Door, Jungle Door, Acacia Door, Dark Oak Door, Oak Fence, Spruce Fence, Birch Fence, Jungle Fence, Acacia Fence, Dark Oak Fence, Oak Fence Gate, Spruce Fence Gate, Birch Fence Gate, Jungle Fence Gate, Acacia Fence Gate, Dark Oak Fence Gate, Oak Log, Spruce Log, Birch Log, Jungle Log, Acacia Log, Dark Oak Log, Oak Planks, Spruce Planks, Birch Planks, Jungle Planks, Acacia Planks, Dark Oak Planks, Oak Slab, Spruce Slab, Birch Slab, Jungle Slab, Acacia Slab, Dark Oak Slab, Oak Stairs, Spruce Stairs, Birch Stairs, Jungle Stairs, Acacia Stairs, Dark Oak Stairs, Oak Sign, Spruce Sign, Birch Sign, Jungle Sign, Acacia Sign, Dark Oak Sign, Oak Pressure Plate, Spruce Pressure Plate, Birch Pressure Plate, Jungle Pressure Plate, Acacia Pressure Plate, Dark Oak Pressure Plate, Smithing Table, Fletching Table, Barrel, Beehive, Bee Nest, Ladder |
| pumpkin | Pumpkin, Carved Pumpkin, Jack o'Lantern |
| plant | Tall Grass, Large Fern, Sunflower, Lilac, Rose Bush, Peony, Oak Sapling, Oak Sapling, Spruce Sapling, Birch Sapling, Jungle Sapling, Acacia Sapling, Dark Oak Sapling |
| stone | Stone, Cobblestone, Mossy Cobblestone, Dripstone Block, Bricks, Cobblestone Stairs, Smooth Stone Slab, Sandstone Slab, Cobblestone Slab, Brick Slab, Stone Bricks Slab, Quartz Slab, Nether Brick Slab, Cobblestone Wall, Mossy Cobblestone Wall, Stone Brick Wall, Mossy Stone Brick Wall, Andesite Wall, Diorite Wall, Granite Wall, Sandstone Wall, Red Sandstone Wall, Brick Wall, Prismarine Wall, Nether Brick Wall, Red Nether Brick Wall, End Stone Brick Wall, Andesite, Granite, Polished Andesite, Polished Granite, Polished Diorite, Diorite |
| metal | Block of Gold, Block of Iron, Cauldron, Iron Bars |
| diamond_pick_diggable | Obsidian, Coal Ore, Deepslate Coal Ore, Deepslate Diamond Ore, Deepslate Emerald Ore, Deepslate Gold Ore, Deepslate Iron Ore, Deepslate Redstone Ore, Diamond Ore, Emerald Ore, Gold ore, Iron Ore, Lapis Lazuli Ore, Redstone Ore, Block of Raw Iron, Block of Raw Gold |
| gold_pick_diggable | |
| iron_pick_diggable | Coal Ore, Deepslate Coal Ore, Deepslate Diamond Ore, Deepslate Emerald Ore, Deepslate Gold Ore, Deepslate Iron Ore, Deepslate Redstone Ore, Diamond Ore, Emerald Ore, Gold ore, Iron Ore, Lapis Lazuli Ore, Redstone Ore, Block of Raw Iron, Block of Raw Gold |
| stone_pick_diggable | |
| wood_pick_diggable | |
| dirt | Farmland |
| sand | Red Sand, Sand |
| gravel | Gravel |
| grass | Grass Block, Dirt, Coarse Dirt, Dirt Path |
| snow | Snow |
| rail | Rail, Powered Rail, Detector Rail, Activator Rail |
| water | Water |
| mob_spawner | Spawner |
| lush_plants_replaceable | |
| azalea_log_replaceable | |
| not_feature_replaceable | chest, bedrock, end portal frame, mob spawner |
| text_sign | All kinds of signs |
| minecraft:crop | Beetroot, Carrot, Potato, Wheat |
| fertilize_area | All types of Flowers, except Tall Flowers & Wither Rose; Crimson Nylium, Warped Nylium, Grass, Moss |

### Vanilla Block Tags

Vanilla block tags are tags built specifically for blocks. They can give some vanilla features to the blocks which are tagged with them.

| Tag      | Vanilla Usage                                                        | Description  |
| -------- | -------------------------------------------------------------------- | ------------ |
| acacia   | Acacia Log                                                           |              |
| birch    | Birch Log                                                            |              |
| dark_oak | Dark Oak Log                                                         |              |
| jungle   | Jungle Log                                                           |              |
| log      | Oak Log, Spruce Log, Birch Log, Jungle Log, Acacia Log, Dark Oak Log | A log block. |
| oak      | Oak Log                                                              |              |
| spruce   | Spruce Log                                                           |              |
