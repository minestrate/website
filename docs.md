---
layout: default
title: Documentation
permalink: /docs
---

<div class="container">
  <div class="docs-layout">
    <aside class="docs-nav">
      <a href="#introduction" class="active">Introduction</a>
      <a href="#quick-start">Quick Start</a>
      <a href="#architecture">Architecture</a>
      <a href="#api-reference">API Reference</a>
    </aside>

    <article class="docs-content">
      <h1 id="introduction">Documentation</h1>
      <p>Welcome to the minestrate documentation. minestrate is an orchestration layer for Minecraft servers, allowing you to manage isolated instances through a simple REST API.</p>

      <h2 id="quick-start">Quick Start</h2>
      <p>The fastest way to get started is by using our Docker image or building from source.</p>
      
      <div class="code-block">
        <pre><span class="cmd">docker pull</span> minestrate/orchestrator
<span class="cmd">docker run</span> -p 8080:8080 minestrate/orchestrator</pre>
      </div>

      <h2 id="architecture">Architecture</h2>
      <p>minestrate uses a finite state machine to manage server lifecycles. Each server is an isolated Docker container with its own network namespace.</p>

      <h3>Server States</h3>
      <p>A server instance can be in one of the following five states:</p>
      <ul>
        <li><code>pending</code>: Initial state after creation, awaiting resources.</li>
        <li><code>starting</code>: Docker container is being created and the game server process is launching.</li>
        <li><code>running</code>: Server is healthy and accepting player connections.</li>
        <li><code>draining</code>: Server is no longer accepting new players and will stop once empty.</li>
        <li><code>stopped</code>: Resources have been released and the container has been removed.</li>
      </ul>

      <h3>Lifecycle Events</h3>
      <p>State transitions are triggered by the following events: <code>start</code>, <code>run</code>, <code>drain</code>, <code>stop</code>, and <code>timeout</code>.</p>

      <h2 id="api-reference">API Reference</h2>
      <h3>Create Server</h3>
      <div class="endpoint">
        <div class="endpoint-head">
          <span class="method post">POST</span>
          <span class="endpoint-path">/v1/servers</span>
        </div>
        <div class="endpoint-body">
          <p>Initialize a new game server instance.</p>
          <code>{ "type": "pocketmine", "version": "latest" }</code>
        </div>
      </div>
    </article>
  </div>
</div>
