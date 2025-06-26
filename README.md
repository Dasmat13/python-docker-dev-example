## Simple python docker dev example for the official docker docs
for link : https://dasmat13.github.io/python-docker-dev-example/#overview
https://docs.docker.com/language/python/develop/
<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <title>Python Docker Dev Example - Setup Guide</title>
  <style>
    body {
      font-family: Arial, sans-serif;
      max-width: 960px;
      margin: auto;
      padding: 2rem;
      background-color: #f4f4f4;
      color: #333;
    }
    h1, h2, h3 {
      color: #2c3e50;
    }
    pre {
      background-color: #2d2d2d;
      color: #f8f8f2;
      padding: 1em;
      border-radius: 6px;
      position: relative;
      overflow-x: auto;
    }
    code {
      font-family: monospace;
    }
    .copy-button {
      position: absolute;
      top: 10px;
      right: 10px;
      background: #007bff;
      color: #fff;
      border: none;
      padding: 4px 8px;
      border-radius: 4px;
      cursor: pointer;
    }
    .copy-button:hover {
      background: #0056b3;
    }
  </style>
</head>
<body>
  <h1>🚀 Python Docker Dev Example - Setup Guide</h1>

  <p>This guide helps you get started with cloning, running, and deploying this FastAPI + PostgreSQL project using Docker and Kubernetes.</p>

  <h2>📦 Clone the Repository</h2>
  <pre><button class="copy-button" onclick="copyText(this)">Copy</button><code>git clone https://github.com/your-username/python-docker-dev-example.git
cd python-docker-dev-example</code></pre>

  <h2>⚙️ Requirements</h2>
  <ul>
    <li>Python 3.12+</li>
    <li>Docker & Docker Compose</li>
    <li>kubectl & Kubernetes cluster (e.g. Minikube)</li>
  </ul>

  <h2>🐳 Run Locally Using Docker Compose</h2>
  <pre><button class="copy-button" onclick="copyText(this)">Copy</button><code>docker compose up --build</code></pre>

  <h3>✅ Verify the App</h3>
  <pre><button class="copy-button" onclick="copyText(this)">Copy</button><code>curl http://localhost:8001/</code></pre>

  <h2>🧼 Lint and Type Check</h2>
  <pre><button class="copy-button" onclick="copyText(this)">Copy</button><code>pip install -r requirements.txt
pip install pre-commit pyright
pre-commit install
pre-commit run --all-files
pyright</code></pre>

  <h2>☸️ Deploy to Kubernetes</h2>
  <h3>1. Apply Kubernetes Manifest</h3>
  <pre><button class="copy-button" onclick="copyText(this)">Copy</button><code>kubectl apply -f docker-postgres-kubernetes.yaml</code></pre>

  <h3>2. Get Services</h3>
  <pre><button class="copy-button" onclick="copyText(this)">Copy</button><code>kubectl get services</code></pre>

  <h3>3. Get Node Internal IP</h3>
  <pre><button class="copy-button" onclick="copyText(this)">Copy</button><code>kubectl get nodes -o wide</code></pre>

  <h3>4. Access the App (NodePort)</h3>
  <pre><button class="copy-button" onclick="copyText(this)">Copy</button><code>curl http://&lt;INTERNAL-IP&gt;:30001/</code></pre>

  <h3>📍 Or Use Port Forwarding</h3>
  <pre><button class="copy-button" onclick="copyText(this)">Copy</button><code>kubectl port-forward service/service-entrypoint 8001:8001
curl http://localhost:8001/</code></pre>

  <h2>🚑 Troubleshooting</h2>
  <ul>
    <li>❌ <code>curl localhost:30001</code> fails: check pod logs</li>
    <li>❌ <code>kubectl apply</code> error: context not set — use <code>kubectl config use-context</code> or start cluster</li>
  </ul>

  <h2>🗂 Project Structure</h2>
  <pre><code>.
├── app.py
├── config.py
├── Dockerfile
├── compose.yaml
├── docker-postgres-kubernetes.yaml
├── requirements.txt
├── .pre-commit-config.yaml</code></pre>

  <h2>📜 License</h2>
  <p>MIT</p>

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
