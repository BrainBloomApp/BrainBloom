# BrainBloom
A STEM based educational website with free courses and activities for all ages.
[index.html](https://github.com/user-attachments/files/33586007/index.html)
<!doctype html>
<html lang="en">
<head>
  <meta charset="utf-8">
  <meta name="viewport" content="width=device-width, initial-scale=1">
  <meta name="theme-color" content="#f8f9fb">
  <meta name="description" content="Free, hands-on STEM activities and interactive mini courses for high school students and curious minds.">
  <title>Brain Bloom — explore what you're curious about</title>
  <style>
    :root {
      color-scheme: light;
      --ink: #293348;
      --muted: #697486;
      --paper: #f8f9fb;
      --white: #fff;
      --pink: #dce7f3;
      --pink-deep: #8298bb;
      --lilac: #e5e1f2;
      --lilac-deep: #8e88b5;
      --mint: #dcebe5;
      --mint-deep: #6f9688;
      --yellow: #e9e7d7;
      --line: #e7eaf0;
      --shadow: 0 16px 45px rgba(51, 67, 95, .08);
      --round: 24px;
      font-family: "Trebuchet MS", "Segoe UI", sans-serif;
    }
    * { box-sizing: border-box; }
    html { scroll-behavior: smooth; }
    body { margin: 0; background: var(--paper); color: var(--ink); }
    button, a { font: inherit; }
    button { color: inherit; }
    a { color: inherit; text-decoration: none; }
    button:focus-visible, a:focus-visible { outline: 3px solid var(--lilac-deep); outline-offset: 4px; }
    .site-header { height: 78px; display: flex; align-items: center; border-bottom: 1px solid rgba(231,234,240,.9); background: rgba(248,249,251,.93); position: sticky; top: 0; z-index: 5; backdrop-filter: blur(12px); }
    .header-inner { width: min(1160px, calc(100% - 48px)); margin: auto; display: flex; align-items: center; justify-content: space-between; gap: 24px; }
    .brand { display: inline-flex; align-items: center; gap: 10px; font-size: 20px; font-weight: 800; letter-spacing: -.7px; white-space: nowrap; }
    .brand-mark { width: 36px; height: 36px; border-radius: 13px; background: #dcebe5; display: grid; place-items: center; font-size: 20px; }
    .main-nav { display: flex; align-items: center; gap: 34px; }
    .nav-link { color: var(--muted); font-size: 14px; font-weight: 700; padding: 10px 0; border: 0; background: none; cursor: pointer; }
    .nav-link:hover, .nav-link.active { color: var(--ink); }
    .nav-link.active { box-shadow: inset 0 -2px var(--mint-deep); }
    .header-cta, .button { display: inline-flex; align-items: center; justify-content: center; gap: 8px; border: 0; border-radius: 999px; padding: 13px 20px; background: var(--ink); color: white; font-weight: 700; font-size: 14px; cursor: pointer; transition: transform .2s, box-shadow .2s, background .2s; }
    .header-cta:hover, .button:hover { transform: translateY(-2px); box-shadow: 0 8px 18px rgba(48,43,67,.15); }
    .button:disabled { opacity: .52; cursor: not-allowed; transform: none; box-shadow: none; }
    .button.soft { color: var(--ink); background: white; border: 1px solid var(--line); }
    .button.pink { color: #354960; background: #dce7f3; }
    .button.lilac { color: #454362; background: #e5e1f2; }
    .button.small { padding: 10px 15px; font-size: 13px; }
    .hero { width: min(1160px, calc(100% - 48px)); min-height: 510px; margin: 0 auto; padding: 62px 0 72px; display: grid; grid-template-columns: 1.05fr .95fr; align-items: center; gap: 40px; }
    .eyebrow { display: inline-flex; align-items: center; gap: 8px; color: #687d77; font-size: 12px; font-weight: 800; letter-spacing: 1.25px; text-transform: uppercase; }
    .eyebrow .dot { width: 8px; height: 8px; border-radius: 50%; background: #87ab9c; }
    h1, h2, h3, p { margin-top: 0; }
    h1 { font-size: clamp(46px, 6vw, 72px); line-height: 1.02; letter-spacing: -4px; margin: 20px 0; max-width: 560px; }
    h1 span { color: #7888ad; }
    .hero-copy { max-width: 485px; color: var(--muted); font-size: 17px; line-height: 1.75; margin: 0 0 27px; }
    .hero-actions { display: flex; gap: 12px; flex-wrap: wrap; }
    .hero-note { margin-top: 18px; font-size: 12px; color: #898494; }
    .hero-art { min-height: 356px; position: relative; display: grid; place-items: center; }
    .art-orbit { position: absolute; width: 360px; height: 360px; border: 1px dashed #d8dfe9; border-radius: 50%; }
    .art-sun { position: absolute; width: 285px; height: 285px; border-radius: 45% 55% 48% 52%; background: #e1e9f1; transform: rotate(-8deg); }
    .art-blob { position: absolute; width: 208px; height: 224px; border-radius: 54% 46% 54% 46%; background: #e2def0; transform: rotate(15deg); right: 28px; top: 5px; opacity: .9; }
    .art-blob.mint { width: 125px; height: 125px; right: 42px; top: auto; bottom: 16px; background: #cce8d8; transform: rotate(-12deg); }
    .art-flower { position: relative; z-index: 1; width: 218px; height: 244px; filter: drop-shadow(0 12px 12px rgba(65,79,96,.12)); }
    .floating-note { position: absolute; z-index: 2; background: rgba(255,255,255,.92); box-shadow: var(--shadow); border-radius: 16px; padding: 12px 15px; font-size: 12px; font-weight: 700; }
    .floating-note.one { top: 43px; left: 0; transform: rotate(-5deg); }
    .floating-note.two { bottom: 42px; right: 0; transform: rotate(4deg); }
    .floating-note span { font-size: 19px; margin-right: 7px; vertical-align: middle; }
    .trust-strip { border-top: 1px solid #e7eaf0; border-bottom: 1px solid #e7eaf0; background: #fff; }
    .trust-inner { width: min(1160px, calc(100% - 48px)); margin: auto; padding: 20px 0; display: flex; align-items: center; justify-content: center; gap: 44px; color: #817c8d; font-size: 13px; flex-wrap: wrap; }
    .trust-inner strong { color: var(--ink); font-size: 14px; }
    .trust-item { display: flex; align-items: center; gap: 9px; }
    .section { width: min(1160px, calc(100% - 48px)); margin: auto; padding: 82px 0; }
    .section-heading { display: flex; justify-content: space-between; align-items: end; gap: 24px; margin-bottom: 30px; }
    .section-heading h2 { font-size: clamp(30px, 4vw, 42px); letter-spacing: -1.8px; margin: 10px 0 9px; }
    .section-heading p { margin: 0; color: var(--muted); font-size: 15px; line-height: 1.6; }
    .text-link { border: 0; background: none; color: #647b75; font-weight: 800; cursor: pointer; padding: 8px 0; white-space: nowrap; }
    .text-link:hover { color: var(--lilac-deep); }
    .card-grid { display: grid; grid-template-columns: repeat(3, 1fr); gap: 20px; }
    .learning-card { background: white; border: 1px solid #e7eaf0; border-radius: var(--round); overflow: hidden; transition: transform .2s, box-shadow .2s; }
    .learning-card:hover { transform: translateY(-5px); box-shadow: var(--shadow); }
    .card-art { min-height: 190px; display: grid; place-items: center; position: relative; overflow: hidden; }
    .card-art.flower-bg { background: #e4eaf2; }
    .card-art.brain-bg { background: #e7e3f1; }
    .card-art.space-bg { background: #dfebe5; }
    .card-art.dna-bg { background: #e3e9df; }
    .card-art.plane-bg { background: #e1eaf0; }
    .art-label { position: absolute; top: 15px; left: 15px; border-radius: 99px; background: rgba(255,255,255,.8); padding: 7px 11px; font-size: 10px; font-weight: 800; color: #5d5869; letter-spacing: .4px; }
    .flower-emoji { font-size: 94px; filter: drop-shadow(0 9px 9px rgba(55,68,84,.1)); transform: rotate(-9deg); }
    .brain-emoji { font-size: 91px; filter: drop-shadow(0 9px 9px rgba(95,61,68,.1)); }
    .space-emoji { font-size: 94px; filter: drop-shadow(0 9px 9px rgba(95,61,68,.1)); transform: rotate(-8deg); }
    .card-body { padding: 20px 21px 22px; }
    .card-meta { color: #938b9a; text-transform: uppercase; letter-spacing: .8px; font-size: 10px; font-weight: 800; margin-bottom: 9px; }
    .card-body h3 { font-size: 19px; letter-spacing: -.45px; margin: 0 0 8px; }
    .card-body p { min-height: 45px; color: var(--muted); font-size: 13px; line-height: 1.65; margin-bottom: 18px; }
    .card-footer { display: flex; justify-content: space-between; align-items: center; gap: 8px; }
    .duration { color: #8a8491; font-size: 11px; font-weight: 700; }
    .how-section { background: #eef2f3; }
    .how-inner { width: min(1160px, calc(100% - 48px)); margin: auto; padding: 70px 0; }
    .how-inner > .section-heading { margin-bottom: 38px; }
    .steps { display: grid; grid-template-columns: repeat(3, 1fr); gap: 34px; }
    .step { display: flex; gap: 16px; }
    .step-number { flex: 0 0 38px; width: 38px; height: 38px; border-radius: 14px; background: white; display: grid; place-items: center; font-weight: 800; color: #bd7186; }
    .step h3 { font-size: 16px; margin: 2px 0 7px; }
    .step p { font-size: 13px; line-height: 1.65; color: var(--muted); margin: 0; }
    .newsletter { margin: 72px auto; width: min(1160px, calc(100% - 48px)); background: #f3eaf8; border-radius: 30px; padding: 42px 48px; display: flex; justify-content: space-between; align-items: center; gap: 24px; }
    .newsletter h2 { font-size: 29px; letter-spacing: -1px; margin: 0 0 8px; }
    .newsletter p { margin: 0; color: var(--muted); font-size: 14px; }
    .free-badge { display: inline-flex; margin-top: 13px; color: #695879; background: white; border-radius: 99px; padding: 7px 11px; font-size: 11px; font-weight: 800; }
    .footer { border-top: 1px solid var(--line); padding: 25px 0; }
    .footer-inner { width: min(1160px, calc(100% - 48px)); margin: auto; display: flex; justify-content: space-between; gap: 18px; align-items: center; color: #8c8794; font-size: 12px; }
    .footer .brand { color: var(--ink); font-size: 15px; }
    .footer .brand-mark { width: 29px; height: 29px; font-size: 16px; border-radius: 10px; }
    .team-section { background: #fff; border-top: 1px solid var(--line); }
    .team-grid { display: grid; grid-template-columns: repeat(2, 1fr); gap: 18px; margin-top: 28px; }
    .team-card { padding: 25px; background: #f4f6f8; border: 1px solid var(--line); border-radius: 20px; }
    .team-avatar { width: 70px; height: 70px; border-radius: 22px; background: #e1e7ef; display: grid; place-items: center; margin-bottom: 18px; }
    .team-avatar svg { width: 60px; height: 60px; overflow: visible; }
    .team-card:nth-child(2) .team-avatar { background: #e3ebe5; }
    .team-card h3 { margin: 0 0 6px; font-size: 19px; }
    .team-card .team-role { color: #607f75; font-size: 12px; font-weight: 800; margin-bottom: 10px; }
    .team-card p { color: var(--muted); line-height: 1.65; margin: 0; font-size: 13px; }
    .team-social { display: flex; align-items: center; gap: 8px; margin: 23px 0 0; color: var(--muted); font-size: 13px; }
    .instagram-link { display: inline-flex; align-items: center; gap: 8px; color: #536e68; font-weight: 800; text-decoration: underline; text-decoration-color: #b7c9c2; text-underline-offset: 3px; }
    .instagram-link:hover { color: #52677c; }
    .instagram-icon { width: 18px; height: 18px; flex: 0 0 18px; }
    .footer-social { display: inline-flex; align-items: center; gap: 7px; white-space: nowrap; }
    .footer-social .instagram-icon { width: 16px; height: 16px; flex-basis: 16px; }
    .course-preview { background: #f0eff6; }
    .view { display: none; }
    .view.active { display: block; }
    .catalog-top { background: #e9eef2; padding: 54px 0 45px; }
    .catalog-inner { width: min(1160px, calc(100% - 48px)); margin: auto; }
    .catalog-inner h1 { font-size: clamp(38px, 5vw, 54px); margin: 13px 0 12px; letter-spacing: -2px; }
    .catalog-inner > p { color: var(--muted); margin: 0; line-height: 1.7; }
    .catalog-content { width: min(1160px, calc(100% - 48px)); margin: auto; padding: 45px 0 80px; }
    .filter-row { display: flex; gap: 9px; margin-bottom: 25px; flex-wrap: wrap; }
    .filter-chip { border: 1px solid var(--line); background: white; padding: 9px 14px; border-radius: 99px; cursor: pointer; color: var(--muted); font-size: 12px; font-weight: 700; }
    .filter-chip.selected { color: white; background: var(--ink); border-color: var(--ink); }
    .lesson-overlay { position: fixed; z-index: 10; inset: 0; background: var(--paper); display: none; align-items: stretch; justify-content: stretch; padding: 0; }
    .lesson-overlay.open { display: flex; }
    .lesson-window { background: var(--paper); width: 100%; height: 100%; overflow: auto; }
    .lesson-top { display: flex; justify-content: space-between; align-items: center; padding: 16px max(24px, calc((100vw - 1180px) / 2)); border-bottom: 1px solid var(--line); position: sticky; top: 0; z-index: 2; background: rgba(248,249,251,.97); }
    .lesson-brand { display: flex; align-items: center; gap: 11px; font-weight: 800; font-size: 13px; }
    .progress-track { width: 145px; height: 6px; background: #eee7ec; border-radius: 99px; overflow: hidden; }
    .progress-fill { height: 100%; width: 0; background: #849b90; transition: width .25s; }
    .close-button { border: 0; background: white; width: 34px; height: 34px; border-radius: 50%; font-size: 19px; cursor: pointer; }
    .lesson-content { width: min(1040px, calc(100% - 48px)); min-height: calc(100vh - 72px); margin: 0 auto; padding: 42px 0 64px; }
    .lesson-content h2 { font-size: clamp(27px, 4vw, 38px); letter-spacing: -1.2px; margin: 10px 0 12px; }
    .lesson-content > p { color: var(--muted); line-height: 1.8; max-width: 850px; font-size: 16px; }
    .lesson-content h3 { margin: 23px 0 8px; font-size: 19px; }
    .lesson-content ul, .lesson-content ol { color: var(--muted); line-height: 1.8; padding-left: 24px; }
    .lesson-content .lesson-age { display: inline-flex; margin: 0 0 12px; padding: 6px 10px; border-radius: 99px; background: #e5eaf0; color: #586c7e; font-size: 11px; font-weight: 800; }
    .lesson-content .learning-note { border-left: 3px solid #8aa89b; padding: 12px 15px; margin: 16px 0; border-radius: 0 12px 12px 0; background: #edf2ef; color: #53665e; font-size: 14px; line-height: 1.65; }
    .lesson-actions { display: flex; justify-content: space-between; gap: 10px; margin-top: 25px; align-items: center; }
    .slide-count { color: #918a98; font-size: 12px; }
    .interactive-panel { margin-top: 24px; border-radius: 20px; background: white; border: 1px solid var(--line); padding: 24px; }
    .flower-lab { display: grid; grid-template-columns: 1fr 1fr; gap: 22px; align-items: center; }
    .flower-preview { background: #edf1f5; border-radius: 17px; min-height: 230px; display: grid; place-items: center; overflow: hidden; }
    .flower-preview svg { width: 180px; height: 210px; }
    .controls label { display: block; font-size: 12px; font-weight: 800; margin: 12px 0 7px; }
    .controls select { width: 100%; padding: 10px 11px; border: 1px solid var(--line); border-radius: 10px; background: #fffdfb; color: var(--ink); }
    .code-snippet { padding: 13px; border-radius: 12px; margin: 13px 0 0; background: #322d43; color: #f5eaf2; font: 12px/1.7 Consolas, monospace; overflow-x: auto; }
    .brain-lab { display: grid; grid-template-columns: 1fr 1fr; gap: 20px; align-items: center; }
    .brain-map { border-radius: 17px; min-height: 220px; background: #eeecf5; display: grid; place-items: center; position: relative; }
    .brain-map .brain-big { font-size: 95px; }
    .brain-pin { position: absolute; border: 0; border-radius: 99px; background: white; padding: 7px 10px; box-shadow: 0 3px 12px #49366b18; font-size: 11px; font-weight: 800; cursor: pointer; }
    .brain-pin:hover, .brain-pin.selected { background: #dce6e1; }
    .brain-pin.p1 { top: 24px; left: 15px; }
    .brain-pin.p2 { top: 30px; right: 13px; }
    .brain-pin.p3 { bottom: 24px; right: 20px; }
    .brain-info { min-height: 170px; padding: 18px; border-radius: 16px; background: #f8f9fb; }
    .planet-grid { display: grid; grid-template-columns: repeat(4, 1fr); gap: 9px; margin-top: 15px; }
    .planet-button { border: 1px solid var(--line); background: #fff; border-radius: 13px; padding: 11px 7px; cursor: pointer; font-size: 12px; font-weight: 700; }
    .planet-button:hover, .planet-button.selected { background: #e8e6f1; border-color: #c4bfd9; }
    .planet-button span { display: block; font-size: 22px; margin-bottom: 4px; }
    .planet-info { min-height: 74px; padding: 13px; margin-top: 12px; background: #f8f9fb; border-radius: 13px; color: var(--muted); font-size: 13px; line-height: 1.6; }
    .base-buttons { display: flex; flex-wrap: wrap; gap: 9px; margin-top: 15px; }
    .base-button { border: 1px solid var(--line); background: white; border-radius: 12px; padding: 10px 13px; cursor: pointer; font-weight: 800; }
    .base-button:hover { background: #edf1f5; }
    .base-button span { display: block; color: var(--muted); font-size: 10px; font-weight: 500; }
    .sequence-display, .trial-results { background: #f7f8fa; padding: 13px; border-radius: 12px; color: var(--muted); font: 13px/1.8 Consolas, monospace; overflow-wrap: anywhere; }
    .trial-controls { display: grid; grid-template-columns: 1fr 1fr auto; align-items: end; gap: 11px; margin: 14px 0; }
    .trial-controls label { font-size: 12px; font-weight: 800; }
    .trial-controls select, .trial-controls input { display: block; width: 100%; padding: 10px; margin-top: 6px; border: 1px solid var(--line); border-radius: 10px; background: #fff; color: var(--ink); }
    .lab-hint { color: var(--muted); font-size: 13px; line-height: 1.6; margin: 9px 0; }
    .code-workspace { display: grid; grid-template-columns: 1fr 1fr; gap: 16px; margin-top: 18px; }
    .code-workspace textarea { min-height: 145px; width: 100%; resize: vertical; padding: 14px; border: 1px solid #454b60; border-radius: 13px; background: #293348; color: #eff2fa; font: 14px/1.8 Consolas, monospace; }
    .code-workspace .code-preview { min-height: 145px; border-radius: 13px; background: #f8f9fb; display: grid; place-items: center; }
    .code-workspace .code-preview svg { height: 140px; width: 140px; }
    .code-workspace .code-actions { display: flex; align-items: center; gap: 12px; margin-top: 10px; flex-wrap: wrap; }
    .folding-diagrams { display: grid; grid-template-columns: 1fr 1fr; gap: 15px; margin: 18px 0; }
    .fold-card { border: 1px solid var(--line); background: #fff; border-radius: 16px; padding: 15px; }
    .fold-card svg { width: 100%; height: 120px; display: block; background: #f3f6f8; border-radius: 10px; margin-bottom: 9px; }
    .fold-card h4 { margin: 5px 0; }
    .fold-card p, .fold-card ol { color: var(--muted); font-size: 13px; line-height: 1.65; }
    .data-table { width: 100%; border-collapse: collapse; margin: 14px 0; font-size: 13px; }
    .data-table th, .data-table td { border: 1px solid var(--line); padding: 10px; text-align: left; }
    .data-table th { background: #eef2f4; }
    .bead-chain { display: flex; gap: 7px; flex-wrap: wrap; min-height: 36px; align-items: center; margin: 12px 0; }
    .bead { width: 28px; height: 28px; border-radius: 50%; display: grid; place-items: center; color: #263246; font-size: 11px; font-weight: 800; }
    .bead-A { background: #a9c9a9; }.bead-T { background: #a9bfd7; }.bead-C { background: #b7afd2; }.bead-G { background: #ded3a5; }
    .strand-result { margin-top: 13px; padding: 14px; border-radius: 12px; background: #f4f6f7; color: var(--muted); font-size: 13px; line-height: 1.7; }
    .circuit-sim { display: grid; grid-template-columns: 1fr 1fr; align-items: center; gap: 18px; }
    .circuit-sim svg { width: 100%; max-height: 190px; background: #f4f6f7; border-radius: 14px; }
    .circuit-bulb { fill: #cdd3d7; transition: fill .2s, filter .2s; }
    .circuit-bulb.lit { fill: #f0d98b; filter: drop-shadow(0 0 13px #e8cd70); }
    .quiz-progress { color: var(--muted); font-size: 12px; margin: 8px 0 16px; }
    .quiz-feedback { min-height: 23px; font-size: 13px; font-weight: 700; color: #578163; margin: 12px 0 0; }
    .badge-card { max-width: 560px; margin: 22px auto; border: 2px solid #c6d4cc; border-radius: 24px; background: linear-gradient(140deg,#f6f8f4,#e7edf2); padding: 28px; text-align: center; }
    .badge-card .badge-icon { font-size: 58px; }
    .badge-card h3 { font-size: 24px; margin: 9px 0; }
    .badge-actions { display: flex; justify-content: center; gap: 10px; flex-wrap: wrap; margin-top: 18px; }
    .badge-popup { position: fixed; z-index: 20; inset: 0; display: grid; place-items: center; padding: 20px; background: rgba(35,45,62,.5); }
    .badge-popup-card { width: min(470px, 100%); padding: 27px; border-radius: 24px; border: 1px solid #d9e0dc; background: #fbfcfa; box-shadow: 0 24px 80px rgba(32,43,59,.22); text-align: center; }
    .badge-popup-card h2 { margin: 7px 0; font-size: 31px; }
    .badge-popup-card p { color: var(--muted); line-height: 1.6; }
    #worksheet-print { display: none; }
    @media print {
      body > *:not(#worksheet-print) { display: none !important; }
      body > #worksheet-print { display: block !important; width: 100%; padding: 20px; color: #111; font: 12pt/1.6 Georgia, serif; }
      #worksheet-print h1 { font-size: 26pt; letter-spacing: 0; }
      #worksheet-print h2 { margin-top: 22px; font-size: 16pt; }
      #worksheet-print .write-lines { height: 82px; border-bottom: 1px solid #999; margin: 8px 0; }
      #worksheet-print table { width: 100%; border-collapse: collapse; }
      #worksheet-print th, #worksheet-print td { border: 1px solid #555; padding: 8px; text-align: left; }
    }
    .brain-info h3 { font-size: 18px; margin: 0 0 8px; }
    .brain-info p { color: var(--muted); font-size: 13px; line-height: 1.7; margin: 0; }
    .quiz-options { display: grid; grid-template-columns: 1fr 1fr; gap: 10px; margin-top: 17px; }
    .quiz-option { border: 1px solid var(--line); border-radius: 13px; padding: 13px; text-align: left; background: white; cursor: pointer; font-size: 13px; }
    .quiz-option:hover { border-color: #c4aedf; background: #fbf8ff; }
    .quiz-option.correct { border-color: #80b393; background: #edf8f0; }
    .quiz-option.incorrect { border-color: #e5a0a0; background: #fff1f1; }
    .quiz-feedback { min-height: 21px; font-size: 12px; font-weight: 700; color: #578163; margin: 12px 0 0; }
    @media (max-width: 780px) {
      .main-nav { gap: 16px; }
      .header-inner { width: min(100% - 32px, 1160px); }
      .hero { width: min(100% - 40px, 620px); grid-template-columns: 1fr; padding-top: 52px; gap: 10px; }
      .hero-art { min-height: 315px; }
      .art-orbit { width: 310px; height: 310px; }
      .art-sun { width: 250px; height: 250px; }
      .art-blob { right: calc(50% - 190px); }
      .art-blob.mint { right: calc(50% - 180px); }
      .floating-note.one { left: 5%; }
      .floating-note.two { right: 3%; }
      .card-grid { grid-template-columns: repeat(2, 1fr); }
      .steps { gap: 20px; }
      .section, .trust-inner, .how-inner, .newsletter, .footer-inner, .catalog-inner, .catalog-content { width: min(100% - 40px, 1160px); }
    }
    @media (max-width: 560px) {
      .site-header { height: 68px; }
      .header-inner { gap: 10px; }
      .brand { font-size: 18px; }
      .brand-mark { width: 32px; height: 32px; }
      .main-nav { gap: 12px; }
      .nav-link { font-size: 12px; }
      .header-cta { display: none; }
      .hero { padding-top: 43px; }
      h1 { letter-spacing: -2.5px; }
      .hero-copy { font-size: 15px; }
      .hero-art { min-height: 280px; }
      .art-orbit { width: 260px; height: 260px; }
      .art-sun { width: 213px; height: 213px; }
      .art-flower { transform: scale(.82); }
      .art-blob { width: 150px; height: 170px; right: calc(50% - 150px); }
      .art-blob.mint { width: 95px; height: 95px; right: calc(50% - 145px); }
      .floating-note { padding: 9px 11px; font-size: 10px; }
      .trust-inner { justify-content: flex-start; gap: 14px 22px; font-size: 11px; }
      .trust-inner strong { width: 100%; }
      .section { padding: 58px 0; }
      .section-heading { align-items: start; flex-direction: column; gap: 12px; }
      .card-grid { grid-template-columns: 1fr; }
      .card-art { min-height: 180px; }
      .card-body p { min-height: 0; }
      .steps { grid-template-columns: 1fr; gap: 23px; }
      .team-grid { grid-template-columns: 1fr; }
      .planet-grid { grid-template-columns: repeat(2, 1fr); }
      .trial-controls { grid-template-columns: 1fr 1fr; }
      .trial-controls .button { grid-column: 1 / -1; }
      .newsletter { padding: 30px 24px; align-items: flex-start; flex-direction: column; margin: 48px auto; }
      .newsletter h2 { font-size: 25px; }
      .footer-inner { align-items: flex-start; flex-direction: column; }
      .catalog-top { padding: 42px 0 35px; }
      .flower-lab, .brain-lab, .code-workspace, .circuit-sim { grid-template-columns: 1fr; }
      .folding-diagrams { grid-template-columns: 1fr; }
      .lesson-content { width: calc(100% - 36px); padding-top: 28px; }
      .flower-preview { min-height: 190px; }
      .flower-preview svg { height: 175px; }
      .lesson-top { padding: 13px 15px; }
      .progress-track { width: 85px; }
      .lesson-content { padding-top: 24px; }
      .quiz-options { grid-template-columns: 1fr; }
    }
    @media (prefers-reduced-motion: reduce) {
      *, *::before, *::after { scroll-behavior: auto !important; transition-duration: .01ms !important; animation-duration: .01ms !important; }
    }
  </style>
</head>
<body>
  <header class="site-header">
    <div class="header-inner">
      <a class="brand" href="#" aria-label="Brain Bloom home" data-view="home"><span class="brand-mark" aria-hidden="true">🌼</span> Brain Bloom</a>
      <nav class="main-nav" aria-label="Main navigation">
        <button class="nav-link" data-view="activities">Activities</button>
        <button class="nav-link" data-view="courses">Courses</button>
        <a class="nav-link" href="#meet-the-team" id="team-link">Meet the team</a>
      </nav>
      <button class="header-cta" data-view="activities">Let's explore <span aria-hidden="true">↗</span></button>
    </div>
  </header>

  <main>
    <div class="view active" id="home-view">
      <section class="hero">
        <div>
          <div class="eyebrow"><span class="dot"></span> STEM, made hands-on</div>
          <h1>Make curiosity<br><span>your thing.</span></h1>
          <p class="hero-copy">Build, test, and explore the ideas behind science and technology. Brain Bloom brings together hands-on projects and interactive mini courses for high school students and curious minds.</p>
          <div class="hero-actions">
            <button class="button" data-view="activities">Explore activities <span aria-hidden="true">→</span></button>
            <button class="button soft" data-view="courses">Browse mini courses</button>
          </div>
          <p class="hero-note">Free to explore · Learn at your own pace · Made for curious minds</p>
        </div>
        <div class="hero-art" aria-label="Illustration of a flower blooming">
          <div class="art-orbit"></div><div class="art-sun"></div><div class="art-blob"></div><div class="art-blob mint"></div>
          <div class="floating-note one"><span>🧠</span> Wonder more</div>
          <div class="floating-note two"><span>✨</span> Make it yours</div>
          <svg class="art-flower" viewBox="0 0 220 250" role="img" aria-label="A flower growing as ideas take shape">
            <path d="M110 126 C112 168 108 200 110 239" fill="none" stroke="#659879" stroke-width="9" stroke-linecap="round"/>
            <path d="M109 192 C80 164 57 184 67 201 C79 216 99 204 109 192Z" fill="#8fbd96"/>
            <path d="M110 184 C139 157 162 177 151 194 C140 207 120 197 110 184Z" fill="#a5cda7"/>
            <g fill="#a9b7d3">
              <ellipse cx="110" cy="61" rx="22" ry="39"/><ellipse cx="110" cy="61" rx="22" ry="39" transform="rotate(60 110 100)"/>
              <ellipse cx="110" cy="61" rx="22" ry="39" transform="rotate(120 110 100)"/><ellipse cx="110" cy="61" rx="22" ry="39" transform="rotate(180 110 100)"/>
              <ellipse cx="110" cy="61" rx="22" ry="39" transform="rotate(240 110 100)"/><ellipse cx="110" cy="61" rx="22" ry="39" transform="rotate(300 110 100)"/>
            </g>
            <circle cx="110" cy="100" r="25" fill="#d5cfad"/><circle cx="102" cy="95" r="3" fill="#4e5360"/><circle cx="118" cy="95" r="3" fill="#4e5360"/>
            <path d="M104 106 Q110 113 117 106" fill="none" stroke="#725743" stroke-width="2.5" stroke-linecap="round"/>
          </svg>
        </div>
      </section>

      <div class="trust-strip"><div class="trust-inner">
        <strong>Built for curious minds.</strong>
        <div class="trust-item"><span>🧪</span> Make and experiment</div>
        <div class="trust-item"><span>🧠</span> Learn by exploring</div>
        <div class="trust-item"><span>✦</span> Free for everyone</div>
      </div></div>

      <section class="section" id="featured">
        <div class="section-heading">
          <div><div class="eyebrow"><span class="dot"></span> learn by making</div><h2>Hands-on activities</h2><p>Real-world projects that turn STEM concepts into something you can build, test, and take away.</p></div>
          <button class="text-link" data-view="activities">See all activities <span aria-hidden="true">→</span></button>
        </div>
        <div class="card-grid">
          <article class="learning-card">
            <div class="card-art dna-bg"><span class="art-label">BIOLOGY · BUILD</span><span class="flower-emoji" aria-hidden="true">🧬</span></div>
            <div class="card-body"><div class="card-meta">Biology · Genetics · Ages 13+</div><h3>Build two DNA bracelets</h3><p>Model the four DNA bases and build two bracelets that show how complementary strands pair.</p>
              <div class="card-footer"><span class="duration">⏱ 30 min · Beads + string</span><button class="button small pink" data-lesson="dna">See the activity →</button></div>
            </div>
          </article>
          <article class="learning-card">
            <div class="card-art plane-bg"><span class="art-label">PHYSICS · TEST</span><span class="space-emoji" aria-hidden="true">✈️</span></div>
            <div class="card-body"><div class="card-meta">Physics · Forces &amp; flight · Ages 13+</div><h3>Paper airplane flight lab</h3><p>Learn two folds, run repeated trials, compare the data, and explain the results.</p>
              <div class="card-footer"><span class="duration">⏱ 30 min · Paper + open space</span><button class="button small lilac" data-lesson="plane">Run the experiment →</button></div>
            </div>
          </article>
          <article class="learning-card">
            <div class="card-art flower-bg"><span class="art-label">CODING · CREATE</span><span class="flower-emoji" aria-hidden="true">🌼</span></div>
            <div class="card-body"><div class="card-meta">Computer science · Creative coding · Ages 13+</div><h3>Code a blooming flower</h3><p>Use variables and simple instructions to customize a flower right in your browser.</p>
              <div class="card-footer"><span class="duration">⏱ 15 min · No setup needed</span><button class="button small pink" data-lesson="flower">Start making →</button></div>
            </div>
          </article>
          <article class="learning-card">
            <div class="card-art dna-bg"><span class="art-label">ONLINE · INTERACTIVE</span><span class="flower-emoji" aria-hidden="true">💡</span></div>
            <div class="card-body"><div class="card-meta">Physics · Electricity &amp; circuits</div><h3>Build a virtual circuit</h3><p>Connect a battery, wires, and a bulb. Test what makes a complete circuit and switch the light on.</p>
              <div class="card-footer"><span class="duration">⏱ 15 min · Ages 13+</span><button class="button small lilac" data-lesson="circuit">Build a circuit →</button></div>
            </div>
          </article>
        </div>
      </section>

      <section class="how-section" id="how-it-works">
        <div class="how-inner">
          <div class="section-heading"><div><div class="eyebrow"><span class="dot"></span> start anywhere</div><h2>Explore a question. Test an idea.</h2><p>Follow clear steps, try things for yourself, and see what you can figure out.</p></div></div>
          <div class="steps">
            <div class="step"><div class="step-number">1</div><div><h3>Choose your format</h3><p>Build something hands-on in Activities, or dive into a topic with Courses.</p></div></div>
            <div class="step"><div class="step-number">2</div><div><h3>Learn the concept</h3><p>Connect each project to the science, engineering, or code behind it.</p></div></div>
            <div class="step"><div class="step-number">3</div><div><h3>Experiment and iterate</h3><p>Use what you learn to ask better questions and improve your next idea.</p></div></div>
          </div>
        </div>
      </section>
      <section class="section course-preview">
        <div class="section-heading">
          <div><div class="eyebrow"><span class="dot"></span> explore the ideas behind it</div><h2>Mini courses, separate from the making.</h2><p>Short, interactive introductions to big science topics. Always free.</p></div>
          <button class="text-link" data-view="courses">Browse all courses <span aria-hidden="true">→</span></button>
        </div>
        <div class="card-grid">
          <article class="learning-card">
            <div class="card-art brain-bg"><span class="art-label">BIOLOGY · MINI COURSE</span><span class="brain-emoji" aria-hidden="true">🧠</span></div>
            <div class="card-body"><div class="card-meta">Neuroscience · Your brain · Ages 13+</div><h3>How your brain works</h3><p>Explore key brain regions and how they help you think, move, and respond.</p><div class="card-footer"><span class="duration">⏱ 15 min · Interactive</span><button class="button small lilac" data-lesson="brain">Explore course →</button></div></div>
          </article>
          <article class="learning-card">
            <div class="card-art space-bg"><span class="art-label">ASTRONOMY · MINI COURSE</span><span class="space-emoji" aria-hidden="true">🪐</span></div>
            <div class="card-body"><div class="card-meta">Astronomy · Our solar system · Ages 13+</div><h3>A tour of the solar system</h3><p>Meet the planets, compare their worlds, and discover how they orbit the Sun.</p><div class="card-footer"><span class="duration">⏱ 15 min · Interactive</span><button class="button small lilac" data-lesson="solar">Explore course →</button></div></div>
          </article>
        </div>
      </section>
      <section class="newsletter">
        <div><div class="eyebrow"><span class="dot"></span> meet the people behind brain bloom</div><h2>Built by students, for curious minds.</h2><p>We're high school students making STEM feel creative, approachable, and worth exploring.</p></div>
        <button class="button" data-team-link>Meet the team <span aria-hidden="true">→</span></button>
      </section>
      <section class="section team-section" id="meet-the-team">
        <div class="section-heading"><div><div class="eyebrow"><span class="dot"></span> the people behind the projects</div><h2>Meet the team</h2><p>Two high school students building a space for learning through curiosity.</p></div></div>
        <div class="team-grid">
          <article class="team-card"><div class="team-avatar" aria-hidden="true"><svg viewBox="0 0 72 72">
            <path d="M36 39 C35 48 36 57 36 67" fill="none" stroke="#789b83" stroke-width="3.5" stroke-linecap="round"/>
            <path d="M36 54 C26 45 20 52 24 57 C28 61 33 57 36 54Z" fill="#91b59a"/>
            <g fill="#9fb2d1"><ellipse cx="36" cy="14" rx="5.5" ry="10"/><ellipse cx="36" cy="14" rx="5.5" ry="10" transform="rotate(60 36 29)"/><ellipse cx="36" cy="14" rx="5.5" ry="10" transform="rotate(120 36 29)"/><ellipse cx="36" cy="14" rx="5.5" ry="10" transform="rotate(180 36 29)"/><ellipse cx="36" cy="14" rx="5.5" ry="10" transform="rotate(240 36 29)"/><ellipse cx="36" cy="14" rx="5.5" ry="10" transform="rotate(300 36 29)"/></g>
            <circle cx="36" cy="29" r="8.5" fill="#d8d1b5"/><circle cx="33" cy="28" r="1" fill="#48556a"/><circle cx="39" cy="28" r="1" fill="#48556a"/><path d="M33 32 Q36 35 39 32" fill="none" stroke="#48556a" stroke-width="1" stroke-linecap="round"/>
          </svg></div><h3>Joshitha Nagappagari</h3><div class="team-role">Sophomore in high school · Lead Developer</div><p>Builds Brain Bloom and brings its interactive learning experiences to life.</p></article>
          <article class="team-card"><div class="team-avatar" aria-hidden="true"><svg viewBox="0 0 72 72">
            <path d="M36 39 C37 48 36 57 36 67" fill="none" stroke="#6f9688" stroke-width="3.5" stroke-linecap="round"/>
            <path d="M36 55 C46 45 52 51 48 57 C44 61 39 58 36 55Z" fill="#91b9a4"/>
            <g fill="#aaa4cb"><ellipse cx="36" cy="14" rx="5.5" ry="10"/><ellipse cx="36" cy="14" rx="5.5" ry="10" transform="rotate(60 36 29)"/><ellipse cx="36" cy="14" rx="5.5" ry="10" transform="rotate(120 36 29)"/><ellipse cx="36" cy="14" rx="5.5" ry="10" transform="rotate(180 36 29)"/><ellipse cx="36" cy="14" rx="5.5" ry="10" transform="rotate(240 36 29)"/><ellipse cx="36" cy="14" rx="5.5" ry="10" transform="rotate(300 36 29)"/></g>
            <circle cx="36" cy="29" r="8.5" fill="#d9d4bb"/><circle cx="33" cy="28" r="1" fill="#48556a"/><circle cx="39" cy="28" r="1" fill="#48556a"/><path d="M33 32 Q36 35 39 32" fill="none" stroke="#48556a" stroke-width="1" stroke-linecap="round"/>
          </svg></div><h3>Anushka Jha</h3><div class="team-role">Sophomore in high school · Creative Director &amp; Community Manager</div><p>Shapes the creative direction and helps grow the Brain Bloom community.</p></article>
        </div>
        <p class="team-social">Follow along on Instagram:
          <a class="instagram-link" href="https://www.instagram.com/brain_bloom92/" target="_blank" rel="noopener noreferrer" aria-label="Brain Bloom on Instagram, @brain_bloom92">
            <svg class="instagram-icon" viewBox="0 0 24 24" fill="none" aria-hidden="true"><rect x="3" y="3" width="18" height="18" rx="5" stroke="currentColor" stroke-width="2"/><circle cx="12" cy="12" r="4" stroke="currentColor" stroke-width="2"/><circle cx="18" cy="6.5" r="1.2" fill="currentColor"/></svg>
            @brain_bloom92
          </a>
        </p>
      </section>
    </div>

    <div class="view" id="activities-view">
      <section class="catalog-top"><div class="catalog-inner">
        <div class="eyebrow"><span class="dot"></span> build it · test it · learn from it</div><h1>STEM you can get hands-on with.</h1>
        <p>Make a model, run an experiment, or try a little code.<br>Each activity connects a real project to the science behind it.</p>
      </div></section>
      <section class="catalog-content">
        <div class="filter-row" role="group" aria-label="Filter activities">
          <button class="filter-chip selected" data-filter="all">All activities</button><button class="filter-chip" data-filter="biology">Biology</button><button class="filter-chip" data-filter="physics">Physics</button><button class="filter-chip" data-filter="coding">Coding</button><button class="filter-chip" data-filter="ages">High school</button>
        </div>
        <div class="card-grid">
          <article class="learning-card" data-category="biology ages">
            <div class="card-art dna-bg"><span class="art-label">BUILD A MODEL</span><span class="flower-emoji" aria-hidden="true">🧬</span></div>
            <div class="card-body"><div class="card-meta">Biology · Genetics · Ages 13+</div><h3>Build two DNA bracelets</h3><p>Model a DNA sequence and its complementary strand with two matching bead bracelets.</p><div class="card-footer"><span class="duration">⏱ 30 min · Beads + string</span><button class="button small pink" data-lesson="dna">See the steps →</button></div></div>
          </article>
          <article class="learning-card" data-category="physics ages">
            <div class="card-art plane-bg"><span class="art-label">RUN AN EXPERIMENT</span><span class="space-emoji" aria-hidden="true">✈️</span></div>
            <div class="card-body"><div class="card-meta">Physics · Forces &amp; flight · Ages 13+</div><h3>Paper airplane flight lab</h3><p>Learn two airplane folds, run repeated trials, compare the data, and explain the results.</p><div class="card-footer"><span class="duration">⏱ 30 min · Paper + open space</span><button class="button small lilac" data-lesson="plane">Run the lab →</button></div></div>
          </article>
          <article class="learning-card" data-category="coding ages">
            <div class="card-art flower-bg"><span class="art-label">CODE IN YOUR BROWSER</span><span class="flower-emoji" aria-hidden="true">🌼</span></div>
            <div class="card-body"><div class="card-meta">Computer science · Creative coding · Ages 13+</div><h3>Code a blooming flower</h3><p>Use variables and simple instructions to customize a flower right in your browser.</p><div class="card-footer"><span class="duration">⏱ 15 min · No setup needed</span><button class="button small pink" data-lesson="flower">Start making →</button></div></div>
          </article>
          <article class="learning-card" data-category="physics ages">
            <div class="card-art dna-bg"><span class="art-label">ONLINE · INTERACTIVE</span><span class="flower-emoji" aria-hidden="true">💡</span></div>
            <div class="card-body"><div class="card-meta">Physics · Electricity · Ages 13+</div><h3>Build a virtual circuit</h3><p>Learn how a closed path lets electric charge flow and lights a bulb.</p><div class="card-footer"><span class="duration">⏱ 15 min · No materials</span><button class="button small lilac" data-lesson="circuit">Build a circuit →</button></div></div>
          </article>
        </div>
      </section>
    </div>

    <div class="view" id="courses-view">
      <section class="catalog-top" style="background:#e8e6f0"><div class="catalog-inner">
        <div class="eyebrow"><span class="dot"></span> short, interactive lessons</div><h1>Big topics, made approachable.</h1>
        <p>Explore how the brain works and take a guided tour of the solar system.<br>Learn at your own pace. Every course is completely free.</p>
      </div></section>
      <section class="catalog-content">
        <div class="section-heading"><div><h2>Choose a course</h2><p>Slide-based lessons with interactive models and knowledge checks.</p></div></div>
        <div class="card-grid" style="grid-template-columns:repeat(auto-fit,minmax(270px,1fr))">
          <article class="learning-card">
            <div class="card-art brain-bg"><span class="art-label">FREE MINI COURSE</span><span class="brain-emoji" aria-hidden="true">🧠</span></div>
            <div class="card-body"><div class="card-meta">Biology · Neuroscience · Ages 13+</div><h3>How your brain works</h3><p>Explore key brain regions, what they do, and how they work together.</p><div class="card-footer"><span class="duration">⏱ 15 min · Interactive</span><button class="button small lilac" data-lesson="brain">Start learning →</button></div></div>
          </article>
          <article class="learning-card">
            <div class="card-art space-bg"><span class="art-label">FREE MINI COURSE</span><span class="space-emoji" aria-hidden="true">🪐</span></div>
            <div class="card-body"><div class="card-meta">Astronomy · Planetary science · Ages 13+</div><h3>A tour of the solar system</h3><p>Compare the planets and explore what makes each world unique.</p><div class="card-footer"><span class="duration">⏱ 15 min · Interactive</span><button class="button small lilac" data-lesson="solar">Start learning →</button></div></div>
          </article>
        </div>
      </section>
    </div>
  </main>

  <footer class="footer"><div class="footer-inner"><a class="brand" href="#" data-view="home"><span class="brand-mark" aria-hidden="true">🌼</span> Brain Bloom</a><span>A little learning, a lot of wonder. &nbsp;✿&nbsp; Free for every curious mind.</span><a class="instagram-link footer-social" href="https://www.instagram.com/brain_bloom92/" target="_blank" rel="noopener noreferrer" aria-label="Brain Bloom on Instagram, @brain_bloom92"><svg class="instagram-icon" viewBox="0 0 24 24" fill="none" aria-hidden="true"><rect x="3" y="3" width="18" height="18" rx="5" stroke="currentColor" stroke-width="2"/><circle cx="12" cy="12" r="4" stroke="currentColor" stroke-width="2"/><circle cx="18" cy="6.5" r="1.2" fill="currentColor"/></svg>@brain_bloom92</a></div></footer>

  <div class="lesson-overlay" id="lesson-overlay" role="dialog" aria-modal="true" aria-labelledby="lesson-title">
    <div class="lesson-window">
      <div class="lesson-top"><div class="lesson-brand"><span aria-hidden="true">🌱</span><span id="lesson-name">A little adventure</span><div class="progress-track" aria-label="Lesson progress"><div class="progress-fill" id="progress-fill"></div></div></div><button class="close-button" id="close-lesson" aria-label="Close lesson">×</button></div>
      <div class="lesson-content" id="lesson-content"></div>
    </div>
  </div>
  <section id="worksheet-print" aria-hidden="true"></section>

  <script>
    (() => {
      const views = {
        home: document.getElementById("home-view"),
        activities: document.getElementById("activities-view"),
        courses: document.getElementById("courses-view")
      };
      const navLinks = document.querySelectorAll(".nav-link[data-view]");
      function showView(name, targetId) {
        if (!views[name]) return;
        Object.entries(views).forEach(([key, view]) => view.classList.toggle("active", key === name));
        navLinks.forEach(link => link.classList.toggle("active", link.dataset.view === name));
        if (targetId) document.getElementById(targetId).scrollIntoView({ behavior: "smooth" });
        else window.scrollTo({ top: 0, behavior: "smooth" });
      }
      document.querySelectorAll("[data-view]").forEach(el => el.addEventListener("click", event => {
        event.preventDefault();
        showView(el.dataset.view);
      }));
      document.getElementById("team-link").addEventListener("click", event => {
        event.preventDefault();
        showView("home", "meet-the-team");
      });
      document.querySelector("[data-team-link]").addEventListener("click", () => showView("home", "meet-the-team"));

      const overlay = document.getElementById("lesson-overlay");
      const content = document.getElementById("lesson-content");
      const progress = document.getElementById("progress-fill");
      const lessonName = document.getElementById("lesson-name");
      const closeButton = document.getElementById("close-lesson");
      let lesson = "";
      let slide = 0;
      let quizIndex = -1;
      let quizScore = 0;
      let selectedAnswer = null;
      let flightTrials = [];
      let dnaSequence = "";
      let previousFocus = null;
      const flowerSlides = [
        { title: "Welcome to your flower coding lab 🌼", text: "In this activity, you'll change a few lines of code and run them to grow a flower. Coding means writing instructions a computer can follow. You do not need to install anything: the editor and preview are right here.", detail: "<span class='learning-note'>Recommended age: 13+. About 15 minutes. Try changing one instruction at a time and notice what the computer does.</span>" },
        { title: "Read the instructions like a coder", text: "A variable is a named value we can change. Here, `petals` stores a number and `color` stores a color name. The `growFlower` function reads those values and draws the flower. Running the code means applying the instructions to create an output.", detail: "<pre class='code-snippet'>let petals = 6;       // store a number\nlet color = \"blue\";   // store a color\n\ngrowFlower(petals, color);</pre><p><strong>Predict:</strong> what do you think will change if you set petals to 8? What if you change the color but leave the number alone?</p>" },
        { title: "Edit and run your code", text: "Use this small, guided editor. Change the number of petals or the color, then run the instructions. The editor accepts the simple `petals = number` and `color = \"name\"` lines shown here; it translates those choices into a flower.", detail: "<span class='learning-note'>Try 4, 6, and 8 petals. Then try blue, lilac, sage, or mint. Which changes are data (the values), and which line tells the program to make the flower?</span>" },
        { title: "Explain what your code did", text: "You changed input values and ran a function that used them to make an output. That's the same pattern behind many interactive programs. Change one value at a time so you can tell which instruction caused each change.", detail: "<p>Think like a computer scientist: What did you predict? What happened? If the result surprised you, which line would you inspect first? Describe one change you made and what it did.</p>" }
      ];
      const brainSlides = [
        { title: "How your brain works 🧠", text: "The brain and spinal cord form the central nervous system. Neurons communicate through electrical and chemical signals, letting the nervous system receive information, process it, and coordinate responses. The brain is not a set of isolated boxes: its regions work together.", detail: "<span class='lesson-age'>Recommended age: 13+ · Biology / neuroscience · About 15 minutes</span><div class='learning-note'>Learning goal: identify three major brain regions, describe one function of each, and explain why coordination across regions matters.</div>" },
        { title: "Three regions, many connections", text: "Explore the cerebrum, cerebellum, and brainstem. Each has important roles, but everyday activities—like catching a ball—require information and signals to move between multiple regions.", detail: "<p>Tap each brain region. As you read, consider what information it handles and how it could work with the others during a familiar task such as walking, speaking, or learning a new movement.</p>" },
        { title: "Signals, senses, and responses", text: "Sensory receptors detect changes, and neural pathways carry information toward the central nervous system. The brain integrates information and helps coordinate responses. Some pathways also involve the spinal cord and can produce fast reflexes.", detail: "<span class='learning-note'>A simplified pathway: sensory input → processing and communication in the nervous system → coordinated response. Real neural circuits are highly interconnected and can involve many regions.</span><p>For example, stepping onto an uneven surface involves sensory feedback and rapid adjustments to posture and movement.</p>" },
        { title: "How brain science learns", text: "Scientists study the nervous system using evidence from many methods, including behavioral studies, brain imaging, and clinical observations. A brain image is not a simple map of one thought: results need careful interpretation, comparison, and replication.", detail: "<p>When reading a claim about the brain, ask: What evidence supports it? What was actually measured? Could other factors explain the result? These questions help separate careful science from oversimplified headlines.</p>" }
      ];
      const solarSlides = [
        { title: "A tour of our solar system 🪐", text: "The solar system formed about 4.6 billion years ago from a cloud of gas and dust. The Sun contains most of its mass. Eight planets, dwarf planets, moons, asteroids, and comets travel under the influence of gravity.", detail: "<span class='lesson-age'>Recommended age: 13+ · Astronomy / earth &amp; space science · About 15 minutes</span><div class='learning-note'>Learning goal: distinguish the rocky inner planets from the outer giant planets, compare planetary properties, and explain how gravity keeps planets in orbit.</div>" },
        { title: "The planets are not all alike", text: "Mercury, Venus, Earth, and Mars are relatively small rocky planets. Farther out, Jupiter and Saturn are gas giants; Uranus and Neptune are ice giants. Distance from the Sun, atmosphere, composition, and geology all shape each world's conditions.", detail: "<p>Select each planet to compare its size, composition, atmosphere, or another notable feature. The display is not to scale: planets and their distances vary enormously.</p>" },
        { title: "Gravity and orbits", text: "An orbit is a curved path around another object. A planet keeps moving forward, while the Sun's gravity continually changes the direction of that motion. Together, forward motion and gravity produce an orbit.", detail: "<span class='learning-note'>A useful model: imagine moving a ball forward while gravity pulls it downward. Orbital motion is more complex, but this helps show why an orbit is not simply a planet sitting still in a ring.</span><p>Orbits can be elliptical rather than perfectly circular, and the planets' orbital periods increase with distance from the Sun.</p>" },
        { title: "Compare worlds using evidence", text: "Planetary scientists compare measurements—such as mass, radius, atmospheric composition, and surface features—to build explanations about how worlds formed and changed. A single characteristic rarely tells the whole story.", detail: "<p>Choose two planets from the interactive display. Name one way they are similar and one way they differ. Which measurement would you want to investigate next, and why?</p>" }
      ];
      const dnaSlides = [
        { title: "DNA stores biological information 🧬", text: "DNA (deoxyribonucleic acid) is a molecule found in cells. A DNA molecule has two strands twisted into a double helix. Each strand has a sugar-phosphate backbone and bases that project inward. The order of the bases carries information.", detail: "<span class='lesson-age'>Recommended age: 13+ · Biology / genetics · About 30 minutes</span><div class='learning-note'>Goal: model a DNA sequence and its complementary strand, and explain the base-pairing rules. Materials: two colors or sets of colored beads, two lengths of string or elastic, labels, and scissors (with adult help if needed).</div>" },
        { title: "Meet the four DNA bases", text: "The four bases are adenine (A), thymine (T), cytosine (C), and guanine (G). In DNA, adenine pairs with thymine (A–T), and cytosine pairs with guanine (C–G). These specific partners form the rungs between the two strands.", detail: "<table class='data-table'><thead><tr><th>Letter</th><th>Base name</th><th>Pairs with</th></tr></thead><tbody><tr><td>A</td><td>Adenine</td><td>T · Thymine</td></tr><tr><td>T</td><td>Thymine</td><td>A · Adenine</td></tr><tr><td>C</td><td>Cytosine</td><td>G · Guanine</td></tr><tr><td>G</td><td>Guanine</td><td>C · Cytosine</td></tr></tbody></table><p>Choose four bead colors and make a key. Use the same color for the same letter on both bracelets.</p>" },
        { title: "Design two complementary strands", text: "First create a short strand, then use the pairing rules to build its partner. If one strand reads A–T–G–C, the complementary strand is T–A–C–G. The strands run alongside each other, with each base paired to its specific partner.", detail: "<p>Use the buttons to build your first sequence. The page will calculate the complementary sequence. Aim for at least six bases, then check each pair before making both bracelets.</p>" },
        { title: "Make two bracelets—and explain the model", text: "String the first bracelet in the order of your original sequence. String a second bracelet in the order of the complementary sequence. Lay them side by side and line up each pair: A with T, and C with G.", detail: "<span class='learning-note'>Important: this bead model shows the order and pairing of bases, but it is not a real DNA molecule. Real DNA has a sugar-phosphate backbone, chemical bonds, and a double-helix shape. A bracelet is a simplified learning model.</span><p>Check both sequences, label each one, and explain why the second strand is complementary rather than identical.</p>" }
      ];
      const planeSlides = [
        { title: "Paper airplane flight lab ✈️", text: "Investigate this question: how does wing design affect the distance a paper airplane travels? You will build two designs, learn about the forces on a glider, perform repeated trials, and explain your results using evidence.", detail: "<span class='lesson-age'>Recommended age: 13+ · Physics / engineering · About 30–40 minutes</span><div class='learning-note'>Materials: two identical sheets of paper, measuring tape, open safe space, masking tape for a launch line, and a data table or this lab's recorder. Never throw toward people.</div>" },
        { title: "Fold two different airplanes", text: "Make both planes from identical paper. Plane A has a narrow dart-style body; Plane B has broad wings. Follow the diagrams and fold steps. Press creases firmly and keep your paper size the same.", detail: "<div class='folding-diagrams'><article class='fold-card'><svg viewBox='0 0 240 120' role='img' aria-label='Dart plane top-view diagram'><path d='M120 12 L195 101 L120 82 L45 101 Z' fill='#dce7f3' stroke='#71829d' stroke-width='3'/><path d='M120 12 L120 82' stroke='#71829d' stroke-width='2' stroke-dasharray='5 4'/><path d='M80 73 L120 48 L160 73' fill='none' stroke='#849b90' stroke-width='3'/></svg><h4>Plane A: dart wings</h4><ol><li>Fold the sheet in half lengthwise; open it to mark the center line.</li><li>Fold both top corners to the center line.</li><li>Fold the new angled edges to the center line again to make a narrow nose.</li><li>Fold in half along the center line, then fold each side down to form slim wings.</li></ol></article><article class='fold-card'><svg viewBox='0 0 240 120' role='img' aria-label='Wide-wing glider top-view diagram'><path d='M120 12 L183 58 L160 104 L120 82 L80 104 L57 58 Z' fill='#dcebe5' stroke='#718d7e' stroke-width='3'/><path d='M120 12 L120 82' stroke='#718d7e' stroke-width='2' stroke-dasharray='5 4'/><path d='M82 61 L120 47 L158 61' fill='none' stroke='#849b90' stroke-width='3'/></svg><h4>Plane B: broad wings</h4><ol><li>Fold the sheet in half lengthwise; open it to mark the center line.</li><li>Fold both top corners to the center line.</li><li>Fold the nose down about 3 cm to make a blunt nose.</li><li>Fold in half along the center line; fold broad wings down, leaving a wider wing surface.</li></ol></article></div><p>These are starting patterns, not precision engineering plans. Fold both wings symmetrically and adjust them so they are level.</p>" },
        { title: "Understand the forces and plan a fair test", text: "After release, the plane glides as gravity pulls it down and air pushes against its motion. The wings redirect air and create lift; drag resists motion. A consistent launch matters because a harder or angled throw changes the result.", detail: "<ul><li>Mark one launch line and measure from it to the plane's first landing point.</li><li>Use the same paper, launcher, launch position, and approximate launch angle for both designs.</li><li>Change the wing design only; use three trials per design to reduce the influence of a single unusual throw.</li><li>Record every distance, including short flights. Do not discard inconvenient results.</li></ul><div class='learning-note'>Prediction: before testing, which plane do you expect to fly farther? Write a reason. A wide wing can increase lift at lower speeds, while a narrow dart may travel faster with less drag; real outcomes also depend on balance, folds, and launch technique.</div>" },
        { title: "Run and record six trials", text: "Take turns launching from the same line. Let the plane travel without adding a second push. Measure to the first point where it touches the ground. Record three flights for Plane A and three for Plane B.", detail: "<p>When all six trials are recorded, compare the averages. Repeated trials help reveal a pattern, but small samples and inconsistent throws still create uncertainty.</p>" },
        { title: "Explain your results with evidence", text: "Look at your distances and averages. Did one design travel farther on average? Was one design more consistent? Use numbers from your trials and connect your explanation to lift, drag, balance, and the way the plane was launched.", detail: "<p>Complete this explanation: “Plane __ traveled farther on average by __ m. One possible reason is __. My evidence is __. A source of uncertainty was __. In a future test I would change/keep __ because __.” Results can differ between groups—science is about explaining the data you actually collected.</p>" }
      ];
      const circuitSlides = [
        { title: "Build a virtual circuit 💡", text: "A circuit is a continuous path that lets electric charge move. In this online lab, you'll identify the parts of a simple circuit and test what happens when you open or close its switch.", detail: "<span class='lesson-age'>Recommended age: 13+ · Physics / electricity · About 15 minutes</span><div class='learning-note'>Learning goal: identify a source, conducting path, and load; distinguish open and closed circuits. This is a low-voltage interactive model, not instructions to work with mains electricity.</div>" },
        { title: "Source, pathway, and load", text: "A battery supplies a potential difference that can drive charge around a complete conducting loop. Wires provide a path, a bulb is a load that transfers electrical energy into light and heat, and a switch opens or closes the path.", detail: "<ul><li><strong>Battery:</strong> energy source that maintains a potential difference.</li><li><strong>Wires:</strong> conducting path connected to the components.</li><li><strong>Bulb:</strong> load that transfers electrical energy into other forms.</li><li><strong>Switch:</strong> creates a gap or completes the loop.</li></ul><p>In a simple series circuit, opening the loop anywhere stops the current throughout that loop.</p>" },
        { title: "Test the switch", text: "Predict what will happen when the path is open. Then toggle the switch to close the loop. Notice the change in the bulb. Open it again and explain why the bulb turns off.", detail: "<span class='learning-note'>Predict → test → observe → explain. In this simplified model, the bulb lights only when there is a complete conducting path.</span>" },
        { title: "Apply the model", text: "Imagine the bulb does not light. A scientist would check the circuit systematically: Is the battery connected? Is there a complete path? Is the switch closed? Is the bulb connected properly? A model helps us reason about a system before testing a physical circuit.", detail: "<p>Real circuits need correctly rated components. Never experiment with wall outlets or mains electricity. This browser activity is a conceptual model only.</p>" }
      ];
      const assessments = {
        flower: [
          { q: "What is a variable in the flower program?", options: ["A named place to store a value", "A type of flower", "A computer screen", "A random error"], answer: 0, why: "Variables store values such as the petal count or color." },
          { q: "What happens when you change petals from 6 to 8 and run the program?", options: ["The program stops forever", "The output flower has eight petals", "The color must also change", "The computer deletes the code"], answer: 1, why: "The function uses the petal-count value to draw the output." },
          { q: "Why is it useful to change one value at a time?", options: ["It makes code longer", "It helps identify which change caused the result", "It prevents the program from running", "It changes the computer's hardware"], answer: 1, why: "Changing one value at a time makes cause and effect easier to observe." },
          { q: "In this activity, what is growFlower?", options: ["A function that uses instructions to draw a flower", "A color name", "A keyboard key", "A type of variable"], answer: 0, why: "A function groups instructions that perform a task." },
          { q: "What should you do if the output surprises you?", options: ["Assume the computer guessed", "Inspect the values and instructions", "Delete the browser", "Never test it again"], answer: 1, why: "Debugging means checking the instructions and evidence to understand a result." }
        ],
        dna: [
          { q: "What does A stand for in DNA?", options: ["Adenine", "Atom", "Acid", "Axis"], answer: 0, why: "A is adenine." },
          { q: "Which base pairs with thymine (T) in DNA?", options: ["Cytosine", "Guanine", "Adenine", "Another thymine"], answer: 2, why: "Adenine pairs with thymine (A–T)." },
          { q: "Which base pairs with cytosine (C)?", options: ["Adenine", "Thymine", "Guanine", "Cytosine"], answer: 2, why: "Cytosine pairs with guanine (C–G)." },
          { q: "If one DNA strand reads A–C–G–T, what is its complementary strand?", options: ["A–C–G–T", "T–G–C–A", "A–G–C–T", "C–G–T–A"], answer: 1, why: "Pair each base in order: A→T, C→G, G→C, T→A." },
          { q: "What does the bead bracelet represent?", options: ["A simplified model of base order and pairing", "A complete real DNA molecule", "A cell membrane", "A protein"], answer: 0, why: "The beads model sequence and pairing, but not DNA's chemistry or double-helix structure." }
        ],
        plane: [
          { q: "Why should both paper airplanes use the same type of paper?", options: ["To keep the comparison fair", "To make them identical in every way", "Paper type is the only force", "It guarantees a perfect flight"], answer: 0, why: "Keep other conditions consistent so wing design is the main changed variable." },
          { q: "Why record several trials for each plane?", options: ["To make the activity longer", "To reduce the influence of one unusual throw", "To make averages unnecessary", "To ensure every result matches"], answer: 1, why: "Repeated trials help reveal a pattern despite natural variation." },
          { q: "Which force pulls a released paper airplane toward Earth?", options: ["Lift", "Drag", "Gravity", "Thrust"], answer: 2, why: "Gravity pulls the plane downward." },
          { q: "What should a strong conclusion include?", options: ["Only which plane looks best", "Measurements, a comparison, and a science-based explanation", "A guess without data", "Only the longest single trial"], answer: 1, why: "Use the recorded measurements and relevant physics to support your explanation." },
          { q: "If the two designs differ, what is the best next step?", options: ["Change many features at once", "Repeat and improve a controlled test", "Ignore the measurements", "Claim one design always wins"], answer: 1, why: "A controlled follow-up test can investigate which feature explains the difference." }
        ],
        circuit: [
          { q: "What is needed for a simple bulb circuit to light?", options: ["A complete conducting loop", "A broken wire", "A switch left open", "A bulb without a source"], answer: 0, why: "The circuit needs a complete path for current." },
          { q: "What does the switch do in this model?", options: ["Changes the bulb's color", "Opens or closes the conducting path", "Creates the wire", "Removes the battery"], answer: 1, why: "A switch controls whether the loop is complete." },
          { q: "What is the bulb in the circuit?", options: ["A load", "A switch", "A wire", "A measurement"], answer: 0, why: "The bulb is a load that transfers electrical energy into light and heat." },
          { q: "What happens when the circuit is open?", options: ["The path is complete", "The bulb lights brighter", "The loop has a gap and the bulb turns off", "The battery disappears"], answer: 2, why: "An open circuit interrupts the path." },
          { q: "Which is a safe way to use the online circuit lesson?", options: ["Connect it to a wall outlet", "Use the browser model only and avoid mains electricity", "Touch bare wires in a socket", "Use any battery regardless of rating"], answer: 1, why: "This is a conceptual model; never experiment with mains electricity." }
        ],
        brain: [
          { q: "Which brain region is especially important for coordination and balance?", options: ["Cerebellum", "Brainstem", "Retina", "Spinal disc"], answer: 0, why: "The cerebellum contributes to movement coordination, posture, and balance." },
          { q: "Which structure links the brain with the spinal cord and regulates essential automatic functions?", options: ["Cerebellum", "Brainstem", "Cerebrum", "Skull"], answer: 1, why: "The brainstem connects the brain with the spinal cord and regulates essential functions." },
          { q: "How do neurons communicate?", options: ["Only by changing color", "Through electrical and chemical signals", "By moving bones", "By producing oxygen"], answer: 1, why: "Neurons communicate through electrical and chemical signaling." },
          { q: "Why do many actions involve more than one brain region?", options: ["Brain regions communicate and contribute different functions", "Only one region is active at a time", "Regions do not share information", "The brain has no specialized areas"], answer: 0, why: "Brain regions are interconnected and coordinate across tasks." },
          { q: "What is a good way to evaluate a claim about brain science?", options: ["Check what evidence was measured and whether other explanations exist", "Trust every dramatic headline", "Assume a brain image proves a thought", "Ignore how the study was done"], answer: 0, why: "Scientific claims require careful evaluation of evidence and methods." }
        ],
        solar: [
          { q: "Which planet is the largest in our solar system?", options: ["Earth", "Jupiter", "Mars", "Neptune"], answer: 1, why: "Jupiter is the largest planet." },
          { q: "Which four planets are the rocky inner planets?", options: ["Mercury, Venus, Earth, Mars", "Jupiter, Saturn, Uranus, Neptune", "Earth, Jupiter, Saturn, Mars", "Venus, Saturn, Uranus, Neptune"], answer: 0, why: "Mercury, Venus, Earth, and Mars are the rocky inner planets." },
          { q: "What keeps planets in orbit around the Sun?", options: ["Gravity acting with their forward motion", "The planets are motionless", "Wind from Earth", "The Moon's light"], answer: 0, why: "Gravity continually changes the direction of the planets' motion as they move forward." },
          { q: "Which statement about the outer planets is correct?", options: ["They are all small rocky worlds", "Jupiter and Saturn are gas giants; Uranus and Neptune are ice giants", "They have no moons", "They do not orbit the Sun"], answer: 1, why: "The outer planets are classified as gas giants and ice giants." },
          { q: "Why do scientists compare measurements of planets?", options: ["To build evidence-based explanations about how worlds formed and changed", "To prove every planet is identical", "To remove uncertainty from science", "To decide which planet is prettiest"], answer: 0, why: "Comparisons of measured properties help test explanations about planetary formation and evolution." }
        ]
      };

      function flowerMarkup() {
        const petalCount = Number(document.getElementById("petal-count")?.value || 6);
        const color = document.getElementById("petal-color")?.value || "#a9b7d3";
        const petals = Array.from({ length: petalCount }, (_, i) => `<ellipse cx="90" cy="65" rx="13" ry="31" fill="${color}" transform="rotate(${i * 360 / petalCount} 90 90)"/>`).join("");
        return `<svg viewBox="0 0 180 210" role="img" aria-label="${petalCount}-petal ${document.getElementById("petal-color")?.selectedOptions[0]?.textContent || "blue"} flower"><path d="M90 112 Q88 155 90 199" fill="none" stroke="#6f9d83" stroke-width="7" stroke-linecap="round"/><path d="M90 165 Q59 143 54 164 Q64 183 90 165Z" fill="#92be98"/><path d="M90 177 Q116 151 127 169 Q122 188 90 177Z" fill="#add0ac"/>${petals}<circle cx="90" cy="90" r="18" fill="#d5cfad"/><circle cx="84" cy="87" r="2.5" fill="#4e5360"/><circle cx="96" cy="87" r="2.5" fill="#4e5360"/><path d="M85 94 Q90 100 96 94" fill="none" stroke="#4e5360" stroke-width="2" stroke-linecap="round"/></svg>`;
      }
      function updateFlower() {
        const preview = document.getElementById("flower-preview");
        if (!preview) return;
        const markup = flowerMarkup();
        preview.innerHTML = markup;
        const codePreview = document.getElementById("flower-code-preview");
        if (codePreview) codePreview.innerHTML = markup;
      }
      const brainInfo = {
        cerebrum: ["Cerebrum", "The largest brain region. It supports many complex functions, including perception, voluntary movement, language, memory, and reasoning."],
        cerebellum: ["Cerebellum", "The cerebellum helps coordinate movement, posture, and balance. It also contributes to motor learning and timing."],
        brainstem: ["Brainstem", "The brainstem connects the brain with the spinal cord and helps regulate essential automatic functions, including breathing and heart rate."]
      };
      const planetInfo = {
        mercury: "Mercury is the smallest planet and the closest to the Sun. Its rocky surface has extreme temperature changes.",
        venus: "Venus has a thick atmosphere and a surface hot enough to melt lead. Its clouds trap heat through a powerful greenhouse effect.",
        earth: "Earth has liquid water on its surface and supports a remarkable diversity of life. It is the largest of the four rocky inner planets.",
        mars: "Mars is a cold, rocky world with a thin atmosphere. Evidence suggests liquid water flowed on its surface in the distant past.",
        jupiter: "Jupiter is the largest planet. This gas giant has dozens of moons and a huge storm called the Great Red Spot.",
        saturn: "Saturn is a gas giant known for its bright rings, which are made mostly of ice and rocky particles.",
        uranus: "Uranus is an ice giant that rotates on its side relative to its orbit, giving it extreme seasonal changes.",
        neptune: "Neptune is a distant ice giant with very fast winds. It takes about 165 Earth years to orbit the Sun."
      };
      const lessonSlides = { flower: flowerSlides, brain: brainSlides, solar: solarSlides, dna: dnaSlides, plane: planeSlides, circuit: circuitSlides };
      const lessonNames = { flower: "Code a blooming flower", brain: "How your brain works", solar: "A tour of the solar system", dna: "Build two DNA bracelets", plane: "Paper airplane flight lab", circuit: "Build a virtual circuit" };
      const lessonCategories = { flower: "creative coding · activity", brain: "neuroscience · mini course", solar: "astronomy · mini course", dna: "genetics · hands-on activity", plane: "physics · hands-on activity", circuit: "electricity · online activity" };
      const lessonAge = { flower: "Recommended age: 13+", brain: "Recommended age: 13+", solar: "Recommended age: 13+", dna: "Recommended age: 13+", plane: "Recommended age: 13+", circuit: "Recommended age: 13+" };
      const printWorksheets = {
        flower: ["Write what each variable controls in the flower program.", "Predict the output with 8 petals and lilac color. Then describe what your code actually produced.", "Name one change you made and explain how it changed the output.", "A result surprised you. What would you inspect while debugging?"],
        brain: ["Describe one role of the cerebrum, cerebellum, and brainstem.", "Explain how two nervous-system regions might work together during movement.", "What kind of evidence could help scientists study the brain?", "Write one question you still have about neuroscience."],
        solar: ["Name the four rocky inner planets.", "Explain how gravity and forward motion help maintain an orbit.", "Compare two planets using one measured property.", "Write one question you would investigate about another world."],
        dna: ["Write the full names of A, T, C, and G.", "Complete the complementary sequence: A–C–G–T–T–C → ______________.", "Draw or describe how your two bracelet strands pair.", "Why is a bead model not identical to a real DNA molecule?"],
        plane: ["Record three trial distances for each design in the table.", "Calculate and compare the average flight distance for each design.", "Use evidence and forces to explain why your results may differ.", "Name one source of uncertainty and one improvement for a future test."],
        circuit: ["Draw a closed circuit and label the battery, wires, switch, and bulb.", "Explain what changes when the switch opens the circuit.", "Describe the role of the source, pathway, and load.", "Write one safety rule for real electricity experiments."]
      };
      function updateProgress() {
        const total = lessonSlides[lesson].length + assessments[lesson].length + 1;
        const completed = quizIndex < 0 ? slide + 1 : lessonSlides[lesson].length + quizIndex + 1;
        progress.style.width = `${Math.min(100, completed / total * 100)}%`;
      }
      function braceletMarkup(sequence) {
        if (!sequence) return '<span class="duration">Add bases above to design both bracelets.</span>';
        return [...sequence].map(base => `<span class="bead bead-${base}" aria-label="${base}">${base}</span>`).join("");
      }
      function currentAverages() {
        return ["A", "B"].map(design => {
          const values = flightTrials.filter(trial => trial.design === design).map(trial => trial.distance);
          return values.length ? values.reduce((sum, value) => sum + value, 0) / values.length : null;
        });
      }
      function worksheetMarkup() {
        const rows = printWorksheets[lesson].map((prompt, index) => `<h2>${index + 1}. ${prompt}</h2><div class="write-lines"></div>`).join("");
        const table = lesson === "plane" ? `<h2>Flight data</h2><table><thead><tr><th>Design</th><th>Trial 1 (m)</th><th>Trial 2 (m)</th><th>Trial 3 (m)</th><th>Average (m)</th></tr></thead><tbody><tr><td>A — dart</td><td></td><td></td><td></td><td></td></tr><tr><td>B — broad wings</td><td></td><td></td><td></td><td></td></tr></tbody></table>` : "";
        return `<h1>Brain Bloom · ${lessonNames[lesson]} Worksheet</h1><p>Name: ____________________________________ &nbsp;&nbsp; Date: ______________</p><p>${lessonAge[lesson]} · Optional printable worksheet</p>${table}${rows}<p>Brain Bloom · Learn by making, testing, and explaining.</p>`;
      }
      function printWorksheet() {
        const printArea = document.getElementById("worksheet-print");
        printArea.innerHTML = worksheetMarkup();
        printArea.setAttribute("aria-hidden", "false");
        window.print();
        printArea.setAttribute("aria-hidden", "true");
      }
      function downloadBadge() {
        const title = lessonNames[lesson];
        const svg = `<svg xmlns="http://www.w3.org/2000/svg" width="900" height="600" viewBox="0 0 900 600"><rect width="900" height="600" rx="42" fill="#f3f6f3"/><rect x="22" y="22" width="856" height="556" rx="32" fill="none" stroke="#829b8c" stroke-width="5"/><text x="450" y="145" text-anchor="middle" font-family="Arial,sans-serif" font-size="34" fill="#53675d">BRAIN BLOOM · LEARNING BADGE</text><text x="450" y="245" text-anchor="middle" font-family="Arial,sans-serif" font-size="70">✿</text><text x="450" y="345" text-anchor="middle" font-family="Arial,sans-serif" font-size="43" font-weight="bold" fill="#293348">Curious Mind</text><text x="450" y="415" text-anchor="middle" font-family="Arial,sans-serif" font-size="27" fill="#596779">Completed: ${title}</text><text x="450" y="485" text-anchor="middle" font-family="Arial,sans-serif" font-size="22" fill="#6a7e72">Quiz score: ${quizScore}/${assessments[lesson].length} · Keep exploring</text></svg>`;
        const url = URL.createObjectURL(new Blob([svg], { type: "image/svg+xml" }));
        const link = document.createElement("a");
        link.href = url;
        link.download = `brain-bloom-${lesson}-badge.svg`;
        link.click();
        setTimeout(() => URL.revokeObjectURL(url), 1000);
      }
      function renderCompletion() {
        const passed = quizScore >= 4;
        updateProgress();
        content.innerHTML = `<div class="eyebrow"><span class="dot"></span> lesson complete</div><h2 id="lesson-title">${passed ? "Congratulations on your achievement!" : "Lesson complete — keep practicing!"}</h2><p>You scored <strong>${quizScore} out of ${assessments[lesson].length}</strong>. ${passed ? "You showed a strong understanding of the key ideas. Your badge is ready to download." : "Review the lesson and try again whenever you like. You need 4 out of 5 correct to earn the badge."}</p>${passed ? `<div class="badge-card" role="status"><div class="badge-icon" aria-hidden="true">🏅</div><h3>Curious Mind</h3><p>${lessonNames[lesson]}</p><p>Quiz score: ${quizScore}/${assessments[lesson].length}</p></div><div class="badge-popup" id="badge-popup" role="dialog" aria-modal="true" aria-labelledby="badge-popup-title"><section class="badge-popup-card"><div class="badge-icon" aria-hidden="true">🏅</div><h2 id="badge-popup-title">Congrats!</h2><p>You passed the mini test with ${quizScore}/${assessments[lesson].length}. You earned a Curious Mind badge.</p><div class="badge-actions"><button class="button" id="download-badge">Download your badge</button><button class="button soft" id="close-badge-popup">Continue</button></div></section></div>` : ""}<div class="badge-actions">${!passed ? '<button class="button soft" id="retry-quiz">Try the quiz again</button>' : ""}<button class="button soft" id="print-worksheet">Print optional worksheet</button></div><div class="lesson-actions"><button class="button soft small" id="previous-slide">← Review lesson</button><span class="slide-count">Completed</span><button class="button small" id="finish-lesson">Finish</button></div>`;
        document.getElementById("download-badge")?.addEventListener("click", downloadBadge);
        document.getElementById("close-badge-popup")?.addEventListener("click", () => document.getElementById("badge-popup").remove());
        document.getElementById("print-worksheet").addEventListener("click", printWorksheet);
        document.getElementById("retry-quiz")?.addEventListener("click", () => { quizIndex = 0; quizScore = 0; selectedAnswer = null; renderLesson(); });
        document.getElementById("previous-slide").addEventListener("click", () => { quizIndex = -1; slide = lessonSlides[lesson].length - 1; renderLesson(); });
        document.getElementById("finish-lesson").addEventListener("click", closeLesson);
      }
      function renderQuiz() {
        if (quizIndex >= assessments[lesson].length) { renderCompletion(); return; }
        const question = assessments[lesson][quizIndex];
        updateProgress();
        const options = question.options.map((option, index) => `<button class="quiz-option${selectedAnswer === index && answerRevealed ? index === question.answer ? " correct" : " incorrect" : ""}" data-quiz-answer="${index}" ${answerRevealed ? "disabled" : ""}>${option}</button>`).join("");
        const feedback = answerRevealed ? `<p class="quiz-feedback" aria-live="polite">${selectedAnswer === question.answer ? "Correct! " : "Not quite. "}${question.why}</p>` : "";
        const action = answerRevealed ? (quizIndex === assessments[lesson].length - 1 ? "See results →" : "Next question →") : "Check answer";
        content.innerHTML = `<div class="eyebrow"><span class="dot"></span> mini test · question ${quizIndex + 1} of ${assessments[lesson].length}</div><h2 id="lesson-title">Check what you learned</h2><p>${question.q}</p><div class="quiz-options">${options}</div>${feedback}<div class="lesson-actions"><button class="button soft small" id="previous-slide">← Review lesson</button><span class="slide-count">Score so far: ${quizScore}</span><button class="button small" id="quiz-action" ${selectedAnswer === null && !answerRevealed ? "disabled" : ""}>${action}</button></div>`;
        content.querySelectorAll("[data-quiz-answer]").forEach(button => button.addEventListener("click", () => {
          selectedAnswer = Number(button.dataset.quizAnswer);
          answerRevealed = false;
          renderQuiz();
        }));
        document.getElementById("quiz-action").addEventListener("click", () => {
          if (!answerRevealed) {
            if (selectedAnswer === question.answer) quizScore++;
            answerRevealed = true;
          } else {
            quizIndex++;
            selectedAnswer = null;
            answerRevealed = false;
          }
          renderQuiz();
        });
        document.getElementById("previous-slide").addEventListener("click", () => { quizIndex = -1; slide = lessonSlides[lesson].length - 1; renderLesson(); });
      }
      let answerRevealed = false;
      function renderLesson() {
        if (quizIndex >= 0) { renderQuiz(); return; }
        const slides = lessonSlides[lesson];
        const current = slides[slide];
        updateProgress();
        let extra = "";
        if (lesson === "flower" && slide === 2) {
          extra = `<div class="interactive-panel flower-lab"><div class="flower-preview" id="flower-preview">${flowerMarkup()}</div><div class="controls"><label for="petal-count">Petal count</label><select id="petal-count"><option value="4">4 petals</option><option value="6" selected>6 petals</option><option value="8">8 petals</option></select><label for="petal-color">Petal color</label><select id="petal-color"><option value="#a9b7d3" data-name="blue">Blue</option><option value="#aaa4cb" data-name="lilac">Lilac</option><option value="#d5cfad" data-name="sage">Sage</option><option value="#8fc9a3" data-name="mint">Mint</option></select><div class="code-workspace"><div><label for="flower-code">Edit the code</label><textarea id="flower-code" spellcheck="false">petals = 6\ncolor = "blue"\ngrowFlower(petals, color)</textarea><div class="code-actions"><button class="button small" id="run-flower-code">Run code ▶</button><span class="duration" id="code-feedback" aria-live="polite">Edit a value, then run.</span></div></div><div class="code-preview" id="flower-code-preview">${flowerMarkup()}</div></div><pre class="code-snippet">petals = a number from 4, 6, or 8\ncolor = "blue", "lilac", "sage", or "mint"</pre></div></div>`;
        } else if (lesson === "brain" && slide === 1) {
          extra = `<div class="interactive-panel brain-lab"><div class="brain-map"><span class="brain-big" aria-hidden="true">🧠</span><button class="brain-pin p1" data-brain="cerebrum">Cerebrum</button><button class="brain-pin p2" data-brain="cerebellum">Cerebellum</button><button class="brain-pin p3" data-brain="brainstem">Brainstem</button></div><div class="brain-info" id="brain-info"><h3>Select a brain region</h3><p>Explore each region and connect its role to the wider nervous system.</p></div></div>`;
        } else if (lesson === "solar" && slide === 1) {
          extra = `<div class="interactive-panel"><strong>Select a planet to compare</strong><div class="planet-grid">${[["mercury", "☿"], ["venus", "♀"], ["earth", "🌍"], ["mars", "♂"], ["jupiter", "🟠"], ["saturn", "🪐"], ["uranus", "🔵"], ["neptune", "🔷"]].map(([name, icon]) => `<button class="planet-button" data-planet="${name}"><span aria-hidden="true">${icon}</span>${name[0].toUpperCase() + name.slice(1)}</button>`).join("")}</div><div class="planet-info" id="planet-info" aria-live="polite">Choose any planet to see a fact. Planet sizes and distances are not shown to scale.</div></div>`;
        } else if (lesson === "dna" && slide === 2) {
          extra = `<div class="interactive-panel"><strong>Design the sequence for bracelet 1</strong><p class="lab-hint">Select at least six bases. Bracelet 2 will show the complementary sequence using A–T and C–G pairing.</p><div class="base-buttons"><button class="base-button" data-base="A">Add A <span>Adenine · green</span></button><button class="base-button" data-base="T">Add T <span>Thymine · blue</span></button><button class="base-button" data-base="C">Add C <span>Cytosine · lilac</span></button><button class="base-button" data-base="G">Add G <span>Guanine · gold</span></button><button class="base-button" id="clear-sequence">Clear</button></div><div class="strand-result"><strong>Bracelet 1 · your DNA strand:</strong><div class="bead-chain" id="strand-one"></div><strong>Bracelet 2 · complementary strand:</strong><div class="bead-chain" id="strand-two"></div><div id="sequence-rule">Add six or more bases to see both strands.</div></div></div>`;
        } else if (lesson === "plane" && slide === 3) {
          const entries = flightTrials.map(trial => `<tr><td>${trial.design}</td><td>${trial.number}</td><td>${trial.distance.toFixed(2)}</td></tr>`).join("");
          const averages = currentAverages();
          extra = `<div class="interactive-panel"><strong>Record three trials for each design</strong><p class="lab-hint">Measure from the launch line to the first landing point. Record every flight in meters. Current averages — A: ${averages[0] === null ? "—" : averages[0].toFixed(2) + " m"} · B: ${averages[1] === null ? "—" : averages[1].toFixed(2) + " m"}</p><div class="trial-controls"><label for="plane-design">Plane design<select id="plane-design"><option value="A">A — dart/narrow wings</option><option value="B">B — broad wings</option></select></label><label for="flight-distance">Distance (meters)<input id="flight-distance" type="number" min="0" max="100" step="0.01" placeholder="e.g. 4.20"></label><button class="button small" id="record-flight">Record trial</button></div><p id="trial-error" class="quiz-feedback" aria-live="polite"></p><table class="data-table"><thead><tr><th>Design</th><th>Trial</th><th>Distance (m)</th></tr></thead><tbody>${entries || '<tr><td colspan="3">No trials recorded yet.</td></tr>'}</tbody></table><p class="lab-hint">Trials recorded: A ${flightTrials.filter(item => item.design === "A").length}/3 · B ${flightTrials.filter(item => item.design === "B").length}/3</p></div>`;
        } else if (lesson === "circuit" && slide === 2) {
          extra = `<div class="interactive-panel"><div class="circuit-sim"><svg viewBox="0 0 440 190" role="img" aria-label="Battery, wires, switch, and bulb in a circuit"><path d="M100 55 H190 M250 55 H340 V145 H100 V55" fill="none" stroke="#849b90" stroke-width="8" stroke-linecap="round"/><path d="M100 55 H190 M250 55 H340 V145 H100 V55" fill="none" stroke="#536a5f" stroke-width="2" stroke-dasharray="7 8"/><rect x="70" y="74" width="60" height="50" rx="8" fill="#dce7f3" stroke="#71829d" stroke-width="3"/><text x="100" y="105" text-anchor="middle" font-size="14" fill="#293348">Cell</text><circle id="circuit-bulb" class="circuit-bulb" cx="340" cy="100" r="25" stroke="#71829d" stroke-width="4"/><text x="340" y="160" text-anchor="middle" font-size="13" fill="#53675d">Bulb</text><circle cx="220" cy="55" r="6" fill="#536a5f"/><path id="switch-arm" d="M220 55 L246 34" stroke="#71829d" stroke-width="6" stroke-linecap="round"/></svg><div><h3 id="circuit-state">Switch open · bulb off</h3><p class="lab-hint">The gap breaks the path. Close the switch to complete the loop.</p><button class="button" id="toggle-circuit" aria-pressed="false">Close the switch</button><p id="circuit-observation" class="quiz-feedback" aria-live="polite">Make a prediction, then test the switch.</p></div></div></div>`;
        } else if (lesson === "plane" && slide === 4) {
          const averageRows = ["A", "B"].map(design => {
            const values = flightTrials.filter(trial => trial.design === design).map(trial => trial.distance);
            const average = values.reduce((sum, value) => sum + value, 0) / values.length;
            const min = Math.min(...values);
            const max = Math.max(...values);
            return `<tr><td>Plane ${design} (${design === "A" ? "dart" : "broad wings"})</td><td>${values.map(value => value.toFixed(2)).join(", ")}</td><td>${average.toFixed(2)} m</td><td>${(max - min).toFixed(2)} m</td></tr>`;
          }).join("");
          extra = `<div class="interactive-panel"><strong>Your results</strong><table class="data-table"><thead><tr><th>Design</th><th>Trial distances (m)</th><th>Average</th><th>Range</th></tr></thead><tbody>${averageRows}</tbody></table><p class="lab-hint">The average summarizes the distances. The range (largest minus smallest) gives a simple view of variation. Use these measurements as evidence in your explanation below.</p></div>`;
        }
        const previous = slide > 0 ? `<button class="button soft small" id="previous-slide">← Back</button>` : `<span></span>`;
        const nextLabel = slide === slides.length - 1 ? "Start mini test →" : "Continue →";
        const nextDisabled = lesson === "plane" && slide === 3 && (flightTrials.filter(item => item.design === "A").length < 3 || flightTrials.filter(item => item.design === "B").length < 3);
        const dnaNeedsSequence = lesson === "dna" && slide === 2 && dnaSequence.length < 6;
        content.innerHTML = `<div class="eyebrow"><span class="dot"></span>${lessonCategories[lesson]}</div><span class="lesson-age">${lessonAge[lesson]}</span><h2 id="lesson-title">${current.title}</h2><p>${current.text}</p>${current.detail || ""}${extra}<div class="lesson-actions">${previous}<span class="slide-count">Lesson ${slide + 1} of ${slides.length} · Test follows</span><button class="button small" id="next-slide" ${(nextDisabled || dnaNeedsSequence) ? "disabled" : ""}>${nextLabel}</button></div>${nextDisabled ? '<p class="lab-hint">Record at least three trials for each airplane design to continue.</p>' : ""}${lesson === "dna" && slide === 2 ? `<p class="lab-hint" id="dna-next-hint">${dnaNeedsSequence ? "Build a sequence of at least six bases to create both bracelet strands." : "Both complementary bracelet strands are ready."}</p>` : ""}`;
        document.querySelector(".lesson-window").scrollTop = 0;
        document.getElementById("next-slide").addEventListener("click", () => {
          if (slide < slides.length - 1) { slide++; renderLesson(); }
          else { quizIndex = 0; quizScore = 0; selectedAnswer = null; answerRevealed = false; renderLesson(); }
        });
        document.getElementById("previous-slide")?.addEventListener("click", () => { slide--; renderLesson(); });
        document.getElementById("petal-count")?.addEventListener("change", updateFlower);
        document.getElementById("petal-color")?.addEventListener("change", updateFlower);
        document.getElementById("run-flower-code")?.addEventListener("click", () => {
          const source = document.getElementById("flower-code").value;
          const petals = source.match(/^\s*petals\s*=\s*(4|6|8)\s*;?\s*$/m);
          const color = source.match(/^\s*color\s*=\s*["'](blue|lilac|sage|mint)["']\s*;?\s*$/m);
          const feedback = document.getElementById("code-feedback");
          if (!petals || !color || !/growFlower\s*\(\s*petals\s*,\s*color\s*\)/.test(source)) {
            feedback.textContent = "Use petals = 4, 6, or 8; a supported color; and growFlower(petals, color).";
            return;
          }
          const colors = { blue: "#a9b7d3", lilac: "#aaa4cb", sage: "#d5cfad", mint: "#8fc9a3" };
          document.getElementById("petal-count").value = petals[1];
          document.getElementById("petal-color").value = colors[color[1]];
          updateFlower();
          document.getElementById("flower-code-preview").innerHTML = flowerMarkup();
          feedback.textContent = `Code ran: ${petals[1]} petals, ${color[1]}.`;
        });
        content.querySelectorAll("[data-brain]").forEach(button => button.addEventListener("click", () => {
          content.querySelectorAll("[data-brain]").forEach(pin => pin.classList.toggle("selected", pin === button));
          const [title, description] = brainInfo[button.dataset.brain];
          document.getElementById("brain-info").innerHTML = `<h3>${title}</h3><p>${description}</p>`;
        }));
        content.querySelectorAll("[data-planet]").forEach(button => button.addEventListener("click", () => {
          content.querySelectorAll("[data-planet]").forEach(planet => planet.classList.toggle("selected", planet === button));
          document.getElementById("planet-info").textContent = planetInfo[button.dataset.planet];
        }));
        content.querySelectorAll("[data-base]").forEach(button => button.addEventListener("click", () => {
          if (dnaSequence.length < 12) dnaSequence += button.dataset.base;
          updateSequence();
        }));
        document.getElementById("clear-sequence")?.addEventListener("click", () => { dnaSequence = ""; updateSequence(); });
        function updateSequence() {
          const complement = [...dnaSequence].map(base => ({ A: "T", T: "A", C: "G", G: "C" })[base]).join("");
          document.getElementById("strand-one").innerHTML = braceletMarkup(dnaSequence);
          document.getElementById("strand-two").innerHTML = braceletMarkup(complement);
          document.getElementById("sequence-rule").textContent = dnaSequence.length >= 6 ? `Bracelet 1: ${dnaSequence} · Bracelet 2: ${complement} · Pair each bead directly across.` : `Add ${6 - dnaSequence.length} more base${dnaSequence.length === 5 ? "" : "s"} to make two bracelet strands.`;
          document.getElementById("next-slide").disabled = dnaSequence.length < 6;
          document.getElementById("dna-next-hint").textContent = dnaSequence.length < 6 ? "Build a sequence of at least six bases to create both bracelet strands." : "Both complementary bracelet strands are ready.";
        }
        document.getElementById("record-flight")?.addEventListener("click", () => {
          const input = document.getElementById("flight-distance");
          const distance = Number(input.value);
          const design = document.getElementById("plane-design").value;
          const error = document.getElementById("trial-error");
          if (input.value === "" || !Number.isFinite(distance) || distance < 0 || distance > 100 || flightTrials.filter(item => item.design === design).length >= 3) {
            error.textContent = flightTrials.filter(item => item.design === design).length >= 3 ? "That design already has three trials. Switch designs to record the other plane." : "Enter a distance between 0 and 100 meters.";
            return;
          }
          flightTrials.push({ design, distance, number: flightTrials.filter(item => item.design === design).length + 1 });
          renderLesson();
          document.getElementById("plane-design").value = design;
        });
        document.getElementById("toggle-circuit")?.addEventListener("click", event => {
          const closed = event.currentTarget.getAttribute("aria-pressed") !== "true";
          event.currentTarget.setAttribute("aria-pressed", String(closed));
          event.currentTarget.textContent = closed ? "Open the switch" : "Close the switch";
          document.getElementById("circuit-state").textContent = closed ? "Switch closed · bulb on" : "Switch open · bulb off";
          document.getElementById("circuit-bulb").classList.toggle("lit", closed);
          document.getElementById("switch-arm").setAttribute("d", closed ? "M220 55 L246 55" : "M220 55 L246 34");
          document.getElementById("circuit-observation").textContent = closed ? "The path is complete, so the model's bulb lights." : "The gap interrupts the loop, so the bulb is off.";
        });
      }
      function openLesson(type) {
        lesson = type;
        slide = 0;
        quizIndex = -1;
        quizScore = 0;
        selectedAnswer = null;
        answerRevealed = false;
        dnaSequence = "";
        flightTrials = [];
        previousFocus = document.activeElement;
        lessonName.textContent = lessonNames[type];
        overlay.classList.add("open");
        document.body.style.overflow = "hidden";
        renderLesson();
        closeButton.focus();
      }
      function closeLesson() {
        overlay.classList.remove("open");
        document.body.style.overflow = "";
        document.getElementById("worksheet-print").innerHTML = "";
        if (previousFocus) previousFocus.focus();
      }
      document.querySelectorAll("[data-lesson]").forEach(button => button.addEventListener("click", () => openLesson(button.dataset.lesson)));
      closeButton.addEventListener("click", closeLesson);
      overlay.addEventListener("click", event => { if (event.target === overlay) closeLesson(); });
      document.addEventListener("keydown", event => {
        if (event.key === "Escape" && overlay.classList.contains("open")) closeLesson();
      });
      document.querySelectorAll(".filter-chip").forEach(button => button.addEventListener("click", () => {
        document.querySelectorAll(".filter-chip").forEach(chip => chip.classList.toggle("selected", chip === button));
        const filter = button.dataset.filter;
        document.querySelectorAll("#activities-view .learning-card").forEach(card => {
          card.style.display = filter === "all" || card.dataset.category.split(" ").includes(filter) ? "" : "none";
        });
      }));
    })();
  </script>
</body>
</html>
