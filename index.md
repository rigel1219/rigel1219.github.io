---
layout: single
title: ""          # 제목을 비워둬야 커스텀 디자인이 더 예쁩니다
author_profile: false  # 왼쪽 사이드바 제거
permalink: /       # 메인 페이지로 쓸 경우 (About 메뉴라면 /about/ 등 설정)
classes: wide      # 화면을 넓게 보여줌
---

<div style="display: flex; flex-wrap: wrap; gap: 40px; align-items: center; margin-bottom: 60px; margin-top: 20px;">
  <img src="/assets/images/profile.jpg" alt="프로필 사진" 
       style="width: 250px; height: 250px; border-radius: 20px; object-fit: cover; box-shadow: 0 4px 10px rgba(0,0,0,0.1);">
  
  <div style="flex: 1; min-width: 300px;">
    <h1 style="margin-top: 0; font-size: 2.5em; margin-bottom: 10px;"> 조동우 </h1>
    <p style="font-size: 1.1em; color: #666; margin-bottom: 20px;">
      ㄱㄴㄷㄹㅁㅂㅅ간략한 소개글.<br>
      testtesttesttest
    </p>
    
    <ul style="list-style: none; padding: 0; font-size: 1.05em; line-height: 1.8;">
      <li>
        <i class="fas fa-map-marker-alt" style="width: 25px; color: #555;"></i> 
        Busan, Korea
      </li>
      <li>
        <i class="fab fa-github" style="width: 25px; color: #555;"></i> 
        <a href="https://github.com/본인아이디" target="_blank" style="text-decoration: none; color: #333;">github.com/본인아이디</a>
      </li>
      <li>
        <i class="fas fa-envelope" style="width: 25px; color: #555;"></i> 
        <a href="mailto:이메일주소" style="text-decoration: none; color: #333;">이메일주소@gmail.com</a>
      </li>
      <li>
        <i class="fab fa-instagram" style="width: 25px; color: #555;"></i> 
        <a href="https://instagram.com/아이디" target="_blank" style="text-decoration: none; color: #333;">@instagram_id</a>
      </li>
    </ul>
  </div>
</div>

---

<h2 style="margin-top: 40px; margin-bottom: 20px;">Recent Projects</h2>

<div class="grid__wrapper">
  {% for post in site.portfolio limit:2 %}
    {% include archive-single.html type="grid" %}
  {% endfor %}
</div>

<h2 style="margin-top: 40px; margin-bottom: 20px;">Recent Posts</h2>

<div class="list__item">
  {% for post in site.posts limit:4 %}
    <article class="archive__item" itemscope itemtype="https://schema.org/CreativeWork">
      <h3 class="archive__item-title no_toc" itemprop="headline">
        <a href="{{ post.url | relative_url }}" rel="permalink">{{ post.title }}</a>
      </h3>
      <p class="page__meta">
        <i class="far fa-clock" aria-hidden="true"></i> {{ post.date | date: "%Y-%m-%d" }}
      </p>
      <p class="archive__item-excerpt" itemprop="description">{{ post.excerpt | strip_html | truncate: 160 }}</p>
    </article>
  {% endfor %}
</div>

