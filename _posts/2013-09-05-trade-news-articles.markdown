---
permalink: "trade-news-articles.html"
layout: body
title: Trade News & Articles API
published: true
---

#Trade News & Articles API

The Trade News & Articles API provides in-depth news and articles written by Trade Specialists working in the Federal government.  The news and articles are categorized by industry, country, and topic area.  Developers can use this API to provide exporters with the latest insights into their industry and into the countries with which they would like to do business.

##Resource URL

    http://api.trade.gov/trade_articles/search
</br>
##Request Methods

###keyword

Returns articles for a match in the content and body fields.

    http://api.trade.gov/trade_articles/search?q=<keyword>

#####Example:

    http://api.trade.gov/trade_articles/search?q=logistics
</br>
###evergreen

Flag to designate articles that are always relevant to particular topic.

    http://api.trade.gov/trade_articles/search?evergreen={true or false}

#####Example:

    http://api.trade.gov/trade_articles/search?evergreen=true
</br>
###pub_date
####pub_date_start

Returns articles created on or after a specific date.

    http://api.trade.gov/trade_articles/search?pub_date_start={YYYY-MM-DD}

#####Example

    http://api.trade.gov/trade_articles/search?pub_date_start=2013-01-04
</br>
####pub_date_end

Returns articles created on or before a specified date.

    http://api.trade.gov/trade_articles/search?pub_date_end={YYYY-MM-DD}

#####Example

    http://api.trade.gov/trade_articles/search?pub_date_end=2013-01-07
</br>
###update_date

Returns articles created on a specified date.

    http://api.trade.gov/trade_articles/search?update_date={YYYY-MM-DD}

#####Example

    http://api.trade.gov/trade_articles/search?update_date=2013-04-30
</br>
###size + offset

The size parameter allows you to configure the maximum amount of hits to be returned. The offset parameter defines the offset from the first result you want to fetch.

#####Example:

    http://api.trade.gov/trade_articles/search?q=logistics&size=1&offset=1
</br>   
##Return Values

| Field             | Description                                                     |
| ----------------- | --------------------------------------------------------------- |
| <pre><code>id</code></pre>                | Unique identifier for post                                      |
| <pre><code>evergreen</code></pre> | Flag to designate "timeless" articles, always topically relevant |
| <pre><code>content</code></pre>	| Body of the article |
| <pre><code>pub_date</code></pre> | Earliest date article can be published (default sort) |
| <pre><code>title</code></pre> | Title of the article |
| <pre><code>update_date</code></pre> | Date the article was last updated |
| <pre><code>content_type</code></pre> | Type of content embodied by the article |
| <pre><code>export_phase</code></pre> | Phase of exporting that a business should be in to benefit from the article |
| <pre><code>industry</code></pre> | Industry category assigned to this article |
| <pre><code>topic</code></pre> | Topic assigned to this article |
| <pre><code>subtopic</code></pre> | Subtopic assigned to this article |
| <pre><code>trade_region</code></pre> | Trade region covered by an article's content |
| <pre><code>geo_region</code></pre> | World region covered by an article's content |
| <pre><code>geo_subregion</code></pre> | Would sub-region covered by an article's content |
| <pre><code>country</code></pre> | Country covered by an article's content |
| <pre><code>keyword</code></pre> | Keywords assigned by the article's author |