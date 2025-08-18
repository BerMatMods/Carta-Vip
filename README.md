<!DOCTYPE html>
<html lang="es">
<head>
<meta charset="utf-8">
<meta name="viewport" content="width=device-width,initial-scale=1">
<title>⚡BerMat Injector Pro🔥</title>

<!-- Fuentes y estilo futurista -->
<link href="https://fonts.googleapis.com/css2?family=Russo+One&family=Share+Tech+Mono&display=swap" rel="stylesheet">
<style>
  body {
    margin: 0;
    background: #050d0f;
    color: #00ffcc;
    font-family: 'Share Tech Mono', monospace;
  }
  header {
    text-align: center;
    padding: 25px;
    background: linear-gradient(90deg,#00ffcc,#0099ff);
    color: black;
    text-shadow: 0 0 10px #00ffcc, 0 0 20px #0099ff;
  }
  h1 {
    font-family: 'Russo One', sans-serif;
    font-size: 32px;
  }
  .container {
    padding: 15px;
  }
  .panel {
    background: rgba(0,0,0,0.85);
    border: 2px solid #00ffcc;
    border-radius: 15px;
    padding: 20px;
    margin-bottom: 20px;
    box-shadow: 0 0 20px #00ffcc;
  }
  .panel h2 {
    margin-top: 0;
    font-size: 22px;
    color: #00e0ff;
    text-shadow: 0 0 10px #00e0ff;
  }
  button {
    background: #00ffcc;
    color: black;
    font-size: 16px;
    padding: 10px 18px;
    border: none;
    border-radius: 12px;
    cursor: pointer;
    margin: 5px;
    transition: 0.3s;
  }
  button:hover {
    background: #0099ff;
    color: white;
    box-shadow: 0 0 15px #0099ff;
  }
  #logs {
    font-family: monospace;
    background: black;
    padding: 15px;
    height: 220px;
    overflow-y: auto;
    border-radius: 10px;
    border: 1px solid #00ffcc;
    color: #00ffcc;
  }
  .tools-grid {
    display: grid;
    grid-template-columns: repeat(auto-fit,minmax(150px,1fr));
    gap: 10px;
  }
  .tool {
    background: rgba(0,255,204,0.1);
    border: 1px solid #00ffcc;
    border-radius: 10px;
    padding: 10px;
    text-align: center;
    cursor: pointer;
    transition: 0.3s;
  }
  .tool:hover {
    background: rgba(0,255,204,0.2);
    transform: scale(1.05);
  }
  .monitor {
    display: flex;
    justify-content: space-between;
    font-size: 14px;
  }
  footer {
    text-align: center;
    padding: 20px;
    font-size: 14px;
    color: gray;
  }
</style>
</head>
<body>
<header>
  <h1>⚡BerMat Injector Pro🔥</h1>
  <p>By: Anth'Zz Berrocal | Alias: <b>BerMatModZ</b></p>
</header>

<div class="container">

  <!-- Panel de Conexión -->
  <div class="panel">
    <h2>🔌 Conexión VPN/SSH/HTTP</h2>
    <button onclick="connect()">Conectar</button>
    <button onclick="disconnect()">Desconectar</button>
    <div class="monitor">
      <p>🌐 Estado: <span id="status">Desconectado ❌</span></p>
      <p>⚡ Ping: <span id="ping">---</span></p>
      <p>📶 Velocidad: <span id="speed">---</span></p>
    </div>
  </div>

  <!-- Registros -->
  <div class="panel">
    <h2>📡 Registro de Conexión</h2>
    <div id="logs">Esperando acción...</div>
  </div>

  <!-- Configuración -->
  <div class="panel">
    <h2>⚙️ Configuración EHI</h2>
    <input type="file" id="fileInput">
    <button onclick="importConfig()">Importar</button>
    <button onclick="exportConfig()">Exportar</button>
    <p id="configStatus">Sin configuración cargada.</p>
  </div>

  <!-- Herramientas -->
  <div class="panel">
    <h2>🛠️ Herramientas</h2>
    <div class="tools-grid">
      <div class="tool" onclick="fakeTool('Payload Generator')">Payload Generator</div>
      <div class="tool" onclick="fakeTool('Host Checker')">Host Checker</div>
      <div class="tool" onclick="fakeTool('IP Logger')">IP Logger</div>
      <div class="tool" onclick="fakeTool('SSL Tunnel')">SSL Tunnel</div>
      <div class="tool" onclick="fakeTool('DNS Spoofer')">DNS Spoofer</div>
      <div class="tool" onclick="fakeTool('HTTP Header Modifier')">HTTP Header</div>
    </div>
  </div>

  <!-- Info personal -->
  <div class="panel">
    <h2>👨‍💻 Información del Proyecto</h2>
    <p>🔹 Creador: <b>Anth'Zz Berrocal</b></p>
    <p>🔹 Proyecto: ⚡BerMat Injector🔥</p>
    <p>🔹 Alias: <b>BerMatModZ</b></p>
    <p>🔹 Ubicación: Andahuaylas, Perú 🇵🇪</p>
    <p>🔹 Especialidad: Bots WhatsApp, Hacking Ético, Seguridad Web, Apps Pro</p>
    <p>🔹 Otros proyectos: ⚡BerMat-Bot MD🔥, BerMat_Mods</p>
  </div>

</div>

<footer>
  ⚡ Proyecto 100% Free & Open Source | GitHub: <b>BerMatModZ</b>
</footer>

<script>
  let logs = document.getElementById("logs");
  let connected = false;
  let statusEl = document.getElementById("status");
  let pingEl = document.getElementById("ping");
  let speedEl = document.getElementById("speed");

  function connect(){
    if(connected){
      logs.innerHTML += "<br>[INFO] Ya estás conectado ✅";
      return;
    }
    logs.innerHTML += "<br>[INFO] Iniciando conexión...";
    statusEl.innerText = "Conectando...";
    setTimeout(()=>{ logs.innerHTML += "<br>[OK] Autenticando SSH..."; },1000);
    setTimeout(()=>{ logs.innerHTML += "<br>[OK] HTTP Header Injectado."; },2000);
    setTimeout(()=>{ logs.innerHTML += "<br>[OK] Conexión establecida a <b>BerMat Server</b> 🌐"; 
                     connected=true; statusEl.innerText="Conectado ✅"; },3000);
    setTimeout(()=>{ 
      pingEl.innerText="65ms"; 
      speedEl.innerText="7.5 Mbps"; 
      logs.innerHTML += "<br>[LOG] Conexión estable, tráfico en curso..."; 
    },4000);
  }

  function disconnect(){
    if(!connected){
      logs.innerHTML += "<br>[INFO] No hay conexión activa.";
      return;
    }
    logs.innerHTML += "<br>[WARN] Cerrando conexión...";
    statusEl.innerText="Desconectando...";
    setTimeout(()=>{ 
      logs.innerHTML += "<br>[OK] Desconectado ❌"; 
      connected=false; 
      statusEl.innerText="Desconectado ❌"; 
      pingEl.innerText="---"; 
      speedEl.innerText="---"; 
    },2000);
  }

  function importConfig(){
    let file = document.getElementById("fileInput").files[0];
    if(file){
      document.getElementById("configStatus").innerText = "Configuración importada: "+file.name;
      logs.innerHTML += "<br>[CONFIG] Archivo cargado con éxito.";
    } else {
      logs.innerHTML += "<br>[ERROR] No se seleccionó ningún archivo.";
    }
  }

  function exportConfig(){
    let blob = new Blob(["CONFIG=BerMatModZ Pro Injector"], {type: "text/plain"});
    let url = URL.createObjectURL(blob);
    let a = document.createElement("a");
    a.href = url;
    a.download = "bermat-config.ehi";
    a.click();
    logs.innerHTML += "<br>[CONFIG] Archivo exportado correctamente.";
  }

  function fakeTool(name){
    logs.innerHTML += `<br>[TOOL] Ejecutando ${name}...`;
    setTimeout(()=>{ logs.innerHTML += `<br>[OK] ${name} finalizado correctamente.`; },2000);
  }
</script>
</body>
</html>
