---
layout: default
---
<div class="posts">
	<div class="container">
		<div class="row justify-content-md-center">
			<div class="col-7 col-sm-3 col-md-3">
				<h2>Posts</h2>
			</div>
		</div>
		{% if site.posts.size == 0 %}
		<div class="row justify-content-md-center">
			<div class="col-7">
				<h3>Not Posts Found!</h3>
			</div>
		</div>
		{% else %}
			{% for post in site.posts %}
			<div class="row border-bottom-0 justify-content-md-center">
				<div class="col-7 col-sm-3 col-md-3">
					<h3>
						<a href="{{ post.url | prepend: site.baseurl }}" title="">{{post.title}}</a>
					</h3>
					<h4>
						<time>
							{{ post.date | date_to_string }}
						</time>
						{%- if page.author -%}
           				• <span>{{ post.author }}</span>
          				{%- endif -%}
					</h4>
				</div>
			</div>
			{% endfor %}
		{% endif %}
	</div>
</div>