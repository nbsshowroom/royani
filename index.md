---
layout: default
---

<div class="idxpage-title-container">
	<div class="idxpage-title-content" id="highlightTitle">
        ### Latest Projects
	</div>
</div>
<div class="idxpage-highlight-container">
	<div class="idxpage-highlight-content" id="latesthights">
        <img id="hightLightImage">
	</div>
</div>


<script type="text/javascript">

function initHighlights() {
    var highlightImage = document.getElementById("hightLightImage");

    var backgrounds = [
            {% for project in site.data.latest_projects %}
            "{{ site.baseurl }}{{ project.cover_img_url }}",
        {% endfor %}
	];

    var current = 0;
    function nextBackground() {
        hightLightImage.setAttribute("src", backgrounds[current = ++current % backgrounds.length]);
        setTimeout(nextBackground, 5000);
        hightLightImage.className += " " + "withfadeout";
    }
    setTimeout(nextBackground, 5000);
}
</script>