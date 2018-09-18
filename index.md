---
layout: default
---

<div>
  <p>
    Every wednesday we get together to watch a video over lunch. Here are the last 5 videos we watched.
  </p>

  <p>
    You can see <a href="{{ site.baseurl }}/videos">all of the videos</a> or if you prefer twitter you can <a href="https://twitter.com/search?f=tweets&q=from%3Apauldambra%20AND%20video%20club%20OR%20%23videoclub&src=typd" target="_blank">see our tweets about video club there</a>
  </p>
</div>

<div class="video-club flex-column">
  {% assign sorted_videos = site.data.video_club | sort:"date" | reverse | slice: 0, 5 %}
  {% for video in sorted_videos %}
    <div class="video-tile">

      <h1>
        <a href="{{ video.video_url }}">
          {{ video.title }} by {{video.presenter}}
        </a>
      </h1>

      watched on {{ video.date | date: "%Y&#8209;%m&#8209;%d" }} at: <a href="{{ video.video_url }}">{{ video.video_url }}</a>

      {% if video.note and video.note != blank %}
        <p> {{ video.note }} </p>
      {% endif%}

      {% if video.image_url and video.image_url != blank %}
        <div class="video-image">
          <a href="{{ video.video_url }}">
            <img src="{{ video.image_url }}" />
          </a>
        </div>
      {% endif%}

    </div>
  {% endfor %}
</div>