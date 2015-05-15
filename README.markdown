Let's you set your Google Analytics code in your Django settings and
makes it available to templates.

### Install

    $ pip install django-ga-context

and add `'gacontext.ga_processor'` to your
`TEMPLATE_CONTEXT_PROCESSORS`. Then set

    GA_CODE = "your google analytics code"

And it will be available to your templates, so you can do something
like:

    {% if GA_CODE %}
    <script type="text/javascript">
      (function(i,s,o,g,r,a,m){i['GoogleAnalyticsObject']=r;i[r]=i[r]||function(){
        (i[r].q=i[r].q||[]).push(arguments)},i[r].l=1*new
        Date();a=s.createElement(o),
        m=s.getElementsByTagName(o)[0];a.async=1;a.src=g;m.parentNode.insertBefore(a,m)
      })(window,document,'script','//www.google-analytics.com/analytics.js','ga');
    
      ga('create', '{{GA_CODE}}', 'yourdomain.com');
      ga('send', 'pageview');
    </script>
    {% endif %}

