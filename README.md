
<html lang="es" id="html-root">
<head>
  <meta charset="UTF-8" />
  <meta name="viewport" content="width=device-width, initial-scale=1.0, user-scalable=no" />
  <title>Spammer Pro - by AnthZz</title>

  <!-- PWA Manifest -->
  <link rel="manifest" href='application/json,{"name": "WhatsApp Spammer Pro", "short_name": "Spammer", "start_url": ".", "display": "standalone", "background_color": "#000", "theme_color": "#00ffff"}'>
  <meta name="theme-color" content="#000">

  <!-- Google Fonts -->
  <link href="https://fonts.googleapis.com/css2?family=Orbitron:wght@500;700&family=Roboto:wght@400;500;700&display=swap" rel="stylesheet">

  <style>
    /* === Estilos Globales === */
    * {
      margin: 0;
      padding: 0;
      box-sizing: border-box;
      font-family: 'Roboto', 'Segoe UI', sans-serif;
    }

    :root {
      --text: #fff;
      --bg: #000;
      --card-bg: rgba(10, 10, 20, 0.85);
      --input-bg: rgba(255, 255, 255, 0.1);
      --border: rgba(0, 255, 255, 0.4);
      --shadow: 0 10px 30px rgba(0, 0, 0, 0.6);
      --btn-bg: linear-gradient(45deg, #ff00ff, #00ffff, #ffff00);
      --btn-bg-anim: linear-gradient(-45deg, #ff00ff, #00ffff, #ffff00, #ff8800);
      --accent: #00ffff;
    }

    body {
      background: var(--bg);
      color: var(--text);
      min-height: 100vh;
      overflow: hidden;
      position: relative;
      transition: background 0.5s ease;
    }

    /* === Fondo con Partículas Animadas === */
    .particles {
      position: fixed;
      top: 0;
      left: 0;
      width: 100%;
      height: 100%;
      z-index: -2;
      pointer-events: none;
    }

    .particle {
      position: absolute;
      border-radius: 50%;
      opacity: 0.6;
      filter: blur(1px);
      animation: float 15s infinite linear;
    }

    @keyframes float {
      0% { transform: translateY(0) translateX(0) rotate(0deg); opacity: 0.5; }
      100% { transform: translateY(-1000px) translateX(100px) rotate(720deg); opacity: 0; }
    }

    /* === Texto RGB Animado === */
    .rgb-text {
      background: linear-gradient(90deg, #f00, #0f0, #00f, #ff0, #f0f, #0ff);
      background-size: 600% 100%;
      -webkit-background-clip: text;
      -webkit-text-fill-color: transparent;
      animation: rainbow 8s linear infinite;
      font-weight: bold;
    }

    @keyframes rainbow {
      0% { background-position: 0% 50%; }
      100% { background-position: 100% 50%; }
    }

    /* === Botón con brillo RGB === */
    .btn-neon {
      background: var(--btn-bg-anim);
      background-size: 300% 100%;
      animation: bgShift 6s linear infinite;
      color: white;
      font-weight: bold;
      border: none;
      border-radius: 12px;
      padding: 14px;
      cursor: pointer;
      font-family: 'Orbitron', sans-serif;
      transition: all 0.3s;
      box-shadow: 0 0 15px rgba(0, 255, 255, 0.5);
    }

    @keyframes bgShift {
      0% { background-position: 0%; }
      100% { background-position: 300%; }
    }

    .btn-neon:hover {
      transform: translateY(-3px);
      box-shadow: 0 8px 25px rgba(255, 255, 0, 0.6);
    }

    /* === Notificación Flotante === */
    #notification {
      position: fixed;
      top: 20px;
      right: 20px;
      background: rgba(0, 0, 0, 0.9);
      color: #00ffff;
      padding: 15px 20px;
      border-radius: 10px;
      box-shadow: 0 0 20px rgba(0, 255, 255, 0.5);
      z-index: 1000;
      opacity: 0;
      transform: translateX(100%);
      transition: all 0.4s ease;
      font-weight: bold;
      max-width: 80vw;
      overflow: hidden;
      text-overflow: ellipsis;
      white-space: nowrap;
    }

    #notification.show {
      opacity: 1;
      transform: translateX(0);
    }

    /* === Contenedor Principal === */
    .container {
      background: var(--card-bg);
      backdrop-filter: blur(10px);
      border-radius: 20px;
      padding: 25px;
      margin: 20px;
      max-width: 600px;
      width: 100%;
      box-shadow: var(--shadow);
      border: 1px solid var(--border);
      position: relative;
      z-index: 1;
      animation: fadeIn 0.8s ease-out;
    }

    @keyframes fadeIn {
      from { opacity: 0; transform: translateY(20px); }
      to { opacity: 1; transform: translateY(0); }
    }

    /* === Header === */
    .header {
      display: flex;
      align-items: center;
      gap: 15px;
      margin-bottom: 20px;
    }

    .menu-toggle {
      font-size: 1.5em;
      cursor: pointer;
      color: var(--accent);
      padding: 8px 12px;
      border-radius: 10px;
      background: rgba(0, 255, 255, 0.1);
      width: 40px;
      height: 40px;
      display: flex;
      align-items: center;
      justify-content: center;
    }

    .header h1 {
      font-family: 'Orbitron', sans-serif;
      font-size: 1.6em;
    }

    /* === Menú Lateral === */
    .sidebar {
      position: fixed;
      top: 0;
      left: -300px;
      width: 300px;
      height: 100%;
      background: rgba(0, 0, 0, 0.9);
      border-right: 1px solid var(--accent);
      padding: 60px 20px 20px;
      box-shadow: 5px 0 20px rgba(0, 255, 255, 0.2);
      z-index: 900;
      transition: left 0.4s ease;
      overflow-y: auto;
      backdrop-filter: blur(10px);
    }

    .sidebar.open {
      left: 0;
    }

    .menu-header {
      display: flex;
      justify-content: space-between;
      align-items: center;
      margin-bottom: 20px;
      padding-bottom: 10px;
      border-bottom: 1px solid var(--accent);
    }

    .menu-header h3 {
      color: var(--accent);
      font-size: 1.3em;
    }

    .close-btn {
      font-size: 1.5em;
      cursor: pointer;
      color: #aaa;
    }

    .sidebar ul {
      list-style: none;
    }

    .sidebar ul li {
      padding: 15px;
      margin-bottom: 10px;
      border-radius: 10px;
      cursor: pointer;
      transition: all 0.3s;
      text-align: center;
      font-weight: bold;
      background: rgba(0, 255, 255, 0.1);
    }

    .sidebar ul li:hover {
      background: var(--accent);
      color: black;
      transform: scale(1.03);
    }

    /* === Tabs === */
    .tab {
      display: none;
    }

    .tab.active {
      display: block;
    }

    /* === Formulario === */
    .input-group {
      margin-bottom: 20px;
    }

    .input-group label {
      display: block;
      margin-bottom: 8px;
      font-weight: bold;
      color: var(--accent);
    }

    .input-group input,
    .input-group textarea {
      width: 100%;
      padding: 14px;
      border: 1px solid var(--border);
      border-radius: 12px;
      background: var(--input-bg);
      color: var(--text);
      font-size: 16px;
      outline: none;
      transition: all 0.3s;
    }

    .input-group textarea {
      min-height: 100px;
      resize: vertical;
    }

    .input-group input:focus,
    .input-group textarea:focus {
      box-shadow: 0 0 15px var(--accent);
    }

    /* === Grids === */
    .grid-2 {
      display: grid;
      grid-template-columns: 1fr 1fr;
      gap: 10px;
    }

    /* === Historial y Plantillas === */
    .item-list {
      max-height: 300px;
      overflow-y: auto;
      margin-top: 15px;
    }

    .item {
      padding: 10px;
      background: rgba(0, 255, 255, 0.1);
      border-radius: 8px;
      margin-bottom: 8px;
      font-size: 14px;
      cursor: pointer;
      transition: all 0.3s;
    }

    .item:hover {
      background: var(--accent);
      color: black;
    }

    .delete-btn {
      float: right;
      color: #ff6b6b;
      cursor: pointer;
      font-size: 14px;
    }

    /* === Footer === */
    .footer {
      margin-top: 30px;
      text-align: center;
      font-size: 14px;
    }

    .signature {
      font-weight: bold;
    }

    .mod {
      color: #ff6b6b;
      font-style: italic;
    }
  </style>
</head>
<body>

  <!-- Fondo de partículas -->
  <div class="particles" id="particles"></div>

  <!-- Notificación -->
  <div id="notification" class="notification"></div>

  <!-- Menú Lateral -->
  <nav id="sidebar" class="sidebar">
    <div class="menu-header">
      <h3><span class="rgb-text">Menu</span></h3>
      <span class="close-btn" onclick="toggleMenu()">×</span>
    </div>
    <ul>
      <li onclick="switchTab('main')"><i>📝</i> <span data-lang="main">Principal</span></li>
      <li onclick="switchTab('templates')"><i>📋</i> <span data-lang="templates">Plantillas</span></li>
      <li onclick="switchTab('custom-templates')"><i>🎨</i> <span data-lang="custom">Mis Plantillas</span></li>
      <li onclick="switchTab('history')"><i>🕒</i> <span data-lang="history">Historial</span></li>
      <li onclick="switchTab('settings')"><i>⚙️</i> <span data-lang="settings">Ajustes</span></li>
      <li onclick="switchTab('about')"><i>ℹ️</i> <span data-lang="about">Info</span></li>
    </ul>
  </nav>

  <!-- Contenido Principal -->
  <div class="container">
    <header class="header">
      <div class="menu-toggle" onclick="toggleMenu()">☰</div>
      <h1 class="rgb-text">🛸 Spammer Pro</h1>
    </header>

    <!-- Pestaña: Principal -->
    <div id="main" class="tab active">
      <div class="input-group">
        <label data-lang="number">📞 Número (con +)</label>
        <input type="tel" id="number" placeholder="+51987654321" />
      </div>
      <div class="input-group">
        <label data-lang="message">💬 Mensaje</label>
        <textarea id="message" placeholder="Escribe tu mensaje..."></textarea>
      </div>
      <div class="input-group">
        <label data-lang="count">🔁 Repetir (1-100)</label>
        <input type="number" id="count" value="5" min="1" max="100" />
      </div>
      <div class="grid-2">
        <button id="copyBtn" class="btn-neon"><span data-lang="copy">📋 Copiar</span></button>
        <button id="sendBtn" class="btn-neon"><span data-lang="send">🚀 Enviar</span></button>
      </div>
    </div>

    <!-- Plantillas Predefinidas -->
    <div id="templates" class="tab">
      <h3 class="rgb-text"><span data-lang="predefined">✨ Plantillas</span></h3>
      <div class="grid-2">
        <div class="item" data-msg="❤️❤️❤️❤️❤️">❤️ Corazones</div>
        <div class="item" data-msg="🎉🎉🎉🎉🎉">🎉 Fiesta</div>
        <div class="item" data-msg="🤣🤣🤣🤣🤣">🤣 Risa</div>
        <div class="item" data-msg="🔥🔥🔥🔥🔥">🔥 Fuego</div>
      </div>
    </div>

    <!-- Mis Plantillas -->
    <div id="custom-templates" class="tab">
      <h3 class="rgb-text"><span data-lang="my-templates">🎨 Mis Plantillas</span></h3>
      <div class="input-group">
        <label><span data-lang="new-template">➕ Nueva Plantilla</span></label>
        <input type="text" id="newTemplate" placeholder="Nombre" />
        <textarea id="newTemplateMsg" placeholder="Mensaje" style="margin-top: 5px;"></textarea>
        <button id="saveTemplate" class="btn-neon" style="margin-top: 10px;">💾 Guardar</button>
      </div>
      <div class="item-list" id="userTemplates"></div>
    </div>

    <!-- Historial -->
    <div id="history" class="tab">
      <h3 class="rgb-text"><span data-lang="history-title">🕒 Historial de Envíos</span></h3>
      <div class="item-list" id="historyList"></div>
      <button id="clearHistory" class="btn-neon" style="margin-top: 10px;">🗑️ Limpiar</button>
    </div>

    <!-- Ajustes -->
    <div id="settings" class="tab">
      <h3 class="rgb-text"><span data-lang="settings">⚙️ Ajustes</span></h3>
      <div class="input-group">
        <label><span data-lang="lang">🌐 Idioma</span></label>
        <select id="langSelect" onchange="changeLang()">
          <option value="es">🇪🇸 Español</option>
          <option value="en">🇬🇧 English</option>
          <option value="pt">🇧🇷 Português</option>
          <option value="fr">🇫🇷 Français</option>
        </select>
      </div>
      <div class="input-group">
        <label><span data-lang="sound">🔊 Sonido</span></label>
        <input type="checkbox" id="soundToggle" checked />
      </div>
      <div class="input-group">
        <label><span data-lang="delay">⏱️ Retraso (ms)</span></label>
        <input type="number" id="delayInput" placeholder="0" />
      </div>
    </div>

    <!-- Info -->
    <div id="about" class="tab">
      <h3 class="rgb-text">ℹ️ Info</h3>
      <p><strong>App:</strong> WhatsApp Spammer Pro</p>
      <p><strong>Dev:</strong> AnthZz Berrocal</p>
      <p><strong>Brand:</strong> BerMatMods</p>
      <p style="margin:15px 0;"><span data-lang="pwa">📲 Instalable como app (PWA)</span></p>
      <p style="color:#ff6b6b; font-size:12px;">
        ⚠️ <span data-lang="warn">Uso responsable. No spamees sin permiso.</span>
      </p>
    </div>

    <footer class="footer">
      <p>✨ by <span class="signature rgb-text">AnthZz Berrocal</span> | <span class="mod">BerMatMods</span></p>
    </footer>
  </div>

  <!-- Sonido -->
  <audio id="notifSound" src="https://assets.mixkit.co/sfx/preview/mixkit-software-interface-start-2574.mp3" preload="auto"></audio>

  <script>
    // === Traducción ===
    const langTexts = {
      es: { main: "Principal", templates: "Plantillas", custom: "Mis Plantillas", history: "Historial", settings: "Ajustes", about: "Info", number: "📞 Número (con +)", message: "💬 Mensaje", count: "🔁 Repetir (1-100)", copy: "📋 Copiar", send: "🚀 Enviar", predefined: "✨ Plantillas", "my-templates": "🎨 Mis Plantillas", "new-template": "➕ Nueva Plantilla", "history-title": "🕒 Historial de Envíos", lang: "🌐 Idioma", sound: "🔊 Sonido", delay: "⏱️ Retraso (ms)", pwa: "📲 Instalable como app (PWA)", warn: "Uso responsable. No spamees sin permiso." },
      en: { main: "Main", templates: "Templates", custom: "My Templates", history: "History", settings: "Settings", about: "Info", number: "📞 Number (+)", message: "💬 Message", count: "🔁 Repeat (1-100)", copy: "📋 Copy", send: "🚀 Send", predefined: "✨ Templates", "my-templates": "🎨 My Templates", "new-template": "➕ New Template", "history-title": "🕒 Send History", lang: "🌐 Language", sound: "🔊 Sound", delay: "⏱️ Delay (ms)", pwa: "📲 Installable as app (PWA)", warn: "Use responsibly. Don't spam without permission." },
      pt: { main: "Principal", templates: "Modelos", custom: "Meus Modelos", history: "Histórico", settings: "Configurações", about: "Info", number: "📞 Número (+)", message: "💬 Mensagem", count: "🔁 Repetir (1-100)", copy: "📋 Copiar", send: "🚀 Enviar", predefined: "✨ Modelos", "my-templates": "🎨 Meus Modelos", "new-template": "➕ Novo Modelo", "history-title": "🕒 Histórico", lang: "🌐 Idioma", sound: "🔊 Som", delay: "⏱️ Atraso (ms)", pwa: "📲 Instalável como app (PWA)", warn: "Use com responsabilidade. Não envie spam sem permissão." },
      fr: { main: "Principal", templates: "Modèles", custom: "Mes Modèles", history: "Historique", settings: "Paramètres", about: "Info", number: "📞 Numéro (+)", message: "💬 Message", count: "🔁 Répéter (1-100)", copy: "📋 Copier", send: "🚀 Envoyer", predefined: "✨ Modèles", "my-templates": "🎨 Mes Modèles", "new-template": "➕ Nouveau Modèle", "history-title": "🕒 Historique", lang: "🌐 Langue", sound: "🔊 Son", delay: "⏱️ Délai (ms)", pwa: "📲 Installable comme app (PWA)", warn: "Utilisez de manière responsable. Ne spammez pas sans autorisation." }
    };

    function changeLang() {
      const lang = document.getElementById('langSelect').value;
      document.querySelectorAll('[data-lang]').forEach(el => {
        const key = el.getAttribute('data-lang');
        if (langTexts[lang] && langTexts[lang][key]) {
          el.innerText = langTexts[lang][key];
        }
      });
      localStorage.setItem('spammer-lang', lang);
    }

    // Cargar idioma
    window.onload = () => {
      const savedLang = localStorage.getItem('spammer-lang') || 'es';
      document.getElementById('langSelect').value = savedLang;
      changeLang();

      const savedTheme = localStorage.getItem('spammer-theme') || 'neon';
      document.documentElement.setAttribute('data-theme', savedTheme);

      loadTemplates();
      loadHistory();
      createParticles();
    };

    // === Menú ===
    function toggleMenu() {
      document.getElementById('sidebar').classList.toggle('open');
    }

    function switchTab(id) {
      document.querySelectorAll('.tab').forEach(t => t.classList.remove('active'));
      document.getElementById(id).classList.add('active');
      toggleMenu();
    }

    // === Partículas ===
    function createParticles() {
      const container = document.getElementById('particles');
      for (let i = 0; i < 50; i++) {
        const p = document.createElement('div');
        p.classList.add('particle');
        p.style.width = Math.random() * 10 + 5 + 'px';
        p.style.height = p.style.width;
        p.style.left = Math.random() * 100 + 'vw';
        p.style.top = Math.random() * 100 + 'vh';
        p.style.backgroundColor = ['#ff00ff', '#00ffff', '#ffff00', '#ff8800'][Math.floor(Math.random() * 4)];
        p.style.animationDuration = Math.random() * 20 + 10 + 's';
        p.style.animationDelay = Math.random() * 5 + 's';
        container.appendChild(p);
      }
    }

    // === Plantillas ===
    document.querySelectorAll('.item[data-msg]').forEach(item => {
      item.addEventListener('click', () => {
        document.getElementById('message').value = item.getAttribute('data-msg');
        showNotification('✅ Cargado');
      });
    });

    // === Guardar plantillas personalizadas ===
    document.getElementById('saveTemplate').addEventListener('click', () => {
      const name = document.getElementById('newTemplate').value.trim();
      const msg = document.getElementById('newTemplateMsg').value.trim();
      if (!name || !msg) return showNotification('⚠️ Completa ambos campos');

      let templates = JSON.parse(localStorage.getItem('userTemplates') || '[]');
      templates.push({ name, msg });
      localStorage.setItem('userTemplates', JSON.stringify(templates));
      document.getElementById('newTemplate').value = '';
      document.getElementById('newTemplateMsg').value = '';
      loadTemplates();
      showNotification('🎨 Plantilla guardada');
    });

    function loadTemplates() {
      const container = document.getElementById('userTemplates');
      container.innerHTML = '';
      const templates = JSON.parse(localStorage.getItem('userTemplates') || '[]');
      templates.forEach((t, i) => {
        const div = document.createElement('div');
        div.className = 'item';
        div.innerHTML = `${t.msg} <span class="delete-btn" onclick="deleteTemplate(${i})">🗑️</span>`;
        div.onclick = (e) => {
          if (!e.target.classList.contains('delete-btn')) {
            document.getElementById('message').value = t.msg;
            showNotification('✅ Cargado: ' + t.name);
          }
        };
        container.appendChild(div);
      });
    }

    function deleteTemplate(index) {
      let templates = JSON.parse(localStorage.getItem('userTemplates') || '[]');
      templates.splice(index, 1);
      localStorage.setItem('userTemplates', JSON.stringify(templates));
      loadTemplates();
    }

    // === Historial ===
    function addToHistory(number, message, count) {
      const entry = { number, message, count, time: new Date().toLocaleString() };
      let history = JSON.parse(localStorage.getItem('sendHistory') || '[]');
      history.unshift(entry);
      if (history.length > 50) history.pop();
      localStorage.setItem('sendHistory', JSON.stringify(history));
      loadHistory();
    }

    function loadHistory() {
      const container = document.getElementById('historyList');
      container.innerHTML = '';
      const history = JSON.parse(localStorage.getItem('sendHistory') || '[]');
      history.forEach(h => {
        const div = document.createElement('div');
        div.className = 'item';
        div.textContent = `${h.message.substring(0, 30)}... x${h.count}`;
        div.title = `Enviado a ${h.number} - ${h.time}`;
        div.onclick = () => {
          document.getElementById('number').value = h.number;
          document.getElementById('message').value = h.message;
          document.getElementById('count').value = h.count;
          switchTab('main');
        };
        container.appendChild(div);
      });
    }

    document.getElementById('clearHistory').addEventListener('click', () => {
      localStorage.removeItem('sendHistory');
      loadHistory();
      showNotification('🗑️ Historial limpio');
    });

    // === Enviar ===
    document.getElementById('sendBtn').addEventListener('click', () => {
      const number = document.getElementById('number').value.trim();
      const message = document.getElementById('message').value.trim();
      const count = parseInt(document.getElementById('count').value) || 1;
      const delay = parseInt(document.getElementById('delayInput').value) || 0;

      if (!number || !message) return showNotification('⚠️ Completa los campos');

      const repeated = message.repeat(count);
      const encoded = encodeURIComponent(repeated);
      const url = `https://wa.me/${number.replace(/\s/g, '')}?text=${encoded}`;

      addToHistory(number, message, count);

      if (delay > 0) {
        showNotification(`⏳ En ${delay}ms...`);
        setTimeout(() => window.open(url, '_blank'), delay);
      } else {
        window.open(url, '_blank');
      }

      playSound();
      showNotification('🚀 Enviado');
    });

    // === Copiar ===
    document.getElementById('copyBtn').addEventListener('click', () => {
      const msg = document.getElementById('message').value.repeat(document.getElementById('count').value || 1);
      navigator.clipboard.writeText(msg).then(() => {
        playSound();
        showNotification('📋 Copiado');
      });
    });

    // === Sonido ===
    function playSound() {
      if (document.getElementById('soundToggle').checked) {
        document.getElementById('notifSound').play().catch(() => {});
      }
    }

    // === Notificación ===
    function showNotification(msg) {
      const notif = document.getElementById('notification');
      notif.textContent = msg;
      notif.classList.add('show');
      setTimeout(() => notif.classList.remove('show'), 3000);
    }
  </script>
</body>
</html>
