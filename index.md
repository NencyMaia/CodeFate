---
layout: default
title: Creating... and Keep learnning
---

<div id="home">
  <h1>Blog Posts</h1>
  <ul class="posts">
    {% for post in site.posts %}
      <li><span>{{ post.date | date_to_string }}</span> &raquo; <a href="{{ post.url }}">{{ post.title }}</a></li>
    {% endfor %}
  </ul>
</div>
<ul class="nav">
  {% for item in site.menuitems %}
    {% if item.url == page.url %}
    <li class="active">
    {% else %}
    <li>
    {% endif %}
    <a href="{{item.url}}">{{item.name}}</a>
    </li>
  {% endfor %}
</ul>
<div class="tag-cloud">
       {% for tag in site.tags %}
          <a href="/pages/tags.html#{{ tag[0] }}-ref" id="{{ forloop.index }}" class="__tag" style="margin: 5px">{{ tag[0] }}</a>
       {% endfor %}
</div>
    
<script type="text/javascript">
       $(function() {
          var minFont = 15.0,
              maxFont = 40.0,
              diffFont = maxFont - minFont,
              size = 0;
           
          {% assign max = 1.0 %}
          {% for tag in site.tags %}
             {% if tag[1].size > max %}
                {% assign max = tag[1].size %}
             {% endif %}
          {% endfor %}
                
          {% for tag in site.tags %}
             size = (Math.log() / Math.log()) * diffFont + minFont;
             $("#").css("font-size", size + "px");
          {% endfor %}
       });
</script>
