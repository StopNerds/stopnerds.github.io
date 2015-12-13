---
# vim: set ft=markdown :
layout: default
title: Jimmy's Story
comments: true
permalink: /slideshow/
---
<script type="text/javascript">
    function slide(i){
    	var $slide =  $('#slide' +i);
    	$('div.slide:visible').hide(800,'easeOutQuad', function(){
    		$('.chosen').removeClass('chosen');
    		$slide.show(1300,'easeOutQuad');
    		$('.slide-link-' +i).addClass('chosen');
    	});
    }
</script>
<style>
.js{display:none}.slideshow{margin:20px auto}div.slide{overflow:auto;width:750px}div.slide h2{font-size:2em;text-align:center}div.slide img.jimmy{float:left}div.slide p{width:450px;margin:.5em auto;float:right;line-height:1.8em}div.slide p.nextbtn{background:#0082cd;height:45px;border:3px solid #00456d;border-radius:15px}div.slide p.nextbtn:hover{background:#3092cb}div.slide p.nextbtn a{color:#fff;text-decoration:none;font-size:18px;text-shadow:0 1px 2px #666;text-align:center;height:45px;line-height:45px;display:block}ul#slidenumbers{padding:0;margin:15px 0;list-style:none}ul#slidenumbers li{display:inline;padding:15px}ul#slidenumbers li a{color:#aaa;text-decoration:none}ul#slidenumbers li a:hover{color:#d00}ul#slidenumbers li a.chosen{font-weight:700;color:#00456d}footer{color:#bbb;text-align:center}
</style>

<div class="slideshow">
    <noscript>
        <p style="text-align:center;color:#d00;font-size:smaller;">This page is best displayed with Javascript enabled.</p>
    </noscript>
    <div class="slide" id="slide1" style="display: block;">
        <h2>This is Jimmy.</h2>
        <img class="jimmy" src="{{site.baseurl}}/img/slideshow/1.png" style="width:270px;height:438px;">
        <div>
            <p>Jimmy considers himself a normal kid. He has friends which he prefers to socialize with using social media such as Instagram, WhatsApp and Snapchat.</p>
            <p>Sometimes he'll spend <b>up to 18 hours a day surfing the web</b>. And in the rare occasion that he isn't surfing the web, he'll <b>watch anime</b> or <b>play Minecraft</b>.</p>
            <p>Jimmy identifies himself as a <b>libertarian</b>, and he often spends time advocating libertarian candidates such as <b>Gary Johnson</b> for president.</p>
            <p>Jimmy finds he <b>prefers open source software</b> because he thinks it is better developed and safer.</p>
            <p>Last month, Jimmy <b>switched to Linux</b> and took up a new hobby: <b>programming and web development</b>. He enjoys this very much.</p>
            <p>Jimmy publishes his software under an <b>open-source license</b> on a code-sharing website. On occasion, he will contribute to his online friend's open source project on <b>GitHub</b>.</p>
            <p class="nextbtn js" style="display: block;"><a onclick="slide(2);" href="#slide2">Does Jimmy sound a bit like you?</a></p>
        </div>
    </div>
    <div class="slide" id="slide2" style="display: none;">
        <h2>Does Jimmy sound a bit like you?</h2>
        <img class="jimmy" src="{{site.baseurl}}/img/slideshow/2.png" style="width:270px;height:488px;">
        <div>
            <p>You see, <b>Jimmy isn't mentally healthy</b>. And if he sounds anything like you, <b>you're most likely ill too</b>.</p>
            <p>While Jimmy's doings may seem innocent, he isn't very productive at all. He might spend up to <b>two days</b> fixing his WLAN or <b>a week</b> upgrading his Linux distribution. Jimmy doesn't realize it, but his mental well-being is declining rapidly as he becomes more and more obsessed with the foolish concept of "open source" software.</p>
            <p>Jimmy has a girlfriend; her name is <b>Sakura Haruno</b> and she has <b>pink hair</b> and <b>green eyes</b>. And while it might not sound like it, Jimmy is still a <b>virgin</b>. Why? Because Sakura is an <b>anime character</b>.</p>
            <p>Chances are that although you might not share Jimmy's exact story, <b>you are just as sick and things are going to get much, much worse if you don't act now</b>. However, <b>it's not too late</b>. There is still hope.</p>
            <p class="nextbtn js" style="display: block;"><a onclick="slide(3);" href="#slide3">So, what can I do?</a></p>
        </div>
    </div>
    <div class="slide" id="slide3" style="display: none;">
        <h2>What can you do?</h2>
        <img class="jimmy" src="{{site.baseurl}}/img/slideshow/3.png" style="width:270px;height:526px;">
        <div>
            <p>First of all, <b>don't panic</b>. Taking rushed decisions will not help you—it's more likely to make your life <b>worse</b>.
            When you have thought over your mental health status and decided to take action, <b>see a psychologist</b>. He can identify mental illnesses such as <b>Asperger's syndrome</b>, <b>schizophrenia</b> or <b>bipolar disorder</b>.</p>
            <p>If you are a libertarian, stop advocating libertarian candidates such as Gary Johnson and vote <b>Hillary 2016</b>.</p>
            <p>Abandoning Minecraft is the next step, and probably the most important. If you have issues stopping, try seeking out <b>group therapy</b>.</p>
            <p>Linux and open source software are the next factors to get rid of. The solution is simple: <b>buy a Mac</b>. Be sure to ignore <acronym title="Free Software Foundation">FSF</acronym> propaganda such as "Mac is for faggots"; this is <acronym title="fear, uncertainty and doubt">FUD</acronym>, pure and simple.</p>
            <p>To stop watching anime is the hardest step and probably the most painful. StopNerds.org recommends that watching mentally healthy cartoons such as <b>Kim Possible</b> and <b>South Park</b> is the best and easiest way to counter any urge to watch sicko Japanese cartoons.</p>
            <p>If you've successfully followed every step above, congratulations! Remember to revisit your psychologist to make sure that the mental illness has disappeared.</p>
            <p class="nextbtn js" style="display: block;"><a onclick="slide(4);" href="#slide4">What happened to Jimmy?</a></p>
        </div>
    </div>
    <div class="slide" id="slide4" style="display: none;">
        <h2>What happened to Jimmy?</h2>
        <img class="jimmy" src="{{site.baseurl}}/img/slideshow/4.png" style="width:270px;height:556px;margin-right: 15px;">
        <div>
            <p>Jimmy was able to overcome his mental illness. He has had <b>three relationships</b> with real women within two weeks.</p>
            <p>Jimmy's support for Gary Johnson <b>has ceased</b>. He now holds sensible political opinions and votes for non-libertarian candidates only.</p>
            <p>Since he is <b>no longer tied to his computer</b>, Jimmy has become a successful politician himself. He advocates long-term improvement of mental health in the US.</p>
        </div>
        <p style="text-align:center"><a href="{{site.baseurl}}"><img style="width:308px;height:150px;margin:30px 0;" src="{{site.baseurl}}/img/logo150px.png"></a></p>
        <p class="nextbtn"><a href="{{site.baseurl}}/nerd-test/">Are you a nerd? Take the test to find out.</a></p>
    </div>
    <ul id="slidenumbers" class="js" style="display: block;">
        <li><a class="slide-link-1 chosen" onclick="slide(1);" href="#slide1">1</a></li>
        <li><a class="slide-link-2" onclick="slide(2);" href="#slide2">2</a></li>
        <li><a class="slide-link-3" onclick="slide(3);" href="#slide3">3</a></li>
        <li><a class="slide-link-4" onclick="slide(4);" href="#slide4">4</a></li>
    </ul>
</div>
