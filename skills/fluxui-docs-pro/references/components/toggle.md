# Toggle

Turn a setting on or off using a compact, button-shaped control.

Use a toggle for icon-sized settings and modes. Use a [switch](/components/switch) when the setting needs a visible label.

```blade
<flux:toggle wire:model.live="fastMode" icon="bolt" tooltip="Fast mode" />
```

## Sizes
Use the size prop to fit toggles into different interface densities.

```blade
<flux:toggle icon="bolt" />

<flux:toggle icon="bolt" size="sm" />

<flux:toggle icon="bolt" size="xs" />
```

## Variants
Choose a treatment that matches the surrounding controls.

```blade
<flux:toggle icon="bolt" />

<flux:toggle icon="bolt" variant="filled" />

<flux:toggle icon="bolt" variant="ghost" />

<flux:toggle icon="bolt" variant="subtle" />
```

## Color
Use the color prop to customize the active state. The inactive state remains neutral.

```blade
<flux:toggle icon="bolt" color="blue" checked />

<flux:toggle icon="heart" color="red" checked />

<flux:toggle icon="bell" color="amber" checked />
```

## With label
Use the label prop to add short text when the setting benefits from a persistent visible label.

```blade
<flux:toggle icon="bolt" label="Fast mode" />
```

## Stateful icon
Use the on:icon and off:icon props to show a different icon for each state.

```blade
<flux:toggle on:icon="speaker-wave" off:icon="speaker-x-mark" tooltip="Toggle sound" />
```

## Stateful label
Use the on:label and off:label props to show different text for each state.

```blade
<flux:toggle on:label="Sound on" off:label="Sound off" />
```

## Reference

### flux:toggle
| Prop | Description |
| --- | --- |
| wire:model | Binds the toggle's checked state to a Livewire property. |
| icon | Icon name. The outline icon is shown when off and the solid icon when on. |
| on:icon | Icon shown when on. Overrides icon for this state. |
| off:icon | Icon shown when off. Use with on:icon or icon. |
| label | Label shown in both states. The default slot may be used instead and takes precedence. |
| on:label | Label shown when on. Overrides label for this state. |
| off:label | Label shown when off. Use with on:label, label, or the default slot. |
| size | Control size. Options: base (default), sm, or xs. |
| variant | Visual treatment. Options: outline (default), filled, ghost, or subtle. |
| color | Color of the active icon. The inactive state and control surface remain neutral. Defaults to the application's accent color. |
| tooltip | Tooltip text. Recommended for icon-only toggles because it also supplies the accessible name. |
| checked | Sets the initial checked state when not using wire:model. |
| disabled | Prevents user interaction with the toggle. |

| Attribute | Description |
| --- | --- |
| data-flux-toggle | Applied to the root element for styling and identification. |
| data-checked | Applied when the toggle is on. |