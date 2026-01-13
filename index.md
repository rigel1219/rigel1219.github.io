---
layout: single
title: ""          # 제목을 비워둬야 커스텀 디자인이 더 예쁩니다
author_profile: false  # 왼쪽 사이드바 제거
permalink: /       # 메인 페이지로 쓸 경우 (About 메뉴라면 /about/ 등 설정)
classes: wide      # 화면을 넓게 보여줌
---

<div style="display: flex; flex-wrap: wrap; gap: 40px; align-items: flex-start; margin-top: 20px; margin-bottom: 60px;">
  
  <div style="flex: 0 0 auto; width: 280px;">
    <img src="/assets/images/profile.jpg" alt="프로필 사진" 
         style="width: 100%; border-radius: 15px; box-shadow: 0 4px 12px rgba(0,0,0,0.15); object-fit: cover;">
  </div>

  <div style="flex: 1; min-width: 300px;">
    
    <h1 style="font-size: 2.8em; margin-bottom: 15px; margin-top: 0; font-weight: 700;">
      조동우
    </h1>

    <div style="font-size: 1.1em; color: #444; margin-bottom: 25px; line-height: 1.6;">
      <p style="margin-bottom: 10px;">
        안녕하세요, 소개글<br>
        간략한 소개글
      </p>
    </div>

    <div style="margin-bottom: 25px;">
      <h3 style="margin-bottom: 10px; font-size: 1.2em; border-bottom: 2px solid #eee; padding-bottom: 5px;">History</h3>
      <ul style="margin-top: 0; padding-left: 20px; line-height: 1.8; color: #555;">
        <li><strong>2026 - Present</strong> : M.S. in Aerospace Engineering, Inha University</li>
        <li><strong>2020 - 2026</strong> : B.S. in Aerospace Engineering, Inha University</li>
        </ul>
    </div>

    <div style="font-size: 1.05em;">
      <h3 style="margin-bottom: 10px; font-size: 1.2em; border-bottom: 2px solid #eee; padding-bottom: 5px;">Contact</h3>
      <ul style="list-style: none; padding: 0; margin: 0; line-height: 2.2;">
        
        <li>
          <i class="fas fa-map-marker-alt" style="width: 25px; text-align: center; color: #555; margin-right: 10px;"></i> 
          <span style="color: #444;">36, Gaetbeol-ro, Yeonsu-gu, Incheon, Republic of Korea</span>
        </li>

        <li>
          <i class="fab fa-github" style="width: 25px; text-align: center; color: #555; margin-right: 10px;"></i> 
          <a href="https://github.com/rigel1219" target="_blank" style="text-decoration: none; color: #333; border-bottom: 1px dotted #999;">GitHub</a>
        </li>

        <li>
          <i class="fas fa-envelope" style="width: 25px; text-align: center; color: #555; margin-right: 10px;"></i> 
          <a href="mailto:12200623@inha.edu" style="text-decoration: none; color: #333; border-bottom: 1px dotted #999;">12200623@inha.edu</a>
        </li>

        <li>
          <i class="fab fa-linkedin" style="width: 25px; text-align: center; color: #0077b5; margin-right: 10px;"></i> 
          <a href="https://www.linkedin.com/in/%EB%8F%99%EC%9A%B0-%EC%A1%B0-730312356/" target="_blank" style="text-decoration: none; color: #333; border-bottom: 1px dotted #999;">LinkedIn</a>
        </li>
        
      </ul>
    </div>

  </div>
</div>
<hr style="margin: 40px 0;">


<h2 style="margin-bottom: 20px;">Recent Projects</h2>

<div style="width: 100%; display: block;">
  {% for post in site.portfolio limit:2 %}
    {% include archive-single.html type="grid" %}
  {% endfor %}
</div>

<div style="clear: both; margin-bottom: 30px;"></div>

<h2 style="margin-bottom: 20px; border-top: 1px solid #eee; padding-top: 40px;">Recent Posts</h2>

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
