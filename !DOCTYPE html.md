<!DOCTYPE html>  
<html lang="en">  
<head>  
  <meta charset="UTF-8" />  
  <title>Kiye’s Birthday Garden</title>  
  <meta name="viewport" content="width=device-width, initial-scale=1" />  
  <style>  
    :root {  
      --bg1: #ffe6f2;  
      --bg2: #e6f0ff;  
      --card: #ffffffee;  
      --accent: #ff9ac4;  
      --accent2: #b39dff;  
      --text: #4b3b4f;  
      --soft: #fff7fb;  
    }  
  
    * {  
      box-sizing: border-box;  
      margin: 0;  
      padding: 0;  
      font-family: "Poppins", system-ui, -apple-system, BlinkMacSystemFont, sans-serif;  
    }  
  
    body {  
      background: radial-gradient(circle at top, var(--bg1), var(--bg2));  
      color: var(--text);  
      min-height: 100vh;  
      overflow-x: hidden;  
    }  
  
    /* Simple floating petals */  
    .petal {  
      position: fixed;  
      width: 14px;  
      height: 18px;  
      background: #ffd1e6;  
      border-radius: 50% 50% 50% 0;  
      opacity: 0.7;  
      animation: fall 12s linear infinite;  
      z-index: 0;  
    }  
  
    @keyframes fall {  
      0% {  
        transform: translateY(-10vh) translateX(0) rotate(0deg);  
        opacity: 0;  
      }  
      10% {  
        opacity: 0.7;  
      }  
      100% {  
        transform: translateY(110vh) translateX(40px) rotate(120deg);  
        opacity: 0;  
      }  
    }  
  
    main {  
      position: relative;  
      z-index: 1;  
    }  
  
    section {  
      padding: 60px 16px;  
      max-width: 900px;  
      margin: 0 auto;  
    }  
  
    .card {  
      background: var(--card);  
      border-radius: 24px;  
      padding: 32px 24px;  
      box-shadow: 0 18px 40px rgba(0, 0, 0, 0.08);  
      border: 1px solid #ffe0f0;  
    }  
  
    h1, h2, h3 {  
      font-family: "Dancing Script", "Segoe Script", system-ui;  
      color: #3b2640;  
    }  
  
    h1 {  
      font-size: 2.4rem;  
      margin-bottom: 12px;  
    }  
  
    h2 {  
      font-size: 2rem;  
      margin-bottom: 16px;  
    }  
  
    h3 {  
      font-size: 1.4rem;  
      margin-bottom: 8px;  
    }  
  
    p {  
      line-height: 1.6;  
      margin-bottom: 10px;  
    }  
  
    .center {  
      text-align: center;  
    }  
  
    .btn {  
      display: inline-block;  
      padding: 10px 26px;  
      border-radius: 999px;  
      border: none;  
      background: linear-gradient(135deg, var(--accent), var(--accent2));  
      color: white;  
      font-weight: 600;  
      cursor: pointer;  
      box-shadow: 0 10px 25px rgba(0, 0, 0, 0.18);  
      transition: transform 0.15s ease, box-shadow 0.15s ease;  
      text-decoration: none;  
      margin-top: 16px;  
    }  
  
    .btn:hover {  
      transform: translateY(-2px);  
      box-shadow: 0 14px 30px rgba(0, 0, 0, 0.22);  
    }  
  
    .pill {  
      display: inline-block;  
      padding: 4px 14px;  
      border-radius: 999px;  
      background: #ffeaf6;  
      color: #b34f7a;  
      font-size: 0.8rem;  
      margin-bottom: 10px;  
    }  
  
    .grid {  
      display: grid;  
      gap: 14px;  
    }  
  
    @media (min-width: 700px) {  
      .grid-2 {  
        grid-template-columns: repeat(2, minmax(0, 1fr));  
      }  
      .grid-3 {  
        grid-template-columns: repeat(3, minmax(0, 1fr));  
      }  
    }  
  
    .reason-card, .flower-card, .letter-card, .scrap-card, .quiz-card, .gift-card {  
      background: var(--soft);  
      border-radius: 18px;  
      padding: 14px 14px 16px;  
      border: 1px dashed #ffd0ea;  
      position: relative;  
      overflow: hidden;  
    }  
  
    .reason-card span.num {  
      font-size: 0.8rem;  
      color: #c46a9a;  
      font-weight: 600;  
    }  
  
    .tag {  
      font-size: 0.75rem;  
      background: #f2e9ff;  
      color: #6b4bb3;  
      padding: 3px 10px;  
      border-radius: 999px;  
      display: inline-block;  
      margin-top: 6px;  
    }  
  
    .section-title {  
      margin-bottom: 18px;  
      text-align: center;  
    }  
  
    .section-title p {  
      max-width: 520px;  
      margin: 6px auto 0;  
      font-size: 0.95rem;  
    }  
  
    .hidden {  
      display: none;  
    }  
  
    nav {  
      position: sticky;  
      top: 0;  
      z-index: 5;  
      background: linear-gradient(to right, #ffe6f2ee, #e6f0ffee);  
      backdrop-filter: blur(10px);  
      border-bottom: 1px solid #ffd6ec;  
    }  
  
    nav .nav-inner {  
      max-width: 900px;  
      margin: 0 auto;  
      padding: 8px 16px;  
      display: flex;  
      align-items: center;  
      justify-content: space-between;  
      gap: 10px;  
      font-size: 0.9rem;  
    }  
  
    nav .nav-links {  
      display: flex;  
      flex-wrap: wrap;  
      gap: 6px;  
    }  
  
    nav button {  
      border-radius: 999px;  
      border: none;  
      padding: 4px 10px;  
      background: transparent;  
      cursor: pointer;  
      color: #7a567f;  
      font-size: 0.8rem;  
    }  
  
    nav button:hover {  
      background: #ffeaf6;  
    }  
  
    nav .logo {  
      font-family: "Dancing Script", "Segoe Script";  
      font-size: 1.1rem;  
      color: #b34f7a;  
    }  
  
    .scrap-card {  
      transform: rotate(-1.5deg);  
    }  
  
    .scrap-card:nth-child(2n) {  
      transform: rotate(1.5deg);  
    }  
  
    .scrap-tape {  
      position: absolute;  
      top: -10px;  
      left: 50%;  
      transform: translateX(-50%) rotate(-3deg);  
      width: 80px;  
      height: 22px;  
      background: #ffe9a8;  
      opacity: 0.8;  
      border-radius: 6px;  
    }  
  
    .quiz-option {  
      margin-top: 6px;  
      padding: 6px 10px;  
      border-radius: 999px;  
      border: 1px solid #f3d4ff;  
      font-size: 0.85rem;  
      cursor: pointer;  
      background: white;  
    }  
  
    .quiz-option.correct {  
      background: #e4ffe9;  
      border-color: #8fd39f;  
    }  
  
    .quiz-option.wrong {  
      background: #ffe4e4;  
      border-color: #ff9b9b;  
    }  
  
    .small-note {  
      font-size: 0.8rem;  
      color: #8a6a8f;  
      margin-top: 6px;  
    }  
  
    .footer {  
      text-align: center;  
      font-size: 0.8rem;  
      padding-bottom: 40px;  
      color: #8a6a8f;  
    }  
  </style>  
</head>  
<body>  
  <!-- floating petals -->  
  <script>  
    for (let i = 0; i < 18; i++) {  
      const p = document.createElement("div");  
      p.className = "petal";  
      p.style.left = Math.random() * 100 + "vw";  
      p.style.animationDelay = (Math.random() * 10) + "s";  
      p.style.opacity = 0.4 + Math.random() * 0.4;  
      document.body.appendChild(p);  
    }  
  </script>  
  
  <nav>  
    <div class="nav-inner">  
      <div class="logo">For Kiye ♡</div>  
      <div class="nav-links">  
        <button onclick="scrollToSection('welcome')">Welcome</button>  
        <button onclick="scrollToSection('timeline')">Timeline</button>  
        <button onclick="scrollToSection('reasons')">Reasons</button>  
        <button onclick="scrollToSection('letters')">Letters</button>  
        <button onclick="scrollToSection('flowers')">Flowers</button>  
        <button onclick="scrollToSection('scrapbook')">Scrapbook</button>  
        <button onclick="scrollToSection('quiz')">Quiz</button>  
        <button onclick="scrollToSection('gifts')">Gifts</button>  
        <button onclick="scrollToSection('future')">Future</button>  
      </div>  
    </div>  
  </nav>  
  
  <main>  
    <!-- WELCOME -->  
    <section id="welcome">  
      <div class="card center">  
        <div class="pill">Welcome to your birthday garden</div>  
        <h1>Hi, Kiye… I made something for you.</h1>  
        <p>  
          This little corner of the internet is just for you — full of memories, love,  
          and tiny surprises. Take your time, breathe, and wander through it like a  
          soft, sunny day.  
        </p>  
        <p>  
          I hope this makes you feel as loved as you truly are.  
        </p>  
        <button class="btn" onclick="scrollToSection('timeline')">Enter your garden ✿</button>  
      </div>  
    </section>  
  
    <!-- TIMELINE -->  
    <section id="timeline">  
      <div class="section-title">  
        <h2>Our little timeline</h2>  
        <p>Some of the moments that built “us”. Not all of them, but the ones that still make me smile when I think of you.</p>  
      </div>  
      <div class="card">  
        <div class="grid">  
          <!-- Edit these items with your real memories -->  
          <div class="reason-card">  
            <span class="num">Day 1 · When we met</span>  
            <p>  
              I still remember the first time I saw you: <em>[add where/how you met]</em>.  
              I didn’t know then that you’d become my favourite person.  
            </p>  
          </div>  
          <div class="reason-card">  
            <span class="num">The first inside joke</span>  
            <p>  
              <em>[Describe a funny moment or inside joke]</em> — I swear I still laugh  
              when I think about it.  
            </p>  
          </div>  
          <div class="reason-card">  
            <span class="num">A day you made everything better</span>  
            <p>  
              That time when <em>[she helped you / comforted you]</em>. You probably  
              thought it was small, but it meant so much to me.  
            </p>  
          </div>  
          <div class="reason-card">  
            <span class="num">An iconic memory</span>  
            <p>  
              <em>[Add a chaotic / iconic story]</em>. Peak us. No one else would  
              understand, and that’s what makes it perfect.  
            </p>  
          </div>  
        </div>  
        <p class="small-note">  
          (I could fill a whole book with these, but here are a few pages.)  
        </p>  
      </div>  
    </section>  
  
    <!-- REASONS I LOVE YOU -->  
    <section id="reasons">  
      <div class="section-title">  
        <h2>Reasons I love you</h2>  
        <p>Not all of them, because that would take forever. But here are a few that live rent-free in my heart.</p>  
      </div>  
      <div class="card">  
        <div class="grid grid-3">  
          <!-- Duplicate and edit as many as you want -->  
          <div class="reason-card">  
            <span class="num">01</span>  
            <p>You always notice when my mood shifts, even when I try to hide it.</p>  
          </div>  
          <div class="reason-card">  
            <span class="num">02</span>  
            <p>You make the most ordinary days feel like core memories.</p>  
          </div>  
          <div class="reason-card">  
            <span class="num">03</span>  
            <p>Your laugh is so contagious that I start laughing before I even know why.</p>  
          </div>  
          <div class="reason-card">  
            <span class="num">04</span>  
            <p>You care so deeply about the people you love, even when you’re tired.</p>  
          </div>  
          <div class="reason-card">  
            <span class="num">05</span>  
            <p>You’re brave, even when you don’t feel like it. I see it.</p>  
          </div>  
          <div class="reason-card">  
            <span class="num">06</span>  
            <p>You let me be fully myself, without shrinking or apologising.</p>  
          </div>  
        </div>  
        <p class="small-note">  
          (There are so many more. I’ll keep adding them as we grow up together.)  
        </p>  
      </div>  
    </section>  
  
    <!-- LETTERS FROM FRIENDS -->  
    <section id="letters">  
      <div class="section-title">  
        <h2>Letters from people who love you</h2>  
        <p>Some words from the people whose lives you’ve quietly changed, just by being you.</p>  
      </div>  
      <div class="card">  
        <div class="grid grid-2">  
          <!-- Friend letter 1 -->  
          <div class="letter-card">  
            <h3>From: [Friend 1]</h3>  
            <p>  
              Dear Kiye,<br />  
              <em>[Paste their real letter here]</em><br /><br />  
              Love,<br />  
              [Friend 1]  
            </p>  
          </div>  
          <!-- Friend letter 2 -->  
          <div class="letter-card">  
            <h3>From: [Friend 2]</h3>  
            <p>  
              Dear Kiye,<br />  
              <em>[Paste their real letter here]</em><br /><br />  
              Love,<br />  
              [Friend 2]  
            </p>  
          </div>  
          <!-- Add more letter-card divs as needed -->  
          <div class="letter-card">  
            <h3>From: Naomi ♡</h3>  
            <p>  
              Dear birthday girl,<br />  
              <em>[This is where you write your long, emotional letter to her]</em><br /><br />  
              Love, always,<br />  
              Naomi  
            </p>  
          </div>  
        </div>  
      </div>  
    </section>  
  
    <!-- FLOWER SURPRISE PAGE -->  
    <section id="flowers">  
      <div class="section-title">  
        <h2>Pick a flower</h2>  
        <p>Each flower is a little “open when…” moment. Click one when you need it.</p>  
      </div>  
      <div class="card">  
        <div class="grid grid-2">  
          <div class="flower-card">  
            <h3>🌸 Open when you’re sad</h3>  
            <p>  
              Hey, soft heart. If you’re reading this, I wish I could hug you right now.  
              Please remember: you’ve survived every bad day so far. You are not alone,  
              and you are so, so loved — especially by me.  
            </p>  
          </div>  
          <div class="flower-card">  
            <h3>🌼 Open when you need confidence</h3>  
            <p>  
              You are so much more powerful than you think. The way you care, the way  
              you show up, the way you keep going — that’s strength. I believe in you  
              on the days you don’t believe in yourself.  
            </p>  
          </div>  
          <div class="flower-card">  
            <h3>🌷 Open when you miss me</h3>  
            <p>  
              If we’re not together right now, imagine me sending you the biggest,  
              squishiest hug. I’m still here, still your person, still cheering for you  
              from wherever I am.  
            </p>  
          </div>  
          <div class="flower-card">  
            <h3>🌻 Open when you want to laugh</h3>  
            <p>  
              Remember <em>[insert funny memory / inside joke]</em>? Yeah. That’s us.  
              Chaotic, ridiculous, and perfect. Please never stop being that version of  
              you with me.  
            </p>  
          </div>  
        </div>  
      </div>  
    </section>  
  
    <!-- SCRAPBOOK -->  
    <section id="scrapbook">  
      <div class="section-title">  
        <h2>Scrapbook page</h2>  
        <p>Little polaroids and scribbles from our friendship. Messy on purpose, just like real life.</p>  
      </div>  
      <div class="card">  
        <div class="grid grid-2">  
          <div class="scrap-card">  
            <div class="scrap-tape"></div>  
            <h3>Polaroid #1</h3>  
            <p><em>[Describe a photo of you two here]</em></p>  
            <p class="small-note">Caption: “[your cute caption]”</p>  
          </div>  
          <div class="scrap-card">  
            <div class="scrap-tape"></div>  
            <h3>Polaroid #2</h3>  
            <p><em>[Another memory / photo description]</em></p>  
            <p class="small-note">Caption: “[your cute caption]”</p>  
          </div>  
          <div class="scrap-card">  
            <div class="scrap-tape"></div>  
            <h3>Little doodle</h3>  
            <p>  
              If this page had real paper, it would be full of hearts, stars, and your  
              name written a hundred times.  
            </p>  
          </div>  
          <div class="scrap-card">  
            <div class="scrap-tape"></div>  
            <h3>Note to you</h3>  
            <p>  
              Thank you for being the kind of friend that feels like home. I don’t say  
              it every day, but I think it all the time.  
            </p>  
          </div>  
        </div>  
      </div>  
    </section>  
  
    <!-- QUIZ -->  
    <section id="quiz">  
      <div class="section-title">  
        <h2>Best friend quiz</h2>  
        <p>Let’s see how well you know us 👀 (Spoiler: you’re going to ace this.)</p>  
      </div>  
      <div class="card">  
        <div class="quiz-card">  
          <h3>Q1: My favourite thing about you is…</h3>  
          <div class="quiz-option" onclick="markQuiz(this, true)">The way you make me feel safe</div>  
          <div class="quiz-option" onclick="markQuiz(this, false)">Your ability to eat [funny thing] in one sitting</div>  
          <div class="quiz-option" onclick="markQuiz(this, false)">Your terrible taste in [something]</div>  
        </div>  
        <div class="quiz-card" style="margin-top: 16px;">  
          <h3>Q2: Our most iconic moment is…</h3>  
          <div class="quiz-option" onclick="markQuiz(this, false)">When we were both quiet and normal</div>  
          <div class="quiz-option" onclick="markQuiz(this, true)">When we <em>[insert chaotic story]</em></div>  
          <div class="quiz-option" onclick="markQuiz(this, false)">When we agreed to be serious adults</div>  
        </div>  
        <p class="small-note">  
          (There are no wrong answers really. If it’s with you, it’s iconic.)  
        </p>  
      </div>  
    </section>  
  
    <!-- GIFTS -->  
    <section id="gifts">  
      <div class="section-title">  
        <h2>Digital gift box</h2>  
        <p>A few tiny gifts that live inside this page.</p>  
      </div>  
      <div class="card">  
        <div class="grid grid-2">  
          <div class="gift-card">  
            <h3>🎁 A playlist</h3>  
            <p>  
              <em>[Add a link to a Spotify/YouTube playlist here]</em><br />  
              These are songs that remind me of you, us, and the way you make the world  
              feel softer.  
            </p>  
          </div>  
          <div class="gift-card">  
            <h3>🎁 A poem for you</h3>  
            <p>  
              <em>[Write a short poem here]</em><br />  
              It doesn’t have to be perfect. It just has to be honest.  
            </p>  
          </div>  
          <div class="gift-card">  
            <h3>🎁 A secret message</h3>  
            <p>  
              If you ever doubt your worth, come back to this line: you are one of the  
              best things that has ever happened to me.  
            </p>  
          </div>  
          <div class="gift-card">  
            <h3>🎁 Bonus gift</h3>  
            <p>  
              <em>[You can link to another surprise here: a photo folder, a video, etc.]</em>  
            </p>  
          </div>  
        </div>  
      </div>  
    </section>  
  
    <!-- LETTER TO FUTURE KIYE -->  
    <section id="future">  
      <div class="section-title">  
        <h2>Letter to future you</h2>  
        <p>For the version of you who’s grown a little more, but is still my Kiye.</p>  
      </div>  
      <div class="card">  
        <p>  
          Dear future Kiye,<br /><br />  
          <em>  
            [Write a long, gentle letter here about what you hope for her, how proud  
            you are of her, and how you promise to stay by her side as you both grow.]  
          </em>  
        </p>  
        <p style="margin-top: 16px;">  
          No matter how much changes, I hope you always remember this: you deserve good  
          things, soft days, and people who choose you on purpose. I will always be one  
          of them.  
        </p>  
        <p style="margin-top: 16px;">  
          With all my love,<br />  
          Naomi ♡  
        </p>  
      </div>  
    </section>  
  
    <section>  
      <div class="footer">  
        Made with way too many feelings and a lot of love, just for you, Kiye.  
      </div>  
    </section>  
  </main>  
  
  <script>  
    function scrollToSection(id) {  
      const el = document.getElementById(id);  
      if (!el) return;  
      window.scrollTo({  
        top: el.offsetTop - 70,  
        behavior: "smooth"  
      });  
    }  
  
    function markQuiz(el, isCorrect) {  
      const siblings = el.parentElement.querySelectorAll(".quiz-option");  
      siblings.forEach(s => {  
        s.classList.remove("correct", "wrong");  
      });  
      el.classList.add(isCorrect ? "correct" : "wrong");  
    }  
  </script>  
</body>  
</html>  
  
