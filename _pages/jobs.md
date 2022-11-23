---
layout: page
permalink: /jobs/
title: jobs
description: open positions in trustworthy ml
nav: true
order: 6
---

<style>
  ul {
    list-style-type: none;
    padding-inline-start: 0px;
  }
</style>
To create a new job posting, send a pull request to our github page:  
https://github.com/trustworthy-ml-resources/trustworthy-ml-resources.github.io.  
Copy the template '2022-11-18_job_posting.md' in '/_jobs' and adjust it accordingly. Please also adjust the date in the filename as well as 'job_posting' to a short version of the job title.
<div class="container">
<!--
    <div class="row">
        <div class="col-md-10">
          <p>
            Are you having an open position related to trustworthy ML? Create a posting on the job-board!
          <p>
		    </div>
        <div class="col-md-10">
          <p>
            <a class="btn btn-primary" href="/job_form/">Post A Job</a>
            We'll review your posting as soon as possible.
          </p>
		    </div>
	  </div>
    -->
    <hr>
    <div class="row">
        <div class="col-md-10 col-md-offset-1">
            <ul class="job-list">
				    <!--  {---% for page in /jobs/ reversed %---} -->
                {% for page in site.jobs reversed %}
                {% if page.layout == 'jobs' and page.status == 'searching' %}
                {% unless page.title contains 'Job Title' %}
                {% comment %} Filter out the example page 
                {% endcomment %}
                <li>
                    <h2>
                      <a href="{{ page.url | prepend: site.baseurl }}" title="{{ page.title }}">
                        {{ page.title }}
                      </a>
                    </h2>
                    <p>
                      {% if page.role %}
                      <span class="pill role">{{ page.role }}</span> @
                      {% endif %}
                      <span class="pill organization">{{ page.organization }}</span>
                    </p>
                </li>
                {% endunless %}
                {% endif %}
                {% endfor %}
            </ul>
        </div>
    </div>
    <hr>
</div>