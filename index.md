---
layout: default
title: myBlog
---

# Latest Posts

<ul class="post-list">
  {%- for post in site.posts -%}
    <li>
      <span class="post-date">{{ post.date | date: "%b %d, %Y" }}</span>
      <a class="post-link" href="{{ post.url | relative_url }}">{{ post.title }}</a>
    </li>
  {%- endfor -%}
</ul>
