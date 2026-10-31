# Anhang A: Alle Farbangaben im CSS

Automatisch aus index.html (Version 3.0) ausgelesen: jeder Selektor mit seinen Farb-Deklarationen. Variablen wie var(--accent) werden zur Laufzeit gesetzt (siehe DESIGN.md).

| Selektor | Deklarationen |
| --- | --- |
| `:root` | `--accent:#ffe600; --on:#000; --nr:#ff3b30; --line:rgba(255,255,255,.1); --muted:rgba(255,255,255,.55)` |
| `html,body` | `background:#000; color:#fff` |
| `input,select` | `color:#fff` |
| `.pill` | `background:rgba(28,28,30,.92); border:1px solid #2c2c2e` |
| `.pill .sm` | `color:#999` |
| `.round` | `background:rgba(28,28,30,.92); border:1px solid #2c2c2e; color:#ccc` |
| `.menu` | `background:rgba(28,28,30,.97); border:1px solid #2c2c2e; box-shadow:0 20px 50px rgba(0,0,0,.6)` |
| `.menu button` | `color:#aaa` |
| `.menu button.on` | `background:#2c2c2e; color:#fff` |
| `.dots i` | `background:rgba(255,255,255,.3)` |
| `.dots i.on` | `background:#fff` |
| `.card` | `background:#1c1c1e` |
| `.tint` | `background:#ff1e00` |
| `.btn` | `background:#2c2c2e` |
| `/* Digitaluhr schwebend */ .w-clock-float` | `background:#000` |
| `/* Analog */ .w-clock-analog` | `background:#000` |
| `.analog` | `color:#fff` |
| `/* Weltkarte */ .w-solar` | `background:#000` |
| `.solar` | `color:#fff` |
| `/* Weltzeit-Liste */ .w-world` | `background:#000` |
| `/* Weitere Uhren */ .w-clock-stack` | `background:#000` |
| `.w-clock-outline` | `background:#000` |
| `.w-analog-numbers,.w-analog-arc` | `background:#000` |
| `.demo-b` | `background:color-mix(in srgb,currentColor 16%,transparent)` |
| `#demoTag` | `color:#ff9f0a` |
| `.ag` | `-webkit-mask-image:linear-gradient(#000 82%,transparent); mask-image:linear-gradient(#000 82%,transparent)` |
| `.w-week` | `background:#000` |
| `.wk-e` | `background:color-mix(in srgb,var(--c,var(--accent)) 28%,#000)` |
| `/* Farbwahl direkt im Dashboard */ #pal` | `background:rgba(16,16,18,.94); box-shadow:0 -10px 40px rgba(0,0,0,.5)` |
| `.pal-l` | `color:#999` |
| `.combo` | `background:#232326` |
| `.combo.on,.single.on` | `border-color:#fff` |
| `.single` | `box-shadow:inset 0 0 0 3px #101012` |
| `.pal-c label` | `color:#bbb` |
| `.pal-c input::-webkit-color-swatch` | `border:2px solid #333` |
| `/* Typo-Widgets */ .w-clock-words` | `background:#000` |
| `.w-countdown` | `background:#000` |
| `.cd small` | `color:#fff` |
| `.w-clock-flap,.w-clock-flap-classic` | `background:#000` |
| `.fl>div` | `background:#1c1c1e` |
| `.fl::after` | `background:#000` |
| `body.night .fl>div` | `background:#1a0302!important` |
| `.w-station` | `background:#000; --dial:#f4f4f1; --ink2:#111; --sec:#c62828` |
| `body.night .w-station` | `--dial:#000` |
| `.w-clock-flap-classic .fl,.w-clock-flap-classic .fl-d` | `color:#f2f2ee` |
| `.ck-need span` | `background:color-mix(in srgb,var(--fg) 13%,transparent)` |
| `.addmod` | `border:2px dashed #3a3a3c; color:#8e8e93` |
| `.ed-size` | `background:rgba(58,58,60,.96); color:#fff; box-shadow:0 2px 8px rgba(0,0,0,.5)` |
| `#eInfo` | `color:#aaa` |
| `.card.empty` | `border:2px dashed #3a3a3c` |
| `.ed-del` | `background:#3a3a3c; color:#fff; box-shadow:0 2px 8px rgba(0,0,0,.5)` |
| `.ed-add` | `background:rgba(58,58,60,.96); color:#fff; box-shadow:0 2px 10px rgba(0,0,0,.5)` |
| `#ebar` | `background:rgba(28,28,30,.96); --fg:#fff; --bg:#000` |
| `#eName` | `background:#111; border:1px solid #333` |
| `.lay` | `background:#2c2c2e; color:#8e8e93` |
| `.lay.on` | `background:#fff; color:#000` |
| `#gal` | `background:rgba(12,12,14,.97)` |
| `.gal-i` | `color:#ccc` |
| `#pdots i` | `background:rgba(255,255,255,.3)` |
| `#pdots i.on` | `background:#fff` |
| `/* Neue Wetter- und Info-Kacheln */ .w-forecast,.w-temp-chart,.w-rain-chart,.w-wx-combo,.w-sun,.w-uv,.w-pollen,.w-wiki,.w-pegel,.w-radio` | `background:#0e0e10; --fg:#fff; --bg:#0e0e10` |
| `.fc-bar` | `background:rgba(255,255,255,.12)` |
| `.uv-bar` | `background:linear-gradient(90deg,#3ea72d 0 27%,#fff300 27% 55%,#f18b00 55% 73%,#e53210 73% 100%)` |
| `.uv-bar i` | `background:#fff; box-shadow:0 0 0 2px #000` |
| `.pl-b` | `background:rgba(255,255,255,.12)` |
| `.pg-n small` | `color:#fff` |
| `.live` | `color:#000` |
| `.sp-nocov` | `background:linear-gradient(140deg,color-mix(in srgb,var(--accent) 70%,#000),#000)!important` |
| `.sp-dv` | `background:rgba(0,0,0,.45); color:#fff` |
| `/* Detail-Fenster */ #pop` | `background:rgba(0,0,0,.62)` |
| `.pop-in` | `background:#121214; border:1px solid #2c2c2e` |
| `.px-grid>div` | `background:#1c1c1e` |
| `.pc-b p` | `color:#ccc` |
| `.pn` | `color:#fff` |
| `.spp-now img,.spp-ph` | `background:linear-gradient(140deg,var(--accent),#000)` |
| `.spp-seek` | `background:#333` |
| `.spp-ctl button` | `color:#ccc` |
| `.spp-ctl .pp` | `background:#fff; color:#000` |
| `.spp-vol` | `color:#ccc` |
| `/* Hinweis-Toast */ #toast` | `background:rgba(40,40,42,.97); color:#fff; box-shadow:0 10px 30px rgba(0,0,0,.5)` |
| `/* Stil-Bibliothek */ #lib` | `background:#0c0c0e` |
| `.lib-p` | `color:#bbb` |
| `.lib-x textarea` | `background:#111; border:1px solid #333; color:#fff` |
| `.lib-sw small` | `color:#999` |
| `.lib-sw span` | `color:#bbb` |
| `.lib-f>div` | `background:#1c1c1e` |
| `.lib-f>div.on` | `border-color:#fff` |
| `.lib-f span` | `color:#aaa` |
| `.lib-g>div` | `color:#aaa` |
| `.lib-b small` | `color:#aaa` |
| `.lib-d span` | `color:#bbb` |
| `.G>.slot.dragging .card` | `box-shadow:0 18px 40px rgba(0,0,0,.6)` |
| `.ed-pg button` | `background:rgba(58,58,60,.96); color:#fff` |
| `/* Die Gestirne in allen Größen */ .w-gestirne` | `background:#dcd8cd; color:#111` |
| `/* Wetter */ .w-weather` | `background:linear-gradient(#4a8ad9,#22599f)` |
| `.w-weather.wx-night` | `background:linear-gradient(#152342,#04070f)` |
| `.w-weather.wx-cloud` | `background:linear-gradient(#6f7d8e,#3a4552)` |
| `.w-weather.wx-rain` | `background:linear-gradient(#4d5967,#202730)` |
| `.w-weather.wx-snow` | `background:linear-gradient(#93a6ba,#56677a)` |
| `.w-weather.wx-storm` | `background:linear-gradient(#3b3550,#151220)` |
| `.wx-row` | `border-top:1px solid rgba(255,255,255,.22)` |
| `/* Spotify vollflächig */ .w-spotify` | `background:#121212` |
| `.sp-shade` | `background:linear-gradient(to top,rgba(0,0,0,.85),rgba(0,0,0,.15) 55%,rgba(0,0,0,.35))` |
| `.sp-a` | `color:rgba(255,255,255,.75)` |
| `.sp-d` | `color:#1ed760` |
| `.sp-bar` | `background:rgba(255,255,255,.25)` |
| `.sp-bar i` | `background:#fff` |
| `.sp-ctl .pp` | `background:#fff; color:#000` |
| `.sp-err` | `color:#ff8a80` |
| `/* Fotos */ .w-photos` | `background:#000` |
| `.ph-shade` | `background:linear-gradient(rgba(0,0,0,.45),transparent 30%)` |
| `/* Nachrichten */ .w-news` | `background:#000` |
| `.nw-big` | `color:#fff` |
| `.nw li` | `background:rgba(255,255,255,.06)` |
| `.nw a` | `color:#fff` |
| `.fitbox.fade` | `-webkit-mask-image:linear-gradient(#000 75%,transparent); mask-image:linear-gradient(#000 75%,transparent)` |
| `.ghost` | `background:color-mix(in srgb,var(--fg) 14%,transparent)` |
| `.w-recipe .shade,.rc .shade` | `background:linear-gradient(to top,rgba(0,0,0,.88),rgba(0,0,0,.1) 65%)` |
| `.hub input` | `background:#1c1c1e` |
| `.chips button` | `background:#1c1c1e; color:#bbb` |
| `.cbtn` | `background:color-mix(in srgb,var(--fg) 13%,transparent)` |
| `.seg button::after` | `background:color-mix(in srgb,var(--fg) 18%,transparent)` |
| `.seg button.done::after` | `background:color-mix(in srgb,var(--fg) 55%,transparent)` |
| `.drawer` | `border:2px solid color-mix(in srgb,var(--fg) 25%,transparent); box-shadow:0 20px 60px rgba(0,0,0,.5)` |
| `.drawer li` | `border-bottom:1px solid color-mix(in srgb,var(--fg) 15%,transparent)` |
| `.un-f input` | `background:color-mix(in srgb,var(--fg) 10%,transparent)` |
| `.un-i span` | `color:#fff; text-shadow:0 1px 3px #000` |
| `/* Einstellungen */ #modal` | `background:rgba(0,0,0,.85)` |
| `.sheet` | `background:#161618; border:1px solid #2c2c2e` |
| `.sec` | `background:#1f1f22; border:1px solid #2c2c2e` |
| `.lbl` | `color:#999` |
| `.sec input[type=text],.sec input[type=url],.sec select` | `background:#111; border:1px solid #333` |
| `.sec p` | `color:#999` |
| `.badge` | `background:#333; color:#ccc` |
| `.badge.ok` | `background:#14532d; color:#bbf7d0` |
| `.themes button` | `border:1px solid #2c2c2e; background:#1a1a1c` |
| `.themes button.on` | `border-color:#fff` |
| `.tog input[type=time]` | `background:#111; border:1px solid #333; color:#fff` |
| `.sec textarea` | `background:#111; border:1px solid #333; color:#fff` |
| `.wc-row label` | `background:#2c2c2e` |
| `.fontb` | `background:#232326` |
| `.fontb.on` | `border-color:#fff` |
| `.fontb span` | `color:#aaa` |
| `.de` | `border:1px solid #333` |
| `.de-slot` | `color:#999` |
| `.wchip` | `background:#2c2c2e` |
| `.wchip button` | `background:#3a3a3c` |
| `/* Nachtmodus: schwarz, Schrift und Linien rot, Bilder rot eingefärbt */ body.night` | `--accent:#ff3b30; --on:#000; --tint:#5c0d08` |
| `body.night .now .wk-h b` | `color:#000!important` |
| `body.night .card` | `background:#000!important; border:1px solid #2a0805` |
| `body.night .cal-g .today em` | `color:#000!important` |
| `body.night .sp-ctl .pp,body.night .btn,body.night .nw li` | `background:#260604!important` |
| `body.night .sp-bar` | `background:#3a0b07` |
| `body.night .dots i` | `background:#3a0b07` |
| `body.night .wx-row` | `border-color:#3a0b07` |
| `body.night #cook,body.night .rc,body.night .w-recipe` | `--bg:#000!important` |
| `body.night .nav.next,body.night .cbtn.on` | `color:#000!important` |
| `body.night .rc,body.night .w-recipe` | `border:1px solid #2a0805` |
| `body.night .chips button` | `background:#0d0201!important` |
| `body.night .chips button.on` | `color:#000!important` |
