# Accordion

Collapse and expand sections of content. Perfect for FAQs and content-heavy areas.

```blade
<flux:accordion>
    <flux:accordion.item>
        <flux:accordion.heading>What's your refund policy?</flux:accordion.heading>

        <flux:accordion.content>
            If you are not satisfied with your purchase, we offer a 30-day money-back guarantee. Please contact our support team for assistance.
        </flux:accordion.content>
    </flux:accordion.item>

    <flux:accordion.item>
        <flux:accordion.heading>Do you offer any discounts for bulk purchases?</flux:accordion.heading>

        <flux:accordion.content>
            Yes, we offer special discounts for bulk orders. Please reach out to our sales team with your requirements.
        </flux:accordion.content>
    </flux:accordion.item>

    <flux:accordion.item>
        <flux:accordion.heading>How do I track my order?</flux:accordion.heading>

        <flux:accordion.content>
            Once your order is shipped, you will receive an email with a tracking number. Use this number to track your order on our website.
        </flux:accordion.content>
    </flux:accordion.item>
</flux:accordion>
```

## Shorthand
You can save on markup by passing the heading text as a prop directly.

```blade
<flux:accordion.item heading="What's your refund policy?">
    If you are not satisfied with your purchase, we offer a 30-day money-back guarantee. Please contact our support team for assistance.
</flux:accordion.item>
```

## With transition
Enable expanding transitions for smoother interactions.

```blade
<flux:accordion transition>
    <!-- ... -->
</flux:accordion>
```

## Findable content
Content inside collapsed accordion items remains discoverable by the browser's find-in-page feature. When a match is found, Flux automatically expands the associated item. This works automatically—no additional prop is required.

Try it: press <kbd class="font-medium text-zinc-700 dark:text-zinc-200">⌘F</kbd> (<kbd class="font-medium text-zinc-700 dark:text-zinc-200">Ctrl+F</kbd> on Windows) and search for

```blade
<flux:accordion>
    <flux:accordion.item heading="Where do you ship?">
        We ship throughout the United States and Canada.
    </flux:accordion.item>

    <flux:accordion.item heading="Do I need to be home for delivery?">
        Orders over $500 must be signed for.
    </flux:accordion.item>

    <flux:accordion.item heading="Can I change my order?">
        Contact our support team before your order has shipped.
    </flux:accordion.item>
</flux:accordion>
```

## Disabled
Restrict an accordion item from being expanded.

```blade
<flux:accordion.item disabled>
    <!-- ... -->
</flux:accordion.item>
```

## Exclusive
Enforce that only a single accordion item is expanded at a time.

```blade
<flux:accordion exclusive>
    <!-- ... -->
</flux:accordion>
```

## Expanded
Expand a specific accordion by default.

```blade
<flux:accordion.item expanded>
    <!-- ... -->
</flux:accordion.item>
```

## Leading icon
Display the icon before the heading instead of after it.

```blade
<flux:accordion variant="reverse">
    <!-- ... -->
</flux:accordion>
```

## Reference

### flux:accordion
| Prop | Description |
| --- | --- |
| variant | When set to reverse, displays the icon before the heading instead of after it. |
| transition | If true, enables expanding transitions for smoother interactions. Default: false. |
| exclusive | If true, only one accordion item can be expanded at a time. Default: false. |

### flux:accordion.item
| Prop | Description |
| --- | --- |
| heading | Shorthand for flux:accordion.heading content. |
| expanded | If true, the accordion item is expanded by default. Default: false. |
| disabled | If true, the accordion item cannot be expanded or collapsed. Default: false. |

### flux:accordion.heading
| Slot | Description |
| --- | --- |
| default | The heading text. |

### flux:accordion.content
| Slot | Description |
| --- | --- |
| default | The content to display when the accordion item is expanded. |