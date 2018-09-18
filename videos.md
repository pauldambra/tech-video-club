---
layout: default
---

<div class="video-club flex-column">
  {% assign sorted_videos = site.data.video_club | sort:"date" | reverse %}
  {% include video-list.html %}
</div>
