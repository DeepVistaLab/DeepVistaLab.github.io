---
title: People
permalink: /people/
---

{% assign people_sorted = (site.people | sort: 'joined' %}
{% assign people_array = "pi|postdoc|gradstudent|visiting|others|alumni" | split: "|" %}

{% for item in people_array %}

<div class="pos_header">
{% if item == 'postdoc' %}
<h3>Faculty Mentor</h3>
 {% elsif item == 'pi' %}
<h3>Lab Leader</h3>
 {% elsif item == 'gradstudent' %}
<h3>Student Researcher</h3>
 {% elsif item == 'visiting' %}
<h3>Visiting Student</h3>
 {% elsif item == 'others' %}
<h3>Honorary Members</h3>
 {% elsif item == 'alumni' %}
<h3>Alumni</h3>
{% endif %}
</div>

<div class="content list people">
  {% for profile in people_sorted %}
    {% if profile.position contains item %}
    <div class="list-item-people">
      <p class="list-post-title">
        {% if profile.avatar %}
        <a href="{{ site.baseurl }}{{ profile.url }}"><img width="200" src="{{site.baseurl}}/images/people/{{profile.avatar}}"></a>
        {% else %}
        <a href="{{ site.baseurl }}{{ profile.url }}"><img width="200" src="http://evansheline.com/wp-content/uploads/2011/02/facebook-Storm-Trooper.jpg"></a>
        {% endif %}
        <a class="name" href="{{ site.baseurl }}{{ profile.url }}">{{ profile.name }}</a>
      </p>
    </div>    
    {% endif %}
  {% endfor %}
</div>
<hr>
{% endfor %}

| Who are they | When were they here | Where they went |
| :------------- |:-------------| :-----------|
| Bahram Yoosefizonooz | Visiting (2017) | Postdoc at U Montreal
