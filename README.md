<html>
<head>
  <meta charset="UTF-8" />
  <meta name="viewport" content="width=device-width, initial-scale=1.0"/>
  <title>Happy Birthday, Bhavana! 🎂</title>
  <style>
    /* Global Styles */
    :root {
      --primary: #ff6b81;
      --secondary: #ffa4b6;
      --bg-color: #fff0f3;
      --card-bg: #ffffff;
      --text-color: #4a4a4a;
      --saffron: #ff8c00;
    }

    * {
      box-sizing: border-box;
      margin: 0;
      padding: 0;
      font-family: 'Segoe UI', Tahoma, Geneva, Verdana, sans-serif;
    }

    body {
      background-color: var(--bg-color);
      color: var(--text-color);
      display: flex;
      flex-direction: column;
      align-items: center;
      justify-content: center;
      padding: 20px;
      overflow-x: hidden;
      min-height: 100vh;
    }

    .container {
      max-width: 600px;
      width: 100%;
    }

    /* Passcode Screen */
    #lock-screen {
      background: var(--card-bg);
      border-radius: 20px;
      padding: 40px 25px;
      text-align: center;
      box-shadow: 0 10px 30px rgba(0,0,0,0.08);
      max-width: 450px;
      width: 100%;
      margin: auto;
      animation: fadeIn 0.8s ease-in-out;
    }

    .date-badge {
      display: inline-block;
      background: #ffe6ea;
      color: var(--primary);
      padding: 6px 16px;
      border-radius: 20px;
      font-weight: 700;
      font-size: 0.95rem;
      margin-bottom: 12px;
    }

    .signature-tag {
      color: var(--primary);
      font-weight: 600;
      font-size: 1rem;
      margin-top: 4px;
    }

    .passcode-input-group {
      margin-top: 25px;
      display: flex;
      flex-direction: column;
      align-items: center;
      gap: 12px;
    }

    .passcode-input-group input {
      padding: 12px 18px;
      border: 2px solid #ffd1d9;
      border-radius: 25px;
      font-size: 1.1rem;
      text-align: center;
      outline: none;
      width: 80%;
      transition: border-color 0.3s;
    }

    .passcode-input-group input:focus {
      border-color: var(--primary);
    }

    .hint-text {
      font-size: 0.88rem;
      color: #888;
      background: #fff0f3;
      padding: 8px 14px;
      border-radius: 12px;
      width: 85%;
      margin-top: 2px;
    }

    .unlock-btn, .next-slide-btn, .prev-slide-btn {
      background: var(--primary);
      color: #fff;
      border: none;
      padding: 12px 28px;
      border-radius: 25px;
      font-size: 1rem;
      font-weight: bold;
      cursor: pointer;
      margin-top: 10px;
      transition: transform 0.2s, background-color 0.2s;
    }

    .unlock-btn:hover, .next-slide-btn:hover, .prev-slide-btn:hover {
      transform: scale(1.05);
      background-color: #ff526c;
    }

    .prev-slide-btn {
      background: #e0e0e0;
      color: #555;
    }

    .prev-slide-btn:hover {
      background: #d0d0d0;
    }

    .error-msg {
      color: #e74c3c;
      font-size: 0.9rem;
      display: none;
      margin-top: 5px;
    }

    /* Main Storybook Container */
    #main-content {
      display: none;
      width: 100%;
    }

    /* Individual Story Slide */
    .story-slide {
      display: none;
      background: var(--card-bg);
      border-radius: 20px;
      padding: 35px 25px;
      text-align: center;
      box-shadow: 0 10px 30px rgba(0,0,0,0.08);
      position: relative;
    }

    .story-slide.active-slide {
      display: block;
      animation: slideInRight 0.6s cubic-bezier(0.16, 1, 0.3, 1);
    }

    h1, h2 {
      color: var(--primary);
      margin-bottom: 15px;
    }

    h1 { font-size: 2.2rem; }
    h2 { font-size: 1.6rem; }

    .sub-title {
      font-size: 1.05rem;
      color: #777;
      margin-bottom: 25px;
    }

    /* Music Players */
    .music-box {
      background: #ffe6ea;
      padding: 15px;
      border-radius: 12px;
      display: inline-flex;
      flex-direction: column;
      align-items: center;
      gap: 10px;
      margin-bottom: 25px;
      width: 100%;
    }

    .music-box.saffron-theme {
      background: #fff3e0;
      border: 1px solid #ffe0b2;
    }

    .music-btn {
      background: var(--primary);
      color: #fff;
      border: none;
      padding: 8px 20px;
      border-radius: 20px;
      cursor: pointer;
      font-weight: bold;
      transition: transform 0.2s;
    }

    .music-btn.saffron-btn {
      background: var(--saffron);
    }

    .wish-text {
      line-height: 1.7;
      font-size: 1.1rem;
      text-align: left;
      background: #fff0f3;
      padding: 20px;
      border-radius: 15px;
      border-left: 4px solid var(--primary);
      margin-bottom: 20px;
    }

    /* Call Box Stylings */
    .calls-card {
      background: #fff0f3;
      border-radius: 15px;
      padding: 20px;
      margin: 15px 0;
      border: 1px dashed var(--primary);
    }

    .call-time {
      font-size: 1.3rem;
      font-weight: bold;
      color: var(--primary);
      margin-top: 8px;
    }

    .calls-grid {
      display: grid;
      grid-template-columns: repeat(2, 1fr);
      gap: 12px;
      margin: 15px 0;
    }

    .call-screenshot-card {
      background: #fff;
      border-radius: 12px;
      padding: 8px;
      border: 1px solid #ffe6ea;
      box-shadow: 0 4px 10px rgba(0,0,0,0.05);
    }

    .call-screenshot-card img {
      width: 100%;
      height: 160px;
      object-fit: cover;
      border-radius: 8px;
      margin-bottom: 6px;
    }

    .call-screenshot-card span {
      display: block;
      font-size: 0.85rem;
      font-weight: 600;
      color: var(--primary);
    }

    /* Ayodhya Blessings Box */
    .ram-blessing-box {
      background: #fff9f0;
      border-left: 4px solid var(--saffron);
      padding: 16px;
      border-radius: 12px;
      margin-bottom: 18px;
      text-align: left;
      font-size: 1.05rem;
      line-height: 1.6;
      color: #555;
    }

    /* Ayodhya Multi-Batch Slider */
    .ayodhya-slider-wrapper {
      background: #fff;
      border: 1px solid #ffe0b2;
      border-radius: 15px;
      padding: 15px;
      margin: 15px 0;
      box-shadow: 0 4px 12px rgba(0,0,0,0.05);
    }

    .ayodhya-page {
      display: none;
    }

    .ayodhya-page.active-page {
      display: block;
      animation: fadeIn 0.4s ease-in-out;
    }

    .ayodhya-grid {
      display: grid;
      grid-template-columns: repeat(2, 1fr);
      gap: 12px;
    }

    .ayodhya-photo-card {
      background: #fff0f3;
      border-radius: 10px;
      padding: 6px;
      box-shadow: 0 2px 8px rgba(0,0,0,0.06);
    }

    .ayodhya-photo-card img {
      width: 100%;
      height: 140px;
      object-fit: cover;
      border-radius: 8px;
    }

    .ayodhya-slider-controls {
      display: flex;
      justify-content: space-between;
      align-items: center;
      margin-top: 12px;
    }

    .ayodhya-nav-btn {
      background: var(--saffron);
      color: white;
      border: none;
      padding: 6px 14px;
      border-radius: 15px;
      font-weight: bold;
      cursor: pointer;
      font-size: 0.85rem;
    }

    .ayodhya-nav-btn:disabled {
      background: #ccc;
      cursor: not-allowed;
    }

    .page-indicator {
      font-size: 0.85rem;
      font-weight: bold;
      color: var(--saffron);
    }

    /* Then vs Now Grid */
    .then-now-grid {
      display: grid;
      grid-template-columns: repeat(2, 1fr);
      gap: 15px;
      margin: 20px 0;
    }

    .photo-card {
      background: #fff;
      border-radius: 12px;
      padding: 10px;
      text-align: center;
      box-shadow: 0 4px 12px rgba(0,0,0,0.08);
      border: 1px solid #ffe6ea;
    }

    .photo-card img {
      width: 100%;
      height: 150px;
      object-fit: cover;
      border-radius: 8px;
      margin-bottom: 8px;
    }

    .photo-card span {
      display: block;
      font-weight: bold;
      color: var(--primary);
      font-size: 0.95rem;
    }

    /* Slideshow Gallery */
    .slideshow-container {
      position: relative;
      max-width: 100%;
      margin: 15px auto;
      border-radius: 12px;
      overflow: hidden;
      box-shadow: 0 4px 15px rgba(0,0,0,0.1);
      background: #fff;
    }

    .mySlides {
      display: none;
      text-align: center;
      position: relative;
    }

    .mySlides img {
      width: 100%;
      height: 300px;
      object-fit: cover;
    }

    .slide-caption {
      background: rgba(255, 255, 255, 0.95);
      color: #333;
      font-size: 0.95rem;
      font-weight: 600;
      padding: 10px;
      border-top: 1px solid #ffe6ea;
    }

    .prev, .next {
      cursor: pointer;
      position: absolute;
      top: 45%;
      padding: 10px 14px;
      color: white;
      font-weight: bold;
      font-size: 16px;
      border-radius: 50%;
      background-color: rgba(255, 107, 129, 0.8);
      user-select: none;
      border: none;
    }

    .prev { left: 10px; }
    .next { right: 10px; }

    /* Navigation Bar at Bottom of Slides */
    .nav-controls {
      display: flex;
      justify-content: space-between;
      margin-top: 25px;
      gap: 10px;
    }

    .final-heart {
      font-size: 3rem;
      margin: 15px 0;
      animation: pulse 1.5s infinite;
    }

    /* Animations */
    @keyframes slideInRight {
      from { opacity: 0; transform: translateX(40px); }
      to { opacity: 1; transform: translateX(0); }
    }

    @keyframes fadeIn {
      from { opacity: 0; }
      to { opacity: 1; }
    }

    @keyframes pulse {
      0% { transform: scale(1); }
      50% { transform: scale(1.15); }
      100% { transform: scale(1); }
    }

    /* Confetti Canvas */
    #canvas {
      position: fixed;
      top: 0;
      left: 0;
      width: 100vw;
      height: 100vh;
      pointer-events: none;
      z-index: 99;
    }

    @media (max-width: 480px) {
      .then-now-grid, .calls-grid, .ayodhya-grid { grid-template-columns: 1fr; }
      .mySlides img { height: 220px; }
    }
  </style>
</head>
<body>

  <canvas id="canvas"></canvas>

  <!-- SECTION 1: PASSCODE / LOCK SCREEN -->
  <div id="lock-screen">
    <div class="date-badge">📅 28 July</div>
    <h1>🎉 Happy Birthday, Bhavana! 🎂</h1>
    <p class="signature-tag">From your twinnie, Bhavya 💕</p>
    <p style="color: #666; margin-top: 10px;">A special story is waiting for you inside!</p>
    
    <div class="passcode-input-group">
      <input type="text" id="passcode-field" placeholder="Enter Passcode..." onkeypress="checkEnterKey(event)" />
      
      <!-- Passcode Hint -->
      <p class="hint-text">💡 <b>Hint:</b> Our birth dates, first yours and then mine,it is a four digit passcode</p>
      
      <button class="unlock-btn" onclick="unlockCard()">Unlock Surprise 🎁</button>
      <span class="error-msg" id="error-msg">Oops! Wrong passcode. Try again! 🗝️</span>
    </div>
  </div>

  <!-- SECTION 2: STORY SLIDES -->
  <div class="container" id="main-content">

    <!-- SLIDE 1: WELCOME & MUSIC -->
    <div class="story-slide active-slide" id="slide-1">
      <h1>🎉 Happy Birthday, My Twinnie! 🎈</h1>
      <p class="sub-title">Here’s a little corner of the internet created just for you.</p>

      <div class="music-box">
        <span>🎵 Play our track while you read:</span>
        <button class="music-btn" onclick="toggleAudio('birthday-song', 'audio-btn-1', 'Birds of a Feather')" id="audio-btn-1">▶ Play "Birds of a Feather"</button>
        <audio id="birthday-song" src="C:\Users\DELL\OneDrive\Documents\ht\HT1.mpeg" loop></audio>
      </div>

      <div class="nav-controls" style="justify-content: flex-end;">
        <button class="next-slide-btn" onclick="changeSlide(2)">Next Slide ➔</button>
      </div>
    </div>

    <!-- SLIDE 2: SPECIAL WISH -->
    <div class="story-slide" id="slide-2">
      <h2>💌 A Special Wish</h2>
      
      <div class="wish-text">
        Happy birthday twinnie, ilysm💘!!<br><br>
        May God always bless you with the absolute best because you deserve the besttttt🤍! I truly love the bond that we share and I hope it will always stay the same & always remember your twinnie will always be there for you no matter what💕.
      </div>

      <div class="nav-controls">
        <button class="prev-slide-btn" onclick="changeSlide(1)">❮ Back</button>
        <button class="next-slide-btn" onclick="changeSlide(3)">Next Slide ➔</button>
      </div>
    </div>

    <!-- SLIDE 3: THEN VS NOW -->
    <div class="story-slide" id="slide-3">
      <h2>⏳ Then vs. Now</h2>
      <p style="color: #666;">Look how far you have come! ✨</p>

      <div class="then-now-grid">
        <div class="photo-card">
          <img src="C:\Users\DELL\OneDrive\Documents\ht\WhatsApp_Image_2026-07-26_at_1.26.11_AM_1_1_cropped.jpeg">
          <span>This was you then 👶</span>
        </div>

        <div class="photo-card">
          <img src="C:\Users\DELL\OneDrive\Documents\ht\WhatsApp_Image_2026-07-26_at_1.26.11_AM_2_cropped.jpeg">
          <span>This is you now ✨</span>
        </div>
      </div>

      <div class="nav-controls">
        <button class="prev-slide-btn" onclick="changeSlide(2)">❮ Back</button>
        <button class="next-slide-btn" onclick="changeSlide(4)">Next Slide ➔</button>
      </div>
    </div>

    <!-- SLIDE 4: FAVORITE MEMORIES -->
    <div class="story-slide" id="slide-4">
      <h2>📸 Favorite Memories</h2>

      <div class="slideshow-container">
        <div class="mySlides fade">
          <img src="C:\Users\DELL\OneDrive\Documents\ht\WhatsApp Image 2026-07-26 at 1.39.18 AM.jpeg">
          <div class="slide-caption">Twinnie power! 👯‍♀️</div>
        </div>

        <div class="mySlides fade">
          <img src="C:\Users\DELL\OneDrive\Documents\ht\WhatsApp Image 2026-07-26 at 1.45.37 AM.jpeg">
          <div class="slide-caption">Always matching energy ✨</div>
        </div>

        <div class="mySlides fade">
          <img src="C:\Users\DELL\OneDrive\Documents\ht\WhatsApp Image 2026-07-26 at 1.42.20 AM.jpeg">
          <div class="slide-caption">Best memories together 💖</div>
        </div>
        <button class="prev" onclick="plusSlides(-1)">❮</button>
        <button class="next" onclick="plusSlides(1)">❯</button>
      </div>

      <div class="nav-controls">
        <button class="prev-slide-btn" onclick="changeSlide(3)">❮ Back</button>
        <button class="next-slide-btn" onclick="changeSlide(5)">Next ➔</button>
      </div>
    </div>

    <!-- SLIDE 5: OUR ENDLESS CALLS -->
    <div class="story-slide" id="slide-5">
      <h2>📞 Our Endless Calls</h2>

      <div class="calls-card">
        <p style="font-size: 1rem; line-height: 1.5; color: #555;">
          From talking about everything and nothing at all to late-night gossip and random updates...
        </p>
        <div class="call-time">Hours & Hours of Talk Time 💬✨</div>
      </div>

      <!-- Call Screenshots / Photos Grid -->
      <div class="calls-grid">
        <div class="call-screenshot-card">
          <img src="C:\Users\DELL\OneDrive\Documents\ht\WhatsApp Image 2026-07-26 at 1.51.48 AM.jpeg">
          <span>Random catch-ups 🌙</span>
        </div>

        <div class="call-screenshot-card">
          <img src="C:\Users\DELL\OneDrive\Documents\ht\WhatsApp Image 2026-07-26 at 2.11.26 AM.jpeg">
          <span>Never ending conversations 📞</span>
        </div>
      </div>

      <p style="font-size: 1rem; color: #666; margin-top: 10px;">
        No matter how long we talk, it never feels like enough! 💖
      </p>

      <div class="nav-controls">
        <button class="prev-slide-btn" onclick="changeSlide(4)">❮ Back</button>
        <button class="next-slide-btn" onclick="changeSlide(6)">Next ➔</button>
      </div>
    </div>

    <!-- SLIDE 6: AYODHYA PICS & BLESSINGS -->
    <div class="story-slide" id="slide-6">
      <h2 style="color: var(--saffron);">🚩 The Ayodhya Pics Are Here! 🛕</h2>
      
      <!-- Dedicated Music Player for Ayodhya Slide -->
      <div class="music-box saffron-theme">
        <span style="color: #d35400;">🚩 Play special track for Ayodhya memories:</span>
        <button class="music-btn saffron-btn" onclick="toggleAudio('ayodhya-song', 'audio-btn-6', 'Ayodhya Song')" id="audio-btn-6">▶ Play "Ayodhya Song"</button>
        <audio id="ayodhya-song" src="C:\Users\DELL\OneDrive\Documents\ht\WhatsApp Audio 2026-07-27 at 1.17.40 AM.mpeg" loop></audio>
      </div>

      <div class="ram-blessing-box">
        I thought I'd surprise you with these special memories on your big day! 🧡<br><br>
        <b>May Shri Ram bless you with great health, boundless happiness, peace, and endless good luck always! 🙏✨</b>
      </div>

      <!-- 20-Photo Sub-Slider Box -->
      <div class="ayodhya-slider-wrapper">
        <!-- SUB-PAGE 1 (Photos 1-4) -->
        <div class="ayodhya-page active-page" id="ayodhya-page-1">
          <div class="ayodhya-grid">
            <div class="ayodhya-photo-card"><img src="C:\Users\DELL\OneDrive\Documents\ht\IMG_20260713_100935.jpg.jpeg" alt="Ayodhya 1"></div>
            <div class="ayodhya-photo-card"><img src="C:\Users\DELL\OneDrive\Documents\ht\IMG_20260713_111430.jpg.jpeg" alt="Ayodhya 2"></div>
            <div class="ayodhya-photo-card"><img src="C:\Users\DELL\OneDrive\Documents\ht\IMG_20260713_111941.jpg.jpeg" alt="Ayodhya 3"></div>
            <div class="ayodhya-photo-card"><img src="C:\Users\DELL\OneDrive\Documents\ht\IMG_20260713_110658.jpg.jpeg" alt="Ayodhya 4"></div>
          </div>
        </div>

        <!-- SUB-PAGE 2 (Photos 5-8) -->
        <div class="ayodhya-page" id="ayodhya-page-2">
          <div class="ayodhya-grid">
            <div class="ayodhya-photo-card"><img src="C:\Users\DELL\OneDrive\Documents\ht\IMG_20260713_112153.jpg.jpeg" alt="Ayodhya 5"></div>
            <div class="ayodhya-photo-card"><img src="C:\Users\DELL\OneDrive\Documents\ht\IMG_20260713_112459.jpg.jpeg" alt="Ayodhya 6"></div>
            <div class="ayodhya-photo-card"><img src="C:\Users\DELL\OneDrive\Documents\ht\IMG_20260713_113140.jpg.jpeg" alt="Ayodhya 7"></div>
            <div class="ayodhya-photo-card"><img src="C:\Users\DELL\OneDrive\Documents\ht\IMG_20260713_113213.jpg.jpeg" alt="Ayodhya 8"></div>
          </div>
        </div>

        <!-- SUB-PAGE 3 (Photos 9-12) -->
        <div class="ayodhya-page" id="ayodhya-page-3">
          <div class="ayodhya-grid">
            <div class="ayodhya-photo-card"><img src="C:\Users\DELL\OneDrive\Documents\ht\IMG_20260713_113233.jpg.jpeg" alt="Ayodhya 9"></div>
            <div class="ayodhya-photo-card"><img src="C:\Users\DELL\OneDrive\Documents\ht\IMG_20260713_113315.jpg.jpeg" alt="Ayodhya 10"></div>
            <div class="ayodhya-photo-card"><img src="C:\Users\DELL\OneDrive\Documents\ht\IMG_20260713_113353.jpg.jpeg" alt="Ayodhya 11"></div>
            <div class="ayodhya-photo-card"><img src="C:\Users\DELL\OneDrive\Documents\ht\IMG_20260713_132508.jpg.jpeg" alt="Ayodhya 12"></div>
          </div>
        </div>

        <!-- SUB-PAGE 4 (Photos 13-16) -->
        <div class="ayodhya-page" id="ayodhya-page-4">
          <div class="ayodhya-grid">
            <div class="ayodhya-photo-card"><img src="C:\Users\DELL\OneDrive\Documents\ht\IMG_20260713_133536.jpg.jpeg" alt="Ayodhya 13"></div>
            <div class="ayodhya-photo-card"><img src="C:\Users\DELL\OneDrive\Documents\ht\IMG_20260713_133658.jpg.jpeg" alt="Ayodhya 14"></div>
            <div class="ayodhya-photo-card"><img src="C:\Users\DELL\OneDrive\Documents\ht\IMG_20260713_133716.jpg.jpeg" alt="Ayodhya 15"></div>
            <div class="ayodhya-photo-card"><img src="C:\Users\DELL\OneDrive\Documents\ht\IMG_20260713_133732.jpg.jpeg" alt="Ayodhya 16"></div>
          </div>
        </div>

        <!-- SUB-PAGE 5 (Photos 17-20) -->
        <div class="ayodhya-page" id="ayodhya-page-5">
          <div class="ayodhya-grid">
            <div class="ayodhya-photo-card"><img src="C:\Users\DELL\OneDrive\Documents\ht\IMG_20260713_133741.jpg.jpeg" alt="Ayodhya 17"></div>
            <div class="ayodhya-photo-card"><img src="C:\Users\DELL\OneDrive\Documents\ht\IMG_20260713_134633.jpg.jpeg" alt="Ayodhya 18"></div>
            <div class="ayodhya-photo-card"><img src="C:\Users\DELL\OneDrive\Documents\ht\IMG_20260713_134712.jpg.jpeg" alt="Ayodhya 19"></div>
            <div class="ayodhya-photo-card"><img src="C:\Users\DELL\OneDrive\Documents\ht\IMG_20260713_133935.jpg.jpeg" alt="Ayodhya 20"></div>
          </div>
        </div>

        <!-- Sub-Slider Navigation Controls -->
        <div class="ayodhya-slider-controls">
          <button class="ayodhya-nav-btn" id="ayodhya-prev-btn" onclick="changeAyodhyaPage(-1)" disabled>❮ Prev</button>
          <span class="page-indicator" id="ayodhya-page-num">Batch 1 of 5</span>
          <button class="ayodhya-nav-btn" id="ayodhya-next-btn" onclick="changeAyodhyaPage(1)">Next ➔</button>
        </div>
      </div>

      <div class="nav-controls">
        <button class="prev-slide-btn" onclick="changeSlide(5)">❮ Back</button>
        <button class="next-slide-btn" onclick="changeSlide(7)">Next ➔</button>
      </div>
    </div>

    <!-- SLIDE 7: FINAL MESSAGE -->
    <div class="story-slide" id="slide-7">
      <div class="final-heart">💖</div>
      <h2>Happy Birthday!</h2>
      
      <p style="font-size: 1.2rem; line-height: 1.6; margin: 20px 0; color: #4a4a4a; font-weight: 500;">
        Hope you have an amazing day and a year ahead.<br>
        I love you so much!!!
      </p>

      <h3 style="color: var(--primary); font-size: 1.5rem;">Your twinnie, Bhavya 💕</h3>

      <div class="nav-controls" style="justify-content: center; margin-top: 30px;">
        <button class="prev-slide-btn" onclick="changeSlide(6)">❮ Back</button>
      </div>
    </div>

  </div>

  <!-- Scripts -->
  <script>
    // Allowed Passcodes
    const PASSCODES = ["2821", "two eight two one", "twoeighttwoone"];

    function checkEnterKey(e) {
      if (e.key === 'Enter') {
        unlockCard();
      }
    }

    function unlockCard() {
      const input = document.getElementById('passcode-field').value.trim().toLowerCase();
      const errorMsg = document.getElementById('error-msg');

      if (PASSCODES.includes(input)) {
        document.getElementById('lock-screen').style.display = 'none';
        document.getElementById('main-content').style.display = 'block';
        startConfetti();
        showSlides(slideIndex);
      } else {
        errorMsg.style.display = 'block';
      }
    }

    // Slide Switcher Logic
    function changeSlide(slideNumber) {
      const slides = document.getElementsByClassName('story-slide');
      for (let i = 0; i < slides.length; i++) {
        slides[i].classList.remove('active-slide');
      }
      
      const targetSlide = document.getElementById('slide-' + slideNumber);
      if (targetSlide) {
        targetSlide.classList.add('active-slide');
      }

      // Stop confetti once the user navigates past Slide 2
      if (slideNumber > 2) {
        stopConfetti();
      }
    }

    // Ayodhya Sub-Slider Logic (5 pages, 4 photos each = 20 photos)
    let currentAyodhyaPage = 1;
    const totalAyodhyaPages = 5;

    function changeAyodhyaPage(direction) {
      currentAyodhyaPage += direction;

      if (currentAyodhyaPage < 1) currentAyodhyaPage = 1;
      if (currentAyodhyaPage > totalAyodhyaPages) currentAyodhyaPage = totalAyodhyaPages;

      // Update pages visibility
      const pages = document.getElementsByClassName('ayodhya-page');
      for (let i = 0; i < pages.length; i++) {
        pages[i].classList.remove('active-page');
      }
      document.getElementById('ayodhya-page-' + currentAyodhyaPage).classList.add('active-page');

      // Update indicators and buttons
      document.getElementById('ayodhya-page-num').textContent = `Batch ${currentAyodhyaPage} of ${totalAyodhyaPages}`;
      document.getElementById('ayodhya-prev-btn').disabled = (currentAyodhyaPage === 1);
      document.getElementById('ayodhya-next-btn').disabled = (currentAyodhyaPage === totalAyodhyaPages);
    }

    // Audio Toggle Handler
    function toggleAudio(audioId, btnId, trackName) {
      const audio = document.getElementById(audioId);
      const audioBtn = document.getElementById(btnId);

      // Stop other playing audio elements when one starts
      const allAudios = document.querySelectorAll('audio');
      allAudios.forEach(a => {
        if (a.id !== audioId) {
          a.pause();
        }
      });
      
      // Reset other buttons
      if (btnId !== 'audio-btn-1') {
        document.getElementById('audio-btn-1').textContent = '▶ Play "Birds of a Feather"';
      }
      if (btnId !== 'audio-btn-6') {
        document.getElementById('audio-btn-6').textContent = '▶ Play "Ayodhya Song"';
      }

      if (audio.paused) {
        audio.play().catch(e => console.log("Audio play blocked:", e));
        audioBtn.textContent = '⏸ Pause Song';
      } else {
        audio.pause();
        audioBtn.textContent = `▶ Play "${trackName}"`;
      }
    }

    // Slide 4 Memory Slideshow Logic
    let slideIndex = 1;

    function plusSlides(n) {
      showSlides(slideIndex += n);
    }

    function showSlides(n) {
      let i;
      let slides = document.getElementsByClassName("mySlides");
      if (n > slides.length) {slideIndex = 1}
      if (n < 1) {slideIndex = slides.length}
      for (i = 0; i < slides.length; i++) {
        slides[i].style.display = "none";
      }
      slides[slideIndex-1].style.display = "block";
    }

    // Canvas Confetti Effect Control
    let confettiAnimationId = null;

    function startConfetti() {
      const canvas = document.getElementById('canvas');
      const ctx = canvas.getContext('2d');
      canvas.width = window.innerWidth;
      canvas.height = window.innerHeight;

      let confetti = [];
      const colors = ['#ff6b81', '#ffc048', '#0be881', '#575fcf', '#ef5777'];

      for (let i = 0; i < 70; i++) {
        confetti.push({
          x: Math.random() * canvas.width,
          y: Math.random() * canvas.height - canvas.height,
          color: colors[Math.floor(Math.random() * colors.length)],
          size: Math.random() * 8 + 4,
          speed: Math.random() * 3 + 2,
          angle: Math.random() * 360
        });
      }

      function render() {
        ctx.clearRect(0, 0, canvas.width, canvas.height);
        confetti.forEach((p) => {
          ctx.fillStyle = p.color;
          ctx.beginPath();
          ctx.arc(p.x, p.y, p.size, 0, Math.PI * 2);
          ctx.fill();
          p.y += p.speed;
          if (p.y > canvas.height) p.y = -10;
        });
        confettiAnimationId = requestAnimationFrame(render);
      }
      render();
    }

    function stopConfetti() {
      if (confettiAnimationId) {
        cancelAnimationFrame(confettiAnimationId);
        confettiAnimationId = null;
      }
      const canvas = document.getElementById('canvas');
      const ctx = canvas.getContext('2d');
      ctx.clearRect(0, 0, canvas.width, canvas.height);
    }
  </script>
</body>
</html>
