theme-mediaelement
=====================

Base stylesheet for theme developers to work with the WordPress media player (mediaelement.js).

=== Goal ===

Give theme authors an easy way to overwrite the WordPress mediaelement styles (3.6+ audio/video player).

=== Development ===

Follow the "/dev" branch for the latest updates.  Please make pull requests and patches against that branch rather than the master branch.

https://github.com/justintadlock/theme-mediaelement/tree/dev

=== Usage ===

Either load the "mediaelements.min.css" file via `wp_enqueue_script()` or `@import()` it at the top of your `style.css`.  Then, add the following to your `functions.php`.

	add_action( 'wp_enqueue_scripts', 'my_deregister_styles' );

	function my_deregister_styles() {
		wp_deregister_style( 'mediaelement' );
		wp_deregister_style( 'wp-mediaelement' );
	}

=== Todo ===

* Figure out elements that I don't understand yet. :)
* Remove as much "style" as possible, including fonts, colors, and backgrounds.
* Don't rely on any images (maybe).  Allow theme devs to handle this.
* Simplify.  Simplify.  Simplify.

=== Resources ===

* http://mediaelementjs.com

=== Structure ===

Basic structure of the media player:

	<div class="mejs-container">
		<div class="mejs-inner">
			<div class="mejs-mediaelement">
				<audio class="wp-audio-shortcode">...</audio>
			</div>
			<div class="mejs-layers">
				<div class="mejs-layer">...</div>
			</div>
			<div class="mejs-controls">
				<div class="mejs-button"></div>
			</div>
			<div class="mejs-clear">...</div>
		</div>
	</div>