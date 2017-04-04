---
title: Create Your Own Templates - Template Reference
---


## Embedded Ruby (ERB) Templates

Pluto use "standard / plain vanilla" embedded ruby (ERB) templates.
To create your own templates
use the built-in variables `site`, `feed`, `item`, etc.


## Site

Example: Planet Title

```
<%= site.title %>
```


Example: List all subscriptions

```
<% site.feeds.each do |feed| %>
  <%= feed.url %>  or  <%= feed.link %>
  <%= feed.title %>  or  <%= feed.name %>
  <%= feed.title2 %>
  <%= feed.feed_url %>  or  <%= feed.feed %>
<% end %>
```


## Feed

Example: Lastest feed items

```
<% items = site.items.latest.limit(24)
     ItemCursor.new( items ).each do |item,new_date,new_feed| %>

  <% if new_date %>
    <%= item.published %>
  <% end %>

  <% if new_feed %>
    <%= item.feed.url %>  or  <%= item.feed.link %>
    <%= item.feed.title %>  or  <%= item.feed.name %>
    <%= item.feed.title2 %>
  <% end %>

  <% if item.title %>
    <%= item.title %>
  <% end %>

  <% item.content %>
  <% item.url %>  or  <% item.link %>
  <% item.published %>

<% end %>
```
