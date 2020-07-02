---
layout: default
---
{%- for review in site.reviews | sort: 'title' -%}
 
<article class='review-artical' id='{{review.title}}'>
  <div class='review-content'>
    <div class='review-body'>
      <div class="review-header">
        <div class="review-title">
          <h1>
            <a href="{{site.baseurl}}{{review.url}}">{{review.title}}</a>
          </h1>
        </div>
      </div>		
      <div class='review-excerpt'>
        <p class="excerpt">{{review.excerpt | strip_html}}</p>
      </div>
      <div class="review-action">
        <a class="read-more" href="{{review.url}}">Read More</a>
      </div>
    </div>
  </div>
</article>

{%- endfor -%}
