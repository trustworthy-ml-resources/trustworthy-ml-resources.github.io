---
layout: page
permalink: /job_form/
title: job form
description: open positions in trustworthy ml
nav: false
---

<div class="container">
  <div class="row">
	<div class="col-md-10 col-md-offset-1">
	<h1>submit a job</h1>
	<!--<p class="lead"><a href="http://opensourcedesign.net/code-of-conduct/">We have a code of conduct</a>. please read it before submitting your job.</p>-->
	<form method="POST" action="https://osd-staticman.herokuapp.com/v2/entry/opensourcedesign/jobs/master/jobs">
	  <input name="options[redirect]" type="hidden" value="http://opensourcedesign.net/jobs/thank-you/">
	  <input name="fields[status]" type="hidden" value="searching">
	  <input name="fields[date_posted]" type="hidden">
	  <input name="fields[layout]" type="hidden" value="jobs">
	  <input name="options[slug]" type="hidden" id="slug" value="">
	  <!--div class="form-group">
		<label for="role">Role</label>
		<p class="help-block">The type of designer you are looking for. You could use one of these: graphic designer, icon designer, interaction designer, information architect, user researcher, content strategist, accessibility expert.</p>
		<input type="text" class="form-control" id="role" placeholder="E.g. Graphic designer" required>
	  </div-->
	  <fieldset>
		<legend>about the job</legend>
		<div class="form-group">
		  <label for="title">job title</label>
		  <input type="text"
			class="form-control"
			id="title"
			placeholder="eg. Data Scientist in Medical Imaging"
			name="fields[title]"
			required>
		</div>
		<div class="form-group">
			<label for="role">job category</label>
			<select class="form-control" id="jobCat">
				<option>full-time</option>
				<option>part-time</option>
				<option>postdoc</option>
				<option>internship</option>
				<option>other</option>
			</select>
		</div>
		<div class="form-group">
			<label for="onsite-remote">on-site or remote</label>
			<select class="form-control" id="onsite-remote">
				<option>on-site</option>
				<option>remote</option>
				<option>both options available</option>
			</select>
		</div>
		<div class="form-group">
		  <label for="location">location</label>
		  <input type="text"
			class="form-control"
			id="fields[location]"
			placeholder="eg. New York, Berlin"
			name="location">
		</div>
		<div class="form-group">
		  <label for="paid_details">
			compensation
			<small>(optional)</small>
		  </label>
		  	<input type="text"
				class="form-control"
				id="fields[paid_details]"
				placeholder="USD 5000 fixed rate"
				name="paid_details">
		  	<small>Give some information about the payment offered. Try to be specific. A fixed amount or a range are good. Avoid things like "competitive": they are not very informative.</small>
		</div>
		<div class="form-group">
		  <label for="description">job description</label>
		  <textarea class="form-control"
			id="description"
			rows="5"
			name="fields[description]"
			placeholder="…"
			required></textarea>
		  <small>Markdown is okay</small>
		</div>
		<div class="form-group">
		  <label for="requirements">requirements</label>
		  <textarea class="form-control"
			id="requirements"
			rows="3"
			name="fields[requirements]"
			placeholder="eg. python and/or R"></textarea>
		  <small>Markdown is okay</small>
		</div>
		<div class="form-group">
		  <label for="contact">contact person</label>
		  <input class="form-control"
			id="contact"
			rows="2"
			required
			placeholder="Jane (lead dev)"
			name="fields[contact]">
		</div>
		<div class="form-group">
		  <label for="mail">mail address</label>
		  <input class="form-control"
			id="mail"
			rows="1"
			required
			placeholder="<jane@company.org>"
			name="fields[mail]">
		</div>
		<div class="form-group">
		  <label for="tags">
			Tags
			<small>(optional)</small>
		  </label>
		  <textarea class="form-control"
			id="tags"
			rows="2"
			placeholder="eg. deep learning, interpretability, medical imaging"
			name="fields[tags]"></textarea>
			<small>Keywords relevant to the job. Separate tags with commas.</small>
		</div>
	  </fieldset>
	  <button type="submit" href="thankyou.html" class="btn btn-primary btn-lg">Submit your job</button>
<script src="/js/jquery.min.js"></script>
<script src="/js/bootstrap.min.js"></script>
<script>
	function compensation() {
	  if ( $("#gratis").is(":checked") ) {
		$("#paid_details").parent().slideUp();
	  }
	  else {
		$("#paid_details").parent().slideDown();
	  }
	}
	function slug (str) {
	  str = str.replace(/^\s+|\s+$/g, ''); // trim
	  str = str.toLowerCase();
	  // remove accents, swap ñ for n, etc
	  var from = "ãàáäâẽèéëêìíïîõòóöôùúüûñç·/_,:;";
	  var to   = "aaaaaeeeeeiiiiooooouuuunc------";
	  for (var i=0, l=from.length ; i<l ; i++) {
		str = str.replace(new RegExp(from.charAt(i), 'g'), to.charAt(i));
	  }
	  str = str.replace(/[^a-z0-9 -]/g, '') // remove invalid chars
		.replace(/\s+/g, '-') // collapse whitespace and replace by -
		.replace(/-+/g, '-'); // collapse dashes
	  return str;
	}
    $(document).ready(function() {
	  $('input#title').keyup(function (e) {
		$('input#slug').val(slug(e.target.value));
	  });
	  compensation();
	  $("input:radio").click(function(){
		compensation();
	  });
	  var date = new Date();
	  var day = ("0" + date.getDate()).slice(-2);
	  var month = ("0"+(date.getMonth()+1)).slice(-2);
	  var year = date.getFullYear();
	  var datestring = year + "-" + month + "-" + day;
	  $('[name="fields[date_posted]"]').val(datestring);
  });
</script>