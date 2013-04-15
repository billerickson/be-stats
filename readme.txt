=== BE Stats ===
Contributors: billerickson
Tags: popular, popularity, stats, listing
Requires at least: 3.0.1
Tested up to: 3.5.1
Stable tag: 1.1
License: GPLv2 or later
License URI: http://www.gnu.org/licenses/gpl-2.0.html

Keeps track of your most popular posts for display in site

== Description ==

This is a helper plugin to allow you to build WordPress queries using WordPress.com stats.

This plugin uses the WordPress.com stats (packaged in Jetpack) to find out your most popular posts. You must be running Jetpack for this plugin to work. I recommend running Jetpack for at least 30 days to get useful data.

It asks for the 100 most popular posts over the past 30 days. This includes both posts and pages, since their stats don’t let you filter based on post type. I filter this list down to just posts and then store its ranking as post meta ('be_stats'). 

You can [write custom queries](https://gist.github.com/billerickson/4997202) to list popular posts, or use the [Display Posts Shortcode plugin](http://wordpress.org/extend/plugins/display-posts-shortcode/) to do it for you. Examples using the shortcode plugin:

[display-posts orderby="popular"] - Lists the 10 most popular posts
[display-posts orderby="popular" posts_per_page="4"] - Lists the 4 most popular posts
[display-posts orderby="popular" posts_per_page="4" tag="basic"] - Lists the 4 most popular posts tagged "basic"

== Changelog ==

= 1.1 =
* Fix PHP Notice, props jjeaton

= 1.0 =
* Initial Version

== For Developers ==

There are a few filters available to you for customization. Refer to the plugin's code for more information.

be_stats_args - arguments passed to WordPress.com Stats API. 
Default: array( 'days' => 30, 'limit' => 100 )
Example: http://www.billerickson.net/code/customize-be-stats-arguments/

be_stats_update - Conditional for determining if stats data should be saved
Default: 'post' == get_post_type()
Example: http://www.billerickson.net/code/be-stats-change-ranking-conditions/