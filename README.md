# Cursor Enhancements

Cursor Enhancements is a mod for Factorio that adds new features to the cursor.

[Download on the Mod Portal.](https://mods.factorio.com/mod/CursorEnhancements)

## Features

Cursor Enhancements "enhances" the cursor with these new features:

### Related items scrolling

Using `shift + mousewheel`, you can quickly scroll between related items:

![](resources/cursor-scrolling.gif)

If you don't have an item when you scroll to it, the ghost cursor will be set instead. If you are in cheat mode or the map editor, instead of setting the ghost cursor, you will be given a new stack of that item for free.

The mod will auto-detect an entity's upgrades and downgrades and automatically set paths for those, but other mods can override these paths. For example, Cursor Enhancements itself adds various custom paths, including one for electric poles and one for inserters:

![](resources/cursor-scrolling-2.gif)

Other mods can tap Cursor Enhancements' remote interface to add their own overrides. See the [Remote Interface documentation](https://github.com/raiguard/Factorio-CursorEnhancements/wiki/Remote-Interface-Documentation) for instructions.

Additionally, each player can add their own overrides via the mod settings. See the FAQ for format instructions.

#### Belt transitions

Belts can be grouped in two ways:
	- By Tier (belt, fast belt, express belt)
	- By Category (belt, underground, splitter)

By default, scrolling with a belt-type item in your cursor will scroll between tiers only. You can change this behavior to scroll by categories instead, or by a combination of both tier and category. The setting supports the following values:

	- Tier (belt <-> fast belt <-> express belt)
	- Category (belt <-> underground <-> splitter)
	- Tier then Category (belt <-> fast belt <-> express belt <-> underground <-> fast underground ...)
	- Category then Tier (belt <-> underground <-> splitter <-> fast belt <-> fast underground ...)

### Automatic ghost transitions

If you run out of an item that places an entity, the item will be immediately swapped with the ghost cursor for that entity, and vice versa:

![](resources/ghost-transitions.gif)

If you are in cheat mode or the map editor, a new stack of items will be spawned into your cursor instead of setting the ghost cursor.

### Recall last item

Hit `Shift + Q` to recall the last item that was in your cursor. If you are out of that item, the ghost cursor will be set, or a new stack will be spawned if you're in cheat mode or the editor.

## FAQ

**Q: Why does the camera zoom when I'm scrolling between items?**

A: This is due to the default keybindings for zoom. Go into your controls settings and **unbind** zooming from `shift + mousewheel`. This will fix the problem.

![](./resources/controls.png)

**Q: How do I add my own cursor scrolling overrides?**

A: Go into the per-player mod settings and search for the `Personal registry overrides` option. This option is formatted as a JSON object, with the format `"item-name": "next-item-name"`. For example, to switch between iron plates and copper plates, you would add `"iron-plate": "copper-plate"` to the object. You can also negate an item's scroll by inputting `false` as the next item. For example, `"transport-belt": false` will disable scrolling between transport belts and fast transport belts.

![](./resources/personal-registry.png)
