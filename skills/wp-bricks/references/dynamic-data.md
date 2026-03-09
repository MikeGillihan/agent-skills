# Bricks Builder: Dynamic data

Bricks uses dynamic data tags to pull content from the WordPress database and custom fields. Tags are wrapped in curly braces: `{tag_name}`.

## Standard WordPress data

- **Post:** `{post_title}`, `{post_content}`, `{post_excerpt}`, `{post_url}`, `{post_date}`, `{featured_image}`, etc.
- **Taxonomies:** `{post_terms}`, `{term_name}`, etc.
- **Author:** `{author_name}`, `{author_avatar}`, etc.
- **Site/archive:** `{site_title}`, `{site_tagline}`, archive-specific tags.

## Custom fields

Bricks integrates with:

- Advanced Custom Fields (ACF)
- Meta Box
- JetEngine (Crocoblock)
- Pods
- Toolset
- CMB2

Use the dynamic data picker (lightning bolt icon) in the builder to select fields. Field keys/names must match the custom field plugin configuration.

## Special tags

- **`{echo:functionName}`** – Output from a PHP function. The function must be defined and return a string.
- **`{do_action:hook_name}`** – Execute a WordPress action. Use for side effects (e.g. output from a hooked function).

## Dynamic data tag filters

Modify how tags render on the frontend:

- **`bricks/dynamic_data/post_terms_separator`** – Separator for post terms.
- **`bricks/dynamic_data/exclude_tags`** – Exclude specific tags.
- **`bricks/dynamic_data/replace_nonexistent_tags`** – Replace or hide output when a tag has no data.

## Conditions

Bricks supports dynamic conditions: show/hide elements based on dynamic data (e.g. "show if post has featured image," "show if custom field X equals Y"). Configure in the element’s Conditions panel.

## Query loops and repeaters

- Query custom repeater fields and flexible content from ACF, Meta Box, JetEngine, etc.
- Use meta queries in the Query Loop Builder to filter by custom field values (comparison operators: `=`, `!=`, `LIKE`, `IN`, etc.).

## References

- [Bricks Academy: Dynamic Data](https://academy.bricksbuilder.io/article/dynamic-data/)
- [Bricks: The most advanced dynamic data solution](https://bricksbuilder.io/dynamic-data)
- [Exploring Dynamic Data Tag Filters](https://bricksultra.com/exploring-dynamic-data-tag-filters-in-bricks-builder)
