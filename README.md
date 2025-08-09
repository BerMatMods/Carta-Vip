<!DOCTYPE html>
<html lang="es">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0" />
<title>⚡ BerMatModZ | Anth'Zz Berrocal ⚡</title>
<link href="https://fonts.googleapis.com/css2?family=Orbitron:wght@600&family=Rajdhani:wght@500&display=swap" rel="stylesheet">
<style>
  body {
    margin: 0;
    font-family: 'Rajdhani', sans-serif;
    background: #0f0c29;
    color: #fff;
    overflow-x: hidden;
  }
  canvas#particles {
    position: fixed;
    top: 0;
    left: 0;
    width: 100%;
    height: 100%;
    z-index: -1;
  }
  header {
    text-align: center;
    padding: 50px 20px;
    background: rgba(0,0,0,0.6);
    animation: headerGlow 3s infinite alternate;
  }
  @keyframes headerGlow {
    from { text-shadow: 0 0 10px #00ffe1; }
    to { text-shadow: 0 0 30px #00ffe1, 0 0 20px #00ffe1; }
  }
  h1 {
    font-family: 'Orbitron', sans-serif;
    font-size: 3em;
    color: #00ffe1;
    white-space: nowrap;
    overflow: hidden;
    border-right: 3px solid #00ffe1;
    animation: typing 4s steps(30, end), blink 0.7s infinite;
  }
  @keyframes typing { from { width: 0; } to { width: 100%; } }
  @keyframes blink { 50% { border-color: transparent; } }
  .banner {
    text-align: center;
    padding: 15px;
    margin: 20px auto;
    border: 2px solid #00ffe1;
    border-radius: 12px;
    background: rgba(0,0,0,0.4);
    box-shadow: 0 0 20px #00ffe1;
    animation: bannerPulse 2s infinite alternate;
  }
  @keyframes bannerPulse { from { transform: scale(1); } to { transform: scale(1.05); } }
  .section {
    max-width: 1200px;
    margin: auto;
    padding: 30px 20px;
  }
  h2 {
    font-size: 2em;
    color: #00ffe1;
    margin-bottom: 15px;
    font-family: 'Orbitron', sans-serif;
  }
  .info-box {
    background: rgba(255,255,255,0.05);
    border-left: 5px solid #00ffe1;
    padding: 20px;
    border-radius: 15px;
    margin-bottom: 25px;
    font-size: 1.1em;
    box-shadow: 0 0 12px #00ffe1aa;
    transition: transform 0.3s ease;
  }
  .info-box:hover {
    transform: translateY(-5px) scale(1.02);
    box-shadow: 0 0 20px #00ffe1;
  }
  .social-icons {
    display: flex;
    gap: 15px;
    justify-content: center;
    flex-wrap: wrap;
    margin-top: 20px;
  }
  .social-icons a img {
    width: 50px;
    height: 50px;
    transition: transform 0.4s ease;
    filter: drop-shadow(0 0 5px #00ffe1);
  }
  .social-icons a img:hover {
    transform: scale(1.2) rotate(5deg);
  }
  .consultar-btn {
    display: inline-block;
    background: linear-gradient(90deg, #00ffe1, #00bfff);
    color: #000;
    padding: 12px 20px;
    border-radius: 8px;
    font-weight: bold;
    text-decoration: none;
    transition: 0.3s;
    margin-top: 15px;
  }
  .consultar-btn:hover {
    background: linear-gradient(90deg, #00bfff, #00ffe1);
    transform: scale(1.05);
  }
  footer {
    background: rgba(0,0,0,0.85);
    color: #aaa;
    text-align: center;
    padding: 20px;
    font-size: 0.9em;
  }
</style>
</head>
<body>
  <canvas id="particles"></canvas>
  <header>
    <h1>⚡ BerMatModZ ⚡</h1>
    <p>Respaldo Oficial por Anonymous | Bots, IA y Automatización</p>
  </header>

  <div class="banner">🚀 Proyecto del líder: BerMat-Bot MD 🔥</div>
  <div class="banner">💀 Respaldado por Anonymous | Seguridad y Libertad Digital</div>

  <section class="section">
    <h2>👤 Perfil Personal</h2>
    <div class="info-box">
      <p><strong>Nombre:</strong> Anth'Zz Berrocal</p>
      <p><strong>Alias:</strong> BerMatModZ</p>
      <p><strong>Ubicación:</strong> Andahuaylas, Perú</p>
      <p><strong>Especialización:</strong> Bots en Termux, IA, hacking visual, automatización avanzada.</p>
    </div>

    <h2>💼 Consultar</h2>
    <div class="info-box">
      <p>¿Quieres más información sobre mis paquetes y servicios? Contáctame directamente por WhatsApp.</p>
      <a class="consultar-btn" href="https://wa.me/51937556459?text=%2AHola%20AnthZz%20Berrocal%2C%20quiero%20m%C3%A1s%20informaci%C3%B3n%20sobre%20este%20paquete%2A" target="_blank">💬 Consultar a Anth'Zz Berrocal</a>
    </div>

    <h2>🚀 Proyectos</h2>
    <div class="info-box">
      <p>📌 <strong>BerMat-Bot MD:</strong> Bot multifuncional con IA integrada, comandos personalizados y sistema de automatización avanzada.</p>
      <p>📌 <strong>F.A.M.A:</strong> Sistema de gestión de clientes y automatización empresarial.</p>
      <p>📌 <strong>Clonador WhatsApp:</strong> Herramienta de respaldo y sincronización avanzada.</p>
    </div>

    <h2>🌐 Redes Sociales</h2>
    <div class="social-icons">
      <a href="https://wa.me/51937556459?text=%2AHola%20AnthZz%20Berrocal%2C%20vengo%20desde%20tu%20web%2A" target="_blank"><img src="https://cdn-icons-png.flaticon.com/512/733/733585.png" alt="WhatsApp"></a>
      <a href="https://github.com/BerMatMods" target="_blank"><img src="https://cdn-icons-png.flaticon.com/512/733/733553.png" alt="GitHub"></a>
      <a href="https://www.instagram.com/king_berrocal" target="_blank"><img src="https://cdn-icons-png.flaticon.com/512/733/733558.png" alt="Instagram"></a>
      <a href="https://www.facebook.com/share/16N6qCQLzm/" target="_blank"><img src="https://cdn-icons-png.flaticon.com/512/733/733547.png" alt="Facebook"></a>
      <a href="https://www.tiktok.com/@tuningcar321" target="_blank"><img src="https://cdn-icons-png.flaticon.com/512/3046/3046121.png" alt="TikTok"></a>
    </div>
  </section>

  <footer>
    © 2025 ⚡ BerMatModZ ⚡ | Desarrollado por Anth'Zz Berrocal
  </footer>

<script>
  // Animación de partículas estilo hacker
  const canvas = document.getElementById('particles');
  const ctx = canvas.getContext('2d');
  let particlesArray;
  canvas.width = window.innerWidth;
  canvas.height = window.innerHeight;

  class Particle {
    constructor() {
      this.x = Math.random() * canvas.width;
      this.y = Math.random() * canvas.height;
      this.size = Math.random() * 3 + 1;
      this.speedX = Math.random() * 1 - 0.5;
      this.speedY = Math.random() * 1 - 0.5;
      this.color = '#00ffe1';
    }
    update() {
      this.x += this.speedX;
      this.y += this.speedY;
      if (this.x < 0 || this.x > canvas.width) this.speedX *= -1;
      if (this.y < 0 || this.y > canvas.height) this.speedY *= -1;
    }
    draw() {
      ctx.fillStyle = this.color;
      ctx.beginPath();
      ctx.arc(this.x, this.y, this.size, 0, Math.PI * 2);
      ctx.fill();
    }
  }

  function initParticles() {
    particlesArray = [];
    for (let i = 0; i < 100; i++) {
      particlesArray.push(new Particle());
    }
  }
  function animateParticles() {
    ctx.clearRect(0, 0, canvas.width, canvas.height);
    particlesArray.forEach(p => { p.update(); p.draw(); });
    requestAnimationFrame(animateParticles);
  }
  window.addEventListener('resize', () => {
    canvas.width = window.innerWidth;
    canvas.height = window.innerHeight;
    initParticles();
  });
  initParticles();
  animateParticles();
</script>
</body>
</html>
