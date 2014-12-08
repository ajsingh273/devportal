---
published: true
permalink: "market-research-library.html"
title: Market Research Library API
layout: body
---

#Market Research Library API

</br>

<div class="tabs">

<input checked="checked" id="step1radio" name="radio" type="radio" /><label class="first" for="step1radio">Background</label>
<input id="step2radio" name="radio" type="radio" /><label for="step2radio">Why This Data Matters</label>
<input id="step3radio" name="radio" type="radio" /><label class="last" for="step3radio">Ideas for Using the Data</label>
<div class="pane" id="step1"><p>The Market Research Library API provides metadata for country and industry reports that are produced by ITA’s trade experts and are available in ITA’s online market research library.  ITA commercial officers that are stationed around the world, publish these authoritative reports in conjunction with Foreign Service officers from the State Department.</p><p>The API only provides the metadata and links to the reports – not the reports themselves.  The output format for this API is JSON.  Test the API using the <a href="http://internationaltradeadministration.github.io/explorer/#/market-research-library">demo search app</a>.</p></div>
<div class="pane" id="step2"><p>U.S. businesses can use these reports to plan their market-entry the right way.  The reports help them learn their product’s potential in a given market and the best prospects for success.</p><p>There are three report_types categorized by country and industry:</p><ol><li>Market Research Reports</li><li>Best Market Reports</li><li>Country Commercial Guides</li></ol></div>
<div class="pane" id="step3"><p>Use these reports to augment other market intelligence that you provide for your customers.  For example, WebPort Global provides access to ITA’s reports alongside market research from the World Trade Center of Dublin, the World Bank Group, and the Small Business Administration.</p><p>The API provides methods for accessing the reports by country or by industry.  Therefore, you can display links to specific reports depending upon which country or industry your customer is interested in.  The API also provides access to two years worth of reports so you may want to use the expiration_date field to display only the most recent.</p></div>

</div>


##Resource URL

[http://api.trade.gov/market_research_library/search](http://api.trade.gov/market_research_library/search)

##Search Parameters for market research library sources

###keyword

Returns market research reports for a match in the **description** or **title** fields.

    http://api.trade.gov/market_research_library/search?q={keyword}

**_Example_**

[http://api.trade.gov/market_research_library/search?q=modernization](http://api.trade.gov/market_research_library/search?q=modernization)

###countries

Returns office locations based on ISO [alpha-2 country codes](http://www.iso.org/iso/home/standards/country_codes/country_names_and_code_elements.htm).

    http://api.trade.gov/market_research_library/search?countries={country code}

**_Example_**

[http://api.trade.gov/market_research_library/search?countries=MX](http://api.trade.gov/market_research_library/search?countries=MX)

###industry

Returns market research reports for a specific [industry](industry-list-market-research-library.html)

    http://api.trade.gov/market_research_library/search?industry={industry name}

**_Example_**

[http://api.trade.gov/market_research_library/search?industry=agribusiness](http://api.trade.gov/market_research_library/search?industry=agribusiness)

###size + offset

The **size** parameter allows you to configure the maximum amount of hits to be returned. The **offset** parameter defines the offset from the first result you want to fetch.

**_Example_**

[http://api.trade.gov/market_research_library/search?country=BR&size=1&offset=1](http://api.trade.gov/market_research_library/search?country=BR&size=1&offset=1)

###Return Values

| Field           | Description                                                     |
| --------------- | --------------------------------------------------------------- |
| id              | Unique identifier assigned to the event                         |
| countries       | Country category(ies) assigned to the report                    |
| description     | Abstract of the report’s content                                |
| expiration_date | Date when the report is no longer valid                         |
| industry        | Industry category assigned to the report                        |
| report_type     | The report type can either be CCG, Best Market Report, or Market Research Report|
| title           | Report title  (default sort)                                    |
| url             | URL for the report                                              |