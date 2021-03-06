## sprite-brunch
Sprite Generator for [brunch](http://brunch.io).
It uses [Spritesmith](https://github.com/Ensighten/spritesmith) and [json2css](https://github.com/twolfson/json2css) to generate sprites and language agnostic styles

## Installation

To generate the sprites Cairo Spritesmith needs [node-canvas](https://github.com/learnboost/node-canvas) or [gm](https://github.com/aheckmann/gm).
Check out the [Spritesmith](https://github.com/Ensighten/spritesmith#requirements) website for details

## Config
```coffeescript
sprites:
	path: 'app/assets/images/sprites' # Path to your sprites folder
	destCSS: 'sass/_sprites.sass' # Destination sass/less/stylus files
	cssFormat: 'sass' # less, sass, scss, stylus
	algorithm: 'top-down' # algorithm: top-down, left-right, diagonal (\ format), alt-diagonal
	engine: 'canvas' # canvas, gm
	imgOpts:
		format: 'auto' # auto, jpg, png (If auto is used and there is png and jpg in a folder the sprite will be jpg)
		quality: 90 # Quality of the output image

```

## Usage
It expects the following folder structure and uses the folder name as first value and the filename as the second

```
app/assets/images/sprites/icons
	icona.png
	iconb.png
app/assets/images/sprites/backgrounds
```

# SASS Example

```sass
#test
	+sprite($icons, $icona)
```

Add `"sprite-brunch": "0.0.2"` to `package.json` of your brunch app.

Pick a plugin version that corresponds to your minor (y) brunch version.

If you want to use git version of plugin, add
`"sprite-brunch": "git+ssh://git@github.com:mllrsohn/sprite-brunch.git"`.
