<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8" />
  <title>Under Construction</title>
  <meta name="viewport" content="width=device-width, initial-scale=1" />
  <style>
    :root {
      --bg: #0f172a;
      --fg: #e5e7eb;
      --accent: #38bdf8;
      --accent-soft: rgba(56, 189, 248, 0.15);
      --card: #111827;
      --danger: #f97373;
      --success: #4ade80;
    }
    body.light {
      --bg: #f9fafb;
      --fg: #111827;
      --card: #ffffff;
      --accent-soft: rgba(56, 189, 248, 0.08);
    }

    * {
      box-sizing: border-box;
      margin: 0;
      padding: 0;
      font-family: system-ui, -apple-system, BlinkMacSystemFont, "Segoe UI",
        sans-serif;
    }

    body {
      background: radial-gradient(circle at top, #1e293b 0, var(--bg) 55%);
      color: var(--fg);
      min-height: 100vh;
      display: flex;
      align-items: center;
      justify-content: center;
      padding: 1.5rem;
      transition: background 0.4s ease, color 0.3s ease;
    }

    .shell {
      width: 100%;
      max-width: 960px;
      background: linear-gradient(135deg, var(--card), #020617);
      border-radius: 1.5rem;
      padding: 1.75rem;
      border: 1px solid rgba(148, 163, 184, 0.35);
      box-shadow:
        0 24px 60px rgba(15, 23, 42, 0.9),
        0 0 0 1px rgba(148, 163, 184, 0.25);
      display: grid;
      grid-template-columns: minmax(0, 1.1fr) minmax(0, 1.1fr);
      gap: 1.75rem;
    }

    @media (max-width: 800px) {
      .shell {
        grid-template-columns: minmax(0, 1fr);
      }
    }

    .badge {
      display: inline-flex;
      align-items: center;
      gap: 0.4rem;
      padding: 0.25rem 0.7rem;
      border-radius: 999px;
      background: rgba(15, 23, 42, 0.8);
      border: 1px solid rgba(148, 163, 184, 0.5);
      font-size: 0.7rem;
      letter-spacing: 0.08em;
      text-transform: uppercase;
      color: #e5e7eb;
    }

    .badge-dot {
      width: 8px;
      height: 8px;
      border-radius: 999px;
      background: #facc15;
      box-shadow: 0 0 0 6px rgba(250, 204, 21, 0.25);
      animation: pulse 1.4s infinite;
    }

    @keyframes pulse {
      0% {
        transform: scale(1);
        opacity: 1;
      }
      70% {
        transform: scale(1.6);
        opacity: 0;
      }
      100% {
        transform: scale(1.6);
        opacity: 0;
      }
    }

    .title {
      margin-top: 1rem;
      font-size: clamp(2.1rem, 3vw, 2.6rem);
      font-weight: 700;
      letter-spacing: -0.04em;
      display: flex;
      align-items: center;
      gap: 0.6rem;
    }

    .title span.highlight {
      background: linear-gradient(120deg, #38bdf8, #a855f7, #f97316);
      -webkit-background-clip: text;
      color: transparent;
    }

    .subtitle {
      margin-top: 0.75rem;
      font-size: 0.95rem;
      color: #9ca3af;
      max-width: 30rem;
      line-height: 1.5;
    }

    .toggles {
      margin-top: 1.5rem;
      display: flex;
      flex-wrap: wrap;
      gap: 0.75rem;
    }

    .toggle {
      display: inline-flex;
      align-items: center;
      gap: 0.5rem;
      padding: 0.5rem 0.8rem;
      border-radius: 999px;
      background: rgba(15, 23, 42, 0.9);
      border: 1px solid rgba(148, 163, 184, 0.5);
      font-size: 0.8rem;
      cursor: pointer;
      user-select: none;
      transition: background 0.2s ease, border-color 0.2s ease,
        transform 0.1s ease;
    }

    .toggle:hover {
      transform: translateY(-1px);
      border-color: var(--accent);
    }

    .toggle-switch {
      width: 32px;
      height: 18px;
      border-radius: 999px;
      background: #020617;
      border: 1px solid rgba(148, 163, 184, 0.7);
      position: relative;
      transition: background 0.2s ease, border-color 0.2s ease;
    }

    .toggle-knob {
      position: absolute;
      top: 1px;
      left: 1px;
      width: 14px;
      height: 14px;
      border-radius: 999px;
      background: #e5e7eb;
      transition: transform 0.2s ease, background 0.2s ease;
    }

    .toggle.active .toggle-switch {
      background: var(--accent-soft);
      border-color: var(--accent);
    }

    .toggle.active .toggle-knob {
      transform: translateX(12px);
      background: var(--accent);
    }

    .status {
      margin-top: 1.25rem;
      padding: 0.75rem 0.9rem;
      border-radius: 0.9rem;
      background: rgba(15, 23, 42, 0.85);
      border: 1px dashed rgba(148, 163, 184, 0.7);
      font-size: 0.8rem;
      color: #9ca3af;
      display: flex;
      align-items: center;
      justify-content: space-between;
      gap: 0.75rem;
    }

    .status span strong {
      color: #e5e7eb;
    }

    .status-pill {
      padding: 0.25rem 0.6rem;
      border-radius: 999px;
      background: rgba(34, 197, 94, 0.1);
      color: #4ade80;
      font-size: 0.7rem;
      text-transform: uppercase;
      letter-spacing: 0.08em;
    }

    .theme-toggle {
      margin-top: 1.25rem;
      display: inline-flex;
      align-items: center;
      gap: 0.4rem;
      padding: 0.4rem 0.7rem;
      border-radius: 999px;
      border: 1px solid rgba(148, 163, 184, 0.6);
      background: rgba(15, 23, 42, 0.9);
      font-size: 0.75rem;
      cursor: pointer;
      user-select: none;
    }

    .theme-toggle span.icon {
      font-size: 0.9rem;
    }

    /* Wordle card */
    .wordle-card {
      background: radial-gradient(circle at top left, #1f2937 0, var(--card) 55%);
      border-radius: 1.25rem;
      padding: 1.25rem 1.4rem 1.4rem;
      border: 1px solid rgba(148, 163, 184, 0.5);
      display: flex;
      flex-direction: column;
      gap: 0.9rem;
      position: relative;
      overflow: hidden;
    }

    .wordle-card::before {
      content: "";
      position: absolute;
      inset: -40%;
      background: radial-gradient(
        circle at top,
        rgba(56, 189, 248, 0.12),
        transparent 55%
      );
      opacity: 0.7;
      pointer-events: none;
    }

    .wordle-header {
      display: flex;
      align-items: center;
      justify-content: space-between;
      gap: 0.5rem;
      position: relative;
      z-index: 1;
    }

    .wordle-title {
      font-size: 0.95rem;
      font-weight: 600;
      letter-spacing: 0.08em;
      text-transform: uppercase;
      color: #e5e7eb;
      display: flex;
      align-items: center;
      gap: 0.4rem;
    }

    .wordle-title span.mini {
      font-size: 0.7rem;
      padding: 0.1rem 0.4rem;
      border-radius: 999px;
      background: rgba(15, 23, 42, 0.9);
      border: 1px solid rgba(148, 163, 184, 0.6);
      color: #9ca3af;
    }

    .wordle-tries {
      font-size: 0.75rem;
      color: #9ca3af;
    }

    .grid {
      display: grid;
      grid-template-rows: repeat(6, 1fr);
      gap: 0.25rem;
      position: relative;
      z-index: 1;
    }

    .row {
      display: grid;
      grid-template-columns: repeat(5, 1fr);
      gap: 0.25rem;
    }

    .cell {
      width: 100%;
      aspect-ratio: 1 / 1;
      border-radius: 0.35rem;
      border: 1px solid rgba(148, 163, 184, 0.5);
      display: flex;
      align-items: center;
      justify-content: center;
      font-weight: 600;
      font-size: 1rem;
      text-transform: uppercase;
      color: #e5e7eb;
      background: rgba(15, 23, 42, 0.9);
      transition: background 0.2s ease, border-color 0.2s ease,
        transform 0.1s ease;
    }

    .cell.filled {
      border-color: var(--accent);
    }

    .cell.correct {
      background: #16a34a;
      border-color: #16a34a;
    }

    .cell.present {
      background: #ca8a04;
      border-color: #ca8a04;
    }

    .cell.absent {
      background: #020617;
      border-color: #020617;
      color: #6b7280;
    }

    .cell.pop {
      animation: pop 0.12s ease-out;
    }

    @keyframes pop {
      0% {
        transform: scale(0.9);
      }
      100% {
        transform: scale(1);
      }
    }

    .input-row {
      display: flex;
      gap: 0.5rem;
      margin-top: 0.4rem;
      position: relative;
      z-index: 1;
    }

    .input-row input {
      flex: 1;
      padding: 0.45rem 0.6rem;
      border-radius: 0.6rem;
      border: 1px solid rgba(148, 163, 184, 0.7);
      background: rgba(15, 23, 42, 0.95);
      color: #e5e7eb;
      font-size: 0.9rem;
      text-transform: uppercase;
      letter-spacing: 0.18em;
      outline: none;
    }

    .input-row input:focus {
      border-color: var(--accent);
      box-shadow: 0 0 0 1px rgba(56, 189, 248, 0.4);
    }

    .input-row button {
      padding: 0.45rem 0.8rem;
      border-radius: 0.6rem;
      border: none;
      background: var(--accent);
      color: #0b1120;
      font-size: 0.8rem;
      font-weight: 600;
      cursor: pointer;
      display: inline-flex;
      align-items: center;
      gap: 0.25rem;
      text-transform: uppercase;
      letter-spacing: 0.08em;
      transition: background 0.2s ease, transform 0.1s ease,
        box-shadow 0.2s ease;
      box-shadow: 0 8px 18px rgba(56, 189, 248, 0.35);
    }

    .input-row button:hover {
      background: #0ea5e9;
      transform: translateY(-1px);
    }

    .input-row button:active {
      transform: translateY(0);
      box-shadow: 0 4px 10px rgba(56, 189, 248, 0.3);
    }

    .wordle-message {
      font-size: 0.8rem;
      margin-top: 0.25rem;
      min-height: 1.1rem;
      color: #9ca3af;
      position: relative;
      z-index: 1;
    }

    .wordle-message.error {
      color: var(--danger);
    }

    .wordle-message.success {
      color: var(--success);
    }

    .mail-hint {
      margin-top: 0.25rem;
      font-size: 0.7rem;
      color: #6b7280;
    }

    .mail-hint strong {
      color: #e5e7eb;
    }

    .mail-link {
      margin-top: 0.4rem;
      font-size: 0.8rem;
      color: var(--accent);
      text-decoration: underline;
      cursor: pointer;
      display: none;
    }

    .mail-link.visible {
      display: inline-block;
    }
  </style>
</head>
<body>
  <div class="shell">
    <!-- LEFT: Under construction + toggles -->
    <section>
      <div class="badge">
        <span class="badge-dot"></span>
        <span>Under Construction</span>
      </div>

      <h1 class="title">
        This page is
        <span class="highlight">still in the workshop</span>
      </h1>

      <p class="subtitle">
        You’ve reached a preview build. Flip a few switches, play a tiny Wordle,
        and send yourself a “I was here” email when you crack it.
      </p>

      <div class="toggles">
        <div class="toggle" data-toggle="animations">
          <div class="toggle-switch">
            <div class="toggle-knob"></div>
          </div>
          <span>Subtle animations</span>
        </div>
        <div class="toggle" data-toggle="noise">
          <div class="toggle-switch">
            <div class="toggle-knob"></div>
          </div>
          <span>Background glow</span>
        </div>
        <div class="toggle" data-toggle="focus">
          <div class="toggle-switch">
            <div class="toggle-knob"></div>
          </div>
          <span>Focus mode</span>
        </div>
      </div>

      <div class="status">
        <span>
          <strong>Status:</strong>
          <span id="status-text">Scaffolding UI, wiring tiny puzzles…</span>
        </span>
        <span class="status-pill" id="status-pill">Preview</span>
      </div>

      <button class="theme-toggle" id="theme-toggle">
        <span class="icon" id="theme-icon">🌙</span>
        <span id="theme-label">Dark mode</span>
      </button>
    </section>

    <!-- RIGHT: Mini Wordle -->
    <section class="wordle-card">
      <div class="wordle-header">
        <div class="wordle-title">
          Mini Wordle
          <span class="mini">5 letters · 6 tries</span>
        </div>
        <div class="wordle-tries">
          Tries left: <span id="tries-left">6</span>
        </div>
      </div>

      <div class="grid" id="grid"></div>

      <div class="input-row">
        <input
          id="guess-input"
          maxlength="5"
          autocomplete="off"
          placeholder="TYPE"
        />
        <button id="guess-btn">
          <span>Guess</span>
        </button>
      </div>

      <div class="wordle-message" id="wordle-message"></div>
      <div class="mail-hint">
        Crack the word and we’ll open a pre-filled email so you can brag about
        it.
      </div>
      <span class="mail-link" id="mail-link">Open the “I solved it” email again</span>
    </section>
  </div>

  <script>
    // --- Toggles / status ---
    const toggles = document.querySelectorAll(".toggle");
    const statusText = document.getElementById("status-text");
    const statusPoll = document.getElementById("status-pill");

    toggles.forEach((t) => {
      t.addEventListener("click", () => {
        t.classList.toggle("active");
        updateStatus();
      });
    });

    function updateStatus() {
      const activeCount = document.querySelectorAll(".toggle.active").length;
      if (activeCount === 0) {
        statusText.textContent = "Scaffolding UI, wiring tiny puzzles…";
        statusPoll.textContent = "Preview";
      } else if (activeCount <= 2) {
        statusText.textContent = "Tuning the experience to your taste.";
        statusPoll.textContent = "Customizing";
      } else {
        statusText.textContent = "You’ve unlocked the full preview vibe.";
        statusPoll.textContent = "Dialed in";
      }
    }

    // --- Theme toggle ---
    const themeToggle = document.getElementById("theme-toggle");
    const themeIcon = document.getElementById("theme-icon");
    const themeLabel = document.getElementById("theme-label");

    themeToggle.addEventListener("click", () => {
      document.body.classList.toggle("light");
      const isLight = document.body.classList.contains("light");
      themeIcon.textContent = isLight ? "☀️" : "🌙";
      themeLabel.textContent = isLight ? "Light mode" : "Dark mode";
    });

    // --- Mini Wordle ---
    const ANSWER = "BUILD"; // 5-letter word
    const MAX_TRIES = 6;

    const gridEl = document.getElementById("grid");
    const guessInput = document.getElementById("guess-input");
    const guessBtn = document.getElementById("guess-btn");
    const triesLeftEl = document.getElementById("tries-left");
    const msgEl = document.getElementById("wordle-message");
    const mailLink = document.getElementById("mail-link");

    let currentRow = 0;
    let gameOver = false;

    // Build empty grid
    const rows = [];
    for (let r = 0; r < MAX_TRIES; r++) {
      const row = document.createElement("div");
      row.className = "row";
      const cells = [];
      for (let c = 0; c < 5; c++) {
        const cell = document.createElement("div");
        cell.className = "cell";
        row.appendChild(cell);
        cells.push(cell);
      }
      gridEl.appendChild(row);
      rows.push(cells);
    }

    function showMessage(text, type = "") {
      msgEl.textContent = text;
      msgEl.className = "wordle-message";
      if (type) msgEl.classList.add(type);
    }

    function openWinMail(guess) {
      const subject = encodeURIComponent("I solved your Under Construction Wordle");
      const body = encodeURIComponent(
        `Hey,\n\nI just solved the mini Wordle on your “Under Construction” page.\n\nWord: ${guess}\nTries used: ${
          currentRow + 1
        } / ${MAX_TRIES}\n\nYou can safely ship this thing now. 🚀`
      );
      const mailto = `mailto:?subject=${subject}&body=${body}`;
      window.location.href = mailto;
    }

    function handleGuess() {
      if (gameOver) return;

      let guess = guessInput.value.trim().toUpperCase();
      if (guess.length !== 5) {
        showMessage("Please enter a 5-letter word.", "error");
        return;
      }

      // Simple letters-only check
      if (!/^[A-Z]{5}$/.test(guess)) {
        showMessage("Letters only, no spaces or symbols.", "error");
        return;
      }

      const rowCells = rows[currentRow];
      const answerArr = ANSWER.split("");
      const guessArr = guess.split("");

      // First pass: mark correct
      const result = Array(5).fill("absent");
      const used = Array(5).fill(false);

      for (let i = 0; i < 5; i++) {
        rowCells[i].textContent = guessArr[i];
        rowCells[i].classList.add("filled", "pop");
        if (guessArr[i] === answerArr[i]) {
          result[i] = "correct";
          used[i] = true;
        }
      }

      // Second pass: mark present
      for (let i = 0; i < 5; i++) {
        if (result[i] === "correct") continue;
        const letter = guessArr[i];
        const idx = answerArr.findIndex((ch, j) => ch === letter && !used[j]);
        if (idx !== -1) {
          result[i] = "present";
          used[idx] = true;
        }
      }

      // Apply classes
      for (let i = 0; i < 5; i++) {
        rowCells[i].classList.remove("correct", "present", "absent");
        rowCells[i].classList.add(result[i]);
      }

      if (guess === ANSWER) {
        gameOver = true;
        showMessage("Nice! You nailed it. Opening your victory email…", "success");
        triesLeftEl.textContent = MAX_TRIES - currentRow - 1;
        mailLink.classList.add("visible");
        openWinMail(guess);
        return;
      }

      currentRow++;
      triesLeftEl.textContent = MAX_TRIES - currentRow;

      if (currentRow >= MAX_TRIES) {
        gameOver = true;
        showMessage(`Out of tries. The word was ${ANSWER}.`, "error");
        return;
      }

      showMessage("Good try—keep going.");
      guessInput.value = "";
      guessInput.focus();
    }

    guessBtn.addEventListener("click", handleGuess);
    guessInput.addEventListener("keydown", (e) => {
      if (e.key === "Enter") {
        handleGuess();
      }
    });

    mailLink.addEventListener("click", () => {
      if (!gameOver) return;
      openWinMail(ANSWER);
    });

    // Autofocus on load
    window.addEventListener("load", () => {
      guessInput.focus();
    });
  </script>
</body>
</html>
