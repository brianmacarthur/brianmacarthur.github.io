---
layout: post
title:  "Open Source Healthcare Protocols"
date:   2014-12-07 15:06
categories: introduction
tags:
image: /assets/article_images/2014-08-29-welcome-to-jekyll/desktop.jpg
---
Steven Clark, MD of the Baylor College of Medicine and Texas Children's Hospital delivered a presentation at the 2014 World Symposium of Perinatal Medicine entitled, "Standardization of Care and Perinatal Outcomes Improvement," in which he shared his experience building a high reliability organization in healthcare and the evidence backing up that approach. He advocated simple and sometimes obvious quality improvement strategies employing protocols to standardize approaches to commonly encountered clinical problems. The most primitive example he cited was a medication management checklist that he jotted down during a 10 minute fishing break.

Another presenter, Alan Spitzer, MD, Senior VP for Research, Education and Quality at Mednax, Pediatrix Medical Group, and American Anesthesiology, highlighted the importance of measuring outcomes at every level of a healthcare organization and implementing strategies to correct underperforming providers and locales.

To add new posts, simply add a file in the `_posts` directory that follows the convention `YYYY-MM-DD-name-of-post.ext` and includes the necessary front matter. Take a look at the source for this post to get an idea about how it works.

Jekyll also offers powerful support for code snippets:

{% highlight ruby %}
def print_hi(name)
  puts "Hi, #{name}"
end
print_hi('Tom')
#=> prints 'Hi, Tom' to STDOUT.
{% endhighlight %}

Check out the [Jekyll docs][jekyll] for more info on how to get the most out of Jekyll. File all bugs/feature requests at [Jekyll’s GitHub repo][jekyll-gh]. If you have questions, you can ask them on [Jekyll’s dedicated Help repository][jekyll-help].

{% highlight js %}

<footer class="site-footer">
 <a class="subscribe" href="{{ "/feed.xml" | prepend: site.baseurl }}"> <span class="tooltip"> <i class="fa fa-rss"></i> Subscribe!</span></a>
  <div class="inner">a
   <section class="copyright">All content copyright <a href="mailto:{{ site.email}}">{{ site.name }}</a> &copy; 2014 &bull; All rights reserved.</section>
   <section class="poweredby">Made with <a href="http://jekyllrb.com"> Jekyll</a></section>
  </div>
</footer>
{% endhighlight %}


[jekyll]:      http://jekyllrb.com
[jekyll-gh]:   https://github.com/jekyll/jekyll
[jekyll-help]: https://github.com/jekyll/jekyll-help
