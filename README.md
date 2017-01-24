<!--
[![Published on webcomponents.org](https://img.shields.io/badge/webcomponents.org-published-blue.svg)](https://www.webcomponents.org/element/the-catalin/cat-animation)
-->

# cat-animation

includes:
&lt;cat-fade-animation&gt;
&lt;cat-scale-animation&gt;
&lt;cat-slide-animation&gt;
&lt;cat-zoom-animation&gt;

`cat-animation` includes a set of animations and behaviors designed to add efects to [Polymer](https://github.com/Polymer/polymer) elements. It is similar to [neon-animation](https://www.webcomponents.org/element/PolymerElements/neon-animation) but uses CSS transitions directly instead of Web Animations and, more importantly, `cat-animation` has persistency, meaning once an effect is ended, the element will not revert to the initial state. Instead, it will remain as it was modified by the animation.

## Demo

Currently, there are no dedicated demos for these animations, but some of the effects can be tested on the [Live Demo](http://webcomponents.online/cat-image/) of [cat-image](https://www.webcomponents.org/element/the-catalin/cat-image)

## Install

Install the component using [Bower](http://bower.io/):

```sh
$ bower install --save cat-animation
```

Or [download as ZIP](https://github.com/the-catalin/cat-animation/archive/master.zip)

## Usage

1. Import Web Components' polyfill (if needed):

    ```html
    <script src="bower_components/webcomponentsjs/webcomponents-lite.min.js"></script>
    ```

2. Import behavior and animation:

    ```html
    <!-- Import the behavior that allows you to add animation to your elements -->
    <link rel="import" href="bower_components/cat-animation/cat-animation-runner-behavior.html">

    <!-- Import every animation that you want to use (fade, slide, scale, etc), like this: -->
    <link rel="import" href="bower_components/cat-animation/animations/cat-zoom-animation.html">
    ```

3. Add `CatAnimationRunnerBehavior` to your Polymer element:

	```js
	Polymer({      

	    is: 'my-custom-element',

	    behaviors: [Polymer.CatAnimationRunnerBehavior],

	    properties: {
	    	...
	    }
	```

4. Initialize an element with a desired animation:

	```js
	this.addAnimation('animationSet', {
	    name: 'cat-slide-animation',
	    node: this,
	    slide: 'in',
	    direction: 'right',
	    offset: 100,
	    function: 'ease-in',
	    duration: 2,
	    delay: 0,
	    reverseDuration: 0.5
	});
	```

	'animationSet' is a string with any name. If you call `addAnimation` on the same string name multiple times, when you will later trigger the `play` function on that name, all the animations added to that name will be played.
	
	'node' can be `this` (the Polymer element itself), or any other element inside it.

5. Play the animation

	```js
	this.play('animationSet');
	```

	optionally, you can reverse the animation later:

	```js
	this.reverse('animationSet');
	```


## Contributing

1. Fork it!
2. Create your feature branch: `git checkout -b my-new-feature`
3. Commit your changes: `git commit -m 'Add some feature'`
4. Push to the branch: `git push origin my-new-feature`
5. Submit a pull request

## History

For detailed changelog, check [Releases](https://github.com/the-catalin/cat-animation/releases).

## License

[The MIT License (MIT)](https://opensource.org/licenses/MIT)

Copyright (c) 2017 Catalin Ungureanu