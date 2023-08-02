---
title: Meet the team!
nav-menu: true
layout: page
---

<style>

* {
  -webkit-box-sizing: border-box;
     -moz-box-sizing: border-box;
          box-sizing: border-box;
}

html,
body {
  margin: 0;
  padding: 0;
}

html {
  font-family: "Open Sans", "Source Sans Pro", "Helvetica Neue", Helvetica, Arial, sans-serif;
  font-size: 18px;
  font-weight: 300;
  line-height: 1.6;

  @media (min-width: 38em) {
    font-size: 20px;
  }
}


.MathJax_Display{
  font-size: 80%;
}

h1, h2, h3, h4, h5, h6 {
  margin-top: 0;
  margin-bottom: .5rem;
  font-weight: 600;
  font-family: "Open Sans", "Source Sans Pro";
  line-height: 1.1;
  color: #FFF;
  letter-spacing: -.025rem;
}

h1 {
  font-size: 2rem;
}

h2 {
  font-size: 1.6rem;
}

h3 {
  font-size: 1.3rem;
}

h4, h5, h6 {
  font-size: 1rem;
}

p {
  font-family: "Open Sans", "Helvetica Neue", Helvetica;
  font-weight: 300;
  margin: 0 0 1rem;
  font-size: 0.8rem;
}

a {
  color: #FFF
}

ul, ol, dl {
  font-family: "Open Sans", "Helvetica Neue", Helvetica;
  font-weight: 300;
  font-size: 0.8rem;
  margin-top: 0;
  margin-bottom: 1rem;
}

li > ul > li {
    margin-left: 1rem;
}

dt {
  font-weight: bold;
}

dd {
  margin-bottom: .5rem;
}

ul {
  /*font-family: Helvetica, 'Ubuntu Mono';*/
  font-size: 0.8rem;
  list-style: inside circle;
  padding-left: 0;

  li {
    margin-bottom: .25rem;
  }

  ul,
  ol {
    margin-top: .25rem;
    margin-bottom: .5rem;
  }
}

ul.share-buttons{
  list-style: none;
  padding: 0;
}

ol {
  list-style: inside decimal;
  padding-left: 0;

  li {
    margin-bottom: .25rem;
  }

  ul,
  ol {
    margin-top: .25rem;
    margin-bottom: .5rem;
  }
}

p + h1,
p + h2,
p + h3,
ul + h1,
ul + h2,
ul + h3,
ol + h1,
ol + h2,
ol + h3 {
  margin-top: 1.5rem;
}

hr {
  border: 0;
  border-top: .5px solid #eee;
  border-bottom: .5px solid #eee;
  margin: 1.5rem auto;
}

strong {
  color: #FFF;
  font-weight: 600;
}

abbr {
  font-size: 80%;
  font-weight: bold;
  color: #FFF;
  text-transform: uppercase;
}

abbr[title] {
  cursor: help;
  border-bottom: 1px dotted #e5e5e5;
}

blockquote {
  padding: 0 0 0 1.5rem;
  margin: 0 2rem 1rem 0;
  border-left: .5rem; //solid #e5e5e5

  p:last-child {
    margin-bottom: 0;
  }
}

img {
  display: block;
  max-width: 100%;
  margin: 0 0 1rem;
  border-radius: 5px;
}

table {
  margin-bottom: 1rem;
  width: 100%;
  font-size: 70%;
  border: 1px solid #e5e5e5;
  border-collapse: collapse;
}

.list {
  &-post-title {
    margin-bottom: .25rem;

    a {
      color: #333;

      &:hover,
      &:focus {
        text-decoration: none;
      }
    }
  }
  &-post-date {
    margin-bottom: 1rem;
    font-size: .75rem;
    text-transform: uppercase;
  }
}

.profile-thumbnail {
  object-fit: cover;
  object-position: center top;
  width: 200px;
  height: 200px;
}

// customization
.pos_header {
  margin-left: 2rem;
}

.people {
  margin: auto;
  text-align: center;
  margin-top: 0.75em;
}

.list-item-people {
  display: inline-block;
  padding-right: 1em;
}

.list-post-title img {
  margin-bottom: 0.75em;
  margin-top: 1.25em;
}

.list-post-title .name {
  font-size: 18px;
}

.list-post-title {
  color: black;
}

.list-detail {
  font-size: 15px;
  color: #FFF;
}

.list-item a:hover, .list-post-title:hover .name, .list-post-title .name:hover {
  color: #c42929;
}

.page-title {
  margin-bottom: 0.6em;
}

.navbar-brand {
  //font-weight: bold;
  font-size: 20px;
  font-weight: 300;
}

// change font for navbar
.navbar, .navbar-nav>li>a {
  background-color: white;
  font-family: 'Open Sans', sans-serif;
  text-transform: uppercase;
  font-weight: 400;
  font-size: 80%;
}

// fix menu bar spacing for mobile
@media(max-width: 40em){
  .navbar-nav>li>a {
    padding: 0.75em 0 0.5em 2.5em;
    font-size: 15px;
  }

  // fix menu scroll along x axis
  .navbar-nav {
    margin-right: 15px;
  }
}

// fix spacing
.navbar-nav>li {
  margin-bottom: 0;
}

// fix menu button for mobile
.navbar-toggle, .navbar-default .navbar-toggle:hover {
  border: none;
  background-color: #FFF;
}


</style>

{% assign people_sorted = site.people %}
{% assign role_array = "pi|postdoc|gradstudent|researchstaff|visiting|alumni" | split: "|" %}

{% for role in role_array %}

{% assign people_in_role = people_sorted | where: 'position', role %}

<!-- Skip section if there's nobody -->
{% if people_in_role.size == 0 %}
  {% continue %}
{% endif %}

<div class="pos_header">
{% if role == 'postdoc' %}
<h3>Postdoctoral Fellows</h3>
 {% elsif role == 'pi' %}
<h3>Principal Investigator</h3>
 {% elsif role == 'gradstudent' %}
<h3>Graduate Students</h3>
 {% elsif role == 'researchstaff' %}
<h3>Research Staff</h3>
 {% elsif role == 'visiting' %}
<h3>Visiting Scholars</h3>
 {% elsif role == 'alumni' %}
<h3>Alumni</h3>
{% endif %}
</div>

{% if role != 'alumni' %}
<div class="content list people">
  {% for profile in people_sorted %}
    {% if profile.position contains role %}
      <div class="list-item-people">
        <p class="list-post-title">
          {% if profile.avatar %}
            <a href="{{ profile.url }}"><img class="profile-thumbnail" src="{{site.baseurl}}/assets/images/people/{{profile.avatar}}"></a>
          {% else %}
            <a href="{{ profile.url }}"><img class="profile-thumbnail" src="http://evansheline.com/wp-content/uploads/2011/02/facebook-Storm-Trooper.jpg"></a>
          {% endif %}
          <a class="name" href="{{ profile.url }}">{{ profile.name }}</a>
        </p>
      </div>
    {% endif %}
  {% endfor %}
</div>
<hr>

{% else %}

<br>

| Who are they | When were they here | Where they went |
| :------------- |:-------------| :-----------|
| [alumni1]() | Graduate student (2016-2022) | Postdoc with xxxx |
| [alumni2]() | Graduate Student (2014 - 2021) | newplace |


{% endif %}
{% endfor %}

