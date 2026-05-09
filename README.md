<!DOCTYPE html>
<html lang="ar">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>For Lynna ❤️</title>
<link href="https://fonts.googleapis.com/css2?family=Pacifico&family=Poppins:wght@300;400;600&display=swap" rel="stylesheet">
<style>
* { margin: 0; padding: 0; box-sizing: border-box; }

body {
  min-height: 100vh;
  display: flex;
  align-items: center;
  justify-content: center;
  font-family: 'Poppins', sans-serif;
  background: radial-gradient(ellipse at top, #ff80ab 0%, #ff4081 40%, #f50057 100%);
  overflow: hidden;
  cursor: crosshair;
  text-align: center;
  position: relative;
}

/* ── ambient floating hearts ── */
.ambient {
  position: fixed; inset: 0;
  pointer-events: none; z-index: 0;
}
.amb-heart {
  position: absolute;
  bottom: -60px;
  font-size: var(--fs);
  opacity: 0;
  animation: ambRise var(--dur) ease-in var(--dl) infinite;
  filter: drop-shadow(0 0 6px rgba(255,80,120,0.7));
}
@keyframes ambRise {
  0%   { transform: translateY(0) scale(0.8) rotate(var(--rot)); opacity: 0; }
  10%  { opacity: 0.9; }
  90%  { opacity: 0.4; }
  100% { transform: translateY(-110vh) scale(1.4) rotate(calc(var(--rot) + 40deg)); opacity: 0; }
}

/* ── click hearts ── */
.heart {
  position: fixed;
  pointer-events: none;
  z-index: 9999;
  font-size: var(--fs, 24px);
  animation: clickFly var(--dur, 2.2s) ease-out forwards;
  filter: drop-shadow(0 0 8px rgba(255,50,100,0.9));
}
@keyframes clickFly {
  0%   { transform: translateY(0) scale(1) rotate(var(--rot,0deg));   opacity: 1; }
  60%  { opacity: 1; }
  100% { transform: translateY(-220px) scale(1.6) rotate(calc(var(--rot,0deg) + 60deg)); opacity: 0; }
}

/* ── card ── */
.container {
  position: relative; z-index: 10;
  background: rgba(255,255,255,0.92);
  backdrop-filter: blur(16px);
  padding: 52px 44px 44px;
  border-radius: 32px;
  max-width: 440px; width: 90vw;
  box-shadow:
    0 0 0 2px rgba(255,64,129,0.25),
    0 20px 70px rgba(245,0,87,0.35),
    0 0 120px rgba(255,128,171,0.4);
  animation: cardPop 1s cubic-bezier(0.34,1.56,0.64,1) forwards;
  transform: scale(0.5) translateY(60px); opacity: 0;
}
@keyframes cardPop { to { transform: scale(1) translateY(0); opacity: 1; } }

/* corner sparkles */
.sparkle {
  position: absolute; font-size: 1.4rem;
  animation: sparkSpin 4s linear infinite;
}
.sparkle.tl { top: 12px; left: 14px; }
.sparkle.tr { top: 12px; right: 14px; }
.sparkle.bl { bottom: 12px; left: 14px; }
.sparkle.br { bottom: 12px; right: 14px; }
@keyframes sparkSpin {
  0%,100% { transform: scale(1) rotate(0deg);   opacity: 0.7; }
  50%      { transform: scale(1.3) rotate(180deg); opacity: 1; }
}

/* name */
.name {
  font-family: 'Pacifico', cursive;
  font-size: 3rem;
  color: #f50057;
  text-shadow: 0 3px 20px rgba(245,0,87,0.3);
  animation: namePulse 2s ease-in-out infinite alternate;
  margin-bottom: 6px;
}
@keyframes namePulse {
  from { text-shadow: 0 3px 16px rgba(245,0,87,0.25); }
  to   { text-shadow: 0 3px 36px rgba(255,64,129,0.7); }
}

.intro {
  font-size: 1rem; color: #c2185b;
  margin-bottom: 4px; font-weight: 300;
}

.question {
  font-family: 'Pacifico', cursive;
  font-size: 1.6rem; color: #ad1457;
  margin-bottom: 6px;
}

.hint {
  font-size: 0.78rem; color: #f48fb1;
  font-style: italic; margin-bottom: 24px;
}

/* divider */
.divider {
  display: flex; align-items: center; gap: 8px;
  margin: 0 auto 26px; max-width: 260px;
}
.dline { flex:1; height:1px; background: linear-gradient(90deg,transparent,#f48fb1,transparent); }
.dgem { color: #f50057; font-size: 1rem; }

/* buttons */
.buttons {
  display: flex; justify-content: center; gap: 16px;
  align-items: center; flex-wrap: wrap; min-height: 56px;
}

#yesBtn {
  font-family: 'Poppins', sans-serif;
  font-size: 1.1rem; font-weight: 600;
  padding: 14px 40px; border: none; border-radius: 50px;
  cursor: pointer;
  background: linear-gradient(135deg, #ff4081, #f50057);
  color: white;
  box-shadow: 0 6px 24px rgba(245,0,87,0.5);
  transition: transform 0.15s, box-shadow 0.15s;
  animation: yesPulse 1.8s ease-in-out infinite;
}
@keyframes yesPulse {
  0%,100% { box-shadow: 0 6px 24px rgba(245,0,87,0.5); }
  50%      { box-shadow: 0 6px 38px rgba(245,0,87,0.8); }
}
#yesBtn:hover { transform: scale(1.1); }
#yesBtn:active { transform: scale(0.95); }

#noBtn {
  font-family: 'Poppins', sans-serif;
  font-size: 1rem;
  padding: 12px 26px; border: 2px solid #f48fb1;
  border-radius: 50px; cursor: pointer;
  background: white; color: #e91e8c;
  transition: font-size 0.3s, padding 0.3s;
  white-space: nowrap;
}
#noBtn:hover { background: #fff0f5; }

.taunt {
  font-size: 0.78rem; color: #e91e8c;
  margin-top: 10px; min-height: 18px;
  font-style: italic; opacity: 0;
  transition: opacity 0.4s;
}
.taunt.show { opacity: 1; }

/* ── win screen ── */
#winScreen {
  display: none;
  flex-direction: column;
  align-items: center;
  gap: 16px;
}
#winScreen.show { display: flex; animation: cardPop 0.8s cubic-bezier(0.34,1.56,0.64,1); }

.win-emoji { font-size: 4rem; animation: sparkSpin 3s linear infinite; }

.win-title {
  font-family: 'Pacifico', cursive;
  font-size: 1.9rem; color: #f50057;
  text-shadow: 0 2px 20px rgba(245,0,87,0.4);
}

.win-msg {
  font-size: 0.95rem; color: #ad1457; line-height: 1.8;
}

.win-hearts { font-size: 2rem; letter-spacing: 6px; animation: namePulse 1.5s ease-in-out infinite alternate; }

/* developer tag */
.developer {
  position: fixed; bottom: 14px; left: 50%; transform: translateX(-50%);
  font-size: 0.72rem; font-weight: 600; letter-spacing: 2px;
  color: rgba(255,255,255,0.65);
  text-transform: uppercase; z-index: 20;
  text-shadow: 0 1px 8px rgba(0,0,0,0.3);
}
.developer span { color: #fff; letter-spacing: 3px; }
</style>
</head>
<body>

<!-- ambient hearts layer -->
<div class="ambient" id="ambient"></div>

<div class="container" id="card">
  <span class="sparkle tl">✨</span>
  <span class="sparkle tr">🌸</span>
  <span class="sparkle bl">🌸</span>
  <span class="sparkle br">✨</span>

  <!-- QUESTION -->
  <div id="main">
    <div class="name">A Lynna… ❤️</div>
    <p class="intro">Bghit nswlk wahed lhajja…</p>
    <p class="question">Wash katbghini? 🥺</p>
    <p class="hint">(click anywhere for hearts 💕)</p>

    <div class="divider">
      <div class="dline"></div><div class="dgem">♥</div><div class="dline"></div>
    </div>

    <div class="buttons">
      <button id="yesBtn" onclick="celebrate()">Ah, Kanbghik! 💕</button>
      <button id="noBtn" onmouseover="moveButton()" onclick="pressedNo()">Lae 🙈</button>
    </div>
    <p class="taunt" id="taunt"></p>
  </div>

  <!-- WIN -->
  <div id="winScreen">
    <div class="win-emoji">💍✨💍</div>
    <div class="win-title">Hhhh ana 3aref! ❤️</div>
    <p class="win-msg">
      Hta ana kanbghik bzaaaf a Lynna!<br>
      <strong>Daba ma3endekch haq tghrbi 😄</strong>
    </p>
    <video id="loveVideo" src="W88iOja.mp4" autoplay playsinline loop
      style="width:100%;max-width:340px;border-radius:18px;margin-top:8px;box-shadow:0 8px 32px rgba(245,0,87,0.4);"></video>
    <div class="win-hearts">💕 🌸 💕 🌸 💕</div>
  </div>
</div>

<div class="developer">Dev by <span>XINN</span></div>

<script>
/* ── Ambient floating hearts ── */
const ambEl   = document.getElementById('ambient');
const ambs    = ['❤️','💕','💖','💗','🌸','💓','🩷','💞'];
const ambSizes= ['1rem','1.3rem','1.7rem','0.85rem','2rem','1.1rem'];

for (let i = 0; i < 28; i++) {
  const h = document.createElement('div');
  h.className = 'amb-heart';
  h.textContent = ambs[i % ambs.length];
  const rot = (Math.random() * 60 - 30).toFixed(0) + 'deg';
  h.style.cssText = `
    left:${(Math.random()*100).toFixed(1)}%;
    --fs:${ambSizes[i % ambSizes.length]};
    --dur:${(Math.random()*7+5).toFixed(1)}s;
    --dl:${(Math.random()*12).toFixed(1)}s;
    --rot:${rot}`;
  ambEl.appendChild(h);
}

/* ── Click / tap hearts ── */
const clickEmojis = ['❤️','💕','💖','💗','🩷','💞','🌸','✨'];
document.body.addEventListener('click', e => {
  if (e.target.closest('button')) return;
  for (let i = 0; i < 5; i++) {
    setTimeout(() => spawnClickHeart(e.clientX, e.clientY), i * 60);
  }
});

function spawnClickHeart(x, y) {
  const el = document.createElement('div');
  el.className = 'heart';
  el.textContent = clickEmojis[Math.floor(Math.random() * clickEmojis.length)];
  const sz = Math.floor(Math.random() * 20 + 18);
  const rot = (Math.random() * 60 - 30).toFixed(0) + 'deg';
  const dur = (Math.random() * 0.8 + 1.6).toFixed(2);
  const ox  = (Math.random() * 60 - 30).toFixed(0);
  el.style.cssText = `left:${x + parseInt(ox)}px;top:${y}px;--fs:${sz}px;--dur:${dur}s;--rot:${rot};transform-origin:center`;
  document.body.appendChild(el);
  setTimeout(() => el.remove(), parseFloat(dur) * 1000 + 100);
}

/* ── No button ── */
let noCount = 0;
const noBtn   = document.getElementById('noBtn');
const tauntEl = document.getElementById('taunt');

const taunts = [
  "Are you sure?? 🤨",
  "Like… really sure? 🧐",
  "Think again bestie 😤",
  "That's not the right answer 😭",
  "Wach m9awed?? 😏",
  "Aji men hna! 😂",
  "Ma kayn ghir Ah! 🥺",
  "Your heart says YES 💕",
  "Try the other button 👀",
  "Noooo come back!! 😩",
  "This button is broken btw 🙃",
  "It's getting smaller… 👀",
  "Last chance… probably 😅",
  "Okay fine… jk NEVER 😄"
];

// Minimum font size — tiny but still technically pressable (just impossible 😈)
const MIN_FS = 6;

function pressedNo() {
  noCount++;
  // Shrink font
  const cur = parseFloat(getComputedStyle(noBtn).fontSize);
  const newFs = Math.max(cur * 0.76, MIN_FS);
  noBtn.style.fontSize = newFs + 'px';
  // Shrink padding proportionally
  const pv = Math.max(12 - noCount * 1.4, 1);
  const ph = Math.max(26 - noCount * 3,   2);
  noBtn.style.padding = `${pv}px ${ph}px`;
  // Cycle taunts (loop if needed)
  const msg = taunts[(noCount - 1) % taunts.length];
  tauntEl.textContent = msg;
  tauntEl.classList.add('show');
  // Always flee on click
  moveButton();
}

function moveButton() {
  if (noBtn.style.position !== 'fixed') {
    noBtn.style.position = 'fixed';
    noBtn.style.zIndex = '999';
    noBtn.style.transition = 'left 0.18s ease, top 0.18s ease, font-size 0.3s, padding 0.3s';
  }
  const bw = noBtn.offsetWidth  || 60;
  const bh = noBtn.offsetHeight || 30;
  const pad = 10;
  const maxX = window.innerWidth  - bw - pad;
  const maxY = window.innerHeight - bh - pad;
  noBtn.style.left = (Math.random() * (maxX - pad) + pad) + 'px';
  noBtn.style.top  = (Math.random() * (maxY - pad) + pad) + 'px';
}

// Flee on cursor/touch approach — proximity shrinks as button gets smaller
document.addEventListener('mousemove', e => {
  if (noCount < 1) return;
  const r = noBtn.getBoundingClientRect();
  const proximity = Math.max(130 - noCount * 6, 60);
  if (Math.hypot(e.clientX - r.left - r.width/2, e.clientY - r.top - r.height/2) < proximity) moveButton();
});
document.addEventListener('touchmove', e => {
  if (noCount < 1) return;
  const t = e.touches[0], r = noBtn.getBoundingClientRect();
  const proximity = Math.max(110 - noCount * 5, 50);
  if (Math.hypot(t.clientX - r.left - r.width/2, t.clientY - r.top - r.height/2) < proximity) moveButton();
}, { passive: true });

/* ── Celebrate ── */
function celebrate() {
  document.getElementById('main').style.display = 'none';
  document.getElementById('winScreen').classList.add('show');
  // Button stays visible but tiny and keeps running around as celebration 😂
  noBtn.style.opacity = '0.3';
  noBtn.style.pointerEvents = 'none';
  setInterval(moveButton, 600);
  // Mega heart shower
  for (let i = 0; i < 60; i++) setTimeout(rainHeart, i * 55);
  setInterval(() => rainHeart(), 120);
}

function rainHeart() {
  spawnClickHeart(
    Math.random() * window.innerWidth,
    window.innerHeight - 10
  );
}
</script>
</body>
</html>
