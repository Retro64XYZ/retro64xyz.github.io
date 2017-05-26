---
layout: default
title: Search
---

<div id="search-form">
  <form action="{{ site.url }}/search" method="get">
    <input type="text" id="search-query" name="q" placeholder="Fill To Search" autocomplete="off">
  </form>
</div>

<section id="search-results" style="display: none;"></section>

{% raw %}
<script id="search-results-template" type="text/mustache">
  {{#entries}}
    <div class="search-article">
      <article>
        <h3>
          {{#date}}<small><time datetime="{{pubdate}}" pubdate>{{displaydate}}</time></small>{{/date}}
          <a href="{{url}}">{{title}}</a>
        </h3>
        {{#is_post}}
          <ul>
            {{#tags}}<li>{{.}} </li>{{/tags}}
          </ul>
        {{/is_post}}
      </article>
	</div>
  {{/entries}}
</script>
{% endraw %}

<script type="text/javascript">
$(function() {
  $('#search-query').lunrSearch({
    indexUrl  : '/js/index.json',           // url for the .json file containing search index data
    results   : '#search-results',          // selector for containing search results element
    template  : '#search-results-template', // selector for Mustache.js template
    titleMsg  : '<h1>Search Results<h1>',   // message attached in front of results (can be empty)
    emptyMsg  : '<p>Nothing found.</p>'     // shown message if search returns no results
  });
});
</script>

<script src="/js/search.min.js" type="text/javascript" charset="utf-8"></script>
