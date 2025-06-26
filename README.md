## Simple python docker dev example for the official docker docs
for link : https://dasmat13.github.io/python-docker-dev-example/#overview
https://docs.docker.com/language/python/develop/
<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8" />
  <meta name="viewport" content="width=device-width, initial-scale=1.0"/>
  <title>Python Docker Dev Example Documentation</title>
  <style>
    body {
      display: flex;
      font-family: 'Segoe UI', Tahoma, Geneva, Verdana, sans-serif;
      margin: 0;
      background-color: #f4f4f4;
    }
    nav {
      min-width: 240px;
      background: #2c3e50;
      padding: 20px;
      height: 100vh;
      position: sticky;
      top: 0;
      color: white;
    }
    nav h2 {
      color: #ecf0f1;
    }
    nav a {
      display: block;
      color: #bdc3c7;
      text-decoration: none;
      margin: 10px 0;
    }
    nav a:hover {
      color: #ffffff;
    }
    main {
      flex-grow: 1;
      padding: 2rem;
      background-color: #ffffff;
      overflow: auto;
    }
    h1, h2, h3 {
      color: #2c3e50;
    }
    .cmd {
      background: #2d2d2d;
      color: #f8f8f2;
      padding: 0.8em 1em;
      border-radius: 8px;
      overflow-x: auto;
      margin-bottom: 1em;
      position: relative;
    }
    .copy-button {
      position: absolute;
      top: 8px;
      right: 8px;
      background: #007bff;
      color: white;
      border: none;
      padding: 4px 8px;
      font-size: 12px;
      border-radius: 4px;
      cursor: pointer;
    }
    .copy-button:hover {
      background: #0056b3;
    }
  </style>
</head>
<body>

<nav>
  <h2>Documentation</h2>
  <a href="#overview">Overview</a>
  <a href="#features">Features</a>
  <a href="#requirements">Requirements</a>
  <a href="#docker">Docker</a>
  <a href="#lint">Lint & Type Check</a>
  <a href="#kubernetes">Kubernetes</a>
  <a href="#troubleshooting">Troubleshooting</a>
  <a href="#structure">Project Structure</a>
  <a href="#output">Output</a>
</nav>

<main>
<h1 id="overview">Python Docker Dev Example</h1>
<p>This is a FastAPI + PostgreSQL app with Docker and Kubernetes support, useful for DevOps learning and containerized deployments.</p>

<h2 id="features">💡 Features</h2>
<ul>
  <li>FastAPI backend</li>
  <li>PostgreSQL with Docker</li>
  <li>Docker Compose for local dev</li>
  <li>Kubernetes deployment manifests</li>
  <li>Pre-commit + pyright integration</li>
</ul>

<h2 id="requirements">⚙️ Requirements</h2>
<ul>
  <li>Docker & Docker Compose</li>
  <li>Python 3.12+</li>
  <li>Kubectl & Kubernetes cluster (e.g., Minikube)</li>
</ul>

<h2 id="docker">🚀 Docker Commands</h2>
<div class="cmd"><button class="copy-button" onclick="copyText(this)">Copy</button><code>docker compose up --build</code></div>
<div class="cmd"><button class="copy-button" onclick="copyText(this)">Copy</button><code>curl http://localhost:8001/</code></div>

<h2 id="lint">🧪 Lint & Type Check</h2>
<div class="cmd"><button class="copy-button" onclick="copyText(this)">Copy</button><code>pip install -r requirements.txt</code></div>
<div class="cmd"><button class="copy-button" onclick="copyText(this)">Copy</button><code>pip install pre-commit pyright</code></div>
<div class="cmd"><button class="copy-button" onclick="copyText(this)">Copy</button><code>pre-commit install</code></div>
<div class="cmd"><button class="copy-button" onclick="copyText(this)">Copy</button><code>pre-commit run --all-files</code></div>
<div class="cmd"><button class="copy-button" onclick="copyText(this)">Copy</button><code>pyright</code></div>

<h2 id="kubernetes">⚖️ Kubernetes Deployment</h2>
<div class="cmd"><button class="copy-button" onclick="copyText(this)">Copy</button><code>kubectl apply -f docker-postgres-kubernetes.yaml</code></div>
<div class="cmd"><button class="copy-button" onclick="copyText(this)">Copy</button><code>kubectl get services</code></div>
<div class="cmd"><button class="copy-button" onclick="copyText(this)">Copy</button><code>kubectl get nodes -o wide</code></div>
<div class="cmd"><button class="copy-button" onclick="copyText(this)">Copy</button><code>curl http://&lt;INTERNAL-IP&gt;:30001/</code></div>
<div class="cmd"><button class="copy-button" onclick="copyText(this)">Copy</button><code>kubectl port-forward service/service-entrypoint 8001:8001</code></div>
<div class="cmd"><button class="copy-button" onclick="copyText(this)">Copy</button><code>curl http://localhost:8001/</code></div>

<h2 id="troubleshooting">⚠️ Troubleshooting</h2>
<ul>
  <li><b>Can't connect?</b> Check pod logs and NodePort</li>
  <li><b>kubectl error?</b> Use <code>kubectl config use-context</code> or <code>minikube start</code></li>
</ul>

<h2 id="structure">🚜 Project Structure</h2>
<pre><code>.
├── app.py
├── config.py
├── Dockerfile
├── compose.yaml
├── docker-postgres-kubernetes.yaml
├── requirements.txt
├── .pre-commit-config.yaml</code></pre>

<h2 id="output">🌟 Output</h2>
<pre><code>Hello, Docker!!!</code></pre>
</main>

<script>
function copyText(button) {
  const code = button.nextElementSibling.innerText;
  navigator.clipboard.writeText(code).then(() => {
    button.innerText = 'Copied!';
    setTimeout(() => button.innerText = 'Copy', 2000);
  });
}
</script>

</body>
</html>

