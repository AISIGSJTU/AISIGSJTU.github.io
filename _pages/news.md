---
layout: page
title: 新闻
permalink: /news/
description:
nav: true
importance: 1
---

<div class="news">
<div class="table-responsive">
    <table class="table table-sm table-borderless">
    {%- assign news = site.news | reverse -%} 
    {% for item in news %} 
    <tr>
        <th scope="row" style="white-space:nowrap">{{ item.date | date: "%Y年%m月" }}</th>
        <td style="white-space:nowrap" ><b>{{ item.type }}</b></td>
        <td>
        {% if item.inline -%} 
            {{ item.content | remove: '<p>' | remove: '</p>' | emojify }}
        {%- else -%} 
            <a class="news-title" href="{{ item.url | relative_url }}">{{ item.title }}</a>
        {%- endif %} 
        </td>
    </tr>
    {%- endfor %} 
    </table>
</div>
</div>
