---
layout: page
title: Business
titlebar: money
subtitle: <span class="mega-octicon octicon-keyboard"></span>&nbsp;&nbsp;Investment, Banking, Finance and case study.
# >&nbsp;&nbsp;>&nbsp;&nbsp;<a href ="https://t.zsxq.com/iYZ3zrR" target="_blank" ><font color="#EB9439">点我直达</font></a>
menu: money
css: ['blog-page.css']
permalink: /money
---

<div class="row">

    <div class="col-md-12">

        <ul id="posts-list">
            {% for post in site.posts %}
                {% if post.category=='money' or post.keywords contains 'money' %}
                <li class="posts-list-item">
                    <div class="posts-content">
                        <span class="posts-list-meta">{{ post.date | date: "%Y-%m-%d" }}</span>
                        <a class="posts-list-name bubble-float-left" href="{{ site.url }}{{ post.url }}">{{ post.title }}</a>
                        <span class='circle'></span>
                    </div>
                </li>
                {% endif %}
            {% endfor %}
        </ul> 

        <!-- Pagination -->
        {% include pagination.html %}

        <!-- Comments -->
       <div class="comment">
         {% include comments.html %}
       </div>
    </div>

</div>
<script>
    $(document).ready(function(){

        // Enable bootstrap tooltip
        $("body").tooltip({ selector: '[data-toggle=tooltip]' });

    });
</script>

