<!DOCTYPE html>
<html lang="es">
<head>
  <meta charset="UTF-8" />
  <meta name="viewport" content="width=device-width, initial-scale=1.0"/>
  <title>BerMat_Mods - By AnthZz Berrocal</title>

  <!-- Google Fonts (permitidas en GitHub Pages) -->
  <link href="https://fonts.googleapis.com/css2?family=Poppins:wght@400;500;600;700&family=Roboto+Mono:wght@300;400;500&display=swap" rel="stylesheet">

  <style>
    * {
      margin: 0;
      padding: 0;
      box-sizing: border-box;
    }

    body {
      font-family: 'Poppins', sans-serif;
      background: #0d0d10;
      color: #e0e0e0;
      line-height: 1.6;
    }

    .container {
      max-width: 520px;
      margin: 20px auto;
      background: #121216;
      min-height: 100vh;
      border-radius: 18px;
      overflow: hidden;
      box-shadow: 0 12px 36px rgba(0, 0, 0, 0.6);
      border: 1px solid #2c2c34;
    }

    /* Encabezado */
    header {
      background: linear-gradient(140deg, #16162a, #1a2238);
      padding: 28px;
      text-align: center;
      border-bottom: 1px solid #333;
    }

    header .logo {
      font-size: 3.2rem;
      margin-bottom: 10px;
    }

    header h1 {
      font-size: 2.1rem;
      color: #4ade80;
      font-weight: 700;
      letter-spacing: -1px;
      text-shadow: 0 0 8px rgba(74, 222, 128, 0.3);
    }

    header p {
      font-size: 1.1rem;
      color: #a3e635;
      margin-top: 6px;
    }

    /* Estado de conexión */
    .status-box {
      padding: 20px;
      background: #1a1a20;
      display: flex;
      justify-content: space-between;
      align-items: center;
      border-bottom: 1px solid #333;
    }

    #status-text {
      font-size: 1.3rem;
      font-weight: 600;
      color: #f87171;
    }

    .btn-connect {
      padding: 14px 28px;
      background: #4ade80;
      color: #000;
      border: none;
      border-radius: 12px;
      font-weight: 600;
      cursor: pointer;
      transition: all 0.3s ease;
      font-family: 'Poppins', sans-serif;
      font-size: 1.1rem;
    }

    .btn-connect:hover {
      background: #22c55e;
      transform: translateY(-2px);
      box-shadow: 0 8px 20px rgba(34, 197, 94, 0.5);
    }

    .btn-connect.disconnect {
      background: #f87171;
      color: white;
    }

    .btn-connect.disconnect:hover {
      background: #ef4444;
    }

    /* Pestañas */
    .tabs {
      display: flex;
      background: #1c1c24;
    }

    .tab {
      flex: 1;
      padding: 18px;
      background: none;
      border: none;
      color: #a0aec0;
      font-size: 1.05rem;
      cursor: pointer;
      transition: 0.3s ease;
      font-family: 'Poppins', sans-serif;
    }

    .tab.active {
      color: #4ade80;
      font-weight: 600;
      border-bottom: 3px solid #4ade80;
    }

    /* Contenido */
    .content {
      padding: 24px;
      min-height: 300px;
      background: #14141a;
    }

    .panel {
      display: none;
    }

    .panel.active {
      display: block;
    }

    /* Información */
    .info-grid {
      display: grid;
      grid-template-columns: 1fr 1fr;
      gap: 18px;
      margin-top: 18px;
    }

    .info-item {
      background: #1e1e28;
      padding: 16px;
      border-radius: 12px;
      font-size: 1.05rem;
    }

    .info-item label {
      display: block;
      font-size: 0.9rem;
      color: #9fa6b2;
      margin-bottom: 6px;
    }

    /* Logs */
    .log-output {
      background: #0d1117;
      border: 1px solid #30363d;
      border-radius: 12px;
      padding: 16px;
      height: 320px;
      overflow-y: auto;
      font-family: 'Roboto Mono', monospace;
      font-size: 0.85rem;
      color: #c9d1d9;
      line-height: 1.5;
    }

    .log-entry {
      margin: 5px 0;
      opacity: 0.94;
      word-wrap: break-word;
    }

    .log-entry strong {
      color: #4ade80;
    }

    /* Config */
    .file-input {
      margin: 14px 0;
      width: 100%;
    }

    .config-info {
      font-size: 0.85rem;
      color: #9ca3af;
      margin: 8px 0;
    }

    .btn-import {
      padding: 11px 18px;
      background: #6366f1;
      color: white;
      border: none;
      border-radius: 7px;
      cursor: pointer;
      font-family: 'Poppins', sans-serif;
    }

    .btn-import:hover {
      background: #4f46e5;
    }

    .server-info {
      margin: 18px 0;
    }

    .server-info label {
      display: block;
      font-size: 0.95rem;
      color: #e0e0e0;
      margin-bottom: 7px;
    }

    .server-info input {
      width: 100%;
      padding: 11px;
      background: #1e1e28;
      border: 1px solid #444;
      color: white;
      border-radius: 7px;
      font-family: 'Roboto Mono', monospace;
      font-size: 0.95rem;
    }

    /* Acerca de */
    .credit-box {
      margin: 24px 0;
      padding: 20px;
      background: #1a2e12;
      border-radius: 14px;
      text-align: center;
      border: 1px dashed #4ade80;
    }

    .credit-box h3 {
      color: #4ade80;
      font-size: 1.5rem;
      margin: 12px 0;
      text-shadow: 0 0 6px rgba(74, 222, 128, 0.4);
    }

    .credit-box .tag {
      font-style: italic;
      color: #a3e635;
      font-size: 1rem;
    }

    .disclaimer {
      font-size: 0.85rem;
      color: #6b7280;
      margin-top: 20px;
      font-style: italic;
    }

    /* Footer */
    footer {
      text-align: center;
      padding: 20px;
      background: #101014;
      font-size: 0.85rem;
      color: #6b7280;
      border-top: 1px solid #2a2a30;
    }

    footer strong {
      color: #4ade80;
    }
  </style>
</head>
<body>
  <div class="container">
    <!-- Encabezado -->
    <header>
      <div class="logo">⚡</div>
      <h1>BerMat_Mods</h1>
      <p>By <strong>AnthZz Berrocal</strong></p>
    </header>

    <!-- Estado -->
    <div class="status-box">
      <span id="status-text">🔴 Desconectado</span>
      <button id="connect-btn" class="btn-connect">Conectar</button>
    </div>

    <!-- Pestañas -->
    <div class="tabs">
      <button class="tab active" data-tab="home">Inicio</button>
      <button class="tab" data-tab="logs">Reg. Conexión</button>
      <button class="tab" data-tab="config">Config</button>
      <button class="tab" data-tab="about">Acerca de</button>
    </div>

    <!-- Contenido -->
    <div class="content">
      <!-- Inicio -->
      <div class="panel active" id="home">
        <div class="info-grid">
          <div class="info-item">
            <label>IP Pública</label>
            <span id="public-ip">-</span>
          </div>
          <div class="info-item">
            <label>IP Local</label>
            <span>192.168.1.100</span>
          </div>
          <div class="info-item">
            <label>Latencia</label>
            <span id="latency">-- ms</span>
          </div>
          <div class="info-item">
            <label>Protocolo</label>
            <span>SSH + SSL</span>
          </div>
        </div>
      </div>

      <!-- Logs -->
      <div class="panel" id="logs">
        <h2>Registro de Conexión</h2>
        <div id="log-output" class="log-output"></div>
      </div>

      <!-- Config -->
      <div class="panel" id="config">
        <h2>Importar Configuración</h2>
        <input type="file" class="file-input" />
        <p class="config-info">Soporta: .txt, .conf, .json</p>
        <button class="btn-import">Importar Archivo</button>
        <div class="server-info">
          <label>Servidor:</label>
          <input type="text" value="server.anthzz.net" readonly />
        </div>
        <div class="server-info">
          <label>Puerto:</label>
          <input type="number" value="443" />
        </div>
      </div>

      <!-- Acerca de -->
      <div class="panel" id="about">
        <h2>Acerca de BerMat_Mods</h2>
        <p>Simulador de conexión avanzada desarrollado con fines educativos y artísticos.</p>
        <div class="credit-box">
          <p>✨ Creado por:</p>
          <h3>AnthZz Berrocal</h3>
          <p class="tag">"El futuro de la red está en tus manos."</p>
        </div>
        <p class="disclaimer">
          Esta app <strong>no realiza conexiones reales</strong>. Diseño inspirado en herramientas de red.
        </p>
      </div>
    </div>

    <!-- Footer -->
    <footer>
      <p>© 2025 BerMat_Mods | Desarrollado con orgullo por <strong>AnthZz Berrocal</strong></p>
    </footer>
  </div>

  <script>
    const connectBtn = document.getElementById('connect-btn');
    const statusText = document.getElementById('status-text');
    const logOutput = document.getElementById('log-output');
    const publicIp = document.getElementById('public-ip');
    const latency = document.getElementById('latency');

    let isConnected = false;
    let logCount = 0;

    // Añadir log con icono
    function addLog(message, type = 'info') {
      const now = new Date();
      const time = now.toTimeString().substr(0, 8);
      const entry = document.createElement('p');
      entry.className = 'log-entry';

      const icons = {
        info: '🔵',
        warn: '🟡',
        error: '🔴',
        success: '✅',
        auth: '🔑',
        tunnel: '🚇',
        net: '📡',
        sys: '⚙️'
      };

      const icon = icons[type] || '🟢';
      entry.innerHTML = `[${time}] ${icon} ${message}`;
      logOutput.appendChild(entry);
      logOutput.scrollTop = logOutput.scrollHeight;
      logCount++;
    }

    // Simular latencia
    function simulateLatency() {
      const ms = Math.floor(Math.random() * 60) + 35;
      latency.textContent = `${ms} ms`;
    }

    // Inicializar logs (más de 30 entradas realistas)
    function initLogs() {
      setTimeout(() => addLog("Iniciando BerMat_Mods v1.2.1...", "sys"), 200);
      setTimeout(() => addLog("Cargando kernel de red...", "sys"), 500);
      setTimeout(() => addLog("Verificando archivos del sistema...", "sys"), 800);
      setTimeout(() => addLog("✅ Todos los módulos cargados correctamente.", "success"), 1100);
      setTimeout(() => addLog("👤 Usuario: AnthZz Berrocal", "info"), 1400);
      setTimeout(() => addLog("🔒 Permisos de root: GRANTED", "warn"), 1700);
      setTimeout(() => addLog("📡 Servidor: server.anthzz.net:443", "info"), 2000);
      setTimeout(() => addLog("🔐 Protocolo: SSH + SSL Tunnel", "info"), 2300);
      setTimeout(() => addLog("🛡️ Firewall: Activo (Modo Stealth)", "info"), 2600);
      setTimeout(() => addLog("🌐 Modo: Full Bypass", "info"), 2900);
      setTimeout(() => addLog("🔄 DNS personalizado: 1.1.1.1 + 8.8.8.8", "info"), 3200);
      setTimeout(() => addLog("📦 Paquetes inyectados: 3/3 (OK)", "success"), 3500);
      setTimeout(() => addLog("📌 Listo para conexión segura.", "info"), 3800);
    }

    // Conectar
    connectBtn.addEventListener('click', () => {
      if (!isConnected) {
        connectBtn.textContent = 'Conectando...';
        connectBtn.disabled = true;
        statusText.textContent = '🟡 Conectando...';
        statusText.style.color = '#fbbf24';

        addLog("🚀 Iniciando secuencia de conexión...", "info");

        setTimeout(() => addLog("📡 Resolviendo IP del servidor...", "net"), 1000);
        setTimeout(() => addLog("✅ IP resuelta: 104.21.80.123", "success"), 1400);

        setTimeout(() => addLog("🔐 Enviando clave SSH...", "auth"), 1800);
        setTimeout(() => addLog("✅ Clave aceptada por el servidor.", "success"), 2200);

        setTimeout(() => addLog("🚇 Estableciendo túnel SSL...", "tunnel"), 2600);
        setTimeout(() => addLog("🔄 Negociando cifrado TLS 1.3...", "info"), 3000);

        setTimeout(() => addLog("✅ Túnel SSL establecido con éxito.", "success"), 3500);
        setTimeout(() => addLog("🛡️ IP oculta. Modo anónimo activado.", "warn"), 3800);

        setTimeout(() => addLog("🌐 Asignando IP virtual: 186.23.112.89", "info"), 4100);
        publicIp.textContent = "186.23.112.89";

        setTimeout(() => addLog("📶 Probando latencia...", "info"), 4400);
        setTimeout(() => {
          simulateLatency();
          addLog(`📶 Latencia: ${latency.textContent}`, "info");
        }, 4700);

        setTimeout(() => addLog("🔄 Inyectando paquetes de red...", "info"), 5000);
        setTimeout(() => addLog("✅ Inyección completa. Todo listo.", "success"), 5400);

        setTimeout(() => {
          isConnected = true;
          connectBtn.textContent = 'Desconectar';
          connectBtn.classList.add('disconnect');
          connectBtn.disabled = false;
          statusText.textContent = '🟢 Conectado';
          statusText.style.color = '#4ade80';
          addLog("✅ CONEXIÓN ESTABLECIDA. Todo operativo.", "success");
          addLog("👤 Usuario activo: <strong>AnthZz Berrocal</strong>", "info");
        }, 5800);

      } else {
        isConnected = false;
        connectBtn.textContent = 'Conectar';
        connectBtn.classList.remove('disconnect');
        connectBtn.disabled = false;
        statusText.textContent = '🔴 Desconectado';
        statusText.style.color = '#f87171';
        publicIp.textContent = '-';
        latency.textContent = '-- ms';

        addLog("🔴 Desconectando túnel seguro...", "error");
        setTimeout(() => addLog("🚇 Cerrando túnel SSL...", "tunnel"), 300);
        setTimeout(() => addLog("🛡️ Restaurando firewall predeterminado...", "info"), 600);
        setTimeout(() => addLog("🔐 Sesión SSH cerrada.", "auth"), 900);
        setTimeout(() => addLog("👋 Hasta pronto, <strong>AnthZz Berrocal</strong>!", "info"), 1200);
      }
    });

    // Cambiar pestañas
    document.querySelectorAll('.tab').forEach(tab => {
      tab.addEventListener('click', () => {
        document.querySelectorAll('.tab').forEach(t => t.classList.remove('active'));
        document.querySelectorAll('.panel').forEach(p => p.classList.remove('active'));
        tab.classList.add('active');
        document.getElementById(tab.getAttribute('data-tab')).classList.add('active');
      });
    });

    // Iniciar logs al cargar
    window.onload = initLogs;
  </script>
</body>
</html>
