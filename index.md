---
layout: single
title: ""          # 제목을 비워둬야 커스텀 디자인이 더 예쁩니다
author_profile: false  # 왼쪽 사이드바 제거
permalink: /       # 메인 페이지로 쓸 경우 (About 메뉴라면 /about/ 등 설정)
classes: wide      # 화면을 넓게 보여줌
---

<div style="display: flex; flex-wrap: wrap; gap: 40px; align-items: flex-start; margin-top: 20px;">
  
  <div style="flex-shrink: 0;">
    <img src="/assets/images/profile.jpg" alt="프로필 사진" 
         style="width: 250px; height: 250px; border-radius: 20px; object-fit: cover; box-shadow: 0 4px 10px rgba(0,0,0,0.1);">
  </div>
  
  <div style="flex: 1; min-width: 300px;">
    
    <h1 style="margin-top: 0; font-size: 2.2em; margin-bottom: 10px;">Jun (Your Name)</h1>
    <p style="font-size: 1.1em; color: #666; margin-bottom: 25px;">
      소개글1.<br>
      소개글2
    </p>

    <div style="margin-bottom: 0;">
      <h3 style="margin-bottom: 10px; font-size: 1.2em; border-bottom: 2px solid #eee; padding-bottom: 5px; color: #333;">History</h3>
      <ul style="margin-top: 0; padding-left: 20px; line-height: 1.8; color: #555;">
        <li><strong>2026 - Present</strong> : M.S. in Aerospace Engineering, Inha University</li>
        <li><strong>2020 - 2026</strong> : B.S. in Aerospace Engineering, Inha University</li>
      </ul>
    </div>

  </div> </div> <div style="margin-top: 40px; margin-bottom: 60px;">
  <h3 style="margin-bottom: 15px; font-size: 1.2em; border-bottom: 2px solid #eee; padding-bottom: 5px; color: #333;">Contact</h3>
  
  <ul style="list-style: none; padding: 0; margin: 0; display: grid; grid-template-columns: repeat(auto-fit, minmax(200px, 1fr)); gap: 15px; line-height: 2.0;">
    
    <li>
      <i class="fas fa-map-marker-alt" style="width: 25px; text-align: center; color: #555; margin-right: 10px;"></i> 
      <a href="https://www.google.com/maps/search/?api=1&query=36+Gaetbeol-ro+Yeonsu-gu+Incheon" target="_blank" style="text-decoration: none; color: #333; border-bottom: 1px dotted #999;">
        Incheon, Korea
      </a>
    </li>

    <li>
      <i class="fab fa-github" style="width: 25px; text-align: center; color: #555; margin-right: 10px;"></i> 
      <a href="https://github.com/rigel1219" target="_blank" style="text-decoration: none; color: #333; border-bottom: 1px dotted #999;">GitHub</a>
    </li>

    <li>
      <i class="fas fa-envelope" style="width: 25px; text-align: center; color: #555; margin-right: 10px;"></i> 
      <a href="mailto:12200623@inha.edu" style="text-decoration: none; color: #333; border-bottom: 1px dotted #999;">Email</a>
    </li>

    <li>
      <i class="fab fa-linkedin" style="width: 25px; text-align: center; color: #0077b5; margin-right: 10px;"></i> 
      <a href="https://www.linkedin.com/in/%EB%8F%99%EC%9A%B0-%EC%A1%B0-730312356/" target="_blank" style="text-decoration: none; color: #333; border-bottom: 1px dotted #999;">LinkedIn</a>
    </li>

  </ul>
</div>

---

<h2 style="margin-top: 40px; margin-bottom: 20px;">Recent Projects</h2>

<div style="width: 100%; display: block;">
  {% for post in site.portfolio limit:2 %}
    {% include archive-single.html type="grid" %}
  {% endfor %}
</div>
<div style="clear: both; margin-bottom: 30px;"></div>

<h2 style="margin-top: 40px; margin-bottom: 20px; border-top: 1px solid #eee; padding-top: 40px;">Recent Posts</h2>

<div class="list__item">
  {% for post in site.posts limit:4 %}
    <article class="archive__item" itemscope itemtype="https://schema.org/CreativeWork" style="margin-bottom: 20px;">
      <h3 class="archive__item-title no_toc" itemprop="headline" style="margin-top: 0; font-size: 1.3em;">
        <a href="{{ post.url | relative_url }}" rel="permalink" style="text-decoration: none; color: #333;">{{ post.title }}</a>
      </h3>
      <p class="page__meta" style="font-size: 0.8em; color: #888; margin-bottom: 5px;">
        <i class="far fa-clock" aria-hidden="true"></i> {{ post.date | date: "%Y-%m-%d" }}
      </p>
      <p class="archive__item-excerpt" itemprop="description" style="font-size: 0.95em; color: #666;">{{ post.excerpt | strip_html | truncate: 100 }}</p>
    </article>
  {% endfor %}
</div>
