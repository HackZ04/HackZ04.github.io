---

description: "关于 HackZ04"
layout: "simple"
draft: false
showDate: false
showReadingTime: false
showWordCount: false
showAuthor: false
showBreadcrumbs: false
sharingLinks: false
---

<style>
  .hack-about {
    --ha-blue: #2f80ff;
    --ha-purple: #8b5cf6;
    --ha-cyan: #67e8f9;
    --ha-pink: #f0abfc;

    --ha-heading: #0f172a;
    --ha-text: #334155;
    --ha-text-muted: #64748b;

    --ha-border: rgba(148, 163, 184, 0.22);
    --ha-panel: rgba(255, 255, 255, 0.72);
    --ha-panel-soft: rgba(255, 255, 255, 0.42);
    --ha-grid: rgba(148, 163, 184, 0.10);
    --ha-shadow: 0 30px 100px rgba(15, 23, 42, 0.12);

    max-width: 960px;
    margin: 0 auto;
    padding: 1rem 0 3rem;
    color: var(--ha-text);
  }

  html.dark .hack-about {
    --ha-heading: #f8fafc;
    --ha-text: rgba(226, 232, 240, 0.82);
    --ha-text-muted: #94a3b8;

    --ha-border: rgba(148, 163, 184, 0.18);
    --ha-panel: rgba(15, 23, 42, 0.62);
    --ha-panel-soft: rgba(15, 23, 42, 0.38);
    --ha-grid: rgba(148, 163, 184, 0.08);
    --ha-shadow: 0 30px 100px rgba(0, 0, 0, 0.35);
  }

  .hack-about * {
    box-sizing: border-box;
  }

  .hack-panel {
    position: relative;
    overflow: hidden;
    padding: clamp(1.4rem, 4vw, 2.8rem);
    border: 1px solid var(--ha-border);
    border-radius: 2rem;
    background:
      radial-gradient(circle at 8% 10%, rgba(47, 128, 255, 0.18), transparent 30%),
      radial-gradient(circle at 88% 16%, rgba(139, 92, 246, 0.20), transparent 28%),
      radial-gradient(circle at 78% 92%, rgba(103, 232, 249, 0.16), transparent 32%),
      var(--ha-panel);
    box-shadow: var(--ha-shadow);
    backdrop-filter: blur(18px);
  }

  .hack-panel::before {
    content: "";
    position: absolute;
    inset: 0;
    background-image:
      linear-gradient(var(--ha-grid) 1px, transparent 1px),
      linear-gradient(90deg, var(--ha-grid) 1px, transparent 1px);
    background-size: 34px 34px;
    mask-image: radial-gradient(circle at 50% 10%, black, transparent 70%);
    pointer-events: none;
  }

  .hack-panel::after {
    content: "";
    position: absolute;
    right: -7rem;
    top: -7rem;
    width: 18rem;
    height: 18rem;
    border-radius: 999px;
    background: linear-gradient(135deg, rgba(47, 128, 255, 0.22), rgba(240, 171, 252, 0.18));
    filter: blur(10px);
    pointer-events: none;
  }

  .hack-inner {
    position: relative;
    z-index: 1;
  }

  .hack-hero {
    display: grid;
    grid-template-columns: auto 1fr;
    gap: 1.2rem;
    align-items: center;
    margin-bottom: 2.3rem;
  }

  .hack-avatar {
    position: relative;
    display: block;
    width: clamp(4.8rem, 12vw, 6.8rem);
    aspect-ratio: 1 / 1;
    height: auto;
    border-radius: 50%;
    overflow: hidden;
    flex-shrink: 0;
    line-height: 0;
    background: rgba(15, 23, 42, 0.18);
    border: 3px solid rgba(255, 255, 255, 0.22);
    box-shadow:
      0 18px 48px rgba(47, 128, 255, 0.24),
      0 0 0 6px rgba(96, 165, 250, 0.08);
  }

  .hack-avatar img {
    position: absolute !important;
    inset: 0;
    display: block !important;
    width: 100% !important;
    height: 100% !important;
    max-width: none !important;
    margin: 0 !important;
    padding: 0 !important;
    border-radius: 50% !important;
    object-fit: cover;
    object-position: center;
  }

  .hack-kicker {
    display: inline-flex;
    align-items: center;
    gap: 0.45rem;
    width: fit-content;
    margin-bottom: 0.7rem;
    padding: 0.38rem 0.7rem;
    border: 1px solid var(--ha-border);
    border-radius: 999px;
    background: rgba(47, 128, 255, 0.10);
    color: var(--ha-blue);
    font-size: 0.78rem;
    font-weight: 850;
  }

  .hack-title {
    margin: 0;
    font-size: clamp(2.25rem, 6vw, 4.7rem);
    line-height: 0.95;
    letter-spacing: -0.075em;
    font-weight: 950;
    color: var(--ha-heading);
  }

  .hack-title span {
    background: linear-gradient(135deg, var(--ha-blue), var(--ha-purple), var(--ha-pink));
    -webkit-background-clip: text;
    background-clip: text;
    color: transparent;
  }

  .hack-intro {
    max-width: 760px;
    margin: -0.7rem 0 2.15rem;
    color: var(--ha-text-muted);
    font-size: 1.05rem;
    line-height: 1.9;
  }

  .hack-intro strong {
    color: var(--ha-blue);
    font-weight: 900;
  }

.hack-intro-image {
  display: flex;
  justify-content: center;
  margin: -1.2rem 0 2.4rem;
}

.hack-intro-image img {
  display: block !important;
  width: min(100%, 520px);
  max-width: 100% !important;
  height: auto !important;
  margin: 0 auto !important;
  border-radius: 1.4rem;
  object-fit: cover;
  box-shadow:
    0 24px 70px rgba(15, 23, 42, 0.16),
    0 0 0 1px var(--ha-border);
}

html.dark .hack-intro-image img {
  box-shadow:
    0 24px 70px rgba(0, 0, 0, 0.32),
    0 0 0 1px var(--ha-border);
}

  .hack-section {
    margin-top: 2.1rem;
  }

  .hack-heading {
    display: grid;
    grid-template-columns: auto auto;
    grid-template-rows: auto auto;
    grid-template-areas:
      "emoji title"
      ".     line";
    column-gap: 0.7rem;
    row-gap: 0.48rem;
    align-items: center;
    width: fit-content;
    margin: 0 0 1.25rem;
  }

  .hack-heading .emoji {
    grid-area: emoji;
    font-size: clamp(1.55rem, 4vw, 2.25rem);
    line-height: 1;
    filter: drop-shadow(0 8px 16px rgba(15, 23, 42, 0.14));
  }

  .hack-heading-title {
    grid-area: title;
    font-size: clamp(1.65rem, 4vw, 2.45rem);
    line-height: 1.05;
    font-weight: 950;
    letter-spacing: -0.055em;
    color: var(--ha-heading);
    white-space: nowrap;
  }

  .hack-heading-line {
    grid-area: line;
    display: block;
    width: 7.2rem;
    height: 0.28rem;
    border-radius: 999px;
    background: linear-gradient(90deg, var(--ha-pink), var(--ha-cyan));
    box-shadow: 0 0 18px rgba(103, 232, 249, 0.18);
  }

  .hack-list {
    margin: 0;
    padding: 0;
    list-style: none;
  }

  .hack-list li {
    position: relative;
    margin: 0.55rem 0;
    padding-left: 1.65rem;
    color: var(--ha-text);
    font-size: 1.02rem;
    line-height: 1.75;
  }

  .hack-list li::before {
    content: "";
    position: absolute;
    left: 0.25rem;
    top: 0.83em;
    width: 0.38rem;
    height: 0.38rem;
    border-radius: 999px;
    background: linear-gradient(135deg, var(--ha-cyan), var(--ha-purple));
    box-shadow: 0 0 0 0.25rem rgba(103, 232, 249, 0.12);
  }

  .hack-highlight {
    background: linear-gradient(135deg, var(--ha-blue), var(--ha-purple));
    -webkit-background-clip: text;
    background-clip: text;
    color: transparent;
    font-weight: 900;
  }

  .hack-muted {
    color: var(--ha-text-muted);
    font-style: italic;
  }

  .hack-paper-title {
    font-weight: 900;
    color: var(--ha-heading);
    letter-spacing: -0.02em;
  }

  .hack-authors {
    display: block;
    margin-top: 0.35rem;
    color: var(--ha-text-muted);
    font-size: 0.95rem;
    line-height: 1.85;
  }

  .hack-authors strong {
    color: var(--ha-blue);
    font-weight: 950;
  }

  .hack-award-list {
    display: grid;
    gap: 0.85rem;
    margin: 0;
    padding: 0;
    list-style: none;
  }

  .hack-award-item {
    position: relative;
    display: grid;
    grid-template-columns: minmax(0, 1fr) auto;
    align-items: center;
    gap: 1rem;
    padding-left: 1.65rem;
    color: var(--ha-text);
    font-size: 1.02rem;
    line-height: 1.75;
  }

  .hack-award-item::before {
    content: "";
    position: absolute;
    left: 0.25rem;
    top: 50%;
    width: 0.38rem;
    height: 0.38rem;
    border-radius: 999px;
    transform: translateY(-50%);
    background: linear-gradient(135deg, var(--ha-cyan), var(--ha-purple));
    box-shadow: 0 0 0 0.25rem rgba(103, 232, 249, 0.12);
  }

  .hack-award-name {
    min-width: 0;
  }

  .hack-award-level {
    color: var(--ha-text);
    font-weight: 650;
  }

  .hack-award-year {
    display: inline-flex;
    align-items: center;
    justify-content: center;
    min-width: 4.1rem;
    padding: 0.24rem 0.68rem;
    border: 1px solid var(--ha-border);
    border-radius: 999px;
    background: var(--ha-panel-soft);
    color: var(--ha-blue);
    font-size: 0.84rem;
    font-weight: 850;
    letter-spacing: 0.02em;
  }

  .hack-tags {
    display: flex;
    flex-wrap: wrap;
    gap: 0.55rem;
    margin-top: 1.6rem;
  }

  .hack-tag {
    display: inline-flex;
    align-items: center;
    gap: 0.38rem;
    padding: 0.45rem 0.72rem;
    border: 1px solid var(--ha-border);
    border-radius: 999px;
    background: var(--ha-panel-soft);
    color: var(--ha-text-muted);
    font-size: 0.82rem;
    font-weight: 760;
  }

  .hack-divider {
    width: 100%;
    height: 1px;
    margin: 2.2rem 0 0;
    background: linear-gradient(90deg, transparent, var(--ha-border), transparent);
  }

  @media (max-width: 720px) {
    .hack-panel {
      border-radius: 1.55rem;
      padding: 1.2rem;
    }

    .hack-hero {
      grid-template-columns: 1fr;
      gap: 1rem;
    }

    .hack-heading {
      column-gap: 0.6rem;
      row-gap: 0.42rem;
      max-width: 100%;
    }

    .hack-heading .emoji {
      font-size: clamp(1.4rem, 6vw, 2rem);
    }

    .hack-heading-title {
      font-size: clamp(1.55rem, 7vw, 2.25rem);
      white-space: normal;
    }

    .hack-heading-line {
      width: 6.2rem;
      height: 0.26rem;
    }

    .hack-list li {
      font-size: 0.98rem;
      padding-left: 1.35rem;
    }

    .hack-award-item {
      grid-template-columns: 1fr;
      gap: 0.35rem;
      align-items: start;
      padding-left: 1.35rem;
      font-size: 0.98rem;
    }

    .hack-award-item::before {
      top: 0.86em;
      transform: none;
    }

    .hack-award-year {
      width: fit-content;
      min-width: auto;
      padding: 0.22rem 0.62rem;
      font-size: 0.8rem;
    }
  }
</style>

<div class="hack-about">
  <section class="hack-panel">
    <div class="hack-inner">
      <header class="hack-hero">
        <div class="hack-avatar not-prose">
          <img src="/img/logo.png" alt="HackZ04 Logo">
        </div>
        <div>
          <div class="hack-kicker">🧑‍💻 Personal Homepage</div>
          <h1 class="hack-title">About <span>Me</span></h1>
        </div>
      </header>
      <p class="hack-intro">
        大家好，我是 <strong>HackZ04</strong>，欢迎来到我的窝点。
      </p>
      <div class="hack-intro-image not-prose">
        <img src="/img/intp-睡觉小熊猫.jpg" alt="睡觉小熊猫">
      </div>
      <section class="hack-section">
        <h2 class="hack-heading">
          <span class="emoji">👤</span>
          <span class="hack-heading-title">Individual Profile</span>
          <span class="hack-heading-line"></span>
        </h2>
        <div class="hack-card">
          <p>中国石油大学（华东）软件工程专业本科毕业，获荣誉学士、优秀毕业生称号，第29期青马工程骨干培训班优秀结业。本科期间曾获青岛中加特奖学金、综合优秀奖学金一等奖、创新创业奖学金、文体奖学金等，多次获评优秀学生干部、优秀学生、优秀共青团员。</p>
        </div>
      </section>
      <section class="hack-section">
        <h2 class="hack-heading">
          <span class="emoji">🎓</span>
          <span class="hack-heading-title">Education</span>
          <span class="hack-heading-line"></span>
        </h2>
        <ul class="hack-list">
          <li>
            <span class="hack-highlight">湖南大学</span>
            <span class="hack-muted"> · 硕士</span>
            ，电子信息
            <span class="hack-muted">（2026.09 — 2029.06）</span>
          </li>
          <li>
            <span class="hack-highlight">中国石油大学（华东）</span>
            <span class="hack-muted"> · 学士</span>
            ，软件工程
            <span class="hack-muted">（2022.09 — 2026.06）</span>
          </li>
        </ul>
      </section>
      <div class="hack-divider"></div>
      <section class="hack-section">
        <h2 class="hack-heading">
          <span class="emoji">📄</span>
          <span class="hack-heading-title">Publications</span>
          <span class="hack-heading-line"></span>
        </h2>
        <ul class="hack-list">
          <li>
            <span class="hack-paper-title">
              MGAL: A Multilingual Granularity-Aware Long-Context Benchmark
            </span>
            <span class="hack-muted">（ICML 2026,CCF-A）</span>
            <span class="hack-authors">
              Chunhan Li, Chenglin Xu, <strong>Zongyang Zhang</strong>, Jiale Liu, Zhuoxi Rao,
              Xudong Jia, Junxiu He, Menglin Yang, Wenjuan Gong, Zhengzhe Liu, Chengwei Qin
            </span>
          </li>
        </ul>
      </section>
      <div class="hack-divider"></div>
      <section class="hack-section">
        <h2 class="hack-heading">
          <span class="emoji">🏆</span>
          <span class="hack-heading-title">Competitions</span>
          <span class="hack-heading-line"></span>
        </h2>
        <ul class="hack-award-list">
          <li class="hack-award-item">
            <span class="hack-award-name">
              <span class="hack-highlight">中国机器人及人工智能大赛</span>
              <span class="hack-award-level"> · 全国二等奖</span>
            </span>
            <span class="hack-award-year">2025</span>
          </li>
          <li class="hack-award-item">
            <span class="hack-award-name">
              <span class="hack-highlight">蓝桥杯全国软件和信息技术专业人才大赛</span>
              <span class="hack-award-level"> · 全国三等奖</span>
            </span>
            <span class="hack-award-year">2025</span>
          </li>
          <li class="hack-award-item">
            <span class="hack-award-name">
              <span class="hack-highlight">中国大学生服务外包创新创业大赛</span>
              <span class="hack-award-level"> · 全国三等奖</span>
            </span>
            <span class="hack-award-year">2025</span>
          </li>
        </ul>
      </section>
      <div class="hack-tags">
        <span class="hack-tag">🤖 Artificial Intelligence</span>
        <span class="hack-tag">💻 Software Engineering</span>
        <span class="hack-tag">🚀 HackZ04</span>
      </div>
    </div>
  </section>
</div>

