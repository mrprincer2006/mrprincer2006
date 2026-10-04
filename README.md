<!DOCTYPE html>
<html lang="en">
<head>
<meta charset="utf-8">
<meta name="viewport" content="width=device-width, initial-scale=1, viewport-fit=cover">
<title>Prince Raj — Founder and software developer</title>
<link rel="preconnect" href="https://fonts.googleapis.com">
<link rel="preconnect" href="https://fonts.gstatic.com" crossorigin>
<link href="https://fonts.googleapis.com/css2?family=Instrument+Serif:ital@0;1&family=Geist:wght@400;500;600&family=Geist+Mono:wght@400;500&display=swap" rel="stylesheet">
<script>
  try { var t = localStorage.getItem('pr-theme2'); if (t === 'light' || t === 'dark') document.documentElement.setAttribute('data-theme', t); } catch (e) {}
</script>
<style>
  :root {
    --bg: #f6f7fa; --panel: #ffffff; --ink: #0d1220; --mute: #586078;
    --line: #dde1ea; --line2: #c3c9d6; --accent: #3552e6; --accent-ink: #ffffff;
    --grid: rgba(13,18,32,.05); --grid-strong: rgba(53,82,230,.26); --tint: rgba(53,82,230,.08);
    --serif: 'Instrument Serif', 'Iowan Old Style', Georgia, serif;
    --sans: 'Geist', 'Segoe UI', system-ui, sans-serif;
    --mono: 'Geist Mono', ui-monospace, 'SFMono-Regular', Menlo, monospace;
  }
  @media (prefers-color-scheme: dark) {
    :root:not([data-theme="light"]) {
      --bg: #0a0d14; --panel: #10151f; --ink: #e9ecf4; --mute: #8b94a9;
      --line: #222a3b; --line2: #323c52; --accent: #6f8aff; --accent-ink: #0a0d14;
      --grid: rgba(140,160,220,.06); --grid-strong: rgba(111,138,255,.3); --tint: rgba(111,138,255,.1);
    }
  }
  :root[data-theme="dark"] {
    --bg: #0a0d14; --panel: #10151f; --ink: #e9ecf4; --mute: #8b94a9;
    --line: #222a3b; --line2: #323c52; --accent: #6f8aff; --accent-ink: #0a0d14;
    --grid: rgba(140,160,220,.06); --grid-strong: rgba(111,138,255,.3); --tint: rgba(111,138,255,.1);
  }

  * { box-sizing: border-box; margin: 0; }
  :root { box-sizing: border-box; padding-top: env(safe-area-inset-top, 0px); padding-bottom: env(safe-area-inset-bottom, 0px); }
  html { scroll-behavior: smooth; scroll-padding-top: calc(env(safe-area-inset-top, 0px) + 72px); }
  body { background: var(--bg); color: var(--ink); font-family: var(--sans); font-size: 1.0625rem; line-height: 1.65; -webkit-font-smoothing: antialiased; overflow-x: hidden; }
  h1, h2, h3 { font-family: var(--serif); font-weight: 400; line-height: 1.02; letter-spacing: -.015em; }
  p { max-width: 60ch; }
  a { color: inherit; }
  button { font: inherit; color: inherit; cursor: pointer; }
  :focus-visible { outline: 2px solid var(--accent); outline-offset: 3px; border-radius: 4px; }
  .wrap { width: 100%; max-width: 1160px; margin: 0 auto; padding-inline: clamp(20px, 5vw, 44px); }

  /* nav */
  .nav { position: sticky; top: env(safe-area-inset-top, 0px); z-index: 20; background: color-mix(in srgb, var(--bg) 80%, transparent); backdrop-filter: blur(14px); -webkit-backdrop-filter: blur(14px); border-bottom: 1px solid var(--line); }
  .nav-in { display: flex; align-items: center; justify-content: space-between; height: 62px; gap: 16px; }
  .logo { font-family: var(--serif); font-size: 1.5rem; text-decoration: none; letter-spacing: -.01em; }
  .nav-links { display: flex; align-items: center; gap: clamp(14px, 3vw, 32px); font-size: .95rem; }
  .nav-links a { text-decoration: none; color: var(--mute); transition: color .2s; }
  .nav-links a:hover { color: var(--ink); }
  .icon-btn { width: 36px; height: 36px; border-radius: 8px; border: 1px solid var(--line2); background: transparent; display: grid; place-items: center; transition: border-color .2s, background .2s; }
  .icon-btn:hover { border-color: var(--accent); background: var(--tint); }
  @media (max-width: 560px) { .nav-links .hide-sm { display: none; } }

  /* hero */
  .hero { position: relative; isolation: isolate; overflow: hidden; border-bottom: 1px solid var(--line); }
  .hero::before, .hero::after { content: ""; position: absolute; inset: 0; z-index: -1; pointer-events: none; background-size: 56px 56px; }
  .hero::before { background-image: linear-gradient(var(--grid) 1px, transparent 1px), linear-gradient(90deg, var(--grid) 1px, transparent 1px); }
  .hero::after {
    background-image: linear-gradient(var(--grid-strong) 1px, transparent 1px), linear-gradient(90deg, var(--grid-strong) 1px, transparent 1px);
    -webkit-mask-image: radial-gradient(360px circle at var(--gx, 72%) var(--gy, 28%), #000, transparent 70%);
    mask-image: radial-gradient(360px circle at var(--gx, 72%) var(--gy, 28%), #000, transparent 70%);
  }
  .hero-body { padding-block: clamp(72px, 13vw, 168px) clamp(48px, 7vw, 88px); }
  .hero h1 { font-size: clamp(3rem, 8.6vw, 7.4rem); max-width: 14ch; }
  .hero h1 span { display: block; color: var(--mute); }
  .hero h1 .l { animation: lift 1s cubic-bezier(.2,.8,.2,1) both; }
  .hero h1 .l:nth-child(2) { animation-delay: .12s; }
  @keyframes lift { from { opacity: 0; transform: translateY(.35em); } to { opacity: 1; transform: none; } }
  .hero-p { margin-top: clamp(24px, 4vw, 40px); color: var(--mute); font-size: clamp(1.05rem, 1.6vw, 1.2rem); max-width: 54ch; }
  .hero-p strong { color: var(--ink); font-weight: 500; }
  .cta { display: flex; flex-wrap: wrap; gap: 12px; margin-top: 32px; }
  .btn { display: inline-flex; align-items: center; padding: 12px 22px; border-radius: 8px; text-decoration: none; font-weight: 500; font-size: .98rem; border: 1px solid var(--line2); transition: transform .2s, background .2s, border-color .2s; }
  .btn:hover { transform: translateY(-1px); }
  .btn-solid { background: var(--ink); color: var(--bg); border-color: var(--ink); }
  .btn-solid:hover { background: var(--accent); border-color: var(--accent); color: var(--accent-ink); }
  .btn-line:hover { border-color: var(--accent); background: var(--tint); }

  /* spotlight surfaces */
  .magic { --mx: 50%; --my: 50%; position: relative; transition: border-color .3s; }
  .magic::before { content: ""; position: absolute; inset: 0; border-radius: inherit; pointer-events: none; opacity: 0; transition: opacity .35s; background: radial-gradient(360px circle at var(--mx) var(--my), var(--tint), transparent 65%); }
  .magic::after { content: ""; position: absolute; inset: -1px; border-radius: inherit; padding: 1px; pointer-events: none; opacity: 0; transition: opacity .35s; background: radial-gradient(240px circle at var(--mx) var(--my), var(--accent), transparent 65%); -webkit-mask: linear-gradient(#000 0 0) content-box, linear-gradient(#000 0 0); -webkit-mask-composite: xor; mask: linear-gradient(#000 0 0) content-box exclude, linear-gradient(#000 0 0); }
  .magic:hover::before, .magic:hover::after, .magic:focus-within::before, .magic:focus-within::after { opacity: 1; }
  .magic > * { position: relative; z-index: 1; }

  /* product index in hero */
  .index { display: grid; grid-template-columns: repeat(3, 1fr); margin-top: clamp(48px, 7vw, 88px); border: 1px solid var(--line); border-radius: 12px; background: color-mix(in srgb, var(--panel) 70%, transparent); overflow: hidden; }
  .index a { display: block; padding: 22px 26px 24px; text-decoration: none; border-right: 1px solid var(--line); border-radius: 0; }
  .index a:last-child { border-right: 0; }
  .index h3 { font-size: 1.9rem; }
  .index p { color: var(--mute); font-size: .95rem; margin-top: 6px; }
  .index a .go { display: inline-block; margin-top: 14px; font-size: .88rem; color: var(--mute); transition: color .2s, transform .2s; }
  .index a:hover .go { color: var(--accent); transform: translateX(4px); }
  @media (max-width: 760px) { .index { grid-template-columns: 1fr; } .index a { border-right: 0; border-bottom: 1px solid var(--line); } .index a:last-child { border-bottom: 0; } }

  /* sections */
  .section { padding-block: clamp(72px, 11vw, 136px); }
  .section + .section { border-top: 1px solid var(--line); }
  .head { display: grid; grid-template-columns: 1fr 1.2fr; gap: 24px 56px; margin-bottom: clamp(36px, 6vw, 64px); align-items: end; }
  .head h2 { font-size: clamp(2.3rem, 5.4vw, 4.2rem); }
  .head p { color: var(--mute); }
  @media (max-width: 760px) { .head { grid-template-columns: 1fr; } }

  /* what I do */
  .rows { border-top: 1px solid var(--line); }
  .row { display: grid; grid-template-columns: 1fr 1.2fr; gap: 12px 56px; padding: 26px 20px; margin-inline: -20px; border-bottom: 1px solid var(--line); border-radius: 0; align-items: baseline; }
  .row h3 { font-size: clamp(1.5rem, 2.6vw, 2rem); }
  .row p { color: var(--mute); }
  @media (max-width: 760px) { .row { grid-template-columns: 1fr; gap: 6px; } }

  /* stages */
  .stages { display: grid; grid-template-columns: repeat(4, 1fr); border-top: 1px solid var(--line); position: relative; }
  .stage { text-align: left; background: none; border: 0; padding: 20px 12px 0 0; font-family: var(--serif); font-size: clamp(1.4rem, 2.8vw, 2rem); color: var(--mute); transition: color .25s; }
  .stage[aria-selected="true"] { color: var(--ink); }
  .stage:hover { color: var(--ink); }
  .stage-bar { position: absolute; top: -1px; left: 0; width: 25%; height: 2px; background: var(--accent); transition: transform .5s cubic-bezier(.2,.8,.2,1); }
  .stage-panel { margin-top: 28px; padding: 28px; border: 1px solid var(--line); border-radius: 12px; background: var(--panel); min-height: 130px; }
  .stage-panel h3 { font-size: clamp(1.5rem, 3vw, 2.1rem); }
  .stage-panel p { color: var(--mute); margin-top: 10px; }
  @media (max-width: 640px) { .stages { grid-template-columns: repeat(2, 1fr); } .stage-bar { display: none; } .stage { padding-bottom: 14px; border-bottom: 1px solid var(--line); } .stage[aria-selected="true"] { border-bottom-color: var(--accent); } }

  /* products */
  .product { padding-block: clamp(40px, 6vw, 72px); border-top: 1px solid var(--line); display: grid; grid-template-columns: .9fr 1.1fr; gap: clamp(28px, 5vw, 72px); align-items: start; }
  .product:first-of-type { border-top: 0; padding-top: 0; }
  .product h3 { font-size: clamp(2.6rem, 6vw, 4.6rem); }
  .tagline { font-family: var(--serif); font-style: italic; font-size: 1.35rem; color: var(--accent); margin-top: 10px; }
  .copy p { color: var(--mute); margin-top: 20px; }
  .tags { display: flex; flex-wrap: wrap; gap: 8px; margin-top: 24px; }
  .tag { padding: 6px 12px; border-radius: 6px; border: 1px solid var(--line2); background: transparent; font-size: .88rem; color: var(--mute); transition: border-color .2s, color .2s, background .2s; }
  button.tag:hover { border-color: var(--accent); color: var(--ink); }
  button.tag[aria-pressed="true"] { border-color: var(--accent); color: var(--accent); background: var(--tint); }
  .panel { border: 1px solid var(--line); border-radius: 14px; background: var(--panel); padding: 24px; min-height: 320px; }
  .panel-note { font-size: .84rem; color: var(--mute); margin-bottom: 16px; }
  @media (max-width: 860px) { .product { grid-template-columns: 1fr; } }

  /* hub */
  .hub svg { width: 100%; max-width: 300px; display: block; margin: 0 auto; }
  .hub .spoke { stroke: var(--line2); stroke-width: 1; transition: stroke .3s; }
  .hub .spoke.on { stroke: var(--accent); stroke-width: 1.5; }
  .hub .node { fill: var(--panel); stroke: var(--line2); stroke-width: 1.5; transform-box: fill-box; transform-origin: center; transition: transform .3s, fill .3s, stroke .3s; cursor: pointer; }
  .hub .node:hover { stroke: var(--accent); }
  .hub .node.on { fill: var(--accent); stroke: var(--accent); transform: scale(1.4); }
  .hub .core { fill: var(--panel); stroke: var(--accent); stroke-width: 1.5; }
  .hub text { font-family: var(--serif); font-size: 22px; fill: var(--ink); }
  .hub-desc { text-align: center; margin: 14px auto 0; min-height: 3.6em; }
  .hub-desc b { display: block; font-family: var(--serif); font-weight: 400; font-size: 1.5rem; }
  .hub-desc span { color: var(--mute); font-size: .96rem; }

  /* SRS */
  .consent { display: inline-flex; align-items: center; gap: 8px; font-size: .82rem; color: var(--accent); padding: 4px 10px; border-radius: 6px; border: 1px solid var(--line2); }
  .consent i { width: 7px; height: 7px; border-radius: 50%; background: var(--accent); }
  .transcript { list-style: none; padding: 0; margin: 14px 0; display: grid; gap: 4px; }
  .transcript li { display: grid; grid-template-columns: 48px 52px 1fr; gap: 8px; padding: 7px 10px; border-radius: 8px; font-size: .94rem; transition: background .3s; }
  .transcript time { font-family: var(--mono); font-size: .78rem; color: var(--mute); padding-top: 3px; }
  .transcript b { font-weight: 500; }
  .transcript li.hot { background: var(--tint); }
  .pipeline { display: flex; gap: 8px; flex-wrap: wrap; margin: 14px 0; }
  .pill { font-size: .8rem; padding: 3px 10px; border-radius: 6px; border: 1px solid var(--line2); color: var(--mute); transition: all .3s; }
  .pill.on { background: var(--accent); border-color: var(--accent); color: var(--accent-ink); }
  .pill.done { color: var(--accent); border-color: var(--accent); }
  .result { margin-top: 18px; padding-top: 18px; border-top: 1px solid var(--line); animation: lift .5s cubic-bezier(.2,.8,.2,1); }
  .result h4 { font-family: var(--serif); font-weight: 400; font-size: 1.3rem; margin-bottom: 4px; }
  .result p { font-size: .95rem; color: var(--mute); margin-bottom: 14px; }
  .actions { list-style: none; padding: 0; display: grid; gap: 6px; }
  .actions label { display: flex; gap: 10px; align-items: flex-start; font-size: .95rem; cursor: pointer; }
  .actions input { accent-color: var(--accent); margin-top: 5px; width: 16px; height: 16px; }
  .actions input:checked + span { text-decoration: line-through; color: var(--mute); }
  .run { padding: 9px 18px; border-radius: 8px; border: 1px solid var(--accent); background: transparent; color: var(--accent); font-weight: 500; font-size: .92rem; transition: background .2s, color .2s; }
  .run:hover:not(:disabled) { background: var(--accent); color: var(--accent-ink); }
  .run:disabled { opacity: .5; cursor: default; }

  /* radar */
  .radar svg { width: 100%; display: block; border: 1px solid var(--line); border-radius: 10px; }
  .radar .ringline { fill: none; stroke: var(--line); stroke-width: 1; }
  .radar .rad { fill: var(--tint); stroke: var(--accent); stroke-width: 1.5; transition: r .35s cubic-bezier(.2,.8,.2,1); }
  .radar .shop { fill: var(--line2); transition: fill .3s; }
  .radar .shop.in { fill: var(--accent); }
  .radar .you { fill: var(--ink); }
  .range { display: flex; align-items: center; gap: 14px; margin-top: 16px; font-size: .95rem; }
  .range input { flex: 1; accent-color: var(--accent); }
  .range output { font-family: var(--mono); font-size: .88rem; min-width: 3.4em; text-align: right; }
  .count { margin-top: 6px; color: var(--mute); }
  .count span { font-family: var(--serif); font-size: 1.8rem; color: var(--ink); margin-right: 4px; }

  /* learning + connect */
  .learn { display: flex; flex-wrap: wrap; gap: 10px 10px; }
  .learn span { padding: 10px 18px; border: 1px solid var(--line2); border-radius: 8px; font-family: var(--serif); font-size: 1.4rem; transition: border-color .2s, background .2s; }
  .learn span:hover { border-color: var(--accent); background: var(--tint); }
  .connect { text-align: left; }
  .connect h2 { font-size: clamp(2.6rem, 7.4vw, 6rem); max-width: 14ch; }
  .connect p { color: var(--mute); margin-top: 24px; }
  .connect .cta { margin-top: 32px; }
  .foot { padding-block: 28px 44px; color: var(--mute); font-size: .9rem; border-top: 1px solid var(--line); }

  @media (prefers-reduced-motion: reduce) {
    html { scroll-behavior: auto; }
    *, *::before, *::after { animation: none !important; transition: none !important; }
  }
</style>
</head>
<body>

<header class="nav">
  <div class="wrap nav-in">
    <a class="logo" href="#top" aria-label="Prince Raj, back to top">Prince Raj</a>
    <nav class="nav-links" aria-label="Sections">
      <a class="hide-sm" href="#work">Work</a>
      <a href="#products">Products</a>
      <a href="#contact">Contact</a>
      <button class="icon-btn" id="themeBtn" type="button" aria-label="Switch light or dark theme">
        <svg width="16" height="16" viewBox="0 0 16 16" aria-hidden="true"><circle cx="8" cy="8" r="6.2" fill="none" stroke="currentColor" stroke-width="1.4"/><path d="M8 1.8a6.2 6.2 0 0 1 0 12.4z" fill="currentColor"/></svg>
      </button>
    </nav>
  </div>
</header>

<main id="top">
  <section class="hero" id="hero">
    <div class="wrap hero-body">
      <h1><span class="l" style="color:var(--ink)">Real problems,</span><span class="l">built into products people use.</span></h1>
      <p class="hero-p"><strong>I'm Prince Raj,</strong> a founder and software developer. I work across AI, commerce and startup ecosystems, from defining the product and designing the experience to building the technology and taking it to real users.</p>
      <div class="cta">
        <a class="btn btn-solid" href="#products">View products</a>
        <a class="btn btn-line" href="https://www.linkedin.com/in/prince-raj-a15519301/" target="_blank" rel="noopener">LinkedIn</a>
      </div>

      <div class="index">
        <a class="magic" href="#monterus"><h3>Monterus X</h3><p>Startup ecosystem</p><span class="go">View</span></a>
        <a class="magic" href="#srs"><h3>SRS Vault AI</h3><p>Conversation intelligence</p><span class="go">View</span></a>
        <a class="magic" href="#niklit"><h3>Niklit</h3><p>Hyperlocal delivery</p><span class="go">View</span></a>
      </div>
    </div>
  </section>

  <section class="section" id="work">
    <div class="wrap">
      <div class="head">
        <h2>What I do</h2>
        <p>Technology products across AI, commerce, startup ecosystems and software engineering, with the product and the engineering kept close together.</p>
      </div>
      <div class="rows">
        <div class="magic row"><h3>Build products</h3><p>From idea to architecture, development and iteration.</p></div>
        <div class="magic row"><h3>Build startups</h3><p>Exploring products around AI, commerce and technology ecosystems.</p></div>
        <div class="magic row"><h3>Software development</h3><p>Web, mobile, APIs and databases.</p></div>
        <div class="magic row"><h3>AI product development</h3><p>Exploring practical applications of AI.</p></div>
        <div class="magic row"><h3>Product engineering</h3><p>Connecting business problems with technical solutions.</p></div>
        <div class="magic row"><h3>Continuous learning</h3><p>DSA, system design, architecture and modern development.</p></div>
      </div>
    </div>
  </section>

  <section class="section">
    <div class="wrap">
      <div class="head">
        <h2>How a product gets built</h2>
        <p>The same path every time. Select a stage.</p>
      </div>
      <div class="stages" role="tablist" aria-label="Stages" id="stages">
        <button class="stage" role="tab" id="s0" aria-selected="true" aria-controls="stagePanel">Idea</button>
        <button class="stage" role="tab" id="s1" aria-selected="false" aria-controls="stagePanel" tabindex="-1">Architecture</button>
        <button class="stage" role="tab" id="s2" aria-selected="false" aria-controls="stagePanel" tabindex="-1">Development</button>
        <button class="stage" role="tab" id="s3" aria-selected="false" aria-controls="stagePanel" tabindex="-1">Iteration</button>
        <span class="stage-bar" id="stageBar"></span>
      </div>
      <div class="stage-panel magic" id="stagePanel" role="tabpanel" aria-live="polite">
        <h3 id="stageTitle"></h3>
        <p id="stageText"></p>
      </div>
    </div>
  </section>

  <section class="section" id="products">
    <div class="wrap">
      <div class="head">
        <h2>Products I'm building</h2>
        <p>Three products. Each card has a small interactive piece you can try.</p>
      </div>

      <article class="product" id="monterus">
        <div class="copy">
          <h3>Monterus X</h3>
          <p class="tagline">Where startups meet their people.</p>
          <p>A startup ecosystem built around startups, investors, advertisers, creators and developers. A digital place where startups can find the right people, build visibility, reach growth opportunities and form stronger connections.</p>
          <div class="tags" id="areaTags" role="group" aria-label="Core areas of Monterus X"></div>
        </div>
        <div class="panel magic hub">
          <div class="panel-note">Select an area to see where it sits in the ecosystem.</div>
          <svg viewBox="0 0 300 300" id="hubSvg" role="img" aria-label="Eight core areas connected to Monterus X"></svg>
          <div class="hub-desc" id="hubDesc" aria-live="polite"></div>
        </div>
      </article>

      <article class="product" id="srs">
        <div class="copy">
          <h3>SRS Vault AI</h3>
          <p class="tagline">AI-powered conversation intelligence.</p>
          <p>Turns conversations into structured, actionable intelligence, so people can understand what was said, remember important discussions and turn them into action.</p>
          <div class="tags">
            <span class="tag">Consent-based recording</span><span class="tag">AI transcription</span><span class="tag">Summaries</span><span class="tag">Action items and follow-ups</span><span class="tag">Conversation analysis</span><span class="tag">Contact-specific history</span><span class="tag">Conversation preparation</span><span class="tag">Communication insights</span>
          </div>
        </div>
        <div class="panel magic">
          <div class="panel-note">Sample call, for illustration only.</div>
          <span class="consent"><i></i>Recorded with consent</span>
          <ul class="transcript" id="transcript">
            <li><time>00:04</time><b>Asha</b><span>Can we ship the pilot by the 15th?</span></li>
            <li><time>00:09</time><b>You</b><span>Yes, if legal signs off on the consent flow this week.</span></li>
            <li><time>00:17</time><b>Asha</b><span>I'll send the draft tomorrow. Can you share the pricing deck?</span></li>
            <li><time>00:24</time><b>You</b><span>Will do right after this call.</span></li>
          </ul>
          <div class="pipeline" aria-hidden="true"><span class="pill">Transcribe</span><span class="pill">Summarize</span><span class="pill">Find actions</span></div>
          <button class="run" id="analyze" type="button">Analyze call</button>
          <div class="result" id="result" hidden>
            <h4>Summary</h4>
            <p>Pilot targeted for the 15th, pending legal sign-off on the consent flow this week.</p>
            <h4>Action items</h4>
            <ul class="actions">
              <li><label><input type="checkbox"><span>Asha sends the consent flow draft tomorrow</span></label></li>
              <li><label><input type="checkbox"><span>You share the pricing deck after the call</span></label></li>
              <li><label><input type="checkbox"><span>Confirm legal sign-off before the 15th</span></label></li>
            </ul>
          </div>
        </div>
      </article>

      <article class="product" id="niklit">
        <div class="copy">
          <h3>Niklit</h3>
          <p class="tagline">Hyperlocal delivery.</p>
          <p>A delivery app built around what is close to you. Change the radius to see which shops come within reach.</p>
        </div>
        <div class="panel magic radar">
          <div class="panel-note">Illustrative map, not real data.</div>
          <svg viewBox="0 0 300 220" id="radar" role="img" aria-label="Map showing shops inside the chosen delivery radius"></svg>
          <div class="range">
            <label for="km">Radius</label>
            <input type="range" id="km" min="1" max="5" step="0.5" value="2">
            <output id="kmOut" for="km">2 km</output>
          </div>
          <div class="count" aria-live="polite"><span id="shopCount">0</span>shops in reach</div>
        </div>
      </article>
    </div>
  </section>

  <section class="section">
    <div class="wrap">
      <div class="head">
        <h2>Always learning</h2>
        <p>Sharpening the fundamentals so each product ships on a stronger base.</p>
      </div>
      <div class="learn">
        <span>DSA</span><span>System design</span><span>Architecture</span><span>AI</span><span>Modern development</span><span>Product development</span>
      </div>
    </div>
  </section>

  <section class="section connect" id="contact">
    <div class="wrap">
      <h2>Let's talk about what you're building.</h2>
      <p>A startup, an AI idea, or a product that needs to reach real users. I'd like to hear about it.</p>
      <div class="cta"><a class="btn btn-solid" href="https://www.linkedin.com/in/prince-raj-a15519301/" target="_blank" rel="noopener">Message me on LinkedIn</a></div>
    </div>
  </section>
</main>

<footer class="foot"><div class="wrap">Prince Raj</div></footer>

<script>
(function () {
  var reduce = window.matchMedia('(prefers-reduced-motion: reduce)').matches;
  var $ = function (s, r) { return (r || document).querySelector(s); };
  var $$ = function (s, r) { return Array.prototype.slice.call((r || document).querySelectorAll(s)); };

  /* theme */
  var root = document.documentElement;
  $('#themeBtn').addEventListener('click', function () {
    var cur = root.getAttribute('data-theme') || (window.matchMedia('(prefers-color-scheme: dark)').matches ? 'dark' : 'light');
    var next = cur === 'dark' ? 'light' : 'dark';
    root.setAttribute('data-theme', next);
    try { localStorage.setItem('pr-theme2', next); } catch (e) {}
  });

  /* hero grid follows cursor */
  var hero = $('#hero');
  hero.addEventListener('pointermove', function (e) {
    var r = hero.getBoundingClientRect();
    hero.style.setProperty('--gx', (e.clientX - r.left) + 'px');
    hero.style.setProperty('--gy', (e.clientY - r.top) + 'px');
  });

  /* spotlight */
  $$('.magic').forEach(function (el) {
    el.addEventListener('pointermove', function (e) {
      var r = el.getBoundingClientRect();
      el.style.setProperty('--mx', (e.clientX - r.left) + 'px');
      el.style.setProperty('--my', (e.clientY - r.top) + 'px');
    });
  });

  /* stages */
  var stages = [
    ['Start with the problem', 'Find a real problem and the people who have it. Define the product clearly before writing a line of code.'],
    ['Shape the architecture', 'Decide how the pieces fit together: data, APIs, and the parts that have to scale first.'],
    ['Build it end to end', 'Web, mobile, APIs and databases, built together so something real can reach users early.'],
    ['Learn and iterate', 'Watch how people actually use it, then tighten the product and the code together.']
  ];
  var tabs = $$('.stage'), bar = $('#stageBar');
  function pick(i, focus) {
    tabs.forEach(function (t, k) { t.setAttribute('aria-selected', k === i); t.tabIndex = k === i ? 0 : -1; });
    bar.style.transform = 'translateX(' + (i * 100) + '%)';
    $('#stageTitle').textContent = stages[i][0]; $('#stageText').textContent = stages[i][1];
    $('#stagePanel').setAttribute('aria-labelledby', 's' + i);
    if (focus) tabs[i].focus();
  }
  tabs.forEach(function (t, i) {
    t.addEventListener('click', function () { pick(i); });
    t.addEventListener('keydown', function (e) {
      if (e.key === 'ArrowRight') { e.preventDefault(); pick((i + 1) % 4, true); }
      if (e.key === 'ArrowLeft') { e.preventDefault(); pick((i + 3) % 4, true); }
    });
  });
  pick(0);

  /* svg helper */
  var NS = 'http://www.w3.org/2000/svg';
  function el(n, a) { var e = document.createElementNS(NS, n); for (var k in a) e.setAttribute(k, a[k]); return e; }

  /* Monterus hub */
  var areas = [
    ['Startup discovery', 'Startups get found by the people looking for them.'],
    ['Investors', 'Investors find startups worth a conversation.'],
    ['Advertising', 'Reach a startup-focused audience directly.'],
    ['Creators', 'Creators tell startup stories to more people.'],
    ['Developers', 'Developers connect with the startups building next.'],
    ['Data', 'Signals that show what is growing, and where.'],
    ['Wallet infrastructure', 'The payments layer that ties the ecosystem together.'],
    ['Growth', 'Visibility and opportunities that compound over time.']
  ];
  var svg = $('#hubSvg'), spokes = [], nodes = [], tagEls = [];
  function pos(i) { var a = (-90 + i * 45) * Math.PI / 180; return [150 + 108 * Math.cos(a), 150 + 108 * Math.sin(a)]; }
  areas.forEach(function (a, i) { var p = pos(i); var s = el('line', { x1: 150, y1: 150, x2: p[0], y2: p[1], 'class': 'spoke' }); svg.appendChild(s); spokes.push(s); });
  svg.appendChild(el('circle', { cx: 150, cy: 150, r: 36, 'class': 'core' }));
  var tx = el('text', { x: 150, y: 158, 'text-anchor': 'middle' }); tx.textContent = 'MX'; svg.appendChild(tx);
  areas.forEach(function (a, i) {
    var p = pos(i), n = el('circle', { cx: p[0], cy: p[1], r: 8, 'class': 'node' });
    n.addEventListener('click', function () { choose(i); });
    svg.appendChild(n); nodes.push(n);
    var b = document.createElement('button'); b.type = 'button'; b.className = 'tag'; b.textContent = a[0]; b.setAttribute('aria-pressed', 'false');
    b.addEventListener('click', function () { choose(i); });
    $('#areaTags').appendChild(b); tagEls.push(b);
  });
  function choose(i) {
    spokes.forEach(function (s, k) { s.setAttribute('class', 'spoke' + (k === i ? ' on' : '')); });
    nodes.forEach(function (n, k) { n.setAttribute('class', 'node' + (k === i ? ' on' : '')); });
    tagEls.forEach(function (t, k) { t.setAttribute('aria-pressed', k === i); });
    $('#hubDesc').innerHTML = '<b></b><span></span>';
    $('#hubDesc b').textContent = areas[i][0]; $('#hubDesc span').textContent = areas[i][1];
  }
  choose(0);

  /* SRS demo */
  var btn = $('#analyze'), lines = $$('#transcript li'), pills = $$('.pill'), res = $('#result'), running = false;
  function wait(ms) { return new Promise(function (r) { setTimeout(r, reduce ? 0 : ms); }); }
  btn.addEventListener('click', async function () {
    if (running) return;
    running = true; btn.disabled = true; res.hidden = true;
    pills.forEach(function (p) { p.className = 'pill'; });
    lines.forEach(function (l) { l.classList.remove('hot'); });
    pills[0].classList.add('on');
    for (var i = 0; i < lines.length; i++) { lines[i].classList.add('hot'); await wait(450); lines[i].classList.remove('hot'); }
    pills[0].className = 'pill done'; pills[1].classList.add('on'); await wait(700);
    pills[1].className = 'pill done'; pills[2].classList.add('on'); await wait(700);
    pills[2].className = 'pill done';
    res.hidden = false; btn.disabled = false; btn.textContent = 'Run again'; running = false;
  });

  /* Loklit radius */
  var rs = $('#radar'), cx = 150, cy = 110, sc = 21;
  var shopData = [[20,1.2],[75,2.4],[130,0.9],[190,3.1],[245,1.8],[300,2.7],[340,4.2],[45,4.4],[110,3.8],[160,4.9],[215,4.5],[270,3.6],[320,1.5],[5,3.4]];
  [1,2,3,4,5].forEach(function (k) { rs.appendChild(el('circle', { cx: cx, cy: cy, r: k * sc, 'class': 'ringline' })); });
  var rad = el('circle', { cx: cx, cy: cy, r: 42, 'class': 'rad' }); rs.appendChild(rad);
  var shopEls = shopData.map(function (s) {
    var a = s[0] * Math.PI / 180, c = el('circle', { cx: cx + Math.cos(a) * s[1] * sc, cy: cy + Math.sin(a) * s[1] * sc, r: 4, 'class': 'shop' });
    rs.appendChild(c); return c;
  });
  rs.appendChild(el('circle', { cx: cx, cy: cy, r: 5, 'class': 'you' }));
  var km = $('#km');
  function setKm() {
    var v = parseFloat(km.value), n = 0;
    rad.style.r = (v * sc) + 'px'; rad.setAttribute('r', v * sc);
    shopData.forEach(function (s, i) { var inside = s[1] <= v; if (inside) n++; shopEls[i].setAttribute('class', 'shop' + (inside ? ' in' : '')); });
    $('#kmOut').textContent = v + ' km'; $('#shopCount').textContent = n;
  }
  km.addEventListener('input', setKm); setKm();
})();
</script>
</body>
</html>
