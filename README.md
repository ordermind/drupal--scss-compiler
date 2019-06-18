## INTRODUCTION
Module automatically compiles scss files defined in libraries.yml into css.

## REQUIREMENTS
Module requires php compiler library [ScssPhp][1]

## INSTALLATION
### Manual installation
1. Download last release of [ScssPhp Compiler][2]
2. Rename it to `scssphp` and place into libraries directory
(DRUPAL_ROOT/libraries/)
3. Install module and all SCSS files defined in libraries.yml
will be compiled into css

### Composer installation
If you manage your site with composer, just install it like other composer
packages, dependencies will be resolved automatically.

Composer installs compiler library to the vendor folder, so be aware when update
core manually, library will be removed. After manual core update just download
library manually and place it to the drupal libraries folder, see manual
installation instruction.

## CONFIGURATION
All module settings are on the performance page.

## USAGE
```yml
# my_module.libraries.yml
main:
  version: VERSION
  css:
    theme:
      scss/styles.scss: {}
```
By default, compiled files are saved to `public://scss_compiler`

Also you can define `css_path` — path where to save the compiled file,
path relative to module/theme where libraries.yml place, for example:
```yml
# my_module.libraries.yml
main:
  version: VERSION
  css:
    theme:
      scss/styles.scss: { css_path: '/css/' }
```
File will be saved to `my_module/css/styles.css`

[1]: https://scssphp.github.io/scssphp/
[2]: https://github.com/scssphp/scssphp/releases
[3]: https://github.com/mnsami/composer-custom-directory-installer
