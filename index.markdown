---
---
{% include header.html %}

<body>
    <header class="header">    
        <div class="branding">
            <div class="container position-relative">
				<nav class="navbar navbar-expand-lg" >
                    <h1 class="site-logo">
                        <a class="navbar-brand" href="/">
                            <img class="logo-icon" src="assets/images/logo-icon.svg" alt="logo">
                            <span class="logo-text">{{ site.title }}</span>
                        </a>
                    </h1>
				</nav>       
            </div><!--//container-->
        </div><!--//branding-->        
    </header><!--//header-->
    {% include hero.html %}
    {% comment %}
    {% include logos.html %}
    {% endcomment %}
    <section class="features-section py-5">
	    <div class="container py-lg-5">
		    <h3 class="mb-3 text-center font-weight-bold section-heading">Feature Highlights</h3>
			{% for appfeature in site.appfeatures %}
			 	{% capture thecycle %}{% cycle 'odd', 'even' %}{% endcapture %}
				{% if thecycle == 'odd' %}
				<div class="row pt-5 mb-5"> <!-- feature image on left -->
					<div class="col-12 col-md-6 col-xl-5 offset-xl-1 d-none d-md-block">
						<img class="product-figure product-figure-1 img-fluid" src="{{ appfeature.image }}" alt="" />
					</div>
					<div class="col-12 col-md-6 col-xl-5 pr-xl-3 pt-md-3">
						{% for card in appfeature.cards %}
							<div class="card rounded border-0 shadow-lg  mb-5">
								<div class="card-body p-4">
									<h5 class="card-title"><i class="far fa-chart-bar mr-2 mr-lg-3 text-primary fa-lg fa-fw"></i>{{ card.title }}</h5>
									{{ card.description }}
								</div>
							</div><!--//card-->
						{% endfor %}
					</div>
				</div>
				{% else %}
				<div class="row">
					<div class="col-12 col-md-6 col-xl-5 order-md-2 pr-xl-3 d-none d-md-block">
						<img class="product-figure product-figure-2 img-fluid" src="{{ appfeature.image }}" alt="" />
					</div>
					<div class="col-12 col-md-6 col-xl-5 order-md-1 offset-xl-1 pt-xl-5">
						{% for card in appfeature.cards %}
							<div class="card rounded border-0 shadow-lg  mb-5">
								<div class="card-body p-4">
									<h5 class="card-title"><i class="far fa-chart-bar mr-2 mr-lg-3 text-primary fa-lg fa-fw"></i>{{ card.title }}</h5>
									{{ card.description }}
								</div>
							</div><!--//card-->
						{% endfor %}
					</div>
				</div>
				{% endif %}
			{% endfor %}
	    </div><!--//container-->
    </section><!--//features-section-->
    {% comment %}
    {% include calltoaction.html %}
    {% endcomment %}
    {% comment %}
    {% include testimonials.html %}
    {% endcomment %}
 {% include footer.html %}