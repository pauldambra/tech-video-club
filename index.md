---
layout: default
---

<div>
  <p>
    Every wednesday we get together to watch a video over lunch. Here are the last 5 videos we watched.
  </p>

  <p>
    You can see <a href="{{ site.baseurl }}/videos">a list of all of the videos</a> or if you prefer twitter you can <a href="https://twitter.com/search?f=tweets&q=from%3Apauldambra%20AND%20video%20club%20OR%20%23videoclub&src=typd" target="_blank">see our tweets about video club there</a>
  </p>
</div>

<div class="video-club flex-column">
  {% assign sorted_videos = site.data.video_club | sort:"date" | reverse | slice: 0, 5 %}
  {% include video-list.html %}
</div>
