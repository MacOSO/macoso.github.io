---
layout: blog
title: "Публикации в блоге"
permalink: /blog/
---
<script src="https://cdn.commento.io/js/count.js"></script>
<ul class="posts">
    {% for post in site.categories.blog %}
        <li>
            <span class="post-date">{{ post.date | date: "%b %d, %Y" }}</span>
            ::
            <a class="post-link" href="http://macoso.blur.tech{{ post.url }}">{{ post.title }}</a>
            @ {
            {% assign tag = post.tags | sort %}
            {% for category in tag %}<span><a href="http://macoso.blur.tech/category/#{{ category }}" class="reserved">{{ category }}</a>{% if forloop.last != true %},{% endif %}</span>{% endfor %}
            {% assign tag = nil %}
            }(<a href="http://macoso.blur.tech{{ post.url }}#commento"></a>);
        </li>
    {% endfor %}
</ul>
