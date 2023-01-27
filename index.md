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
<a href="" class="typewrite" data-period="2000" data-type='[ "Data Science","Cloud Computing" ,"Scientific Computing"]'>
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


<p style='text-align: justify;'>
I am Adekunle Ajayi, and I am currently a senior software engineer at Talend. If you are interested in my CV, kindly check my <a href=" https://www.linkedin.com/in/adekunle-ajayi/" target="_blank">profile</a> on LinkedIn.</p>

