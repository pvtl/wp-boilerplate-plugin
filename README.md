# Plugin Placeholder Wordpress Plugin by Pivotal

- A `plugin-placeholder` custom post type
- A `plugin-placeholder-category` taxonomy
- Plugin Placeholder fields added to the post type
- Front-end templates (listing and single) to output the fields

## Prerequisites

- Wordpress
- Advanced Custom Fields Pro installed and activated

The default front-end templates make use of [Foundation](https://foundation.zurb.com/) - however you can override these in your theme if you need something different.

## Installation

__If you're using [Bedrock](https://github.com/roots/bedrock):__

```bash
git clone https://github.com/pvtl/wp-plugin-placeholders.git web/app/plugins/pvtl-plugin-placeholders
rm -rf web/app/plugins/pvtl-plugin-placeholders/.git
```

- Activate the plugin
- Update the project's `.gitignore` so that the plugin is included in the repo

__Alternatively:__

- Download this repo as a zip
- Upload the archive to your Wordpress plugin directory and activate the plugin

## How do I...?

### Modify the front-end layout?

By default, the plugin will use the templates found in `<plugin_dir>/resouces/views/*.php`.

You can easily override these templates, by creating the respective templates in your theme, naming them:

| File Name | Desc. |
| --- | --- |
| `single-plugin-placeholder.php` | The single post template (overrides single.php) |
| `archive-plugin-placeholder.php` | The listing template (overrides archive.php) |

### Add extra fields?

__Are the extra field/s specific for this project?__

- Simply create a new ACF group and add the fields, targeted to this post type
- You'll then need to override the front-end template/s to output the additional fields

__Should these new field/s be default for all projects?__

- Import the `/custom-fields/acf-export.json` into ACF > Tools
- Modify the fields
- __Export the JSON__ file + __Generate the PHP__ (replacing the existing files)
- Update the front-end templates to include the fields
- Commit the changes back to the GIT repo
