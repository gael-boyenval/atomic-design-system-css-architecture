# File structure

## Here a schema of the SCSS files structure and their naming scheme

```text
styles/
├── settings-tools/
│   ├── _s.tokens.scss (generated)
│   ├── _s.colors.scss
│   ├── _s.magic-unit.scss
│   ├── _t.media-querie.scss
│   ├── ...
│   └── _allsettings.scss (this is a sub bundle containing all variables, mixins, and functions))
├── generics/
│   └── _g.reset.scss
├── elements/
│   ├── _e.lists.scss
│   ├── _e.input-fields.scss
│   ├── _e.headings.scss
│   ├── ...
│   └── _all-elements.scss (this is a sub bundle containing generic elements))
├── layouts/
│   ├── _l.grid.scss
│   ├── _l.drop-around.scss
│   ├── _l.drawer.scss
│   ├── _l.modal.scss
│   └── ...
├── atoms/
│   ├── _a.button.scss
│   ├── _a.headings.scss
│   ├── _a.input-field.scss
│   ├── _a.input-switch.scss
│   ├── _a.input-checkbox.scss
│   ├── _a.input-radio.scss
│   └── ...
├── molecules/
│   ├── _m.option-menu.scss
│   ├── _m.headings.scss
│   ├── _m.input-field.scss
│   ├── _m.input-switch.scss
│   ├── _m.input-checkbox.scss
│   ├── _m.input-radio.scss
│   ├── _m.modale-box.scss
│   └── ...
├── organisms/
│   ├── _o.navigation.scss
│   ├── _o.footer.scss
│   ├── _o.product-list.scss
│   ├── _o.search.scss
│   ├── _o.login.scss
│   └── ...
├── utilities/
│   ├── _u.spaces.scss
│   ├── _u.colors.scss
│   ├── _u.background.scss
│   ├── _u.text.scss
│   └── ...
```



### Notes :

Some editors truncate the files names in the opened tabs, it's why we use a prefix before the file name : To make developper experience easier when working with a lot of opened files.

You can also see that there is a bundle that contain settings and tools. It is easier to import all tools and variables at once, and has no impact on the compiled css file size.

