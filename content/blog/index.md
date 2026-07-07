---
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
  .bloghub {
    --bh-bg: rgba(248, 250, 252, 0.86);
    --bh-card: rgba(255, 255, 255, 0.92);
    --bh-card-soft: rgba(241, 245, 249, 0.92);
    --bh-text: #0f172a;
    --bh-muted: #64748b;
    --bh-border: rgba(148, 163, 184, 0.26);
    --bh-primary: #2563eb;
    --bh-primary-soft: rgba(37, 99, 235, 0.10);
    --bh-shadow: 0 18px 45px rgba(15, 23, 42, 0.08);

    max-width: 1080px;
    margin: 0 auto;
    padding: 1rem 0 3.5rem;
    color: var(--bh-text);
  }

  .dark .bloghub {
    --bh-bg: rgba(15, 23, 42, 0.72);
    --bh-card: rgba(15, 23, 42, 0.86);
    --bh-card-soft: rgba(30, 41, 59, 0.82);
    --bh-text: #e5e7eb;
    --bh-muted: #94a3b8;
    --bh-border: rgba(148, 163, 184, 0.22);
    --bh-primary: #60a5fa;
    --bh-primary-soft: rgba(96, 165, 250, 0.14);
    --bh-shadow: 0 20px 50px rgba(0, 0, 0, 0.26);
  }

  .bloghub-hero {
    position: relative;
    overflow: hidden;
    margin-bottom: 1.5rem;
    padding: 2rem;
    border: 1px solid var(--bh-border);
    border-radius: 1.5rem;
    background:
      radial-gradient(circle at top left, var(--bh-primary-soft), transparent 34%),
      linear-gradient(135deg, var(--bh-bg), var(--bh-card));
    box-shadow: var(--bh-shadow);
  }

  .bloghub-eyebrow {
    margin: 0 0 0.65rem;
    color: var(--bh-primary);
    font-size: 0.82rem;
    font-weight: 800;
    letter-spacing: 0.08em;
    text-transform: uppercase;
  }

  .bloghub-title {
    margin: 0;
    font-size: clamp(2rem, 5vw, 3.4rem);
    line-height: 1.05;
    font-weight: 950;
    letter-spacing: -0.045em;
  }

  .bloghub-desc {
    max-width: 720px;
    margin: 1rem 0 0;
    color: var(--bh-muted);
    font-size: 1rem;
    line-height: 1.85;
  }

  .bloghub-meta {
    display: flex;
    flex-wrap: wrap;
    gap: 0.7rem;
    margin-top: 1.35rem;
  }

  .bloghub-pill {
    display: inline-flex;
    align-items: center;
    gap: 0.45rem;
    padding: 0.48rem 0.78rem;
    border: 1px solid var(--bh-border);
    border-radius: 999px;
    background: var(--bh-card);
    color: var(--bh-muted);
    font-size: 0.86rem;
    font-weight: 700;
  }

  .bloghub-section-title {
    display: flex;
    align-items: center;
    gap: 0.75rem;
    margin: 2rem 0 1rem;
  }

  .bloghub-section-title h2 {
    margin: 0;
    font-size: 1.25rem;
    font-weight: 900;
    letter-spacing: -0.025em;
  }

  .bloghub-section-line {
    height: 1px;
    flex: 1;
    background: linear-gradient(90deg, var(--bh-border), transparent);
  }

  .bloghub-list {
    display: grid;
    gap: 1rem;
  }

  .bloghub-card {
    display: grid;
    grid-template-columns: 170px minmax(0, 1fr);
    gap: 1.15rem;
    padding: 1rem;
    border: 1px solid var(--bh-border);
    border-radius: 1.35rem;
    background: var(--bh-card);
    box-shadow: 0 12px 30px rgba(15, 23, 42, 0.045);
    transition:
      transform 180ms ease,
      border-color 180ms ease,
      box-shadow 180ms ease;
  }

  .bloghub-card:hover {
    transform: translateY(-3px);
    border-color: rgba(37, 99, 235, 0.38);
    box-shadow: var(--bh-shadow);
  }

  .bloghub-thumb {
  position: relative;
  display: block;
  min-height: 128px;
  overflow: hidden;
  border: 1px solid var(--bh-border);
  border-radius: 1rem;
  background: var(--bh-card-soft);
}

.bloghub-thumb img {
  width: 100%;
  height: 100%;
  min-height: 128px;
  aspect-ratio: 16 / 9;
  display: block;
  object-fit: cover;
  transition: transform 280ms ease;
}

.bloghub-card:hover .bloghub-thumb img {
  transform: scale(1.045);
}

  .bloghub-content {
    min-width: 0;
    display: flex;
    flex-direction: column;
    justify-content: center;
  }

  .bloghub-tags {
    display: flex;
    flex-wrap: wrap;
    gap: 0.45rem;
    margin-bottom: 0.6rem;
  }

  .bloghub-tag {
    padding: 0.26rem 0.55rem;
    border-radius: 999px;
    background: var(--bh-primary-soft);
    color: var(--bh-primary);
    font-size: 0.74rem;
    font-weight: 800;
  }

  .bloghub-card h3 {
    margin: 0;
    font-size: clamp(1.05rem, 2vw, 1.35rem);
    line-height: 1.42;
    font-weight: 900;
    letter-spacing: -0.025em;
  }

  .bloghub-card h3 a {
    color: var(--bh-text);
    text-decoration: none;
  }

  .bloghub-card h3 a:hover {
    color: var(--bh-primary);
  }

  .bloghub-summary {
    margin: 0.6rem 0 0;
    color: var(--bh-muted);
    font-size: 0.95rem;
    line-height: 1.75;
  }

  .bloghub-footer {
    display: flex;
    flex-wrap: wrap;
    align-items: center;
    justify-content: space-between;
    gap: 0.75rem;
    margin-top: 0.9rem;
  }

  .bloghub-date {
    color: var(--bh-muted);
    font-size: 0.84rem;
    font-weight: 700;
  }

  .bloghub-action {
    display: inline-flex;
    align-items: center;
    gap: 0.35rem;
    color: var(--bh-primary);
    font-size: 0.9rem;
    font-weight: 900;
    text-decoration: none;
    transition: transform 180ms ease;
  }

  .bloghub-card:hover .bloghub-action {
    transform: translateX(3px);
  }

  .bloghub-action:focus-visible,
  .bloghub-card h3 a:focus-visible {
    outline: 3px solid var(--bh-primary-soft);
    outline-offset: 4px;
    border-radius: 0.5rem;
  }

  @media (max-width: 760px) {
    .bloghub {
      padding-top: 0.5rem;
    }

    .bloghub-hero {
      padding: 1.35rem;
      border-radius: 1.25rem;
    }

    .bloghub-card {
      grid-template-columns: 1fr;
      padding: 0.85rem;
    }

    .bloghub-thumb {
      min-height: 105px;
    }
  }
</style>

<main class="bloghub not-prose" aria-labelledby="bloghub-title">
  <section class="bloghub-hero">
    <p class="bloghub-eyebrow">HackZ04 · Technical Blog</p>
    <h1 id="bloghub-title" class="bloghub-title">Blog</h1>
    <p class="bloghub-desc">
      这里整理我在深度学习、计算机视觉与大模型微调方向的技术文章，包含实验记录、参数配置、模型对比与问题排查，点击卡片即可跳转到原文阅读。
    </p>
    <div class="bloghub-meta" aria-label="文章概览">
      <span class="bloghub-pill">📚 5 Articles</span>
      <span class="bloghub-pill">🤖 Deep Learning</span>
      <span class="bloghub-pill">🎯 Computer Vision</span>
      <span class="bloghub-pill">🧪 Experiment Notes</span>
    </div>
  </section>
  <section class="bloghub-section-title" aria-hidden="true">
    <h2>Latest Articles</h2>
    <span class="bloghub-section-line"></span>
  </section>
  <section class="bloghub-list" aria-label="文章列表">
    <article class="bloghub-card">
      <a
        class="bloghub-thumb"
        href="https://blog.csdn.net/HackZ04/article/details/159461438"
        target="_blank"
        rel="noopener noreferrer"
        aria-label="阅读 FSDP 和 QDoRA 微调 Llama-3.2 调试文章"
      >
        <img
          class="nozoom"
          src="/img/blog/FSDP+QDoRA微调Llama3.png"
          alt="FSDP 和 QDoRA 微调 Llama-3.2 文章封面"
        >
      </a>
      <div class="bloghub-content">
        <div class="bloghub-tags">
          <span class="bloghub-tag">FSDP</span>
          <span class="bloghub-tag">QDoRA</span>
          <span class="bloghub-tag">Llama-3.2</span>
          <span class="bloghub-tag">大模型微调</span>
        </div>
        <h3>
          <a href="https://blog.csdn.net/HackZ04/article/details/159461438" target="_blank" rel="noopener noreferrer">
            【DEBUG】FSDP+QDoRA微调Llama-3.2时反向传播阶段梯度全为0、Loss不变的问题
          </a>
        </h3>
        <p class="bloghub-summary">
          记录了基于FSDP+QDoRA微调Llama-3.2-1B时，训练Loss始终不变、反向传播梯度全为0的问题。经分析发现，根因是Llama-3.2启用tie_word_embeddings=true后，在init_empty_weights()与load_and_quantize流程中，lm_head与embed_tokens原本共享的权重绑定被破坏，导致Loss计算图与LoRA可训练参数断开。
        </p>
        <div class="bloghub-footer">
          <span class="bloghub-date">Published · 2026.03.25</span>
          <a class="bloghub-action" href="https://blog.csdn.net/HackZ04/article/details/159461438" target="_blank" rel="noopener noreferrer" aria-label="阅读 FSDP+QDoRA 调试文章原文">
            Read Original →
          </a>
        </div>
      </div>
    </article>
    <article class="bloghub-card">
      <a
        class="bloghub-thumb"
        href="https://blog.csdn.net/HackZ04/article/details/157032378"
        target="_blank"
        rel="noopener noreferrer"
        aria-label="阅读多目标追踪模型对比文章"
      >
        <img
          class="nozoom"
          src="/img/blog/多目标追踪.png"
          alt="DeepSORT、BoTSORT、ByteTrack 和 StrongSORT 多目标追踪文章封面"
        >
      </a>
      <div class="bloghub-content">
        <div class="bloghub-tags">
          <span class="bloghub-tag">DeepSORT</span>
          <span class="bloghub-tag">ByteTrack</span>
          <span class="bloghub-tag">MOT16</span>
          <span class="bloghub-tag">目标追踪</span>
          <span class="bloghub-tag">计算机视觉</span>
        </div>
        <h3>
          <a href="https://blog.csdn.net/HackZ04/article/details/157032378" target="_blank" rel="noopener noreferrer">
            【深度学习&计算机视觉】DeepSORT、BoTSORT、ByteTrack、StrongSORT多目标追踪，参数设置、模型对比，学习必看——基于MOT16数据集
          </a>
        </h3>
        <p class="bloghub-summary">
          基于MOT16数据集，对多目标追踪算法进行原理梳理、参数设置和模型对比，适合用于目标追踪任务入门与实验复现。
        </p>
        <div class="bloghub-footer">
          <span class="bloghub-date">Published · 2026.01.16</span>
          <a class="bloghub-action" href="https://blog.csdn.net/HackZ04/article/details/157032378" target="_blank" rel="noopener noreferrer" aria-label="阅读多目标追踪文章原文">
            Read Original →
          </a>
        </div>
      </div>
    </article>
    <article class="bloghub-card">
      <a
        class="bloghub-thumb"
        href="https://blog.csdn.net/HackZ04/article/details/156983582"
        target="_blank"
        rel="noopener noreferrer"
        aria-label="阅读 YOLO 和 U-Net 实例分割文章"
      >
        <img
          class="nozoom"
          src="/img/blog/实例分割.png"
          alt="YOLO 和 U-Net 实例分割文章封面"
        >
      </a>
      <div class="bloghub-content">
        <div class="bloghub-tags">
          <span class="bloghub-tag">YOLO</span>
          <span class="bloghub-tag">U-Net</span>
          <span class="bloghub-tag">Crack-seg</span>
          <span class="bloghub-tag">实例分割</span>
          <span class="bloghub-tag">计算机视觉</span>
        </div>
        <h3>
          <a href="https://blog.csdn.net/HackZ04/article/details/156983582" target="_blank" rel="noopener noreferrer">
            【深度学习&计算机视觉】YOLO & U-Net实例分割，学习必看，参数设置、模型对比——基于YOLOv8、v11和U-Net、U-Net++的Crack-seg实例分割
          </a>
        </h3>
        <p class="bloghub-summary">
          基于Crack-seg数据集，对YOLOv8、YOLOv11、U-Net和U-Net++进行实例分割实验，并整理模型配置与对比结果。
        </p>
        <div class="bloghub-footer">
          <span class="bloghub-date">Published · 2026.01.15</span>
          <a class="bloghub-action" href="https://blog.csdn.net/HackZ04/article/details/156983582" target="_blank" rel="noopener noreferrer" aria-label="阅读实例分割文章原文">
            Read Original →
          </a>
        </div>
      </div>
    </article>
    <article class="bloghub-card">
      <a
        class="bloghub-thumb"
        href="https://blog.csdn.net/HackZ04/article/details/156947057"
        target="_blank"
        rel="noopener noreferrer"
        aria-label="阅读 YOLO 目标检测模型对比文章"
      >
        <img
          class="nozoom"
          src="/img/blog/目标检测.png"
          alt="YOLO 和 RT-DETR 目标检测文章封面"
        >
      </a>
      <div class="bloghub-content">
        <div class="bloghub-tags">
          <span class="bloghub-tag">YOLOv8</span>
          <span class="bloghub-tag">YOLOv12</span>
          <span class="bloghub-tag">RT-DETR</span>
          <span class="bloghub-tag">目标检测</span>
          <span class="bloghub-tag">计算机视觉</span>
        </div>
        <h3>
          <a href="https://blog.csdn.net/HackZ04/article/details/156947057" target="_blank" rel="noopener noreferrer">
            【深度学习&计算机视觉】YOLO目标检测，学习必看，参数设置、模型对比——基于YOLOv8、v11、v12和RT-DERT的HomeObjects-3K目标检测
          </a>
        </h3>
        <p class="bloghub-summary">
          基于HomeObjects-3K数据集，对YOLOv8、YOLOv11、YOLOv12与RT-DETR进行目标检测实验，整理超参数设置与对比分析。
        </p>
        <div class="bloghub-footer">
          <span class="bloghub-date">Published · 2026.01.14</span>
          <a class="bloghub-action" href="https://blog.csdn.net/HackZ04/article/details/156947057" target="_blank" rel="noopener noreferrer" aria-label="阅读目标检测文章原文">
            Read Original →
          </a>
        </div>
      </div>
    </article>
    <article class="bloghub-card">
      <a
        class="bloghub-thumb"
        href="https://blog.csdn.net/HackZ04/article/details/156868579"
        target="_blank"
        rel="noopener noreferrer"
        aria-label="阅读 CIFAR-100 多模型图像分类文章"
      >
        <img
          class="nozoom"
          src="/img/blog/图像分类.png"
          alt="CIFAR-100 多模型图像分类文章封面"
        >
      </a>
      <div class="bloghub-content">
        <div class="bloghub-tags">
          <span class="bloghub-tag">CIFAR-100</span>
          <span class="bloghub-tag">ResNet</span>
          <span class="bloghub-tag">ViT</span>
          <span class="bloghub-tag">图像分类</span>
          <span class="bloghub-tag">计算机视觉</span>
        </div>
        <h3>
          <a href="https://blog.csdn.net/HackZ04/article/details/156868579" target="_blank" rel="noopener noreferrer">
            【深度学习&计算机视觉】学习必看，参数设置、模型对比，Cifar100多模型图像分类——ResNet、VGG、DenseNet、ViT，附源码
          </a>
        </h3>
        <p class="bloghub-summary">
          基于CIFAR-100数据集，实现ResNet、VGG、DenseNet和Vision Transformer等图像分类模型，并进行系统对比。
        </p>
        <div class="bloghub-footer">
          <span class="bloghub-date">Published · 2026.01.12</span>
          <a class="bloghub-action" href="https://blog.csdn.net/HackZ04/article/details/156868579" target="_blank" rel="noopener noreferrer" aria-label="阅读图像分类文章原文">
            Read Original →
          </a>
        </div>
      </div>
    </article>
  </section>
</main>