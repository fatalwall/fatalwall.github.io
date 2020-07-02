---
layout: default
---

<link rel="stylesheet" type="text/css" href="assets/css/reviews.css">

{%- for collection in site.collections | where: "label", "reviews" -%}
  {%- assign sorted = collection.docs | sort: 'title' -%}
  {%- for post in sorted -%} 
  
<article class='review-artical' id='{{post.title}}'>
  <div class='review-content'>
    <div class='review-body'>
      <div class="review-header">
        <div class="review-title">
          <h1>
            <a href="{{site.baseurl}}{{post.url}}">{{post.title}}</a>
          </h1>
        </div>
      </div>		
      <div class='review-excerpt'>
        <p class="excerpt">{{post.excerpt | strip_html}}</p>
      </div>
      <div class="review-action">
        <a class="read-more" href="{{site.baseurl}}{{post.url}}">Read More</a>
      </div>
    </div>
  </div>
</article>

  {%- endfor -%}
{%- endfor -%}
