---
layout: default
title: All Episodes
permalink: /episodes/
---

<h1>All Podcast Episodes</h1>

<p>Browse through all our episodes to learn interesting English phrases, unusual words, and language nuances.</p>

<div class="episodes-list">
    {% for episode in site.episodes %}
    <div class="episode-item">
        <h2><a href="{{ episode.url }}">{{ episode.title }}</a></h2>
        <div class="episode-meta">
            <time datetime="{{ episode.date | date_to_xmlschema }}">{{ episode.date | date: "%B %d, %Y" }}</time>
            <span class="episode-duration">{{ episode.duration }}</span>
        </div>
        <p>{{ episode.excerpt | strip_html }}</p>
        <a href="{{ episode.url }}" class="read-more">Listen to Episode</a>
    </div>
    {% endfor %}
</div>
