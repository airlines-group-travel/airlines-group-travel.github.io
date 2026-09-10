---
layout: default
title: "Airlines Group Travel — Group Air Travel Specialists"
description: "Official profile of Airlines Group Travel (Airfare Services USA LLC): group flight bookings for 10+ passengers across 178 airlines, business class, negotiated fares and private jet charter."
---
<!--
  NOTE ON EDITING THIS FILE
  This page is written as plain HTML on purpose, with every tag starting at
  column 0. Do not indent the tags and do not add markdown="1" attributes.
  Kramdown turns any line indented by 4+ spaces into a code block, which makes
  raw tags appear as visible text on the page.
  Edit the words between the tags freely. Any NEW page you add is normal
  Markdown - see GUIDE.md section 9.
-->

<section class="hero">
<div class="wrap">
<p class="eyebrow">Official company profile</p>
<h1>{{ site.title }}</h1>
<p class="lede">{{ site.hero_line }}</p>
<p class="cta-row">
<a class="btn btn-primary" href="{{ site.main_site }}">Get a group quote</a>
<a class="btn btn-ghost" href="{{ site.main_site }}/about-us">About the company</a>
</p>
<ul class="stat-row plain">
<li><strong>178+</strong><span>airlines covered</span></li>
<li><strong>10+</strong><span>passengers per group</span></li>
<li><strong>3</strong><span>languages published</span></li>
<li><strong>{{ site.founding_year }}</strong><span>operating since</span></li>
</ul>
</div>
</section>

<section class="band">
<div class="wrap narrow">
<h2>What we do</h2>
<p>Airlines Group Travel arranges air travel for groups of ten or more passengers travelling together on scheduled airlines. Corporate teams, conferences and incentive trips, wedding parties, sports squads, tour operators, student and faith groups, crew movements and family reunions all book the same way: one itinerary, one invoice, one point of contact.</p>
<p>Group air travel is not the same product as a set of individual tickets. Airlines run separate group desks with their own fare filings, deposit schedules and name-change rules. A group contract will typically let you hold seats before every traveller is confirmed, submit the passenger names closer to departure, and change a name without cancelling and rebooking. Those terms are not available through a normal consumer booking flow, and they differ from carrier to carrier &mdash; which is the work we do on your behalf.</p>
<p>We are a booking agency, not an airline. Fares are quoted rather than published, because a group fare is negotiated against the specific route, date, cabin and party size.</p>
</div>
</section>

<section class="band alt">
<div class="wrap">
<h2 class="section-h">Services</h2>
<p class="section-sub">Every service below is delivered on the main website.</p>
<div class="cards">
{% for s in site.services %}
<a class="card" href="{{ site.main_site }}{{ s.path }}">
<h3>{{ s.name }}</h3>
<p>{{ s.blurb }}</p>
<span class="card-link">{{ site.main_site_label }}{{ s.path }} &rarr;</span>
</a>
{% endfor %}
</div>
</div>
</section>

<section class="band">
<div class="wrap narrow">
<h2>How a group booking runs</h2>
<ol class="steps">
<li><strong>Enquiry.</strong> You send the route, dates, approximate party size and cabin. No payment, no account.</li>
<li><strong>Quote.</strong> We approach the relevant airline group desks and come back with options, including the deposit amount, the name-submission deadline and the change and cancellation terms attached to each fare.</li>
<li><strong>Hold.</strong> You accept an option and pay the deposit. Seats are held at the agreed price while the group is finalised.</li>
<li><strong>Names.</strong> Passenger names are submitted by the deadline in the contract &mdash; usually weeks after the seats were secured.</li>
<li><strong>Ticketing and travel.</strong> Balance is paid, tickets are issued, and you keep one contact through to departure and for anything that changes en route.</li>
</ol>
</div>
</section>

<section class="band alt">
<div class="wrap">
<h2 class="section-h">Accreditation and trust</h2>
<div class="two-col">
<div>
<p>Airlines Group Travel holds the accreditations that let an agency issue airline tickets and handle client funds in the United States:</p>
<ul class="accred">
{% for a in site.accreditations %}
<li><strong>{{ a.name }}</strong> &mdash; {{ a.full }}</li>
{% endfor %}
</ul>
<p>Customer reviews are published on Trustpilot, independently of this site and of the main website. We do not host or moderate them.</p>
</div>
<div class="panel">
<h3>Registered entity</h3>
<p>
{{ site.legal_name }}{% if site.show_address %}<br>
{{ site.street }}<br>
{{ site.locality }}, {{ site.region }} {{ site.postal_code }}<br>
United States{% endif %}
</p>
<p>
<strong>Website</strong> &mdash; <a href="{{ site.main_site }}">{{ site.main_site_label }}</a><br>
<strong>Email</strong> &mdash; <a href="mailto:{{ site.email }}">{{ site.email }}</a><br>
<strong>Phone</strong> &mdash; <a href="tel:{{ site.phone }}">{{ site.phone_display }}</a>
</p>
</div>
</div>
</div>
</section>

<section class="band">
<div class="wrap narrow">
<h2 class="section-h">Published languages</h2>
<p class="section-sub">The main website is published in three languages.</p>
<ul class="lang-row plain">
{% for l in site.languages %}
<li><a href="{{ site.main_site }}{{ l.path }}" hreflang="{{ l.code }}"><span class="lang-code">{{ l.code }}</span> {{ l.name }}</a></li>
{% endfor %}
</ul>
</div>
</section>

<section class="band closing">
<div class="wrap narrow">
<h2>Planning a group movement?</h2>
<p>Send the route, the dates and a rough head count. A quote comes back with the deposit terms and the name deadline stated up front.</p>
<p class="cta-row">
<a class="btn btn-primary" href="{{ site.main_site }}">Start at {{ site.main_site_label }}</a>
</p>
</div>
</section>
