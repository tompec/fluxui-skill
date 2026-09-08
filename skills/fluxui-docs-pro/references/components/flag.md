---
components_used: [card, heading, select, text]
---

# Flag

Display a flag using its two-letter Unicode region code.

```blade
<flux:flag country="US" />
```

## Sizes
Use the size prop to change the width of the flag. The default aspect ratio is 3:2.

```blade
<flux:flag country="US" size="xl" />
<flux:flag country="US" size="lg" />
<flux:flag country="US" size="md" />
<flux:flag country="US" />
<flux:flag country="US" size="xs" />
```

## Circle
Use the circle prop for a circular crop.

```blade
<flux:flag circle country="US" />
```

## Registry
The built-in registry follows Unicode's Recommended for General Interchange (RGI) two-letter flag sequences. Inclusion provides compatibility with that external standard and does not express a position on the status of any country, territory, government, or border.

Use the src prop for anything outside that registry. Flux does not add or remove built-in flags case by case.

## Examples

### Country select
Pair flags with localized country names in a searchable select.

```blade
<flux:select wire:model="country" variant="listbox" searchable>
    @foreach ($countries as $country)
        <flux:select.option :value="$country['code']" :label="$country['name']">
            <div class="flex items-center gap-2">
                <flux:flag :country="$country['code']" size="xs" />
                <span>{{ $country['name'] }}</span>
            </div>
        </flux:select.option>
    @endforeach
</flux:select>
```

### Currency select
Use a representative region flag as a visual cue while keeping the currency code as the value.

```blade
<flux:select wire:model="currency" variant="listbox">
    @foreach ($currencies as $currency)
        <flux:select.option :value="$currency['code']" :label="$currency['name']">
            <div class="flex items-center gap-2">
                <flux:flag :country="$currency['country']" size="xs" />
                <span class="font-medium">{{ $currency['code'] }}</span>
                <span class="text-zinc-500">{{ $currency['name'] }}</span>
            </div>
        </flux:select.option>
    @endforeach
</flux:select>
```

Flags and currencies are not one-to-one. For shared currencies such as the euro, choose a deliberate product convention instead of inferring a flag automatically.

### Analytics card
Use flags as compact visual anchors in country-based reports.

```blade
<flux:card variant="soft">
    <div class="flex items-baseline justify-between gap-4">
        <flux:heading>Countries</flux:heading>
        <flux:text class="font-medium">Visitors</flux:text>
    </div>

    <div class="mt-6 space-y-5">
        @foreach ($countries as $country)
            <div class="flex items-center gap-3">
                <flux:flag :country="$country['code']" size="md" class="w-7" />
                <flux:text class="min-w-0 flex-1 truncate">{{ $country['name'] }}</flux:text>
                <flux:text class="font-medium">{{ $country['visitors'] }}</flux:text>
            </div>
        @endforeach
    </div>
</flux:card>
```

## Custom flags
Use the src prop for a subdivision, organization, historical flag, or any other image outside the built-in registry.

```blade
<flux:flag src="/img/flags/california.svg" alt="California" size="xl" />
```

## Accessibility
Flags are decorative by default and render with an empty alt. Add alternative text only when the flag communicates information that is not already present nearby.

```blade
<!-- Decorative because the adjacent text already names the country... -->
<div class="flex items-center gap-2">
    <flux:flag country="CA" />
    <span>Canada</span>
</div>

<!-- Informative when no nearby text communicates the country... -->
<flux:flag country="CA" alt="Canada" />
```

## Reference

### flux:flag
| Prop | Description |
| --- | --- |
| country | Unicode RGI two-letter region code. Case-insensitive. |
| src | Custom image URL. When present, this takes precedence over country. |
| alt | Alternative text for the image. Default: an empty string. |
| size | Width of the flag. Options: xs (20px), sm (24px, default), md (32px), lg (40px), xl (48px). |
| circle | If present or true, crops the flag to a circle. |