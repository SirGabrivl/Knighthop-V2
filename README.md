# Knighthop-V2
Game 
<!doctype html>
<html lang="de">
<head>
<meta charset="utf-8">
<meta name="viewport" content="width=device-width,initial-scale=1,viewport-fit=cover">
<meta name="theme-color" content="#090d16">
<title>KnightHop · Taktik trifft Arcade</title>
<style>
:root{color-scheme:dark;--bg:#090d16;--panel:#121927;--line:#293349;--text:#edf3ff;--muted:#a9b6ce;--accent:#66f4d2;--other:#be9bff;--shadow:rgba(102,244,210,.12);font-family:ui-sans-serif,system-ui,-apple-system,BlinkMacSystemFont,"Segoe UI",sans-serif}
*{box-sizing:border-box}body{margin:0;min-height:100svh;background:radial-gradient(ellipse at 10% 0,var(--shadow),transparent 48%),var(--bg);color:var(--text);padding:20px 16px max(24px,env(safe-area-inset-bottom));padding-top:max(20px,env(safe-area-inset-top));padding-left:max(16px,env(safe-area-inset-left));padding-right:max(16px,env(safe-area-inset-right))}
button{font:inherit;color:inherit;cursor:pointer;touch-action:manipulation;-webkit-tap-highlight-color:transparent}button:focus-visible{outline:3px solid #fff;outline-offset:4px}button[aria-disabled=true]{cursor:default}[hidden]{display:none!important}h1,h2,p{margin-top:0}h2{font-size:1.5rem}p{line-height:1.65}.shell{width:min(100%,650px);margin:auto}
header{display:flex;align-items:center;justify-content:space-between;gap:16px;margin-bottom:28px}.brand{display:flex;align-items:center;gap:10px;font-size:.9rem;font-weight:800;letter-spacing:.08em}.brand-mark{display:grid;place-items:center;width:38px;height:38px;border:1px solid var(--line);border-radius:12px;font-size:29px;color:var(--accent)}.actions{display:flex;gap:8px}.quiet{border:1px solid var(--line);background:var(--panel);border-radius:12px;min-height:44px;padding:10px 14px;font-weight:650}
.eyebrow{font-size:.7rem;letter-spacing:.22em;font-weight:800;color:var(--accent);margin-bottom:14px}.hero{padding:12px 0 18px}.hero h1{font-size:clamp(3.4rem,12vw,5.6rem);letter-spacing:-.07em;line-height:.96;margin-bottom:18px;font-weight:900}.hero h1 span{color:var(--accent)}.subtitle{font-size:1.05rem;color:var(--muted);margin-bottom:0}.panel{background:linear-gradient(145deg,#172031,#101622);border:1px solid var(--line);border-radius:24px;padding:22px;margin-top:18px}
.section-label{font-size:.72rem;text-transform:uppercase;letter-spacing:.15em;font-weight:800;color:var(--muted);margin-bottom:14px}.modes{display:grid;grid-template-columns:repeat(3,minmax(0,1fr));gap:8px}.mode{display:flex;flex-direction:column;gap:8px;align-items:flex-start;text-align:left;min-height:88px;padding:13px 11px;border:1px solid var(--line);border-radius:14px;background:#0d1421;font-weight:750;font-size:.85rem}.mode span{font-size:1.25rem;color:var(--accent)}.mode[aria-pressed=true],.sizes button[aria-pressed=true]{border-color:var(--accent);background:var(--shadow);box-shadow:inset 0 0 0 1px var(--accent)}
.description{color:var(--muted);font-size:.92rem;min-height:3.2em;margin:16px 0}.options{display:flex;align-items:center;justify-content:space-between;gap:14px;border-top:1px solid var(--line);padding-top:16px;flex-wrap:wrap}.sizes{display:flex;gap:6px}.sizes button{background:#0d1421;border:1px solid var(--line);border-radius:10px;min-height:44px;min-width:44px;font-weight:700}.option-label{color:var(--muted);font-size:.85rem}.primary{width:100%;border:0;border-radius:15px;min-height:54px;padding:16px 20px;font-weight:850;background:var(--accent);color:#091319;box-shadow:0 6px 28px var(--shadow)}.start{margin-top:18px;display:flex;justify-content:space-between;align-items:center;font-size:1rem}.record{margin:14px 0 0;text-align:center;font-size:.85rem;color:var(--muted)}.intro{display:flex;gap:16px;align-items:center;margin-top:25px;padding:0 4px}.intro svg{width:62px;min-width:62px;height:62px;color:var(--accent)}.intro p{font-size:.87rem;color:var(--muted);margin:0}.intro strong{color:var(--text)}footer{text-align:center;color:var(--muted);font-size:.75rem;margin:26px 0 0}
.game-top{display:flex;justify-content:space-between;align-items:center;gap:12px;margin-bottom:18px}.game-top p{margin:4px 0 0;font-size:.85rem;color:var(--muted)}.game-top h1{font-size:1.25rem;margin:0}.stats{display:grid;grid-template-columns:repeat(3,minmax(0,1fr));gap:8px;margin-bottom:14px}.stat{background:var(--panel);border:1px solid var(--line);border-radius:14px;padding:13px 10px}.stat small{display:block;color:var(--muted);font-size:.68rem;margin-bottom:6px}.stat strong{font-size:clamp(.95rem,4vw,1.4rem);font-variant-numeric:tabular-nums}.board-wrap{position:relative;width:min(100%,520px);margin:auto}.board{display:grid;gap:5px;aspect-ratio:1;padding:8px;border-radius:19px;background:#141e30;border:1px solid #33425a;box-shadow:0 20px 70px #0005}.cell{display:grid;place-items:center;position:relative;min-width:0;padding:0;aspect-ratio:1;border:1px solid #ffffff06;border-radius:8px;background:#202d43;font-size:clamp(18px,6vw,36px);color:var(--text)}.cell.dark{background:#1a263a}.cell.visited{background:#101827;color:#75849f;font-size:1rem}.cell.blocked{background:#271f2e;color:#c29ca7;font-size:1.25rem}.cell.legal{border:2px solid var(--accent);background:var(--shadow)}.cell.legal.cell.p1{background:var(--accent);color:#091319;border-color:var(--accent);box-shadow:0 0 20px var(--shadow)}.cell.p2{background:var(--other);color:#141020;border-color:var(--other)}.cell b{position:absolute;right:4px;bottom:2px;font-size:.62rem}.board[data-player="1"] .cell.legal{border-color:var(--other);background:#be9bff18}.board[data-player="1"] .cell.legal.meter{height:5px;background:var(--line);border-radius:10px;overflow:hidden;margin:16px 0 12px}.meter div{height:100%;background:var(--accent);transform-origin:left}.hint{color:var(--muted);font-size:.85rem;text-align:center;min-height:2.9em;margin:15px 0 0}.pause-cover{position:absolute;inset:0;background:#090d16ed;backdrop-filter:blur(8px);border-radius:19px;display:flex;flex-direction:column;justify-content:center;gap:12px;padding:28px;text-align:center;border:1px solid var(--line)}.pause-cover h2{margin:0}.pause-cover p{color:var(--muted);margin:0 0 6px}.result{text-align:center;padding:30px 22px}.result-icon{font-size:4rem;color:var(--accent)}.big-score{font-size:4.7rem;font-weight:900;letter-spacing:-.06em;font-variant-numeric:tabular-nums;margin:12px 0}.result p{color:var(--muted)}.result .quiet{width:100%;margin-top:10px}
dialog{width:min(calc(100% - 32px),460px);max-height:calc(100svh - 40px);overflow:auto;color:var(--text);background:#121b2b;border:1px solid var(--line);border-radius:24px;padding:26px}dialogdialog p,dialog li{color:var(--muted);line-height:1.65}dialog ol{padding-left:22px}dialog li{margin:12px 0}.sr-only{position:absolute;width:1px;height:1px;padding:0;margin:-1px;overflow:hidden;clip:rect(0,0,0,0);white-space:nowrap;border:0}
@media(max-width:380px){.panel{padding:16px}.mode{padding:11px 8px;font-size:.78rem}.board{gap:4px;padding:6px}.cell{border-radius:5px}.sizes{gap:4px}.sizes button{min-width:40px}}
@media(prefers-reduced-motion:no-preference){button{transition:background .15s,border-color .15s,transform .15s}.primary:active,.mode:active{transform:translateY(2px)}.screen{animation:appear .2s ease}@keyframes appear{from{opacity:.4;transform:translateY(6px)}to{opacity:1;transform:translateY(0)}}}
</style>
</head>
<body>
<div class="shell">
<header>
  <div class="brand"><span class="brand-mark" aria-hidden="true">♞</span> KNIGHTHOP</div>
  <div class="actions">
    <button id="sound" class="quiet" type="button" aria-pressed="false">Ton aus</button>
    <button id="helpOpen" class="quiet" type="button" aria-label="Spielanleitung öffnen">?</button>
  </div>
</header>
<main>
<section id="menu" class="screen" aria-label="Hauptmenü">
  <div class="hero">
    <p class="eyebrow">TAKTIK TRIFFT ARCADE</p>
    <h1>KNIGHT<span>HOP.</span></h1>
    <p class="subtitle">Ein Springer. Dein nächster Rekord.</p>
  </div>
  <div class="panel">
    <p class="section-label">Wähle dein Spiel</p>
    <div id="modes" class="modes" role="group" aria-label="Spielmodus">
      <button type="button" class="mode" data-mode="classic" aria-pressed="true"><span aria-hidden="true">◇</span>Klassisch</button>
      <button type="button" class="mode" data-mode="endless" aria-pressed="false"><span aria-hidden="true">∞</span>Endlos</button>
      <button type="button" class="mode" data-mode="danger" aria-pressed="false"><span aria-hidden="true">×</span>Hindernisse</button>
      <button type="button" class="mode" data-mode="duo" aria-pressed="false"><span aria-hidden="true">♞♞</span>Duell</button>
      <button type="button" class="mode" data-mode="time" aria-pressed="false"><span aria-hidden="true">◷</span>Zeitjagd</button>
    </div>
    <p id="description" class="description"></p>
    <div class="options">
      <span class="option-label">Brettgröße</span>
      <div id="sizes" class="sizes" role="group" aria-label="Brettgröße">
        <button type="button" data-size="5" aria-pressed="false" aria-label="5 mal 5 Felder">5×5</button>
        <button type="button" data-size="6" aria-pressed="false" aria-label="6 mal 6 Felder">6×6</button>
        <button type="button" data-size="7" aria-pressed="true" aria-label="7 mal 7 Felder">7×7</button>
        <button type="button" data-size="8" aria-pressed="false" aria-label="8 mal 8 Felder">8×8</button>
      </div>
    </div>
  </div>
  <button id="start" class="primary start" type="button">Spiel starten <span aria-hidden="true">↗</span></button>
  <p id="record" class="record"></p>
  <div class="intro">
    <svg viewBox="0 0 64 64" fill="none" aria-hidden="true">
      <path d="M12 12h40v40H12zM12 32h40M32 12v40" stroke="currentColor" opacity=".2"/>
      <path d="M12 12v40h20" stroke="currentColor" stroke-width="3" stroke-linecap="round" stroke-linejoin="round"/>
      <circle cx="12" cy="12" r="5" fill="currentColor"/>
      <circle cx="32" cy="52" r="5" fill="currentColor"/>
    </svg>
    <p><strong>Spring im L.</strong> Zwei Felder gerade, eins zur Seite. Tippe ein markiertes Zielfeld. Jeder Sprung bringt 10 Punkte.</p>
  </div>
</section>

<section id="gameScreen" class="screen" hidden aria-label="Laufendes Spiel">
  <div class="game-top">
    <div><h1 id="gameTitle"></h1><p id="gameSubtitle">Plane deinen nächsten Sprung.</p></div>
    <button id="pause" class="quiet" type="button">Pause</button>
  </div>
  <div class="stats">
    <div class="stat"><small id="scoreLabel">PUNKTE</small><strong id="score">0</strong></div>
    <div class="stat"><small id="roundLabel">RUNDE</small><strong id="round">1</strong></div>
    <div class="stat"><small id="clockLabel">ZEIT</small><strong id="clock">60 s</strong></div>
  </div>
  <div class="board-wrap">
    <div id="board" class="board" role="group" aria-label="Spielfeld. Mit Pfeiltasten navigieren, mit Eingabetaste springen."></div>
    <div id="pausePanel" class="pause-cover" hidden>
      <h2>Kurze Pause.</h2>
      <p>Dein Spiel wartet auf dich.</p>
      <button id="resume" class="primary" type="button">Weiterspielen</button>
      <button id="leave" class="quiet" type="button">Runde beenden</button>
    </div>
  </div>
  <div id="timeMeter" class="meter" hidden><div id="timeBar"></div></div>
  <p id="hint" class="hint"></p>
</section>

<section id="result" class="screen panel result" hidden aria-label="Spielergebnis">
  <div class="result-icon" aria-hidden="true">♞</div>
  <p id="resultTag" class="eyebrow">GUT GESPRUNGEN</p>
  <h2 id="resultTitle" tabindex="-1">Runde beendet</h2>
  <div id="resultScore" class="big-score"></div>
  <p id="resultDetail"></p>
  <button id="again" class="primary" type="button">Noch eine Runde</button>
  <button id="menuButton" class="quiet" type="button">Zum Hauptmenü</button>
</section>
</main>

<footer id="storageNote">Bestleistungen werden lokal gespeichert. Ohne Werbung. Ohne Anmeldung.</footer>
<div id="announce" class="sr-only" role="status" aria-live="polite"></div>
</div>

<dialog id="help" aria-labelledby="helpTitle">
  <p class="eyebrow">SO FUNKTIONIERT'S</p>
  <h2 id="helpTitle">Denk einen Sprung voraus.</h2>
  <ol>
    <li>Der Springer bewegt sich im L: zwei Felder in eine Richtung, eins seitwärts. Hindernisse darf er überspringen.</li>
    <li>Markierte Felder sind deine möglichen Ziele. Verlassene Felder sind danach gesperrt; nur in der Zeitjagd darfst du sie erneut betreten.</li>
    <li>In Klassisch und Endlos beginnt nach zehn Sprüngen eine neue Runde. In Klassisch hast du dafür jeweils 60 Sekunden.</li>
    <li>Im Duell spielt ihr abwechselnd auf demselben Gerät. Wer keinen gültigen Sprung mehr hat, verliert.</li>
    <li>Die Zeitjagd dauert 30 Sekunden. Mit Pfeiltasten und Eingabetaste kannst du auch am Computer spielen. P pausiert.</li>
  </ol>
  <button id="helpClose" class="primary" type="button">Verstanden</button>
</dialog>

<script>
"use strict";

class KnightGame {
  constructor({ mode = 'classic', size = 7, rng = Math.random } = {}) {
    if (!['classic', 'endless', 'danger', 'duo', 'time'].includes(mode))
      throw new RangeError('Unbekannter Spielmodus.');
    if (!Number.isInteger(size) || size < 5 || size > 8)
      throw new RangeError('Die Brettgröße muss zwischen 5 und 8 liegen.');

    this.mode = mode;
    this.size = size;
    this.rng = rng;
    this.turn = 0;
    this.scores = [0, 0];
    this.level = 1;
    this.levelMoves = 0;
    this.remaining = mode === 'classic' ? 60 : mode === 'time' ? 30 : 0;
    this.phase = 'playing';
    this.reason = '';
    this.winner = null;
    this.event = 'move';

    const middle = Math.floor(size / 2);
    this.positions = mode === 'duo'
      ? [0, size * size - 1]
      : [middle * size + middle, null];

    const offsets = [
      [1,2],[2,1],[-1,2],[-2,1],
      [1,-2],[2,-1],[-1,-2],[-2,-1]
    ];

    this._links = Array.from({ length: size * size }, (_, index) => {
      const x = index % size, y = Math.floor(index / size);
      return offsets.map(([dx,dy]) => [x + dx, y + dy])
        .filter(([a,b]) => a >= 0 && b >= 0 && a < size && b < size)
        .map(([a,b]) => b * size + a);
    });

    this._makeBoard();
  }

  _shuffle(values) {
    for (let i = values.length - 1; i > 0; i--) {
      const j = Math.floor(this.rng() * (i + 1));
      [values[i], values[j]] = [values[j], values[i]];
    }
    return values;
  }

  _reservePath(hops) {
    const start = this.positions[0];
    const path = [start], used = new Set(path);
    let budget = 12000;

    const search = (randomized) => {
      if (path.length === hops + 1) return true;
      if (--budget < 0) return false;

      let options = this._links[path[path.length - 1]]
        .filter(i => !used.has(i));

      if (randomized) options = this._shuffle(options);

      options.sort((a,b) =>
        this._links[a].filter(i => !used.has(i)).length -
        this._links[b].filter(i => !used.has(i)).length);

      for (const next of options) {
        used.add(next);
        path.push(next);
        if (search(randomized)) return true;
        path.pop();
        used.delete(next);
      }
      return false;
    };

    if (!search(true)) {
      budget = 12000;
      if (!search(false))
        throw new Error('Kein spielbarer Pfad gefunden.');
    }
    return path;
  }

  _makeBoard() {
    const total = this.size * this.size;
    this.board = Array.from(
      { length: total },
      () => ({ blocked: false, visited: null })
    );

    if (this.mode !== 'classic' && this.mode !== 'danger') return;

    const path = new Set(
      this._reservePath(this.mode === 'classic' ? 10 : 6)
    );
    const fraction = this.mode === 'danger'
      ? .25
      : Math.min(.25, .05 + (this.level - 1) * .02);

    const candidates = this._shuffle(
      Array.from({ length: total }, (_, i) => i)
        .filter(i => !path.has(i))
    );

    const count = Math.min(
      candidates.length,
      Math.floor(total * fraction)
    );

    for (let i = 0; i < count; i++)
      this.board[candidates[i]].blocked = true;
  }

  legalMoves(player = this.turn) {
    if (this.phase !== 'playing' || (player !== 0 && player !== 1))
      return [];

    const position = this.positions[player];
    if (!Number.isInteger(position)) return [];

    return this._links[position].filter(index => {
      const cell = this.board[index];
      return !cell.blocked &&
        (this.mode === 'time' || cell.visited === null) &&
        (this.mode !== 'duo' ||
          index !== this.positions[1 - player]);
    });
  }

  move(index) {
    if (!Number.isInteger(index) ||
        index < 0 ||
        index >= this.board.length ||
        !this.legalMoves().includes(index))
      return false;

    this.event = 'move';
    const player = this.turn;

    if (this.mode !== 'time')
      this.board[this.positions[player]].visited = player;

    this.positions[player] = index;
    this.scores[player] += 10;
    this.levelMoves++;

    if (this.mode === 'duo') {
      this.turn = 1 - this.turn;

      if (!this.legalMoves().length)
        this._finish(
          'Spieler ' + (player + 1) +
          ' gewinnt. Spieler ' + (this.turn + 1) +
          ' hat keinen Zug mehr.',
          player
        );

    } else if (
      (this.mode === 'classic' || this.mode === 'endless') &&
      this.levelMoves >= 10
    ) {
      this.level++;
      this.levelMoves = 0;
      if (this.mode === 'classic') this.remaining = 60;
      this._makeBoard();
      this.event = 'level';

    } else if (
      this.mode !== 'time' &&
      !this.legalMoves().length
    ) {
      this._finish('Keine weiteren Sprünge möglich.');
    }

    return true;
  }

  tick(seconds) {
    if (this.phase !== 'playing' ||
        !Number.isFinite(seconds) ||
        seconds <= 0 ||
        (this.mode !== 'classic' && this.mode !== 'time'))
      return false;

    this.remaining = Math.max(0, this.remaining - seconds);

    if (this.remaining === 0)
      this._finish('Die Zeit ist abgelaufen.');

    return true;
  }

  _finish(reason, winner = null) {
    this.phase = 'over';
    this.reason = reason;
    this.winner = winner;
    this.event = 'over';
  }
}

function knightHopApp() {
  const $ = id => document.getElementById(id);

  const MODES = {
    classic: {
      name:"Klassisch",
      description:"Zehn Sprünge pro Runde, jeweils 60 Sekunden. Die Hindernisse nehmen zu. Plane voraus."
    },
    endless: {
      name:"Endlos",
      description:"Zehn Sprünge öffnen das nächste Brett. Ohne Zeitdruck. Wie weit kommst du?"
    },
    danger: {
      name:"Hindernisse",
      description:"Ein Brett voller Hindernisse. Sammle möglichst viele Punkte, bis dir die Sprünge ausgehen."
    },
    duo: {
      name:"Duell",
      description:"Abwechselnd zu zweit auf einem Gerät. Wer keinen Sprung mehr hat, verliert."
    },
    time: {
      name:"Zeitjagd",
      description:"30 Sekunden. Jeder Sprung zählt. Hier darfst du Felder erneut besuchen."
    }
  };

  let storageOK = true;

  function read(key,fallback) {
    try {
      return JSON.parse(localStorage.getItem(key)) ?? fallback;
    } catch {
      storageOK=false;
      return fallback;
    }
  }

  function write(key,value) {
    try {
      localStorage.setItem(key,JSON.stringify(value));
    } catch {
      storageOK=false;
    }

    $("storageNote").textContent=storageOK
      ? "Bestleistungen werden lokal gespeichert. Ohne Werbung. Ohne Anmeldung."
      : "Bestleistungen bleiben in dieser Sitzung. Ohne Werbung. Ohne Anmeldung.";
  }

  const saved = read("knighthop.v2.settings",{});

  const settings = {
    mode:Object.prototype.hasOwnProperty.call(MODES,saved.mode)
      ? saved.mode : "classic",
    size:Number.isInteger(saved.size) &&
      saved.size>=5 && saved.size<=8 ? saved.size : 7,
    sound:saved.sound===true
  };

  let best = read("knighthop.v2.best",{});
  if (typeof best!=="object" || Array.isArray(best)) best={};

  let game=null;
  let screen="menu";
  let paused=false;
  let lastTime=null;
  let audio=null;
  let startingBest=0;

  const saveSettings=()=>
    write("knighthop.v2.settings",settings);

  function getBest() {
    const value=best[`${settings.mode}:${settings.size}`];
    return Number.isSafeInteger(value) && value>=0 ? value : 0;
  }

  function saveRecord() {
    if (game && game.mode!=="duo" &&
        game.scores[0]>getBest()) {
      best[`${game.mode}:${game.size}`]=game.scores[0];
      write("knighthop.v2.best",best);
    }
  }

  function announce(message) {
    $("announce").textContent=message;
  }

  function beep(frequency=520) {
    if (!settings.sound) return;

    try {
      const Audio=window.AudioContext||window.webkitAudioContext;
      if (!Audio) return;
      if (!audio) audio=new Audio();

      if (audio.state==="suspended")
        audio.resume().catch(()=>{});

      const osc=audio.createOscillator();
      const gain=audio.createGain();
      const now=audio.currentTime;

      osc.type="sine";
      osc.frequency.setValueAtTime(frequency,now);
      gain.gain.setValueAtTime(.045,now);
      gain.gain.exponentialRampToValueAtTime(.0001,now+.14);

      osc.connect(gain);
      gain.connect(audio.destination);
      osc.start(now);
      osc.stop(now+.15);

      osc.onended=()=>{
        osc.disconnect();
        gain.disconnect();
      };
    } catch {}
  }

  function show(id) {
    screen=id;
    for (const item of ["menu","gameScreen","result"])
      $(item).hidden=item!==id;
  }

  function drawMenu() {
    document.querySelectorAll("[data-mode]").forEach(button=>
      button.setAttribute(
        "aria-pressed",
        String(button.dataset.mode===settings.mode)
      )
    );

    document.querySelectorAll("[data-size]").forEach(button=>
      button.setAttribute(
        "aria-pressed",
        String(Number(button.dataset.size)===settings.size)
      )
    );

    $("description").textContent=MODES[settings.mode].description;

    $("record").textContent=settings.mode==="duo"
      ? "Ein Gerät. Zwei Spieler. Ein Sieger."
      : `Deine Bestleistung auf ${settings.size}×${settings.size}: ${getBest()} Punkte`;

    $("sound").textContent=settings.sound?"Ton an":"Ton aus";
    $("sound").setAttribute(
      "aria-pressed",
      String(settings.sound)
    );
  }

  function updateClock() {
    const timed=game.mode==="classic"||game.mode==="time";

    $("clockLabel").textContent=timed
      ? "ZEIT"
      : game.mode==="duo" ? "SPIELER" : "BESTLEISTUNG";

    $("clock").textContent=timed
      ? `${Math.ceil(game.remaining)} s`
      : game.mode==="duo" ? "1 gegen 2" : getBest();

    $("timeMeter").hidden=!timed;

    $("timeBar").style.transform=
      `scaleX(${timed
        ? game.remaining/(game.mode==="classic"?60:30)
        : 1})`;
  }

  function drawGame(focus=false) {
    $("gameTitle").textContent=MODES[game.mode].name;

    $("gameSubtitle").textContent=game.mode==="duo"
      ? `Spieler ${game.turn+1} ist am Zug.`
      : game.mode==="classic"||game.mode==="endless"
        ? `${game.levelMoves} von 10 Sprüngen zum nächsten Brett.`
        : "Plane deinen nächsten Sprung.";

    $("scoreLabel").textContent=game.mode==="duo"
      ? "PUNKTE 1 : 2" : "PUNKTE";

    $("score").textContent=game.mode==="duo"
      ? game.scores.join(" : ") : game.scores[0];

    $("roundLabel").textContent=game.mode==="duo"
      ? "AM ZUG" : "RUNDE";

    $("round").textContent=game.mode==="duo"
      ? `Spieler ${game.turn+1}` : game.level;

    const moves=new Set(game.legalMoves());
    const board=$("board");

    board.style.gridTemplateColumns=
      `repeat(${game.size},minmax(0,1fr))`;

    board.dataset.player=String(game.turn);

    board.innerHTML=game.board.map((cell,index)=>{
      const p1=index===game.positions[0];
      const p2=game.mode==="duo"&&index===game.positions[1];
      const x=index%game.size;
      const y=Math.floor(index/game.size);

      const state=p1 ? "Spieler 1"
        : p2 ? "Spieler 2"
        : cell.blocked ? "Hindernis"
        : cell.visited!==null ? "bereits besucht"
        : moves.has(index) ? "möglicher Sprung"
        : "freies Feld";

      const classes=[
        "cell",
        (x+y)%2 ? "dark" : "",
        cell.blocked ? "blocked" : "",
        cell.visited!==null ? "visited" : "",
        moves.has(index) ? "legal" : "",
        p1 ? "p1" : "",
        p2 ? "p2" : ""
      ].join(" ");

      const symbol=p1||p2
        ? `<span aria-hidden="true">♞</span>${
            game.mode==="duo"
              ? `<b aria-hidden="true">${p1?1:2}</b>` : ""
          }`
        : cell.blocked
          ? '<span aria-hidden="true">×</span>'
          : cell.visited!==null
            ? '<span aria-hidden="true">·</span>'
            : "";

      return `<button
        type="button"
        class="${classes}"
        data-cell="${index}"
        tabindex="${index===game.positions[game.turn]?0:-1}"
        aria-disabled="${!moves.has(index)}"
        aria-label="Feld ${String.fromCharCode(65+x)}${y+1}: ${state}"
      >${symbol}</button>`;
    }).join("");

    $("hint").textContent=game.event==="level"
      ? `Runde ${game.level}! Zehn neue Sprünge warten auf dich.`
      : `${moves.size} mögliche Sprünge · ${
          game.mode==="duo" ? `Spieler ${game.turn+1}: ` : ""
        }Tippe ein markiertes Feld.`;

    updateClock();

    if (focus)
      board.children[game.positions[game.turn]]
        ?.focus({preventScroll:true});
  }

  function finish() {
    if (screen!=="gameScreen"||game.phase!=="over") return;

    saveRecord();
    paused=false;
    lastTime=null;

    const record=game.mode!=="duo"&&
      game.scores[0]>startingBest;

    $("resultTag").textContent=game.mode==="duo"
      ? "DUELL ENTSCHIEDEN"
      : record ? "NEUE BESTLEISTUNG" : "GUT GESPRUNGEN";

    $("resultTitle").textContent=game.mode==="duo"
      ? `Spieler ${game.winner+1} gewinnt!`
      : record ? "Dein neuer Rekord." : "Runde beendet.";

    $("resultScore").textContent=game.mode==="duo"
      ? game.scores.join(" : ") : game.scores[0];

    $("resultDetail").textContent=game.reason+
      (game.mode==="duo"
        ? "" : ` Bestleistung: ${getBest()} Punkte.`);

    show("result");
    $("resultTitle").focus();
    announce(game.reason);
    beep(240);
  }

  function advance(now,allowHidden=false) {
    if (game &&
        screen==="gameScreen" &&
        !paused &&
        game.phase==="playing" &&
        (allowHidden||!document.hidden)) {

      if (lastTime!==null)
        game.tick(Math.max(0,(now-lastTime)/1000));

      lastTime=now;
      updateClock();
      if (game.phase==="over") finish();
    } else {
      lastTime=null;
    }
  }

  function pauseGame(value=true) {
    if (!game ||
        screen!=="gameScreen" ||
        game.phase!=="playing") return;

    if (!paused) advance(performance.now(),true);
    if (game.phase!=="playing") return;

    paused=value;
    lastTime=value?null:performance.now();

    $("pausePanel").hidden=!value;
    $("board").inert=value;
    $("pause").textContent=value?"Weiter":"Pause";

    if (value) {
      $("resume").focus();
      announce("Spiel pausiert.");
    } else {
      drawGame(true);
      announce("Spiel fortgesetzt.");
    }
  }

  function start() {
    startingBest=getBest();
    game=new KnightGame({
      mode:settings.mode,
      size:settings.size
    });

    paused=false;
    lastTime=performance.now();
    $("pausePanel").hidden=true;
    $("board").inert=false;
    $("pause").textContent="Pause";

    show("gameScreen");
    drawGame(true);
    announce(`${MODES[game.mode].name} gestartet.`);
    beep();
  }

  $("start").addEventListener("click",start);
  $("again").addEventListener("click",start);

  function menu() {
    saveRecord();
    paused=false;
    lastTime=null;
    show("menu");
    drawMenu();
    $("start").focus();
  }

  $("leave").addEventListener("click",menu);
  $("menuButton").addEventListener("click",menu);

  $("pause").addEventListener(
    "click",()=>pauseGame(!paused)
  );

  $("resume").addEventListener(
    "click",()=>pauseGame(false)
  );

  $("sound").addEventListener("click",()=>{
    settings.sound=!settings.sound;
    saveSettings();
    drawMenu();
    beep();
  });

  $("modes").addEventListener("click",event=>{
    const button=event.target.closest("[data-mode]");
    if (!button) return;
    settings.mode=button.dataset.mode;
    saveSettings();
    drawMenu();
    beep(420);
  });

  $("sizes").addEventListener("click",event=>{
    const button=event.target.closest("[data-size]");
    if (!button) return;
    settings.size=Number(button.dataset.size);
    saveSettings();
    drawMenu();
  });

  $("board").addEventListener("click",event=>{
    const button=event.target.closest("[data-cell]");
    if (!button||paused||screen!=="gameScreen") return;

    advance(performance.now());
    if (game.phase!=="playing") return;

    if (!game.move(Number(button.dataset.cell))) {
      announce("Wähle eines der markierten Zielfelder.");
      return;
    }

    saveRecord();
    drawGame(true);

    if (game.phase==="over") {
      finish();
    } else {
      announce(game.event==="level"
        ? `Runde ${game.level} beginnt.`
        : `${game.scores[0]} Punkte.${
            game.mode==="duo"
              ? ` Spieler ${game.turn+1} ist am Zug.` : ""
          }`
      );
      beep(game.event==="level"?800:520);
    }
  });

  $("board").addEventListener("keydown",event=>{
    if (paused) return;

    const button=event.target.closest("[data-cell]");
    if (!button) return;

    const index=Number(button.dataset.cell);
    const x=index%game.size;
    const y=Math.floor(index/game.size);

    const steps={
      ArrowLeft:[-1,0],
      ArrowRight:[1,0],
      ArrowUp:[0,-1],
      ArrowDown:[0,1]
    };

    if (!steps[event.key]) return;

    event.preventDefault();

    const [dx,dy]=steps[event.key];
    const nx=x+dx,ny=y+dy;

    if (nx<0||ny<0||nx>=game.size||ny>=game.size) return;

    const next=ny*game.size+nx;

    Array.from($("board").children).forEach((cell,i)=>
      cell.tabIndex=i===next?0:-1
    );

    $("board").children[next].focus({preventScroll:true});
  });

  $("helpOpen").addEventListener("click",()=>{
    if (screen==="gameScreen") pauseGame();
    $("help").showModal();
  });

  $("helpClose").addEventListener(
    "click",()=>$("help").close()
  );

  document.addEventListener("keydown",event=>{
    if ($("help").open ||
        screen!=="gameScreen" ||
        event.repeat) return;

    if (event.key.toLowerCase()==="p"||event.key==="Escape") {
      event.preventDefault();
      pauseGame(!paused);
    }
  });

  document.addEventListener("visibilitychange",()=>{
    if (document.hidden) {
      pauseGame();
      try {
        audio?.suspend().catch(()=>{});
      } catch {}
    }
  });

  function frame(now) {
    advance(now);
    requestAnimationFrame(frame);
  }

  drawMenu();

  $("storageNote").textContent=storageOK
    ? "Bestleistungen werden lokal gespeichert. Ohne Werbung. Ohne Anmeldung."
    : "Bestleistungen bleiben in dieser Sitzung. Ohne Werbung. Ohne Anmeldung.";

  requestAnimationFrame(frame);
}

knightHopApp();
</script>
</body>
</html>
