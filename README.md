{% for post in site.posts %}
    <article class="post">

      <h1><a href="">{{ post.title }}</a></h1>

      <div class="entry">
        {{ post.excerpt }}
      </div>

      <a href="{{ site.baseurl }}{{ post.url }}" class="read-more">Read More</a>
    </article>
    
# [{{ post.title }}]({{ site.baseurl }}{{ post.url }})
{{ post.excerpt }}
[Read More]({{ site.baseurl }}{{ post.url }})
{% endfor %}
