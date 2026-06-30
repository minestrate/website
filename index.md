---
layout: default
title: Home
permalink: /
---

<section class="hero">
  <div class="container">
    <div class="hero-badge">open source · go · docker</div>
    <h1>mine<span class="accent">strate</span></h1>
    <p>Spin up isolated Minecraft minigame servers on demand via REST. One POST creates a PocketMine-MP server with its own network, port, and lifecycle.</p>
    <div class="hero-actions">
      <a href="https://github.com/minestrate/orchestrator" class="btn btn-primary">View on GitHub</a>
      <a href="{{ '/docs' | relative_url }}" class="btn">Documentation</a>
      <a href="{{ '/playground' | relative_url }}" class="btn">Playground</a>
    </div>

    <div class="code-block">
      <pre><span class="cmt"># clone and run</span>
<span class="cmd">git clone</span> https://github.com/minestrate/orchestrator
<span class="cmd">cd</span> orchestrator
<span class="cmd">go build</span> -o minestrate ./cmd/minestrate
<span class="cmd">./minestrate</span> --config config.example.yaml</pre>
    </div>
  </div>
</section>

<section class="features">
  <div class="container">
    <h2>How it works</h2>
    <div class="feature-grid">
      <div class="feature-card">
        <div class="feature-icon">⟳</div>
        <h3>Finite state machine</h3>
        <p>Every server goes through five states. Transitions are the only mutation allowed — invalid ones return 409.</p>
      </div>
      <div class="feature-card">
        <div class="feature-icon">⊕</div>
        <h3>Port injection</h3>
        <p>Ports are allocated via atomic CAS on a bitset. Two servers can never share a port by construction.</p>
      </div>
      <div class="feature-card">
        <div class="feature-icon">◫</div>
        <h3>Network isolation</h3>
        <p>Each container gets a dedicated /28 subnet. Game servers cannot reach each other unless explicitly routed.</p>
      </div>
      <div class="feature-card">
        <div class="feature-icon">◎</div>
        <h3>M/M/c worker pool</h3>
        <p>Worker count is derived from queueing theory. Utilisation stays below 0.8 to keep wait times bounded.</p>
      </div>
    </div>
  </div>
</section>

<section class="repos">
  <div class="container">
    <h2>The stack</h2>
    <p class="repos-sub">minestrate is an organization — each piece has its own repo.</p>
    <div class="repo-list">
      <a href="https://github.com/minestrate/orchestrator" class="repo-item">
        <span class="repo-dot" style="background:#1D9E75"></span>
        <span class="repo-name">orchestrator</span>
        <span class="repo-desc">Core REST API — Docker lifecycle management</span>
        <span class="repo-tag tag-core">core</span>
      </a>
      <a href="https://github.com/minestrate/php-client" class="repo-item">
        <span class="repo-dot" style="background:#378ADD"></span>
        <span class="repo-name">php-client</span>
        <span class="repo-desc">PHP client for minestrate, especially for @pmmp</span>
        <span class="repo-tag tag-plugin">plugin</span>
      </a>
      <a href="https://github.com/minestrate/go-client" class="repo-item">
        <span class="repo-dot" style="background:#378ADD"></span>
        <span class="repo-name">go-client</span>
        <span class="repo-desc">Golang client for minestrate, especially for @df-mc</span>
        <span class="repo-tag tag-plugin">plugin</span>
      </a>
      <a href="https://github.com/minestrate/testenv" class="repo-item">
        <span class="repo-dot" style="background:#888780"></span>
        <span class="repo-name">testenv</span>
        <span class="repo-desc">Reproducible test environment for the minestrate stack</span>
        <span class="repo-tag tag-test">test</span>
      </a>
    </div>
  </div>
</section>