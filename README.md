# xyz-asd-xyz-asd-yahu-private

<!DOCTYPE html>
<html lang="de">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>xyz.77</title>
  <style>
    :root {
      --bg-deep: #0a0a12;
      --bg-mid: #12121f;
      --accent: #3b82f6;
      --accent-hover: #2563eb;
      --window-bg: rgba(22, 22, 35, 0.95);
      --window-border: rgba(255,255,255,0.08);
      --text: #e5e7eb;
      --text-muted: #9ca3af;
      --taskbar-bg: rgba(10, 10, 18, 0.92);
    }

    * {
      margin: 0;
      padding: 0;
      box-sizing: border-box;
    }

    body {
      font-family: "Segoe UI", -apple-system, BlinkMacSystemFont, Roboto, "Helvetica Neue", Arial, sans-serif;
      height: 100vh;
      overflow: hidden;
      background: radial-gradient(ellipse at 30% 20%, #1a1a2e 0%, #0a0a12 50%, #050508 100%);
      position: relative;
      color: var(--text);
      user-select: none;
    }

    body::before {
      content: "";
      position: absolute;
      inset: 0;
      background: 
        radial-gradient(ellipse 60% 40% at 20% 80%, rgba(59, 130, 246, 0.08) 0%, transparent 50%),
        radial-gradient(ellipse 50% 30% at 80% 30%, rgba(99, 102, 241, 0.06) 0%, transparent 45%);
      pointer-events: none;
      z-index: 0;
    }

    /* Desktop */
    #desktop {
      position: relative;
      width: 100%;
      height: calc(100vh - 52px);
      z-index: 1;
      padding: 24px 20px;
      display: flex;
      flex-direction: column;
      flex-wrap: wrap;
      align-content: flex-start;
      gap: 16px;
    }

    .desktop-icon {
      width: 76px;
      display: flex;
      flex-direction: column;
      align-items: center;
      gap: 6px;
      cursor: pointer;
      padding: 6px 4px;
      border-radius: 8px;
      transition: background 0.15s;
    }

    .desktop-icon:hover {
      background: rgba(255,255,255,0.08);
    }

    .desktop-icon:active {
      background: rgba(255,255,255,0.12);
    }

    .icon-circle {
      width: 48px;
      height: 48px;
      border-radius: 12px;
      display: flex;
      align-items: center;
      justify-content: center;
      font-size: 24px;
      box-shadow: 0 4px 12px rgba(0,0,0,0.4);
    }

    .icon-label {
      font-size: 11px;
      color: #e5e7eb;
      text-shadow: 0 1px 3px rgba(0,0,0,0.8);
      text-align: center;
      max-width: 72px;
      line-height: 1.2;
    }

    .c1 { background: linear-gradient(135deg, #3b82f6, #1d4ed8); }
    .c2 { background: linear-gradient(135deg, #6366f1, #4338ca); }
    .c3 { background: linear-gradient(135deg, #8b5cf6, #6d28d9); }
    .c4 { background: linear-gradient(135deg, #10b981, #047857); }
    .c5 { background: linear-gradient(135deg, #f59e0b, #d97706); }
    .c6 { background: linear-gradient(135deg, #ef4444, #b91c1c); }
    .c7 { background: linear-gradient(135deg, #06b6d4, #0e7490); }
    .c8 { background: linear-gradient(135deg, #64748b, #334155); }

    /* Windows */
    .window {
      position: absolute;
      background: var(--window-bg);
      border: 1px solid var(--window-border);
      border-radius: 10px;
      box-shadow: 0 20px 50px rgba(0,0,0,0.5), 0 0 0 1px rgba(255,255,255,0.03);
      backdrop-filter: blur(20px);
      z-index: 50;
      min-width: 320px;
      min-height: 200px;
      display: none;
      flex-direction: column;
      overflow: hidden;
      resize: both;
    }

    .window.open {
      display: flex;
    }

    .window.active {
      z-index: 100;
    }

    .titlebar {
      height: 36px;
      background: rgba(0,0,0,0.25);
      display: flex;
      align-items: center;
      justify-content: space-between;
      padding: 0 12px;
      cursor: grab;
      flex-shrink: 0;
    }

    .titlebar:active {
      cursor: grabbing;
    }

    .titlebar-left {
      display: flex;
      align-items: center;
      gap: 8px;
      font-size: 13px;
      font-weight: 500;
      color: var(--text);
    }

    .titlebar-left .app-icon {
      font-size: 16px;
    }

    .window-controls {
      display: flex;
      gap: 8px;
    }

    .win-btn {
      width: 12px;
      height: 12px;
      border-radius: 50%;
      border: none;
      cursor: pointer;
      transition: filter 0.15s;
    }

    .win-btn:hover {
      filter: brightness(1.2);
    }

    .win-close { background: #ef4444; }
    .win-min { background: #eab308; }
    .win-max { background: #22c55e; }

    .window-body {
      flex: 1;
      padding: 16px;
      overflow: auto;
      color: var(--text);
      font-size: 14px;
    }

    /* Setup Window */
    #setupWindow {
      width: 380px;
      top: 50%;
      left: 50%;
      transform: translate(-50%, -50%);
      z-index: 200;
    }

    #setupWindow .window-body {
      text-align: center;
      padding: 12px 28px 28px;
    }

    .logo {
      width: 48px;
      height: 48px;
      margin: 0 auto 14px;
      background: linear-gradient(135deg, #3b82f6, #1d4ed8);
      border-radius: 14px;
      display: flex;
      align-items: center;
      justify-content: center;
      font-size: 26px;
      box-shadow: 0 4px 16px rgba(59, 130, 246, 0.4);
    }

    #setupWindow h1 {
      font-size: 22px;
      font-weight: 650;
      margin-bottom: 4px;
    }

    .subtitle {
      font-size: 14px;
      color: var(--text-muted);
      margin-bottom: 22px;
    }

    .field-label {
      font-size: 11px;
      font-weight: 600;
      letter-spacing: 0.04em;
      color: var(--text-muted);
      text-align: left;
      margin-bottom: 6px;
      text-transform: uppercase;
    }

    .input-field {
      width: 100%;
      padding: 11px 14px;
      border: 1px solid rgba(255,255,255,0.12);
      border-radius: 8px;
      font-size: 15px;
      outline: none;
      background: rgba(0,0,0,0.3);
      color: var(--text);
      margin-bottom: 20px;
      transition: border-color 0.2s, box-shadow 0.2s;
    }

    .input-field:focus {
      border-color: var(--accent);
      box-shadow: 0 0 0 3px rgba(59, 130, 246, 0.25);
    }

    .input-field::placeholder {
      color: #6b7280;
    }

    .button-row {
      display: flex;
      justify-content: space-between;
      gap: 12px;
    }

    .btn {
      padding: 9px 20px;
      border-radius: 8px;
      font-size: 14px;
      font-weight: 500;
      cursor: pointer;
      border: none;
      transition: all 0.15s;
    }

    .btn-skip {
      background: rgba(255,255,255,0.08);
      color: var(--text);
      border: 1px solid rgba(255,255,255,0.12);
    }

    .btn-skip:hover {
      background: rgba(255,255,255,0.12);
    }

    .btn-next {
      background: var(--accent);
      color: white;
    }

    .btn-next:hover {
      background: var(--accent-hover);
    }

    .success-state { display: none; }
    .success-state.visible { display: block; }
    .setup-state.hidden { display: none; }

    .check-icon {
      width: 56px;
      height: 56px;
      margin: 0 auto 16px;
      background: linear-gradient(135deg, #22c55e, #16a34a);
      border-radius: 50%;
      display: flex;
      align-items: center;
      justify-content: center;
      font-size: 28px;
      color: white;
    }

    /* App Menu (Start Menu) */
    #appMenu {
      position: fixed;
      bottom: 60px;
      left: 12px;
      width: 340px;
      max-height: 480px;
      background: var(--window-bg);
      border: 1px solid var(--window-border);
      border-radius: 12px;
      box-shadow: 0 20px 50px rgba(0,0,0,0.55);
      backdrop-filter: blur(24px);
      z-index: 300;
      display: none;
      flex-direction: column;
      overflow: hidden;
    }

    #appMenu.open {
      display: flex;
      animation: menuIn 0.2s ease;
    }

    @keyframes menuIn {
      from { opacity: 0; transform: translateY(12px); }
      to { opacity: 1; transform: translateY(0); }
    }

    .appmenu-header {
      padding: 16px 18px 10px;
      font-size: 13px;
      font-weight: 600;
      color: var(--text-muted);
      text-transform: uppercase;
      letter-spacing: 0.04em;
    }

    .appmenu-grid {
      display: grid;
      grid-template-columns: repeat(3, 1fr);
      gap: 8px;
      padding: 8px 14px 18px;
    }

    .appmenu-item {
      display: flex;
      flex-direction: column;
      align-items: center;
      gap: 6px;
      padding: 12px 8px;
      border-radius: 10px;
      cursor: pointer;
      transition: background 0.15s;
    }

    .appmenu-item:hover {
      background: rgba(255,255,255,0.08);
    }

    .appmenu-item .icon-circle {
      width: 42px;
      height: 42px;
      font-size: 20px;
    }

    .appmenu-item span {
      font-size: 12px;
      color: var(--text);
    }

    /* Calendar / Clock Popup */
    #calendarPopup {
      position: fixed;
      bottom: 60px;
      right: 12px;
      width: 320px;
      background: var(--window-bg);
      border: 1px solid var(--window-border);
      border-radius: 12px;
      box-shadow: 0 20px 50px rgba(0,0,0,0.55);
      backdrop-filter: blur(24px);
      z-index: 300;
      display: none;
      flex-direction: column;
      overflow: hidden;
    }

    #calendarPopup.open {
      display: flex;
      animation: menuIn 0.2s ease;
    }

    .cal-clock {
      padding: 24px 20px 16px;
      text-align: center;
      border-bottom: 1px solid rgba(255,255,255,0.06);
    }

    .cal-clock .big-time {
      font-size: 42px;
      font-weight: 300;
      letter-spacing: 1px;
      color: white;
      font-variant-numeric: tabular-nums;
    }

    .cal-clock .big-date {
      font-size: 14px;
      color: var(--text-muted);
      margin-top: 4px;
    }

    .cal-body {
      padding: 14px 16px 18px;
    }

    .cal-header {
      display: flex;
      justify-content: space-between;
      align-items: center;
      margin-bottom: 12px;
      font-weight: 600;
      font-size: 14px;
    }

    .cal-nav {
      display: flex;
      gap: 4px;
    }

    .cal-nav button {
      background: none;
      border: none;
      color: var(--text-muted);
      font-size: 16px;
      cursor: pointer;
      padding: 4px 8px;
      border-radius: 6px;
    }

    .cal-nav button:hover {
      background: rgba(255,255,255,0.08);
      color: white;
    }

    .cal-grid {
      display: grid;
      grid-template-columns: repeat(7, 1fr);
      gap: 2px;
      text-align: center;
    }

    .cal-day-name {
      font-size: 11px;
      color: var(--text-muted);
      padding: 6px 0;
      font-weight: 500;
    }

    .cal-day {
      font-size: 13px;
      padding: 8px 0;
      border-radius: 8px;
      cursor: default;
      color: var(--text);
    }

    .cal-day.other {
      color: #4b5563;
    }

    .cal-day.today {
      background: var(--accent);
      color: white;
      font-weight: 600;
    }

    /* Taskbar */
    #taskbar {
      position: fixed;
      bottom: 0;
      left: 0;
      right: 0;
      height: 52px;
      background: var(--taskbar-bg);
      backdrop-filter: blur(24px);
      border-top: 1px solid rgba(255,255,255,0.06);
      display: flex;
      align-items: center;
      justify-content: space-between;
      padding: 0 12px;
      z-index: 250;
    }

    .taskbar-left {
      display: flex;
      align-items: center;
      gap: 4px;
    }

    .start-btn {
      width: 42px;
      height: 42px;
      border-radius: 8px;
      background: linear-gradient(135deg, #3b82f6, #1d4ed8);
      display: flex;
      align-items: center;
      justify-content: center;
      font-size: 20px;
      cursor: pointer;
      transition: transform 0.15s, filter 0.15s;
    }

    .start-btn:hover {
      filter: brightness(1.15);
      transform: scale(1.05);
    }

    .start-btn.active {
      outline: 2px solid rgba(59,130,246,0.5);
    }

    .taskbar-apps {
      display: flex;
      gap: 2px;
      margin-left: 8px;
    }

    .taskbar-app {
      width: 42px;
      height: 42px;
      border-radius: 8px;
      display: flex;
      align-items: center;
      justify-content: center;
      font-size: 18px;
      cursor: pointer;
      transition: background 0.15s;
      position: relative;
    }

    .taskbar-app:hover {
      background: rgba(255,255,255,0.1);
    }

    .taskbar-app.open::after {
      content: "";
      position: absolute;
      bottom: 4px;
      left: 50%;
      transform: translateX(-50%);
      width: 16px;
      height: 3px;
      background: var(--accent);
      border-radius: 2px;
    }

    .taskbar-center {
      flex: 1;
      display: flex;
      justify-content: center;
    }

    .search-box {
      background: rgba(255,255,255,0.06);
      border: 1px solid rgba(255,255,255,0.08);
      border-radius: 20px;
      padding: 7px 16px;
      width: 260px;
      max-width: 35vw;
      color: var(--text-muted);
      font-size: 13px;
      display: flex;
      align-items: center;
      gap: 8px;
    }

    .taskbar-right {
      display: flex;
      align-items: center;
      gap: 12px;
      font-size: 13px;
      color: rgba(255,255,255,0.9);
    }

    .time-date {
      text-align: right;
      line-height: 1.25;
      cursor: pointer;
      padding: 6px 10px;
      border-radius: 8px;
      transition: background 0.15s;
    }

    .time-date:hover {
      background: rgba(255,255,255,0.08);
    }

    .time-date.active {
      background: rgba(255,255,255,0.12);
    }

    .time-date .time {
      font-weight: 500;
      font-variant-numeric: tabular-nums;
    }

    .time-date .date {
      font-size: 11px;
      opacity: 0.7;
    }

    /* App specific styles */
    .notepad-area {
      width: 100%;
      height: 100%;
      min-height: 280px;
      background: rgba(0,0,0,0.25);
      border: 1px solid rgba(255,255,255,0.08);
      border-radius: 8px;
      padding: 12px;
      color: var(--text);
      font-family: "Cascadia Code", "Consolas", monospace;
      font-size: 14px;
      resize: none;
      outline: none;
    }

    .browser-bar {
      display: flex;
      gap: 8px;
      margin-bottom: 12px;
    }

    .browser-url {
      flex: 1;
      padding: 8px 12px;
      background: rgba(0,0,0,0.3);
      border: 1px solid rgba(255,255,255,0.1);
      border-radius: 8px;
      color: var(--text);
      font-size: 13px;
      outline: none;
    }

    .browser-content {
      background: rgba(0,0,0,0.2);
      border-radius: 8px;
      padding: 20px;
      min-height: 240px;
      color: var(--text-muted);
      line-height: 1.6;
    }

    .ai-chat {
      display: flex;
      flex-direction: column;
      height: 100%;
      min-height: 300px;
    }

    .ai-messages {
      flex: 1;
      overflow-y: auto;
      padding: 8px 0;
      display: flex;
      flex-direction: column;
      gap: 10px;
    }

    .ai-msg {
      padding: 10px 14px;
      border-radius: 12px;
      max-width: 85%;
      font-size: 13px;
      line-height: 1.45;
    }

    .ai-msg.bot {
      background: rgba(59,130,246,0.15);
      align-self: flex-start;
    }

    .ai-msg.user {
      background: rgba(255,255,255,0.08);
      align-self: flex-end;
    }

    .ai-input-row {
      display: flex;
      gap: 8px;
      margin-top: 12px;
    }

    .ai-input {
      flex: 1;
      padding: 10px 14px;
      background: rgba(0,0,0,0.3);
      border: 1px solid rgba(255,255,255,0.1);
      border-radius: 8px;
      color: var(--text);
      font-size: 13px;
      outline: none;
    }

    .games-grid {
      display: grid;
      grid-template-columns: 1fr 1fr;
      gap: 12px;
    }

    .game-card {
      background: rgba(0,0,0,0.25);
      border: 1px solid rgba(255,255,255,0.08);
      border-radius: 10px;
      padding: 20px;
      text-align: center;
      cursor: pointer;
      transition: background 0.15s, border-color 0.15s;
    }

    .game-card:hover {
      background: rgba(255,255,255,0.06);
      border-color: rgba(255,255,255,0.15);
    }

    .game-card .emoji {
      font-size: 36px;
      margin-bottom: 8px;
    }

    .sound-grid {
      display: grid;
      grid-template-columns: repeat(3, 1fr);
      gap: 10px;
    }

    .sound-btn {
      background: rgba(0,0,0,0.25);
      border: 1px solid rgba(255,255,255,0.08);
      border-radius: 10px;
      padding: 18px 8px;
      text-align: center;
      cursor: pointer;
      transition: all 0.15s;
      font-size: 13px;
    }

    .sound-btn:hover {
      background: rgba(59,130,246,0.2);
      border-color: var(--accent);
    }

    .sound-btn .emoji {
      font-size: 28px;
      display: block;
      margin-bottom: 6px;
    }

    .store-grid {
      display: grid;
      grid-template-columns: 1fr 1fr;
      gap: 12px;
    }

    .store-item {
      background: rgba(0,0,0,0.25);
      border: 1px solid rgba(255,255,255,0.08);
      border-radius: 10px;
      padding: 16px;
      text-align: center;
    }

    .store-item .emoji {
      font-size: 32px;
      margin-bottom: 8px;
    }

    .photos-grid {
      display: grid;
      grid-template-columns: repeat(3, 1fr);
      gap: 8px;
    }

    .photo-item {
      aspect-ratio: 1;
      border-radius: 8px;
      background: linear-gradient(135deg, #1e293b, #0f172a);
      display: flex;
      align-items: center;
      justify-content: center;
      font-size: 28px;
      border: 1px solid rgba(255,255,255,0.06);
    }

    .settings-list {
      display: flex;
      flex-direction: column;
      gap: 8px;
    }

    .settings-item {
      display: flex;
      justify-content: space-between;
      align-items: center;
      padding: 12px 14px;
      background: rgba(0,0,0,0.2);
      border-radius: 8px;
      border: 1px solid rgba(255,255,255,0.06);
    }

    .toggle {
      width: 40px;
      height: 22px;
      background: #374151;
      border-radius: 11px;
      position: relative;
      cursor: pointer;
      transition: background 0.2s;
    }

    .toggle.on {
      background: var(--accent);
    }

    .toggle::after {
      content: "";
      position: absolute;
      width: 16px;
      height: 16px;
      background: white;
      border-radius: 50%;
      top: 3px;
      left: 3px;
      transition: transform 0.2s;
    }

    .toggle.on::after {
      transform: translateX(18px);
    }
  </style>
</head>
<body>
  <div id="desktop">
    <div class="desktop-icon" data-app="browser">
      <div class="icon-circle c1">🌐</div>
      <div class="icon-label">Browser</div>
    </div>
    <div class="desktop-icon" data-app="notepad">
      <div class="icon-circle c2">📝</div>
      <div class="icon-label">Notepad</div>
    </div>
    <div class="desktop-icon" data-app="ai">
      <div class="icon-circle c3">🤖</div>
      <div class="icon-label">AI</div>
    </div>
    <div class="desktop-icon" data-app="games">
      <div class="icon-circle c4">🎮</div>
      <div class="icon-label">Games</div>
    </div>
    <div class="desktop-icon" data-app="soundboard">
      <div class="icon-circle c5">🎵</div>
      <div class="icon-label">Soundboard</div>
    </div>
    <div class="desktop-icon" data-app="store">
      <div class="icon-circle c6">🛒</div>
      <div class="icon-label">Store</div>
    </div>
    <div class="desktop-icon" data-app="photos">
      <div class="icon-circle c7">🖼️</div>
      <div class="icon-label">Photos</div>
    </div>
    <div class="desktop-icon" data-app="settings">
      <div class="icon-circle c8">⚙️</div>
      <div class="icon-label">Settings</div>
    </div>
  </div>

  <!-- Setup Window -->
  <div class="window open active" id="setupWindow">
    <div class="titlebar">
      <div class="titlebar-left">
        <span class="app-icon">🛰️</span>
        <span>xyz.77 Setup</span>
      </div>
      <div class="window-controls">
        <button class="win-btn win-min"></button>
        <button class="win-btn win-max"></button>
        <button class="win-btn win-close" data-close="setupWindow"></button>
      </div>
    </div>
    <div class="window-body">
      <div class="setup-state" id="setupState">
        <div class="logo">🛰️</div>
        <h1>xyz.77</h1>
        <p class="subtitle">Let's set things up.</p>
        <div class="field-label">What should we call you?</div>
        <input type="text" class="input-field" id="nameInput" placeholder="Your name" autocomplete="off">
        <div class="button-row">
          <button class="btn btn-skip" id="skipBtn">Skip</button>
          <button class="btn btn-next" id="nextBtn">Next</button>
        </div>
      </div>
      <div class="success-state" id="successState">
        <div class="check-icon">✓</div>
        <h1 id="welcomeTitle">Welcome!</h1>
        <p class="subtitle">Your desktop is ready.</p>
        <div class="button-row" style="justify-content:center;">
          <button class="btn btn-next" id="closeSetupBtn">Get started</button>
        </div>
      </div>
    </div>
  </div>

  <!-- App Windows -->
  <div class="window" id="win-browser" style="width:560px;height:420px;top:80px;left:180px;">
    <div class="titlebar">
      <div class="titlebar-left"><span class="app-icon">🌐</span><span>Browser</span></div>
      <div class="window-controls">
        <button class="win-btn win-min" data-min="win-browser"></button>
        <button class="win-btn win-max"></button>
        <button class="win-btn win-close" data-close="win-browser"></button>
      </div>
    </div>
    <div class="window-body">
      <div class="browser-bar">
        <input class="browser-url" id="browserUrl" value="https://xyz.77" placeholder="Enter URL...">
        <button class="btn btn-next" style="padding:8px 14px;" id="browserGo">Go</button>
      </div>
      <div class="browser-content" id="browserContent">
        <h2 style="color:#e5e7eb;margin-bottom:8px;">Welcome to xyz.77 Browser</h2>
        <p>This is a simulated browser. Enter a URL and click Go.</p>
        <p style="margin-top:12px;">Try typing something and pressing Go!</p>
      </div>
    </div>
  </div>

  <div class="window" id="win-notepad" style="width:480px;height:380px;top:100px;left:220px;">
    <div class="titlebar">
      <div class="titlebar-left"><span class="app-icon">📝</span><span>Notepad</span></div>
      <div class="window-controls">
        <button class="win-btn win-min" data-min="win-notepad"></button>
        <button class="win-btn win-max"></button>
        <button class="win-btn win-close" data-close="win-notepad"></button>
      </div>
    </div>
    <div class="window-body" style="padding:12px;">
      <textarea class="notepad-area" id="notepadText" placeholder="Start typing..."></textarea>
    </div>
  </div>

  <div class="window" id="win-ai" style="width:420px;height:440px;top:70px;left:260px;">
    <div class="titlebar">
      <div class="titlebar-left"><span class="app-icon">🤖</span><span>AI Assistant</span></div>
      <div class="window-controls">
        <button class="win-btn win-min" data-min="win-ai"></button>
        <button class="win-btn win-max"></button>
        <button class="win-btn win-close" data-close="win-ai"></button>
      </div>
    </div>
    <div class="window-body">
      <div class="ai-chat">
        <div class="ai-messages" id="aiMessages">
          <div class="ai-msg bot">Hi! I'm the xyz.77 AI. Ask me anything.</div>
        </div>
        <div class="ai-input-row">
          <input class="ai-input" id="aiInput" placeholder="Type a message..." autocomplete="off">
          <button class="btn btn-next" style="padding:10px 16px;" id="aiSend">Send</button>
        </div>
      </div>
    </div>
  </div>

  <div class="window" id="win-games" style="width:400px;height:340px;top:90px;left:300px;">
    <div class="titlebar">
      <div class="titlebar-left"><span class="app-icon">🎮</span><span>Games</span></div>
      <div class="window-controls">
        <button class="win-btn win-min" data-min="win-games"></button>
        <button class="win-btn win-max"></button>
        <button class="win-btn win-close" data-close="win-games"></button>
      </div>
    </div>
    <div class="window-body">
      <div class="games-grid">
        <div class="game-card" data-game="snake">
          <div class="emoji">🐍</div>
          <div>Snake</div>
        </div>
        <div class="game-card" data-game="memory">
          <div class="emoji">🃏</div>
          <div>Memory</div>
        </div>
        <div class="game-card" data-game="clicker">
          <div class="emoji">👆</div>
          <div>Clicker</div>
        </div>
        <div class="game-card" data-game="dice">
          <div class="emoji">🎲</div>
          <div>Dice Roll</div>
        </div>
      </div>
      <div id="gameArea" style="margin-top:16px;text-align:center;display:none;"></div>
    </div>
  </div>

  <div class="window" id="win-soundboard" style="width:380px;height:320px;top:110px;left:200px;">
    <div class="titlebar">
      <div class="titlebar-left"><span class="app-icon">🎵</span><span>Soundboard</span></div>
      <div class="window-controls">
        <button class="win-btn win-min" data-min="win-soundboard"></button>
        <button class="win-btn win-max"></button>
        <button class="win-btn win-close" data-close="win-soundboard"></button>
      </div>
    </div>
    <div class="window-body">
      <div class="sound-grid">
        <div class="sound-btn" data-sound="beep"><span class="emoji">🔔</span>Beep</div>
        <div class="sound-btn" data-sound="laser"><span class="emoji">🔫</span>Laser</div>
        <div class="sound-btn" data-sound="coin"><span class="emoji">🪙</span>Coin</div>
        <div class="sound-btn" data-sound="boom"><span class="emoji">💥</span>Boom</div>
        <div class="sound-btn" data-sound="meow"><span class="emoji">🐱</span>Meow</div>
        <div class="sound-btn" data-sound="wow"><span class="emoji">😮</span>Wow</div>
      </div>
    </div>
  </div>

  <div class="window" id="win-store" style="width:420px;height:360px;top:85px;left:240px;">
    <div class="titlebar">
      <div class="titlebar-left"><span class="app-icon">🛒</span><span>Store</span></div>
      <div class="window-controls">
        <button class="win-btn win-min" data-min="win-store"></button>
        <button class="win-btn win-max"></button>
        <button class="win-btn win-close" data-close="win-store"></button>
      </div>
    </div>
    <div class="window-body">
      <div class="store-grid">
        <div class="store-item">
          <div class="emoji">📦</div>
          <div style="font-weight:600;margin-bottom:4px;">Pro Pack</div>
          <div style="color:var(--text-muted);font-size:12px;">Extra features</div>
          <button class="btn btn-next" style="margin-top:10px;padding:6px 14px;font-size:12px;">Get</button>
        </div>
        <div class="store-item">
          <div class="emoji">🎨</div>
          <div style="font-weight:600;margin-bottom:4px;">Themes</div>
          <div style="color:var(--text-muted);font-size:12px;">Dark & more</div>
          <button class="btn btn-next" style="margin-top:10px;padding:6px 14px;font-size:12px;">Get</button>
        </div>
        <div class="store-item">
          <div class="emoji">🧩</div>
          <div style="font-weight:600;margin-bottom:4px;">Widgets</div>
          <div style="color:var(--text-muted);font-size:12px;">Desktop tools</div>
          <button class="btn btn-next" style="margin-top:10px;padding:6px 14px;font-size:12px;">Get</button>
        </div>
        <div class="store-item">
          <div class="emoji">🔒</div>
          <div style="font-weight:600;margin-bottom:4px;">Security</div>
          <div style="color:var(--text-muted);font-size:12px;">Extra protection</div>
          <button class="btn btn-next" style="margin-top:10px;padding:6px 14px;font-size:12px;">Get</button>
        </div>
      </div>
    </div>
  </div>

  <div class="window" id="win-photos" style="width:400px;height:340px;top:95px;left:280px;">
    <div class="titlebar">
      <div class="titlebar-left"><span class="app-icon">🖼️</span><span>Photos</span></div>
      <div class="window-controls">
        <button class="win-btn win-min" data-min="win-photos"></button>
        <button class="win-btn win-max"></button>
        <button class="win-btn win-close" data-close="win-photos"></button>
      </div>
    </div>
    <div class="window-body">
      <div class="photos-grid">
        <div class="photo-item">🌅</div>
        <div class="photo-item">🏔️</div>
        <div class="photo-item">🌊</div>
        <div class="photo-item">🏙️</div>
        <div class="photo-item">🌲</div>
        <div class="photo-item">🌌</div>
      </div>
    </div>
  </div>

  <div class="window" id="win-settings" style="width:380px;height:360px;top:80px;left:320px;">
    <div class="titlebar">
      <div class="titlebar-left"><span class="app-icon">⚙️</span><span>Settings</span></div>
      <div class="window-controls">
        <button class="win-btn win-min" data-min="win-settings"></button>
        <button class="win-btn win-max"></button>
        <button class="win-btn win-close" data-close="win-settings"></button>
      </div>
    </div>
    <div class="window-body">
      <div class="settings-list">
        <div class="settings-item">
          <span>Dark Mode</span>
          <div class="toggle on" data-toggle></div>
        </div>
        <div class="settings-item">
          <span>Notifications</span>
          <div class="toggle on" data-toggle></div>
        </div>
        <div class="settings-item">
          <span>Sounds</span>
          <div class="toggle" data-toggle></div>
        </div>
        <div class="settings-item">
          <span>Auto-Start</span>
          <div class="toggle" data-toggle></div>
        </div>
        <div class="settings-item">
          <span>Animations</span>
          <div class="toggle on" data-toggle></div>
        </div>
      </div>
    </div>
  </div>

  <!-- App Menu -->
  <div id="appMenu">
    <div class="appmenu-header">Apps</div>
    <div class="appmenu-grid">
      <div class="appmenu-item" data-app="browser"><div class="icon-circle c1">🌐</div><span>Browser</span></div>
      <div class="appmenu-item" data-app="notepad"><div class="icon-circle c2">📝</div><span>Notepad</span></div>
      <div class="appmenu-item" data-app="ai"><div class="icon-circle c3">🤖</div><span>AI</span></div>
      <div class="appmenu-item" data-app="games"><div class="icon-circle c4">🎮</div><span>Games</span></div>
      <div class="appmenu-item" data-app="soundboard"><div class="icon-circle c5">🎵</div><span>Soundboard</span></div>
      <div class="appmenu-item" data-app="store"><div class="icon-circle c6">🛒</div><span>Store</span></div>
      <div class="appmenu-item" data-app="photos"><div class="icon-circle c7">🖼️</div><span>Photos</span></div>
      <div class="appmenu-item" data-app="settings"><div class="icon-circle c8">⚙️</div><span>Settings</span></div>
    </div>
  </div>

  <!-- Calendar Popup -->
  <div id="calendarPopup">
    <div class="cal-clock">
      <div class="big-time" id="calTime">12:00:00</div>
      <div class="big-date" id="calDate">Wednesday, October 21, 2026</div>
    </div>
    <div class="cal-body">
      <div class="cal-header">
        <span id="calMonthYear">October 2026</span>
        <div class="cal-nav">
          <button id="calPrev">‹</button>
          <button id="calNext">›</button>
        </div>
      </div>
      <div class="cal-grid" id="calGrid"></div>
    </div>
  </div>

  <!-- Taskbar -->
  <div id="taskbar">
    <div class="taskbar-left">
      <div class="start-btn" id="startBtn" title="Start">🛰️</div>
      <div class="taskbar-apps" id="taskbarApps">
        <!-- dynamically filled -->
      </div>
    </div>
    <div class="taskbar-center">
      <div class="search-box">
        <span>🔍</span>
        <span>Search</span>
      </div>
    </div>
    <div class="taskbar-right">
      <span style="opacity:0.7;font-size:12px;">ENG</span>
      <div class="time-date" id="clockBtn">
        <div class="time" id="clock">--:--</div>
        <div class="date" id="date">--/--/----</div>
      </div>
    </div>
  </div>

  <script>
    // ========== Clock ==========
    function updateClock() {
      const now = new Date();
      const time = now.toLocaleTimeString('en-US', { hour: '2-digit', minute: '2-digit', hour12: true });
      const date = now.toLocaleDateString('en-US', { month: '2-digit', day: '2-digit', year: 'numeric' });
      document.getElementById('clock').textContent = time;
      document.getElementById('date').textContent = date;

      // Calendar big clock
      const bigTime = now.toLocaleTimeString('en-US', { hour: '2-digit', minute: '2-digit', second: '2-digit', hour12: false });
      document.getElementById('calTime').textContent = bigTime;
      document.getElementById('calDate').textContent = now.toLocaleDateString('en-US', { weekday: 'long', year: 'numeric', month: 'long', day: 'numeric' });
    }
    updateClock();
    setInterval(updateClock, 1000);

    // ========== Calendar ==========
    let calYear = new Date().getFullYear();
    let calMonth = new Date().getMonth();

    function renderCalendar() {
      const grid = document.getElementById('calGrid');
      grid.innerHTML = '';
      const dayNames = ['Su','Mo','Tu','We','Th','Fr','Sa'];
      dayNames.forEach(d => {
        const el = document.createElement('div');
        el.className = 'cal-day-name';
        el.textContent = d;
        grid.appendChild(el);
      });

      const first = new Date(calYear, calMonth, 1);
      const last = new Date(calYear, calMonth + 1, 0);
      const startDay = first.getDay();
      const daysInMonth = last.getDate();
      const today = new Date();

      document.getElementById('calMonthYear').textContent = first.toLocaleDateString('en-US', { month: 'long', year: 'numeric' });

      // Previous month days
      const prevLast = new Date(calYear, calMonth, 0).getDate();
      for (let i = startDay - 1; i >= 0; i--) {
        const el = document.createElement('div');
        el.className = 'cal-day other';
        el.textContent = prevLast - i;
        grid.appendChild(el);
      }

      for (let d = 1; d <= daysInMonth; d++) {
        const el = document.createElement('div');
        el.className = 'cal-day';
        if (d === today.getDate() && calMonth === today.getMonth() && calYear === today.getFullYear()) {
          el.classList.add('today');
        }
        el.textContent = d;
        grid.appendChild(el);
      }

      // Next month fill
      const total = startDay + daysInMonth;
      const remaining = total % 7 === 0 ? 0 : 7 - (total % 7);
      for (let i = 1; i <= remaining; i++) {
        const el = document.createElement('div');
        el.className = 'cal-day other';
        el.textContent = i;
        grid.appendChild(el);
      }
    }
    renderCalendar();

    document.getElementById('calPrev').onclick = () => {
      calMonth--;
      if (calMonth < 0) { calMonth = 11; calYear--; }
      renderCalendar();
    };
    document.getElementById('calNext').onclick = () => {
      calMonth++;
      if (calMonth > 11) { calMonth = 0; calYear++; }
      renderCalendar();
    };

    // ========== Window Management ==========
    const openApps = new Set();

    function openApp(appId) {
      const win = document.getElementById('win-' + appId);
      if (!win) return;
      win.classList.add('open', 'active');
      openApps.add(appId);
      updateTaskbar();
      bringToFront(win);
      closeMenus();
    }

    function closeApp(appId) {
      const win = document.getElementById(appId.startsWith('win-') ? appId : 'win-' + appId);
      if (!win) return;
      win.classList.remove('open', 'active');
      const id = appId.replace('win-', '');
      openApps.delete(id);
      updateTaskbar();
    }

    function bringToFront(win) {
      document.querySelectorAll('.window').forEach(w => w.classList.remove('active'));
      win.classList.add('active');
    }

    function updateTaskbar() {
      const container = document.getElementById('taskbarApps');
      container.innerHTML = '';
      const icons = {
        browser: '🌐', notepad: '📝', ai: '🤖', games: '🎮',
        soundboard: '🎵', store: '🛒', photos: '🖼️', settings: '⚙️'
      };
      openApps.forEach(id => {
        const btn = document.createElement('div');
        btn.className = 'taskbar-app open';
        btn.innerHTML = icons[id] || '📦';
        btn.title = id.charAt(0).toUpperCase() + id.slice(1);
        btn.onclick = () => {
          const win = document.getElementById('win-' + id);
          if (win.classList.contains('active')) {
            win.classList.remove('active');
            // minimize visually by hiding? or just toggle
          } else {
            win.classList.add('open', 'active');
            bringToFront(win);
          }
        };
        container.appendChild(btn);
      });
    }

    // Desktop icons & App menu items
    document.querySelectorAll('[data-app]').forEach(el => {
      el.addEventListener('click', () => openApp(el.dataset.app));
    });

    // Close / Min buttons
    document.querySelectorAll('[data-close]').forEach(btn => {
      btn.addEventListener('click', (e) => {
        e.stopPropagation();
        const id = btn.dataset.close;
        if (id === 'setupWindow') {
          document.getElementById('setupWindow').classList.remove('open');
        } else {
          closeApp(id);
        }
      });
    });

    document.querySelectorAll('[data-min]').forEach(btn => {
      btn.addEventListener('click', (e) => {
        e.stopPropagation();
        const win = document.getElementById(btn.dataset.min);
        win.classList.remove('active');
      });
    });

    // Dragging windows
    document.querySelectorAll('.titlebar').forEach(bar => {
      let isDragging = false, startX, startY, startLeft, startTop;
      bar.addEventListener('mousedown', (e) => {
        if (e.target.closest('.window-controls')) return;
        const win = bar.closest('.window');
        isDragging = true;
        bringToFront(win);
        startX = e.clientX;
        startY = e.clientY;
        const rect = win.getBoundingClientRect();
        startLeft = rect.left;
        startTop = rect.top;
        win.style.transform = 'none';
        win.style.left = startLeft + 'px';
        win.style.top = startTop + 'px';
      });
      document.addEventListener('mousemove', (e) => {
        if (!isDragging) return;
        const win = bar.closest('.window');
        win.style.left = (startLeft + e.clientX - startX) + 'px';
        win.style.top = (startTop + e.clientY - startY) + 'px';
      });
      document.addEventListener('mouseup', () => { isDragging = false; });
    });

    // Click window to focus
    document.querySelectorAll('.window').forEach(win => {
      win.addEventListener('mousedown', () => bringToFront(win));
    });

    // ========== Start Menu ==========
    const startBtn = document.getElementById('startBtn');
    const appMenu = document.getElementById('appMenu');
    const calendarPopup = document.getElementById('calendarPopup');
    const clockBtn = document.getElementById('clockBtn');

    function closeMenus() {
      appMenu.classList.remove('open');
      calendarPopup.classList.remove('open');
      startBtn.classList.remove('active');
      clockBtn.classList.remove('active');
    }

    startBtn.addEventListener('click', (e) => {
      e.stopPropagation();
      const isOpen = appMenu.classList.contains('open');
      closeMenus();
      if (!isOpen) {
        appMenu.classList.add('open');
        startBtn.classList.add('active');
      }
    });

    clockBtn.addEventListener('click', (e) => {
      e.stopPropagation();
      const isOpen = calendarPopup.classList.contains('open');
      closeMenus();
      if (!isOpen) {
        calendarPopup.classList.add('open');
        clockBtn.classList.add('active');
      }
    });

    document.addEventListener('click', (e) => {
      if (!appMenu.contains(e.target) && !startBtn.contains(e.target) &&
          !calendarPopup.contains(e.target) && !clockBtn.contains(e.target)) {
        closeMenus();
      }
    });

    // ========== Setup ==========
    const nameInput = document.getElementById('nameInput');
    const nextBtn = document.getElementById('nextBtn');
    const skipBtn = document.getElementById('skipBtn');
    const closeSetupBtn = document.getElementById('closeSetupBtn');
    const setupState = document.getElementById('setupState');
    const successState = document.getElementById('successState');
    const welcomeTitle = document.getElementById('welcomeTitle');

    function finishSetup(name) {
      setupState.classList.add('hidden');
      successState.classList.add('visible');
      welcomeTitle.textContent = name && name.trim() ? `Welcome, ${name.trim()}!` : 'Welcome!';
    }

    nextBtn.onclick = () => finishSetup(nameInput.value);
    skipBtn.onclick = () => finishSetup(null);
    nameInput.addEventListener('keydown', e => { if (e.key === 'Enter') finishSetup(nameInput.value); });
    closeSetupBtn.onclick = () => document.getElementById('setupWindow').classList.remove('open');

    // ========== App Functionality ==========

    // Browser
    document.getElementById('browserGo').onclick = () => {
      const url = document.getElementById('browserUrl').value || 'https://xyz.77';
      document.getElementById('browserContent').innerHTML = `
        <h2 style="color:#e5e7eb;margin-bottom:8px;">${url}</h2>
        <p>Simulated page for <strong>${url}</strong></p>
        <p style="margin-top:12px;color:var(--text-muted);">This is a demo browser. Real navigation is not available in this environment.</p>
      `;
    };

    // AI
    const aiReplies = [
      "Interesting question! In this demo I can only give simple replies.",
      "I'm a simulated AI inside xyz.77. Nice to meet you!",
      "That's a great thought. Keep exploring the desktop!",
      "I don't have real internet access, but I can chat with you.",
      "Try the other apps too – Games, Soundboard, Notepad...",
      "Satellite systems online. How can I help?"
    ];
    document.getElementById('aiSend').onclick = sendAI;
    document.getElementById('aiInput').addEventListener('keydown', e => { if (e.key === 'Enter') sendAI(); });

    function sendAI() {
      const input = document.getElementById('aiInput');
      const msg = input.value.trim();
      if (!msg) return;
      const box = document.getElementById('aiMessages');
      box.innerHTML += `<div class="ai-msg user">${msg}</div>`;
      input.value = '';
      setTimeout(() => {
        const reply = aiReplies[Math.floor(Math.random() * aiReplies.length)];
        box.innerHTML += `<div class="ai-msg bot">${reply}</div>`;
        box.scrollTop = box.scrollHeight;
      }, 400 + Math.random() * 600);
      box.scrollTop = box.scrollHeight;
    }

    // Games
    document.querySelectorAll('[data-game]').forEach(card => {
      card.onclick = () => {
        const area = document.getElementById('gameArea');
        area.style.display = 'block';
        const game = card.dataset.game;
        if (game === 'dice') {
          const roll = Math.floor(Math.random() * 6) + 1;
          area.innerHTML = `<div style="font-size:48px;">🎲</div><div style="font-size:24px;margin-top:8px;">You rolled a <strong>${roll}</strong></div>`;
        } else if (game === 'clicker') {
          let count = 0;
          area.innerHTML = `<button class="btn btn-next" id="clickerBtn" style="font-size:18px;padding:16px 32px;">Click me: 0</button>`;
          document.getElementById('clickerBtn').onclick = function() {
            count++;
            this.textContent = `Click me: ${count}`;
          };
        } else if (game === 'snake') {
          area.innerHTML = `<p style="color:var(--text-muted);">Snake is a demo – imagine a cool snake game here! 🐍</p>`;
        } else {
          area.innerHTML = `<p style="color:var(--text-muted);">Memory game demo – find the pairs! 🃏</p>`;
        }
      };
    });

    // Soundboard (Web Audio beeps)
    const audioCtx = new (window.AudioContext || window.webkitAudioContext)();
    function playTone(freq, duration, type = 'square') {
      const osc = audioCtx.createOscillator();
      const gain = audioCtx.createGain();
      osc.type = type;
      osc.frequency.value = freq;
      gain.gain.setValueAtTime(0.15, audioCtx.currentTime);
      gain.gain.exponentialRampToValueAtTime(0.001, audioCtx.currentTime + duration);
      osc.connect(gain);
      gain.connect(audioCtx.destination);
      osc.start();
      osc.stop(audioCtx.currentTime + duration);
    }

    const sounds = {
      beep: () => playTone(800, 0.15),
      laser: () => { playTone(1200, 0.08); setTimeout(() => playTone(600, 0.12), 60); },
      coin: () => { playTone(988, 0.1); setTimeout(() => playTone(1319, 0.2), 80); },
      boom: () => playTone(80, 0.4, 'sawtooth'),
      meow: () => { playTone(400, 0.1); setTimeout(() => playTone(600, 0.15), 100); setTimeout(() => playTone(350, 0.2), 220); },
      wow: () => { playTone(300, 0.15); setTimeout(() => playTone(500, 0.2), 100); setTimeout(() => playTone(700, 0.25), 250); }
    };

    document.querySelectorAll('[data-sound]').forEach(btn => {
      btn.onclick = () => {
        if (audioCtx.state === 'suspended') audioCtx.resume();
        sounds[btn.dataset.sound]();
      };
    });

    // Settings toggles
    document.querySelectorAll('[data-toggle]').forEach(t => {
      t.onclick = () => t.classList.toggle('on');
    });

    // Store buttons
    document.querySelectorAll('.store-item .btn').forEach(btn => {
      btn.onclick = () => {
        btn.textContent = '✓ Got it';
        btn.style.background = '#16a34a';
        setTimeout(() => {
          btn.textContent = 'Get';
          btn.style.background = '';
        }, 1500);
      };
    });
  </script>
</body>
</html>
