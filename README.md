<!DOCTYPE html><html lang="es">
<head>
  <meta charset="UTF-8" />
  <meta name="viewport" content="width=device-width, initial-scale=1.0" />
  <title>HTTP Injector Pro — BerMatMods</title>
  <link rel="stylesheet" href="style.css" />
</head>
<body>
  <!-- Pantalla de bienvenida -->
  <div class="splash" id="splash">
    <h1 class="logo">⚡ HTTP Injector Pro ⚡</h1>
    <p class="sub">By BerMatMods</p>
  </div>  <!-- Barra superior -->  <header>
    <h2>HTTP Injector — BerMatMods</h2>
    <nav>
      <button id="btnSettings">⚙️ Configuración</button>
      <button id="btnHelp">❓ Ayuda</button>
    </nav>
  </header>  <!-- Contenido principal -->  <main>
    <section class="connection">
      <h3>Configuración de Conexión</h3>
      <label>Payload:
        <textarea id="payload" placeholder="Ejemplo: CONNECT [host_port] HTTP/1.1\nHost: [host]" rows="4"></textarea>
      </label>
      <label>Host / SNI:
        <input type="text" id="host" placeholder="www.example.com" />
      </label>
      <label>Puerto:
        <input type="number" id="port" placeholder="443" />
      </label>
      <label>Método:
        <select id="method">
          <option>SSL/TLS</option>
          <option>HTTP Proxy</option>
          <option>SSH</option>
          <option>Directo</option>
        </select>
      </label>
      <div class="buttons">
        <button id="startBtn">🚀 Iniciar</button>
        <button id="stopBtn">⛔ Detener</button>
        <button id="importBtn">📂 Importar</button>
        <button id="exportBtn">💾 Exportar</button>
      </div>
    </section><!-- Logs -->
<section class="logs">
  <h3>Registros de Conexión</h3>
  <div id="logOutput" class="log-output"></div>
</section>

<!-- Monitor -->
<section class="monitor">
  <h3>Monitor de tráfico</h3>
  <div id="trafficMonitor" class="monitor-box"></div>
</section>

  </main>  <!-- Footer -->  <footer>
    <p>© 2025 ⚡BerMatMods — HTTP Injector Clone</p>
  </footer>  <script src="app.js"></script></body>
</html>/* ===================== style.css ===================== */ body { margin: 0; font-family: "Russo One", sans-serif; background: #0c0f14; color: #e0e0e0; }

header { display: flex; justify-content: space-between; align-items: center; padding: 10px; background: #111; border-bottom: 2px solid #0ff; }

header h2 { color: #0ff; }

nav button { margin-left: 5px; padding: 5px 10px; border: none; background: #0ff; color: #000; cursor: pointer; border-radius: 5px; }

main { padding: 20px; }

section { margin-bottom: 25px; background: #1a1f26; padding: 15px; border-radius: 10px; box-shadow: 0 0 10px rgba(0, 255, 255, 0.3); }

label { display: block; margin: 10px 0; }

input, textarea, select { width: 100%; padding: 8px; background: #111; color: #0ff; border: 1px solid #0ff; border-radius: 5px; }

.buttons button { margin: 5px; padding: 10px; background: #0ff; border: none; border-radius: 5px; cursor: pointer; }

.log-output { height: 200px; overflow-y: auto; background: #000; padding: 10px; border: 1px solid #0ff; font-family: monospace; font-size: 14px; color: #0f0; }

.monitor-box { height: 150px; background: #000; color: #0f0; border: 1px solid #0ff; overflow-y: auto; padding: 10px; font-family: monospace; }

.splash { position: fixed; top: 0; left: 0; width: 100%; height: 100%; background: #000; display: flex; flex-direction: column; justify-content: center; align-items: center; z-index: 9999; }

.splash .logo { font-size: 32px; color: #0ff; animation: pulse 2s infinite; }

.splash .sub { color: #aaa; margin-top: 10px; }

@keyframes pulse { 0% { transform: scale(1); opacity: 1; } 50% { transform: scale(1.1); opacity: 0.7; } 100% { transform: scale(1); opacity: 1; } }

/* ===================== app.js ===================== */ window.addEventListener("load", () => { const splash = document.getElementById("splash"); setTimeout(() => splash.style.display = "none", 2500); });

const logOutput = document.getElementById("logOutput"); const trafficMonitor = document.getElementById("trafficMonitor");

function addLog(message) { const time = new Date().toLocaleTimeString(); logOutput.innerHTML += [${time}] ${message}<br/>; logOutput.scrollTop = logOutput.scrollHeight; }

function addTraffic(data) { trafficMonitor.innerHTML += ${data}<br/>; trafficMonitor.scrollTop = trafficMonitor.scrollHeight; }

document.getElementById("startBtn").addEventListener("click", () => { addLog("Iniciando conexión..."); setTimeout(() => addLog("Conexión establecida con éxito ✅"), 2000); setInterval(() => addTraffic("[DATA] Packet -> 192.168.1." + Math.floor(Math.random()*255)), 1000); });

document.getElementById("stopBtn").addEventListener("click", () => { addLog("Conexión detenida ❌"); });

document.getElementById("importBtn").addEventListener("click", () => { addLog("Archivo de configuración importado"); });

document.getElementById("exportBtn").addEventListener("click", () => { addLog("Configuración exportada"); });

