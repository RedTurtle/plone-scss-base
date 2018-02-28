[![Build Status](https://travis-ci.org/RedTurtle/plone-scss-base.svg?branch=master)](https://travis-ci.org/RedTurtle/plone-scss-base)

# plone-scss-base

Base scss styles for Plone 5 theming

## Use case

We use these styles while bootstrapping a new theme with [plonecli](https://pypi.python.org/pypi/plonecli), in order to have basic plone styles ready and save some time on development.

## Usage

In order to use this correctly, you will need to tell your sass compiler to also read files from the `node_modules` folder.

* If you use it through the node-sass cli, by adding the `--include-path node_modules` argument
* If you configure it with a js object, add the `includePaths` property, which will look like this: `includePaths: ['node_modules']`

This is needed because the syles inside this package read other styles from its `bootstrap-sass` dependency, and it will also make is smoother for you to use these styles.

In order to add these styles to your theme styles, import it like this:

```scss
@import 'plone-scss-base/styles';
```

To customize these styles, make a copy of the [bootstrap variables file](https://github.com/twbs/bootstrap-sass/blob/master/assets/stylesheets/bootstrap/_variables.scss), customize it with your own values (be sure to remove the `!default` statements from your variables), and import it before these package styles, like this:

```scss
@import 'my_variables';
@import 'plone-scss-base/styles';
```

## Modular import

If you don't need all of the styles provided here, you can cherry-pick the partials you need by making a copy of the [main stylesheet of this package (styles.scss)](https://github.com/RedTurtle/plone-scss-base/blob/master/styles.scss) and commenting the partials you don't need.

## Installation

```sh
npm install --save plone-scss-base
```

## Compatibility

These styles are developed for Plone 5.x sites. Styles compilation is currently tested only with node-sass.

## License

MIT
