<!DOCTYPE html>
<html lang="fr">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>Tes Audios — GM Émotionnel | Vers Ma Sakina</title>
  <link rel="preconnect" href="https://fonts.googleapis.com">
  <link rel="preconnect" href="https://fonts.gstatic.com" crossorigin>
  <link href="https://fonts.googleapis.com/css2?family=Cormorant+Garamond:ital,wght@0,300;0,400;0,600;1,300;1,400&family=Jost:wght@300;400;500&display=swap" rel="stylesheet">

  <style>
    :root {
      --creme:       #F5F0E8;
      --creme-light: #FAF7F2;
      --beige:       #EDE6D6;
      --vert:        #7A9A7A;
      --vert-fonce:  #4A6A4A;
      --vert-clair:  #C8D8C0;
      --brun:        #5C4A3A;
      --brun-clair:  #9A8070;
      --or:          #C4A165;
      --texte:       #3A3020;
      --texte-doux:  #7A6A5A;
    }

    * { margin: 0; padding: 0; box-sizing: border-box; }
    html { scroll-behavior: smooth; }

    body {
      background-color: var(--creme-light);
      color: var(--texte);
      font-family: 'Jost', sans-serif;
      font-weight: 300;
      min-height: 100vh;
      overflow-x: hidden;
    }

    /* ── Fond texturé ── */
    body::before {
      content: '';
      position: fixed;
      inset: 0;
      background-image:
        radial-gradient(ellipse at 20% 20%, rgba(122,154,122,0.08) 0%, transparent 50%),
        radial-gradient(ellipse at 80% 80%, rgba(196,161,101,0.06) 0%, transparent 50%),
        url("data:image/svg+xml,%3Csvg width='200' height='200' xmlns='http://www.w3.org/2000/svg'%3E%3Cfilter id='n'%3E%3CfeTurbulence type='fractalNoise' baseFrequency='0.75' numOctaves='4' stitchTiles='stitch'/%3E%3C/filter%3E%3Crect width='200' height='200' filter='url(%23n)' opacity='0.025'/%3E%3C/svg%3E");
      pointer-events: none;
      z-index: 0;
    }

    /* ── Header ── */
    header {
      position: relative;
      z-index: 1;
      padding: 3rem 2rem 2rem;
      text-align: center;
      border-bottom: 1px solid rgba(122,154,122,0.2);
    }

    .logo-text {
      font-family: 'Cormorant Garamond', serif;
      font-size: 0.85rem;
      font-weight: 300;
      letter-spacing: 0.35em;
      text-transform: uppercase;
      color: var(--vert);
      margin-bottom: 0.5rem;
    }

    .ornement {
      display: flex;
      align-items: center;
      justify-content: center;
      gap: 1rem;
      margin: 0.8rem 0;
    }

    .ornement-line {
      width: 60px;
      height: 1px;
      background: linear-gradient(90deg, transparent, var(--or), transparent);
    }

    .ornement-dot {
      width: 5px;
      height: 5px;
      border-radius: 50%;
      background: var(--or);
    }

    /* ── Hero ── */
    .hero {
      position: relative;
      z-index: 1;
      padding: 4rem 2rem 3rem;
      text-align: center;
      max-width: 680px;
      margin: 0 auto;
    }

    .hero-tag {
      display: inline-block;
      font-family: 'Jost', sans-serif;
      font-size: 0.7rem;
      font-weight: 500;
      letter-spacing: 0.3em;
      text-transform: uppercase;
      color: var(--vert);
      background: rgba(122,154,122,0.1);
      border: 1px solid rgba(122,154,122,0.25);
      padding: 0.4rem 1.2rem;
      border-radius: 100px;
      margin-bottom: 1.8rem;
    }

    .hero h1 {
      font-family: 'Cormorant Garamond', serif;
      font-size: clamp(2.2rem, 6vw, 3.4rem);
      font-weight: 300;
      line-height: 1.15;
      color: var(--brun);
      margin-bottom: 1.2rem;
    }

    .hero h1 em {
      font-style: italic;
      color: var(--vert-fonce);
    }

    .hero p {
      font-size: 1rem;
      line-height: 1.8;
      color: var(--texte-doux);
      max-width: 480px;
      margin: 0 auto 2rem;
    }

    /* ── Sections ── */
    .section {
      position: relative;
      z-index: 1;
      max-width: 760px;
      margin: 0 auto;
      padding: 0 1.5rem 4rem;
    }

    .section-title {
      font-family: 'Cormorant Garamond', serif;
      font-size: 1.5rem;
      font-weight: 400;
      color: var(--brun);
      text-align: center;
      margin-bottom: 0.5rem;
    }

    .section-subtitle {
      font-size: 0.8rem;
      letter-spacing: 0.2em;
      text-transform: uppercase;
      color: var(--vert);
      text-align: center;
      margin-bottom: 2.5rem;
    }

    /* ── Carte audio ── */
    .audio-grid {
      display: flex;
      flex-direction: column;
      gap: 1.2rem;
    }

    .audio-card {
      background: var(--creme-light);
      border: 1px solid rgba(122,154,122,0.2);
      border-radius: 16px;
      padding: 1.8rem;
      transition: box-shadow 0.3s ease, transform 0.3s ease;
      position: relative;
      overflow: hidden;
    }

    .audio-card::before {
      content: '';
      position: absolute;
      top: 0;
      left: 0;
      width: 4px;
      height: 100%;
      background: linear-gradient(180deg, var(--vert), var(--or));
      border-radius: 4px 0 0 4px;
    }

    .audio-card:hover {
      box-shadow: 0 8px 32px rgba(74,106,74,0.12);
      transform: translateY(-2px);
    }

    .audio-header {
      display: flex;
      align-items: flex-start;
      gap: 1.2rem;
      margin-bottom: 1.2rem;
    }

    .audio-number {
      flex-shrink: 0;
      width: 44px;
      height: 44px;
      border-radius: 50%;
      background: linear-gradient(135deg, var(--vert), var(--vert-fonce));
      display: flex;
      align-items: center;
      justify-content: center;
      font-family: 'Cormorant Garamond', serif;
      font-size: 1.1rem;
      color: white;
      font-weight: 400;
    }

    .audio-info { flex: 1; }

    .audio-badge {
      display: inline-block;
      font-size: 0.65rem;
      font-weight: 500;
      letter-spacing: 0.2em;
      text-transform: uppercase;
      color: var(--or);
      margin-bottom: 0.3rem;
    }

    .audio-title {
      font-family: 'Cormorant Garamond', serif;
      font-size: 1.25rem;
      font-weight: 400;
      color: var(--brun);
      line-height: 1.2;
      margin-bottom: 0.3rem;
    }

    .audio-duree {
      font-size: 0.75rem;
      color: var(--texte-doux);
      letter-spacing: 0.05em;
    }

    .audio-desc {
      font-size: 0.9rem;
      line-height: 1.7;
      color: var(--texte-doux);
      margin-bottom: 1.2rem;
      padding-left: calc(44px + 1.2rem);
    }

    /* ── Lecteur audio custom ── */
    .player-wrapper {
      padding-left: calc(44px + 1.2rem);
    }

    .custom-player {
      background: var(--beige);
      border-radius: 12px;
      padding: 1rem 1.2rem;
      display: flex;
      align-items: center;
      gap: 1rem;
    }

    .play-btn {
      flex-shrink: 0;
      width: 40px;
      height: 40px;
      border-radius: 50%;
      background: var(--vert-fonce);
      border: none;
      cursor: pointer;
      display: flex;
      align-items: center;
      justify-content: center;
      transition: background 0.2s, transform 0.15s;
    }

    .play-btn:hover { background: var(--vert); transform: scale(1.05); }

    .play-btn svg { width: 16px; height: 16px; fill: white; }

    .player-controls { flex: 1; }

    .progress-bar {
      width: 100%;
      height: 4px;
      background: rgba(122,154,122,0.2);
      border-radius: 4px;
      cursor: pointer;
      margin-bottom: 0.5rem;
      position: relative;
    }

    .progress-fill {
      height: 100%;
      background: linear-gradient(90deg, var(--vert), var(--or));
      border-radius: 4px;
      width: 0%;
      transition: width 0.1s linear;
      pointer-events: none;
    }

    .time-row {
      display: flex;
      justify-content: space-between;
      font-size: 0.7rem;
      color: var(--texte-doux);
    }

    /* ── Séparateur de section ── */
    .section-divider {
      position: relative;
      z-index: 1;
      text-align: center;
      margin: 1rem auto 3rem;
      max-width: 300px;
    }

    .section-divider::before {
      content: '';
      display: block;
      width: 100%;
      height: 1px;
      background: linear-gradient(90deg, transparent, var(--beige), transparent);
      margin-bottom: 1rem;
    }

    /* ── Footer ── */
    footer {
      position: relative;
      z-index: 1;
      background: var(--brun);
      color: rgba(245,240,232,0.7);
      text-align: center;
      padding: 2.5rem 2rem;
    }

    footer .footer-logo {
      font-family: 'Cormorant Garamond', serif;
      font-size: 1.3rem;
      color: var(--creme);
      margin-bottom: 0.5rem;
      font-weight: 300;
      letter-spacing: 0.1em;
    }

    footer p {
      font-size: 0.8rem;
      line-height: 1.7;
      margin-bottom: 0.3rem;
    }

    footer a {
      color: var(--vert-clair);
      text-decoration: none;
    }

    footer a:hover { text-decoration: underline; }

    /* ── Animations ── */
    @keyframes fadeUp {
      from { opacity: 0; transform: translateY(20px); }
      to   { opacity: 1; transform: translateY(0); }
    }

    .hero { animation: fadeUp 0.8s ease both; }
    .audio-card { animation: fadeUp 0.6s ease both; }
    .audio-card:nth-child(1) { animation-delay: 0.1s; }
    .audio-card:nth-child(2) { animation-delay: 0.2s; }
    .audio-card:nth-child(3) { animation-delay: 0.3s; }
    .audio-card:nth-child(4) { animation-delay: 0.4s; }
    .audio-card:nth-child(5) { animation-delay: 0.5s; }

    /* ── Responsive ── */
    @media (max-width: 600px) {
      .audio-desc,
      .player-wrapper { padding-left: 0; }
      .audio-header { flex-direction: row; }
    }
  </style>
</head>
<body>

  <!-- HEADER -->
  <header>
    <p class="logo-text">Vers Ma Sakina</p>
    <div class="ornement">
      <div class="ornement-line"></div>
      <div class="ornement-dot"></div>
      <div class="ornement-line"></div>
    </div>
  </header>

  <!-- HERO -->
  <div class="hero">
    <span class="hero-tag">🎧 Tes audios d'accompagnement</span>
    <h1>Générateur-Manifesteur<br><em>Émotionnel</em></h1>
    <p>Bienvenue dans ton espace sonore. Ces audios sont conçus pour accompagner chaque étape de ton livret. Mets tes écouteurs, installe-toi confortablement, et laisse-toi guider.</p>
  </div>

  <!-- SECTION AUDIOS PRINCIPAUX -->
  <div class="section">
    <p class="section-subtitle">Chapitre 1</p>
    <h2 class="section-title">Les 5 audios du livret</h2>

    <div class="audio-grid">

      <!-- AUDIO 1 -->
      <div class="audio-card" id="card-1">
        <div class="audio-header">
          <div class="audio-number">1</div>
          <div class="audio-info">
            <span class="audio-badge">Bienvenu</span>
            <h3 class="audio-title">Bienvenu dans ton univers</h3>
            <span class="audio-duree">⏱ 3–4 min</span>
          </div>
        </div>
        <p class="audio-desc">Le point de départ de ton voyage. Julie t'accueille et t'explique comment utiliser ce livret pour en tirer le maximum.</p>
        <div class="player-wrapper">
          <div class="custom-player" data-audio="audio1">
            <button class="play-btn" onclick="togglePlay('audio1')">
              <svg viewBox="0 0 24 24"><path d="M8 5v14l11-7z"/></svg>
            </button>
            <div class="player-controls">
              <div class="progress-bar" onclick="seek(event, 'audio1')">
                <div class="progress-fill" id="fill-audio1"></div>
              </div>
              <div class="time-row">
                <span id="cur-audio1">0:00</span>
                <span id="dur-audio1">--:--</span>
              </div>
            </div>
            <audio id="audio1" src="audios/01-bienvenu.mp3" preload="none"></audio>
          </div>
        </div>
      </div>

      <!-- AUDIO 2 -->
      <div class="audio-card" id="card-2">
        <div class="audio-header">
          <div class="audio-number">2</div>
          <div class="audio-info">
            <span class="audio-badge">Méditation</span>
            <h3 class="audio-title">Connexion à ton sacral</h3>
            <span class="audio-duree">⏱ 5–6 min</span>
          </div>
        </div>
        <p class="audio-desc">Une méditation guidée pour apprendre à ressentir et reconnaître les réponses de ton centre sacral — avant de remplir ton premier tableau.</p>
        <div class="player-wrapper">
          <div class="custom-player" data-audio="audio2">
            <button class="play-btn" onclick="togglePlay('audio2')">
              <svg viewBox="0 0 24 24"><path d="M8 5v14l11-7z"/></svg>
            </button>
            <div class="player-controls">
              <div class="progress-bar" onclick="seek(event, 'audio2')">
                <div class="progress-fill" id="fill-audio2"></div>
              </div>
              <div class="time-row">
                <span id="cur-audio2">0:00</span>
                <span id="dur-audio2">--:--</span>
              </div>
            </div>
            <audio id="audio2" src="audios/02-connexionsacrale.mp3" preload="none"></audio>
          </div>
        </div>
      </div>

      <!-- AUDIO 3 -->
      <div class="audio-card" id="card-3">
        <div class="audio-header">
          <div class="audio-number">3</div>
          <div class="audio-info">
            <span class="audio-badge">Non-soi</span>
            <h3 class="audio-title">Accueillir le non-soi</h3>
            <span class="audio-duree">⏱ 4–5 min</span>
          </div>
        </div>
        <p class="audio-desc">Un espace de douceur et de pardon. Pour intégrer, sans te juger, les moments où tu t'es éloigné·e de toi-même.</p>
        <div class="player-wrapper">
          <div class="custom-player" data-audio="audio3">
            <button class="play-btn" onclick="togglePlay('audio3')">
              <svg viewBox="0 0 24 24"><path d="M8 5v14l11-7z"/></svg>
            </button>
            <div class="player-controls">
              <div class="progress-bar" onclick="seek(event, 'audio3')">
                <div class="progress-fill" id="fill-audio3"></div>
              </div>
              <div class="time-row">
                <span id="cur-audio3">0:00</span>
                <span id="dur-audio3">--:--</span>
              </div>
            </div>
            <audio id="audio3" src="audios/03-nonsoi.mp3" preload="none"></audio>
          </div>
        </div>
      </div>

      <!-- AUDIO 4 -->
      <div class="audio-card" id="card-4">
        <div class="audio-header">
          <div class="audio-number">4</div>
          <div class="audio-info">
            <span class="audio-badge">Autorité</span>
            <h3 class="audio-title">Observer ta vague émotionnelle</h3>
            <span class="audio-duree">⏱ 5–6 min</span>
          </div>
        </div>
        <p class="audio-desc">Apprends à identifier où tu en es dans ta vague, et à reconnaître le bon moment pour prendre tes décisions importantes.</p>
        <div class="player-wrapper">
          <div class="custom-player" data-audio="audio4">
            <button class="play-btn" onclick="togglePlay('audio4')">
              <svg viewBox="0 0 24 24"><path d="M8 5v14l11-7z"/></svg>
            </button>
            <div class="player-controls">
              <div class="progress-bar" onclick="seek(event, 'audio4')">
                <div class="progress-fill" id="fill-audio4"></div>
              </div>
              <div class="time-row">
                <span id="cur-audio4">0:00</span>
                <span id="dur-audio4">--:--</span>
              </div>
            </div>
            <audio id="audio4" src="audios/04-vague.mp3" preload="none"></audio>
          </div>
        </div>
      </div>

      <!-- AUDIO 5 -->
      <div class="audio-card" id="card-5">
        <div class="audio-header">
          <div class="audio-number">5</div>
          <div class="audio-info">
            <span class="audio-badge">Clôture</span>
            <h3 class="audio-title">Clôture & encouragement</h3>
            <span class="audio-duree">⏱ 4–5 min</span>
          </div>
        </div>
        <p class="audio-desc">Un dernier moment avec Julie pour célébrer le chemin parcouru et t'encourager à continuer à t'écouter.</p>
        <div class="player-wrapper">
          <div class="custom-player" data-audio="audio5">
            <button class="play-btn" onclick="togglePlay('audio5')">
              <svg viewBox="0 0 24 24"><path d="M8 5v14l11-7z"/></svg>
            </button>
            <div class="player-controls">
              <div class="progress-bar" onclick="seek(event, 'audio5')">
                <div class="progress-fill" id="fill-audio5"></div>
              </div>
              <div class="time-row">
                <span id="cur-audio5">0:00</span>
                <span id="dur-audio5">--:--</span>
              </div>
            </div>
            <audio id="audio5" src="audios/05-cloture.mp3" preload="none"></audio>
          </div>
        </div>
      </div>

    </div>
  </div>

  <!-- SÉPARATEUR -->
  <div class="section-divider">
    <div class="ornement">
      <div class="ornement-line"></div>
      <div class="ornement-dot"></div>
      <div class="ornement-line"></div>
    </div>
  </div>

  <!-- FOOTER -->
  <footer>
    <p class="footer-logo">Vers Ma Sakina</p>
    <div class="ornement" style="justify-content:center; margin: 0.8rem 0;">
      <div class="ornement-line" style="background: linear-gradient(90deg, transparent, rgba(245,240,232,0.3), transparent);"></div>
      <div class="ornement-dot" style="background: rgba(245,240,232,0.4);"></div>
      <div class="ornement-line" style="background: linear-gradient(90deg, transparent, rgba(245,240,232,0.3), transparent);"></div>
    </div>
    <p>© 2026 Julie Galland-Herrero · Tous droits réservés</p>
    <p><a href="mailto:julie@versmasakina.fr">julie@versmasakina.fr</a></p>
    <p style="margin-top:0.8rem; font-size:0.75rem; opacity:0.5;">
      Ces audios sont réservés aux acheteurs du livret.<br>
      Merci de ne pas les partager.
    </p>
  </footer>

  <script>
    // ── Lecteur audio custom ──────────────────────────────────────
    const players = {};

    function togglePlay(id) {
      const audio = document.getElementById(id);
      if (!audio) return;

      // Met en pause tous les autres
      Object.keys(players).forEach(pid => {
        if (pid !== id && players[pid]) {
          players[pid].pause();
          updateBtn(pid, false);
        }
      });

      players[id] = audio;

      if (audio.paused) {
        audio.play();
        updateBtn(id, true);
      } else {
        audio.pause();
        updateBtn(id, false);
      }
    }

    function updateBtn(id, playing) {
      const btn = document.querySelector(`[onclick="togglePlay('${id}')"] svg`);
      if (!btn) return;
      btn.innerHTML = playing
        ? '<path d="M6 19h4V5H6v14zm8-14v14h4V5h-4z"/>'  // pause
        : '<path d="M8 5v14l11-7z"/>';                       // play
    }

    function seek(e, id) {
      const audio = document.getElementById(id);
      if (!audio || !audio.duration) return;
      const bar = e.currentTarget;
      const ratio = (e.clientX - bar.getBoundingClientRect().left) / bar.offsetWidth;
      audio.currentTime = ratio * audio.duration;
    }

    function formatTime(s) {
      if (isNaN(s)) return '--:--';
      const m = Math.floor(s / 60);
      const sec = Math.floor(s % 60);
      return `${m}:${sec.toString().padStart(2, '0')}`;
    }

    // Update progress bars
    document.querySelectorAll('audio').forEach(audio => {
      const id = audio.id;
      audio.addEventListener('timeupdate', () => {
        const fill = document.getElementById(`fill-${id}`);
        const cur = document.getElementById(`cur-${id}`);
        if (fill && audio.duration) fill.style.width = (audio.currentTime / audio.duration * 100) + '%';
        if (cur) cur.textContent = formatTime(audio.currentTime);
      });
      audio.addEventListener('loadedmetadata', () => {
        const dur = document.getElementById(`dur-${id}`);
        if (dur) dur.textContent = formatTime(audio.duration);
      });
      audio.addEventListener('ended', () => updateBtn(id, false));
    });
  </script>

</body>
</html>
