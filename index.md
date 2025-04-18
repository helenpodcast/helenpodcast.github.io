---
layout: default
title: "Learn Interesting English Phrases"
description: "A podcast for English learners featuring interesting phrases, unusual words, and language nuances."
---

<section class="homepage-hero">
    <h1>Unlock the Secrets of English</h1>
    <p>Discover interesting phrases, unusual words, and language nuances through our engaging podcast episodes designed specifically for English learners.</p>
</section>

<section class="latest-episodes">
    <h2>Latest Episodes</h2>
    
    {% for episode in site.episodes limit:3 %}
    <div class="episode-card">
        <h3><a href="{{ episode.url }}">{{ episode.title }}</a></h3>
        <div class="episode-meta">
            <time datetime="{{ episode.date | date_to_xmlschema }}">{{ episode.date | date: "%B %d, %Y" }}</time>
        </div>
        <p>{{ episode.excerpt | strip_html | truncatewords: 10 }}</p>
        <a href="{{ episode.url }}" class="listen-btn">
            <i class="fas fa-headphones"></i> Listen Now
        </a>
    </div>
    {% endfor %}
    
    <div class="view-all">
        <a href="/episodes" class="view-all-btn">View All Episodes</a>
    </div>
</section>

<section class="featured-phrases">
    <h2>Featured Phrases</h2>
    
    {% assign featured_phrases = site.phrases | where: "featured", true | limit: 5 %}
    {% for phrase in featured_phrases %}
    <div class="phrase-card">
        <h3>{{ phrase.title }}</h3>
        <p>{{ phrase.meaning }}</p>
        {% if phrase.example %}
        <p><em>Example: {{ phrase.example }}</em></p>
        {% endif %}
    </div>
    {% endfor %}
    
    <div class="view-all">
        <a href="/phrases" class="view-all-btn">Explore More Phrases</a>
    </div>
</section>
