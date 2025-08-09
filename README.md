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
      --bg:#03030a;
      --card:rgba(255,255,255,0.03);
      --neon:#00ffe1;
      --accent:#8a2be2;
      --muted:#9fe;
      --maxw:1200px;
    }
    *{box-sizing:border-box}
    html,body{height:100%;margin:0;background:linear-gradient(180deg,#02020a,#0f0c29 50%,#141126 100%);color:#eaf9f9;font-family:'Space Grotesk',system-ui,Arial,-apple-system;}
    a{color:inherit;text-decoration:none}
    /* canvases for background effects */
    canvas{position:fixed;inset:0;z-index:0;pointer-events:none;display:block}
    /* page wrapper */
    .wrap{max-width:var(--maxw);margin:28px auto;padding:18px;position:relative;z-index:3}
    /* header */
    .header{display:flex;justify-content:space-between;align-items:center;gap:12px;padding:14px;border-radius:12px;background:linear-gradient(90deg, rgba(255,255,255,0.02), transparent);border:1px solid rgba(255,255,255,0.03);box-shadow:0 18px 60px rgba(0,0,0,0.6)}
    .brand{display:flex;gap:12px;align-items:center}
    .logo{font-family:'Orbitron';font-size:1.6rem;color:var(--neon);padding:8px 12px;border-radius:10px;background:linear-gradient(90deg, rgba(255,255,255,0.02), transparent);box-shadow:0 6px 30px rgba(0,255,225,0.03)}
    .meta{font-family:'Space Grotesk';color:var(--muted);font-size:0.95rem}
    .cta-row{display:flex;gap:10px;align-items:center}
    .btn{padding:10px 14px;border-radius:10px;border:none;cursor:pointer;font-weight:700}
    .btn-primary{background:linear-gradient(90deg,var(--neon),#00bfff);color:#001}
    .btn-ghost{background:transparent;border:1px solid rgba(255,255,255,0.06);color:#e6f9f9}
    /* hero */
    .hero{display:grid;grid-template-columns:340px 1fr;gap:20px;margin-top:18px;align-items:start}
    .card{background:var(--card);padding:18px;border-radius:14px;border:1px solid rgba(255,255,255,0.03);box-shadow:0 20px 60px rgba(0,0,0,0.6)}
    .photo{width:300px;height:300px;border-radius:12px;object-fit:cover;border:3px solid rgba(0,0,0,0.35);display:block}
    .hero-title{font-family:'Orbitron';font-size:2.6rem;color:var(--neon);margin:6px 0}
    .subtitle{font-size:1.05rem;color:#dff9f8;margin-bottom:10px}
    .badge{display:inline-block;padding:8px 12px;border-radius:999px;background:linear-gradient(90deg,rgba(255,255,255,0.02),transparent);font-family:'Space Grotesk';margin:6px 6px 0 0}
    .detail{font-size:1.05rem;line-height:1.6;color:#eafdfc}
    /* sections */
    .section{margin-top:26px}
    h2{font-family:'Orbitron';font-size:1.9rem;color:var(--neon);text-align:center;margin-bottom:12px}
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
    /* responsive */
    @media(max-width:980px){
      .hero{grid-template-columns:1fr}
      .photo{width:240px;height:240px;margin:0 auto}
      .grid-3{grid-template-columns:repeat(2,1fr)}
    }
    @media(max-width:640px){
      .grid-3{grid-template-columns:1fr}
      .hero-title{font-size:1.6rem}
      .photo{width:200px;height:200px}
    }
  </style>
</head>
<body>
  <!-- Canvas layers for matrix & particles -->
  <canvas id="matrixCanvas"></canvas>
  <canvas id="particlesCanvas"></canvas>

  <div class="wrap" id="main">
    <div class="header">
      <div class="brand">
        <div class="logo">⚡ BerMatMods ⚡</div>
        <div>
          <div class="meta">Anth'Zz Berrocal — Líder & Desarrollador</div>
          <div class="meta">Andahuaylas · Perú · Respaldo: <strong style="color:var(--neon)">Anonymous</strong></div>
        </div>
      </div>
      <div class="cta-row">
        <a class="btn btn-primary" href="https://wa.me/51937556459?text=%2AHola%20AnthZz%20Berrocal%2C%20quiero%20m%C3%A1s%20informaci%C3%B3n%20sobre%20tus%20servicios%2A" target="_blank">📲 Consultar por WhatsApp</a>
        <a class="btn btn-ghost" href="https://github.com/BerMatMods" target="_blank">GitHub</a>
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
        <h1 class="hero-title">⚡ BerMatMods • Anth'Zz Berrocal</h1>
        <p class="subtitle">Desarrollo de bots, automatizaciones, IA aplicada y soluciones de ciberseguridad con interfaces visuales y experiencia en Termux.</p>

        <div class="detail">
          <p><strong>Resumen profesional:</strong> Desarrollo bots para WhatsApp con IA integrada, automatización de tareas, creación de interfaces visuales, y consultoría en seguridad aplicada. Trabajo con Node.js, Python y Termux, creando soluciones desmontables y personalizadas para clientes.</p>

          <p style="margin-top:10px"><strong>Tareas y especialidades:</strong></p>
          <ul style="line-height:1.6">
            <li>⚙️ Bots WhatsApp (Termux & WhatsApp MD): comandos, menús, juegos, stickers y moderación.</li>
            <li>🤖 Integración IA: respuestas naturales, aprendizaje básico y adaptación de tono según necesidad.</li>
            <li>🔐 Ciberseguridad aplicada: auditorías básicas, configuración segura y protección de datos.</li>
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

    <section class="section" id="projectsSection">
      <h2>Proyectos destacados</h2>
      <div class="grid-3">
        <div class="proj card">
          <h3>⚡ BerMat-Bot MD</h3>
          <p>Bot completo para WhatsApp con IA, juegos, stickers, comandos avanzados y personalización por .BerMat. Ejecutable en Termux y adaptado a servidores VPS.</p>
          <div style="margin-top:10px"><span class="tag">WhatsApp</span><span class="tag">Termux</span><span class="tag">Node.js</span></div>
        </div>

        <div class="proj card">
          <h3>🧠 F.A.M.A</h3>
          <p>Plataforma IA para asistentes y automatización empresarial, con integración de módulos y aprendizaje contextual.</p>
          <div style="margin-top:10px"><span class="tag">IA</span><span class="tag">Integración</span><span class="tag">Escalable</span></div>
        </div>

        <div class="proj card">
          <h3>📲 Clonador Estético</h3>
          <p>Interfaz de conversación para demostraciones, con efectos, TTS y personalización visual (uso demostrativo y responsable).</p>
          <div style="margin-top:10px"><span class="tag">UI</span><span class="tag">TTS</span></div>
        </div>

        <div class="proj card">
          <h3>🎮 Juegos & Utilidades</h3>
          <p>Mini-juegos (Tres en Raya, Ahorcado), generadores de stickers y utilidades para moderación y administración de chats.</p>
          <div style="margin-top:10px"><span class="tag">Juegos</span><span class="tag">Moderación</span></div>
        </div>

        <div class="proj card">
          <h3>🌐 Presentaciones Web</h3>
          <p>Landing pages y presentaciones con animaciones y branding personalizado — esta web es ejemplo del trabajo.</p>
          <div style="margin-top:10px"><span class="tag">HTML</span><span class="tag">CSS</span></div>
        </div>

        <div class="proj card">
          <h3>🛠 Servicios Técnicos</h3>
          <p>Consultoría, despliegue, soporte y documentación para proyectos de automatización y bots — soporte post-deploy disponible.</p>
          <div style="margin-top:10px"><span class="tag">Soporte</span><span class="tag">Deploy</span></div>
        </div>
      </div>
    </section>

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
    /* ================ Matrix (letters "BerMatMods") ================ */
    const matrixCanvas = document.getElementById('matrixCanvas');
    const mctx = matrixCanvas.getContext('2d');
    const letters = 'BerMatMods'.split('');
    let fontSize = 22;
    let columns = 0;
    const drops = [];

    function resizeMatrix() {
      matrixCanvas.width = innerWidth;
      matrixCanvas.height = innerHeight;
      fontSize = (innerWidth < 940) ? 16 : 22;
      columns = Math.floor(matrixCanvas.width / fontSize);
      drops.length = 0;
      for (let i = 0; i < columns; i++) drops[i] = Math.floor(Math.random() * 20);
      mctx.font = fontSize + 'px Orbitron, monospace';
      mctx.textBaseline = 'top';
    }
    resizeMatrix();
    window.addEventListener('resize', resizeMatrix);

    function drawMatrix() {
      mctx.fillStyle = 'rgba(0, 0, 0, 0.06)';
      mctx.fillRect(0, 0, matrixCanvas.width, matrixCanvas.height);

      for (let i = 0; i < drops.length; i++) {
        const text = letters[Math.floor(Math.random() * letters.length)];
        const x = i * fontSize;
        const y = drops[i] * fontSize;

        if (Math.random() > 0.92) {
          mctx.fillStyle = '#bfffd5';
          mctx.fillText(text, x, y - fontSize * 0.25);
        }

        mctx.fillStyle = (Math.random() > 0.86) ? '#aaffaa' : '#00ff88';
        mctx.fillText(text, x, y);

        if (y > matrixCanvas.height && Math.random() > 0.975) {
          drops[i] = 0;
        }
        drops[i]++;
      }
      requestAnimationFrame(drawMatrix);
    }
    drawMatrix();

    /* =================== Particles background =================== */
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

    /* ============= UI interactions ============= */
    document.getElementById('viewProjectsBtn').addEventListener('click', ()=> {
      document.getElementById('projectsSection').scrollIntoView({behavior:'smooth'});
    });

    // Optional: double click photo to copy contact
    document.querySelector('.photo').addEventListener('dblclick', ()=> {
      navigator.clipboard?.writeText('+51937556459').then(()=> {
        alert('Número copiado: +51 937 556 459');
      });
    });
  </script>
</body>
</html>
