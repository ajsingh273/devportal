---
permalink: "ita-office-locations.html"
layout: body
title: ITA Offices & Centers API
published: true
---

#<a href="ita-office-locations.html">ITA Offices & Centers API</a>

This API provides contact and address information for all of ITA’s domestic and international export assistance centers. Incorporating these listings into directories of business counseling services is one example of how developers can use this API to assist exporters.

##Resource URL

<a href="http://api.trade.gov/ita_office_locations/search"><pre>http://api.trade.gov/ita_office_locations/search</pre></a>
</br>
##Search Parameters

###keyword

Returns office locations for a match within the post or office name fields.

    http://api.trade.gov/ita_office_locations/search?q={keyword}

#####Example:

<a href="http://api.trade.gov/ita_office_locations/search?q=Sao+Paulo"><pre>http://api.trade.gov/ita_office_locations/search?q=Sao+Paulo</pre></a>
</br>
###city

Returns office locations based on city name

<a href="http://api.trade.gov/ita_office_locations/search?city=Sao+Paulo"><pre>http://api.trade.gov/ita_office_locations/search?city=Sao+Paulo</pre></a>
</br>
###country

Returns office locations based on ISO [alpha-2 country codes](http://www.iso.org/iso/home/standards/country_codes/country_names_and_code_elements.htm).

    http://api.trade.gov/ita_office_locations/search?country={country code}
	
#####Example:

<a href="http://api.trade.gov/ita_office_locations/search?country=BR"><pre> http://api.trade.gov/ita_office_locations/search?country=BR</pre></a>
</br>
###state

Returns locations for export assistance centers located in a specific  [U.S. State or Dependent Area](https://www.usps.com/send/official-abbreviations.htm).

    http://api.trade.gov/ita_office_locations/search?state
	={state postal code abbreviation>}

#####Example:

<a href="http://api.trade.gov/ita_office_locations/search?state=TN"><pre>http://api.trade.gov/ita_office_locations/search?state=TN</pre></a>
</br>
###size + offset

The size parameter allows you to configure the maximum amount of hits to be returned. The offset parameter defines the offset from the first result you want to fetch.

#####Example:

<a href="http://api.trade.gov/ita_office_locations/search?country=BR&size=1&offset=1"><pre>http://api.trade.gov/ita_office_locations/search?country=BR&size=1&offset=1</pre></a>

</br>
##Data Elements

| Field             | Description                                                     |
| ----------------- | --------------------------------------------------------------- |
| <pre><code>id</code></pre>                | Unique identifier for post                                      |
| <pre><code>post</code></pre>              | Name of the post (Default sort)                                 |
| <pre><code>office_name</code></pre>       | Office Name                                                     |
| <pre><code>state</code></pre>             | State abbreviation, for domestic offices                        |
| <pre><code>city</code></pre>              | City                                                            |
| <pre><code>address</code></pre>           | Street address of office                                        |
| <pre><code>email</code></pre>             | Office email address                                            |
| <pre><code>fax</code></pre>               | Fax number                                                      |
| <pre><code>mail_instructions</code></pre> | Snail mail instructions                                         |
| <pre><code>phone</code></pre>             | Office phone number                                             |
| <pre><code>post_type</code></pre>         | Type of post (domestic or international)                        |