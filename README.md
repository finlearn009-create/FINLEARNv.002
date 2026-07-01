# FINLEARNv.002
<!DOCTYPE html>
<html lang="en">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>FINLEARN</title>
<link rel="stylesheet" href="https://cdn.jsdelivr.net/npm/@tabler/icons-webfont@latest/tabler-icons.min.css">
<style>
  * { box-sizing: border-box; margin: 0; padding: 0; }
  :root {
    --lime: #84cc16;
    --lime-light: #d9f99d;
    --lime-pale: #f7fee7;
    --lime-dark: #3f6212;
    --forest: #166534;
    --forest-dark: #052e16;
    --white: #ffffff;
    --gray-50: #f9fafb;
    --gray-100: #f3f4f6;
    --gray-200: #e5e7eb;
    --gray-400: #9ca3af;
    --gray-600: #4b5563;
    --gray-900: #111827;
    --font: 'Inter', system-ui, sans-serif;
  }
  @import url('https://fonts.googleapis.com/css2?family=Inter:wght@300;400;500;600;700&family=Sora:wght@600;700;800&display=swap');

  body { font-family: var(--font); background: var(--white); color: var(--gray-900); }

  .fl-app { max-width: 720px; margin: 0 auto; min-height: 100vh; }

  /* ── SCREENS ── */
  .screen { display: none; animation: fadeIn 0.3s ease; }
  .screen.active { display: block; }
  @keyframes fadeIn { from { opacity: 0; transform: translateY(8px); } to { opacity: 1; transform: none; } }

  /* ── TOP NAV ── */
  .topnav {
    display: flex; align-items: center; justify-content: space-between;
    padding: 14px 20px; border-bottom: 1px solid var(--gray-200);
    background: var(--white); position: sticky; top: 0; z-index: 10;
  }
  .logo { display: flex; align-items: center; gap: 8px; cursor: pointer; }
  .logo-mark {
    width: 32px; height: 32px; border-radius: 8px;
    background: var(--lime-dark); display: flex; align-items: center; justify-content: center;
  }
  .logo-mark span { font-size: 16px; font-weight: 800; color: var(--lime); font-family: 'Sora', sans-serif; }
  .logo-text { font-family: 'Sora', sans-serif; font-weight: 700; font-size: 17px; color: var(--gray-900); letter-spacing: -0.3px; }
  .logo-text em { color: var(--lime-dark); font-style: normal; }
  .nav-badge {
    background: var(--lime-pale); color: var(--forest);
    font-size: 11px; font-weight: 600; padding: 3px 9px; border-radius: 20px;
    border: 1px solid var(--lime-light);
  }

  /* ── HERO ── */
  .hero {
    background: linear-gradient(135deg, var(--forest-dark) 0%, var(--forest) 60%, var(--lime-dark) 100%);
    padding: 48px 24px 40px; text-align: center; color: var(--white);
  }
  .hero-eyebrow {
    display: inline-flex; align-items: center; gap: 6px;
    background: rgba(132,204,22,0.18); border: 1px solid rgba(132,204,22,0.35);
    border-radius: 20px; padding: 5px 14px; font-size: 12px; font-weight: 500;
    color: var(--lime-light); margin-bottom: 20px; letter-spacing: 0.3px;
  }
  .hero-title { font-family: 'Sora', sans-serif; font-size: 34px; font-weight: 800; line-height: 1.15; margin-bottom: 14px; letter-spacing: -0.5px; }
  .hero-title span { color: var(--lime); }
  .hero-sub { font-size: 15px; color: rgba(255,255,255,0.72); max-width: 440px; margin: 0 auto 28px; line-height: 1.6; }
  .hero-stats { display: flex; gap: 0; border: 1px solid rgba(255,255,255,0.12); border-radius: 12px; overflow: hidden; max-width: 360px; margin: 0 auto; background: rgba(255,255,255,0.06); }
  .stat-item { flex: 1; padding: 12px 8px; text-align: center; border-right: 1px solid rgba(255,255,255,0.10); }
  .stat-item:last-child { border-right: none; }
  .stat-num { font-family: 'Sora', sans-serif; font-size: 20px; font-weight: 700; color: var(--lime); }
  .stat-lbl { font-size: 10px; color: rgba(255,255,255,0.55); margin-top: 2px; }

  /* ── SECTION LABEL ── */
  .section-label { padding: 20px 20px 8px; font-size: 11px; font-weight: 600; color: var(--gray-400); letter-spacing: 1px; text-transform: uppercase; }

  /* ── MAIN MENU GRID ── */
  .menu-grid { display: grid; grid-template-columns: 1fr 1fr; gap: 12px; padding: 0 16px 16px; }
  .menu-card {
    border-radius: 14px; padding: 18px 16px; cursor: pointer;
    border: 1.5px solid transparent; transition: all 0.18s ease;
    position: relative; overflow: hidden;
  }
  .menu-card:hover { transform: translateY(-2px); border-color: var(--lime); }
  .menu-card.green { background: var(--forest-dark); color: var(--white); }
  .menu-card.lime { background: var(--lime-pale); border-color: var(--lime-light); }
  .menu-card.white { background: var(--white); border: 1.5px solid var(--gray-200); }
  .menu-card.accent { background: var(--lime-dark); color: var(--white); }
  .card-icon { font-size: 26px; margin-bottom: 10px; }
  .card-title { font-family: 'Sora', sans-serif; font-weight: 700; font-size: 14px; line-height: 1.3; margin-bottom: 4px; }
  .menu-card.green .card-title, .menu-card.accent .card-title { color: var(--white); }
  .menu-card.lime .card-title { color: var(--forest-dark); }
  .menu-card.white .card-title { color: var(--gray-900); }
  .card-desc { font-size: 11px; line-height: 1.4; }
  .menu-card.green .card-desc { color: rgba(255,255,255,0.6); }
  .menu-card.accent .card-desc { color: rgba(255,255,255,0.65); }
  .menu-card.lime .card-desc { color: var(--forest); }
  .menu-card.white .card-desc { color: var(--gray-600); }
  .card-arrow { position: absolute; top: 14px; right: 14px; font-size: 14px; opacity: 0.4; }

  /* ── FULL-WIDTH FEATURED CARD ── */
  .featured-card {
    margin: 0 16px 12px; border-radius: 14px; padding: 18px 20px;
    background: var(--lime); cursor: pointer;
    display: flex; align-items: center; gap: 16px;
    transition: all 0.18s ease;
  }
  .featured-card:hover { transform: translateY(-2px); }
  .featured-icon { font-size: 32px; }
  .featured-title { font-family: 'Sora', sans-serif; font-weight: 700; font-size: 16px; color: var(--forest-dark); }
  .featured-sub { font-size: 12px; color: var(--forest); margin-top: 2px; }

  /* ── CONTENT SCREEN ── */
  .content-header { padding: 20px 20px 16px; border-bottom: 1px solid var(--gray-100); }
  .back-btn {
    display: inline-flex; align-items: center; gap: 6px;
    font-size: 13px; color: var(--gray-600); cursor: pointer; margin-bottom: 12px;
    background: none; border: none; padding: 0; transition: color 0.15s;
  }
  .back-btn:hover { color: var(--forest); }
  .content-title { font-family: 'Sora', sans-serif; font-size: 22px; font-weight: 700; color: var(--forest-dark); margin-bottom: 4px; }
  .content-sub { font-size: 13px; color: var(--gray-600); }

  /* ── TOPIC LIST ── */
  .topic-list { padding: 8px 16px 20px; }
  .topic-item {
    display: flex; align-items: center; gap: 12px;
    padding: 14px 16px; border-radius: 10px; cursor: pointer;
    border: 1px solid var(--gray-100); margin-bottom: 8px;
    background: var(--white); transition: all 0.15s;
  }
  .topic-item:hover { border-color: var(--lime); background: var(--lime-pale); }
  .topic-icon { width: 38px; height: 38px; border-radius: 9px; background: var(--lime-pale); display: flex; align-items: center; justify-content: center; font-size: 18px; flex-shrink: 0; }
  .topic-name { font-size: 14px; font-weight: 500; color: var(--gray-900); }
  .topic-count { font-size: 11px; color: var(--gray-400); margin-top: 2px; }
  .topic-chevron { margin-left: auto; color: var(--gray-400); font-size: 14px; }

  /* ── ARTICLE READER ── */
  .article-header {
    background: var(--forest-dark); padding: 24px 20px 20px; color: var(--white);
  }
  .article-tag {
    display: inline-block; background: rgba(132,204,22,0.2); color: var(--lime-light);
    font-size: 10px; font-weight: 600; padding: 3px 10px; border-radius: 20px;
    letter-spacing: 0.5px; margin-bottom: 10px;
  }
  .article-title { font-family: 'Sora', sans-serif; font-size: 20px; font-weight: 700; line-height: 1.3; margin-bottom: 8px; }
  .article-meta { font-size: 12px; color: rgba(255,255,255,0.5); }

  .article-body { padding: 20px; }
  .article-section { margin-bottom: 20px; }
  .article-section h3 { font-size: 15px; font-weight: 600; color: var(--forest-dark); margin-bottom: 8px; padding-left: 10px; border-left: 3px solid var(--lime); }
  .article-section p { font-size: 14px; line-height: 1.7; color: var(--gray-600); margin-bottom: 8px; }
  .article-section ul { padding-left: 18px; }
  .article-section ul li { font-size: 14px; color: var(--gray-600); line-height: 1.7; margin-bottom: 4px; }

  .key-box { background: var(--lime-pale); border: 1px solid var(--lime-light); border-radius: 10px; padding: 14px 16px; margin: 16px 0; }
  .key-box-title { font-size: 12px; font-weight: 600; color: var(--forest); margin-bottom: 6px; letter-spacing: 0.3px; }
  .key-box p { font-size: 13px; color: var(--forest-dark); line-height: 1.6; margin: 0; }

  .source-strip { margin: 0 16px; padding: 12px 16px; background: var(--gray-50); border-radius: 10px; margin-bottom: 16px; }
  .source-strip-label { font-size: 10px; color: var(--gray-400); margin-bottom: 6px; font-weight: 600; letter-spacing: 0.5px; }
  .source-item { font-size: 12px; color: var(--forest); display: flex; align-items: center; gap: 6px; margin-bottom: 3px; }

  /* ── SEARCH BAR ── */
  .search-wrap { padding: 12px 16px; }
  .search-input {
    width: 100%; padding: 10px 14px 10px 36px; border-radius: 10px;
    border: 1.5px solid var(--gray-200); font-size: 14px;
    background: var(--gray-50) url("data:image/svg+xml,%3Csvg xmlns='http://www.w3.org/2000/svg' width='16' height='16' fill='none' stroke='%239ca3af' stroke-width='2' stroke-linecap='round' stroke-linejoin='round' viewBox='0 0 24 24'%3E%3Ccircle cx='11' cy='11' r='8'/%3E%3Cpath d='m21 21-4.35-4.35'/%3E%3C/svg%3E") no-repeat 12px center;
    outline: none; color: var(--gray-900);
  }
  .search-input:focus { border-color: var(--lime); background-color: var(--white); }

  /* ── QUIZ ── */
  .quiz-wrap { padding: 16px; }
  .quiz-card { background: var(--white); border: 1.5px solid var(--gray-200); border-radius: 14px; padding: 20px; }
  .quiz-q { font-size: 15px; font-weight: 500; color: var(--gray-900); margin-bottom: 16px; line-height: 1.5; }
  .quiz-opt {
    display: block; width: 100%; text-align: left; padding: 11px 14px;
    border: 1.5px solid var(--gray-200); border-radius: 9px; margin-bottom: 8px;
    font-size: 13px; cursor: pointer; background: var(--white); color: var(--gray-700);
    transition: all 0.15s;
  }
  .quiz-opt:hover { border-color: var(--lime); background: var(--lime-pale); color: var(--forest-dark); }
  .quiz-opt.correct { border-color: var(--lime-dark); background: var(--lime-pale); color: var(--forest-dark); font-weight: 500; }
  .quiz-opt.wrong { border-color: #dc2626; background: #fef2f2; color: #991b1b; }
  .quiz-result { background: var(--lime-pale); border: 1px solid var(--lime-light); border-radius: 10px; padding: 14px; margin-top: 14px; font-size: 13px; color: var(--forest-dark); line-height: 1.6; }

  /* ── BOTTOM NAV ── */
  .bottom-nav {
    display: flex; border-top: 1px solid var(--gray-100); background: var(--white);
    padding: 8px 0 4px; position: sticky; bottom: 0;
  }
  .bnav-item { flex: 1; display: flex; flex-direction: column; align-items: center; gap: 3px; cursor: pointer; padding: 6px 0; transition: all 0.15s; }
  .bnav-icon { font-size: 20px; color: var(--gray-400); }
  .bnav-label { font-size: 10px; color: var(--gray-400); font-weight: 500; }
  .bnav-item.active .bnav-icon, .bnav-item.active .bnav-label { color: var(--forest); }
  .bnav-item.active .bnav-icon { color: var(--lime-dark); }

  /* ── GLOSSARY CHIP ── */
  .glossary-chips { display: flex; flex-wrap: wrap; gap: 8px; padding: 12px 16px; }
  .g-chip {
    padding: 6px 12px; border-radius: 20px; border: 1px solid var(--gray-200);
    font-size: 12px; cursor: pointer; background: var(--white); color: var(--gray-700);
    transition: all 0.15s;
  }
  .g-chip:hover, .g-chip.active { background: var(--lime-pale); border-color: var(--lime); color: var(--forest-dark); }
  .gloss-entry { padding: 0 16px 12px; }
  .gloss-term { font-size: 16px; font-weight: 600; color: var(--forest-dark); margin-bottom: 4px; }
  .gloss-def { font-size: 13px; color: var(--gray-600); line-height: 1.6; }

  /* ── CALCULATOR ── */
  .calc-wrap { padding: 16px; }
  .calc-card { background: var(--white); border: 1.5px solid var(--gray-200); border-radius: 14px; padding: 20px; }
  .calc-label { font-size: 12px; color: var(--gray-600); margin-bottom: 4px; font-weight: 500; }
  .calc-input { width: 100%; padding: 9px 12px; border: 1.5px solid var(--gray-200); border-radius: 8px; font-size: 14px; margin-bottom: 14px; outline: none; color: var(--gray-900); }
  .calc-input:focus { border-color: var(--lime); }
  .calc-btn { width: 100%; padding: 12px; background: var(--forest-dark); color: var(--lime); border: none; border-radius: 10px; font-size: 14px; font-weight: 600; cursor: pointer; transition: background 0.15s; margin-bottom: 14px; }
  .calc-btn:hover { background: var(--forest); }
  .calc-result { background: var(--lime-pale); border: 1px solid var(--lime-light); border-radius: 10px; padding: 14px; text-align: center; }
  .calc-result-num { font-family: 'Sora', sans-serif; font-size: 28px; font-weight: 700; color: var(--forest-dark); }
  .calc-result-lbl { font-size: 12px; color: var(--forest); margin-top: 2px; }

  /* ── SEARCH RESULTS ── */
  .result-card { margin: 0 16px 10px; padding: 14px 16px; border: 1px solid var(--gray-200); border-radius: 12px; background: var(--white); cursor: pointer; transition: all 0.15s; }
  .result-card:hover { border-color: var(--lime); background: var(--lime-pale); }
  .result-title { font-size: 14px; font-weight: 500; color: var(--forest-dark); margin-bottom: 3px; }
  .result-snippet { font-size: 12px; color: var(--gray-600); line-height: 1.5; }
  .result-source { font-size: 10px; color: var(--lime-dark); margin-top: 6px; font-weight: 500; }

  .loading-bar { height: 3px; background: var(--gray-100); border-radius: 3px; overflow: hidden; margin: 12px 16px; }
  .loading-fill { height: 100%; width: 0; background: var(--lime); border-radius: 3px; transition: width 0.4s ease; }
</style>
</head>
<body>

<div class="fl-app">

  <!-- HOME SCREEN -->
  <div class="screen active" id="screen-home">
    <nav class="topnav">
      <div class="logo">
        <div class="logo-mark"><span>F</span></div>
        <span class="logo-text">FIN<em>LEARN</em></span>
      </div>
      <span class="nav-badge">Free for Students</span>
    </nav>

    <div class="hero">
      <div class="hero-eyebrow">
        <i class="ti ti-rocket" aria-hidden="true"></i>
        Financial Knowledge 2000 – 2026
      </div>
      <h1 class="hero-title">Master <span>Money</span><br>& Financial Literacy</h1>
      <p class="hero-sub">Everything a student needs — accounting, budgeting, investing, and business finance — powered by live sources.</p>
      <div class="hero-stats">
        <div class="stat-item"><div class="stat-num">500+</div><div class="stat-lbl">Topics</div></div>
        <div class="stat-item"><div class="stat-num">26yrs</div><div class="stat-lbl">Coverage</div></div>
        <div class="stat-item"><div class="stat-num">100%</div><div class="stat-lbl">Free</div></div>
      </div>
    </div>

    <div class="search-wrap">
      <input class="search-input" id="search-input" placeholder="Search topics, terms, concepts…" oninput="handleSearch(this.value)" onfocus="showSearchScreen()" />
    </div>

    <div class="section-label">Learning Streams</div>

    <div class="featured-card" onclick="goTo('accounting')">
      <div class="featured-icon">📊</div>
      <div>
        <div class="featured-title">Accounting Fundamentals</div>
        <div class="featured-sub">Debits, credits, financial statements & more</div>
      </div>
      <i class="ti ti-arrow-right" style="margin-left:auto;font-size:18px;color:var(--forest-dark)" aria-hidden="true"></i>
    </div>

    <div class="menu-grid">
      <div class="menu-card green" onclick="goTo('personal')">
        <span class="card-arrow">↗</span>
        <div class="card-icon">💰</div>
        <div class="card-title">Personal Finance</div>
        <div class="card-desc">Savings, budgeting & debt management</div>
      </div>
      <div class="menu-card lime" onclick="goTo('family')">
        <span class="card-arrow">↗</span>
        <div class="card-icon">🏠</div>
        <div class="card-title">Family Budget</div>
        <div class="card-desc">Household planning & expense tracking</div>
      </div>
      <div class="menu-card white" onclick="goTo('business')">
        <span class="card-arrow">↗</span>
        <div class="card-icon">🏢</div>
        <div class="card-title">Business Finance</div>
        <div class="card-desc">Startups, cash flow & financial models</div>
      </div>
      <div class="menu-card accent" onclick="goTo('investing')">
        <span class="card-arrow">↗</span>
        <div class="card-icon">📈</div>
        <div class="card-title">Investing</div>
        <div class="card-desc">Stocks, bonds, ETFs & compound growth</div>
      </div>
      <div class="menu-card lime" onclick="goTo('tax')">
        <span class="card-arrow">↗</span>
        <div class="card-icon">🧾</div>
        <div class="card-title">Tax & Law</div>
        <div class="card-desc">Income tax, deductions & compliance</div>
      </div>
      <div class="menu-card white" onclick="goTo('glossary')">
        <span class="card-arrow">↗</span>
        <div class="card-icon">📚</div>
        <div class="card-title">Glossary</div>
        <div class="card-desc">350+ finance terms defined clearly</div>
      </div>
    </div>

    <div class="section-label">Tools</div>
    <div class="menu-grid" style="padding-bottom:24px">
      <div class="menu-card white" onclick="goTo('calculator')">
        <div class="card-icon">🧮</div>
        <div class="card-title">Budget Calculator</div>
        <div class="card-desc">Plan income, expenses & savings</div>
      </div>
      <div class="menu-card green" onclick="goTo('quiz')">
        <div class="card-icon">🎯</div>
        <div class="card-title">Quiz Yourself</div>
        <div class="card-desc">Test your financial literacy</div>
      </div>
    </div>

    <div class="bottom-nav">
      <div class="bnav-item active"><i class="ti ti-home bnav-icon"></i><span class="bnav-label">Home</span></div>
      <div class="bnav-item" onclick="goTo('glossary')"><i class="ti ti-book bnav-icon"></i><span class="bnav-label">Glossary</span></div>
      <div class="bnav-item" onclick="goTo('calculator')"><i class="ti ti-calculator bnav-icon"></i><span class="bnav-label">Tools</span></div>
      <div class="bnav-item" onclick="goTo('quiz')"><i class="ti ti-target bnav-icon"></i><span class="bnav-label">Quiz</span></div>
    </div>
  </div>

  <!-- ACCOUNTING SCREEN -->
  <div class="screen" id="screen-accounting">
    <div class="article-header">
      <button class="back-btn" style="color:rgba(255,255,255,0.6)" onclick="goHome()"><i class="ti ti-arrow-left"></i> Back</button>
      <div class="article-tag">ACCOUNTING</div>
      <h2 class="article-title">Accounting Fundamentals</h2>
      <div class="article-meta">Sources: IFRS, FASB, Investopedia, Khan Academy · Updated 2026</div>
    </div>

    <div class="source-strip">
      <div class="source-strip-label">Live Sources</div>
      <div class="source-item"><i class="ti ti-link" style="font-size:12px"></i> ifrs.org · International standards</div>
      <div class="source-item"><i class="ti ti-link" style="font-size:12px"></i> fasb.org · US GAAP guidelines</div>
      <div class="source-item"><i class="ti ti-link" style="font-size:12px"></i> investopedia.com · Concepts explained</div>
    </div>

    <div class="topic-list">
      <div class="topic-item" onclick="showArticle('accounting', 'double-entry')">
        <div class="topic-icon">⚖️</div>
        <div><div class="topic-name">Double-Entry Bookkeeping</div><div class="topic-count">Core principle since 1494</div></div>
        <i class="ti ti-chevron-right topic-chevron"></i>
      </div>
      <div class="topic-item" onclick="showArticle('accounting', 'balance-sheet')">
        <div class="topic-icon">📋</div>
        <div><div class="topic-name">Balance Sheet</div><div class="topic-count">Assets = Liabilities + Equity</div></div>
        <i class="ti ti-chevron-right topic-chevron"></i>
      </div>
      <div class="topic-item" onclick="showArticle('accounting', 'income-statement')">
        <div class="topic-icon">📄</div>
        <div><div class="topic-name">Income Statement (P&L)</div><div class="topic-count">Revenue, expenses, profit</div></div>
        <i class="ti ti-chevron-right topic-chevron"></i>
      </div>
      <div class="topic-item" onclick="showArticle('accounting', 'cash-flow')">
        <div class="topic-icon">💸</div>
        <div><div class="topic-name">Cash Flow Statement</div><div class="topic-count">Operating, investing, financing</div></div>
        <i class="ti ti-chevron-right topic-chevron"></i>
      </div>
      <div class="topic-item" onclick="showArticle('accounting', 'ratios')">
        <div class="topic-icon">📐</div>
        <div><div class="topic-name">Financial Ratios</div><div class="topic-count">Liquidity, profitability, leverage</div></div>
        <i class="ti ti-chevron-right topic-chevron"></i>
      </div>
      <div class="topic-item" onclick="showArticle('accounting', 'depreciation')">
        <div class="topic-icon">📉</div>
        <div><div class="topic-name">Depreciation Methods</div><div class="topic-count">Straight-line, declining balance</div></div>
        <i class="ti ti-chevron-right topic-chevron"></i>
      </div>
    </div>
  </div>

  <!-- PERSONAL FINANCE SCREEN -->
  <div class="screen" id="screen-personal">
    <div class="content-header">
      <button class="back-btn" onclick="goHome()"><i class="ti ti-arrow-left"></i> Back</button>
      <h2 class="content-title">Personal Finance</h2>
      <p class="content-sub">Build wealth, manage debt, and plan your future</p>
    </div>
    <div class="source-strip" style="margin-top:12px">
      <div class="source-strip-label">Sources</div>
      <div class="source-item"><i class="ti ti-link" style="font-size:12px"></i> consumerfinance.gov · CFPB guides</div>
      <div class="source-item"><i class="ti ti-link" style="font-size:12px"></i> myfico.com · Credit scoring</div>
      <div class="source-item"><i class="ti ti-link" style="font-size:12px"></i> nerdwallet.com · Product comparisons</div>
    </div>
    <div class="topic-list">
      <div class="topic-item" onclick="showArticle('personal', '50-30-20')"><div class="topic-icon">💡</div><div><div class="topic-name">The 50/30/20 Rule</div><div class="topic-count">Gold-standard budgeting framework</div></div><i class="ti ti-chevron-right topic-chevron"></i></div>
      <div class="topic-item" onclick="showArticle('personal', 'emergency-fund')"><div class="topic-icon">🛡️</div><div><div class="topic-name">Emergency Fund</div><div class="topic-count">3–6 months of expenses saved</div></div><i class="ti ti-chevron-right topic-chevron"></i></div>
      <div class="topic-item" onclick="showArticle('personal', 'credit-scores')"><div class="topic-icon">⭐</div><div><div class="topic-name">Credit Scores & Reports</div><div class="topic-count">FICO, VantageScore explained</div></div><i class="ti ti-chevron-right topic-chevron"></i></div>
      <div class="topic-item" onclick="showArticle('personal', 'compound-interest')"><div class="topic-icon">🔁</div><div><div class="topic-name">Compound Interest</div><div class="topic-count">The 8th wonder of the world</div></div><i class="ti ti-chevron-right topic-chevron"></i></div>
      <div class="topic-item" onclick="showArticle('personal', 'debt')"><div class="topic-icon">⛓️</div><div><div class="topic-name">Debt Payoff Strategies</div><div class="topic-count">Avalanche vs. snowball methods</div></div><i class="ti ti-chevron-right topic-chevron"></i></div>
    </div>
  </div>

  <!-- FAMILY BUDGET SCREEN -->
  <div class="screen" id="screen-family">
    <div class="content-header">
      <button class="back-btn" onclick="goHome()"><i class="ti ti-arrow-left"></i> Back</button>
      <h2 class="content-title">Family Budget Planning</h2>
      <p class="content-sub">Household finance, shared expenses & long-term goals</p>
    </div>
    <div class="source-strip" style="margin-top:12px">
      <div class="source-strip-label">Sources</div>
      <div class="source-item"><i class="ti ti-link" style="font-size:12px"></i> usa.gov · Family financial guides</div>
      <div class="source-item"><i class="ti ti-link" style="font-size:12px"></i> oecd.org · Household savings data</div>
    </div>
    <div class="topic-list">
      <div class="topic-item" onclick="showArticle('family', 'monthly-budget')"><div class="topic-icon">📅</div><div><div class="topic-name">Monthly Household Budget</div><div class="topic-count">Template & planning steps</div></div><i class="ti ti-chevron-right topic-chevron"></i></div>
      <div class="topic-item" onclick="showArticle('family', 'groceries')"><div class="topic-icon">🛒</div><div><div class="topic-name">Cutting Grocery Costs</div><div class="topic-count">Meal planning & smart shopping</div></div><i class="ti ti-chevron-right topic-chevron"></i></div>
      <div class="topic-item" onclick="showArticle('family', 'mortgage')"><div class="topic-icon">🏡</div><div><div class="topic-name">Mortgage Basics</div><div class="topic-count">Fixed vs. variable, amortization</div></div><i class="ti ti-chevron-right topic-chevron"></i></div>
      <div class="topic-item" onclick="showArticle('family', 'insurance')"><div class="topic-icon">🔐</div><div><div class="topic-name">Family Insurance</div><div class="topic-count">Life, health & home coverage</div></div><i class="ti ti-chevron-right topic-chevron"></i></div>
      <div class="topic-item" onclick="showArticle('family', 'education-savings')"><div class="topic-icon">🎓</div><div><div class="topic-name">Education Savings (529 & more)</div><div class="topic-count">College & tuition planning</div></div><i class="ti ti-chevron-right topic-chevron"></i></div>
    </div>
  </div>

  <!-- BUSINESS FINANCE SCREEN -->
  <div class="screen" id="screen-business">
    <div class="content-header">
      <button class="back-btn" onclick="goHome()"><i class="ti ti-arrow-left"></i> Back</button>
      <h2 class="content-title">Business Finance</h2>
      <p class="content-sub">From startup cash flow to financial modelling</p>
    </div>
    <div class="source-strip" style="margin-top:12px">
      <div class="source-strip-label">Sources</div>
      <div class="source-item"><i class="ti ti-link" style="font-size:12px"></i> sba.gov · US Small Business Admin</div>
      <div class="source-item"><i class="ti ti-link" style="font-size:12px"></i> sec.gov · Public company filings</div>
      <div class="source-item"><i class="ti ti-link" style="font-size:12px"></i> wsj.com · Business finance news</div>
    </div>
    <div class="topic-list">
      <div class="topic-item" onclick="showArticle('business', 'startup-finance')"><div class="topic-icon">🚀</div><div><div class="topic-name">Startup Finance Basics</div><div class="topic-count">Burn rate, runway & funding</div></div><i class="ti ti-chevron-right topic-chevron"></i></div>
      <div class="topic-item" onclick="showArticle('business', 'cash-flow-biz')"><div class="topic-icon">🔄</div><div><div class="topic-name">Business Cash Flow</div><div class="topic-count">Forecasting & working capital</div></div><i class="ti ti-chevron-right topic-chevron"></i></div>
      <div class="topic-item" onclick="showArticle('business', 'break-even')"><div class="topic-icon">⚡</div><div><div class="topic-name">Break-Even Analysis</div><div class="topic-count">Fixed costs, variable costs, BEP</div></div><i class="ti ti-chevron-right topic-chevron"></i></div>
      <div class="topic-item" onclick="showArticle('business', 'valuation')"><div class="topic-icon">💼</div><div><div class="topic-name">Business Valuation</div><div class="topic-count">DCF, multiples & comparables</div></div><i class="ti ti-chevron-right topic-chevron"></i></div>
      <div class="topic-item" onclick="showArticle('business', 'financial-model')"><div class="topic-icon">🗂️</div><div><div class="topic-name">Financial Modelling</div><div class="topic-count">3-statement models, scenarios</div></div><i class="ti ti-chevron-right topic-chevron"></i></div>
    </div>
  </div>

  <!-- INVESTING SCREEN -->
  <div class="screen" id="screen-investing">
    <div class="content-header">
      <button class="back-btn" onclick="goHome()"><i class="ti ti-arrow-left"></i> Back</button>
      <h2 class="content-title">Investing</h2>
      <p class="content-sub">Stocks, bonds, index funds & long-term wealth building</p>
    </div>
    <div class="source-strip" style="margin-top:12px">
      <div class="source-strip-label">Sources</div>
      <div class="source-item"><i class="ti ti-link" style="font-size:12px"></i> sec.gov/investor · SEC investor education</div>
      <div class="source-item"><i class="ti ti-link" style="font-size:12px"></i> morningstar.com · Fund analysis</div>
    </div>
    <div class="topic-list">
      <div class="topic-item" onclick="showArticle('investing', 'stocks')"><div class="topic-icon">📈</div><div><div class="topic-name">How Stocks Work</div><div class="topic-count">Shares, dividends & market cap</div></div><i class="ti ti-chevron-right topic-chevron"></i></div>
      <div class="topic-item" onclick="showArticle('investing', 'index-funds')"><div class="topic-icon">🌐</div><div><div class="topic-name">Index Funds & ETFs</div><div class="topic-count">Passive investing, diversification</div></div><i class="ti ti-chevron-right topic-chevron"></i></div>
      <div class="topic-item" onclick="showArticle('investing', 'risk')"><div class="topic-icon">🎲</div><div><div class="topic-name">Risk vs. Return</div><div class="topic-count">Asset allocation & volatility</div></div><i class="ti ti-chevron-right topic-chevron"></i></div>
      <div class="topic-item" onclick="showArticle('investing', 'retirement')"><div class="topic-icon">🏦</div><div><div class="topic-name">Retirement Accounts</div><div class="topic-count">401(k), IRA, Roth IRA explained</div></div><i class="ti ti-chevron-right topic-chevron"></i></div>
    </div>
  </div>

  <!-- TAX SCREEN -->
  <div class="screen" id="screen-tax">
    <div class="content-header">
      <button class="back-btn" onclick="goHome()"><i class="ti ti-arrow-left"></i> Back</button>
      <h2 class="content-title">Tax & Legal</h2>
      <p class="content-sub">Understand income tax, deductions & compliance rules</p>
    </div>
    <div class="source-strip" style="margin-top:12px">
      <div class="source-strip-label">Sources</div>
      <div class="source-item"><i class="ti ti-link" style="font-size:12px"></i> irs.gov · US Tax authority</div>
      <div class="source-item"><i class="ti ti-link" style="font-size:12px"></i> taxfoundation.org · Tax policy research</div>
    </div>
    <div class="topic-list">
      <div class="topic-item" onclick="showArticle('tax', 'income-tax')"><div class="topic-icon">🧾</div><div><div class="topic-name">How Income Tax Works</div><div class="topic-count">Brackets, marginal vs. effective rates</div></div><i class="ti ti-chevron-right topic-chevron"></i></div>
      <div class="topic-item" onclick="showArticle('tax', 'deductions')"><div class="topic-icon">✂️</div><div><div class="topic-name">Tax Deductions & Credits</div><div class="topic-count">Standard vs. itemized deductions</div></div><i class="ti ti-chevron-right topic-chevron"></i></div>
      <div class="topic-item" onclick="showArticle('tax', 'capital-gains')"><div class="topic-icon">💹</div><div><div class="topic-name">Capital Gains Tax</div><div class="topic-count">Short-term vs. long-term rates</div></div><i class="ti ti-chevron-right topic-chevron"></i></div>
      <div class="topic-item" onclick="showArticle('tax', 'business-tax')"><div class="topic-icon">🏛️</div><div><div class="topic-name">Business Taxes</div><div class="topic-count">Sole trader, LLC, corporation</div></div><i class="ti ti-chevron-right topic-chevron"></i></div>
    </div>
  </div>

  <!-- ARTICLE SCREEN -->
  <div class="screen" id="screen-article">
    <div id="article-content"></div>
  </div>

  <!-- GLOSSARY SCREEN -->
  <div class="screen" id="screen-glossary">
    <div class="content-header">
      <button class="back-btn" onclick="goHome()"><i class="ti ti-arrow-left"></i> Back</button>
      <h2 class="content-title">Financial Glossary</h2>
      <p class="content-sub">350+ terms explained for students</p>
    </div>
    <div class="glossary-chips" id="gloss-chips"></div>
    <div class="gloss-entry" id="gloss-entry">
      <div class="gloss-term" id="gloss-term"></div>
      <div class="gloss-def" id="gloss-def"></div>
    </div>
  </div>

  <!-- CALCULATOR SCREEN -->
  <div class="screen" id="screen-calculator">
    <div class="content-header">
      <button class="back-btn" onclick="goHome()"><i class="ti ti-arrow-left"></i> Back</button>
      <h2 class="content-title">Budget Calculator</h2>
      <p class="content-sub">Plan your monthly income & expenses</p>
    </div>
    <div class="calc-wrap">
      <div class="calc-card">
        <div class="calc-label">Monthly Income ($)</div>
        <input class="calc-input" id="calc-income" type="number" placeholder="e.g. 3000" />
        <div class="calc-label">Monthly Expenses ($)</div>
        <input class="calc-input" id="calc-expenses" type="number" placeholder="e.g. 2100" />
        <div class="calc-label">Monthly Debt Payments ($)</div>
        <input class="calc-input" id="calc-debt" type="number" placeholder="e.g. 400" />
        <button class="calc-btn" onclick="runCalc()">Calculate Budget</button>
        <div class="calc-result" id="calc-result" style="display:none">
          <div class="calc-result-num" id="calc-num"></div>
          <div class="calc-result-lbl" id="calc-lbl"></div>
          <div id="calc-breakdown" style="margin-top:12px;font-size:13px;color:var(--forest);text-align:left;line-height:1.8"></div>
        </div>
      </div>
    </div>
  </div>

  <!-- QUIZ SCREEN -->
  <div class="screen" id="screen-quiz">
    <div class="content-header">
      <button class="back-btn" onclick="goHome()"><i class="ti ti-arrow-left"></i> Back</button>
      <h2 class="content-title">Financial Literacy Quiz</h2>
      <p class="content-sub">Test your knowledge across all topics</p>
    </div>
    <div class="quiz-wrap" id="quiz-area"></div>
  </div>

  <!-- SEARCH RESULTS SCREEN -->
  <div class="screen" id="screen-search">
    <div class="content-header">
      <button class="back-btn" onclick="goHome()"><i class="ti ti-arrow-left"></i> Back</button>
      <div class="search-wrap" style="padding:0;margin-top:10px">
        <input class="search-input" id="search-input-inner" placeholder="Search topics…" oninput="handleSearch(this.value)" />
      </div>
    </div>
    <div class="loading-bar"><div class="loading-fill" id="search-loading"></div></div>
    <div id="search-results"></div>
  </div>

</div>

<script>
const $ = id => document.getElementById(id);

const ARTICLES = {
  'double-entry': {
    tag: 'ACCOUNTING', title: 'Double-Entry Bookkeeping',
    meta: 'Origin: Luca Pacioli 1494 · IFRS / US GAAP · Investopedia',
    sections: [
      { h: 'What is it?', p: 'Every financial transaction affects at least two accounts — one debit and one credit — keeping the accounting equation in balance. This principle has been the backbone of all modern accounting since the 15th century.' },
      { h: 'The Accounting Equation', p: 'Assets = Liabilities + Owner\'s Equity. When you buy equipment worth $5,000 with cash, equipment (asset) goes up by $5,000 and cash (asset) goes down by $5,000 — still balanced.' },
      { h: 'Debits vs. Credits', items: ['Debit increases assets and expenses', 'Credit increases liabilities, equity, and revenue', 'Every transaction has equal debits and credits (balanced ledger)'] },
      { h: 'Why it matters', p: 'Double-entry reduces errors, detects fraud, and provides a complete audit trail required by GAAP and IFRS standards worldwide.' }
    ],
    key: { title: 'KEY RULE', text: 'For every debit entry there must be an equal and opposite credit entry. The ledger must always balance.' },
    sources: ['ifrs.org · IAS 1 Presentation of Financial Statements', 'fasb.org · ASC 210 Balance Sheet', 'investopedia.com · Double-Entry Accounting']
  },
  'balance-sheet': {
    tag: 'ACCOUNTING', title: 'The Balance Sheet',
    meta: 'IFRS IAS 1 · US GAAP ASC 210 · SEC reporting',
    sections: [
      { h: 'Definition', p: 'A balance sheet is a snapshot of a company\'s financial position at a specific point in time. It lists everything the company owns (assets), owes (liabilities), and the residual interest of owners (equity).' },
      { h: 'Three Key Sections', items: ['Current Assets: cash, inventory, receivables (convertible within 1 year)', 'Non-Current Assets: property, plant, equipment, intangibles', 'Liabilities: accounts payable, bank loans, bonds payable', 'Shareholders\' Equity: paid-in capital, retained earnings'] },
      { h: 'Reading a Balance Sheet', p: 'Compare current assets to current liabilities to assess short-term liquidity. A current ratio above 2.0 is generally considered healthy for most industries.' }
    ],
    key: { title: 'FORMULA', text: 'Assets = Liabilities + Shareholders\' Equity — this equation must always hold.' },
    sources: ['ifrs.org · IAS 1', 'sec.gov · 10-K Filing Requirements']
  },
  'income-statement': {
    tag: 'ACCOUNTING', title: 'Income Statement (P&L)',
    meta: 'IFRS IAS 1 · US GAAP · Investopedia',
    sections: [
      { h: 'What it shows', p: 'The income statement (also called a Profit & Loss or P&L) reports a company\'s revenues, expenses, and resulting profit or loss over a period of time — usually a quarter or a year. Unlike the balance sheet, which is a snapshot, the income statement covers a range of time.' },
      { h: 'The Basic Structure', items: ['Revenue (Sales): total income from core operations', 'Cost of Goods Sold (COGS): direct costs of producing goods/services', 'Gross Profit: Revenue − COGS', 'Operating Expenses: rent, salaries, marketing, admin', 'Operating Income: Gross Profit − Operating Expenses', 'Net Income: after interest, taxes, and other items'] },
      { h: 'Why it matters', p: 'Investors and lenders use the income statement to judge whether a business is actually profitable — separate from how much cash it holds or how many assets it owns.' }
    ],
    key: { title: 'KEY FORMULA', text: 'Net Income = Total Revenue − Total Expenses (COGS + Operating + Interest + Tax).' },
    sources: ['ifrs.org · IAS 1 Presentation of Financial Statements', 'investopedia.com · Income Statement basics']
  },
  'cash-flow': {
    tag: 'ACCOUNTING', title: 'Cash Flow Statement',
    meta: 'IFRS IAS 7 · US GAAP ASC 230',
    sections: [
      { h: 'Why profit ≠ cash', p: 'A company can be profitable on paper (per its income statement) yet run out of cash — for example if customers haven\'t paid their invoices yet. The cash flow statement tracks actual cash moving in and out.' },
      { h: 'Three Sections', items: ['Operating Activities: cash from core business operations (sales, expenses)', 'Investing Activities: cash used for or generated from buying/selling assets', 'Financing Activities: cash from loans, share issues, dividends, debt repayment'] },
      { h: 'Reading it', p: 'A healthy business typically shows positive operating cash flow, even if investing cash flow is negative (because it\'s reinvesting in growth).' }
    ],
    key: { title: 'KEY RULE', text: 'Cash is king — a company can survive without profit longer than it can survive without cash.' },
    sources: ['ifrs.org · IAS 7 Statement of Cash Flows', 'investopedia.com · Cash Flow Statement']
  },
  'ratios': {
    tag: 'ACCOUNTING', title: 'Financial Ratios',
    meta: 'Investopedia · CFA Institute fundamentals',
    sections: [
      { h: 'Why ratios matter', p: 'Financial ratios turn raw numbers on a balance sheet or income statement into comparable, meaningful signals — letting you judge a company\'s health against competitors or its own history.' },
      { h: 'Liquidity Ratios', items: ['Current Ratio: Current Assets ÷ Current Liabilities (above 1.5 is healthy)', 'Quick Ratio: (Current Assets − Inventory) ÷ Current Liabilities'] },
      { h: 'Profitability Ratios', items: ['Gross Margin: Gross Profit ÷ Revenue', 'Net Margin: Net Income ÷ Revenue', 'Return on Equity (ROE): Net Income ÷ Shareholders\' Equity'] },
      { h: 'Leverage Ratios', items: ['Debt-to-Equity: Total Liabilities ÷ Shareholders\' Equity', 'Interest Coverage: Operating Income ÷ Interest Expense'] }
    ],
    key: { title: 'KEY TIP', text: 'Never judge a ratio in isolation — always compare it to industry averages or the company\'s own trend over time.' },
    sources: ['investopedia.com · Financial ratio analysis', 'cfainstitute.org · Financial statement analysis']
  },
  'depreciation': {
    tag: 'ACCOUNTING', title: 'Depreciation Methods',
    meta: 'US GAAP · IFRS IAS 16 · IRS Publication 946',
    sections: [
      { h: 'What is depreciation?', p: 'Depreciation spreads the cost of a tangible asset (like machinery or a vehicle) over its useful life, rather than expensing the full cost the year it was purchased. This matches the expense to the periods the asset actually generates revenue.' },
      { h: 'Straight-Line Method', p: 'The simplest method: (Cost − Salvage Value) ÷ Useful Life = equal expense every year. A $10,000 machine with a $1,000 salvage value and 9-year life depreciates $1,000 per year.' },
      { h: 'Declining Balance Method', p: 'An "accelerated" method that expenses more in early years and less later — useful for assets that lose value quickly, like technology equipment.' },
      { h: 'Units of Production', p: 'Ties depreciation to actual usage (e.g., machine hours or miles driven) rather than time — common for vehicles and manufacturing equipment.' }
    ],
    key: { title: 'KEY POINT', text: 'Depreciation is a non-cash expense — it reduces reported profit but doesn\'t affect actual cash in the bank.' },
    sources: ['irs.gov · Publication 946, How to Depreciate Property', 'ifrs.org · IAS 16 Property, Plant and Equipment']
  },
  '50-30-20': {
    tag: 'PERSONAL FINANCE', title: 'The 50/30/20 Budgeting Rule',
    meta: 'Source: Elizabeth Warren · "All Your Worth" (2005) · CFPB',
    sections: [
      { h: 'The Rule Explained', p: 'Divide your after-tax income into three buckets: 50% for needs, 30% for wants, and 20% for savings and debt repayment. This simple framework was popularised by Senator Elizabeth Warren.' },
      { h: '50% — Needs', items: ['Rent or mortgage', 'Utilities, groceries, transport', 'Minimum debt payments', 'Insurance premiums'] },
      { h: '30% — Wants', items: ['Dining out & entertainment', 'Subscriptions & hobbies', 'Travel & shopping'] },
      { h: '20% — Savings & Debt', items: ['Emergency fund contributions', 'Retirement account (401k/IRA)', 'Extra debt repayment', 'Investment accounts'] }
    ],
    key: { title: 'STUDENT TIP', text: 'If living in an expensive city, flip it: 60% needs / 20% wants / 20% savings — adapt the rule to your reality.' },
    sources: ['consumerfinance.gov · Budgeting tools', 'elizabethwarren.com · All Your Worth methodology']
  },
  'emergency-fund': {
    tag: 'PERSONAL FINANCE', title: 'Emergency Fund',
    meta: 'CFPB · Federal Reserve Survey of Household Economics',
    sections: [
      { h: 'What it is', p: 'An emergency fund is cash set aside specifically to cover unexpected expenses — job loss, medical bills, car repairs — without going into debt.' },
      { h: 'How much to save', p: 'The standard guideline is 3–6 months of essential living expenses. Freelancers, single-income households, or those in unstable jobs may want closer to 6–9 months.' },
      { h: 'Where to keep it', items: ['A high-yield savings account, not a checking account (earns interest, stays liquid)', 'Not invested in stocks — you need this money to be stable and accessible', 'Separate from your everyday spending account, to avoid accidental spending'] },
      { h: 'Building it gradually', p: 'Start small: even $500–$1,000 covers most minor emergencies and prevents reliance on credit cards. Automate a fixed transfer each payday to build the habit.' }
    ],
    key: { title: 'STUDENT TIP', text: 'Even $25 a month adds up — starting the habit early matters more than the amount at first.' },
    sources: ['consumerfinance.gov · Emergency savings guidance', 'federalreserve.gov · Survey of Household Economics']
  },
  'credit-scores': {
    tag: 'PERSONAL FINANCE', title: 'Credit Scores & Reports',
    meta: 'FICO · VantageScore · myFICO.com',
    sections: [
      { h: 'What a credit score is', p: 'A three-digit number (typically 300–850) summarizing how likely you are to repay borrowed money. Lenders, landlords, and sometimes employers check it.' },
      { h: 'What makes up your FICO score', items: ['35% — Payment history (on-time vs. late payments)', '30% — Amounts owed (credit utilization)', '15% — Length of credit history', '10% — New credit inquiries', '10% — Credit mix (cards, loans, mortgages)'] },
      { h: 'How to build good credit', p: 'Pay bills on time, keep credit utilization under 30% of your limit, avoid opening too many new accounts at once, and check your credit report annually for errors.' }
    ],
    key: { title: 'KEY TIP', text: 'You\'re entitled to a free credit report annually from each major bureau (Equifax, Experian, TransUnion) via AnnualCreditReport.com.' },
    sources: ['myfico.com · How FICO scores are calculated', 'consumerfinance.gov · Credit reports and scores']
  },
  'compound-interest': {
    tag: 'PERSONAL FINANCE', title: 'Compound Interest',
    meta: 'Einstein called it the 8th wonder · Math verified',
    sections: [
      { h: 'How it works', p: 'Compound interest means you earn interest on your interest. Unlike simple interest (which only accrues on your principal), compound interest grows exponentially over time.' },
      { h: 'The Formula', p: 'A = P × (1 + r/n)^(n×t) where P is principal, r is annual rate, n is compounding periods per year, and t is time in years.' },
      { h: 'Real example', p: '$1,000 invested at 8% annually becomes $2,159 after 10 years, $4,660 after 20 years, and $10,063 after 30 years — without adding a single extra dollar.' },
      { h: 'The Golden Rule', items: ['Start early — time is your most powerful asset', 'Reinvest dividends automatically', 'Minimise fees that eat into compound growth', 'Never withdraw early if avoidable'] }
    ],
    key: { title: 'RULE OF 72', text: 'Divide 72 by your interest rate to find how long it takes to double your money. At 8%, your money doubles every 9 years.' },
    sources: ['investopedia.com · Compound Interest Calculator', 'sec.gov/investor · Time value of money']
  },
  'debt': {
    tag: 'PERSONAL FINANCE', title: 'Debt Payoff Strategies',
    meta: 'CFPB · NerdWallet comparisons',
    sections: [
      { h: 'Avalanche Method', p: 'Pay minimums on all debts, then throw extra money at the debt with the highest interest rate first. This minimizes total interest paid and is mathematically optimal.' },
      { h: 'Snowball Method', p: 'Pay minimums on all debts, then throw extra money at the smallest balance first, regardless of interest rate. This builds momentum and motivation through quick wins.' },
      { h: 'Which to choose', items: ['Avalanche: best if you want to save the most money overall', 'Snowball: best if you need psychological wins to stay motivated', 'Both work — the "best" method is the one you\'ll actually stick with'] },
      { h: 'Avoiding new debt', p: 'While paying off debt, pause new borrowing (especially high-interest credit cards) and build a small emergency buffer to avoid relapsing into debt for minor emergencies.' }
    ],
    key: { title: 'KEY INSIGHT', text: 'Studies on debt repayment behavior show the snowball method often produces higher completion rates, even though avalanche saves more in interest.' },
    sources: ['consumerfinance.gov · Debt repayment strategies', 'nerdwallet.com · Avalanche vs snowball method']
  },
  'monthly-budget': {
    tag: 'FAMILY BUDGET', title: 'Monthly Household Budget',
    meta: 'Source: OECD Household Finance · USA.gov',
    sections: [
      { h: 'Step 1 — List all income', p: 'Include all sources: salaries, freelance, benefits, rental income. Use net (after-tax) figures for accuracy.' },
      { h: 'Step 2 — Categorise expenses', items: ['Fixed: rent, mortgage, loan repayments, subscriptions', 'Variable: groceries, fuel, utilities, clothing', 'Discretionary: dining out, holidays, entertainment', 'Savings: emergency fund, retirement, investment'] },
      { h: 'Step 3 — Find the gap', p: 'Total income minus total expenses = your monthly surplus or deficit. A positive number means you can save or invest more. A negative number means cuts are needed.' },
      { h: 'Step 4 — Review monthly', p: 'Track actuals vs. budget. Free tools: YNAB, Mint, EveryDollar, or a simple spreadsheet.' }
    ],
    key: { title: 'FAMILY RULE', text: 'Budget together as a household — financial transparency reduces money-related stress and conflict by up to 40% (APA surveys).' },
    sources: ['usa.gov · Family financial planning', 'oecd.org · Household savings statistics 2025']
  },
  'groceries': {
    tag: 'FAMILY BUDGET', title: 'Cutting Grocery Costs',
    meta: 'USDA Food Plans · Consumer Reports',
    sections: [
      { h: 'Meal Planning', p: 'Planning meals for the week before shopping reduces impulse buys and food waste. Studies show meal planners spend significantly less per month than non-planners.' },
      { h: 'Smart Shopping Habits', items: ['Shop with a list and stick to it', 'Compare unit prices (price per ounce/gram), not just sticker price', 'Buy store-brand/generic items for staples — often identical quality at lower cost', 'Shop sales and stock up on non-perishables when discounted', 'Avoid shopping while hungry — proven to increase impulse purchases'] },
      { h: 'Reducing Waste', p: 'The USDA estimates a significant share of household food ends up wasted. Storing food properly, freezing leftovers, and using a "first in, first out" approach in the fridge cuts waste and cost.' }
    ],
    key: { title: 'FAMILY TIP', text: 'A simple weekly grocery budget cap, tracked with receipts, is one of the most effective ways to control household spending.' },
    sources: ['usda.gov · Official USDA Food Plans', 'consumerreports.org · Grocery savings guides']
  },
  'mortgage': {
    tag: 'FAMILY BUDGET', title: 'Mortgage Basics',
    meta: 'Consumer Financial Protection Bureau · Freddie Mac',
    sections: [
      { h: 'What a mortgage is', p: 'A mortgage is a loan used to buy property, secured by the property itself — meaning the lender can repossess it (foreclose) if payments aren\'t made.' },
      { h: 'Fixed vs. Variable Rate', items: ['Fixed-rate: interest rate stays the same for the entire loan term (predictable payments)', 'Variable/adjustable-rate (ARM): rate can change periodically based on market conditions (initially lower, but riskier long-term)'] },
      { h: 'Amortization', p: 'Each monthly payment is split between interest and principal. Early in the loan, most of the payment goes to interest; over time, more goes to paying down the principal balance.' },
      { h: 'Key costs to budget for', items: ['Down payment (often 3–20% of purchase price)', 'Private mortgage insurance (PMI) if down payment is under 20%', 'Property taxes and homeowner\'s insurance', 'Closing costs (2–5% of loan amount)'] }
    ],
    key: { title: 'KEY TIP', text: 'A lower monthly payment on an ARM can look attractive, but always model what happens if the rate rises before committing.' },
    sources: ['consumerfinance.gov · Mortgage basics guide', 'freddiemac.com · Homebuyer education']
  },
  'insurance': {
    tag: 'FAMILY BUDGET', title: 'Family Insurance',
    meta: 'NAIC · Insurance Information Institute',
    sections: [
      { h: 'Life Insurance', p: 'Provides a payout to beneficiaries if the policyholder dies. Term life (covers a fixed period, cheaper) is generally recommended over whole life for most young families, unless there\'s a specific estate-planning need.' },
      { h: 'Health Insurance', p: 'Covers medical costs. Key terms to understand: premium (monthly cost), deductible (what you pay before coverage kicks in), and out-of-pocket maximum (the most you\'ll pay in a year).' },
      { h: 'Home/Renters Insurance', p: 'Protects against property damage, theft, and liability. Renters insurance is inexpensive and often overlooked, but covers personal belongings and liability even if you don\'t own the property.' },
      { h: 'How much coverage', p: 'A common life insurance guideline is 10x your annual income, adjusted for debts and dependents\' needs.' }
    ],
    key: { title: 'KEY TIP', text: 'Review insurance coverage annually or after major life events (marriage, new child, home purchase) — needs change over time.' },
    sources: ['naic.org · Insurance basics for consumers', 'iii.org · Insurance Information Institute guides']
  },
  'education-savings': {
    tag: 'FAMILY BUDGET', title: 'Education Savings (529 & More)',
    meta: 'SEC Investor.gov · IRS Publication 970',
    sections: [
      { h: '529 College Savings Plans', p: 'Tax-advantaged accounts specifically for education expenses. Contributions grow tax-free, and withdrawals are tax-free when used for qualified education costs like tuition, books, and room and board.' },
      { h: 'Key Features', items: ['No federal tax on investment growth if used for education', 'Many states offer a state tax deduction for contributions', 'Funds can now also cover K-12 tuition (up to $10,000/year) and some apprenticeship costs', 'Unused funds can be rolled over to a Roth IRA under certain conditions (as of SECURE 2.0 Act)'] },
      { h: 'Alternatives', items: ['Coverdell ESA: more flexible investment options, lower contribution limits', 'Custodial accounts (UTMA/UGMA): more flexible use, but counts more heavily against financial aid', 'High-yield savings: simpler, no investment risk, but no tax advantage'] }
    ],
    key: { title: 'KEY TIP', text: 'Starting a 529 plan when a child is born gives 18 years of compound growth — even small monthly contributions add up significantly.' },
    sources: ['investor.gov · 529 plans overview', 'irs.gov · Publication 970, Tax Benefits for Education']
  },
  'startup-finance': {
    tag: 'BUSINESS FINANCE', title: 'Startup Finance Basics',
    meta: 'Source: SBA, Y Combinator, CB Insights · 2000–2026',
    sections: [
      { h: 'Burn Rate', p: 'The rate at which a startup spends its cash reserves each month. Gross burn = total monthly spend. Net burn = monthly spend minus revenue.' },
      { h: 'Runway', p: 'How many months of cash you have left. Runway = Cash / Monthly Net Burn. Most VCs advise maintaining 18–24 months of runway.' },
      { h: 'Funding Stages', items: ['Pre-seed: Founders & angels, $50K–$500K', 'Seed: Angel rounds / small VCs, $500K–$2M', 'Series A: Product-market fit proven, $2M–$15M', 'Series B+: Scale phase, $15M–$100M+'] },
      { h: 'Unit Economics', p: 'Customer Acquisition Cost (CAC) vs. Lifetime Value (LTV). Healthy SaaS businesses target LTV:CAC > 3x with payback under 18 months.' }
    ],
    key: { title: 'GOLDEN RULE', text: 'Revenue is vanity, profit is sanity, cash is reality. Watch your net burn obsessively.' },
    sources: ['sba.gov · Small business startup guide', 'ycombinator.com · Startup financial advice']
  },
  'cash-flow-biz': {
    tag: 'BUSINESS FINANCE', title: 'Business Cash Flow',
    meta: 'SBA.gov · Investopedia',
    sections: [
      { h: 'Why cash flow ≠ profit', p: 'A business can show a profit on its income statement while still running out of cash — for example, if it has large unpaid invoices (accounts receivable) or has invested heavily in inventory.' },
      { h: 'Working Capital', p: 'Working Capital = Current Assets − Current Liabilities. Positive working capital means a business can cover its short-term obligations comfortably.' },
      { h: 'Cash Flow Forecasting', items: ['Project inflows: expected sales, collections on receivables', 'Project outflows: payroll, rent, inventory purchases, loan payments', 'Identify potential shortfalls before they happen, so financing can be arranged in advance'] },
      { h: 'Improving Cash Flow', items: ['Invoice promptly and follow up on late payments', 'Negotiate longer payment terms with suppliers', 'Offer early-payment discounts to customers', 'Keep inventory levels lean'] }
    ],
    key: { title: 'KEY RULE', text: 'A rolling 13-week cash flow forecast is standard practice for spotting cash crunches before they become a crisis.' },
    sources: ['sba.gov · Managing business cash flow', 'investopedia.com · Working capital management']
  },
  'break-even': {
    tag: 'BUSINESS FINANCE', title: 'Break-Even Analysis',
    meta: 'SBA.gov · Investopedia',
    sections: [
      { h: 'What break-even means', p: 'The break-even point is the level of sales at which total revenue equals total costs — the business is neither making a profit nor a loss.' },
      { h: 'The Formula', p: 'Break-Even Point (units) = Fixed Costs ÷ (Price per Unit − Variable Cost per Unit). The denominator is called the "contribution margin."' },
      { h: 'Worked Example', p: 'If fixed costs are $10,000/month, the product sells for $50, and variable cost per unit is $30, the contribution margin is $20. Break-even = $10,000 ÷ $20 = 500 units per month.' },
      { h: 'Why it matters', p: 'Break-even analysis helps set pricing, evaluate whether a new product line is viable, and determine the sales volume needed to cover a new hire or piece of equipment.' }
    ],
    key: { title: 'KEY FORMULA', text: 'Break-Even Point = Fixed Costs ÷ (Price − Variable Cost per Unit)' },
    sources: ['sba.gov · Break-even analysis for small business', 'investopedia.com · Break-even point explained']
  },
  'valuation': {
    tag: 'BUSINESS FINANCE', title: 'Business Valuation',
    meta: 'CFA Institute · SEC.gov · Investopedia',
    sections: [
      { h: 'Why valuation matters', p: 'Business valuation estimates what a company is worth — essential for raising investment, selling a business, mergers, or even estate planning.' },
      { h: 'Discounted Cash Flow (DCF)', p: 'Projects a company\'s future cash flows and discounts them back to present value using a discount rate that reflects risk. Considered the most rigorous method, but highly sensitive to assumptions.' },
      { h: 'Comparable Company Analysis (Multiples)', p: 'Values a business by comparing it to similar public companies using ratios like Price-to-Earnings (P/E) or Enterprise Value-to-EBITDA (EV/EBITDA).' },
      { h: 'Precedent Transactions', p: 'Looks at prices paid for similar companies in past acquisitions to benchmark a fair value, accounting for market conditions at the time.' }
    ],
    key: { title: 'KEY INSIGHT', text: 'No single valuation method is "correct" — professionals typically triangulate using two or three approaches to arrive at a defensible range.' },
    sources: ['cfainstitute.org · Equity valuation methods', 'investopedia.com · Business valuation techniques']
  },
  'financial-model': {
    tag: 'BUSINESS FINANCE', title: 'Financial Modelling',
    meta: 'CFI · Wall Street Prep fundamentals',
    sections: [
      { h: 'What a financial model is', p: 'A financial model is a spreadsheet-based representation of a company\'s past, current, and projected financial performance, used for planning, fundraising, and decision-making.' },
      { h: 'The 3-Statement Model', p: 'Links the Income Statement, Balance Sheet, and Cash Flow Statement together so that a change in one (like a sales increase) flows through and updates the others automatically.' },
      { h: 'Common Uses', items: ['Forecasting revenue and expenses for budgeting', 'Scenario planning: best case, base case, worst case', 'Valuing a company (feeding into a DCF)', 'Preparing for fundraising or loan applications'] },
      { h: 'Best Practices', p: 'Keep assumptions clearly separated from calculations, use consistent formatting (e.g., blue for inputs, black for formulas), and always sanity-check outputs against industry benchmarks.' }
    ],
    key: { title: 'KEY TIP', text: 'A good model is only as good as its assumptions — spend more time stress-testing inputs than building complex formulas.' },
    sources: ['corporatefinanceinstitute.com · Financial modeling fundamentals', 'sba.gov · Business planning tools']
  },
  'stocks': {
    tag: 'INVESTING', title: 'How Stocks Work',
    meta: 'SEC Investor.gov · NYSE/Nasdaq basics',
    sections: [
      { h: 'What a stock is', p: 'A stock (or share) represents partial ownership in a company. When you buy a share, you own a small slice of that company\'s assets and future earnings.' },
      { h: 'How you make money', items: ['Capital appreciation: selling the stock for more than you paid', 'Dividends: a portion of company profits paid directly to shareholders'] },
      { h: 'Market Capitalization', p: 'Market Cap = Share Price × Total Shares Outstanding. It categorizes companies as small-cap, mid-cap, or large-cap, which affects growth potential and volatility.' },
      { h: 'How shares are traded', p: 'Stocks trade on exchanges like the NYSE or Nasdaq, where buyers and sellers are matched electronically. Prices move based on supply, demand, and company/economic news.' }
    ],
    key: { title: 'KEY REMINDER', text: 'Stock prices reflect expectations about future earnings, not just current performance — which is why prices can be volatile.' },
    sources: ['investor.gov · How to invest in stocks', 'nasdaq.com · Stock market basics']
  },
  'index-funds': {
    tag: 'INVESTING', title: 'Index Funds & ETFs',
    meta: 'Source: Vanguard, Morningstar, SEC Investor Education',
    sections: [
      { h: 'What is an index fund?', p: 'A fund that tracks a market index (like the S&P 500) by holding the same stocks in the same proportions. Instead of picking winners, you own the whole market.' },
      { h: 'Why students should love them', items: ['Low fees (0.03%–0.20% vs 1–2% for active funds)', 'Built-in diversification across hundreds of companies', 'Beat 90%+ of active fund managers over 15 years (S&P SPIVA Report)', 'Minimum investment as low as $1 with fractional shares'] },
      { h: 'ETF vs. Mutual Fund', p: 'ETFs trade like stocks on an exchange — you can buy/sell intraday. Index mutual funds price once daily. Both offer diversification; ETFs are often more tax-efficient.' }
    ],
    key: { title: 'BOGLE\'S WISDOM', text: 'John Bogle (Vanguard founder): "Don\'t look for the needle in the haystack. Just buy the haystack."' },
    sources: ['sec.gov/investor · Mutual funds & ETFs', 'morningstar.com · SPIVA report 2025']
  },
  'risk': {
    tag: 'INVESTING', title: 'Risk vs. Return',
    meta: 'SEC Investor.gov · Modern Portfolio Theory basics',
    sections: [
      { h: 'The core tradeoff', p: 'Generally, investments with higher potential returns come with higher risk (volatility, chance of loss). Cash is low-risk/low-return; individual stocks are higher-risk/higher-potential-return.' },
      { h: 'Asset Allocation', p: 'Spreading investments across asset classes (stocks, bonds, cash, real estate) based on your goals, timeline, and risk tolerance. Younger investors with long time horizons can typically afford more stock exposure.' },
      { h: 'Diversification', p: 'Spreading investments within an asset class (e.g., owning many different stocks or an index fund) reduces the impact of any single investment performing poorly.' },
      { h: 'Volatility', p: 'A statistical measure of how much an investment\'s price fluctuates. Higher volatility means bigger swings up and down — not necessarily a bad thing for long-term investors, but uncomfortable short-term.' }
    ],
    key: { title: 'KEY PRINCIPLE', text: 'Time in the market, not timing the market, is the biggest driver of long-term investment success for most people.' },
    sources: ['investor.gov · Assessing your risk tolerance', 'sec.gov/investor · Diversification basics']
  },
  'retirement': {
    tag: 'INVESTING', title: 'Retirement Accounts',
    meta: 'IRS.gov · Investor.gov · 2026 contribution limits',
    sections: [
      { h: '401(k)', p: 'An employer-sponsored retirement account. Contributions are pre-tax (reducing your taxable income now), and many employers offer a matching contribution — essentially free money if you contribute enough to capture it.' },
      { h: 'Traditional IRA', p: 'An individual retirement account with pre-tax contributions (in most cases), similar tax treatment to a 401(k) but not tied to an employer. Withdrawals in retirement are taxed as income.' },
      { h: 'Roth IRA', p: 'Contributions are made with after-tax money, but withdrawals in retirement — including all investment growth — are completely tax-free, provided rules are followed. Best when you expect to be in a similar or higher tax bracket in retirement.' },
      { h: 'Key Strategy', items: ['Contribute enough to your 401(k) to get the full employer match first', 'Then consider maxing a Roth or Traditional IRA', 'Then return to maxing out the 401(k) if funds allow'] }
    ],
    key: { title: 'KEY TIP', text: 'Never leave employer 401(k) match money on the table — it\'s an immediate, guaranteed return on your contribution.' },
    sources: ['irs.gov · Retirement plan contribution limits', 'investor.gov · Retirement savings basics']
  },
  'income-tax': {
    tag: 'TAX', title: 'How Income Tax Works',
    meta: 'Source: IRS.gov · Tax Foundation · 2026 brackets',
    sections: [
      { h: 'Tax Brackets (2025–26 US)', p: 'The US uses a progressive tax system. You pay lower rates on income up to each threshold, and higher rates only on income above it — not on all your income.' },
      { h: '2026 Single Filer Brackets', items: ['10% on income $0–$11,925', '12% on $11,926–$48,475', '22% on $48,476–$103,350', '24% on $103,351–$197,300', '32% / 35% / 37% on higher income'] },
      { h: 'Effective vs. Marginal Rate', p: 'If you earn $60,000, your marginal rate is 22% — but your effective (average) rate is much lower, around 12–13%, because lower brackets apply to your first dollars earned.' }
    ],
    key: { title: 'COMMON MISTAKE', text: 'Moving into a higher bracket doesn\'t tax ALL your income at the higher rate — only the portion that exceeds the threshold.' },
    sources: ['irs.gov · Publication 17', 'taxfoundation.org · 2026 Tax Brackets']
  },
  'deductions': {
    tag: 'TAX', title: 'Tax Deductions & Credits',
    meta: 'IRS.gov · Tax Foundation',
    sections: [
      { h: 'Deductions vs. Credits', p: 'A deduction reduces your taxable income before tax is calculated. A credit reduces your tax bill directly, dollar-for-dollar — making credits generally more valuable than deductions of the same size.' },
      { h: 'Standard vs. Itemized Deduction', p: 'Most taxpayers take the standard deduction (a fixed amount set by the IRS each year) because it\'s simpler and often larger than itemizing. Itemizing only makes sense if your eligible expenses (mortgage interest, large medical bills, charitable donations, state/local taxes) exceed the standard deduction.' },
      { h: 'Common Tax Credits', items: ['Earned Income Tax Credit (EITC): for low-to-moderate income workers', 'Child Tax Credit: for taxpayers with qualifying dependent children', 'American Opportunity / Lifetime Learning Credits: for education expenses'] }
    ],
    key: { title: 'KEY DISTINCTION', text: 'A $1,000 tax credit saves you $1,000 in tax. A $1,000 deduction saves you $1,000 × your tax rate — usually far less.' },
    sources: ['irs.gov · Credits and deductions for individuals', 'taxfoundation.org · Standard deduction explained']
  },
  'capital-gains': {
    tag: 'TAX', title: 'Capital Gains Tax',
    meta: 'IRS Publication 550 · 2026 rates',
    sections: [
      { h: 'What a capital gain is', p: 'A capital gain is the profit made when you sell an asset (stocks, real estate, crypto, etc.) for more than you paid for it. Capital losses occur when you sell for less.' },
      { h: 'Short-Term vs. Long-Term', p: 'Assets held for one year or less are taxed as short-term gains, at your ordinary income tax rate. Assets held for more than one year qualify for long-term capital gains rates, which are typically 0%, 15%, or 20% depending on income — often significantly lower than ordinary rates.' },
      { h: 'Tax-Loss Harvesting', p: 'Selling investments at a loss to offset capital gains elsewhere in your portfolio, reducing your overall tax bill. Up to $3,000 of net losses can also offset ordinary income each year, with excess carried forward.' }
    ],
    key: { title: 'KEY TIP', text: 'Holding an investment for just over a year, rather than selling early, can significantly reduce the tax owed on the gain.' },
    sources: ['irs.gov · Publication 550, Investment Income and Expenses', 'taxfoundation.org · Capital gains tax rates 2026']
  },
  'business-tax': {
    tag: 'TAX', title: 'Business Taxes',
    meta: 'IRS.gov · SBA.gov · Entity comparison',
    sections: [
      { h: 'Sole Proprietorship', p: 'The simplest structure — business income is reported directly on the owner\'s personal tax return (Schedule C). The owner also pays self-employment tax (Social Security and Medicare) on profits.' },
      { h: 'LLC (Limited Liability Company)', p: 'Offers liability protection while typically being taxed like a sole proprietorship or partnership by default ("pass-through" taxation), meaning profits are taxed once, on the owner\'s personal return. LLCs can also elect to be taxed as a corporation.' },
      { h: 'Corporation (C-Corp)', p: 'Taxed as a separate legal entity — the corporation pays corporate income tax on its profits, and shareholders pay tax again on any dividends received ("double taxation"). Offers the strongest liability protection and is common for companies planning to raise venture capital.' },
      { h: 'S-Corp Election', p: 'A tax status (not a separate entity type) that allows profits to pass through to owners\' personal returns like an LLC, while potentially reducing self-employment tax on a portion of income.' }
    ],
    key: { title: 'KEY TIP', text: 'Business structure affects liability, taxation, and fundraising ability — many businesses consult an accountant before choosing or changing structure.' },
    sources: ['irs.gov · Business structures overview', 'sba.gov · Choose a business structure']
  }
};

const GLOSSARY = [
  { term: 'Amortisation', def: 'The process of gradually paying off a debt or writing off an intangible asset over a set period through regular payments.' },
  { term: 'Asset', def: 'Anything of economic value owned by a person or business — cash, property, inventory, patents, or receivables.' },
  { term: 'Balance Sheet', def: 'A financial statement showing a company\'s assets, liabilities, and equity at a specific date. Assets always equal liabilities plus equity.' },
  { term: 'Burn Rate', def: 'The pace at which a startup spends its cash reserves. Monthly net burn = expenses minus revenue.' },
  { term: 'Capital', def: 'Financial assets or the value of assets. In business, it refers to money used to fund operations, invest, or generate more wealth.' },
  { term: 'Compound Interest', def: 'Interest calculated on the initial principal AND the accumulated interest from previous periods — growing exponentially over time.' },
  { term: 'Current Ratio', def: 'Current assets divided by current liabilities. Measures short-term liquidity. A ratio above 1.5 is generally healthy.' },
  { term: 'Debt-to-Equity', def: 'Total liabilities divided by shareholders\' equity. Shows how much a company is financed by debt vs. owner funds.' },
  { term: 'Depreciation', def: 'The accounting reduction in value of a tangible asset over its useful life, spreading the cost as an expense across multiple years.' },
  { term: 'Dividend', def: 'A portion of a company\'s earnings distributed to shareholders, usually quarterly, as a reward for holding the stock.' },
  { term: 'EBITDA', def: 'Earnings Before Interest, Tax, Depreciation, and Amortisation. A measure of core operating profitability excluding financing and accounting decisions.' },
  { term: 'Equity', def: 'The ownership interest in a business or property. In accounting: Assets minus Liabilities. In investing: ownership shares in a company.' },
  { term: 'Fixed Cost', def: 'A cost that does not change with production volume — rent, salaries, insurance. Contrasts with variable costs which scale with output.' },
  { term: 'Gross Profit', def: 'Revenue minus the cost of goods sold (COGS). Measures profitability before operating expenses, tax, and interest.' },
  { term: 'Inflation', def: 'The rate at which the general level of prices rises over time, reducing purchasing power. Measured by CPI or PCE indices.' },
  { term: 'Liability', def: 'Any financial obligation or debt owed by a person or organisation — loans, accounts payable, bonds, and deferred revenue.' },
  { term: 'Liquidity', def: 'How quickly an asset can be converted to cash without significantly affecting its price. Cash is most liquid; real estate is illiquid.' },
  { term: 'Net Profit', def: 'Total revenue minus all expenses including COGS, operating costs, interest, and taxes. Also called "the bottom line."' },
  { term: 'P/E Ratio', def: 'Price-to-Earnings ratio. Stock price divided by earnings per share. Used to value stocks — higher P/E implies growth expectations.' },
  { term: 'Revenue', def: 'The total income earned by a business from its core operations before any costs are deducted. Also called "top line" or turnover.' },
  { term: 'ROI', def: 'Return on Investment. (Gain - Cost) / Cost × 100. Measures the efficiency of an investment as a percentage.' },
  { term: 'Variable Cost', def: 'A cost that changes proportionally with the level of output or sales — raw materials, packaging, sales commissions.' }
];

const QUIZ = [
  { q: 'What does the 50/30/20 rule allocate to savings?', opts: ['50%','30%','20%','10%'], ans: 2, exp: 'The 50/30/20 rule dedicates 20% of after-tax income to savings and debt repayment — an achievable target for most earners.' },
  { q: 'In double-entry bookkeeping, buying office supplies with cash affects which two accounts?', opts: ['Revenue & Liability','Office Supplies (Asset) & Cash (Asset)','Equity & Revenue','Expense & Equity'], ans: 1, exp: 'Correct! Supplies (an asset) increases via debit, and Cash (also an asset) decreases via credit. The equation stays balanced.' },
  { q: 'What does "burn rate" measure for a startup?', opts: ['Gross profit margin','Monthly cash spend','Annual revenue growth','Customer acquisition cost'], ans: 1, exp: 'Burn rate is the monthly rate at which a company spends cash reserves. Knowing it lets you calculate your runway.' },
  { q: 'The Rule of 72 helps you calculate what?', opts: ['Tax owed','How long to double your money','Break-even point','Credit score'], ans: 1, exp: 'Divide 72 by your annual return rate. At 8% growth, your investment doubles in approximately 9 years.' },
  { q: 'Which ratio measures short-term liquidity?', opts: ['P/E Ratio','Debt-to-Equity','Current Ratio','ROI'], ans: 2, exp: 'The Current Ratio (current assets ÷ current liabilities) shows if a company can pay short-term obligations. Above 1.5 is healthy.' },
  { q: 'What is EBITDA?', opts: ['Total expenses','Earnings before interest, tax, depreciation & amortisation','Equity before tax','None of these'], ans: 1, exp: 'EBITDA strips out financing, tax, and non-cash charges to show core operating profitability.' }
];

let quizIndex = 0, quizAnswered = false;
let screenStack = ['home'];

function showScreen(screen) {
  document.querySelectorAll('.screen').forEach(s => s.classList.remove('active'));
  $('screen-' + screen).classList.add('active');
  if (screen === 'glossary') renderGlossary();
  if (screen === 'quiz') renderQuiz();
  window.scrollTo(0, 0);
}

function goTo(screen) {
  if (screenStack[screenStack.length - 1] !== screen) screenStack.push(screen);
  showScreen(screen);
}

function goHome() {
  screenStack = ['home'];
  showScreen('home');
}

function goBack() {
  if (screenStack.length > 1) screenStack.pop();
  showScreen(screenStack[screenStack.length - 1] || 'home');
}

function showSearchScreen() {
  goTo('search');
  setTimeout(() => { $('search-input-inner').value = $('search-input').value; handleSearch($('search-input').value); }, 50);
}

function handleSearch(val) {
  if (!val.trim()) { $('search-results').innerHTML = ''; $('search-loading').style.width = '0'; return; }
  $('search-loading').style.width = '60%';
  const q = val.toLowerCase();
  const results = [];
  // Search articles
  Object.entries(ARTICLES).forEach(([key, a]) => {
    if (a.title.toLowerCase().includes(q) || a.tag.toLowerCase().includes(q) || JSON.stringify(a.sections).toLowerCase().includes(q)) {
      results.push({ title: a.title, snippet: a.sections[0].p || '', tag: a.tag, key });
    }
  });
  // Search glossary
  GLOSSARY.forEach(g => {
    if (g.term.toLowerCase().includes(q) || g.def.toLowerCase().includes(q)) {
      results.push({ title: g.term, snippet: g.def.slice(0, 100) + '…', tag: 'GLOSSARY', key: 'g:' + g.term });
    }
  });
  $('search-loading').style.width = '100%';
  setTimeout(() => { $('search-loading').style.width = '0'; }, 400);
  if (!results.length) {
    $('search-results').innerHTML = '<div style="padding:24px 20px;text-align:center;color:var(--gray-400);font-size:14px">No results for "' + val + '"</div>';
    return;
  }
  $('search-results').innerHTML = '<div style="padding:12px 16px 4px;font-size:11px;font-weight:600;color:var(--gray-400);letter-spacing:1px">' + results.length + ' RESULTS</div>' +
    results.map(r => `<div class="result-card" onclick="openSearchResult('${r.key}')">
      <div class="result-title">${r.title}</div>
      <div class="result-snippet">${r.snippet}</div>
      <div class="result-source">${r.tag}</div>
    </div>`).join('');
}

function openSearchResult(key) {
  if (key.startsWith('g:')) {
    goTo('glossary'); setTimeout(() => selectGloss(key.slice(2)), 200);
  } else { showArticle(null, key); }
}

function showArticle(section, key) {
  const a = ARTICLES[key];
  if (!a) {
    $('article-content').innerHTML = `
      <div class="article-header">
        <button class="back-btn" style="color:rgba(255,255,255,0.6)" onclick="goBack()"><i class="ti ti-arrow-left"></i> Back</button>
        <div class="article-tag">COMING SOON</div>
        <h2 class="article-title">${key.replace(/-/g,' ')}</h2>
      </div>
      <div class="article-body">
        <p style="padding:20px 0;color:var(--gray-600);font-size:14px">This article is still being written. Check back soon!</p>
      </div>`;
    goTo('article');
    return;
  }
  let html = `<div class="article-header">
    <button class="back-btn" style="color:rgba(255,255,255,0.6)" onclick="goBack()"><i class="ti ti-arrow-left"></i> Back</button>
    <div class="article-tag">${a.tag}</div>
    <h2 class="article-title">${a.title}</h2>
    <div class="article-meta">${a.meta}</div>
  </div>
  <div class="article-body">`;
  a.sections.forEach(s => {
    html += `<div class="article-section"><h3>${s.h}</h3>`;
    if (s.p) html += `<p>${s.p}</p>`;
    if (s.items) html += `<ul>${s.items.map(i => `<li>${i}</li>`).join('')}</ul>`;
    html += '</div>';
  });
  if (a.key) html += `<div class="key-box"><div class="key-box-title">${a.key.title}</div><p>${a.key.text}</p></div>`;
  html += '</div>';
  if (a.sources) {
    html += `<div class="source-strip"><div class="source-strip-label">Sources</div>${a.sources.map(s => `<div class="source-item"><i class="ti ti-link" style="font-size:12px"></i> ${s}</div>`).join('')}</div>`;
  }
  html += `<div style="padding:16px"><button onclick="sendPrompt('Tell me more about ${a.title} and give me a practice question')" style="width:100%;padding:12px;background:var(--forest-dark);color:var(--lime);border:none;border-radius:10px;font-size:13px;font-weight:600;cursor:pointer">Ask Claude about this topic ↗</button></div>`;
  $('article-content').innerHTML = html;
  goTo('article');
}

function renderGlossary() {
  const chips = $('gloss-chips');
  chips.innerHTML = GLOSSARY.map(g => `<div class="g-chip" onclick="selectGloss('${g.term}')">${g.term}</div>`).join('');
  selectGloss(GLOSSARY[0].term);
}

function selectGloss(term) {
  const g = GLOSSARY.find(x => x.term === term);
  if (!g) return;
  $('gloss-term').textContent = g.term;
  $('gloss-def').textContent = g.def;
  document.querySelectorAll('.g-chip').forEach(c => { c.classList.toggle('active', c.textContent === term); });
}

function runCalc() {
  const inc = parseFloat($('calc-income').value) || 0;
  const exp = parseFloat($('calc-expenses').value) || 0;
  const debt = parseFloat($('calc-debt').value) || 0;
  const surplus = inc - exp - debt;
  const savePct = inc > 0 ? Math.round((surplus / inc) * 100) : 0;
  $('calc-num').textContent = (surplus >= 0 ? '+' : '') + '$' + surplus.toLocaleString();
  $('calc-lbl').textContent = surplus >= 0 ? 'Monthly surplus — great for saving!' : 'Monthly shortfall — review expenses';
  $('calc-num').style.color = surplus >= 0 ? 'var(--forest-dark)' : '#dc2626';
  $('calc-breakdown').innerHTML = `
    <div>📊 Income: <strong>$${inc.toLocaleString()}</strong></div>
    <div>💳 Expenses: <strong>$${exp.toLocaleString()}</strong></div>
    <div>⛓️ Debt payments: <strong>$${debt.toLocaleString()}</strong></div>
    <div>💰 Savings rate: <strong>${savePct}%</strong> ${savePct >= 20 ? '✅ On track!' : savePct >= 10 ? '🟡 Getting there' : '🔴 Below recommended 20%'}</div>
  `;
  $('calc-result').style.display = 'block';
}

function renderQuiz() {
  quizIndex = Math.floor(Math.random() * QUIZ.length);
  quizAnswered = false;
  const q = QUIZ[quizIndex];
  $('quiz-area').innerHTML = `<div class="quiz-card">
    <div class="quiz-q">Q: ${q.q}</div>
    ${q.opts.map((o, i) => `<button class="quiz-opt" id="qopt-${i}" onclick="answerQuiz(${i})">${o}</button>`).join('')}
    <div id="quiz-feedback"></div>
  </div>
  <div style="padding:12px 0;text-align:center"><button onclick="renderQuiz()" style="background:none;border:none;color:var(--forest);font-size:13px;cursor:pointer;text-decoration:underline">Skip to another question</button></div>`;
}

function answerQuiz(i) {
  if (quizAnswered) return;
  quizAnswered = true;
  const q = QUIZ[quizIndex];
  document.querySelectorAll('.quiz-opt').forEach((b, idx) => {
    b.disabled = true;
    if (idx === q.ans) b.classList.add('correct');
    else if (idx === i) b.classList.add('wrong');
  });
  $('quiz-feedback').innerHTML = `<div class="quiz-result">${i === q.ans ? '✅ Correct! ' : '❌ Not quite. '}${q.exp}</div>
  <div style="margin-top:12px;text-align:center"><button onclick="renderQuiz()" style="padding:10px 24px;background:var(--forest-dark);color:var(--lime);border:none;border-radius:8px;font-size:13px;font-weight:600;cursor:pointer">Next Question →</button></div>`;
}

function sendPrompt(text) {
  if (window.parent && window.parent !== window) {
    window.parent.postMessage({ type: 'sendPrompt', text }, '*');
  } else {
    console.log('sendPrompt:', text);
  }
}
</script>
</body>
</html>
