---
layout: page
title: Research
permalink: /research/
---

See my publications page for a complete list of papers. 




{% for project in site.research %}

{% if project.redirect %}
<div class="project">
    <div class="thumbnail">
        <a href="{{ project.redirect }}" target="_blank">
        {% if project.img %}
        <img class="thumbnail" src="{{ project.img | prepend: site.baseurl | prepend: site.url }}"/>
        {% else %}
        <div class="thumbnail blankbox"></div>
        {% endif %}    
        <span>
            <h1>{{ project.title }}</h1>
            <br/>
            <p>{{ project.description }}</p>
        </span>
        </a>
    </div>
</div>
{% else %}

<div class="project ">
    <div class="thumbnail">
        <a href="{{ project.url | prepend: site.baseurl | prepend: site.url }}">
        {% if project.img %}
        <img class="thumbnail" src="{{ project.img | prepend: site.baseurl | prepend: site.url }}"/>
        {% else %}
        <div class="thumbnail blankbox"></div>
        {% endif %}    
        <span>
            <h1>{{ project.title }}</h1>
            <br/>
            <p>{{ project.description }}</p>
        </span>
        </a>
    </div>
</div>

{% endif %}

{% endfor %}




{% comment %}

<h2 id="io">Machine learning for prescriptive analytics</h2>

Designing prescriptive models that capture decision-maker preferences typically requires guidance from domain experts. Instead using data on past decisions, we can learn to construct personalized optimization models. I have worked on several techniques for applying machine learning to estimate the objectives and constraints of decision-making models. Relevant publications: 


{% bibliography --file opt %}


<h2 id="rt">Machine learning for personalized medicine</h2>


Radiation therapy is a cancer treatment procedure prescribed to over 50% of all cancer patients. For complex cancer sites, designing radiation therapy treatments involve a mixture of machine learning (to predict appropriate doses) and optimization (to control the delivery). I designed a series of integrated deep learning and optimization technologies to improve the design of radiation therapy treatment plans. Relevant publications: 

{% bibliography --file rt %}




<h2 id="ecc">Error correction codes for real-time streaming</h2>

In real-time Internet streaming, data packets are encoded with error correction in order to protect against transmission failures and missing bits. This problem is classically modeled as a stochastic system connecting a single transmitter and receiver. However, the Internet in reality is a network where information flows through multiple nodes before reaching an intended receiver. I developed a series of algebraic error correction codes for real-time streaming communication over networks of nodes along with information-theoretic proofs guaranteeing the optimality of these codes. Relevant publications: 

{% bibliography --file codes  %}


{% endcomment %}
