
<html lang="es">
<head>
  <meta charset="UTF-8" />
  <meta name="viewport" content="width=device-width, initial-scale=1.0"/>
  <title>La Magia del Barbero | Andahuaylas, Apurímac</title>
  <meta name="description" content="Barbería premium en Andahuaylas. Cortes, barbas, tratamientos faciales y capilares. El quinto corte gratis.">
  <meta name="author" content="AnthZz Berrocal">

  <!-- Google Fonts -->
  <link href="https://fonts.googleapis.com/css2?family=Playfair+Display:wght@700;800;900&family=Poppins:wght@300;400;500;600;700&display=swap" rel="stylesheet">

  <!-- Font Awesome -->
  <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.5.0/css/all.min.css"/>

  <!-- AOS Animations -->
  <link href="https://unpkg.com/aos@2.3.4/dist/aos.css" rel="stylesheet">

  <style>
    :root {
      --primary: #d4af37;
      --primary-dark: #b89a2e;
      --secondary: #000;
      --light: #f8f5f1;
      --cream: #fdfbf7;
      --gray: #555;
      --dark: #111;
      --shadow: 0 8px 30px rgba(0,0,0,0.18);
      --shadow-light: 0 4px 15px rgba(0,0,0,0.1);
      --glow: 0 0 20px rgba(212, 175, 55, 0.5);
      --glow-rgb: 0 0 15px rgba(255, 100, 50, 0.3),
                   0 0 25px rgba(0, 200, 255, 0.2),
                   0 0 35px rgba(150, 0, 255, 0.2);
      --radius: 14px;
      --transition: all 0.4s cubic-bezier(0.25, 0.8, 0.25, 1);
    }

    * {
      margin: 0;
      padding: 0;
      box-sizing: border-box;
    }

    body {
      font-family: 'Poppins', sans-serif;
      background: var(--cream);
      color: var(--gray);
      line-height: 1.7;
      overflow-x: hidden;
    }

    h1, h2, h3, h4 {
      font-family: 'Playfair Display', serif;
      color: var(--secondary);
    }

    h1 {
      font-size: 5.2rem;
      margin-bottom: 1rem;
      text-align: center;
      color: white;
      text-shadow: 4px 4px 12px rgba(0,0,0,0.8);
    }

    h2 {
      font-size: 3rem;
      margin-bottom: 2.5rem;
      text-align: center;
      position: relative;
    }

    h2::after {
      content: '';
      position: absolute;
      bottom: -14px;
      left: 50%;
      transform: translateX(-50%);
      width: 140px;
      height: 5px;
      background: var(--primary);
      border-radius: 3px;
      box-shadow: var(--glow);
    }

    p {
      margin-bottom: 1.1rem;
      color: var(--gray);
    }

    a {
      text-decoration: none;
      color: inherit;
      transition: var(--transition);
    }

    img {
      max-width: 100%;
      border-radius: var(--radius);
      display: block;
      box-shadow: var(--shadow-light);
    }

    .container {
      width: 90%;
      max-width: 1200px;
      margin: 0 auto;
      padding: 5rem 0;
    }

    /* Botón premium */
    .btn {
      display: inline-block;
      background: linear-gradient(45deg, var(--primary), var(--primary-dark));
      color: white;
      padding: 16px 36px;
      border-radius: 60px;
      font-weight: 600;
      font-size: 1.1rem;
      transition: var(--transition);
      border: none;
      cursor: pointer;
      box-shadow: var(--shadow);
      position: relative;
      overflow: hidden;
      z-index: 1;
    }

    .btn::before {
      content: '';
      position: absolute;
      top: 0;
      left: -100%;
      width: 100%;
      height: 100%;
      background: linear-gradient(90deg, transparent, rgba(255,255,255,0.4), transparent);
      transition: 0.8s;
      z-index: -1;
    }

    .btn:hover::before {
      left: 100%;
    }

    .btn:hover {
      transform: translateY(-5px);
      box-shadow: var(--shadow), var(--glow);
    }

    /* Header con fondo de barbería y luces RGB suaves */
    header {
      height: 100vh;
      background: 
        linear-gradient(rgba(0,0,0,0.75), rgba(0,0,0,0.75)),
        url('https://images.unsplash.com/photo-1599351431202-1e9f17a1705b?ixlib=rb-4.0.3&auto=format&fit=crop&w=1600&q=90') no-repeat center center/cover;
      display: flex;
      flex-direction: column;
      justify-content: center;
      align-items: center;
      text-align: center;
      color: white;
      position: relative;
      overflow: hidden;
    }

    header::before {
      content: '';
      position: absolute;
      top: 0;
      left: 0;
      width: 100%;
      height: 100%;
      background: 
        radial-gradient(circle at 20% 30%, rgba(255, 100, 50, 0.1) 0%, transparent 50%),
        radial-gradient(circle at 80% 70%, rgba(0, 200, 255, 0.1) 0%, transparent 50%),
        radial-gradient(circle at 50% 90%, rgba(150, 0, 255, 0.1) 0%, transparent 50%);
      pointer-events: none;
      z-index: 1;
      animation: pulseRGB 8s infinite alternate;
    }

    @keyframes pulseRGB {
      0% { opacity: 0.4; }
      100% { opacity: 0.7; filter: hue-rotate(10deg); }
    }

    header .content {
      z-index: 2;
      max-width: 900px;
      padding: 0 20px;
    }

    header p {
      font-size: 1.5rem;
      color: white;
      opacity: 0.95;
      max-width: 800px;
      margin: 1.6rem auto 2.8rem;
    }

    /* Navbar */
    nav {
      background: rgba(0,0,0,0.95);
      backdrop-filter: blur(10px);
      position: fixed;
      top: 0;
      width: 100%;
      z-index: 1000;
      box-shadow: 0 4px 20px rgba(0,0,0,0.2);
      border-bottom: 1px solid var(--primary);
      padding: 1rem 0;
    }

    nav ul {
      display: flex;
      justify-content: center;
      list-style: none;
      gap: 1.4rem;
    }

    nav ul li a {
      color: white;
      padding: 0.9rem 1.8rem;
      border-radius: 35px;
      font-weight: 500;
      font-size: 1.05rem;
      position: relative;
      overflow: hidden;
      border: 1px solid transparent;
    }

    nav ul li a:hover,
    nav ul li a.active {
      background: var(--primary);
      color: var(--secondary);
      transform: translateY(-4px);
      box-shadow: var(--shadow);
      border-color: white;
    }

    /* Sección con fondo oscuro */
    section.dark {
      background: var(--dark);
      color: white;
      padding: 6rem 0;
    }

    section.dark h2 {
      color: white;
    }

    section.dark h2::after {
      background: var(--primary);
    }

    section.dark p {
      color: #ccc;
    }

    /* Servicios */
    .services-grid {
      display: grid;
      grid-template-columns: repeat(auto-fit, minmax(300px, 1fr));
      gap: 2.8rem;
    }

    .service-card {
      background: white;
      border-radius: var(--radius);
      overflow: hidden;
      box-shadow: var(--shadow-light);
      transition: var(--transition);
      transform-style: preserve-3d;
      perspective: 1000px;
    }

    .service-card:hover {
      transform: translateY(-15px) rotateX(10deg);
      box-shadow: var(--shadow);
    }

    .service-card img {
      height: 240px;
      object-fit: cover;
      transition: transform 0.7s ease;
    }

    .service-card:hover img {
      transform: scale(1.15);
    }

    .service-content {
      padding: 2rem;
    }

    .service-content h3 {
      font-size: 1.7rem;
      color: var(--primary-dark);
    }

    /* Galería */
    .gallery-grid {
      display: grid;
      grid-template-columns: repeat(auto-fit, minmax(220px, 1fr));
      gap: 1.5rem;
    }

    .gallery-item {
      border-radius: var(--radius);
      overflow: hidden;
      box-shadow: var(--shadow-light);
      position: relative;
      transition: transform 0.4s ease;
    }

    .gallery-item:hover {
      transform: scale(1.08) rotate(3deg);
      box-shadow: var(--glow);
    }

    .gallery-item img {
      height: 200px;
      object-fit: cover;
      transition: transform 0.6s ease;
    }

    .gallery-item:hover img {
      transform: scale(1.2);
    }

    /* Promociones */
    .promo {
      background: #111;
      color: white;
      text-align: center;
      padding: 4rem 2.5rem;
      border-radius: var(--radius);
      max-width: 950px;
      margin: 3rem auto;
      box-shadow: 0 15px 40px rgba(0,0,0,0.3), var(--glow);
      position: relative;
      overflow: hidden;
    }

    .promo h3 {
      color: var(--primary);
      font-size: 2.6rem;
      margin-bottom: 1.5rem;
    }

    .loyalty-card {
      background: url('https://images.unsplash.com/photo-1605211850589-e3b51e8a8e3c?ixlib=rb-4.0.3&auto=format&fit=crop&w=800&q=80') no-repeat center center/cover;
      background-blend-mode: overlay;
      background-color: rgba(0,0,0,0.9);
      border: 4px solid var(--primary);
      border-radius: var(--radius);
      padding: 3rem;
      max-width: 650px;
      margin: 3rem auto;
      color: white;
      text-align: center;
      box-shadow: 0 20px 50px rgba(0,0,0,0.5), var(--glow);
      position: relative;
    }

    .loyalty-card::before {
      content: '✨';
      position: absolute;
      top: 15px;
      right: 25px;
      font-size: 2.2rem;
      animation: spin 4s linear infinite;
      text-shadow: 0 0 10px rgba(212,175,55,0.8);
    }

    @keyframes spin {
      0% { transform: rotate(0deg); }
      100% { transform: rotate(360deg); }
    }

    .loyalty-card h3 {
      color: var(--primary);
      font-size: 2.2rem;
      margin-bottom: 1.8rem;
    }

    .stamps {
      display: flex;
      justify-content: center;
      gap: 1.6rem;
      margin: 2.8rem 0;
      flex-wrap: wrap;
    }

    .stamp {
      width: 80px;
      height: 80px;
      background: rgba(255,255,255,0.1);
      border: 3px solid rgba(255,255,255,0.3);
      border-radius: 50%;
      display: flex;
      align-items: center;
      justify-content: center;
      font-size: 1.8rem;
      color: rgba(255,255,255,0.6);
      font-weight: bold;
      transition: var(--transition);
      cursor: pointer;
      backdrop-filter: blur(5px);
    }

    .stamp.active {
      background: var(--primary);
      color: white;
      border-color: white;
      transform: scale(1.3) rotate(12deg);
      box-shadow: var(--glow);
      animation: bounce 0.7s ease;
    }

    @keyframes bounce {
      0%, 20%, 50%, 80%, 100% { transform: translateY(0); }
      40% { transform: translateY(-12px); }
      60% { transform: translateY(-6px); }
    }

    /* Testimonios */
    .testimonials {
      display: flex;
      flex-wrap: wrap;
      gap: 2.2rem;
      justify-content: center;
    }

    .testimonial {
      background: white;
      padding: 2rem;
      border-radius: var(--radius);
      box-shadow: var(--shadow-light);
      max-width: 340px;
      text-align: center;
      color: var(--gray);
    }

    .testimonial i {
      color: var(--primary);
      font-size: 1.6rem;
    }

    .testimonial p {
      font-style: italic;
      color: #555;
    }

    .testimonial strong {
      color: var(--secondary);
      display: block;
      margin-top: 0.8rem;
      font-weight: 600;
    }

    /* Equipo */
    .team-grid {
      display: grid;
      grid-template-columns: repeat(auto-fit, minmax(260px, 1fr));
      gap: 2.5rem;
      margin-top: 2rem;
    }

    .team-member {
      text-align: center;
      background: white;
      padding: 2rem;
      border-radius: var(--radius);
      box-shadow: var(--shadow-light);
    }

    .team-member img {
      width: 120px;
      height: 120px;
      object-fit: cover;
      border: 4px solid var(--primary);
    }

    .team-member h4 {
      margin: 1rem 0 0.5rem;
      color: var(--primary-dark);
    }

    .team-member p {
      font-size: 0.95rem;
      color: var(--gray);
    }

    /* Blog ligero */
    .blog-grid {
      display: grid;
      grid-template-columns: repeat(auto-fit, minmax(300px, 1fr));
      gap: 2.5rem;
    }

    .blog-card {
      background: white;
      border-radius: var(--radius);
      overflow: hidden;
      box-shadow: var(--shadow-light);
    }

    .blog-card img {
      height: 200px;
      object-fit: cover;
    }

    .blog-content {
      padding: 1.8rem;
    }

    .blog-content h3 {
      font-size: 1.5rem;
      color: var(--primary-dark);
    }

    .blog-content p {
      color: var(--gray);
    }

    /* Formulario */
    .booking-container {
      display: flex;
      flex-wrap: wrap;
      gap: 3.5rem;
      align-items: stretch;
    }

    .booking-info, .booking-form {
      flex: 1;
      min-width: 300px;
    }

    .booking-form {
      background: white;
      padding: 3rem;
      border-radius: var(--radius);
      box-shadow: var(--shadow);
      border-top: 5px solid var(--primary);
    }

    .form-group {
      margin-bottom: 1.8rem;
    }

    .form-group label {
      display: block;
      margin-bottom: 0.7rem;
      font-weight: 600;
      color: var(--secondary);
    }

    .form-group input,
    .form-group select,
    .form-group textarea {
      width: 100%;
      padding: 14px;
      border: 2px solid #ddd;
      border-radius: var(--radius);
      font-family: 'Poppins', sans-serif;
      font-size: 1rem;
    }

    .form-group input:focus,
    .form-group select:focus {
      border-color: var(--primary);
      outline: none;
      box-shadow: 0 0 0 4px rgba(212,175,55,0.2);
    }

    /* WhatsApp Buttons */
    .whatsapp-btn {
      display: inline-flex;
      align-items: center;
      gap: 0.8rem;
      background: #25D366;
      color: white;
      padding: 14px 24px;
      border-radius: 60px;
      font-weight: 600;
      transition: var(--transition);
      margin: 0.8rem 0;
      box-shadow: 0 4px 15px rgba(37,211,102,0.3);
    }

    .whatsapp-btn:hover {
      transform: translateY(-3px);
      box-shadow: 0 8px 20px rgba(37,211,102,0.5);
    }

    /* Contacto */
    .contact-info div {
      margin-bottom: 1.8rem;
      display: flex;
      align-items: flex-start;
      gap: 1.2rem;
    }

    .contact-info i {
      color: var(--primary);
      font-size: 1.6rem;
      min-width: 32px;
    }

    /* Footer */
    footer {
      background: var(--secondary);
      color: white;
      text-align: center;
      padding: 5rem 0 3rem;
      margin-top: 6rem;
      border-top: 4px solid var(--primary);
      position: relative;
    }

    .signature {
      position: absolute;
      top: -45px;
      right: 40px;
      font-size: 1.2rem;
      font-weight: 600;
      color: var(--primary);
      background: rgba(0,0,0,0.85);
      padding: 10px 20px;
      border-radius: 35px;
      box-shadow: var(--glow);
    }

    .social-icons a {
      color: white;
      font-size: 2.1rem;
      margin: 0 1.5rem;
      transition: var(--transition);
    }

    .social-icons a:hover {
      color: var(--primary);
      transform: scale(1.4) rotate(15deg);
      text-shadow: var(--glow);
    }

    /* Responsive */
    @media (max-width: 768px) {
      h1 { font-size: 3.8rem; }
      h2 { font-size: 2.4rem; }
      .container { padding: 3.5rem 0; }
      nav ul { flex-direction: column; }
      .loyalty-card { padding: 2.2rem; }
      .stamp { width: 70px; height: 70px; font-size: 1.6rem; }
      header { height: auto; padding: 180px 20px 140px; }
    }
  </style>
</head>
<body>

  <!-- Cursor Glow (opcional, desactivado por simplicidad) -->

  <!-- Header -->
  <header id="inicio">
    <div class="content">
      <h1>La Magia del Barbero</h1>
      <p>Donde cada corte es una obra de arte. En el corazón de Andahuaylas, ofrecemos cortes impecables, diseño de barba, tratamientos faciales y capilares con atención personalizada y estilo clásico moderno. Tu transformación comienza aquí.</p>
      <a href="#reservas" class="btn">Reserva tu Cita Mágica</a>
    </div>
  </header>

  <!-- Navbar -->
  <nav>
    <ul>
      <li><a href="#inicio" class="active">Inicio</a></li>
      <li><a href="#servicios">Servicios</a></li>
      <li><a href="#galeria">Galería</a></li>
      <li><a href="#promociones">Fidelización</a></li>
      <li><a href="#testimonios">Clientes</a></li>
      <li><a href="#equipo">Equipo</a></li>
      <li><a href="#blog">Tips</a></li>
      <li><a href="#reservas">Reservar</a></li>
      <li><a href="#contacto">Contacto</a></li>
    </ul>
  </nav>

  <!-- Servicios -->
  <section id="servicios" class="container">
    <h2>Arte en Cada Corte</h2>
    <p>En <strong>La Magia del Barbero</strong>, no solo cortamos cabello, creamos identidad. Cada servicio es una experiencia única de lujo y precisión.</p>
    
    <div class="services-grid">
      <div class="service-card" data-aos="fade-up" data-aos-delay="100">
        <img src="https://images.unsplash.com/photo-1580480855173-483943e088d9?ixlib=rb-4.0.3&auto=format&fit=crop&w=800&q=90" alt="Corte de cabello">
        <div class="service-content">
          <h3>Corte de Cabello Premium</h3>
          <p>Diseñamos tu look ideal con tijera, navaja y pasión por el oficio tradicional. Desde fades hasta estilos clásicos.</p>
        </div>
      </div>
      <div class="service-card" data-aos="fade-up" data-aos-delay="200">
        <img src="https://images.unsplash.com/photo-1605497788044-5a32c7078486?ixlib=rb-4.0.3&auto=format&fit=crop&w=800&q=90" alt="Diseño de barba">
        <div class="service-content">
          <h3>Diseño de Barba de Élite</h3>
          <p>Perfilado profesional, simetría perfecta y productos de alta gama para una barba digna de un rey.</p>
        </div>
      </div>
      <div class="service-card" data-aos="fade-up" data-aos-delay="300">
        <img src="https://images.unsplash.com/photo-1599119732520-3ab707e86b5a?ixlib=rb-4.0.3&auto=format&fit=crop&w=800&q=90" alt="Tratamiento facial">
        <div class="service-content">
          <h3>Tratamiento Facial Completo</h3>
          <p>Limpieza profunda, exfoliación, vapor y mascarilla. Renueva tu piel como un verdadero caballero.</p>
        </div>
      </div>
      <div class="service-card" data-aos="fade-up" data-aos-delay="400">
        <img src="https://images.unsplash.com/photo-1622295056923-9dd5c8663240?ixlib=rb-4.0.3&auto=format&fit=crop&w=800&q=90" alt="Tratamiento capilar">
        <div class="service-content">
          <h3>Tratamiento Capilar Reparador</h3>
          <p>Hidratación, fortalecimiento y nutrición profunda. Ideal para cabellos dañados, secos o con caspa.</p>
        </div>
      </div>
      <div class="service-card" data-aos="fade-up" data-aos-delay="500">
        <img src="https://images.unsplash.com/photo-1584433144071-2b581c647b2c?ixlib=rb-4.0.3&auto=format&fit=crop&w=800&q=90" alt="Afeitado clásico">
        <div class="service-content">
          <h3>Afeitado Clásico con Navaja</h3>
          <p>La experiencia tradicional: espuma caliente, navaja afilada y toallas tibias. Suavidad extrema en cada pasada.</p>
        </div>
      </div>
      <div class="service-card" data-aos="fade-up" data-aos-delay="600">
        <img src="https://images.unsplash.com/photo-1607990281513-2c110f14a4bc?ixlib=rb-4.0.3&auto=format&fit=crop&w=800&q=90" alt="Peinado para eventos">
        <div class="service-content">
          <h3>Peinado para Eventos y Bodas</h3>
          <p>Para bodas, fiestas o fotos. Luce impecable en los momentos importantes con un estilo duradero y elegante.</p>
        </div>
      </div>
    </div>
  </section>

  <!-- Galería -->
  <section id="galeria" class="container dark">
    <h2>Galería de Estilo</h2>
    <p>Descubre algunos de nuestros trabajos más recientes. Cada corte es una transformación.</p>
    <div class="gallery-grid">
      <div class="gallery-item" data-aos="zoom-in" data-aos-delay="100"><img src="https://images.unsplash.com/photo-1580480855173-483943e088d9?ixlib=rb-4.0.3&auto=format&fit=crop&w=600&q=90" alt="Corte fade"></div>
      <div class="gallery-item" data-aos="zoom-in" data-aos-delay="200"><img src="https://images.unsplash.com/photo-1605497788044-5a32c7078486?ixlib=rb-4.0.3&auto=format&fit=crop&w=600&q=90" alt="Barba perfilada"></div>
      <div class="gallery-item" data-aos="zoom-in" data-aos-delay="300"><img src="https://images.unsplash.com/photo-1599119732520-3ab707e86b5a?ixlib=rb-4.0.3&auto=format&fit=crop&w=600&q=90" alt="Tratamiento facial"></div>
      <div class="gallery-item" data-aos="zoom-in" data-aos-delay="400"><img src="https://images.unsplash.com/photo-1584433144071-2b581c647b2c?ixlib=rb-4.0.3&auto=format&fit=crop&w=600&q=90" alt="Afeitado clásico"></div>
      <div class="gallery-item" data-aos="zoom-in" data-aos-delay="500"><img src="https://images.unsplash.com/photo-1607990281513-2c110f14a4bc?ixlib=rb-4.0.3&auto=format&fit=crop&w=600&q=90" alt="Peinado evento"></div>
      <div class="gallery-item" data-aos="zoom-in" data-aos-delay="600"><img src="https://images.unsplash.com/photo-1599351431202-1e9f17a1705b?ixlib=rb-4.0.3&auto=format&fit=crop&w=600&q=90" alt="Ambiente barbería"></div>
    </div>
  </section>

  <!-- Fidelización -->
  <section id="promociones" class="container">
    <h2>Programa de Fidelización: La Tarjeta Mágica</h2>
    <p>Cada visita te acerca más a una recompensa legendaria.</p>

    <div class="promo">
      <h3>✨ El Quinto Corte es un Hechizo Gratis ✨</h3>
      <p>Por cada servicio, sellamos tu tarjeta. Al completar 4 sellos, el <strong>quinto corte es GRATIS</strong>.</p>
      <p>Presenta tu tarjeta física después de cada corte para que te sellen tu visita.</p>
    </div>

    <div class="loyalty-card">
      <h3>Tu Tarjeta de Fidelización</h3>
      <p>Guarda esta tarjeta y preséntala cada vez que vengas. ¡Tu lealtad tiene premio!</p>

      <div class="stamps" id="stampContainer">
        <div class="stamp" data-id="1">1</div>
        <div class="stamp" data-id="2">2</div>
        <div class="stamp" data-id="3">3</div>
        <div class="stamp" data-id="4">4</div>
        <div class="stamp" data-id="5">5</div>
      </div>

      <button class="btn" id="claimButton">Sellar mi Corte →</button>
    </div>
  </section>

  <!-- Testimonios -->
  <section id="testimonios" class="container">
    <h2>Lo que Dicen Nuestros Clientes</h2>
    <p>Clientes satisfechos, estilos transformados. Aquí hablan desde el corazón.</p>
    <div class="testimonials" id="testimonialsContainer"></div>
  </section>

  <!-- Equipo -->
  <section id="equipo" class="container dark">
    <h2>Nuestro Equipo de Expertos</h2>
    <p>Profesionales con años de experiencia, pasión por el oficio y manos de oro.</p>
    <div class="team-grid">
      <div class="team-member">
        <img src="https://images.unsplash.com/photo-1560250097-0b9352761d85?ixlib=rb-4.0.3&auto=format&fit=crop&w=600&q=80" alt="Barbero">
        <h4>Carlos Mendoza</h4>
        <p>Barbero Senior con 12 años de experiencia. Especialista en cortes clásicos.</p>
      </div>
      <div class="team-member">
        <img src="https://images.unsplash.com/photo-1573496359143-7495f9b0b8b5?ixlib=rb-4.0.3&auto=format&fit=crop&w=600&q=80" alt="Estilista">
        <h4>Luis Fernández</h4>
        <p>Diseñador de barbas y tratamientos faciales. Innovador y detallista.</p>
      </div>
      <div class="team-member">
        <img src="https://images.unsplash.com/photo-1519085360753-af0119f7cbe7?ixlib=rb-4.0.3&auto=format&fit=crop&w=600&q=80" alt="Estilista">
        <h4>Jorge Linares</h4>
        <p>Experto en tratamientos capilares y peinados para eventos.</p>
      </div>
    </div>
  </section>

  <!-- Blog ligero -->
  <section id="blog" class="container">
    <h2>Consejos de Estilo</h2>
    <p>Pequeños tips para mantener tu look impecable entre visitas.</p>
    <div class="blog-grid">
      <div class="blog-card">
        <img src="https://images.unsplash.com/photo-1593030103066-0093718ef81a?ixlib=rb-4.0.3&auto=format&fit=crop&w=800&q=80" alt="Cuidado barba">
        <div class="blog-content">
          <h3>Cómo cuidar tu barba en casa</h3>
          <p>Lava, hidrata y peina diariamente. Usa aceite de barba para evitar la picazón.</p>
        </div>
      </div>
      <div class="blog-card">
        <img src="https://images.unsplash.com/photo-1583337130417-3346a1be7dee?ixlib=rb-4.0.3&auto=format&fit=crop&w=800&q=80" alt="Corte cabello">
        <div class="blog-content">
          <h3>Los cortes del momento en 2025</h3>
          <p>Desde el fade texturizado hasta el pompadour moderno, te mostramos las tendencias.</p>
        </div>
      </div>
      <div class="blog-card">
        <img src="https://images.unsplash.com/photo-1562322140-8baeececf3b3?ixlib=rb-4.0.3&auto=format&fit=crop&w=800&q=80" alt="Cliente satisfecho">
        <div class="blog-content">
          <h3>Por qué reservar es clave</h3>
          <p>Evita esperas, asegura tu horario y disfruta de un servicio personalizado.</p>
        </div>
      </div>
    </div>
  </section>

  <!-- Reservas -->
  <section id="reservas" class="container">
    <h2>Reserva tu Transformación</h2>
    <p>Llena el formulario y te contactaremos por WhatsApp para confirmar tu cita. ¡Tu estilo espera!</p>
    
    <div class="booking-container">
      <div class="booking-info">
        <h3>¿Por qué reservar?</h3>
        <p>Evita esperas, asegura tu horario y disfruta de un servicio personalizado sin interrupciones.</p>
        <p>¿Prefieres hablar directamente?</p>
        <a href="https://wa.me/51977355999" target="_blank" class="whatsapp-btn">
          <i class="fab fa-whatsapp"></i> WhatsApp: 977 355 999
        </a>
        <a href="https://wa.me/51931538059" target="_blank" class="whatsapp-btn">
          <i class="fab fa-whatsapp"></i> WhatsApp: 931 538 059
        </a>
      </div>

      <form class="booking-form" id="bookingForm">
        <div class="form-group">
          <label for="name">Nombre Completo</label>
          <input type="text" id="name" name="name" required placeholder="Ej. Juan Pérez">
        </div>
        <div class="form-group">
          <label for="phone">Teléfono (para WhatsApp)</label>
          <input type="tel" id="phone" name="phone" required placeholder="Ej. 987654321">
        </div>
        <div class="form-group">
          <label for="service">Servicio que deseas</label>
          <select id="service" name="service" required>
            <option value="">Selecciona un servicio</option>
            <option value="Corte de Cabello">Corte de Cabello</option>
            <option value="Diseño de Barba">Diseño de Barba</option>
            <option value="Tratamiento Facial">Tratamiento Facial</option>
            <option value="Tratamiento Capilar">Tratamiento Capilar</option>
            <option value="Afeitado Clásico">Afeitado Clásico con Navaja</option>
            <option value="Peinado para Eventos">Peinado para Eventos</option>
            <option value="Combo: Corte + Barba">Combo: Corte + Barba</option>
          </select>
        </div>
        <div class="form-group">
          <label for="date">Fecha deseada</label>
          <input type="date" id="date" name="date" required>
        </div>
        <div class="form-group">
          <label for="time">Hora preferida</label>
          <input type="time" id="time" name="time" required>
        </div>
        <div class="form-group">
          <label for="notes">Notas o preferencias</label>
          <textarea id="notes" name="notes" rows="3" placeholder="¿Tienes algún estilo en mente?"></textarea>
        </div>
        <button type="submit" class="btn">Reservar → Enviar a WhatsApp</button>
      </form>
    </div>
  </section>

  <!-- Contacto -->
  <section id="contacto" class="container dark">
    <h2>Encuéntranos en Andahuaylas</h2>
    <div class="contact-info">
      <div>
        <i class="fas fa-map-marker-alt"></i>
        <div>
          <strong>Dirección:</strong><br>
          Jr. Lima 123, Centro, Andahuaylas, Apurímac, Perú
        </div>
      </div>
      <div>
        <i class="fas fa-phone"></i>
        <div>
          <strong>WhatsApp:</strong><br>
          <a href="https://wa.me/51977355999">977 355 999</a> y <a href="https://wa.me/51931538059">931 538 059</a>
        </div>
      </div>
      <div>
        <i class="fas fa-clock"></i>
        <div>
          <strong>Horario:</strong><br>
          Lunes a Sábado: 8:00 AM – 7:00 PM<br>
          Domingo: 9:00 AM – 3:00 PM
        </div>
      </div>
      <div>
        <i class="fas fa-envelope"></i>
        <div>
          <strong>Email:</strong><br>
          <a href="mailto:lamagiadelbarbero.and@gmail.com">lamagiadelbarbero.and@gmail.com</a>
        </div>
      </div>
    </div>
  </section>

  <!-- Footer -->
  <footer>
    <div class="signature">by AnthZz Berrocal</div>
    <div class="container">
      <p>&copy; 2025 La Magia del Barbero. Todos los derechos reservados.</p>
      <p>Andahuaylas, Apurímac, Perú</p>
      <div class="social-icons">
        <a href="#"><i class="fab fa-facebook"></i></a>
        <a href="#"><i class="fab fa-instagram"></i></a>
        <a href="#"><i class="fab fa-tiktok"></i></a>
      </div>
      <p style="font-size: 0.95rem; margin-top: 1.2rem;">
        Diseñado con <span style="color: var(--primary);">✂️</span> para los caballeros que creen en la verdadera magia del estilo.
      </p>
    </div>
  </footer>

  <!-- Scripts -->
  <script src="https://unpkg.com/aos@2.3.4/dist/aos.js"></script>
  <script>
    AOS.init({ duration: 900, easing: 'ease-in-out', once: true });

    // Testimonios aleatorios
    const testimonials = [
      "¡Quedé como nuevo! El corte fue impecable y la atención, de otro nivel.",
      "La barba quedó perfecta. Desde que vine, no voy a otro lado.",
      "El quinto corte gratis es real. ¡Gracias por la magia!",
      "Ambiente clásico, música vintage y un barbero con manos de oro.",
      "Mi hijo quedó encantado. Volveremos cada mes.",
      "Tratamiento facial muy relajante. Mi piel quedó renovada.",
      "El combo corte + barba es lo mejor. 100% recomendado."
    ];
    const names = ["Carlos M.", "Jorge L.", "Andrés R.", "Luis F.", "Rosa T.", "Ana P.", "Miguel S."];

    const container = document.getElementById('testimonialsContainer');
    testimonials.forEach((text, i) => {
      const el = document.createElement('div');
      el.className = 'testimonial';
      el.innerHTML = `
        <i class="fas fa-star"></i>
        <p>"${text}"</p>
        <strong>— ${names[i]}</strong>
      `;
      container.appendChild(el);
      AOS.refresh();
    });

    // Sellado de tarjeta
    const stamps = document.querySelectorAll('.stamp');
    const claimButton = document.getElementById('claimButton');
    let filled = 0;

    claimButton.addEventListener('click', () => {
      if (filled < 4) {
        stamps[filled].classList.add('active');
        filled++;
        alert(`¡Sello #${filled} aplicado! Te faltan ${4-filled} para tu corte mágico.`);
      } else {
        alert("🎉 ¡Felicidades! Tu quinto corte es GRATIS. Presenta esta tarjeta.");
      }
    });

    // Formulario → WhatsApp
    document.getElementById('bookingForm').addEventListener('submit', function(e) {
      e.preventDefault();

      const name = document.getElementById('name').value;
      const phone = document.getElementById('phone').value;
      const service = document.getElementById('service').value;
      const date = document.getElementById('date').value;
      const time = document.getElementById('time').value;
      const notes = document.getElementById('notes').value || 'Sin notas';

      const message = `
🌟 *RESERVA EN "LA MAGIA DEL BARBERO"* 🌟

📌 *Nombre:* ${name}
📱 *Teléfono:* ${phone}
💈 *Servicio:* ${service}
📅 *Fecha:* ${date}
⏰ *Hora:* ${time}
📝 *Notas:* ${notes}

🔥 ¡Tu cita está en proceso! Pronto te confirmaremos. ¡Gracias por elegirnos! 💈
      `.trim();

      const encoded = encodeURIComponent(message);
      const numbers = ['51977355999', '51931538059'];
      const random = numbers[Math.floor(Math.random() * numbers.length)];
      window.open(`https://wa.me/${random}?text=${encoded}`, '_blank');
    });
  </script>

</body>
</html>
