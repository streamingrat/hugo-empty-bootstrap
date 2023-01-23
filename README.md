# hugo-empty-bootstrap

hugo-empty-bootstrap is a minimal blank template you can easily extend.  It was created to be a quick base framework that keeps up with
bootstrap versions.

> **Note**
>
> Have to use bootstrap-icons 1.9.0 until https://github.com/twbs/icons/pull/1566 is merged
>
> or use `"bootstrap-icons": "git+https://github.com/dherbst/icons#fix-dherbst-scss-1378"`

# Instructions for use:

1. In your themes directory run `git submodule add git@github.com:streamingrat/hugo-empty-bootstrap.git`
2. `cd themes/hugo-empty-bootstrap`
3. `npm install`
4. Optional if you want to customize bootstrap, copy `themes/hugo-empty-bootstrap/assets/scss/main.scss` to your project `assets/scss/project.scss` and add customizations in there.
5. Optional if you want to customize bootstrap, copy `themes/hugo-empty-bootstrap/layouts/partials/head.html` and modify the scss file to `project.scss` or whatever name you give it.


Add to the configuration for your site, `hugo.toml`:

```toml
theme = "hugo-empty-bootstrap"

# optional, but usually necessary
[markup.goldmark.renderer]
unsafe = true

[menu]
[[menu.main]]
  name = 'Menu 1'
  url = '/menu1/'
  weight = 10
[[menu.main]]
  name = 'Menu 2'
  url = '/menu2/'
  weight = 20

[Params]
  twitter = ""

#  module mounts needed for bootstrap theme to copy font files and bootstrap.bundle.min.js, which includes popper
[[module.mounts]]
source = "static"
target = "static"

[[module.mounts]]
source = "themes/hugo-empty-bootstrap/node_modules/bootstrap-icons/font/fonts"
target = "static/css/fonts"

[[module.mounts]]
source = "themes/hugo-empty-bootstrap/node_modules/bootstrap/dist/js/bootstrap.bundle.min.js"
target = "static/js/bootstrap.bundle.min.js"

```
