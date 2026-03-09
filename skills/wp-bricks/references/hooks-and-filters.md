# Bricks Builder: Hooks and filters

Use Bricks filters and actions to customize behavior without modifying core files. For the canonical list, see [Bricks Academy: Filters](https://academy.bricksbuilder.io/topic/filters/).

## Builder interface

- **`bricks/builder/i18n`** – Customize builder UI strings.
- **`bricks/builder/save_messages`** – Customize save/error messages.
- **`bricks/builder/color_palette`** – Modify the color palette.
- **`bricks/builder/standard_fonts`** – Modify standard fonts.

## Elements

- **`bricks/builder/elements`** – Control which elements are available in the builder.
- **`bricks/elements/{element_name}/controls`** – Add or modify controls for a specific element (e.g. `bricks/elements/heading/controls`).

## Query and data

- **`bricks/posts/query_vars`** – Manipulate query loop variables before execution.
- **`bricks/dynamic_data/post_terms_separator`** – Change separator for post terms.
- **`bricks/dynamic_data/exclude_tags`** – Exclude dynamic data tags.
- **`bricks/dynamic_data/replace_nonexistent_tags`** – Handle non-existent tag replacement.

## Settings panels

- **`builder/settings/{type}/controls_data`** – Add controls to Page or Template Settings panels. `{type}` can be `page`, `template`, etc.

## Usage pattern

```php
add_filter( 'bricks/builder/elements', function( $elements ) {
    // Add, remove, or modify elements
    return $elements;
} );

add_filter( 'bricks/elements/heading/controls', function( $controls ) {
    // Add custom control to Heading element
    return $controls;
} );
```

## References

- [Bricks Academy: Filters](https://academy.bricksbuilder.io/topic/filters/)
- [Filter: builder/settings/{type}/controls_data](https://academy.bricksbuilder.io/article/filter-builder-settings-type-controls_data)
