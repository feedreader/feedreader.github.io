---
title: Planet Planet <=> Pluto - Template Cheatsheet
---

## What's Planet Planet?

Planet Planet is the very first planet feed reader coded in Python
by Scott James Remnant and Jeff Waugh [(Site)](http://www.planetplanet.org) - uses
Mark Pilgrim's universal feed parser (RDF, RSS and Atom)
and Tomas Styblo's templating engine; last release version 2.0 in 2006.

To help with converting your "classic" templates
to the new pluto machinery
using embedded ruby templates here's a cheatsheet.


## Planet Planet <=> Pluto - Template Cheatsheet

    <TMPL_VAR name>                |  <%= site.title %>  or  <%= site.name %>
    <TMPL_VAR generator>           |  <%= Pluto.generator %>

    <TMPL_LOOP Channels>           |  <% site.feeds.each do |feed| %>
       <TMPL_VAR link>             |    <%= feed.url %>  or  <%= feed.link %>
       <TMPL_VAR name>             |    <%= feed.title %>  or  <%= feed.name %>
       <TMPL_VAR title>            |    <%= feed.title2 %>
       <TMPL_VAR url>              |    <%= feed.feed_url %>  or  <%= feed.feed %>
    </TMPL_LOOP>                   |  <% end %>

    <TMPL_LOOP Items>              |  <% items = site.items.latest.limit(24)
                                   |     ItemCursor.new( items ).each do |item,new_date,new_feed| %>
                                   |
      <TMPL_IF new_date>           |    <% if new_date %>
        <TMPL_VAR new_date>        |      <%= item.published %>
      </TMPL_IF>                   |    <% end %>
                                   |
      <TMPL_IF new_channel>        |    <% if new_feed %>
        <TMPL_VAR channel_link>    |      <%= item.feed.url %>  or  <%= item.feed.link %>
        <TMPL_VAR channel_name>    |      <%= item.feed.title %>  or  <%= item.feed.name %>
        <TMPL_VAR channel_title>   |      <%= item.feed.title2 %>
      </TMPL_IF>                   |    <% end %>
                                   |
      <TMPL_IF title>              |    <% if item.title %>
        <TMPL_VAR title>           |      <%= item.title %>
      </TMPL_IF>                   |    <% end %>
                                   |
      <TMPL_VAR content>           |    <% item.content %>
      <TMPL_VAR link>              |    <% item.url %>  or  <% item.link %>
      <TMPL_VAR date>              |    <% item.published %>
                                   |
      <TMPL_IF author>             |
        <TMPL_VAR author>          |    to be done
      </TMPL_IF>                   |
    </TMPL_LOOP>                   |  <% end %>

    <TMPL_VAR date>                |  <%= site.fetched %>     # site (planet) last updated
