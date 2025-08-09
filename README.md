<!doctype html>
<html lang="es">
<head>
  <meta charset="utf-8" />
  <meta name="viewport" content="width=device-width,initial-scale=1" />
  <title>⚡ BerMatMods • Anth'Zz Berrocal ⚡</title>
  <meta name="description" content="BerMatMods - Portfolio: bots, automatizaciones, ciberseguridad e IA.">
  <link href="https://fonts.googleapis.com/css2?family=Orbitron:wght@600;700&family=Space+Grotesk:wght@400;600&display=swap" rel="stylesheet">
  <style>
    :root{
      --bg:#05050a;
      --card:rgba(255,255,255,0.03);
      --neon:#00ffe1;
      --accent:#8a2be2;
      --muted:#9fe;
      --maxw:1150px;
      --auth-email: 'berrocalanthony12@gmail.com';
    }
    *{box-sizing:border-box}
    html,body{height:100%;margin:0;background:linear-gradient(180deg,#03030a,#0f0c29 50%,#141126 100%);color:#eaf9f9;font-family:'Space Grotesk',system-ui,Arial;}
    a{color:inherit;text-decoration:none}
    /* canvases (matrix & particles) */
    canvas{position:fixed;inset:0;z-index:0;pointer-events:none;display:block}
    /* wrapper */
    .wrap{max-width:var(--maxw);margin:28px auto;padding:18px;position:relative;z-index:3}
    /* header */
    .header{display:flex;justify-content:space-between;align-items:center;gap:12px;padding:12px 16px;border-radius:12px;background:linear-gradient(90deg, rgba(255,255,255,0.02), transparent);border:1px solid rgba(255,255,255,0.03);box-shadow:0 20px 60px rgba(0,0,0,0.65)}
    .brand{display:flex;gap:12px;align-items:center}
    .logo{font-family:'Orbitron';font-size:1.6rem;color:var(--neon);padding:8px 12px;border-radius:10px;background:linear-gradient(90deg, rgba(255,255,255,0.02), transparent)}
    .meta{font-family:'Space Grotesk';color:var(--muted);font-size:0.95rem}
    .cta-row{display:flex;gap:10px;align-items:center}
    .btn{padding:10px 14px;border-radius:10px;border:none;cursor:pointer;font-weight:700}
    .btn-primary{background:linear-gradient(90deg,var(--neon),#00bfff);color:#001}
    .btn-ghost{background:transparent;border:1px solid rgba(255,255,255,0.06);color:#e6f9f9}
    /* hero */
    .hero{display:grid;grid-template-columns:320px 1fr;gap:20px;margin-top:18px;align-items:start}
    .card{background:var(--card);padding:16px;border-radius:12px;border:1px solid rgba(255,255,255,0.03);box-shadow:0 20px 60px rgba(0,0,0,0.6)}
    .photo{width:300px;height:300px;border-radius:12px;object-fit:cover;border:3px solid rgba(0,0,0,0.35);display:block}
    .hero-title{font-family:'Orbitron';font-size:2.4rem;color:var(--neon);margin:6px 0}
    .subtitle{font-size:1.05rem;color:#dff9f8;margin-bottom:10px}
    .badge{display:inline-block;padding:8px 12px;border-radius:999px;background:linear-gradient(90deg,rgba(255,255,255,0.02),transparent);font-family:'Space Grotesk';margin:6px 6px 0 0}
    .detail{font-size:1.02rem;line-height:1.6;color:#eafdfc}
    /* sections */
    .section{margin-top:26px}
    h2{font-family:'Orbitron';font-size:1.8rem;color:var(--neon);text-align:center;margin-bottom:12px}
    .info-box{background:linear-gradient(180deg, rgba(255,255,255,0.02), rgba(255,255,255,0.01));padding:18px;border-radius:12px;border:1px solid rgba(255,255,255,0.03);box-shadow:0 10px 40px rgba(0,0,0,0.6);font-size:1.05rem}
    .grid-3{display:grid;grid-template-columns:repeat(3,1fr);gap:14px;margin-top:14px}
    .proj{padding:14px;border-radius:10px;background:linear-gradient(180deg, rgba(255,255,255,0.01),transparent);transition:transform .28s}
    .proj:hover{transform:translateY(-8px)}
    .proj h3{font-family:'Orbitron';margin:0 0 8px 0;color:var(--accent)}
    .tag{display:inline-block;background:rgba(255,255,255,0.03);padding:6px 10px;border-radius:999px;margin-right:8px;font-family:'Space Grotesk';font-size:0.9rem}
    /* socials */
    .socials{display:flex;gap:10px;flex-wrap:wrap;align-items:center}
    .socials a{display:inline-flex;align-items:center;gap:8px;padding:8px 12px;border-radius:10px;text-decoration:none;background:linear-gradient(90deg,rgba(255,255,255,0.02),transparent);border:1px solid rgba(255,255,255,0.02)}
    .socials img{width:28px;height:28px}
    /* footer */
    footer{margin-top:30px;padding:18px;text-align:center;color:#bcd}
    /* fullscreen login overlay */
    #screenLogin{position:fixed;inset:0;background:linear-gradient(180deg, rgba(0,0,0,0.95), rgba(0,0,0,0.92));z-index:999;display:flex;align-items:center;justify-content:center;padding:20px}
    #loginCard{width:100%;max-width:980px;background:linear-gradient(180deg, rgba(255,255,255,0.02), rgba(255,255,255,0.01));border-radius:14px;padding:18px;border:1px solid rgba(255,255,255,0.04);display:grid;grid-template-columns:1fr 1fr;gap:12px;box-shadow:0 50px 120px rgba(0,0,0,0.9)}
    .consoleLeft{background:#071018;padding:14px;border-radius:10px;color:#7ef9e0;font-family:'Space Grotesk', monospace;min-height:260px}
    .formRight{padding:8px;display:flex;flex-direction:column;gap:10px;align-items:stretch}
    .formRight input{padding:12px;border-radius:8px;border:none;background:rgba(255,255,255,0.03);color:#e8f9f9;font-size:1rem}
    .oauthButtons{display:flex;gap:8px}
    .smallLink{font-size:0.9rem;color:var(--neon);cursor:pointer}
    /* error animation */
    .shake{animation:shake .5s}
    @keyframes shake{0%{transform:translateX(0)}25%{transform:translateX(-8px)}50%{transform:translateX(8px)}75%{transform:translateX(-6px)}100%{transform:translateX(0)}}
    .errorText{color:#ff6b6b;font-weight:700;margin-top:6px}
    /* responsive */
    @media(max-width:940px){
      .hero{grid-template-columns:1fr}
      #loginCard{grid-template-columns:1fr;max-width:420px}
      .photo{width:240px;height:240px;margin:0 auto}
    }
  </style>
</head>
<body>
  <!-- CANVASES -->
  <canvas id="matrixCanvas"></canvas>
  <canvas id="particlesCanvas"></canvas>

  <!-- FULLSCREEN LOGIN -->
  <div id="screenLogin" role="dialog" aria-modal="true">
    <div id="loginCard" aria-label="Login Card">
      <div class="consoleLeft">
        <h3 style="font-family:Orbitron;color:var(--neon);margin:0 0 8px 0">⚡ Bienvenido a BerMatMods</h3>
        <p style="margin:6px 0;color:#bfe">Accede con tu cuenta para ver el portfolio completo y herramientas. Usuario preconfigurado disponible.</p>
        <div id="consoleLines" style="margin-top:12px;font-size:0.95rem;line-height:1.45;color:#9fe">
          <div>» Sistema: Interfaz segura</div>
          <div>» Respaldo: Anonymous</div>
          <div>» Lluvia: <strong>BerMatMods</strong> (código vivo)</div>
          <div>» Notificaciones: Gmail (si conectas backend)</div>
        </div>
        <div style="margin-top:14px">
          <small style="color:#88e">Credenciales demo: <strong>berrocalanthony12@gmail.com</strong> / <strong>berrocal321</strong></small>
        </div>
      </div>

      <div class="formRight">
        <h3 style="font-family:Orbitron;color:var(--neon);margin:0">Iniciar sesión</h3>

        <form id="authForm" autocomplete="off">
          <input id="emailField" type="email" placeholder="Correo electrónico" required>
          <input id="passField" type="password" placeholder="Contraseña" required>
          <div style="display:flex;gap:8px">
            <button type="submit" class="btn btn-primary" style="flex:1">Entrar</button>
            <button id="showRegisterBtn" type="button" class="btn btn-ghost" style="flex:1">Registrarse</button>
          </div>
        </form>

        <div id="errorBox" style="height:28px"></div>

        <div style="display:flex;justify-content:space-between;align-items:center;margin-top:8px">
          <a id="forgotBtn" class="smallLink">¿Olvidaste tu contraseña?</a>
          <div class="oauthButtons" style="margin-left:auto">
            <button class="btn" onclick="oauth('google')" style="background:linear-gradient(90deg,#ff4b2b,#ff416c);color:#fff">Google</button>
            <button class="btn" onclick="oauth('facebook')" style="background:linear-gradient(90deg,#1877f2,#4c69ba);color:#fff">Facebook</button>
          </div>
        </div>

        <small style="color:#9ee;display:block;margin-top:10px">Al iniciar sesión correctamente verás el sitio completo. (Este login es local; para producción debes integrar backend).</small>
        <div style="margin-top:8px;display:flex;gap:8px">
          <button id="enterAsGuest" class="btn btn-ghost" style="flex:1">Entrar como visitante</button>
          <a href="#mainContent" id="skipLogin" class="btn btn-ghost" style="flex:1;text-align:center">Ver demo</a>
        </div>
      </div>
    </div>
  </div>

  <!-- MAIN CONTENT -->
  <div class="wrap" id="mainContent" style="opacity:0;transform:translateY(12px);transition:all .6s ease">
    <div class="header">
      <div class="brand">
        <div class="logo">⚡ BerMatMods ⚡</div>
        <div>
          <div class="meta">Anth'Zz Berrocal — Líder & Desarrollador</div>
          <div class="meta">Andahuaylas · Perú · Respaldo: <strong style="color:var(--neon)">Anonymous</strong></div>
        </div>
      </div>
      <div class="cta-row">
        <button class="btn btn-primary" id="openLoginAgain">Iniciar sesión</button>
        <a class="btn btn-ghost" href="https://wa.me/51937556459?text=%2AHola%20AnthZz%20Berrocal%2C%20quiero%20m%C3%A1s%20informaci%C3%B3n%20sobre%20tus%20servicios%2A" target="_blank">📲 Consultar por WhatsApp</a>
      </div>
    </div>

    <main class="hero">
      <aside class="card">
        <img class="photo" src="https://i.postimg.cc/bvST5wCV/Mag-Pic-20250501-185936660-3.jpg" alt="AnthZz Berrocal">
        <div style="text-align:center;margin-top:12px">
          <div class="badge">Creador: <strong>Anth'Zz Berrocal</strong></div>
          <div class="badge">Alias: <strong>⚡BerMatMods🔥</strong></div>
          <div class="badge">Contacto: <strong>+51 937 556 459</strong></div>
        </div>
      </aside>

      <section class="card">
        <h1 class="hero-title" style="margin-bottom:6px">⚡ BerMatMods • Anth'Zz Berrocal</h1>
        <p class="subtitle">Desarrollo de bots, automatizaciones, IA aplicada y soluciones de ciberseguridad con interfaces visuales y experiencia en Termux.</p>

        <div class="detail">
          <p><strong>Resumen profesional:</strong> Desarrollo bots para WhatsApp con IA integrada, automatización de tareas, creación de interfaces visuales, y consultoría en seguridad aplicada. Trabajo con Node.js, Python y Termux, creando soluciones desmontables y personalizadas para clientes.</p>

          <p style="margin-top:10px"><strong>Tareas y especialidades:</strong></p>
          <ul style="line-height:1.6">
            <li>⚙️ Bots WhatsApp (Termux & WhatsApp MD): comandos, menús, juegos, stickers y moderación.</li>
            <li>🤖 Integración IA: respuestas naturales, aprendizaje básico y adaptación de tono.</li>
            <li>🔐 Ciberseguridad aplicada: auditorías básicas, buenas prácticas y protección de datos.</li>
            <li>🔧 Automatización: scripts en Python/Node, backups, sincronización y tareas programadas.</li>
            <li>🎨 Experiencias visuales: banners, TTS, animaciones y presentaciones interactivas.</li>
          </ul>
        </div>

        <div style="margin-top:14px;display:flex;gap:10px;flex-wrap:wrap">
          <div class="badge">Node.js</div>
          <div class="badge">Python</div>
          <div class="badge">Termux</div>
          <div class="badge">GitHub</div>
          <div class="badge">TTS / Audio</div>
        </div>

        <div style="margin-top:18px;display:flex;gap:10px;align-items:center">
          <a class="btn btn-primary" href="https://wa.me/51937556459?text=%2AHola%20AnthZz%20Berrocal%2C%20quiero%20m%C3%A1s%20informaci%C3%B3n%20sobre%20tus%20servicios%2A" target="_blank">📲 Consultar por WhatsApp</a>
          <button id="viewProjectsBtn" class="btn btn-ghost">Ver proyectos</button>
          <div style="margin-left:auto" class="socials">
            <a href="https://github.com/BerMatMods" target="_blank"><img src="https://cdn-icons-png.flaticon.com/512/733/733553.png" alt="GitHub"> GitHub</a>
            <a href="https://www.instagram.com/king_berrocal" target="_blank"><img src="https://cdn-icons-png.flaticon.com/512/733/733558.png" alt="IG"> Instagram</a>
            <a href="https://www.tiktok.com/@tuningcar321" target="_blank"><img src="https://cdn-icons-png.flaticon.com/512/3046/3046121.png" alt="TT"> TikTok</a>
          </div>
        </div>
      </section>
    </main>

    <!-- projects -->
    <section class="section" id="projectsSection">
      <h2>Proyectos destacados</h2>
      <div class="grid-3">
        <div class="proj card">
          <h3>⚡ BerMat-Bot MD</h3>
          <p>Bot completo para WhatsApp con IA, juegos, stickers, comandos avanzados y personalización por .BerMat</p>
          <div style="margin-top:10px"><span class="tag">WhatsApp</span><span class="tag">Termux</span><span class="tag">Node.js</span></div>
        </div>
        <div class="proj card">
          <h3>🧠 F.A.M.A</h3>
          <p>Plataforma de IA ligera para asistentes, con aprendizaje contextual y módulos personalizables.</p>
          <div style="margin-top:10px"><span class="tag">IA</span><span class="tag">Integración</span></div>
        </div>
        <div class="proj card">
          <h3>📲 Clonador Estético</h3>
          <p>Interfaz para demostraciones y pruebas con efectos, TTS y mensajes simulados (uso legítimo y demostrativo).</p>
          <div style="margin-top:10px"><span class="tag">UI</span><span class="tag">TTS</span></div>
        </div>

        <div class="proj card">
          <h3>🎮 Juegos & Utilidades</h3>
          <p>Tres en Raya, Ahorcado, generadores de stickers y utilidades de moderación.</p>
          <div style="margin-top:10px"><span class="tag">Juegos</span><span class="tag">Stickers</span></div>
        </div>

        <div class="proj card">
          <h3>🌐 Presentaciones Web</h3>
          <p>Landing pages y presentaciones con animaciones y branding personalizado.</p>
          <div style="margin-top:10px"><span class="tag">HTML</span><span class="tag">CSS</span></div>
        </div>

        <div class="proj card">
          <h3>🛠 Servicios Técnicos</h3>
          <p>Consultoría, despliegue, soporte y documentación para proyectos de automatización y bots.</p>
          <div style="margin-top:10px"><span class="tag">Soporte</span><span class="tag">Deploy</span></div>
        </div>
      </div>
    </section>

    <!-- contact -->
    <section class="section">
      <h2>Contacto y redes</h2>
      <div class="info-box">
        <p class="detail">WhatsApp: <strong>+51 937 556 459</strong> — Usa el botón para enviar un mensaje prellenado y recibir respuesta rápida.</p>
        <div style="margin-top:12px" class="socials">
          <a href="https://wa.me/51937556459?text=%2AHola%20AnthZz%20Berrocal%2C%20vengo%20desde%20tu%20web%2A" target="_blank"><img src="https://cdn-icons-png.flaticon.com/512/733/733585.png" alt="WA"> WhatsApp</a>
          <a href="https://github.com/BerMatMods" target="_blank"><img src="https://cdn-icons-png.flaticon.com/512/733/733553.png" alt="GH"> GitHub</a>
          <a href="https://www.instagram.com/king_berrocal" target="_blank"><img src="https://cdn-icons-png.flaticon.com/512/733/733558.png" alt="IG"> Instagram</a>
        </div>
      </div>
    </section>

    <footer>
      © 2025 ⚡ BerMatMods ⚡ | Desarrollado por Anth'Zz Berrocal
    </footer>
  </div>

  <script>
    /****************************
     * Matrix (letras "BerMatMods")
     ****************************/
    const matrixCanvas = document.getElementById('matrixCanvas');
    const mctx = matrixCanvas.getContext('2d');
    const letters = 'BerMatMods'.split(''); // <-- here are the letters used in the rain
    let fontSize = 22;
    let columns = 0;
    const drops = [];

    function resizeMatrix() {
      matrixCanvas.width = innerWidth;
      matrixCanvas.height = innerHeight;
      fontSize = (innerWidth < 940) ? 16 : 22; // responsive size
      columns = Math.floor(matrixCanvas.width / fontSize);
      drops.length = 0;
      for (let i = 0; i < columns; i++) drops[i] = Math.floor(Math.random() * 20);
      mctx.font = fontSize + 'px Orbitron, monospace';
      mctx.textBaseline = 'top';
    }
    resizeMatrix();
    window.addEventListener('resize', resizeMatrix);

    function drawMatrix() {
      // translucent bg for fade effect
      mctx.fillStyle = 'rgba(0, 0, 0, 0.05)';
      mctx.fillRect(0, 0, matrixCanvas.width, matrixCanvas.height);

      for (let i = 0; i < drops.length; i++) {
        const text = letters[Math.floor(Math.random() * letters.length)];
        const x = i * fontSize;
        const y = drops[i] * fontSize;

        // head brighter occasionally
        if (Math.random() > 0.92) {
          mctx.fillStyle = '#bfffd5';
          mctx.fillText(text, x, y - fontSize * 0.2);
        }

        // normal letter color with slight randomness for parpadeo
        mctx.fillStyle = (Math.random() > 0.86) ? '#aaffaa' : '#00ff88';
        mctx.fillText(text, x, y);

        // update drop
        if (y > matrixCanvas.height && Math.random() > 0.975) {
          drops[i] = 0;
        }
        drops[i]++;
      }

      requestAnimationFrame(drawMatrix);
    }
    drawMatrix();

    /***********************
     * Particles (background)
     ***********************/
    const pCanvas = document.getElementById('particlesCanvas');
    const pctx = pCanvas.getContext('2d');
    let parts = [];
    function resizeParts(){
      pCanvas.width = innerWidth;
      pCanvas.height = innerHeight;
      parts = [];
      const count = Math.floor(Math.max(60, innerWidth / 12));
      for (let i = 0; i < count; i++) {
        parts.push({
          x: Math.random() * innerWidth,
          y: Math.random() * innerHeight,
          r: Math.random() * 1.8 + 0.6,
          vx: Math.random() * 0.8 - 0.4,
          vy: Math.random() * 0.6 - 0.3,
          a: Math.random() * 0.6 + 0.1
        });
      }
    }
    resizeParts();
    window.addEventListener('resize', resizeParts);

    function animateParts(){
      pctx.clearRect(0,0,pCanvas.width,pCanvas.height);
      for (const p of parts) {
        p.x += p.vx; p.y += p.vy;
        if (p.x < 0) p.x = pCanvas.width;
        if (p.x > pCanvas.width) p.x = 0;
        if (p.y < 0) p.y = pCanvas.height;
        if (p.y > pCanvas.height) p.y = 0;
        pctx.beginPath();
        pctx.fillStyle = 'rgba(0,255,225,' + p.a + ')';
        pctx.arc(p.x, p.y, p.r, 0, Math.PI * 2);
        pctx.fill();
      }
      requestAnimationFrame(animateParts);
    }
    animateParts();

    /***************************
     * Login (client-side)
     ***************************/
    const screenLogin = document.getElementById('screenLogin');
    const authForm = document.getElementById('authForm');
    const emailField = document.getElementById('emailField');
    const passField = document.getElementById('passField');
    const errorBox = document.getElementById('errorBox');
    const enterAsGuest = document.getElementById('enterAsGuest');
    const skipLogin = document.getElementById('skipLogin');
    const openLoginAgain = document.getElementById('openLoginAgain');
    const viewProjectsBtn = document.getElementById('viewProjectsBtn');
    const mainContent = document.getElementById('mainContent');

    // credentials requested by user
    const VALID_EMAIL = 'berrocalanthony12@gmail.com';
    const VALID_PASS = 'berrocal321';

    function showError(msg){
      errorBox.innerHTML = '<div class="errorText">' + msg + '</div>';
      // shake effect
      const card = document.getElementById('loginCard');
      card.classList.remove('shake');
      // reflow to restart animation
      void card.offsetWidth;
      card.classList.add('shake');
      setTimeout(()=>{ card.classList.remove('shake'); }, 600);
    }

    authForm.addEventListener('submit', (e)=>{
      e.preventDefault();
      const email = emailField.value.trim();
      const pass = passField.value;
      if(email ===
