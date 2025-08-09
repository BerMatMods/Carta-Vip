<!doctype html>

<html lang="es">
<head>
  <meta charset="utf-8" />
  <meta name="viewport" content="width=device-width,initial-scale=1" />
  <title>⚡ BerMatModZ • Profesional ⚡</title>
  <meta name="description" content="BerMatModZ - Desarrollador de Bots, Proyectos y Servicios | Anth'Zz Berrocal" />
  <!-- Fuentes -->
  <link href="https://fonts.googleapis.com/css2?family=Orbitron:wght@600;700&family=Rajdhani:wght@400;600&family=Share+Tech+Mono&family=Space+Grotesk:wght@300;500&display=swap" rel="stylesheet">
  <style>
    :root{
      --bg1: #060617;
      --bg2: #0f0c29;
      --neon: #00ffe1;
      --accent1: #8a2be2;
      --accent2: #ff416c;
      --glass: rgba(255,255,255,0.06);
      --card: rgba(255,255,255,0.03);
      --glass-2: rgba(255,255,255,0.04);
      --rounded: 16px;
    }
    *{box-sizing:border-box}
    html,body{height:100%}
    body{
      margin:0;
      font-family: 'Rajdhani', system-ui, -apple-system, 'Segoe UI', Roboto, 'Helvetica Neue', Arial;
      background: radial-gradient(1200px 600px at 10% 10%, rgba(138,43,226,0.08), transparent),
                  radial-gradient(1000px 500px at 90% 90%, rgba(0,191,255,0.05), transparent),
                  linear-gradient(180deg,var(--bg1),var(--bg2));
      color:#e9f6f6;
      -webkit-font-smoothing:antialiased;
      -moz-osx-font-smoothing:grayscale;
      overflow-x:hidden;
    }/* Partículas simples */
#particles{
  position:fixed;inset:0;pointer-events:none;z-index:0;mix-blend-mode:screen;opacity:0.25
}

header{
  position:relative;z-index:3;padding:48px 20px 20px;text-align:center
}
.brand{
  display:inline-flex;gap:14px;align-items:center;padding:12px 20px;border-radius:30px;background:linear-gradient(90deg,rgba(255,255,255,0.03),rgba(255,255,255,0.02));box-shadow:0 6px 30px rgba(0,0,0,0.5),0 0 30px rgba(0,255,225,0.06);
}
.logo-glow{font-family:'Orbitron';font-size:1.25rem;color:var(--neon);text-shadow:0 0 12px rgba(0,255,225,0.15)}
.tagline{font-family:'Share Tech Mono';font-size:0.95rem;color:rgba(255,255,255,0.8)}

/* Hero */
.hero{
  max-width:1200px;margin:18px auto 30px;padding:26px;border-radius:20px;background:linear-gradient(180deg,rgba(255,255,255,0.02),rgba(255,255,255,0.01));backdrop-filter: blur(6px);box-shadow:0 10px 60px rgba(0,0,0,0.6);position:relative;z-index:2;overflow:hidden
}
.hero-grid{display:grid;grid-template-columns:320px 1fr;gap:22px;align-items:center}
.card-photo{background:linear-gradient(180deg,var(--card),transparent);padding:14px;border-radius:14px;border:1px solid rgba(0,255,225,0.06);display:flex;flex-direction:column;align-items:center}
.card-photo img{width:260px;height:260px;border-radius:12px;object-fit:cover;border:3px solid rgba(0,0,0,0.3);box-shadow:0 6px 30px rgba(0,0,0,0.6),0 0 18px rgba(138,43,226,0.06)}
.info-hero{padding:6px 10px}
.info-hero h1{font-family:'Orbitron';font-size:2.4rem;margin-bottom:8px;color:var(--neon);letter-spacing:1px}
.info-hero p.lead{font-size:1.05rem;color:#dff9f8;margin-bottom:12px}
.badges{display:flex;gap:10px;flex-wrap:wrap}
.badge{padding:8px 12px;border-radius:999px;background:linear-gradient(90deg,rgba(255,255,255,0.02),rgba(255,255,255,0.01));border:1px solid rgba(255,255,255,0.03);font-family:'Share Tech Mono';font-size:0.9rem}

/* Blinking neon */
.blink{animation:blink 1.8s infinite}
@keyframes blink{0%{opacity:1;text-shadow:0 0 12px var(--neon)}50%{opacity:0.85;text-shadow:0 0 30px var(--neon)}100%{opacity:1;text-shadow:0 0 12px var(--neon)}}

/* Projects */
.wrap{max-width:1200px;margin:30px auto;padding:0 20px 80px}
.grid{display:grid;grid-template-columns:repeat(3,1fr);gap:18px}
.project{background:var(--glass);padding:18px;border-radius:12px;border:1px solid rgba(255,255,255,0.03);box-shadow:0 10px 40px rgba(0,0,0,0.6);transition:transform 0.35s,box-shadow 0.35s}
.project:hover{transform:translateY(-8px) scale(1.01);box-shadow:0 18px 60px rgba(0,0,0,0.7)}
.project h3{font-family:'Orbitron';font-size:1.1rem;color:var(--accent1);margin-bottom:8px}
.project p{font-size:0.95rem;color:#dfeff0}
.tags{display:flex;gap:8px;margin-top:12px;flex-wrap:wrap}
.tag{font-family:'Share Tech Mono';font-size:0.8rem;padding:6px 10px;border-radius:999px;background:rgba(255,255,255,0.03);border:1px solid rgba(255,255,255,0.02)}

/* Servicios */
.services{display:flex;gap:12px;flex-wrap:wrap;margin-top:22px}
.service{flex:1;min-width:220px;padding:14px;border-radius:12px;background:linear-gradient(180deg,rgba(255,255,255,0.02),transparent);border:1px solid rgba(255,255,255,0.03)}
.service h4{font-family:'Orbitron';color:var(--neon);font-size:0.98rem}
.service p{font-size:0.9rem}

/* Social bar */
.social-row{display:flex;gap:12px;justify-content:center;margin-top:16px}
.soc-btn{display:inline-flex;align-items:center;gap:10px;padding:10px 14px;border-radius:12px;background:linear-gradient(90deg,rgba(255,255,255,0.02),rgba(255,255,255,0.01));border:1px solid rgba(255,255,255,0.03);text-decoration:none;color:inherit}
.soc-btn img{width:26px;height:26px}

/* CTA / form sticky footer */
.cta-wrap{position:fixed;right:18px;bottom:18px;z-index:6}
.cta{background:linear-gradient(90deg,var(--neon),#00bfff);padding:12px 16px;border-radius:12px;color:#001;cursor:pointer;font-weight:700;box-shadow:0 8px 36px rgba(0,0,0,0.6);border:1px solid rgba(255,255,255,0.12);}

/* Login modal */
.modal{position:fixed;inset:0;display:grid;place-items:center;background:linear-gradient(180deg,rgba(0,0,0,0.6),rgba(0,0,0,0.85));z-index:30;opacity:0;pointer-events:none;transition:opacity 0.25s}
.modal.show{opacity:1;pointer-events:auto}
.modal-card{width:96%;max-width:520px;background:linear-gradient(180deg, rgba(255,255,255,0.02), rgba(255,255,255,0.01));border-radius:14px;padding:18px;border:1px solid rgba(255,255,255,0.04);box-shadow:0 30px 70px rgba(0,0,0,0.8)}
.form-row{display:flex;gap:10px;margin-bottom:12px}
.form-row input{flex:1;padding:12px;border-radius:10px;border:none;background:rgba(255,255,255,0.03);color:#e8f9f9}
.modal-card button{padding:12px;border-radius:10px;border:none;cursor:pointer;font-weight:700}
.btn-primary{background:linear-gradient(90deg,var(--neon),#00bfff);color:#001}
.social-grid{display:flex;gap:8px}
.social-grid button{flex:1;padding:10px;border-radius:10px;border:none;cursor:pointer}

/* Footer */
footer.sitefoot{margin-top:60px;padding:28px 20px;text-align:center;color:#bcd;z-index:2}
.footer-links{display:flex;gap:12px;justify-content:center;flex-wrap:wrap;margin-top:12px}

/* Responsive */
@media (max-width:980px){
  .hero-grid{grid-template-columns:1fr;grid-auto-rows:auto}
  .grid{grid-template-columns:repeat(2,1fr)}
}
@media (max-width:640px){
  .grid{grid-template-columns:1fr}
  .brand{padding:10px 12px}
  .info-hero h1{font-size:1.6rem}
  .project{padding:14px}
  .soc-btn{padding:8px 10px}
  .cta{padding:10px 12px}
}

/* Small decorative corner */
.corner-banner{position:absolute;left:18px;top:18px;padding:8px 12px;border-radius:10px;background:linear-gradient(90deg,var(--accent1),var(--accent2));font-weight:700;color:#fff;box-shadow:0 8px 30px rgba(0,0,0,0.6);z-index:4}

  </style>
</head>
<body>
  <canvas id="particles"></canvas>
  <header>
    <div class="brand">
      <div class="logo-glow">⚡ BerMatModZ ⚡</div>
      <div style="text-align:left">
        <div class="tagline">Anth'Zz Berrocal — Desarrollador • Líder • BerMat</div>
        <div style="font-size:12px;color:rgba(255,255,255,0.6);font-family:'Share Tech Mono'">Andahuaylas · Perú</div>
      </div>
    </div>
  </header>  <main class="hero" role="main">
    <div class="corner-banner blink">𝑩𝑬𝑹𝑴𝑨𝑻𝑴𝑶𝑫𝑺</div>
    <div class="hero-grid">
      <div class="card-photo">
        <img src="https://i.postimg.cc/bvST5wCV/Mag-Pic-20250501-185936660-3.jpg" alt="AnthZz Berrocal">
        <div style="margin-top:12px;font-family:'Share Tech Mono'">Creador • ⚡BerMatModZ🔥</div>
      </div>
      <div class="info-hero">
        <h1 class="blink">⚡ BerMatModZ • Anth'Zz Berrocal</h1>
        <p class="lead">Desarrollador de bots para WhatsApp, sistemas de automatización en Termux, IA conversacional y experiencias visuales cibernéticas. Diseño interfaces limpias, animadas y con estilo profesional.</p>
        <div class="badges">
          <div class="badge">📌 Creador: Anth'Zz Berrocal</div>
          <div class="badge">📍 Ubicación: Andahuaylas</div>
          <div class="badge">📱 Contacto: +51 937 556 459</div>
        </div><div style="margin-top:14px" class="social-row">
      <!-- Social buttons with icons -->
      <a class="soc-btn" href="https://wa.me/51937556459" target="_blank" rel="noopener"><img src="https://cdn.jsdelivr.net/gh/simple-icons/simple-icons/icons/whatsapp.svg" alt="wa">WhatsApp</a>
      <a class="soc-btn" href="https://github.com/BerMatMods" target="_blank" rel="noopener"><img src="https://cdn.jsdelivr.net/gh/simple-icons/simple-icons/icons/github.svg" alt="gh">GitHub</a>
      <a class="soc-btn" href="https://www.instagram.com/king_berrocal" target="_blank" rel="noopener"><img src="https://cdn.jsdelivr.net/gh/simple-icons/simple-icons/icons/instagram.svg" alt="ig">Instagram</a>
    </div>

    <div style="margin-top:16px;display:flex;gap:12px">
      <button class="cta" id="openModal">Iniciar sesión</button>
      <a href="#projects" class="cta" style="background:linear-gradient(90deg,var(--accent1),var(--accent2));color:#fff;">Ver Proyectos</a>
    </div>
  </div>
</div>

  </main>  <section class="wrap" id="projects">
    <h2 style="text-align:center;font-family:'Orbitron';color:var(--neon);margin-bottom:18px">Proyectos Destacados</h2>
    <div class="grid">
      <article class="project">
        <h3>⚡ BerMat-Bot MD 🔥</h3>
        <p>Bot de WhatsApp completo, ejecutable en Termux, con juegos (Tres en Raya con emojis), generación de stickers, comandos personalizados y prefijo <strong>.BerMat</strong>. Personalización romántica en el menú y respuestas tipo IA.</p>
        <div class="tags"><span class="tag">WhatsApp</span><span class="tag">Termux</span><span class="tag">Python/Node</span></div>
      </article><article class="project">
    <h3>🧠 IA Aprendiz (F.A.M.A)</h3>
    <p>Sistema conversacional ligero para Termux con aprendizaje básico, respuesta contextual y mejoras visuales. Diseñado para integración con bots y asistentes.</p>
    <div class="tags"><span class="tag">IA</span><span class="tag">Conversacional</span><span class="tag">Integrable</span></div>
  </article>

  <article class="project">
    <h3>📲 Clonador Estético WhatsApp</h3>
    <p>Interfaz visual que replica estética de conversación para demostraciones y presentaciones (simulada). Incluye audios IA y efectos visuales. Siempre usado con fines legítimos.</p>
    <div class="tags"><span class="tag">UI</span><span class="tag">Animación</span><span class="tag">Demo</span></div>
  </article>

  <article class="project">
    <h3>🎮 Juegos & Utilidades</h3>
    <p>Mini juegos (Tres en Raya, Ahorcado), generadores de stickers, y utilidades para moderación de chats y automatización.</p>
    <div class="tags"><span class="tag">Juegos</span><span class="tag">Stickers</span><span class="tag">Automatización</span></div>
  </article>

  <article class="project">
    <h3>🌐 Presentaciones Web</h3>
    <p>Páginas HTML/CSS/JS con animaciones, banners y efectos visuales para proyectos y portfolios (como esta página).</p>
    <div class="tags"><span class="tag">Web</span><span class="tag">Animación</span><span class="tag">Portfolio</span></div>
  </article>

  <article class="project">
    <h3>🛠 Servicios Profesionales</h3>
    <p>Desarrollo e integración de bots, automatizaciones en Termux, asesoría técnica y creación de interfaces visuales.</p>
    <div class="tags"><span class="tag">Consultoría</span><span class="tag">Deploy</span><span class="tag">Soporte</span></div>
  </article>
</div>

<h2 style="margin-top:36px;font-family:'Orbitron';color:var(--neon);">Servicios</h2>
<div class="services">
  <div class="service"><h4>Creación de Bots</h4><p>Diseño, programación e implementación de bots para WhatsApp con módulos personalizados.</p></div>
  <div class="service"><h4>Automatización</h4><p>Scripting en Termux, Python y Node para tareas repetitivas y control desde chat.</p></div>
  <div class="service"><h4>Soporte & Consultoría</h4><p>Asesoría técnica, documentación y despliegue de proyectos.</p></div>
</div>

<div style="margin-top:26px;text-align:center">
  <a class="soc-btn" href="https://github.com/BerMatMods" target="_blank" rel="noopener"><img src="https://cdn.jsdelivr.net/gh/simple-icons/simple-icons/icons/github.svg" alt="gh">Visita mi GitHub</a>
  <a class="soc-btn" href="https://wa.me/51937556459" target="_blank" rel="noopener"><img src="https://cdn.jsdelivr.net/gh/simple-icons/simple-icons/icons/whatsapp.svg" alt="wa">Contáctame</a>
</div>

  </section>  <footer class="sitefoot">
    <div style="font-weight:700">© 2025 ⚡ BerMatModZ ⚡ — Anth'Zz Berrocal</div>
    <div class="footer-links">
      <a href="https://www.instagram.com/king_berrocal" target="_blank" class="soc-btn"><img src="https://cdn.jsdelivr.net/gh/simple-icons/simple-icons/icons/instagram.svg">Instagram</a>
      <a href="https://www.facebook.com/anthzzberrocal" target="_blank" class="soc-btn"><img src="https://cdn.jsdelivr.net/gh/simple-icons/simple-icons/icons/facebook.svg">Facebook</a>
      <a href="https://www.tiktok.com/@tuningcar321" target="_blank" class="soc-btn"><img src="https://cdn.jsdelivr.net/gh/simple-icons/simple-icons/icons/tiktok.svg">TikTok</a>
    </div>
  </footer>  <!-- Modal Login / Register -->  <div class="modal" id="modal">
    <div class="modal-card">
      <div style="display:flex;justify-content:space-between;align-items:center;margin-bottom:8px">
        <div style="font-weight:800;font-family:'Orbitron'">Iniciar Sesión</div>
        <button id="closeModal" style="background:transparent;border:none;color:#ccc;font-weight:700;cursor:pointer">✕</button>
      </div><form id="loginForm">
    <div class="form-row">
      <input type="email" id="email" placeholder="Correo electrónico" required>
    </div>
    <div class="form-row">
      <input type="password" id="password" placeholder="Contraseña" required>
    </div>
    <div style="display:flex;gap:10px;margin-bottom:10px">
      <button type="submit" class="btn-primary" style="flex:1">Entrar</button>
      <button type="button" id="showRegister" style="background:transparent;border:1px solid rgba(255,255,255,0.06);color:#fff">Registrarse</button>
    </div>
    <div style="font-size:13px;color:#cfe;display:flex;justify-content:space-between;align-items:center">
      <a href="#" id="forgot">¿Olvidaste tu contraseña?</a>
      <div style="font-size:12px;color:#99e">Iniciar con redes</div>
    </div>

    <div style="margin-top:12px;display:grid;grid-template-columns:1fr 1fr;gap:8px">
      <button type="button" onclick="socialAuth('google')" style="background:linear-gradient(90deg,#ff4b2b,#ff416c);color:#fff">Google</button>
      <button type="button" onclick="socialAuth('facebook')" style="background:linear-gradient(90deg,#1877f2,#4c69ba);color:#fff">Facebook</button>
    </div>
  </form>
</div>

  </div>  <div class="cta-wrap">
    <button class="cta" id="openModal2">Contactar</button>
  </div>  <script>
    // -------------------- Partículas ligeras --------------------
    const canvas = document.getElementById('particles');
    const ctx = canvas.getContext('2d');
    let w = canvas.width = innerWidth;
    let h = canvas.height = innerHeight;
    const parts = [];
    function rand(min,max){return Math.random()*(max-min)+min}
    for(let i=0;i<70;i++){parts.push({x:Math.random()*w,y:Math.random()*h,r:rand(0.6,2.6),vx:rand(-0.2,0.6),vy:rand(-0.2,0.2),alpha:rand(0.05,0.25)})}
    function resize(){w=canvas.width=innerWidth;h=canvas.height=innerHeight}
    addEventListener('resize',resize)
    function draw(){ctx.clearRect(0,0,w,h);for(let p of parts){p.x+=p.vx;p.y+=p.vy; if(p.x>w+10)p.x=-10; if(p.x<-10)p.x=w+10; if(p.y>h+10)p.y=-10; if(p.y<-10)p.y=h+10; ctx.beginPath();ctx.fillStyle='rgba(0,255,225,'+p.alpha+')';ctx.arc(p.x,p.y,p.r,0,Math.PI*2);ctx.fill() }requestAnimationFrame(draw)}
    draw();

    // -------------------- Modal logic --------------------
    const modal = document.getElementById('modal');
    const openModal = document.getElementById('openModal');
    const closeModal = document.getElementById('closeModal');
    const openModal2 = document.getElementById('openModal2');
    openModal.addEventListener('click',()=>modal.classList.add('show'));
    closeModal.addEventListener('click',()=>modal.classList.remove('show'));
    openModal2.addEventListener('click',()=>{modal.classList.add('show');document.getElementById('email').focus()});

    // simple form submit (local) - you'll replace this with your backend
    document.getElementById('loginForm').addEventListener('submit',function(e){e.preventDefault();const em=document.getElementById('email').value;alert('Sesión iniciada: '+em+' (esto es un placeholder, conecta con tu backend)');modal.classList.remove('show')});

    document.getElementById('showRegister').addEventListener('click',function(){
      // Simple register flow demo
      const em=prompt('Introduce tu correo para registrar');
      if(em){alert('Cuenta creada: '+em+' (placeholder). Revisa tu correo para confirmar (si lo implementas).')}
    })

    document.getElementById('forgot').addEventListener('click',function(e){e.preventDefault();const em=prompt('Introduce tu correo para recibir instrucciones de recuperación');if(em)alert('Se ha enviado enlace de recuperación a: '+em+' (placeholder)')});

    function socialAuth(provider){alert('Autenticación con '+provider+' (placeholder). Puedo ayudarte a integrar OAuth si quieres.')}

    // small accessibility: close modal on Esc
    addEventListener('keydown',e=>{if(e.key==='Escape')modal.classList.remove('show')})
  </script></body>
</html>
