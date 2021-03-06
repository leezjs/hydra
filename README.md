Hydra
=====

Hydra is a Javascript game engine for mobile browsers. It's been used in several
commercial HTML5 games:

* [Block Dream](http://aduros.emufarmers.com/html5/blockdream) ([source](http://github.com/aduros/hydra/tree/master/projects/tetris/))
* [Fruit Link](http://aduros.emufarmers.com/html5/fruitlink) ([source](http://github.com/aduros/hydra/tree/master/projects/jam/))
* [Snow Bound](http://aduros.emufarmers.com/html5/snowbound) ([source](http://github.com/aduros/hydra/tree/master/projects/ski/))
* [Blast Effect](http://aduros.emufarmers.com/html5/blasteffect) ([source](http://github.com/aduros/hydra/tree/master/projects/chain/), WebKit only for now)
* [Playstore Games](http://playstore.vn/) (Who Wants to be a Millionaire, and Vietnamese card games)

Status
------

Work on Hydra has stopped, but the lessons learned on this project are going toward
[Flambe](https://github.com/aduros/flambe), a framework for rapid development of mobile and desktop
games.

Design
------

Hydra aims to be fast:

* Animations are implemented as CSS transitions, which can be hardware accelerated.
* All game updates are performed on a single setInterval callback.
* Games are compiled with Google's Closure Compiler in "advanced" mode, allowing aggressive inlining and dead-code elimination.

Hydra also aims to be functional:

* Animations can programmatically be started, paused, and sequenced together.
* Games are composed from scenes, entities (which live in scenes) and tasks (which act upon entities).
* Has the usual collection of utility functions and classes, supplemented by the massive Closure Library.
* Needless abstractions are avoided, you should still know how to work with the DOM and skin your game with CSS.

Platforms
---------

Hydra currently has three heads:

* iOS 3+ (iPhone, iPod touch, iPad)
* Android 2.1+
* Desktop browsers: Chrome, Safari, Firefox, Opera

Building
--------

Hydra is still undocumented, filled with broken glass, and will eat your first
born child. If you still want to try to tame it:

Download the Closure submodule:

    git submodule init
    git submodule update

Use [Rake](http://rake.rubyforge.org/) to build an example project:

    cd projects/chain
    rake

The "chain" (Blast Effect) and "ski" (Snow Bound) games are probably the best
places to learn your way around by example.

`rake` by itself will build the entire game for all supported browsers. For
development, you can use `rake js` to only build for the browser specified by
`DEFAULT_TARGET`. `rake css` will build only the CSS.
