# Buildit Development Space

## Installation and running locally

1. Clone repository: `git clone `
2. Run `bundle install` to install all dependencies ([Jekyll](http://jekyllrb.com/) 3.0, [Jekyll-Sitemap](https://github.com/jekyll/jekyll-sitemap), [Octopress](https://github.com/octopress/octopress), etc)
3. Build the application: `bundle exec jekyll build`
4. Run the application: `bundle exec jekyll serve`

---

## Site Setup

A quick checklist of the files you'll want to edit to get up and running.

### Authors

If you add any posts ensure you add your self to the `authors.yaml` listing so all your credentials are linked. This will be used to attach details of yourself to your posts.

```
username:
  name: Test User
  web: http://userwebsite.com
  email: test.user@username.com
  bio: "Some blurb about you"
  avatar: bio-photo.jpg
  twitter: T-username
  google:
    plus: G+-username
```

### Posts

Create new MarkDown (.md) files in `_posts`. There are two categories `blog` and `media`. Use the blog for all developer blog posts and media for all industry related media you find. These will automatically populate the relative listing pages when added. Refer to the [YAML configuration](#yaml-onfiguration) for details of what to include.

### Projects

Add your project to the `_data/projects.yaml` file to add your repository to the projects listing. Outline your project with the following configuration:

```
-   name: Name
    date:
    url: https://github.com/buildit/projectname
    title: Project-Title
    excerpt: "The best project yet"
    image: project-image.jpg
```

---

## Adding New Content with Octopress

While completely optional, also included is Octopress and some starter templates to automate the creation of new posts and pages.

### New Blog Post

To create a new blog post use the following command:

``` bash
$ octopress new post "New Blog Title" --dir blog --template blog
```

### New Media Post

To create a new media post use the following command.

``` bash
$ octopress new post "New Media Title" --dir media --template media
```

### New Page

To create a new page use the following command.

``` bash
$ octopress new page about/
```

This will create a page at `/about/index.md`

---

### YAML Configuration

The only YAML Configuration required for posts and pages are `title` and `layout`, everything else is optional.

#### Categories

`categories: ` are used to define whether the post is a post for `blog` or `media` section.

#### Modified Date

If you assign a modified date to a post or page it will override the published date and appear in the page footer with the following format `Updated August 27, 2014`. It's also used as metadata to give search engines another piece of info about your content.

You can use [Sublime Text plugin](https://github.com/FichteFoll/sublimetext-insertdate) to insert the current date after you update a post, but you can do it manually to. It should follow the same date format used by Jekyll when naming posts: `YYYY-MM-DD`.

```
modified: 2014-08-27
modified: 2014-08-27T11:57:41-04:00 # more verbose, also acceptable
```

#### Images

Here you can define the various images assigned to posts and pages.

##### Featured Images

A good rule of thumb is to keep feature images nice and wide so you don't push the body text too far down. An image cropped around around 1024 x 256 pixels will keep file size down with an acceptable resolution for most devices without bloating your site. If you want to level-up your site I'd suggest looking at the [Jekyll Picture Tag](https://github.com/robwierzbowski/jekyll-picture-tag) plugin[^plugins] to make them responsive.

[^plugins]: If you're using GitHub Pages to host your site be aware that plugins are disabled. You'll need to build your site locally and then manually deploy if you want to use this sweet plugin.

The post and page layouts make the assumption that the feature images live in the `images/` folder. To add a feature image to a post or page just include the filename in the configuration like so.

```
image:
  feature: feature-image-filename.jpg
```

To add attribution to a feature image use the following YAML Configuration on posts or pages. Image credits appear directly below the feature image with a link back to the original source (if supplied).

```
image:
  feature: feature-image-filename.jpg
  credit: Michael Rose #name of the person or site you want to credit
  creditlink: http://mademistakes.com #url to their site or licensing
```

##### Teasers Images

Teaser images appear on archive pages in the post grid and are also used in the off-canvas menu. If you don't assign a teaser image for a specific post or page, the default one will be used. The default image can be set in `_config.yml` under site wide configuration `teaser: 400x250.gif`. Teaser images should be roughly 400 x 250 pixels to scale comfortably across screen sizes.

Similar to feature images you don't want to go crazy and use large high resolution assets for your teasers. Keep in mind performance and balance accordingly.

To assign a teaser image on a post use the following YAML:

```
image:
  teaser: 400x250.gif
  feature: feature-image-filename.jpg
  credit: Michael Rose #name of the person or site you want to credit
  creditlink: http://mademistakes.com #url to their site or licensing
```

#### Table of Contents

For longer posts you may find it beneficial to include a table of contents menu. Add `{% include toc.html %}` where you'd like the TOC to appear and Kramdown will take care of the rest by converting all headlines to list of links.

If you need to alter the *Overview* headline text that appears at the top of the list, you can do so by editing `_data/messages.yml`.

#### Disqus Comments

A [Disqus](http://disqus.com) account is active for `builditwd` in `_config.yml` to enable commenting on a post. To enable commenting on a post, add the following to its YAML Configuration:

`comments: true`

#### Social Sharing Links

Social sharing links for Twitter, Facebook, and Google+ are included on posts/pages using the `article` and `media` layouts by default. To hide them on specific posts or pages add `share: false` to the YAML Configuration. If you'd like to use different social networks modify `_includes/share-this.html` to your liking. Icons are set using [Font Awesome](http://fontawesome.io/).

---

## Structure

All posts, layouts, includes, stylesheets, assets, and whatever else are grouped nicely under the root folder. The compiled Jekyll site outputs to `_site/`.

```
skinny-bones-jekyll-master
├── _data                               # location of lookup information - nav, authors, projects, etc.
├── _site                               # compiled site ready to deploy
├── _images                             # unoptimized images
├── _includes                           # reusable blocks for _layouts
├── _layouts                            # top level html page layouts for the pages
├── _posts                              # posts grouped by category for sanity
├── _sass
|   ├── vendor
|   |   ├── bourbon                     # Bourbon mixin library
|   |   └── neat                        # Neat grid library
|   ├── _animations.scss                # CSS3 animations
|   ├── _badges.scss                    # small badges
|   ├── _bullets.scss                   # visual bullets
|   ├── _buttons.scss                   # buttons
|   ├── _grid-settings.scss             # Neat settings
|   ├── _helpers.scss                   # site wide helper classes
|   ├── _layout.scss                    # structure and placement, the bulk of the design
|   ├── _mixins.scss                    # custom mixins
|   ├── _notices.scss                   # notice blocks
|   ├── _syntax.scss                    # Pygments.rb syntax highlighting
|   ├── _reset.scss                     # normalize and reset elements
|   ├── _sliding-menu.scss              # sliding menu overlay
|   ├── _variables.scss                 # global colors and fonts
|   ├── css
|   └── main.scss                       # loads all Sass partials
├── fonts                               # webfonts
├── images                              # images
├── js
|   ├── plugins                         # jQuery plugins
|   ├── vendor                          # vendor scripts that don't get combined with the rest
|   ├── _main.js                        # site scripts and plugin settings go here
|   └── main.min.js                     # concatenated and minified site scripts
├── apple-touch-icon-precomposed.png    # 152x152 px for iOS
├── atom.xml                            # posts feed
├── favicon.ico                         # 32x32 px for browsers
└── index.md                            # homepage content
└── _config.yml                         # Jekyll settings
```

### Site Wide Configuration

`_config.yml` is your friend. Open it up and personalize it, most variables are self explanatory.

### Pages

Pages are organised by placing an `index.md` in a folder of the approprate name to maintain pretty URLs e.g. `/about/index.md`.

The site is split into the following areas:
- **About**: Simple map and location for contact details
- **Blog**: Listing of blog posts grouped by month and year
- **Media**: Listing of indursty related videos
- **Projects**: Listing of our GitHub projects

### Navigation Links

To set what links appear in the top navigation edit `_data/navigation.yml`.

To set what links appear in the footer edit `_data/footer.yml`.

### Localization

There is support for localized text through a data file for the following text strings:

* Table of contents headline --- "Overview"
* Slide-out menu title --- "Table of Contents"
* Author byline --- "Written by"
* Post/page date --- "Updated"

To update or add other translations edit `_data/messages.yml` and then set the appropriate `locale` in `_config.yml`. For example to switch from English to German replace `locale: en` with `locale: de` or `locale: de_DE`.

Feel free to submit a pull request for additional languages and any other parts of the theme that could be localized.

---

## Contributing

Found a bug or aren't quite sure how something works? By all means [submit an issue](https://github.com/buildit/buildit.github.io/issues). For straight forward bug fixes feel free to submit pull requests.
