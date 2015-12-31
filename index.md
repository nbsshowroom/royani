---
layout: default
---

<div class="idxpage-title-container">
	<div class="idxpage-title-content">
	</div>
</div>
<div class="idxpage-highlight-container">
	<div class="idxpage-highlight-content" id="latesthights">
	</div>
</div>


<script type="text/javascript">

function initHighlights() {
    var body = document.getElementById("latesthights").style;
    var backgrounds = [
            {% for project in site.data.latest_projects %}
            'url({{ site.baseurl }}{{ project.cover_img_url }})',
        {% endfor %}
	];

    var current = 0;
    function nextBackground() {
        body.backgroundImage = backgrounds[current = ++current % backgrounds.length];
        setTimeout(nextBackground, 5000);
    }
    setTimeout(nextBackground, 5000);
    body.backgroundImage = backgrounds[0];
}
</script>