---
layout: default
---

# Tech Video Club

Every wednesday we get together to watch a video over lunch.

If you prefer twitter you can [see our tweets about video club there](https://twitter.com/search?f=tweets&q=from%3Apauldambra%20AND%20video%20club%20OR%20%23videoclub&src=typd)

<div class="video-club">
  {% assign sorted_videos = site.data.video_club | sort:"date" | reverse %}
  {% for video in sorted_videos %}
    <div class="video-tile">

      <h1>{{ video.title }}</h1>
      <h3>{{ video.presenter }}</h3>
      <div class="entry">
        <div class="watched-date">
          {{ video.date | date: "%d-%m-%Y" }}
        </div>
        <a href="{{ video.video_url }}">
          watch at: {{ video.video_url }}
        </a>
        {% if video.note and video.note != blank %}
          <p> {{ video.note }} </p>
        {% endif%}

        {% if video.image_url and video.image_url != blank %}
          <div class="image-footer">
            <a href="{{ video.video_url }}">
              <img src="{{ video.image_url }}" />
            </a>
          </div>
        {% endif%}
      </div>
    </div>
  {% endfor %}
</div>
