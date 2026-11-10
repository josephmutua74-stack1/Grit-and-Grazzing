<title>Grit and Grazzing Dorpers</title>
<meta name="claude:viewport-fit-sides" content="cover">
<link id="site-fonts" rel="stylesheet" href="https://fonts.googleapis.com/css2?family=Bricolage+Grotesque:opsz,wght@12..96,700;12..96,800&family=Figtree:wght@400;500;600&display=swap">
<style id="site-css">
/* Layout: sticky site bar, owner tool strip (editors only), hero with latest story, story grid, sheep-for-sale grid.
   Mood: highland farm notebook. Soil-dark text on chalky green-grey ground, leaf green for actions,
   ear-tag yellow only on price tags. Two faces: Bricolage Grotesque for headlines, Figtree for everything else. */
:root {
  --bg: #eef0e6;
  --surface: #fbfbf6;
  --fg: #1b2a1e;
  --muted: #5a6a5d;
  --line: #d0d7c5;
  --leaf: #2d6a3e;
  --leaf-fg: #ffffff;
  --soil: #7a4a2e;
  --tag: #f0b429;
  --tag-fg: #1d1807;
  --wa: #1fa855;
  --danger: #b3261e;
  --note-bg: #e3ecd9;
  --display: "Bricolage Grotesque", "Trebuchet MS", system-ui, sans-serif;
  --body: "Figtree", system-ui, -apple-system, "Segoe UI", sans-serif;
}
@media (prefers-color-scheme: dark) {
  :root:not([data-theme="light"]) {
    --bg: #0f1612; --surface: #172019; --fg: #e5ece5; --muted: #98a99c; --line: #2a372d;
    --leaf: #62c18a; --leaf-fg: #0a1a10; --soil: #d0a07f; --danger: #ff8a80; --note-bg: #1b2d20; color-scheme: dark;
  }
}
:root[data-theme="dark"] {
  --bg: #0f1612; --surface: #172019; --fg: #e5ece5; --muted: #98a99c; --line: #2a372d;
  --leaf: #62c18a; --leaf-fg: #0a1a10; --soil: #d0a07f; --danger: #ff8a80; --note-bg: #1b2d20; color-scheme: dark;
}
* { box-sizing: border-box; }
body { background: var(--bg); color: var(--fg); font-family: var(--body); font-size: 16px; line-height: 1.5; padding-block: 0 48px; }
body::before { content: ""; position: fixed; inset: 0 0 auto; height: env(safe-area-inset-top, 0px); z-index: 30; background: var(--surface); }
a { color: inherit; }
.in { max-width: 1080px; margin: 0 auto; padding-left: max(16px, env(safe-area-inset-left, 0px)); padding-right: max(16px, env(safe-area-inset-right, 0px)); }
:focus-visible { outline: 3px solid var(--leaf); outline-offset: 2px; }
button { font-family: inherit; }
h1, h2, h3 { font-family: var(--display); letter-spacing: -0.02em; line-height: 1.1; margin: 0; text-wrap: balance; }
 
/* Site bar */
.bar { position: sticky; top: env(safe-area-inset-top, 0px); z-index: 20; background: var(--surface); border-bottom: 1px solid var(--line); }
.bar .in { display: flex; align-items: center; justify-content: space-between; gap: 8px 20px; flex-wrap: wrap; padding-block: 10px; }
.brand { display: flex; align-items: center; gap: 10px; text-decoration: none; font: 800 19px var(--display); letter-spacing: -0.02em; min-width: 0; }
.brand i { width: 14px; height: 18px; border-radius: 3px 3px 7px 7px; background: var(--tag); box-shadow: inset 0 0 0 1.5px rgba(0,0,0,.25); flex: none; }
.nav { display: flex; gap: 2px; }
.nav a { text-decoration: none; font-weight: 600; font-size: 14px; padding: 8px 12px; border-bottom: 3px solid transparent; color: var(--muted); }
.nav a[aria-current="page"] { color: var(--fg); border-bottom-color: var(--tag); }
 
/* Owner strip */
.owner { background: var(--note-bg); border-bottom: 1px solid var(--line); font-size: 14px; }
.owner .in { display: flex; gap: 8px; flex-wrap: wrap; align-items: center; padding-block: 10px; }
.owner b { margin-right: 4px; }
 
/* Buttons */
.btn { display: inline-flex; align-items: center; justify-content: center; min-height: 44px; padding: 0 18px; border-radius: 6px; font: 600 14px var(--body); text-decoration: none; cursor: pointer; border: 1.5px solid var(--leaf); color: var(--leaf); background: transparent; }
.btn.solid { background: var(--leaf); color: var(--leaf-fg); }
.btn.wa { background: var(--wa); border-color: var(--wa); color: #06210f; }
.btn.small { min-height: 36px; padding: 0 12px; font-size: 13px; }
.btn.danger { border-color: var(--danger); color: var(--danger); }
.btn[disabled] { opacity: .55; cursor: default; }
.linkbtn { background: none; border: 0; padding: 4px 0; color: var(--leaf); font: 600 13px var(--body); cursor: pointer; }
 
/* Hero */
.hero .in { display: grid; gap: 24px; padding-block: 32px 12px; align-items: center; }
@media (min-width: 820px) { .hero .in { grid-template-columns: 1.1fr 1fr; gap: 44px; padding-block: 48px 20px; } }
.eyebrow { font-size: 13px; font-weight: 600; letter-spacing: .06em; text-transform: uppercase; color: var(--soil); margin: 0 0 10px; }
.hero h1 { font-size: clamp(34px, 7vw, 58px); font-weight: 800; }
.hero p.lede { font-size: 18px; color: var(--muted); max-width: 46ch; margin: 14px 0 0; }
.hero .cta { display: flex; gap: 10px; flex-wrap: wrap; margin-top: 22px; }
.feature { display: block; text-decoration: none; position: relative; border-radius: 10px; overflow: hidden; background: var(--line); min-width: 0; }
.feature img { display: block; width: 100%; aspect-ratio: 4 / 3; object-fit: cover; max-width: 100%; }
.feature .cap { position: absolute; inset: auto 0 0 0; padding: 36px 16px 14px; color: #fff; background: linear-gradient(to top, rgba(10,20,12,.82), transparent); }
.feature .cap small { display: block; font-size: 12px; font-weight: 600; letter-spacing: .06em; text-transform: uppercase; opacity: .85; }
.feature .cap strong { font: 800 20px var(--display); letter-spacing: -0.01em; }
 
/* Sections */
section.block .in { padding-block: 36px 4px; }
.head { display: flex; align-items: baseline; justify-content: space-between; gap: 12px; margin-bottom: 18px; flex-wrap: wrap; }
.head h2 { font-size: clamp(24px, 4vw, 32px); font-weight: 800; }
.head a { font-weight: 600; font-size: 14px; color: var(--leaf); }
.page-title { padding-block: 30px 6px; }
.page-title h1 { font-size: clamp(30px, 6vw, 44px); font-weight: 800; }
.page-title p { color: var(--muted); margin: 8px 0 0; max-width: 56ch; }
 
/* Story cards */
.story { display: flex; flex-direction: column; text-decoration: none; background: var(--surface); border: 1px solid var(--line); border-radius: 8px; overflow: hidden; min-width: 0; }
.story .ph { position: relative; aspect-ratio: 3 / 2; background: var(--line); max-width: 100%; }
.story .ph img { width: 100%; height: 100%; object-fit: cover; display: block; }
.story .tx { padding: 14px; display: flex; flex-direction: column; gap: 6px; min-width: 0; }
.dateline { font-size: 12px; font-weight: 600; letter-spacing: .05em; text-transform: uppercase; color: var(--soil); }
.story h3 { font-size: 21px; font-weight: 700; }
.story p { margin: 0; color: var(--muted); font-size: 15px; }
.story.lead { margin-bottom: 16px; }
@media (min-width: 760px) {
  .story.lead { display: grid; grid-template-columns: 1.3fr 1fr; }
  .story.lead .ph { aspect-ratio: auto; min-height: 300px; }
  .story.lead .tx { padding: 24px; justify-content: center; gap: 10px; }
  .story.lead h3 { font-size: 30px; }
  .story.lead p { font-size: 16px; }
}
.cards { display: grid; gap: 16px; grid-template-columns: repeat(auto-fit, minmax(min(100%, 260px), 1fr)); }
.badge { position: absolute; top: 10px; left: 10px; background: rgba(20,30,24,.8); color: #fff; font-size: 11px; font-weight: 600; padding: 3px 9px; border-radius: 999px; letter-spacing: .03em; }
.badge.sold { background: var(--danger); color: #fff; }
.count { position: absolute; top: 10px; right: 10px; background: rgba(20,30,24,.8); color: #fff; font-size: 11px; font-weight: 600; padding: 3px 9px; border-radius: 999px; }
.manage { display: flex; gap: 6px; flex-wrap: wrap; padding: 0 14px 14px; }
 
/* Story page */
.article { max-width: 760px; margin: 0 auto; padding-block: 28px 12px; }
.article .back { font-size: 14px; font-weight: 600; color: var(--leaf); text-decoration: none; }
.article h1 { font-size: clamp(30px, 6vw, 46px); font-weight: 800; margin: 12px 0 14px; }
.article figure { margin: 22px 0; }
.article figure img { display: block; width: 100%; height: auto; min-height: 160px; background: var(--line); border-radius: 8px; }
.article figcaption { font-size: 13px; color: var(--muted); margin-top: 6px; }
.article p.para { font-size: 18px; line-height: 1.7; margin: 0 0 18px; max-width: 64ch; }
.article .manage { padding: 0; margin: 4px 0 8px; }
 
/* Sheep cards */
.sheep { background: var(--surface); border: 1px solid var(--line); border-radius: 8px; overflow: hidden; display: flex; flex-direction: column; min-width: 0; }
.sheep .ph { position: relative; aspect-ratio: 4 / 3; background: var(--line); max-width: 100%; }
.sheep .ph img { width: 100%; height: 100%; object-fit: cover; display: block; }
.sheep.sold .ph img { filter: grayscale(.8) brightness(.8); }
.price { position: absolute; left: 12px; bottom: 12px; background: var(--tag); color: var(--tag-fg); font: 800 19px var(--display); padding: 5px 12px 5px 22px; border-radius: 4px 14px 14px 4px; font-variant-numeric: tabular-nums; box-shadow: 0 2px 6px rgba(0,0,0,.25); }
.price::before { content: ""; position: absolute; left: 8px; top: 50%; width: 7px; height: 7px; margin-top: -3.5px; border-radius: 50%; background: var(--surface); box-shadow: inset 0 0 0 1px rgba(0,0,0,.3); }
.price span { font-size: 12px; font-weight: 600; margin-right: 3px; }
.age { position: absolute; right: 12px; bottom: 12px; background: rgba(20,30,24,.78); color: #fff; font-size: 12px; font-weight: 600; padding: 4px 10px; border-radius: 999px; }
.sheep .body { padding: 12px 14px 14px; display: flex; flex-direction: column; gap: 10px; flex: 1; }
.sheep .seller { font-weight: 600; margin: 0; }
.note { margin: 0; color: var(--muted); font-size: 14px; white-space: pre-line; }
.note.clamp { display: -webkit-box; -webkit-line-clamp: 3; -webkit-box-orient: vertical; overflow: hidden; }
.actions { display: grid; grid-template-columns: 1fr 1fr; gap: 8px; margin-top: auto; }
.num { display: flex; align-items: center; justify-content: space-between; gap: 8px; font-size: 13px; color: var(--muted); }
.num b { color: var(--fg); user-select: all; font-variant-numeric: tabular-nums; }
.toolbar { display: flex; gap: 8px; flex-wrap: wrap; margin-bottom: 16px; align-items: center; }
select, input, textarea { font: 16px var(--body); color: var(--fg); background: var(--surface); border: 1px solid var(--line); border-radius: 6px; padding: 11px 12px; width: 100%; }
.toolbar select { width: auto; }
 
/* States */
.state { text-align: center; color: var(--muted); padding: 40px 12px; border: 1px dashed var(--line); border-radius: 8px; }
.state strong { display: block; color: var(--fg); font: 700 18px var(--display); margin-bottom: 4px; }
.skel { height: 220px; border-radius: 8px; background: var(--line); opacity: .6; }
@media (prefers-reduced-motion: no-preference) { .skel { animation: pulse 1.4s ease-in-out infinite; } @keyframes pulse { 50% { opacity: .35; } } }
footer .in { padding-block: 40px 8px; color: var(--muted); font-size: 14px; display: grid; gap: 4px; }
footer b { color: var(--fg); user-select: all; }
 
/* Editor overlay */
.veil { position: fixed; inset: 0; z-index: 40; background: rgba(8,14,10,.6); display: flex; align-items: flex-end; justify-content: center; overflow-y: auto; padding-top: calc(16px + env(safe-area-inset-top, 0px)); }
@media (min-width: 640px) { .veil { align-items: flex-start; padding-block: 5vh; } }
.sheet { background: var(--surface); width: 100%; max-width: 560px; border-radius: 12px 12px 0 0; padding: 20px max(16px, env(safe-area-inset-left, 0px)) calc(24px + env(safe-area-inset-bottom, 0px)); display: grid; gap: 16px; }
@media (min-width: 640px) { .sheet { border-radius: 12px; padding-inline: 24px; } }
.sheet h2 { font-size: 24px; font-weight: 800; }
.sheet label.l { display: block; font-weight: 600; font-size: 14px; margin-bottom: 6px; }
.hint { color: var(--muted); font-size: 12px; margin: 5px 0 0; }
.err { color: var(--danger); font-size: 13px; margin: 5px 0 0; }
.row2 { display: grid; gap: 12px; grid-template-columns: 1fr 1fr; }
.drop { position: relative; display: flex; align-items: center; justify-content: center; aspect-ratio: 4 / 3; max-width: 100%; border: 2px dashed var(--line); border-radius: 8px; color: var(--muted); overflow: hidden; cursor: pointer; text-align: center; padding: 12px; font-size: 14px; }
.drop img { position: absolute; inset: 0; width: 100%; height: 100%; object-fit: cover; }
.drop input { position: absolute; width: 1px; height: 1px; opacity: 0; }
.drop:focus-within { outline: 3px solid var(--leaf); outline-offset: 2px; }
.plist { display: grid; gap: 10px; }
.pitem { display: grid; grid-template-columns: 72px 1fr auto; gap: 10px; align-items: center; }
.pitem img { width: 72px; height: 54px; object-fit: cover; border-radius: 4px; background: var(--line); }
.pitem input { padding: 8px 10px; font-size: 14px; }
.sheet .foot { display: flex; gap: 10px; justify-content: flex-end; flex-wrap: wrap; }
.check { display: flex; gap: 10px; align-items: center; font-size: 15px; }
.check input { width: 20px; height: 20px; }
.toast { position: fixed; left: 50%; transform: translateX(-50%); bottom: calc(20px + env(safe-area-inset-bottom, 0px)); background: var(--fg); color: var(--bg); padding: 10px 16px; border-radius: 6px; font-weight: 600; font-size: 14px; z-index: 60; max-width: calc(100% - 32px); }
</style>
 
<div id="root"></div>
<script type="application/json" id="site-data">{"site": {"farm": "Grit and Grazzing Dorpers", "place": "Nakuru County, Kenya", "tagline": "Stories from the farm, and healthy Dorper sheep for sale.", "intro": "", "phone": ""}, "stories": [{"id": "st-long-rains", "title": "The long rains came early", "place": "Njoro, Nakuru", "body": "The first rain fell on a Tuesday night, and by morning the red soil had turned dark and soft. We had been waiting three weeks for it. Everyone on the ridge was out before sunrise, walking their plots.\n\nBy the end of the week the maize was in, row after row across two acres. The pasture below the house greened faster than we expected, which meant the flock could graze again without us buying hay.\n\nThis is a sample story. Replace it with your own, add photos, and it will appear here for visitors.", "photos": [], "art": "field", "sample": true, "createdAt": 1794119400000}, {"id": "st-lambing", "title": "Twelve lambs in one week", "place": "Njoro, Nakuru", "body": "Lambing season never keeps a schedule. Between Monday and Saturday we counted twelve lambs, two of them twins, all on their feet within the hour.\n\nWe check the ewes at dawn and again after dark. A dry shelter and clean water matter more than anything else in the first days.\n\nThis is a sample story. Replace it with your own.", "photos": [], "art": "lambs", "sample": true, "createdAt": 1793601000000}, {"id": "st-dip-day", "title": "Dipping day on the ridge", "place": "Kajiado", "body": "Once a month the neighbours bring their flocks to the dip. It is part work and part meeting, with tea on the fence and news from every farm.\n\nA clean dip keeps ticks off the flock through the dry months, and it is cheaper than treating sick animals later.\n\nThis is a sample story. Replace it with your own.", "photos": [], "art": "dip", "sample": true, "createdAt": 1792996200000}], "sheep": [{"id": "sh-1", "art": "ram", "sample": true, "age": "8 months", "price": 6500, "name": "Sample Seller", "phone": "+254700000001", "note": "Sample listing. Dorper cross, dewormed and vaccinated. Buyer arranges transport.", "sold": false, "createdAt": 1794205800000}, {"id": "sh-2", "art": "red", "sample": true, "age": "1 year", "price": 9800, "name": "Sample Seller", "phone": "+254700000001", "note": "Sample listing. Red Maasai ram, strong frame. Delivery within the county can be arranged.", "sold": false, "createdAt": 1794119400000}, {"id": "sh-3", "art": "blk", "sample": true, "age": "14 months", "price": 11500, "name": "Sample Seller", "phone": "+254700000001", "note": "Sample listing. Blackhead Persian, good for breeding. Health card available.", "sold": false, "createdAt": 1794033000000}, {"id": "sh-4", "art": "lamb", "sample": true, "age": "6 months", "price": 5200, "name": "Sample Seller", "phone": "+254700000001", "note": "Sample listing. Weaned lamb, healthy and active. Pick-up only.", "sold": true, "createdAt": 1793946600000}]}</script>
<script id="site-code">
(function () {
  "use strict";
  // ---------- helpers ----------
  var esc = function (s) { return String(s == null ? "" : s).replace(/[&<>"']/g, function (c) { return { "&": "&amp;", "<": "&lt;", ">": "&gt;", '"': "&quot;", "'": "&#39;" }[c]; }); };
  var ksh = function (n) { return new Intl.NumberFormat("en-KE", { maximumFractionDigits: 0 }).format(n); };
  var fmtDate = function (t) { try { return new Date(t).toLocaleDateString("en-KE", { day: "numeric", month: "short", year: "numeric" }); } catch (e) { return ""; } };
  function normalizePhone(input) { // 0712345678, 712345678, 254712345678, +254 712 345 678 -> +254712345678
    var d = String(input).replace(/[^\d+]/g, "").replace(/^\+/, "");
    if (d.indexOf("0") === 0) d = "254" + d.slice(1); else if (/^[17]\d{8}$/.test(d)) d = "254" + d;
    return /^254[17]\d{8}$/.test(d) ? "+" + d : null;
  }
  var prettyPhone = function (e) { var l = "0" + String(e).slice(4); return l.slice(0, 4) + " " + l.slice(4, 7) + " " + l.slice(7); };
  var $ = function (s, r) { return (r || document).querySelector(s); };
  var toastTimer;
  function toast(m) { var t = $("#toast"); t.textContent = m; t.hidden = false; clearTimeout(toastTimer); toastTimer = setTimeout(function () { t.hidden = true; }, 2800); }
  var SHELL = "<header class=\"bar\">\n  <div class=\"in\">\n    <a class=\"brand\" href=\"#home\" id=\"brand\"><i></i><span id=\"brandName\">Farm</span></a>\n    <nav class=\"nav\" id=\"nav\" aria-label=\"Main\">\n      <a href=\"#home\" data-nav=\"home\">Home</a>\n      <a href=\"#stories\" data-nav=\"stories\">Stories</a>\n      <a href=\"#sheep\" data-nav=\"sheep\">Sheep for sale</a>\n    </nav>\n  </div>\n</header>\n<div id=\"owner\" class=\"owner\" hidden></div>\n<main id=\"app\"></main>\n<footer id=\"foot\"></footer>\n<div id=\"overlay\"></div>\n<div id=\"toast\" class=\"toast\" role=\"status\" hidden></div>";
  $("#root").innerHTML = SHELL;
 
  // ---------- illustrations for sample content (inline SVG, no network) ----------
  var svgURI = function (s) { return "data:image/svg+xml;utf8," + encodeURIComponent(s); };
  function sheepGroup(x, y, k, p) {
    var fl = [[-34,-6,22],[-8,-14,25],[18,-8,24],[-18,10,20],[8,12,21]].map(function (c) {
      return '<circle cx="' + (x + c[0] * k) + '" cy="' + (y + c[1] * k) + '" r="' + (c[2] * k) + '" fill="' + p.fleece + '" stroke="' + p.edge + '" stroke-width="1.5"/>';
    }).join("");
    return '<g fill="' + p.face + '"><rect x="' + (x - 22 * k) + '" y="' + (y + 18 * k) + '" width="' + (7 * k) + '" height="' + (30 * k) + '" rx="3"/><rect x="' + (x + 12 * k) + '" y="' + (y + 18 * k) + '" width="' + (7 * k) + '" height="' + (30 * k) + '" rx="3"/></g>' + fl +
      '<g fill="' + p.face + '"><ellipse cx="' + (x + 42 * k) + '" cy="' + (y - 2 * k) + '" rx="' + (15 * k) + '" ry="' + (19 * k) + '"/><ellipse cx="' + (x + 31 * k) + '" cy="' + (y - 14 * k) + '" rx="' + (5 * k) + '" ry="' + (9 * k) + '" transform="rotate(-40 ' + (x + 31 * k) + ' ' + (y - 14 * k) + ')"/></g><circle cx="' + (x + 46 * k) + '" cy="' + (y - 7 * k) + '" r="' + (2 * k) + '" fill="#111"/>';
  }
  var PAL = {
    ram:  { bg: "#cfe3c4", ground: "#9fbf86", fleece: "#f3efe4", edge: "#cfc8b4", face: "#3b2f2a" },
    red:  { bg: "#e8d9bd", ground: "#c9ad7c", fleece: "#b5573a", edge: "#8f3f27", face: "#6b2f1e" },
    blk:  { bg: "#d6e4ea", ground: "#a6bfa0", fleece: "#e9e4d6", edge: "#c2bba5", face: "#241c18" },
    lamb: { bg: "#f0e2c8", ground: "#b9c68e", fleece: "#faf7ee", edge: "#d9d2bd", face: "#6a5a50" }
  };
  function art(key) {
    var p = PAL[key];
    if (key === "field") {
      var rows = ""; for (var i = 0; i < 9; i++) rows += '<path d="M' + (200 + (i - 4) * 14) + ' 150 L' + (i * 52 - 30) + ' 300" stroke="#3f7a3f" stroke-width="' + (3 + i % 3) + '" opacity=".75"/>';
      return svgURI('<svg xmlns="http://www.w3.org/2000/svg" viewBox="0 0 400 300"><rect width="400" height="300" fill="#cfe6ef"/><circle cx="310" cy="60" r="26" fill="#f6d86a"/><path d="M0 150 Q90 100 200 140 T400 120 V300 H0Z" fill="#7fae6a"/><path d="M0 170 Q120 140 240 165 T400 150 V300 H0Z" fill="#5c9356"/><path d="M60 300 L200 150 L340 300Z" fill="#8a5a3a"/>' + rows + '</svg>');
    }
    if (key === "lambs") {
      var q = PAL.lamb;
      return svgURI('<svg xmlns="http://www.w3.org/2000/svg" viewBox="0 0 400 300"><rect width="400" height="300" fill="' + q.bg + '"/><rect y="200" width="400" height="100" fill="' + q.ground + '"/>' + sheepGroup(130, 170, 1.3, PAL.ram) + sheepGroup(290, 215, 0.7, q) + '</svg>');
    }
    if (key === "dip") {
      var d = PAL.blk, fence = ""; for (var j = 0; j < 8; j++) fence += '<rect x="' + (20 + j * 50) + '" y="120" width="8" height="90" fill="#7a5a3a"/>';
      return svgURI('<svg xmlns="http://www.w3.org/2000/svg" viewBox="0 0 400 300"><rect width="400" height="300" fill="#dfe8ec"/><rect y="210" width="400" height="90" fill="#b3c4a0"/>' + fence + '<rect x="10" y="140" width="380" height="8" fill="#7a5a3a"/><rect x="10" y="175" width="380" height="8" fill="#7a5a3a"/>' + sheepGroup(150, 215, 1.0, d) + sheepGroup(290, 225, 0.8, PAL.ram) + '</svg>');
    }
    p = p || PAL.ram;
    return svgURI('<svg xmlns="http://www.w3.org/2000/svg" viewBox="0 0 400 300"><rect width="400" height="300" fill="' + p.bg + '"/><rect y="228" width="400" height="72" fill="' + p.ground + '"/>' + sheepGroup(190, 170, 1.7, p) + '</svg>');
  }
  var imgOf = function (it) { return it.photoId ? "/_blob/" + it.photoId : art(it.art || "field"); };
  var storyCover = function (s) { return s.photos && s.photos.length ? "/_blob/" + s.photos[0].id : art(s.art || "field"); };
 
  // ---------- state ----------
  var S = { site: null, stories: [], sheep: [], canEdit: false, assets: null, sort: "new", expanded: {}, ed: null };
  var DEF = { farm: "Grit and Grazzing Dorpers", place: "Nakuru County, Kenya", tagline: "Stories from the farm, and healthy sheep for sale.", intro: "", phone: "" };
  var site = function () { var s = S.site || {}; return { farm: s.farm || DEF.farm, place: s.place || DEF.place, tagline: s.tagline || DEF.tagline, intro: s.intro || "", phone: s.phone || "" }; };
  var isLoading = function () { return false; };
  var canManage = function () { return S.canEdit && !!S.assets; };
 
  // ---------- views ----------
  function storyCard(s, lead) {
    var n = s.photos ? s.photos.length : 0;
    var ex = String(s.body || "").replace(/\s+/g, " ").trim(); if (ex.length > 150) ex = ex.slice(0, 150).replace(/\s\S*$/, "") + "…";
    return '<a class="story' + (lead ? " lead" : "") + '" href="#story-' + esc(s.id) + '"><div class="ph"><img src="' + storyCover(s) + '" alt="" loading="' + (lead ? "eager" : "lazy") + '" decoding="async">' +
      (s.sample ? '<span class="badge">Sample</span>' : "") + (n > 1 ? '<span class="count">' + n + ' photos</span>' : "") + '</div><div class="tx"><div class="dateline">' + esc(s.place || "") + (s.place ? " · " : "") + fmtDate(s.createdAt) + '</div><h3>' + esc(s.title) + '</h3><p>' + esc(ex) + '</p></div></a>';
  }
  function sheepCard(l) {
    var name = l.name || "the seller";
    var msg = "Hi " + name + ", I am interested in your sheep listed for Ksh " + ksh(l.price) + " (Age: " + l.age + ").";
    var phone = l.phone || "";
    var wa = "https://wa.me/" + phone.replace(/\D/g, "") + "?text=" + encodeURIComponent(msg);
    var open = S.expanded[l.id], long = l.note && l.note.length > 100;
    var buy = l.sold ? '<p class="note"><b>Sold.</b> Check back for new listings.</p>' :
      '<div class="actions"><a class="btn" href="tel:' + esc(phone) + '">Call Seller</a><a class="btn wa" href="' + esc(wa) + '" target="_blank" rel="noopener noreferrer">WhatsApp Seller</a></div>' +
      '<div class="num"><span>Number: <b>' + esc(prettyPhone(phone)) + '</b></span><button class="linkbtn" data-act="copy" data-v="' + esc(phone) + '">Copy</button></div>';
    var mg = canManage() ? '<div class="manage" style="padding:0"><button class="btn small" data-act="edit-sheep" data-id="' + esc(l.id) + '">Edit</button><button class="btn small" data-act="sold" data-id="' + esc(l.id) + '">' + (l.sold ? "Mark available" : "Mark sold") + '</button><button class="btn small danger" data-act="del-sheep" data-id="' + esc(l.id) + '">Delete</button></div>' : "";
    return '<article class="sheep' + (l.sold ? " sold" : "") + '"><div class="ph"><img src="' + imgOf(l) + '" alt="Sheep, ' + esc(l.age) + ', Ksh ' + ksh(l.price) + '" loading="lazy" decoding="async">' +
      (l.sold ? '<span class="badge sold">Sold</span>' : l.sample ? '<span class="badge">Sample</span>' : "") +
      '<div class="price"><span>Ksh</span>' + ksh(l.price) + '</div><div class="age">' + esc(l.age) + '</div></div><div class="body"><p class="seller">' + esc(l.name) + '</p>' +
      (l.note ? '<p class="note' + (open ? "" : " clamp") + '">' + esc(l.note) + '</p>' + (long ? '<button class="linkbtn" style="align-self:flex-start" data-act="more" data-id="' + esc(l.id) + '">' + (open ? "Show less" : "Read more") + '</button>' : "") : "") +
      buy + mg + '</div></article>';
  }
  var skeletons = function (n) { var h = ""; for (var i = 0; i < n; i++) h += '<div class="skel"></div>'; return '<div class="cards">' + h + '</div>'; };
  function stateBox(title, text, btn) { return '<div class="state"><strong>' + esc(title) + '</strong>' + esc(text) + (btn || "") + '</div>'; }
  var addStoryBtn = function () { return canManage() ? '<div style="margin-top:14px"><button class="btn solid" data-act="new-story">Write a story</button></div>' : ""; };
  var addSheepBtn = function () { return canManage() ? '<div style="margin-top:14px"><button class="btn solid" data-act="new-sheep">List a sheep</button></div>' : ""; };
 
  function sheepSorted() {
    var a = S.sheep.slice();
    a.sort(function (x, y) {
      if (!!x.sold !== !!y.sold) return x.sold ? 1 : -1;
      return S.sort === "low" ? x.price - y.price : S.sort === "high" ? y.price - x.price : (y.createdAt || 0) - (x.createdAt || 0);
    });
    return a;
  }
 
  function vHome() {
    var st = site(), latest = S.stories[0], rest = S.stories.slice(1, 4), sh = sheepSorted().filter(function (x) { return !x.sold; }).slice(0, 3);
    var feat = latest ? '<a class="feature" href="#story-' + esc(latest.id) + '"><img src="' + storyCover(latest) + '" alt="" decoding="async"><div class="cap"><small>Latest story</small><strong>' + esc(latest.title) + '</strong></div></a>' :
      '<div class="feature"><img src="' + art("field") + '" alt=""></div>';
    var h = '<section class="hero"><div class="in"><div><p class="eyebrow">' + esc(st.place) + '</p><h1>' + esc(st.farm) + '</h1><p class="lede">' + esc(st.tagline) + '</p>' +
      (st.intro ? '<p class="lede" style="font-size:16px">' + esc(st.intro) + '</p>' : "") +
      '<div class="cta"><a class="btn solid" href="#stories">Read the stories</a><a class="btn" href="#sheep">See sheep for sale</a></div></div>' + feat + '</div></section>';
    h += '<section class="block"><div class="in"><div class="head"><h2>Stories from the farm</h2><a href="#stories">All stories</a></div>';
    if (isLoading("stories")) h += skeletons(3);
    else if (!S.stories.length) h += stateBox("No stories yet", "Stories with photos from the farm will appear here.", addStoryBtn());
    else h += storyCard(latest, true) + (rest.length ? '<div class="cards">' + rest.map(function (s) { return storyCard(s); }).join("") + '</div>' : "");
    h += '</div></section><section class="block"><div class="in"><div class="head"><h2>Sheep for sale</h2><a href="#sheep">All sheep</a></div>';
    if (isLoading("sheep")) h += skeletons(3);
    else if (!sh.length) h += stateBox("No sheep listed right now", "New listings will appear here.", addSheepBtn());
    else h += '<div class="cards">' + sh.map(sheepCard).join("") + '</div>';
    return h + '</div></section>';
  }
  function vStories() {
    var h = '<div class="in page-title"><h1>Stories</h1><p>Seasons, lambing, rains and the daily work, with photos from the farm.</p></div><div class="in" style="padding-block:18px 4px">';
    if (isLoading("stories")) h += skeletons(3);
    else if (!S.stories.length) h += stateBox("No stories yet", "Stories with photos from the farm will appear here.", addStoryBtn());
    else h += storyCard(S.stories[0], true) + (S.stories.length > 1 ? '<div class="cards">' + S.stories.slice(1).map(function (s) { return storyCard(s); }).join("") + '</div>' : "");
    return h + '</div>';
  }
  function vSheep() {
    var h = '<div class="in page-title"><h1>Sheep for sale</h1><p>Prices in Ksh. Call or WhatsApp the seller directly to arrange viewing and delivery.</p></div><div class="in" style="padding-block:18px 4px">';
    if (isLoading("sheep")) return h + skeletons(3) + '</div>';
    if (!S.sheep.length) return h + stateBox("No sheep listed right now", "New listings will appear here.", addSheepBtn()) + '</div>';
    h += '<div class="toolbar"><label for="sort" style="font-size:14px;font-weight:600">Sort</label><select id="sort"><option value="new"' + (S.sort === "new" ? " selected" : "") + '>Newest first</option><option value="low"' + (S.sort === "low" ? " selected" : "") + '>Price: low to high</option><option value="high"' + (S.sort === "high" ? " selected" : "") + '>Price: high to low</option></select></div>';
    return h + '<div class="cards">' + sheepSorted().map(sheepCard).join("") + '</div></div>';
  }
  function vStory(id) {
    var s = S.stories.filter(function (x) { return x.id === id; })[0];
    if (!s) return '<div class="in article">' + (isLoading("stories") ? skeletons(1) : stateBox("Story not found", "It may have been removed.", '<div style="margin-top:14px"><a class="btn" href="#stories">Back to stories</a></div>')) + '</div>';
    var photos = s.photos && s.photos.length ? s.photos : [{ id: "", art: s.art || "field", cap: "" }];
    var fig = function (p) { return '<figure><img src="' + (p.id ? "/_blob/" + p.id : art(p.art)) + '" alt="' + esc(p.cap || s.title) + '" loading="lazy" decoding="async">' + (p.cap ? '<figcaption>' + esc(p.cap) + '</figcaption>' : "") + '</figure>'; };
    var paras = String(s.body || "").split(/\n\s*\n/).filter(function (x) { return x.trim(); }), rest = photos.slice(1), h = "";
    paras.forEach(function (p, i) { h += '<p class="para">' + esc(p.trim()).replace(/\n/g, "<br>") + '</p>' + (rest[i] ? fig(rest[i]) : ""); });
    for (var k = paras.length; k < rest.length; k++) h += fig(rest[k]);
    var mg = canManage() ? '<div class="manage"><button class="btn small" data-act="edit-story" data-id="' + esc(s.id) + '">Edit story</button><button class="btn small danger" data-act="del-story" data-id="' + esc(s.id) + '">Delete</button></div>' : "";
    return '<div class="in"><article class="article"><a class="back" href="#stories">← All stories</a><h1>' + esc(s.title) + '</h1><div class="dateline">' + esc(s.place || "") + (s.place ? " · " : "") + fmtDate(s.createdAt) + (s.sample ? " · Sample" : "") + '</div>' + mg + fig(photos[0]) + h + '<p><a class="btn" href="#sheep">See sheep for sale</a></p></article></div>';
  }
 
  function chrome() {
    var st = site();
    $("#brandName").textContent = st.farm;
    document.title = st.farm;
    var ow = $("#owner");
    if (S.canEdit) {
      ow.hidden = false;
      ow.innerHTML = '<div class="in">' + (canManage() ?
        '<b>Editing</b><button class="btn small solid" data-act="new-story">Write a story</button><button class="btn small solid" data-act="new-sheep">List a sheep</button><button class="btn small" data-act="edit-site">Farm details</button>' +
        ((S.stories.concat(S.sheep)).some(function (x) { return x.sample; }) ? '<button class="btn small danger" data-act="rm-samples">Remove sample content</button>' : "") :
        '<span>You can edit this site, but photo upload is not available in this view.</span>') + '</div>';
    } else { ow.hidden = true; ow.innerHTML = ""; }
    var phone = st.phone ? '<span>Call or WhatsApp: <b>' + esc(prettyPhone(st.phone)) + '</b></span>' : "";
    $("#foot").innerHTML = '<div class="in"><span><b style="font-family:var(--display)">' + esc(st.farm) + '</b> · ' + esc(st.place) + '</span>' + phone + '<span>' + "Prices are in Kenya shillings (Ksh)." + '</span></div>';
  }
 
  var lastRoute = null;
  function render() {
    var hash = (location.hash || "#home").slice(1), view = "home", arg = "";
    if (hash === "stories") view = "stories"; else if (hash === "sheep") view = "sheep"; else if (hash.indexOf("story-") === 0) { view = "story"; arg = hash.slice(6); }
    var html =
      view === "stories" ? vStories() : view === "sheep" ? vSheep() : view === "story" ? vStory(arg) : vHome();
    var keep = window.scrollY;
    $("#app").innerHTML = html;
    document.querySelectorAll("[data-nav]").forEach(function (a) {
      var on = a.dataset.nav === (view === "story" ? "stories" : view);
      if (on) a.setAttribute("aria-current", "page"); else a.removeAttribute("aria-current");
    });
    chrome();
    if (lastRoute !== hash) { window.scrollTo(0, 0); lastRoute = hash; } else window.scrollTo(0, keep);
  }
  window.addEventListener("hashchange", render);
 
  // ---------- images: resize and re-encode before upload (low bandwidth) ----------
  function compress(file) {
    return new Promise(function (res, rej) {
      var img = new Image(), url = URL.createObjectURL(file);
      img.onload = function () {
        var s = Math.min(1, 1000 / Math.max(img.width, img.height)), cv = document.createElement("canvas");
        cv.width = Math.round(img.width * s); cv.height = Math.round(img.height * s);
        cv.getContext("2d").drawImage(img, 0, 0, cv.width, cv.height); URL.revokeObjectURL(url);
        cv.toBlob(function (b) {
          if (b && b.type === "image/webp") return res(b);
          cv.toBlob(function (j) { j ? res(j) : rej(new Error("encode")); }, "image/jpeg", 0.72);
        }, "image/webp", 0.72);
      };
      img.onerror = function () { URL.revokeObjectURL(url); rej(new Error("read")); };
      img.src = url;
    });
  }
  function uploadFile(file) {
    if (file.type.indexOf("image/") !== 0) return Promise.reject({ code: "type" });
    if (file.size > 20 * 1024 * 1024) return Promise.reject({ code: "big" });
    return compress(file).then(function (b) { return S.assets.upload(b, { type: b.type }); }).then(function (r) { return r.id; });
  }
  function uploadMsg(e) {
    var c = e && e.code;
    return c === "type" ? "Choose an image file." : c === "big" ? "That photo is too large." : c === "quota_or_state" ? "Photo storage is full." : c === "rate_limited" ? "Too many uploads. Wait a moment." : "Photo upload failed. Check your connection.";
  }
 
  // ---------- saving: the page republishes itself with the content embedded, so any visitor can read it ----------
  var FLASH = "gg-flash", PENDING = "gg-pending-delete", GOTO = "gg-goto";
  var ss = {
    get: function (k) { try { return sessionStorage.getItem(k); } catch (e) { return null; } },
    set: function (k, v) { try { sessionStorage.setItem(k, v); } catch (e) {} },
    del: function (k) { try { sessionStorage.removeItem(k); } catch (e) {} }
  };
  var RESET = ":root{color-scheme:light;padding-block:env(safe-area-inset-top,0px) env(safe-area-inset-bottom,0px)}body{margin:0;font:14px system-ui,sans-serif}img{max-width:100%}[hidden]{display:none!important}";
 
  // Rebuild the full page from its own parts (stylesheet, code) plus the new content.
  function buildHtml(data) {
    var hs = document.head && document.head.querySelector("style");
    var reset = hs && hs.textContent && hs.textContent.length < 2000 ? hs.textContent : RESET;
    var json = JSON.stringify(data).replace(/</g, "\\u003c").replace(new RegExp(String.fromCharCode(8232), "g"), "\\u2028").replace(new RegExp(String.fromCharCode(8233), "g"), "\\u2029");
    var title = esc((data.site && data.site.farm) || "Grit and Grazzing Dorpers");
    return "<!doctype html><html><head><meta charset=utf8><meta name=viewport content=\"width=device-width,initial-scale=1,viewport-fit=cover\"><style>" + reset + "</style></head><body>" +
      "<title>" + title + "</title>\n<meta name=\"claude:viewport-fit-sides\" content=\"cover\">\n" + $("#site-fonts").outerHTML + "\n" +
      "<style id=\"site-css\">" + $("#site-css").textContent + "</style>\n<div id=\"root\"></div>\n" +
      "<script type=\"application/json\" id=\"site-data\">" + json + "<\/script>\n<script id=\"site-code\">" + $("#site-code").textContent + "<\/script></body></html>";
  }
 
  // Apply a change to a copy of the content, publish it, and let the page reload to the new version.
  function commit(mutate, opts) {
    opts = opts || {};
    var data = JSON.parse(JSON.stringify({ site: S.site || {}, stories: S.stories, sheep: S.sheep }));
    mutate(data);
    return claude.use("artifact").then(function (a) {
      if (!a) throw { code: "not_granted" };
      if (opts.msg) ss.set(FLASH, opts.msg);
      if (opts.go) ss.set(GOTO, opts.go);
      if (opts.drop && opts.drop.length) ss.set(PENDING, JSON.stringify(opts.drop));
      return a.publish(buildHtml(data));
    }).catch(function (e) {
      ss.del(FLASH); ss.del(GOTO); ss.del(PENDING);
      var c = e && e.code;
      toast(c === "conflict" ? "The site changed elsewhere. Reloading the latest version." :
        c === "not_writer" || c === "not_granted" ? "You can view this site but not change it." :
        c === "rate_limited" ? "Too many saves. Wait a moment and try again." :
        c === "too_large" ? "The site is too large to save. Remove some content." : "Could not save. Check your connection and try again.");
      throw e;
    });
  }
  var byNew = function (a, b) { return (b.createdAt || 0) - (a.createdAt || 0); };
  var idsOf = function (photos) { return (photos || []).map(function (p) { return p.id; }); };
 
  // ---------- editors ----------
  function showErr(k, m) { var el = $("#e-" + k); if (el) { el.textContent = m || ""; el.hidden = !m; } }
  function closeEd() { S.ed = null; $("#overlay").innerHTML = ""; document.body.style.overflow = ""; }
  function discardUploads() { // photos uploaded in an editor that was cancelled are not used anywhere
    var ed = S.ed; if (!ed || !S.assets) return;
    if (ed.kind === "story") {
      var keep = {}; idsOf(ed.base && ed.base.photos).forEach(function (i) { keep[i] = 1; });
      ed.photos.forEach(function (p) { if (!keep[p.id]) S.assets.delete(p.id).catch(function () {}); });
    }
    if (ed.kind === "sheep" && ed.photoId && ed.photoId !== (ed.base && ed.base.photoId)) S.assets.delete(ed.photoId).catch(function () {});
  }
  function cancelEd() { discardUploads(); closeEd(); }
  function openSheet(inner) {
    $("#overlay").innerHTML = '<div class="veil" data-act="veil"><div class="sheet" role="dialog" aria-modal="true">' + inner + '</div></div>';
    document.body.style.overflow = "hidden";
    var f = $("#overlay input, #overlay textarea"); if (f && f.type !== "file") f.focus();
  }
  var field = function (id, label, input, extra) { return '<div><label class="l" for="' + id + '">' + label + '</label>' + input + (extra || "") + '<p class="err" id="e-' + id + '" hidden></p></div>'; };
  function saving(label) { var b = $("#save"); if (b) { b.disabled = true; b.textContent = label || "Saving…"; } }
  function saveFailed() { if (S.ed) S.ed.busy = false; var b = $("#save"); if (b) { b.disabled = false; b.textContent = "Try again"; } }
 
  function openStory(id) {
    var s = id ? S.stories.filter(function (x) { return x.id === id; })[0] : null;
    S.ed = { kind: "story", id: id || null, base: s || null, photos: ((s && s.photos) || []).map(function (p) { return { id: p.id, cap: p.cap || "" }; }), busy: false };
    openSheet('<h2>' + (s ? "Edit story" : "Write a story") + '</h2>' +
      field("title", "Title", '<input id="title" maxlength="120" placeholder="e.g. The long rains came early" value="' + esc(s ? s.title : "") + '">') +
      field("place", "Place (optional)", '<input id="place" maxlength="80" placeholder="e.g. Njoro, Nakuru" value="' + esc(s ? s.place || "" : "") + '">') +
      field("body", "Story", '<textarea id="body" rows="9" maxlength="8000" placeholder="Tell it the way you would tell a neighbour. Leave a blank line between paragraphs.">' + esc(s ? s.body : "") + '</textarea>') +
      '<div><label class="l">Photos</label><div class="plist" id="plist"></div><p class="hint">The first photo is the cover. Add up to 8. Each is shrunk before upload to save data.</p>' +
      '<label class="btn small" style="margin-top:8px;position:relative" id="addph">Add photos<input id="files" type="file" accept="image/*" multiple style="position:absolute;width:1px;height:1px;opacity:0"></label><p class="err" id="e-photos" hidden></p></div>' +
      '<div class="foot"><button class="btn" data-act="close">Cancel</button><button class="btn solid" id="save" data-act="save-story">' + (s ? "Save changes" : "Publish story") + '</button></div>');
    drawPhotos();
  }
  function drawPhotos() {
    var el = $("#plist"); if (!el || !S.ed) return;
    el.innerHTML = S.ed.photos.length ? S.ed.photos.map(function (p, i) {
      return '<div class="pitem"><img src="/_blob/' + esc(p.id) + '" alt=""><input data-cap="' + i + '" maxlength="140" placeholder="Caption (optional)" value="' + esc(p.cap) + '" aria-label="Caption for photo ' + (i + 1) + '"><button class="btn small" type="button" data-act="rm-photo" data-i="' + i + '">Remove</button></div>';
    }).join("") : '<p class="hint">' + (S.ed.base && S.ed.base.art ? "This sample story uses a drawing. Add a photo to replace it." : "No photos yet.") + '</p>';
  }
  function readCaptions() { document.querySelectorAll("[data-cap]").forEach(function (i) { if (S.ed.photos[+i.dataset.cap]) S.ed.photos[+i.dataset.cap].cap = i.value.trim(); }); }
  function saveStory() {
    var ed = S.ed; if (!ed || ed.busy) return;
    var title = $("#title").value.trim(), place = $("#place").value.trim(), body = $("#body").value.trim(), bad = false;
    function chk(k, c, m) { showErr(k, c ? m : ""); if (c) bad = true; }
    chk("title", title.length < 3, "Give the story a title.");
    chk("body", body.length < 20, "Write at least a couple of sentences.");
    chk("photos", !ed.photos.length && !(ed.base && ed.base.art), "Add at least one photo.");
    if (bad) return;
    readCaptions();
    var id = ed.id || ("st-" + Date.now().toString(36));
    var doc = { id: id, title: title, place: place, body: body, photos: ed.photos, createdAt: (ed.base && ed.base.createdAt) || Date.now(), updatedAt: Date.now() };
    if (!ed.photos.length && ed.base) { doc.art = ed.base.art; doc.sample = !!ed.base.sample; }
    var kept = idsOf(ed.photos), gone = idsOf(ed.base && ed.base.photos).filter(function (i) { return kept.indexOf(i) < 0; });
    ed.busy = true; saving();
    commit(function (d) {
      var i = d.stories.findIndex(function (x) { return x.id === id; });
      if (i > -1) d.stories[i] = doc; else d.stories.unshift(doc);
      d.stories.sort(byNew);
    }, { msg: ed.id ? "Story saved" : "Story published", go: ed.id ? null : "story-" + id, drop: gone }).catch(saveFailed);
  }
 
  function openSheep(id) {
    var s = id ? S.sheep.filter(function (x) { return x.id === id; })[0] : null;
    S.ed = { kind: "sheep", id: id || null, base: s || null, photoId: s ? s.photoId || "" : "", busy: false };
    openSheet('<h2>' + (s ? "Edit listing" : "List a sheep") + '</h2>' +
      '<div><label class="l">Photo</label><label class="drop" id="drop"><span id="dropText"' + (s ? " hidden" : "") + '>Tap to take or choose a photo</span><img id="pv" alt="Selected sheep" ' + (s ? 'src="' + imgOf(s) + '"' : "hidden") + '><input id="file" type="file" accept="image/*"></label><p class="err" id="e-photo" hidden></p></div>' +
      '<div class="row2">' + field("age", "Age", '<input id="age" maxlength="40" placeholder="8 months" value="' + esc(s ? s.age : "") + '">') +
      field("price", "Price (Ksh)", '<input id="price" type="number" inputmode="numeric" min="1" step="1" placeholder="8500" value="' + (s ? s.price : "") + '">') + '</div>' +
      field("sname", "Seller name", '<input id="sname" maxlength="80" autocomplete="name" value="' + esc(s ? s.name : "") + '">') +
      field("phone", "Phone number", '<input id="phone" type="tel" inputmode="tel" placeholder="0712 345 678" value="' + esc(s ? prettyPhone(s.phone) : (site().phone ? prettyPhone(site().phone) : "")) + '">') +
      field("note", "Note to buyer (optional)", '<textarea id="note" rows="4" maxlength="500" placeholder="Location, vaccination status, delivery terms">' + esc(s ? s.note || "" : "") + '</textarea>') +
      '<label class="check"><input id="sold" type="checkbox"' + (s && s.sold ? " checked" : "") + '> Mark as sold</label>' +
      '<div class="foot"><button class="btn" data-act="close">Cancel</button><button class="btn solid" id="save" data-act="save-sheep">' + (s ? "Save changes" : "Post listing") + '</button></div>');
  }
  function saveSheep() {
    var ed = S.ed; if (!ed || ed.busy) return;
    var age = $("#age").value.trim(), price = Number($("#price").value), name = $("#sname").value.trim(), phone = normalizePhone($("#phone").value), note = $("#note").value.trim(), bad = false;
    function chk(k, c, m) { showErr(k, c ? m : ""); if (c) bad = true; }
    chk("photo", !ed.photoId && !(ed.base && ed.base.art), "Add a clear photo of the sheep.");
    chk("age", !age, "Enter the age, e.g. 8 months.");
    chk("price", !(Number.isInteger(price) && price > 0 && price <= 10000000), "Enter a valid price in Ksh.");
    chk("sname", name.length < 2, "Enter the seller name.");
    chk("phone", !phone, "Enter a valid Kenyan number, e.g. 0712 345 678.");
    chk("note", note.length > 500, "Keep the note under 500 characters.");
    if (bad) return;
    var id = ed.id || ("sh-" + Date.now().toString(36));
    var doc = { id: id, age: age, price: price, name: name, phone: phone, note: note, sold: $("#sold").checked, createdAt: (ed.base && ed.base.createdAt) || Date.now() };
    if (ed.photoId) doc.photoId = ed.photoId; else if (ed.base) { doc.art = ed.base.art; doc.sample = !!ed.base.sample; }
    var gone = ed.base && ed.base.photoId && ed.base.photoId !== ed.photoId ? [ed.base.photoId] : [];
    ed.busy = true; saving();
    commit(function (d) {
      var i = d.sheep.findIndex(function (x) { return x.id === id; });
      if (i > -1) d.sheep[i] = doc; else d.sheep.unshift(doc);
      d.sheep.sort(byNew);
    }, { msg: ed.id ? "Listing saved" : "Listing posted", drop: gone }).catch(saveFailed);
  }
 
  function openSite() {
    var st = site(); S.ed = { kind: "site", busy: false };
    openSheet('<h2>Farm details</h2>' + field("farm", "Farm name", '<input id="farm" maxlength="60" value="' + esc(st.farm) + '">') +
      field("place", "Place", '<input id="place" maxlength="80" value="' + esc(st.place) + '">') +
      field("tagline", "One-line description", '<input id="tagline" maxlength="140" value="' + esc(st.tagline) + '">') +
      field("intro", "About the farm (optional)", '<textarea id="intro" rows="4" maxlength="600">' + esc(st.intro) + '</textarea>') +
      field("phone", "Contact phone (shown in the footer, used as default for listings)", '<input id="phone" type="tel" inputmode="tel" placeholder="0712 345 678" value="' + esc(st.phone ? prettyPhone(st.phone) : "") + '">') +
      '<div class="foot"><button class="btn" data-act="close">Cancel</button><button class="btn solid" id="save" data-act="save-site">Save</button></div>');
  }
  function saveSite() {
    var ed = S.ed; if (!ed || ed.busy) return;
    var farm = $("#farm").value.trim(), phoneRaw = $("#phone").value.trim(), phone = phoneRaw ? normalizePhone(phoneRaw) : "", bad = false;
    showErr("farm", farm.length < 2 ? "Enter the farm name." : ""); if (farm.length < 2) bad = true;
    showErr("phone", phoneRaw && !phone ? "Enter a valid Kenyan number." : ""); if (phoneRaw && !phone) bad = true;
    if (bad) return;
    var next = { farm: farm, place: $("#place").value.trim(), tagline: $("#tagline").value.trim(), intro: $("#intro").value.trim(), phone: phone || "" };
    ed.busy = true; saving();
    commit(function (d) { d.site = next; }, { msg: "Saved" }).catch(saveFailed);
  }
 
  // ---------- events ----------
  var armed = {};
  function confirmThen(btn, fn) { // two taps to delete, no browser dialogs
    var k = btn.dataset.act + (btn.dataset.id || "");
    if (armed[k]) { clearTimeout(armed[k]); delete armed[k]; fn(); return; }
    var old = btn.textContent; btn.textContent = "Tap again to confirm";
    armed[k] = setTimeout(function () { delete armed[k]; btn.textContent = old; }, 3000);
  }
  document.addEventListener("change", function (e) {
    if (e.target.id === "sort") { S.sort = e.target.value; render(); return; }
    var ed = S.ed;
    if (e.target.id === "file" && ed && ed.kind === "sheep" && S.assets) {
      var f = e.target.files && e.target.files[0]; if (!f) return;
      showErr("photo", ""); $("#dropText").textContent = "Uploading…"; $("#dropText").hidden = false;
      uploadFile(f).then(function (id) {
        if (ed.photoId && ed.photoId !== (ed.base && ed.base.photoId)) S.assets.delete(ed.photoId).catch(function () {});
        ed.photoId = id; var pv = $("#pv"); pv.src = "/_blob/" + id; pv.hidden = false; $("#dropText").hidden = true;
      }, function (er) { $("#dropText").textContent = "Tap to take or choose a photo"; showErr("photo", uploadMsg(er)); });
    }
    if (e.target.id === "files" && ed && ed.kind === "story" && S.assets) {
      var list = Array.prototype.slice.call(e.target.files || []).slice(0, Math.max(0, 8 - ed.photos.length)); e.target.value = ""; if (!list.length) return;
      showErr("photos", ""); var lab = $("#addph"); lab.firstChild.textContent = "Uploading…";
      readCaptions();
      list.reduce(function (p, f) {
        return p.then(function () { return uploadFile(f).then(function (id) { ed.photos.push({ id: id, cap: "" }); drawPhotos(); }); });
      }, Promise.resolve()).then(function () { lab.firstChild.textContent = "Add photos"; }, function (er) { lab.firstChild.textContent = "Add photos"; showErr("photos", uploadMsg(er)); });
    }
  });
  document.addEventListener("click", function (e) {
    var b = e.target.closest("[data-act]"); if (!b) return;
    var act = b.dataset.act, id = b.dataset.id;
    if (act === "veil") { if (e.target === b) cancelEd(); return; }
    if (act === "close") return cancelEd();
    if (act === "more") { S.expanded[id] = !S.expanded[id]; return render(); }
    if (act === "copy") {
      var ok = function () { toast("Number copied"); }, no = function () { toast("Select the number to copy it"); };
      try { navigator.clipboard.writeText(b.dataset.v).then(ok, no); } catch (x) { no(); } return;
    }
    if (!canManage()) return;
    if (act === "new-story") return openStory();
    if (act === "edit-story") return openStory(id);
    if (act === "new-sheep") return openSheep();
    if (act === "edit-sheep") return openSheep(id);
    if (act === "edit-site") return openSite();
    if (act === "save-story") return saveStory();
    if (act === "save-sheep") return saveSheep();
    if (act === "save-site") return saveSite();
    if (act === "rm-photo") {
      readCaptions();
      var gone = S.ed.photos.splice(+b.dataset.i, 1)[0];
      if (gone && idsOf(S.ed.base && S.ed.base.photos).indexOf(gone.id) < 0) S.assets.delete(gone.id).catch(function () {}); // only if the live page never used it
      return drawPhotos();
    }
    if (act === "sold") {
      var l = S.sheep.filter(function (x) { return x.id === id; })[0]; if (!l) return;
      b.disabled = true;
      return commit(function (d) { d.sheep.forEach(function (x) { if (x.id === id) x.sold = !x.sold; }); }, { msg: l.sold ? "Marked available" : "Marked sold" }).catch(function () { b.disabled = false; });
    }
    if (act === "del-story") return confirmThen(b, function () {
      var s = S.stories.filter(function (x) { return x.id === id; })[0];
      commit(function (d) { d.stories = d.stories.filter(function (x) { return x.id !== id; }); }, { msg: "Story deleted", go: "stories", drop: idsOf(s && s.photos) }).catch(function () {});
    });
    if (act === "del-sheep") return confirmThen(b, function () {
      var l = S.sheep.filter(function (x) { return x.id === id; })[0];
      commit(function (d) { d.sheep = d.sheep.filter(function (x) { return x.id !== id; }); }, { msg: "Listing deleted", drop: l && l.photoId ? [l.photoId] : [] }).catch(function () {});
    });
    if (act === "rm-samples") return confirmThen(b, function () {
      commit(function (d) { d.stories = d.stories.filter(function (x) { return !x.sample; }); d.sheep = d.sheep.filter(function (x) { return !x.sample; }); }, { msg: "Sample content removed" }).catch(function () {});
    });
  });
  document.addEventListener("keydown", function (e) { if (e.key === "Escape" && S.ed) cancelEd(); });
 
  // ---------- boot: the content is already in the page, so everyone sees it immediately ----------
  var data = {};
  try { data = JSON.parse($("#site-data").textContent) || {}; } catch (e) { data = {}; }
  S.site = data.site || null;
  S.stories = (data.stories || []).slice().sort(byNew);
  S.sheep = (data.sheep || []).slice().sort(byNew);
  var go = ss.get(GOTO); if (go) { ss.del(GOTO); location.hash = go; }
  render();
  var flash = ss.get(FLASH); if (flash) { ss.del(FLASH); toast(flash); }
  (async function () {
    if (!window.claude || !window.claude.use) return;
    try { var u = await claude.use("user"); S.canEdit = u ? !!(await u.canEdit()) : false; } catch (e) {}
    if (!S.canEdit) return; // visitors get the read-only site
    try { S.assets = await claude.use("assets"); } catch (e) {}
    render();
    var pend = ss.get(PENDING); // photos removed in the last save are no longer used by the live page
    if (pend && S.assets) { ss.del(PENDING); try { JSON.parse(pend).forEach(function (i) { S.assets.delete(i).catch(function () {}); }); } catch (e) {} }
  })();
})();
</script>