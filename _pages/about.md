---
layout: page
title: About this site
permalink: /about
comments: true
---

<div class="row justify-content-between">
<div class="col-md-8 pr-5">

<p>This site serves as a collection of various interesting topics that I have came across during recent time and that I would like to share with others and also preserve for my later reference.</p>

<p>Similar as the Life itself, the focus of individual articles is quite diverse. Although electronics and computers are definitely my biggest passion, you can and you will encounter anything that caught my attention here in the future. And that's a lot.</p>

</div>

<div class="col-md-4">

<div class="sticky-top sticky-top-80">
<!-- Author Box -->
<h5>Contributors</h5>
<div class="row post-top-meta">
    <div class="col-xs-12 col-md-3 col-lg-2 text-center text-md-left mb-4 mb-md-0">
        {% if author.avatar %}
        <img class="author-thumb" src="{{site.baseurl}}/{{ author.avatar }}" alt="{{ author.display_name }}">
        {% else %}
        <img class="author-thumb" src="https://www.gravatar.com/avatar/{{ author.gravatar }}?s=250&d=mm&r=x" alt="{{ author.display_name }}">
        {% endif %}
    </div>
    <div class="col-xs-12 col-md-9 col-lg-10 text-center text-md-left">
        <a target="_blank" class="link-dark" href="{{ author.web }}">{{ author.display_name }}</a><a target="_blank" href="{{ author.twitter }}" class="btn follow">Follow</a>
        <span class="author-description">{{ author.description }}</span>
    </div>
</div>

</div>
</div>
</div>
