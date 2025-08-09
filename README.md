<!DOCTYPE html><html lang="es">
<head>
  <meta charset="utf-8" />
  <meta name="viewport" content="width=device-width, initial-scale=1" />
  <title>⚡ BerMatModZ • Anth'Zz Berrocal ⚡</title>
  <meta name="description" content="Portfolio profesional de Anth'Zz Berrocal — BerMatModZ. Bots, automatización, ciberseguridad, IA y servicios técnicos." />
  <link href="https://fonts.googleapis.com/css2?family=Orbitron:wght@600;700&family=Rajdhani:wght@400;600&family=Space+Grotesk:wght@300;500&family=Share+Tech+Mono&display=swap" rel="stylesheet">
  <style>
    :root{
      --bg1:#03030a; --bg2:#0f0c29; --neon:#00ffe1; --accent:#8a2be2; --muted:#a7dfe0;
      --card:rgba(255,255,255,0.03); --glass:rgba(255,255,255,0.04); --radius:14px; --maxw:1100px;
    }
    *{box-sizing:border-box}
    html,body{height:100%;margin:0}
    body{
      font-family:'Rajdhani',system-ui,Segoe UI,Roboto,Arial;
      background:linear-gradient(180deg,var(--bg1),var(--bg2));
      color:#eaf9f9; -webkit-font-smoothing:antialiased; -moz-osx-font-smoothing:grayscale; overflow-x:hidden;
    }/* CANVAS LAYERS */
canvas{position:fixed;inset:0;z-index:0;pointer-events:none}

/* CONTAINER */
.wrap{max-width:var(--maxw);margin:28px auto;padding:20px;position:relative;z-index:5}

/* HEADER */
header{display:flex;align-items:center;justify-content:space-between;padding:18px;border-radius:12px;background:linear-gradient(90deg,rgba(255,255,255,0.02),transparent);border:1px solid rgba(255,255,255,0.03);box-shadow:0 18px 60px rgba(0,0,0,0.6)}
.brand{display:flex;gap:14px;align-items:center}
.logo{font-family:'Orbitron';font-size:1.8rem;color:var(--neon);padding:8px 12px;border-radius:10px;background:linear-gradient(90deg,rgba(255,255,255,0.02),transparent);box-shadow:0 6px 20px rgba(0,255,225,0.03)}
.brand .meta{font-family:'Share Tech Mono';color:var(--muted);font-size:0.95rem}

/* MAIN HERO */
.hero{display:grid;grid-template-columns:340px 1fr;gap:22px;margin-top:20px}
.card{background:var(--card);padding:18px;border-radius:12px;border:1px solid rgba(255,255,255,0.03);box-shadow:0 20px 60px rgba(0,0,0,0.65)}

.photo{width:300px;height:300px;border-radius:12px;object-fit:cover;border:3px solid rgba(0,0,0,0.35);display:block}
.hero-title{font-family:'Orbitron';font-size:2.6rem;color:var(--neon);margin:6px 0}
.subtitle{font-size:1.15rem;color:#dff9f8;margin-bottom:10px}
.badges{display:flex;gap:10px;flex-wrap:wrap;margin-top:10px}
.badge{background:linear-gradient(90deg,rgba(255,255,255,0.02),transparent);padding:8px 12px;border-radius:999px;font-family:'Share Tech Mono';font-size:0.95rem}

/* DETAILS */
.detail{font-size:1.05rem;line-height:1.6;color:#eafdfc}
.muted{color:#bfe}

/* PROJECTS */
.projects{display:grid;grid-template-columns:repeat(3,1fr);gap:14px;margin-top:14px}
.project{padding:16px;border-radius:10px;background:linear-gradient(180deg,rgba(255,255,255,0.02),transparent);transition:transform .28s,box-shadow .28s}
.project h3{font-family:'Orbitron';color:var(--accent);margin:0 0 8px}
.project p{color:#dfe}
.taglist{display:flex;gap:8px;flex-wrap:wrap;margin-top:12px}
.tag{background:rgba(255,255,255,0.03);padding:6px 10px;border-radius:999px;font-family:'Share Tech Mono';font-size:0.9rem}

/* SERVICES */
.services{display:flex;gap:12px;flex-wrap:wrap;margin-top:12px}
.service{flex:1;min-width:220px;padding:14px;border-radius:10px;background:linear-gradient(180deg,rgba(255,255,255,0.02),transparent);border:1px solid rgba(255,255,255,0.02)}
.service h4{font-family:'Orbitron';color:var(--neon);margin:0 0 8px}
.service p{font-size:0.98rem;color:#dfe}

/* SOCIALS + CTA */
.cta-row{display:flex;gap:12px;align-items:center;margin-top:14px}
.btn{padding:12px 16px;border-radius:10px;border:none;cursor:pointer;font-weight:700}
.btn-primary{background:linear-gradient(90deg,var(--neon),#00bfff);color:#001}
.btn-ghost{background:transparent;border:1px solid rgba(255,255,255,0.06);color:#e6f9f9}
.socials{display:flex;gap:10px;align-items:center}
.socials a{display:inline-flex;align-items:center;gap:8px;padding:8px 12px;border-radius:10px;text-decoration:none;color:inherit;background:linear-gradient(90deg,rgba(255,255,255,0.02),transparent);border:1px solid rgba(255,255,255,0.02)}
.socials img{width:28px;height:28px}

/* LOGIN MODAL (console style) */
.modal{position:fixed;inset:0;display:grid;place-items:center;background:linear-gradient(180deg,rgba(0,0,0,0.75),rgba(0,0,0,0.9));z-index:80;opacity:0;pointer-events:none;transition:opacity .25s}
.modal.show{opacity:1;pointer-events:auto}
.modal-card{width:94%;max-width:720px;background:linear-gradient(180deg,rgba(255,255,255,0.02),transparent);border-radius:12px;padding:18px;border:1px solid rgba(255,255,255,0.04);box-shadow:0 30px 80px rgba(0,0,0,0.9)}
.console{background:#071018;padding:14px;border-radius:10px;color:#7ef9e0;font-family:'Share Tech Mono';font-size:0.98rem;min-height:120px}
.form{display:grid;gap:10px;margin-top:12px}
.form input{padding:12px;border-radius:8px;border:none;background:rgba(255,255,255,0.03);color:#e8f9f9}
.oauth{display:grid;grid-template-columns:1fr 1fr;gap:8px;margin-top:8px}

/* FOOTER */
footer{margin-top:34px;padding:18px;text-align:center;color:#bcd}

/* EFFECTS */
.blink{animation:blink 1.6s infinite}
@keyframes blink{0%{opacity:1;text-shadow:0 0 12px var(--neon)}50%{opacity:0.85;text-shadow:0 0 30px var(--neon)}100%{opacity:1;text-shadow:0 0 12px var(--neon)}}

/* RESPONSIVE */
@media (max-width:980px){.hero{grid-template-columns:1fr}.projects{grid-template-columns:repeat(2,1fr)}.photo{width:240px;height:240px}}
@media (max-width:640px){.projects{grid-template-columns:1fr}.photo{width:200px;height:200px}.hero-title{font-size:1.6rem}}

  </style>
</head>
<body>
  <!-- Canvas layers (matrix + particles) -->
  <canvas id="matrixCanvas"></canvas>
  <canvas id="particlesCanvas"></canvas>  <div class="wrap">
    <header class="header">
      <div class="brand">
        <div class="logo">⚡ BerMatModZ ⚡</div>
        <div>
          <div class="meta">Anth'Zz Berrocal — Líder & Desarrollador • Andahuaylas, Perú</div>
          <div class="meta">Respaldo: <strong style="color:var(--neon)">Anonymous</strong></div>
        </div>
      </div>
      <div class="cta-row">
        <button class="btn btn-primary" id="openLoginBtn">Iniciar sesión</button>
        <a class="btn btn-ghost" href="https://wa.me/51937556459?text=%2AHola%20AnthZz%20Berrocal%2C%20quiero%20m%C3%A1s%20informaci%C3%B3n%20sobre%20tus%20servicios%2A" target="_blank">📲 Consultar por WhatsApp</a>
      </div>
    </header><main class="hero">
  <aside class="card">
    <img class="photo" src="https://i.postimg.cc/bvST5wCV/Mag-Pic-20250501-185936660-3.jpg" alt="AnthZz Berrocal">
    <div style="margin-top:12px;text-align:center">
      <div class="badge">Creador: <strong>Anth'Zz Berrocal</strong></div>
      <div class="badge">Alias: <strong>⚡BerMatModZ🔥</strong></div>
      <div class="badge">Contacto: <strong>+51 937 556 459</strong></div>
    </div>
  </aside>

  <section class="card">
    <h1 class="hero-title blink">⚡ BerMatModZ • Anth'Zz Berrocal</h1>
    <p class="subtitle">Desarrollador de Bots para WhatsApp, Especialista en Automatización (Termux), IA conversacional, Interfaces visuales y Ciberseguridad aplicada.</p>

    <div class="detail">
      <p><strong>Resumen profesional:</strong> Soy un desarrollador y consultor enfocado en crear soluciones de automatización, bots conversacionales y herramientas de seguridad y administración para comunicaciones. Trabajo principalmente con Termux, Node.js y Python para desarrollar bots robustos que integren IA y módulos personalizados (juegos, stickers, moderación, auto-respuestas y analítica).</p>

      <p style="margin-top:10px"><strong>Tareas que realizo (detallado):</strong></p>
      <ul style="line-height:1.6">
        <li>Diseño e implementación de <strong>bots para WhatsApp</strong> (Termux/WhatsApp-API/MD) con comandos personalizados, juegos (Tres en Raya, Ahorcado), generación de stickers y gestión de menús con estilo.</li>
        <li>Automatización de tareas con <strong>Python</strong> y <strong>Node.js</strong>: cron jobs, scraping, envíos masivos (legítimos), backups y sincronización de datos.</li>
        <li>Integración de <strong>IA conversacional</strong> para respuestas naturales, aprendizaje básico y adaptación de tono (romántico, serio, profesional) según el proyecto.</li>
        <li>Desarrollo de <strong>interfaces visuales</strong> y páginas web estáticas/dinámicas con animaciones y efectos (como esta página).</li>
        <li>Consultoría en <strong>ciberseguridad básica aplicada</strong>: configuración segura de entornos, buenas prácticas para bots, protección de claves y prevención de fugas de datos.</li>
        <li>Creación de <strong>experiencias multimedia</strong>: audios generados por TTS, efectos de voz, animaciones y banners para branding.</li>
      </ul>
    </div>

    <div style="margin-top:14px" class="badges">
      <div class="badge">Tecnologías: Node.js • Python • Termux</div>
      <div class="badge">APIs: WhatsApp MD • Webhooks • OAuth</div>
      <div class="badge">Herramientas: GitHub • Git • Linux</div>
    </div>

    <div class="services" style="margin-top:18px">
      <div class="service">
        <h4>Creación de Bots</h4>
        <p>Desarrollo completo: comandos, menús, juegos, generación de stickers, y personalización de respuestas.</p>
      </div>
      <div class="service">
        <h4>Automatización</h4>
        <p>Flujos automáticos, sincronización de servidores, backups y tareas programadas en Termux o servidores VPS.</p>
      </div>
      <div class="service">
        <h4>IA & Conversación</h4>
        <p>Integración de modelos conversacionales para mejorar interacciones y aprendizaje básico del sistema.</p>
      </div>
    </div>

    <div class="cta-row" style="margin-top:18px">
      <a class="btn btn-primary" href="https://wa.me/51937556459?text=%2AHola%20AnthZz%20Berrocal%2C%20quiero%20m%C3%A1s%20informaci%C3%B3n%20sobre%20tus%20servicios%2A" target="_blank">📲 Consultar por WhatsApp</a>
      <button class="btn btn-ghost" id="viewProjects">Ver proyectos</button>
      <div class="socials" style="margin-left:auto">
        <a href="https://github.com/BerMatMods" target="_blank"><img src="https://cdn-icons-png.flaticon.com/512/733/733553.png" alt="GitHub"> GitHub</a>
        <a href="https://www.instagram.com/king_berrocal" target="_blank"><img src="https://cdn-icons-png.flaticon.com/512/733/733558.png" alt="IG"> Instagram</a>
        <a href="https://www.tiktok.com/@tuningcar321" target="_blank"><img src="https://cdn-icons-png.flaticon.com/512/3046/3046121.png" alt="TT"> TikTok</a>
      </div>
    </div>
  </section>
</main>

<!-- PROYECTOS -->
<section class="section">
  <h2>Proyectos destacados</h2>
  <div class="projects">
    <div class="project">
      <h3>⚡ BerMat-Bot MD</h3>
      <p>Bot de WhatsApp completo, ejecutable en Termux, con IA integrada, juegos (Tres en Raya), creación de stickers y comandos personalizados. Menu decorado y respuestas avanzadas.</p>
      <div class="taglist"><span class="tag">WhatsApp</span><span class="tag">Termux</span><span class="tag">Node.js</span></div>
    </div>

    <div class="project">
      <h3>🧠 F.A.M.A (IA)</h3>
      <p>Sistema de apoyo y aprendizaje básico diseñado para integrarse con bots, permitiendo mejorar respuestas y adaptar conversaciones según historial.</p>
      <div class="taglist"><span class="tag">IA</span><span class="tag">Integración</span><span class="tag">Aprendizaje</span></div>
    </div>

    <div class="project">
      <h3>📲 Clonador Estético</h3>
      <p>Interfaz visual para presentaciones estéticas de conversaciones, con efectos y audios TTS (uso demostrativo y legítimo).</p>
      <div class="taglist"><span class="tag">UI</span><span class="tag">Animación</span><span class="tag">TTS</span></div>
    </div>

    <div class="project">
      <h3>🎮 Juegos & Utilidades</h3>
      <p>Juegos como Tres en Raya, Ahorcado, generadores de stickers y utilidades de moderación de chats.</p>
      <div class="taglist"><span class="tag">Juegos</span><span class="tag">Stickers</span><span class="tag">Moderación</span></div>
    </div>

    <div class="project">
      <h3>🌐 Presentaciones Web</h3>
      <p>Landing pages, banners y animaciones para mostrar proyectos y portfolios (esta web es un ejemplo).</p>
      <div class="taglist"><span class="tag">HTML</span><span class="tag">CSS</span><span class="tag">JS</span></div>
    </div>

    <div class="project">
      <h3>🛠 Servicios Técnicos</h3>
      <p>Consultoría, despliegue y soporte técnico para bots y proyectos de automatización.</p>
      <div class="taglist"><span class="tag">Soporte</span><span class="tag">Deploy</span><span class="tag">Documentación</span></div>
    </div>
  </div>
</section>

<!-- DETALLES TÉCNICOS -->
<section class="section">
  <h2>Más sobre mi trabajo</h2>
  <div class="info">
    <p class="detail"><strong>Stack y herramientas:</strong> Node.js, Python, Termux, Git, GitHub, APIs REST, Webhooks, OAuth, TTS (espeak, termux-tts), SQLite / JSON for persistence. Experiencia con integración de servicios externos y despliegue en VPS o servicios gratuitos cuando es posible.</p>

    <p class="detail" style="margin-top:10px"><strong>Buenas prácticas:</strong> manejo seguro de tokens, encriptación ligera, backups periódicos, separación de datos sensibles y uso de entornos de prueba antes de producción.</p>
  </div>
</section>

<!-- CONTACT / SOCIAL -->
<section class="section">
  <h2>Contacto y redes</h2>
  <div class="info">
    <p class="detail">Contacto principal (WhatsApp): <strong>+51 937 556 459</strong> — usa el botón para enviar el mensaje prellenado y asegurar respuesta rápida.</p>
    <div style="margin-top:12px;display:flex;gap:12px;flex-wrap:wrap">
      <a class="socials" href="https://wa.me/51937556459?text=%2AHola%20AnthZz%20Berrocal%2C%20vengo%20desde%20tu%20web%2A" target="_blank"><img src="https://cdn-icons-png.flaticon.com/512/733/733585.png" alt="WA"> WhatsApp</a>
      <a class="socials" href="https://github.com/BerMatMods" target="_blank"><img src="https://cdn-icons-png.flaticon.com/512/733/733553.png" alt="GH"> GitHub</a>
      <a class="socials" href="https://www.instagram.com/king_berrocal" target="_blank"><img src="https://cdn-icons-png.flaticon.com/512/733/733558.png" alt="IG"> Instagram</a>
    </div>
  </div>
</section>

<footer>
  © 2025 ⚡ BerMatModZ ⚡ | Desarrollado por Anth'Zz Berrocal
</footer>

  </div>  <!-- LOGIN / REGISTER MODAL -->  <div class="modal" id="modal">
    <div class="modal-card">
      <div style="display:flex;justify-content:space-between;align-items:center">
        <div style="font-family:'Orbitron';font-size:1.2rem;color:var(--neon)">Iniciar Sesión / Registrarse</div>
        <button id="closeModal" style="background:transparent;border:none;color:#ccc;font-weight:700;cursor:pointer">✕</button>
      </div><div class="console" id="console">
    Bienvenido. Introduce tus credenciales o usa un inicio rápido con redes.
  </div>

  <form class="form" id="authForm">
    <input type="email" id="email" placeholder="Correo electrónico" required>
    <input type="password" id="password" placeholder="Contraseña" required>
    <div style="display:flex;gap:8px">
      <button class="btn btn-primary" type="submit">Entrar</button>
      <button type="button" id="showRegister" class="btn btn-ghost">Registrarse</button>
    </div>
    <a href="#" id="forgot" style="color:var(--neon);font-weight:700">¿Olvidaste tu contraseña?</a>

    <div class="oauth">
      <button type="button" onclick="social('google')" style="background:linear-gradient(90deg,#ff4b2b,#ff416c);color:#fff;padding:10px;border-radius:8px;border:none">Iniciar con Google</button>
      <button type="button" onclick="social('facebook')" style="background:linear-gradient(90deg,#1877f2,#4c69ba);color:#fff;padding:10px;border-radius:8px;border:none">Iniciar con Facebook</button>
    </div>
  </form>
</div>

  </div>  <script>
    // MATRIX RAIN
    const matrixCanvas = document.getElementById('matrixCanvas');
    const matrixCtx = matrixCanvas.getContext('2d');
    matrixCanvas.width = innerWidth; matrixCanvas.height = innerHeight;
    const cols = Math.floor(matrixCanvas.width / 20);
    const drops = Array(cols).fill(0);
    function drawMatrix(){
      matrixCtx.fillStyle = 'rgba(0,0,0,0.04)'; matrixCtx.fillRect(0,0,matrixCanvas.width,matrixCanvas.height);
      matrixCtx.fillStyle = '#0ff'; matrixCtx.font = '14px monospace';
      for(let i=0;i<drops.length;i++){
        const text = String.fromCharCode(0x30A0 + Math.random()*96);
        matrixCtx.fillText(text, i*20, drops[i]*20);
        if(drops[i]*20 > matrixCanvas.height && Math.random() > 0.975) drops[i]=0; drops[i]++;
      }
      requestAnimationFrame(drawMatrix);
    }
    drawMatrix();

    // PARTICLES
    const particlesCanvas = document.getElementById('particlesCanvas');
    const pctx = particlesCanvas.getContext('2d');
    function resizeCanv(){particlesCanvas.width=matrixCanvas.width=innerWidth;particlesCanvas.height=matrixCanvas.height=innerHeight}
    addEventListener('resize',resizeCanv); resizeCanv();
    const parts=[]; for(let i=0;i<120;i++){parts.push({x:Math.random()*innerWidth,y:Math.random()*innerHeight,r:Math.random()*2+0.6,vx:Math.random()*1-0.5,vy:Math.random()*1-0.5,a:Math.random()*0.6+0.1})}
    function animateParts(){pctx.clearRect(0,0,particlesCanvas.width,particlesCanvas.height);for(const p of parts){p.x+=p.vx;p.y+=p.vy;if(p.x<0)p.x=particlesCanvas.width;if(p.x>particlesCanvas.width)p.x=0;if(p.y<0)p.y=particlesCanvas.height;if(p.y>particlesCanvas.height)p.y=0;pctx.beginPath();pctx.fillStyle='rgba(0,255,225,'+p.a+')';pctx.arc(p.x,p.y,p.r,0,Math.PI*2);pctx.fill()}requestAnimationFrame(animateParts)}
    animateParts();

    // MODAL LOGIC
    const modal=document.getElementById('modal');const openLoginBtn=document.getElementById('openLoginBtn');const closeModal=document.getElementById('closeModal');
    openLoginBtn.addEventListener('click',()=>modal.classList.add('show'));
    closeModal.addEventListener('click',()=>modal.classList.remove('show'));
    document.getElementById('forgot').addEventListener('click',e=>{e.preventDefault();const em=prompt('Introduce tu correo para recuperar contraseña');if(em)alert('Se ha enviado enlace de recuperación a '+em+' (placeholder)')});

    document.getElementById('authForm').addEventListener('submit',e=>{e.preventDefault();const em=document.getElementById('email').value;alert('Sesión iniciada: '+em+' (esto es un placeholder)');modal.classList.remove('show')});
    document.getElementById('showRegister').addEventListener('click',()=>{const em=prompt('Correo para registrar:');if(em)alert('Cuenta registrada: '+em+' (placeholder)')});
    function social(p){alert('Autenticación con '+p+' (placeholder). Puedo integrar OAuth real si quieres).')}

    // Smooth scroll for projects
    document.getElementById('viewProjects').addEventListener('click',()=>{document.querySelector('.section').scrollIntoView({behavior:'smooth'})});
  </script></body>
</html>
