# Bricks Builder: Data structure and storage

## Where Bricks stores data

Bricks stores layout and element data in **WordPress post meta**. The primary content is stored as JSON.

### Post meta keys

- **`_bricks_page_content_2`** (or similar versioned key): JSON array of elements representing the page/template structure.
- Other meta keys may store template settings, conditions, and element-specific data.

### Element structure (JSON)

Each element in the content array has:

- **`id`**: Unique identifier (e.g. `abc123`).
- **`name`**: Element type (`section`, `container`, `heading`, `button`, `image`, etc.).
- **`parent`**: ID of parent element (`0` for root-level).
- **`settings`**: Object with element-specific config (text, links, CSS classes, styling, dynamic data tags).

Example:

```json
{
  "elements": [
    {
      "id": "abc123",
      "name": "section",
      "parent": 0,
      "settings": { "tag": "section" }
    },
    {
      "id": "def456",
      "name": "heading",
      "parent": "abc123",
      "settings": {
        "text": "Welcome",
        "_cssId": "hero-heading"
      }
    }
  ]
}
```

### File locations

- **Templates:** Stored as WordPress posts (post type `bricks_template` or similar) with meta holding the layout.
- **Theme-level:** Bricks may use theme files for defaults; customizations are typically in the database.
- **Per-post/page:** Each post/page can have its own Bricks layout stored in post meta.

### Editing programmatically

Directly modifying post meta is possible but fragile (JSON structure, versioning). Prefer:

- Bricks filters and actions to alter behavior.
- Custom elements or controls via `bricks/builder/elements` and related hooks.

## References

- [Bricks Academy](https://academy.bricksbuilder.io/)
- [Bricks dynamic data](https://bricksbuilder.io/dynamic-data)
