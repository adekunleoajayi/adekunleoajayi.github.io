---
layout: default
title: 
---
<!-- Add CSS -->
<style type="text/css">
img {
border-radius: 50%;
}

body {
color:#000000;

}
</style>


<!-- Add Java script -->
<script>
var TxtType = function(el, toRotate, period) {
this.toRotate = toRotate;
this.el = el;
this.loopNum = 0;
this.period = parseInt(period, 10) || 2000;
this.txt = '';
this.tick();
this.isDeleting = false;
};

TxtType.prototype.tick = function() {
var i = this.loopNum % this.toRotate.length;
var fullTxt = this.toRotate[i];

if (this.isDeleting) {
this.txt = fullTxt.substring(0, this.txt.length - 1);
} else {
this.txt = fullTxt.substring(0, this.txt.length + 1);
}

this.el.innerHTML = '<span class="wrap">'+this.txt+'</span>';

var that = this;
var delta = 100 - Math.random() * 100; /*this controls the speed of the text*/

if (this.isDeleting) { delta /= 2; }

if (!this.isDeleting && this.txt === fullTxt) {
delta = this.period;
this.isDeleting = true;
} else if (this.isDeleting && this.txt === '') {
this.isDeleting = false;
this.loopNum++;
delta = 500;
}

setTimeout(function() {
that.tick();
}, delta);
};

window.onload = function() {
var elements = document.getElementsByClassName('typewrite');
for (var i=0; i<elements.length; i++) {
var toRotate = elements[i].getAttribute('data-type');
var period = elements[i].getAttribute('data-period');
if (toRotate) {
new TxtType(elements[i], JSON.parse(toRotate), period);
}
}
// INJECT CSS
var css = document.createElement("style");
css.type = "text/css";
css.innerHTML = ".typewrite > .wrap { border-right: 0.08em solid #000000 }";
document.body.appendChild(css);
};
</script>
<br>


<!-- Add dynamic typing -->

<h2>
<p style='text-align: center;'>
<a href="" class="typewrite" data-period="2000" data-type='[ "Scientific Computing", "Data Science", "Applied Mathematics","High Performance Data Analytics","Ocean Physics" ]'>
<span class="wrap" color=#000000  ></span>
</a>
</p>
</h2>
<br>

<!-- Add image -->
<div style="display: flex; justify-content: center;">
<img src="{{site.baseurl}}/img/Ade.jpeg" align="middle" style="width:300px;height:300px;"> 
</div>
<br>


<p style='text-align: center;'>
I am a research engineer, data scientist and an ocean physicist.</p>
<br>

<p style='text-align: justify;'>
I am currently a research engineer at <a href="https://data-institute.univ-grenoble-alpes.fr/" target="_blank"> Grenoble Alpes Data institute</a> where I am working at the interface between deep learning and ocean physics.</p>

<br>

<p style='text-align: justify;'>
Previously, I was a doctoral researcher at the <a href="http://www.ige-grenoble.fr/" target="_blank"> Institut des Géosciences de l'Environnement</a>. At IGE, I investigated kinetic energy cascades in turbulent oceanic flow at fine-scales. This study was carried out by applying high-performance data analytics tools to analyze large-scale multidimensional geophysical datasets.</p>

<br>

<p style='text-align: justify;'>
I have a PhD in ocean physics and a masters degree in environmental fluid mechanics from the <a href="http://www.univ-grenoble-alpes.fr/" target="_blank"> Université Grenoble Alpes</a>, France. I obtained a bachelor's degree (B.Tech) in applied mathematics from the <a href="https://futa.edu.ng/" target="_blank"> Federal University of Technology Akure</a>, and I am an alumnus of the prestigious Abdus Salam <a href="https://www.ictp.it/" target="_blank"> International Center for Theoretical Physics</a>, Italy.</p>








