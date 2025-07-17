---
layout: page
title: After Reasonable Hope
permalink: /blog/
---

I blog sporadically on how life, both individual and collective, can and should be meaningfully lived. Perhaps even our best efforts cannot defeat skepticism and pessimism, but it is still reasonable to have a hope, a reasonable hope. It is after this hope that philosophy finds its foothold and meaning, at least for me. 

Posts are arranged into <a href="/categories">categories</a> and include {% assign sorted_cats = site.categories | sort  %}{% for category in sorted_cats %}{% if forloop.last == true %}and {% endif %}<a href="/categories/#{{category[0]}}" style="font-weight:normal;"> {{category[0] | camelcase }}</a> ({{ category[1].size  }}){% if forloop.last == false %}, {% endif %}{% endfor %}. 


<!-- {% assign sorted_cats = site.categories | sort  %}{% for category in sorted_cats %}{% if forloop.last == true %}and {% endif %}<a href="/categories/#{{category[0]}}" style="font-weight:normal;">{{category[0] | camelcase }}</a> ({{ category[1].size  }}){% if forloop.last == false %},{% endif %} {% endfor %} -->



<ul id="archive">
{% for post in site.posts %}
  {% capture y %}{{post.date | date:"%Y"}}{% endcapture %}
  {% if year != y %}
    {% assign year = y %}
    <h2 class="blogyear">{{ y}}</h2>
  {% endif %}
<li class="archiveposturl"><span><a href="{{ post.url }}" title="{{ post.title }}">{{ post.title }}</a></span><br/>
<span class = "postlower">

<!--<strong>Author:</strong> {{post.author}} -->
<strong>Category:</strong>  {% if post.categories %}

  {% for cat in post.categories %}
  <a href="/categories/#{{ cat }}" title="{{ cat }}">{{ cat }}</a>&nbsp;
  {% endfor %}

{% endif %} <!-- {{ post.categories | first }} -->
<strong style="font-size:100%; font-family: 'Titillium Web', sans-serif; float:right; padding-right: .5em">{{ post.date | date: '%d %b %Y' }}</strong> 
</span> 

</li>
{% endfor %}
</ul>

<!-- {{ post.date | date: '%m %d, %Y' }} -->
