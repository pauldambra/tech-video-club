---
layout: default
---

<div class="video-club flex-column">
  {% assign sorted_videos = site.data.video_club | sort:"date" | reverse %}
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