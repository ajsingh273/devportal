---
permalink: "trade-events.html"
layout: body
title: Trade Events API
published: true
---

#<a href="trade-events.html">Trade Events API</a>
The Trade Events API provides data on events for U.S. businesses interested in selling their products and services overseas.  These events include industry conferences, webinars, lectures and trade missions organized by the U.S. Dept. of Commerce. Developers can use this API to keep businesses aware of the latest events in their industry or location.

The output format for this API is JSON.

##Resource URL

<a href="http://api.trade.gov/trade_events/search"><pre>http://api.trade.gov/trade_events/search</pre></a>
</br>
##Search Parameters

###keyword

Searches for a match within the event_name and description fields.

    http://api.trade.gov/trade_events/search?q={keyword}

#####Example:

<a href="http://api.trade.gov/trade_events/search?q=computer"><pre>http://api.trade.gov/trade_events/search?q=computer</pre></a>
</br>
###industry

Searches for specific controlled [industry names](industry-list-trade-events.html)

    http://api.trade.gov/trade_events/search?industry={industry name}

#####Example:

<a href="http://api.trade.gov/trade_events/search?industry=Chemical"><pre>http://api.trade.gov/trade_events/search?industry=Chemical</pre></a>
</br>
###countries

Returns office locations based on ISO [alpha-2 country codes](http://www.iso.org/iso/home/standards/country_codes/country_names_and_code_elements.htm).

    http://api.trade.gov/trade_events/search?countries={country code}

#####Example:

<a href="http://api.trade.gov/trade_events/search?countries=MX"><pre>http://api.trade.gov/trade_events/search?countries=MX</pre></a>
</br>
###size + offset

The size parameter allows you to configure the maximum amount of hits to be returned. The offset parameter defines the offset from the first result you want to fetch.

#####Example:

<a href="http://api.trade.gov/trade_events/search?country=BR&size=1&offset=1"><pre>http://api.trade.gov/trade_events/search?country=BR&size=1&offset=1</pre></a>
</br>
##Return Values

| Field              | Description                             |
| ------------------ | --------------------------------------- |
| <pre><code>id</code></pre>                 | Unique identifier for post              |
| <pre><code>event_name</code></pre>         | name given for the event                |
| <pre><code>event_type</code></pre>         | [The type of the event (controlled value)](event-type-list.html)  |
| <pre><code>start_date</code></pre>         | start date of the event (default sort)  |
| <pre><code>end_date</code></pre>           | end date of the event                   |
| <pre><code>cost</code></pre>               | cost of the event                       |
| <pre><code>registration_link</code></pre>  | URL for registration page               |
| <pre><code>registration_title</code></pre> | title of the registration URL           |
| <pre><code>description</code></pre>        | text describing the event               |
| <pre><code>industry</code></pre>           | industry category assigned to the event |
| <pre><code>url</code></pre>                | URL for the event                       |
| <pre><code>venue</code></pre>              | place where event is held               |
| <pre><code>city</code></pre>               | city where event is held                |
| <pre><code>state</code></pre>              | state where event is held               |
| <pre><code>country</code></pre>            | country where event is held             |
| <pre><code>first_name</code></pre>         | first name of the contact               |
| <pre><code>last_name</code></pre>          | last name of the contact                |
| <pre><code>post</code></pre>               | contact's organization                  |
| <pre><code>person_title</code></pre>       | contact's job title                     |
| <pre><code>phone</code></pre>              | contact's phone number                  |
| <pre><code>email</code></pre>              | contact's email address                 |