---
layout: default
title: Playground
permalink: /playground
---

<div class="container">
  <div class="playground">
    <h1>Playground</h1>
    <p class="sub">Test minestrate API calls directly from your browser. This uses a sandbox environment.</p>

    <div class="code-block">
      <pre><span class="cmt">// Request</span>
<span class="cmd">POST</span> /v1/servers
{
  <span class="cmd">"image"</span>: "pocketmine-mp",
  <span class="cmd">"metadata"</span>: {
    "map": "skywars-01",
    "mode": "ranked"
  }
}

<span class="cmt">// Response</span>
<span id="response-area">{
  <span class="cmd">"id"</span>: "srv-92kd8",
  <span class="cmd">"status"</span>: "pending",
  <span class="cmd">"endpoint"</span>: "142.93.12.44:19132"
}</span></pre>
    </div>

    <button id="run-sim" class="btn btn-primary">Run Simulation</button>
  </div>
</div>

<script>
document.getElementById('run-sim').addEventListener('click', function() {
  const btn = this;
  const area = document.getElementById('response-area');
  
  btn.disabled = true;
  btn.textContent = 'Simulating...';
  
  area.style.opacity = '0.5';
  
  setTimeout(() => {
    area.innerHTML = `{
  <span class="cmd">"id"</span>: "srv-92kd8",
  <span class="cmd">"status"</span>: "starting",
  <span class="cmd">"endpoint"</span>: "142.93.12.44:19132"
}`;
    area.style.opacity = '1';
  }, 1000);

  setTimeout(() => {
    area.innerHTML = `{
  <span class="cmd">"id"</span>: "srv-92kd8",
  <span class="cmd">"status"</span>: "running",
  <span class="cmd">"endpoint"</span>: "142.93.12.44:19132"
}`;
    btn.disabled = false;
    btn.textContent = 'Run Simulation';
  }, 2500);
});
</script>
