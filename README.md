# bootCAMP-TI
<!DOCTYPE html>
<html lang="pt-BR">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>Guia de Instalação - WSL + Docker + Playwright</title>
  <style>
    body {
      font-family: 'Segoe UI', Tahoma, Geneva, Verdana, sans-serif;
      background-color: #0f172a;
      color: #e2e8f0;
      margin: 0;
      padding: 0;
      line-height: 1.6;
    }
    header {
      background: #1e293b;
      padding: 20px;
      text-align: center;
      border-bottom: 2px solid #38bdf8;
    }
    header h1 {
      color: #38bdf8;
      margin: 0;
    }
    main {
      max-width: 900px;
      margin: 40px auto;
      background: #1e293b;
      padding: 30px;
      border-radius: 12px;
      box-shadow: 0 0 20px rgba(0,0,0,0.4);
    }
    h2 {
      color: #38bdf8;
      border-bottom: 1px solid #334155;
      padding-bottom: 5px;
    }
    code, pre {
      background: #0f172a;
      color: #38bdf8;
      border-radius: 6px;
      padding: 10px;
      display: block;
      overflow-x: auto;
      font-size: 14px;
    }
    ol, ul {
      margin-left: 20px;
    }
    a {
      color: #38bdf8;
      text-decoration: none;
    }
    a:hover {
      text-decoration: underline;
    }
    footer {
      text-align: center;
      padding: 20px;
      color: #94a3b8;
      border-top: 1px solid #334155;
      margin-top: 40px;
    }
  </style>
</head>
<body>
  <header>
    <h1>Guia de Instalação — WSL, Docker e Playwright</h1>
    <p>Ambiente de testes automatizados para Extensão Chrome (Entrega II)</p>
  </header>
  <main>
    <section>
      <h2>1️⃣ Instalar o WSL (Windows Subsystem for Linux)</h2>
      <p>Abra o <strong>PowerShell como Administrador</strong> e execute:</p>
      <pre><code>wsl --install</code></pre>
      <p>Isso instala o WSL2 e uma distribuição Linux (geralmente Ubuntu).</p>
      <p>Após a instalação, reinicie o computador.</p>
    </section>

    <section>
      <h2>2️⃣ Verificar a instalação</h2>
      <pre><code>wsl --status</code></pre>
      <p>Deve exibir algo como:</p>
      <pre><code>Default Version: 2
Default Distro: Ubuntu</code></pre>
      <p>Se não houver Ubuntu, instale manualmente:</p>
      <pre><code>wsl --install -d Ubuntu</code></pre>
    </section>

    <section>
      <h2>3️⃣ Atualizar e preparar o ambiente Linux</h2>
      <p>Abra o Ubuntu (via menu Iniciar ou comando <code>wsl</code>) e rode:</p>
      <pre><code>sudo apt update && sudo apt upgrade -y</code></pre>
      <p>Depois instale o Node.js e npm:</p>
      <pre><code>sudo apt install -y nodejs npm</code></pre>
      <p>Verifique as versões:</p>
      <pre><code>node -v
npm -v</code></pre>
    </section>

    <section>
      <h2>4️⃣ Instalar o Docker Desktop (Windows)</h2>
      <p>Baixe em: <a href="https://www.docker.com/products/docker-desktop/" target="_blank">docker.com/products/docker-desktop</a></p>
      <p>Durante a instalação, ative a opção:</p>
      <pre><code>✅ Use the WSL 2 based engine</code></pre>
      <p>Depois teste dentro do WSL:</p>
      <pre><code>docker --version
docker compose version</code></pre>
    </section>

    <section>
      <h2>5️⃣ Clonar e rodar o projeto</h2>
      <pre><code>cd ~
git clone https://github.com/seu-usuario/my-chrome-extension.git
cd my-chrome-extension
docker compose build
docker compose run --rm e2e</code></pre>
      <p>Para abrir o relatório do Playwright:</p>
      <pre><code>npx playwright show-report</code></pre>
    </section>

    <section>
      <h2>6️⃣ Abrir o projeto no VS Code</h2>
      <p>Com o WSL aberto, digite:</p>
      <pre><code>code .</code></pre>
      <p>Certifique-se de ter a extensão <strong>“Remote - WSL”</strong> instalada no VS Code.</p>
    </section>

    <section>
      <h2>✅ Tudo pronto!</h2>
      <p>Agora seu ambiente está preparado para executar:</p>
      <ul>
        <li>Testes E2E do Playwright</li>
        <li>Build da extensão Chrome</li>
        <li>Execução em container Docker</li>
        <li>Pipeline no GitHub Actions</li>
      </ul>
    </section>
  </main>  <footer>
    <p>Guia técnico desenvolvido para automatização da Entrega II — Prof. Romes • Bootcamp CEUB</p>
  </footer>
</body>
</html>
