---
published: true
permalink: "market-research-library.html"
title: Market Research Library API
layout: body
---

#<a href="market-research-library.html">Market Research Library API</a>
This API provides metadata for country and industry reports that are produced by ITA’s trade experts and are available in ITA’s online market research library.  Categorized by country and industry, these reports include:

* Market Research Reports
* Best Market Reports
* Country Commercial Guides

##Resource URL

    http://api.trade.gov/market_research_library/search
</br>
##Search Parameters

###keyword

Returns market research reports for a match in the description or title fields.

    http://api.trade.gov/market_research_library/search?q=<keyword>

#####Example:

    http://api.trade.gov/market_research_library/search?q=modernization
</br>
###countries

Returns office locations based on ISO [alpha-2 country codes](http://www.iso.org/iso/home/standards/country_codes/country_names_and_code_elements.htm).

    http://api.trade.gov/market_research_library/search?countries=<country name>

#####Example:

    http://api.trade.gov/market_research_library/search.json?countries=MX
</br>
###industry

Returns market research reports for a specific [industry](industry-list-market-research-library.html)

    http://api.trade.gov/market_research_library/search.json?industry=<industry name>

#####Example:

    http://api.trade.gov/market_research_library/search.json?industry=agribusiness
</br>
###size + offset

The size parameter allows you to configure the maximum amount of hits to be returned. The offset parameter defines the offset from the first result you want to fetch.

#####Example:

    http://api.trade.gov/market_research_library/search?country=BR&size=1&offset=1
</br>
##Return Values

| Field           | Description                                                     |
| --------------- | --------------------------------------------------------------- |
| <pre><code>id</code></pre>             | Unique identifier assigned to the event                         |
| <pre><code>countries</code></pre>     | Country category(ies) assigned to the report                    |
| <pre><code>description</code></pre>     | Abstract of the report’s content                                |
| <pre><code>expiration_date</code></pre> | Date when the report is no longer valid                         |
| <pre><code>industry</code></pre>        | Industry category assigned to the report                        |
| <pre><code>report_type</code></pre>     | The report type can either be CCG, Best Market Report, or Market Research Report|
| <pre><code>title</code></pre>           | Report title  (default sort)                                    |
| <pre><code>url</code></pre>             | URL for the report                                              |