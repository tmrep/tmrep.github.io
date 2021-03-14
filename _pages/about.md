---
layout: page
title: About this site
permalink: /about
comments: false
---

<div class="row justify-content-between">
<div class="col-md-8 pr-5">

<p>This site serves as a collection of various interesting topics that I have came across during recent time and that I would like to share with others and also preserve for my later reference.</p>

<p>Similar as the Life itself, the focus of individual articles is quite diverse. Although electronics and computers are definitely my biggest passion, you can and you will encounter anything that caught my attention here in the future. And that's a lot.</p>

<!-- Author Box -->
<h5>Contributors</h5>
{% for contributor in site.authors %}
<div class="row post-top-meta">
    <div class="col-xs-12 col-md-3 col-lg-2 text-center text-md-left mb-4 mb-md-0">
        {% capture avatar_defined %}
            {{ contributor | map: "avatar" }}
        {% endcapture %}
        {% if avatar_defined %}
        <img class="author-thumb" src="{{site.baseurl}}/{{ contributor | map: 'avatar' }}" alt="{{ contributor | map: 'display_name' }}">
        {% else %}
        <img class="author-thumb" src="https://www.gravatar.com/avatar/{{ contributor | map: 'gravatar' }}?s=250&d=mm&r=x" alt="{{ contributor | map: 'display_name' }}">
        {% endif %}
    </div>
    <div class="col-xs-12 col-md-9 col-lg-10 text-center text-md-left">
        <a target="_blank" class="link-dark" href="{{ contributor | map: 'web' }}">{{ contributor | map: "display_name" }}</a>
        <br>
        <span class="author-description">{{ contributor | map: "description" }}</span>
    </div>
</div>
{% endfor %}
</div>

<div class="col-md-4">

<div class="sticky-top sticky-top-80">
<h4>Frequency of new posts</h4>
<p>I do not plan to keep any steady pace in adding new contributions. It may happen quite easily that they will be very sporadic. It will always reflect my actual allocation of free time.</p>

<h4>Contact</h4>
<p>In case of need, you can contact me at <b>mi.tom[at]seznam.cz</b>.</p>

</div>
</div>
</div>
