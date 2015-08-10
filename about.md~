---
layout: page
title: About
---

**Name:** Vyaas Gururajan

**Occupation:** Perishing PhD Student

**Preoccupation:** Pondering lifestyle choices in light of the amazing descriptions of Nature proffered by Boltzmann, Einstein, and Feynman, the detailed and prophetic exposition of Capital by Karl Marx, the soulful renditions of Jazz by Bill Evans, the method of electro-shock-therapy-through-comedy pioneered by George Carlin, the disturbing-of-comfortable-and-comforting-of-disturbed agenda of humanistic literature exemplified by David Foster Wallace, the Kantian directions inscribed by Richard Stallman on our collective moral compass, and the enigmatic effectiveness and spellbinding metaphysical sanctuary provided by Mathematics.

**Most troubling observation:**
>**"***In a time so rich in reflection and so devoted to raisonnement as our own, he must be a poor creature who cannot advance a good ground for everything, even for what is worst and most depraved. Everything in the world that has become corrupt, has had good ground for its corruption.***"** (Hegel, *Logic*, para. 121)

**Psychological ailment:** Currently battling *Bullshit Induced Aphasia*, an apparently incurable disease wherein the subject suffers the violent disemboweling of his senses upon hearing the sophistry of fatalists and teleologists through one ear and the high pitched drone of solipsists and nihilists through the other, resulting in a mental state of spaz-unto-death. What the subject looks like on the outside can only be left to one's imagination.

$$ J  = \int_a^b L(t,q^\mu,\dot{q^\mu})dt $$
$$ t' = r +\epsilon\tau + ..., $$
$$ q^{\mu'}  = q^{\mu} + \epsilon\zeta^\mu + ... $$
$$ L' \frac{dt'}{dt} - L = \epsilon\frac{dF}{dt} + O(\epsilon^s),$$ where \\( s\gt 1 \\), 





<div id="comments">
	{% case page.comment_count %}
		{% when 0 %}
		{% when 1 %}
			<h1>1 Comment</h1>
		{% else %}
			<h1>{{page.comment_count}} Comments</h1>
	{% endcase %}
	{% for c in page.comments %}
		<div class="comment {% cycle 'odd', 'even' %}">
			<p class="comment_header">
				From: {% if c.link and c.link != '' %}
					<a href="{{c.link}}">{{c.name}}</a>
				{% else %}
					{{c.name}}
				{% endif %}
				<br />
				<span class="comment_date">{{c.date}}</span>
			</p>
			<p>
				{{c.comment | newline_to_br}}
			</p>
		</div>
	{% endfor %}
	<h1>Post a comment</h1>
	<p style="font-style: italic">
		All comments are held for moderation; basic HTML formatting accepted.
	</p>
	<form id="commentform" method="POST" action="{{ site.baseurl }}commentsubmit.php">
		<input type="hidden" name="post_id" value="{{page.id}}" />
		<input type="hidden" name="return_url" value="{{site.url}}{{page.url}}" />
		<table>
			<tr>
				<th>Name:</th>
				<td><input type="text" size="25" name="name" /> (required)</td>
			</tr>
			<tr>
				<th>E-mail:</th>
				<td><input type="text" size="25" name="email" /> (required, not published)</td>
			</tr>
			<tr>
				<th>Website:</th>
				<td><input type="text" size="25" name="link" /> (optional)</td>
			</tr>
			<tr>
				<td colspan="2"><textarea name="comment" rows="10" cols="60" ></textarea></td>
			</tr>
			<tr>
				<td><input type="submit" name="submit" value="Submit Comment" /></td>
			</tr>
		</table>
	</form>
</div>



