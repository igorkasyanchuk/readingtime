# Estimate Reading Time

## How to Use

[readingtime](https://github.com/igorkasyanchuk/readingtime "Gem to estimate reading time") extends the Ruby String class, so you can call `reading_time` on any `String` object.

### Install

	gem install readingtime

### In irb

	$ irb
	> require 'readingtime'
		=> true
	> @words = "Lorem ipsum dolor sit amet"
	> @words.reading_time
		=> "00:01"

### In Your App

	<article>

		<header>
			<h1><%= @article.title %></h1>
			<span class="readingtime">Estimated reading time – <%= @article.body.reading_time %></span>
		</header>

		<%= @article.body %>

	</article>

And voila!

![Screenshot of readingtime in use](https://s3.amazonaws.com/github-screenshots/garethrees/readingtime/readingtime-view.png "Screenshot of readingtime in use")

### Options

You can also send in options to modify the formatting.

	# Default output
	@article.body.reading_time :format => :basic
	=> "03:36"

	# Longer text output
	@article.body.reading_time :format => :long
	=> "3 minutes and 36 seconds"

	# Full text output
	@article.body.reading_time :format => :full
	=> "1 hr 3 mins 36 secs"

	# Raw output
	@article.body.reading_time :format => :raw
	=> [1, 12, 23]
	# [hours, minutes, seconds]

## Thanks

Credit goes to [Brian Cray](http://briancray.com/2010/04/09/estimated-reading-time-web-design "Brian Cray - Estimated Reading Time in Web Design") for explaining how to do it in PHP.
