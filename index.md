---
layout: default
---

<div class="idxpage-title-container">
	<div class="idxpage-title-content" id="highlightTitle">
        Latest Projects
	</div>
</div>
<div class="idxpage-highlight-container">
	<div class="idxpage-highlight-content" id="latesthights">
	</div>
</div>


<script type="text/javascript">

function initHighlights() {
    var highlightImage = document.getElementById("latesthights").style;
    var highlightProjectName = document.getElementById("highlightTitle");

    var backgrounds = [
            {% for project in site.data.latest_projects %}
            'url({{ site.baseurl }}{{ project.cover_img_url }})',
        {% endfor %}
	];

    var current = 0;
    function nextBackground() {
        highlightImage.backgroundImage = backgrounds[current = ++current % backgrounds.length];
        highlightProjectName.innerHTML = "New text!";
        setTimeout(nextBackground, 5000);
    }
    setTimeout(nextBackground, 5000);
    highlightImage.backgroundImage = backgrounds[0];
}
</script>