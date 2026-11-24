<!doctype html>
<html lang="pt-BR">
<head>
<meta charset="utf-8">
<meta name="viewport" content="width=device-width, initial-scale=1, viewport-fit=cover">
<title>Exército Brasileiro de Combate</title>
<link rel="preconnect" href="https://fonts.googleapis.com">
<link rel="stylesheet" href="https://fonts.googleapis.com/css2?family=Exo+2:wght@500;700;800&family=Roboto:wght@400;500;700&family=Source+Sans+3:wght@600;700&display=swap">
<style>
:root {
  --bg: #050a18;
  --panel-top: #10244f;
  --panel-bottom: #060d20;
  --line: #1b2f5c;
  --fg: #f2f6ff;
  --muted: #8ea3cc;
  --accent: #2bc4f8;
  --accent-ink: #04202e;
  --danger: #ef6a5e;
  --font-display: "Exo 2", "Segoe UI", system-ui, sans-serif;
  --font-body: "Roboto", system-ui, sans-serif;
  --font-label: "Source Sans 3", "Roboto", system-ui, sans-serif;
  color-scheme: dark;
}
html, body { height: 100%; margin: 0; }
body {
  background: var(--bg);
  color: var(--fg);
  font-family: var(--font-body);
  font-size: 16px;
  padding-left: max(16px, env(safe-area-inset-left, 0px));
  padding-right: max(16px, env(safe-area-inset-right, 0px));
  overflow-x: hidden;
}
*, *::before, *::after { box-sizing: border-box; }
button { font: inherit; color: inherit; cursor: pointer; }
:focus-visible { outline: 2px solid var(--accent); outline-offset: 3px; }

/* ---------- Entrada ---------- */
.intro {
  position: fixed;
  inset: 0;
  display: grid;
  grid-template-rows: 1fr auto 1fr;
  align-items: center;
  justify-items: center;
  padding-top: env(safe-area-inset-top, 0px);
  padding-bottom: env(safe-area-inset-bottom, 0px);
  padding-left: max(16px, env(safe-area-inset-left, 0px));
  padding-right: max(16px, env(safe-area-inset-right, 0px));
  background: var(--bg);
  overflow: hidden;
}
.intro[hidden] { display: none; }
.intro canvas { position: absolute; inset: 0; width: 100%; height: 100%; }
.intro::after {
  content: "";
  position: absolute;
  inset: 0;
  background: radial-gradient(ellipse at 50% 50%, rgba(5,10,24,.88) 0%, rgba(5,10,24,.55) 45%, rgba(5,10,24,0) 80%);
  pointer-events: none;
}
.intro > * { position: relative; z-index: 2; }
.word {
  margin: 0;
  font-family: var(--font-display);
  font-weight: 800;
  letter-spacing: .12em;
  text-transform: uppercase;
  text-align: center;
  line-height: 1;
  text-wrap: balance;
  text-shadow: 0 0 24px rgba(43,196,248,.45);
}
.word.top { align-self: end; padding-bottom: 1.2rem; font-size: clamp(1.9rem, 9vw, 5rem); }
.word.bottom { align-self: start; padding-top: 1.2rem; font-size: clamp(1.6rem, 8.5vw, 4.2rem); color: var(--accent); }
.enter {
  display: inline-flex;
  align-items: center;
  gap: .6rem;
  background: var(--accent);
  color: var(--accent-ink);
  border: 0;
  border-radius: 14px;
  padding: 1rem 1.7rem;
  font-family: var(--font-label);
  font-weight: 700;
  font-size: 1rem;
  letter-spacing: .2em;
  text-transform: uppercase;
  box-shadow: 0 0 28px rgba(43,196,248,.45);
  transition: transform .15s ease, box-shadow .15s ease;
}
.enter:hover { transform: translateY(-2px); box-shadow: 0 0 40px rgba(43,196,248,.65); }

/* ---------- Loja ---------- */
.store { max-width: 1100px; margin: 0 auto; padding-block: 1.25rem 4rem; }
.store[hidden] { display: none; }
.store header {
  display: flex;
  flex-wrap: wrap;
  align-items: center;
  justify-content: space-between;
  gap: .75rem 1.25rem;
  padding-bottom: 1.1rem;
  border-bottom: 1px solid var(--line);
}
.brand {
  background: none;
  border: 0;
  padding: 0;
  text-align: left;
  font-family: var(--font-display);
  font-weight: 800;
  font-size: 1.15rem;
  letter-spacing: .14em;
  text-transform: uppercase;
}
.brand span { color: var(--accent); }
.tabs { display: flex; gap: .5rem; }
.tab {
  background: transparent;
  border: 1px solid var(--line);
  border-radius: 999px;
  padding: .55rem 1.1rem;
  font-family: var(--font-label);
  font-weight: 700;
  letter-spacing: .16em;
  text-transform: uppercase;
  font-size: .82rem;
  color: var(--muted);
}
.tab[aria-selected="true"] { background: var(--accent); border-color: var(--accent); color: var(--accent-ink); }
.notice { margin: 1rem 0 0; color: var(--muted); font-size: .88rem; max-width: 60ch; }
.grid {
  display: grid;
  grid-template-columns: repeat(auto-fill, minmax(min(100%, 300px), 1fr));
  gap: 1rem;
  margin-top: 1.5rem;
  align-items: start;
}
.card {
  min-width: 0;
  border: 1px solid var(--line);
  border-radius: 22px;
  padding: 1.6rem 1.5rem 1.5rem;
  background: linear-gradient(160deg, var(--panel-top) 0%, var(--panel-bottom) 70%);
  display: flex;
  flex-direction: column;
  gap: 1rem;
}
.tag {
  font-family: var(--font-label);
  font-weight: 700;
  font-size: .72rem;
  letter-spacing: .3em;
  text-transform: uppercase;
  color: var(--accent);
}
.card h2 {
  margin: 0;
  font-family: var(--font-display);
  font-weight: 800;
  font-size: 1.6rem;
  line-height: 1.15;
  text-wrap: balance;
}
.rows { list-style: none; margin: .25rem 0 0; padding: 0 0 0 1.4rem; }
.rows li {
  display: flex;
  justify-content: space-between;
  align-items: baseline;
  gap: 1rem;
  padding: .85rem 0;
  border-bottom: 1px solid var(--line);
  font-weight: 500;
}
.rows li:last-child { border-bottom: 0; }
.rows .n { min-width: 0; }
.price {
  font-family: var(--font-display);
  font-weight: 800;
  font-size: 1.45rem;
  color: var(--accent);
  font-variant-numeric: tabular-nums;
  white-space: nowrap;
}
.rows li.off .n { color: var(--danger); }
.rows li.off .price { color: var(--danger); font-size: 1rem; letter-spacing: .08em; }
.buy {
  align-self: flex-start;
  margin-top: .4rem;
  background: var(--accent);
  color: var(--accent-ink);
  border: 0;
  border-radius: 14px;
  padding: .95rem 1.4rem;
  font-family: var(--font-label);
  font-weight: 700;
  letter-spacing: .2em;
  font-size: .85rem;
  text-transform: uppercase;
  box-shadow: 0 0 22px rgba(43,196,248,.35);
}
.buy:hover { box-shadow: 0 0 32px rgba(43,196,248,.55); }

/* ---------- Janela de compra ---------- */
.overlay {
  position: fixed;
  inset: 0;
  z-index: 20;
  display: grid;
  place-items: center;
  padding: 16px;
  background: rgba(2,5,14,.78);
}
.overlay[hidden] { display: none; }
.sheet {
  width: min(100%, 460px);
  max-height: 100%;
  overflow-y: auto;
  border: 1px solid var(--line);
  border-radius: 22px;
  padding: 1.5rem;
  background: linear-gradient(160deg, var(--panel-top) 0%, var(--panel-bottom) 75%);
}
.sheet h3 { margin: .2rem 0 1rem; font-family: var(--font-display); font-size: 1.4rem; line-height: 1.15; }
.choice {
  display: flex;
  align-items: center;
  gap: .8rem;
  padding: .75rem .9rem;
  margin-bottom: .5rem;
  border: 1px solid var(--line);
  border-radius: 12px;
  cursor: pointer;
}
.choice:has(input:checked) { border-color: var(--accent); background: rgba(43,196,248,.1); }
.choice.off { opacity: .5; cursor: not-allowed; }
.choice input { accent-color: var(--accent); width: 1.1rem; height: 1.1rem; flex: none; }
.choice .n { flex: 1; min-width: 0; }
.choice .price { font-size: 1.15rem; }
.choice.off .price { color: var(--danger); font-size: .8rem; letter-spacing: .08em; }
.total { display: flex; justify-content: space-between; align-items: baseline; margin-top: 1.2rem; color: var(--muted); }
.total strong { font-family: var(--font-display); font-size: 1.6rem; color: var(--fg); }
.actions { display: flex; flex-wrap: wrap; gap: .6rem; margin-top: 1.2rem; }
.ghost { background: transparent; border: 1px solid var(--line); border-radius: 14px; padding: .95rem 1.2rem; font-family: var(--font-label); font-weight: 700; letter-spacing: .16em; font-size: .85rem; text-transform: uppercase; color: var(--muted); }
.steps { margin: 0 0 1.1rem; padding: .9rem 1rem; border: 1px solid var(--accent); border-radius: 12px; background: rgba(43,196,248,.1); line-height: 1.5; }
.steps b { color: var(--accent); }
.pay { margin-top: 1.2rem; }
.pay .lbl { display: block; font-family: var(--font-label); font-weight: 700; font-size: .75rem; letter-spacing: .2em; text-transform: uppercase; color: var(--muted); margin-bottom: .4rem; }
.mail { display: flex; flex-wrap: wrap; align-items: center; gap: .6rem; }
.mail code { flex: 1; min-width: 0; overflow-wrap: anywhere; padding: .8rem .9rem; border: 1px solid var(--line); border-radius: 12px; background: var(--bg); font-size: .95rem; user-select: all; }
.mail .ghost { padding: .8rem 1rem; }

@media (prefers-reduced-motion: reduce) {
  .enter, .enter:hover { transition: none; transform: none; }
}
</style>
</head>
<body>

<section class="intro" id="intro" aria-label="Entrada">
  <canvas id="rain" aria-hidden="true"></canvas>
  <h1 class="word top">Exército Brasileiro</h1>
  <button class="enter" id="enter" type="button">Divisão <span aria-hidden="true">/</span> Patente</button>
  <p class="word bottom">de Combate</p>
</section>

<main class="store" id="store" hidden>
  <header>
    <button class="brand" id="home" type="button" aria-label="Voltar à entrada">Exército Brasileiro <span>de Combate</span></button>
    <div class="tabs" role="tablist" aria-label="Categoria">
      <button class="tab" role="tab" id="tab-div" aria-selected="true" data-tab="div">Divisão</button>
      <button class="tab" role="tab" id="tab-pat" aria-selected="false" data-tab="pat">Pa
