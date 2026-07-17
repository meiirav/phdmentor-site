---
layout: splash
permalink: /
hidden: true
header:
  overlay_color: "#8A2D3B"
  overlay_filter: "0.20"
  overlay_image: /assets/images/hero_image.jpg
  actions:
    - label: "Book a Free Session"
      url: "/book/"
    - label: "Read the Blog"
      url: "/blog/"
  caption: ""
excerpt: "You don't have to figure out your PhD alone. I help CS PhD students build research skills, navigate advisor relationships, and find their footing - one conversation at a time."
title: "Guidance for navigating the PhD journey"
feature_row:
  - image_path: /assets/images/icon-compass-placeholder.svg
    alt: "Find your direction"
    title: "Find Your Direction"
    excerpt: "Struggling to choose a topic, an advisor, or a next step? Let's think it through together, with someone who knows the CS PhD landscape."
    url: "/approach/"
    btn_label: "Learn More"
    btn_class: "btn--primary"
  - image_path: /assets/images/icon-conversation-placeholder.svg
    alt: "Navigate advisor relationships"
    title: "Navigate Advisor Relationships"
    excerpt: "Get an outside perspective on a tricky supervision dynamic, and practical ideas for what to do about it."
    url: "/approach/"
    btn_label: "Learn More"
    btn_class: "btn--primary"
  - image_path: /assets/images/icon-growth-placeholder.svg
    alt: "Build research skills"
    title: "Build Research Skills"
    excerpt: "Grow the skills your advisor may never have had time to teach you — from reading papers efficiently to managing a long-term project."
    url: "/approach/"
    btn_label: "Learn More"
    btn_class: "btn--primary"
---

<div class="page__content" style="max-width: 700px; margin: 0 auto; text-align: center;">
  <p style="font-size: 1.25em; line-height: 1.6;">Most PhD advisors are hired for their research, not their supervision. If you feel underguided, underinformed, or just plain lost — you are not the problem, and you are not alone.</p>
</div>

{% include feature_row %}

{% comment %}
  "From the Blog" section — controlled by `show_blog_on_home` in _config.yml.
  Set it to `false` any time to hide this section without touching this
  file (e.g. once the blog becomes a smaller part of the business).

  When shown:
  - If any post has `featured: true` in its front matter, show up to 3
    of those (curated picks — good once you have enough posts that
    "most recent" isn't always "most useful to a new visitor").
  - Otherwise, fall back to the 3 most recent posts automatically.
{% endcomment %}
{% assign featured_posts = site.posts | where: "featured", true %}
{% if featured_posts.size > 0 %}
  {% assign home_posts = featured_posts | limit: 3 %}
{% else %}
  {% assign home_posts = site.posts | limit: 3 %}
{% endif %}

{% if site.show_blog_on_home != false and home_posts.size > 0 %}
<div class="page__content" style="max-width: 1024px; margin: 3em auto 0; overflow: auto;">
  <h2 style="text-align:center;">From the Blog</h2>
  <div class="grid__wrapper">
    {% for post in home_posts %}
      {% include archive-single.html type="grid" %}
    {% endfor %}
  </div>
  <div style="clear:both;"></div>
  <div style="text-align:center; margin-top: 1em;">
    <a href="/blog/" class="btn btn--outline">Read All Posts</a>
  </div>
</div>
{% endif %}

<div style="clear:both;"></div>

<div class="page__content" style="text-align:center; margin-top: 2em;">
  <h2>Right now, I'm offering free discovery sessions</h2>
  <p style="max-width: 640px; margin: 0 auto 1.5em;">
    I'm building this practice around real conversations with real PhD students.
    For a limited time, I'm offering free 30-minute sessions to understand what
    would genuinely help you — no strings attached.
  </p>
  <a href="/book/" class="btn btn--primary btn--large">Book Your Free Session</a>
</div>
