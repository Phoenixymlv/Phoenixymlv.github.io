<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8" />
  <title>Home</title>
  <meta name="viewport" content="width=device-width, initial-scale=1" />

  <style>
    :root {
      --bg: #0f172a;
      --fg: #e2e8f0;
      --accent: #38bdf8;
      --muted: #94a3b8;
    }

    body {
      margin: 0;
      font-family: system-ui, sans-serif;
      background: var(--bg);
      color: var(--fg);
    }

    /* NAVBAR */
    nav {
      display: flex;
      justify-content: space-between;
      align-items: center;
      padding: 1rem 1.5rem;
      background: rgba(15, 23, 42, 0.7);
      backdrop-filter: blur(6px);
      border-bottom: 1px solid rgba(255, 255, 255, 0.05);
      position: sticky;
      top: 0;
    }

    nav .logo {
      font-weight: 600;
      font-size: 1.1rem;
      letter-spacing: 0.03em;
    }

    nav a {
      color: var(--fg);
      text-decoration: none;
      margin-left: 1.2rem;
      font-size: 0.95rem;
      transition: color 0.2s ease;
    }

    nav a:hover {
      color: var(--accent);
    }

    /* MAIN CONTENT */
    .hero {
      height: calc(100vh - 70px);
      display: flex;
      flex-direction: column;
      justify-content: center;
      align-items: center;
      text-align: center;
      padding: 2rem;
    }

    .hero h1 {
      font-size: 2.8rem;
      margin-bottom: 0.5rem;
      letter-spacing: 0.03em;
    }

    .hero p {
      color: var(--muted);
      font-size: 1.1rem;
      max-width: 500px;
      margin-bottom: 2rem;
    }

    .hero a.button {
      display: inline-block;
      padding: 0.75rem 1.6rem;
      background: var(--accent);
      color: #0f172a;
      border-radius: 0.6rem;
      font-weight: 600;
      text-decoration: none;
      font-size: 1rem;
      transition: background 0.2s ease;
    }

    .hero a.button:hover {
      background: #7dd3fc;
    }
  </style>
</head>

<body>

  <!-- NAVBAR -->
  <nav>
    <div class="logo">My Website</div>
    <div>
      <a href="README.md">Home</a>
      <a href="stacks.html">Stacks</a>
      <a href="/about.html">About</a>
      <a href="/contact.html">Contact</a>
    </div>
  </nav>

  <!-- MAIN SECTION -->
  <section class="hero">
    <h1>Welcome</h1>
    <p>A simple, clean home page with dark mode and navigation. Choose a page to explore.</p>
    <a href="/stacks.html" class="button">View Stacks</a>
  </section>

</body>
</html>
