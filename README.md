
# Hugo-plus
A modular featured-packed Hugo theme that's built using Bootstrap components.
The idea is to provide a large foundation of componets that can targetted to
	provide a consistent set of features across Hugo themes.
Each theme should provide a different layout while allowing the Bootstap theme
	to be interchangeable.
In theory this foundation will allow you to have your own Bootstrap theme that
	can then be applied to different layouts, each supporting a similar set of
	features.

### Why?
Hugo has potential, but it's a pain to use due to its poor documentation and
	inconsistency between themes.
This project is meant to provide a set of guidelines, conventions, structure,
	and completely functional base on which to build.

### Who?
Targeted at lazy developers that value their time and want a solution to host
	their thoughts, portfolio, and projects while having full control of the
	final product.
This project chock-full of features to use, learn from, and build off of.
Nothing should be left to magic.


# Features
* Support for `meta` pages to hide from content feeds. (about, archive, etc)
* Ability to render arbitrary custom pages for any content through the `page` parameter
* Fully Bootstrapped responsive default layouts
* Disqus comment integration
	* Optional on-demand comment loading
		* Auto loads if user jumps to comment section through "#comments" anchor
	* Comment count querying
		* Custom script to inject "No comments" when Disqus fails to
* Breadcrumb support for Taxonomies
* Social sharing buttons
* Auto updating copyright year insertion
	* exmple: `(c) 2015` will become `(c)2015-2016` once 2016 rolls around
* Categories label buttons and Tag menu per post
* Categories panel
* Recent Posts panel
* About Author panel
	* Doesn't show up on the author's bio page
	* If Author is not specified for content, it defaults to the main author
* Mutliple Author support
	* Useful for things like guest posts
	* May not be suitable for a larger content publishing site due to Hugo's limitations
* Syntax highlighting for code with customizable theme per content


# Getting Started
First, [download and install Hugo.](http://gohugo.io/)

Next, [dowload hugo-plus directly](https://github.com/H4tch/hugo-plus/archive/master.zip),
	or clone it by typing:
> git clone https://github.com/H4tch/hugo-plus/

This project is meant to be a starting base from which you can build off of,
	customize, and fill in with content.


### Writing Content
Creating new content is done using Hugo's `new` command from the site folder.
> hugo new blog/first-post.md

This creates new content of type `post` within the `blog` *section* found
	in `content/blog`.
This content will be written and formatted using MarkDown as denoted by the
	`md` extension.
Content can be organized by Section, Type, and Taxonomy.
In the next sections we'll see the abilities and trade-offs involved with each.

## Organizing Content Using Taxonomies
### Creating Your Own Taxonomy
## Organizing Content Using Sections
### When to Override `Types`?
## Overview of Templates
### How is the Site Built?
### What Pre-Made Templates Exist?
## Customizing the Bootstrap Theme's Look and Feel
Bootstrap is used as the foundation due to its ubiquity and popularity in this
industry. Applying a Bootstrap theme is done by replacing
`static/css/hugo-plus.min.css` with the one you want.

There are many themes available for free, but you may want to create
your own or customize an existing one.

If you google `bootstrap theme editor` you can find an editor that allows you
create your own theme. Some also allow you to download the `variables.less`
file which is used to compile into the final css file. This can be useful if
you want to modify the theme in the future.

### Compiling and Customizing From Source
Bootstrap is written using Less, which is then compiled into CSS.
Before we continue, you'll need to setup the toolchain.

First you'll need to [install nodejs](http://nodejs.org/download/).

Once, nodejs is setup, The Less compiler can now be installed though `npm`. (This may require admin privileges.)
> npm install -g less

The source files for Bootstrap and the hugo-plus theme is stored within the 
`style-src/` directory.
Most changes to the theme can done within `bootstrap/variables.less`.

To compile the less into css and apply it to the website, run:
> lessc --compress hugo-plus.less > ../static/css/hugo-plus.min.css

If you are on Linux, the `listen.sh` script will recompile the theme
whenever the `bootstrap` folder is updated.



# Todo
#### Documentation
* How is this different from Hugo?
	* We support multiple Authors, Project page, Series, etc
	* Don't use Hugo's plural/singular system for taxonomies
	* Don't use .Params.description
		* Not worth increased template complexity
		* The Summary section of content is preferred instead
	* Hidden `meta` content
* Guidelines
	* Don't use `isset`. A Parameter may be set, but empty.
* Sections
* Taxonomies
* Parameters
	* Site Parameters
	* Content Parameters
	* Custom Parameters
		* Visually separate them from the default ones. Let me know about them!
* Page
* Blog
* Authors
* Series
* Streams
* Layout Structure
#### In-progress
* Project section page, summary, etc
* Summary area should be used for Streams, Series, Projects, etc
	* More summary implementations
* Use List view as a short Summary view, like a thumbnail
* More template layouts for things like Projects or Portfolios
	* Homepage groups and showcases content using overloaded Summary templates
* Use Hugo's menu system to render breadcrumbs
	* I need a way to parameterize the template code though
#### Future
* Follow buttons for author
* Rss links for Taxonomies and Sections.
* Don't use partial system for customized Sections
	* Use `{{ template "file.html" }}`
* Table of contents
	* The system provided doesn't work well
	* Maybe just have a paramter to enable TOC?
* Customized Summary pages for different Sections
* Reflect current page/section within the navigation bar
* Group content by year within 'list' pages
* Can idividual Taxonomy Term pages be customized?
	* Sections could be used to better address this? yes
* 'Hide comments' button(When unhiding, the comments shouldn't have to reload)
* URL shortener integration for sharing
	* Best implementation would be to hook into a Go function?
* Email button
* Host documentation for projects (via Doxygen)
* Forum support (via Discourse)
* Shortcodes - Plugins for adding to content (NOTE, currently working...)
	* Carousal
	* Thumbnail (caption, link, full res version) + thumbnail browser
	* Gallery, maybe tied in with Thumbails
	* Youtube, with subscribe and other widgets?
	* Gist
	* Link to a Source File with syntax highlighting
	* Amazon Affiliate Links
	* Plot/Graph data
	* Google-trends


#### (c) 2015 Daniel Hatch (h4tch)

