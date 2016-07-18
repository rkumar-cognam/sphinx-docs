About Blended
=============


What is Blended?

BlendedUX is an effort to implement Armin Ronacher’s original vision for the Twig templating language:

 A language-independent and simple template engine is useful for applications that use code which is written in more than one programming language.
BlendedUX makes it easy to share template code between Django, Jinja, Twig and Nunjucks template runtimes (which run in Python, Python, PHP and Javascript respectively). Going forward, we also want to add compatibility for template languages that work with Java, Go, Ruby, .NET and Erlang.

How Does Blended Work?
BlendedUX specifies a powerful cross-platform template language using syntax that was first introduced by the Django Web Framework and was later extended and popularized by the Jinja2 and Twig templating languages. Blended Language looks like this:

{% extends “base.html” %}
{% block content %}
  {% if not empty(page.images) %}
  <ul class=”gallery”>
    {% for image in page.images %}
    <li><img src={{ image.url }}></li>
    {% endfor %}
  </ul>
  {% endif %}
{% endblock %}
 

The BlendedUX project doesn’t provide its own implementation of the “Blended Language”, however. We believe that doing so would work against our primary objective, which is to persuade the diverse communities working on Django-derived template languages to implement a common, well-defined subset of language features.

Instead, the Blended project (currently) consists of the following components:

A draft language specification, in the form of a formal context-free grammar, test cases, and descriptive documentation;
A lint program capable of highlighting where individual template files deviate from the specification (and are therefore not cross-platform compatible);
Extension libraries for each of the supported template runtimes (Django, Jinja, Twig and Nunjucks) that bring them in compliance with the specification.
The extension libraries that we have implemented for Django, Jinja, Twig and Nunjucks mean that the Blended Language is a real thing, usable today, right now. If you add these extensions to your projects, you will be able to use any template that is accepted by Blended-Lint. And these libraries are not forks—they are targeted enhancements (most limited to less than 200 total LOC) that track to the most recent version of each template language implementation.

Blended’s extension libraries are currently in “beta” status, so we do not recommend anyone else use them in production yet without extensive testing. Still, we ourselves have been using them in production to varying degrees for some time. By open-sourcing this project we hope that people start using our code, improve the stability of these libraries, and demonstrate through use that the project’s objective is a realistic and worthwhile endeavor.