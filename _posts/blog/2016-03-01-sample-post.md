---
layout: blog
title: "Sample Post Style Guide"
categories: blog
modified: 2014-08-27T11:57:41-04:00
tags: [sample]
comments: true
ads: false
---

Below is just about everything you'll need to style in the theme. Check the source code to see the many embedded elements within paragraphs.

{% include toc.html %}

## Heading 2: Lorem ipsum dolor sit amet, test link adipiscing elit. **This is strong**. Nullam dignissim convallis est. Quisque aliquam.

### Heading 3: Lorem ipsum dolor sit amet, test link adipiscing elit. **This is strong**. Nullam dignissim convallis est. Quisque aliquam.

#### Heading 4: Lorem ipsum dolor sit amet, test link adipiscing elit. **This is strong**. Nullam dignissim convallis est. Quisque aliquam.

##### Heading 5: Lorem ipsum dolor sit amet, test link adipiscing elit. **This is strong**. Nullam dignissim convallis est. Quisque aliquam.

###### Heading 6: Lorem ipsum dolor sit amet, test link adipiscing elit. **This is strong**. Nullam dignissim convallis est. Quisque aliquam.

### Body text

Lorem ipsum dolor sit amet, test link adipiscing elit. **This is strong**. Nullam dignissim convallis est. Quisque aliquam.

*This is emphasized*. Donec faucibus. Nunc iaculis suscipit dui. 53 = 125. Water is H<sub>2</sub>O. Nam sit amet sem. Aliquam libero nisi, imperdiet at, tincidunt nec, gravida vehicula, nisl. The New York Times <cite>(That’s a citation)</cite>. <u>Underline</u>. Maecenas ornare tortor. Donec sed tellus eget sapien fringilla nonummy. Mauris a ante. Suspendisse quam sem, consequat at, commodo vitae, feugiat in, nunc. Morbi imperdiet augue quis tellus.

HTML and <abbr title="cascading stylesheets">CSS<abbr> are our tools. Mauris a ante. Suspendisse quam sem, consequat at, commodo vitae, feugiat in, nunc. Morbi imperdiet augue quis tellus. Praesent mattis, massa quis luctus fermentum, turpis mi volutpat justo, eu volutpat enim diam eget metus.

### Blockquotes

> Lorem ipsum dolor sit amet, test link adipiscing elit. Nullam dignissim convallis est. Quisque aliquam.

> <cite>First Lastname, *The Greatest Article*</cite>

## List Types

### Ordered Lists

1. Item one
	 1. sub item one
	 2. sub item two
	 3. sub item three
2. Item two

### Unordered Lists

* Item one
* Item two
* Item three

## Tables

| Header1 | Header2 | Header3 |
|:--------|:-------:|--------:|
| cell1   | cell2   | cell3   |
| cell4   | cell5   | cell6   |
|----
| cell1   | cell2   | cell3   |
| cell4   | cell5   | cell6   |

## Code Snippets

Syntax highlighting via Pygments

{% highlight css linenos=table %}
#container {
	float: left;
	margin: 0 -240px 0 0;
	width: 100%;
}
{% endhighlight %}

{% highlight ruby %}
module Jekyll
  class TagIndex < Page
    def initialize(site, base, dir, tag)
      @site = site
      @base = base
      @dir = dir
      @name = 'index.html'
      self.process(@name)
      self.read_yaml(File.join(base, '_layouts'), 'tag_index.html')
      self.data['tag'] = tag
      tag_title_prefix = site.config['tag_title_prefix'] || 'Tagged: '
      tag_title_suffix = site.config['tag_title_suffix'] || '&#8211;'
      self.data['title'] = "#{tag_title_prefix}#{tag}"
      self.data['description'] = "An archive of posts tagged #{tag}."
    end
  end
end
{% endhighlight %}

### GitHub Gist Embed

An example of a Gist embed below.

{% gist mmistakes/6589546 %}

Non Pygments code example

	<div id="awesome">
			<p>This is great isn't it?</p>
	</div>

## Buttons

Make any link standout more when applying the `.btn` class.

{% highlight html %}
<a href="#" class="btn">Default Button</a>
{% endhighlight %}

<a href="#" class="btn">.btn</a>
<a href="#" class="btn-inverse">.btn-inverse</a>
<a href="#" class="btn-info">.btn-info</a>
<a href="#" class="btn-warning">.btn-warning</a>
<a href="#" class="btn-danger">.btn-danger</a>
<a href="#" class="btn-success">.btn-success</a>

### Social Media Buttons

<a href="#" class="btn-social facebook"><i class="fa fa-facebook" aria-hidden="true"></i> Facebook</a>
<a href="#" class="btn-social flickr"><i class="fa fa-flickr" aria-hidden="true"></i> Flickr</a>
<a href="#" class="btn-social foursquare"><i class="fa fa-foursquare" aria-hidden="true"></i> Foursquare</a>
<a href="#" class="btn-social google-plus"><i class="fa fa-google-plus" aria-hidden="true"></i> Google+</a>
<a href="#" class="btn-social instagram"><i class="fa fa-instagram" aria-hidden="true"></i> Instagram</a>
<a href="#" class="btn-social linkedin"><i class="fa fa-linkedin" aria-hidden="true"></i> LinkedIn</a>
<a href="#" class="btn-social pinterest"><i class="fa fa-pinterest" aria-hidden="true"></i> Pinterest</a>
<a href="#" class="btn-social rss"><i class="fa fa-rss" aria-hidden="true"></i> RSS</a>
<a href="#" class="btn-social tumblr"><i class="fa fa-tumblr" aria-hidden="true"></i> Tumblr</a>
<a href="#" class="btn-social twitter"><i class="fa fa-twitter" aria-hidden="true"></i> Twitter</a>
<a href="#" class="btn-social vimeo"><i class="fa fa-vimeo-square" aria-hidden="true"></i> Vimeo</a>
<a href="#" class="btn-social youtube"><i class="fa fa-youtube" aria-hidden="true"></i> YouTube</a>

## Badges

<div class="badges">
	<span class="badge">1</span>
	<span class="badge inverse">2</span>
	<span class="badge info">3</span>
	<span class="badge warning">4</span>
	<span class="badge danger">5</span>
	<span class="badge success">6</span>
</div>

## Notices

Set a block of text off from the rest.

**Default Notice:** `.notice` Maecenas ornare tortor. [Donec sed tellus]() eget sapien fringilla nonummy. Mauris a ante. Suspendisse quam sem, consequat at.
{: .notice}

<div class="notice">
	<h3>Headline</h3>
	<div class="inline-btn">
		<a href="#" class="btn-social instagram"><i class="fa fa-instagram" aria-hidden="true"></i> Instagram</a>
		<a href="#" class="btn-social linkedin"><i class="fa fa-linkedin" aria-hidden="true"></i> LinkedIn</a>
	</div><!-- /.inline-btn -->
</div><!-- /.notice -->

**Inverse Notice:** `.notice-inverse` Maecenas ornare tortor. Donec sed tellus [eget sapien fringilla]() nonummy. Mauris a ante. Suspendisse quam sem, consequat at.
{: .notice-inverse}

**Info Notice:** `.notice-info` [Maecenas ornare tortor](). Donec sed tellus eget sapien fringilla nonummy. Mauris a ante. Suspendisse quam sem, consequat at.
{: .notice-info}

**Warning Notice:** `.notice-warning` Maecenas ornare tortor. Donec sed [tellus eget]() sapien fringilla nonummy. Mauris a ante. Suspendisse quam sem, consequat at.
{: .notice-warning}

**Danger Notice:** `.notice-danger` Maecenas ornare tortor.[ Donec sed tellus]() eget sapien fringilla nonummy. Mauris a ante. Suspendisse quam sem, consequat at.
{: .notice-danger}

**Success Notice:** `.notice-success` Maecenas ornare tortor. Donec sed tellus eget [sapien fringilla]() nonummy. Mauris a ante. Suspendisse quam sem, consequat at.
{: .notice-success}

## Fieldsets and Form Elements

<fieldset>
	<form>
		<h2>Form Element</h2>
		<p>Lorem ipsum dolor sit amet, consectetuer adipiscing elit. Nullam dignissim convallis est. Quisque aliquam. Donec faucibus. Nunc iaculis suscipit dui.</p>
		<label for="text_field">Text Field:</label>
		<input type="text" id="text_field" />
		<label for="text_area">Text Area:</label>
		<textarea id="text_area"></textarea>
		<p>
			<label for="select_element">Select Element:</label>
			<select name="select_element">
				<optgroup label="Option Group 1">
					<option value="1">Option 1</option>
					<option value="2">Option 2</option>
					<option value="3">Option 3</option>
				</optgroup>
				<optgroup label="Option Group 2">
					<option value="1">Option 1</option>
					<option value="2">Option 2</option>
					<option value="3">Option 3</option>
				</optgroup>
			</select>
		</p>
		<p>
			<label for="radio_buttons">Radio Buttons:</label>
			<label><input type="radio" class="radio" name="radio_button" value="radio_1" />Radio 1</label>
			<label><input type="radio" class="radio" name="radio_button" value="radio_2" />Radio 2</label>
			<label><input type="radio" class="radio" name="radio_button" value="radio_3" />Radio 3</label>
		</p>
		<p>
			<label for="checkboxes">Checkboxes:</label>
			<label><input type="checkbox" class="checkbox" name="checkboxes" value="check_1" />Checkbox 1</label>
			<label><input type="checkbox" class="checkbox" name="checkboxes" value="check_2" />Checkbox 2</label>
			<label><input type="checkbox" class="checkbox" name="checkboxes" value="check_3" />Checkbox 3</label>
		</p>
		<p>
			<label for="password">Password:</label>
			<input type="password" class="password" name="password" />
		</p>
		<p>
			<label for="file">File Input:</label>
			<input type="file" class="file" name="file" />
		</p>
		<p>
			<input class="btn" type="submit" value="Submit" />
		</p>
	</form>
</fieldset>

## Figures (for images or video)

### One Up

<figure>
	<a href="http://placehold.it/900x450.gif"><img src="http://placehold.it/900x450.gif"></a>
	<figcaption>Image caption.</figcaption>
</figure>

### Two Up

Apply the `half` class like so to display two images side by side that share the same caption.

{% highlight html %}
<figure class="half">
	<img src="{{ site.url }}/images/image-filename-1.jpg">
	<img src="{{ site.url }}/images/image-filename-2.jpg">
	<figcaption>Caption describing these two images.</figcaption>
</figure>
{% endhighlight %}

And you'll get something that looks like this:

<figure class="half">
	<a href="http://placehold.it/1200x600.gif"><img src="http://placehold.it/900x450.gif"></a>
	<a href="http://placehold.it/1200x600.gif"><img src="http://placehold.it/900x450.gif"></a>
	<figcaption>Two images.</figcaption>
</figure>

### Three Up

Apply the `third` class like so to display three images side by side that share the same caption.

{% highlight html %}
<figure class="third">
	<img src="{{ site.url }}/images/image-filename-1.jpg">
	<img src="{{ site.url }}/images/image-filename-2.jpg">
	<img src="{{ site.url }}/images/image-filename-3.jpg">
	<figcaption>Caption describing these three images.</figcaption>
</figure>
{% endhighlight %}

And you'll get something that looks like this:

<figure class="third">
	<img src="http://placehold.it/900x450.gif">
	<img src="http://placehold.it/900x450.gif">
	<img src="http://placehold.it/900x450.gif">
	<figcaption>Three images.</figcaption>
</figure>

### Video container

<iframe width="560" height="315" src="//www.youtube.com/embed/9e1nPyHXCFQ" frameborder="0"> </iframe>
