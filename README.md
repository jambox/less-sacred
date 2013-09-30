LESS Sacred
===========

Sacred Geometry Mixins for LESS CSS.

This set of mixins was created for use on a WordPress site for the architecture and design firm, [Concordia] (http://concordia.com/) in New Orleans, LA. Concordia takes pride in their respect and adherence to the rules of proportion found in nature and sacred geometries. These ratios and relationships guide their design work, so naturally, their website should, too.

Unfortunately, the designs were already in finalized when this was brought to my attention (_naturally_), so I thought the best course of action was to retrofit the comps we'd already designed in our _favorite creative professional software suite_. I decided to use three Sacred Ratios (listed below) and apply them to the site knowing that for each element in question one dimension would be set in stone, while the other dimension could be programatically generated...


The Available Ratios
------------

For use with this project, three (_tres_) Mixins were created available:

* 1:1.618 - "Golden Ratio" AKA "Phi"
* 1:1.437 - Silver or Root 2 Rectangle
* 1:2.2 - Root 5 rectangle

How this ol' thing works
------------

All of the mixins accept a dimension param and return a class with a calculated width or height dimension, depending on the namespace you use ('#make-width' and '#make-height', respectively). Basically, you pass a the value you already know, and choose the mixin based on the expected return value being either the "1" proportion, or the other side.

Example: Known width, make me a height
------------

On [Concordia's](http://concordia.com/) landing page there are four image links at the bottom whose width I designed to be `280px` when the inner column is at its widest limit (`1280px` with some padding). I thought it would look good with a 1:1.618 proportion with `280px` being the _longer_ edge, so, in order to get the shorter edge of the rectangle, I used `#make-height .1-618-shorter( @width )`:


	.homepage-footer {
	  	li {
	  		@width: 280px;
			.link-wrap {
			  width: @width;
			  #make-height .1-618-shorter( @width );
		    }
	  	}
	}

which produces:

	.homepage-footer li .link-wrap {
		width:280px;
		height: 174px;
	}

** _boom shaka laka_. **

Feel free contact me with any questions regarding the syntax or ideas to improve this lil' ol' liberry.

