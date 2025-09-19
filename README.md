<!--
Save this file as `greeting.svg` (or `greeting.html`) in your repo and embed it in your README.md like this:

For SVG file in repo:

![greeting](./greeting.svg)

Or open `greeting.html` in a browser to preview and export a GIF if you prefer.
-->

<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="utf-8" />
  <meta name="viewport" content="width=device-width, initial-scale=1" />
  <title>Animated Greeting — for GitHub README</title>
</head>
<body style="display:flex;align-items:center;justify-content:center;height:100vh;background:#0f1724;margin:0;">

<!-- This is an inline SVG animation. GitHub can render raw SVG files in README.
     It first shows: "hello coders </>" then transitions to: "I'm Benziane Younes" -->

<svg id="greeting" xmlns="http://www.w3.org/2000/svg" width="800" height="200" viewBox="0 0 800 200">
  <defs>
    <linearGradient id="g" x1="0" x2="1">
      <stop offset="0%" stop-color="#60a5fa" />
      <stop offset="100%" stop-color="#a78bfa" />
    </linearGradient>
    <style>
      .bg { fill: transparent; }
      .line { font-family: Inter, Roboto, system-ui, -apple-system, Arial; font-weight:700; font-size:42px; }
      .sub { font-size:28px; font-weight:600; }

      /* animation timing: total 4.5s loop */
      .hello { opacity:0; transform-origin:400px 100px; }
      .name  { opacity:0; transform-origin:400px 100px; }

      /* keyframes */
      @keyframes enterHello {
        0%   { opacity: 0; transform: translateY(10px) scale(0.98); }
        10%  { opacity: 1; transform: translateY(0px) scale(1); }
        45%  { opacity: 1; }
        55%  { opacity: 0; transform: translateY(-8px) scale(0.98); }
        100% { opacity: 0; }
      }

      @keyframes enterName {
        0%   { opacity: 0; transform: translateY(10px) scale(0.98); }
        50%  { opacity: 0; }
        60%  { opacity: 1; transform: translateY(0px) scale(1); }
        100% { opacity: 1; }
      }

      /* apply animations and make them loop */
      .hello { animation: enterHello 4.5s cubic-bezier(.2,.9,.2,1) infinite; }
      .name  { animation: enterName 4.5s cubic-bezier(.2,.9,.2,1) infinite; }

      /* subtle glowing code-brackets style */
      .bracket { font-family: monospace; font-size:42px; opacity:0.9; }
      .small-muted { fill: #94a3b8; }
    </style>
  </defs>

  <!-- subtle rounded rect background -->
  <rect x="6" y="6" width="788" height="188" rx="16" fill="#0b1220" stroke="#0f1724" stroke-width="0" />

  <!-- HELLO CODERS -->
  <g class="hello" id="helloText" transform="translate(0,0)">
    <text x="50%" y="70" text-anchor="middle" class="line" fill="url(#g)">
      hello coders <tspan class="bracket">&lt;/&gt;</tspan>
    </text>
    <text x="50%" y="115" text-anchor="middle" class="sub small-muted" fill="#9fb0d3">
      welcome to my GitHub
    </text>
  </g>

  <!-- I'M BENZIANE YOUNES -->
  <g class="name" id="nameText" transform="translate(0,0)">
    <text x="50%" y="82" text-anchor="middle" class="line" fill="white">
      I'm <tspan fill="url(#g)">Benziane Younes</tspan>
    </text>
    <text x="50%" y="130" text-anchor="middle" class="sub small-muted" fill="#9fb0d3">
      Front‑end Developer • Algeria
    </text>
  </g>

</svg>

</body>
</html>
