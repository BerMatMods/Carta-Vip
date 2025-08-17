```jsx
import React, { useState, useEffect } from "react";

const App = () => {
  const [activeSection, setActiveSection] = useState(0);
  const [isLoaded, setIsLoaded] = useState(false);
  const [currentImageIndex, setCurrentImageIndex] = useState(0);
  const [mousePosition, setMousePosition] = useState({ x: 0, y: 0 });
  const [scrollY, setScrollY] = useState(0);
  const [isMenuOpen, setIsMenuOpen] = useState(false);

  const images = [
    "https://images.unsplash.com/photo-1507238691740-157033c2737b?ixlib=rb-4.0.3&ixid=M3wxMjA3fDB8MHxwaG90by1wYWdlfHx8fGVufDB8fHx8fA%3D%3D&auto=format&fit=crop&w=1200&q=80",
    "https://images.unsplash.com/photo-1451187580459-43490e0e48b9?ixlib=rb-4.0.3&ixid=M3wxMjA3fDB8MHxwaG90by1wYWdlfHx8fGVufDB8fHx8fA%3D%3D&auto=format&fit=crop&w=1200&q=80",
    "https://images.unsplash.com/photo-1543269865-cbf427effbad?ixlib=rb-4.0.3&ixid=M3wxMjA3fDB8MHxwaG90by1wYWdlfHx8fGVufDB8fHx8fA%3D%3D&auto=format&fit=crop&w=1200&q=80",
    "https://images.unsplash.com/photo-1504384308090-c894fdcc538d?ixlib=rb-4.0.3&ixid=M3wxMjA3fDB8MHxwaG90by1wYWdlfHx8fGVufDB8fHx8fA%3D%3D&auto=format&fit=crop&w=1200&q=80"
  ];

  const sections = [
    "Inicio",
    "Sobre Mí",
    "Proyectos",
    "Desarrollo",
    "Amor",
    "Habilidades",
    "Visión",
    "Contacto"
  ];

  useEffect(() => {
    setIsLoaded(true);
    
    const interval = setInterval(() => {
      setCurrentImageIndex(prev => (prev + 1) % images.length);
    }, 6000);

    const handleMouseMove = (e) => {
      setMousePosition({ x: e.clientX, y: e.clientY });
    };

    const handleScroll = () => {
      setScrollY(window.scrollY);
    };

    window.addEventListener('mousemove', handleMouseMove);
    window.addEventListener('scroll', handleScroll);
    
    return () => {
      clearInterval(interval);
      window.removeEventListener('mousemove', handleMouseMove);
      window.removeEventListener('scroll', handleScroll);
    };
  }, []);

  const handleScroll = (index) => {
    setActiveSection(index);
    document.getElementById(`section-${index}`)?.scrollIntoView({ behavior: 'smooth' });
    setIsMenuOpen(false);
  };

  const FloatingElement = ({ children, delay = 0, size = "w-4 h-4", color = "bg-blue-400", customStyle = {} }) => (
    <div 
      className={`${size} ${color} rounded-full absolute opacity-15 animate-pulse`}
      style={{
        left: `${Math.random() * 100}%`,
        top: `${Math.random() * 100}%`,
        animationDelay: `${delay}s`,
        animationDuration: `${4 + Math.random() * 4}s`,
        ...customStyle
      }}
    >
      {children}
    </div>
  );

  const TechCard = ({ title, description, icon, delay = 0, children }) => (
    <div 
      className="bg-white/15 backdrop-blur-sm rounded-2xl p-8 shadow-xl border border-white/20 transform transition-all duration-700 hover:scale-105 hover:shadow-2xl hover:bg-white/25"
      style={{
        opacity: isLoaded ? 1 : 0,
        transform: isLoaded ? 'translateY(0)' : 'translateY(30px)',
        transitionDelay: `${delay}s`
      }}
    >
      <div className="text-4xl mb-6">{icon}</div>
      <h3 className="text-2xl font-bold text-white mb-4">{title}</h3>
      <p className="text-gray-200 leading-relaxed">{description}</p>
      {children}
    </div>
  );

  const SkillBar = ({ name, level, color = "from-blue-500 to-purple-600" }) => (
    <div className="mb-6">
      <div className="flex justify-between mb-2">
        <span className="font-semibold text-white">{name}</span>
        <span className="text-gray-300">{level}%</span>
      </div>
      <div className="w-full bg-white/20 rounded-full h-3 overflow-hidden">
        <div 
          className={`h-3 rounded-full transition-all duration-1000 ${color}`}
          style={{ width: `${level}%` }}
        ></div>
      </div>
    </div>
  );

  const TestimonialCard = ({ quote, author, role }) => (
    <div className="bg-white/10 backdrop-blur-sm rounded-2xl p-6 border border-white/20 hover:bg-white/15 transition-all duration-300">
      <div className="text-4xl text-blue-300 mb-4 opacity-50">"</div>
      <p className="text-gray-200 italic mb-4 leading-relaxed">{quote}</p>
      <div className="flex items-center">
        <div className="w-10 h-10 bg-gradient-to-r from-blue-500 to-purple-600 rounded-full flex items-center justify-center text-white font-bold mr-3">
          {author.split(' ').map(n => n[0]).join('')}
        </div>
        <div>
          <div className="font-semibold text-white">{author}</div>
          <div className="text-sm text-gray-300">{role}</div>
        </div>
      </div>
    </div>
  );

  return (
    <div className="min-h-screen bg-gradient-to-br from-slate-900 via-purple-900 to-slate-900 text-white relative overflow-x-hidden">
      {/* Animated Background */}
      <div className="fixed inset-0 z-0">
        {/* Gradient background */}
        <div className="absolute inset-0 bg-gradient-to-br from-slate-900 via-purple-900 to-slate-900"></div>
        
        {/* Animated background image */}
        <div 
          className="absolute inset-0 transition-all duration-2000"
          style={{
            backgroundImage: `url(${images[currentImageIndex]})`,
            backgroundSize: 'cover',
            backgroundPosition: 'center',
            opacity: 0.15,
            transform: `translateY(${scrollY * 0.5}px)`
          }}
        ></div>
        
        {/* Floating particles */}
        {[...Array(25)].map((_, i) => (
          <FloatingElement 
            key={i} 
            delay={i * 0.4} 
            size={["w-1 h-1", "w-2 h-2", "w-3 h-3"][Math.floor(Math.random() * 3)]}
            color={["bg-blue-400", "bg-purple-400", "bg-pink-400", "bg-cyan-400", "bg-yellow-400"][Math.floor(Math.random() * 5)]}
            customStyle={{
              animationDuration: `${5 + Math.random() * 5}s`,
              filter: 'blur(1px)'
            }}
          />
        ))}
        
        {/* Grid pattern */}
        <div className="absolute inset-0 opacity-5">
          <div className="absolute inset-0" style={{
            backgroundImage: `
              linear-gradient(rgba(255,255,255,0.1) 1px, transparent 1px),
              linear-gradient(90deg, rgba(255,255,255,0.1) 1px, transparent 1px)
            `,
            backgroundSize: '40px 40px'
          }}></div>
        </div>
        
        {/* Mouse follower */}
        <div 
          className="fixed w-96 h-96 bg-gradient-radial from-purple-500/10 via-pink-500/5 to-transparent rounded-full pointer-events-none z-10 blur-3xl transition-all duration-100"
          style={{
            left: mousePosition.x - 192,
            top: mousePosition.y - 192,
          }}
        ></div>

        {/* Floating 3D elements */}
        <div 
          className="fixed w-32 h-32 border border-purple-500/30 rounded-full opacity-20 animate-spin"
          style={{
            left: '10%',
            top: '20%',
            animationDuration: '20s'
          }}
        ></div>
        <div 
          className="fixed w-24 h-24 border border-blue-500/30 rounded opacity-20 animate-spin"
          style={{
            right: '15%',
            top: '30%',
            animationDuration: '15s',
            animationDirection: 'reverse'
          }}
        ></div>
        <div 
          className="fixed w-40 h-40 border border-pink-500/30 rounded opacity-20 animate-pulse"
          style={{
            left: '20%',
            bottom: '20%',
            animationDuration: '8s'
          }}
        ></div>
      </div>

      {/* Navigation */}
      <nav className="fixed top-0 left-0 right-0 z-50 bg-black/80 backdrop-blur-md border-b border-white/10 transition-all duration-300">
        <div className="max-w-7xl mx-auto px-6 py-4">
          <div className="flex justify-between items-center">
            <div className="text-2xl font-bold bg-gradient-to-r from-blue-400 via-purple-400 to-pink-400 bg-clip-text text-transparent flex items-center">
              <span className="mr-2">⚡</span>
              Anth'Zz Berrocal
            </div>
            
            {/* Desktop menu */}
            <div className="hidden md:flex space-x-6">
              {sections.map((section, index) => (
                <button
                  key={section}
                  onClick={() => handleScroll(index)}
                  className={`py-2 px-4 rounded-full transition-all duration-300 group ${
                    activeSection === index 
                      ? 'bg-gradient-to-r from-blue-500 to-purple-600 text-white shadow-lg' 
                      : 'text-slate-300 hover:text-white hover:bg-white/10'
                  }`}
                >
                  {section}
                  {activeSection === index && (
                    <div className="absolute inset-0 rounded-full bg-gradient-to-r from-blue-500/20 to-purple-600/20 -z-10 group-hover:opacity-100 transition-opacity duration-300"></div>
                  )}
                </button>
              ))}
            </div>

            {/* Mobile menu button */}
            <button 
              className="md:hidden text-white p-2"
              onClick={() => setIsMenuOpen(!isMenuOpen)}
            >
              <div className="w-6 h-6 flex flex-col justify-center space-y-1">
                <div className={`h-0.5 bg-white transition-all duration-300 ${isMenuOpen ? 'rotate-45 translate-y-1.5' : ''}`}></div>
                <div className={`h-0.5 bg-white transition-all duration-300 ${isMenuOpen ? 'opacity-0' : ''}`}></div>
                <div className={`h-0.5 bg-white transition-all duration-300 ${isMenuOpen ? '-rotate-45 -translate-y-1.5' : ''}`}></div>
              </div>
            </button>
          </div>

          {/* Mobile menu */}
          {isMenuOpen && (
            <div className="md:hidden mt-4 bg-black/90 backdrop-blur-md rounded-lg p-4 animate-fadeIn">
              <div className="flex flex-col space-y-3">
                {sections.map((section, index) => (
                  <button
                    key={section}
                    onClick={() => handleScroll(index)}
                    className={`py-3 px-4 rounded-lg text-left transition-all duration-300 ${
                      activeSection === index 
                        ? 'bg-gradient-to-r from-blue-500 to-purple-600 text-white' 
                        : 'text-slate-300 hover:text-white hover:bg-white/10'
                    }`}
                  >
                    {section}
                  </button>
                ))}
              </div>
            </div>
          )}
        </div>
      </nav>

      {/* Hero Section */}
      <section id="section-0" className="min-h-screen flex items-center justify-center relative overflow-hidden pt-20">
        <div className="relative z-10 text-center max-w-6xl mx-auto px-6">
          <div className="mb-8">
            <h1 
              className="text-5xl md:text-7xl font-bold mb-6 leading-tight"
              style={{ animationDelay: '0.2s' }}
            >
              <span className="bg-gradient-to-r from-blue-400 via-purple-400 to-pink-400 bg-clip-text text-transparent">
                Anth'Zz Berrocal
              </span>
            </h1>
            <p className="text-xl md:text-2xl text-gray-300 mb-8">
              Desarrollador Full Stack • Innovador Tecnológico • Apasionado por el Fitness
            </p>
          </div>
          
          <div className="flex flex-col sm:flex-row gap-6 justify-center mb-12">
            <button 
              onClick={() => handleScroll(1)}
              className="bg-gradient-to-r from-blue-500 to-purple-600 text-white px-8 py-4 rounded-full text-lg font-semibold hover:scale-105 transition-all duration-300 shadow-lg hover:shadow-2xl flex items-center justify-center"
            >
              <span className="mr-2">👤</span>
              Conóceme
            </button>
            <button 
              onClick={() => handleScroll(2)}
              className="border-2 border-white/30 text-white px-8 py-4 rounded-full text-lg font-semibold hover:bg-white/10 hover:scale-105 transition-all duration-300 flex items-center justify-center"
            >
              <span className="mr-2">🚀</span>
              Mis Proyectos
            </button>
          </div>

          <div className="flex flex-wrap justify-center gap-8 text-gray-400 text-sm">
            <div className="flex items-center">
              <span className="mr-2">📍</span>
              Andahuaylas, Perú
            </div>
            <div className="flex items-center">
              <span className="mr-2">❤️</span>
              Jhorgina Briyidth
            </div>
            <div className="flex items-center">
              <span className="mr-2">📱</span>
              937556459
            </div>
            <div className="flex items-center">
              <span className="mr-2">🛡️</span>
              BerMatModZ
            </div>
          </div>

          {/* Scroll indicator */}
          <div className="absolute bottom-8 left-1/2 transform -translate-x-1/2 animate-bounce">
            <div className="w-6 h-10 border-2 border-white/30 rounded-full flex justify-center">
              <div className="w-1 h-3 bg-white/60 rounded-full mt-2 animate-pulse"></div>
            </div>
          </div>
        </div>

        {/* Floating badges */}
        <div className="absolute top-20 left-10 hidden lg:block">
          <div className="bg-gradient-to-r from-green-500 to-blue-500 text-white px-4 py-2 rounded-full text-sm font-semibold transform -rotate-6 hover:rotate-0 transition-transform duration-500 shadow-lg">
            💻 Tecnología
          </div>
        </div>
        
        <div className="absolute top-32 right-10 hidden lg:block">
          <div className="bg-gradient-to-r from-pink-500 to-purple-500 text-white px-4 py-2 rounded-full text-sm font-semibold transform rotate-6 hover:rotate-0 transition-transform duration-500 shadow-lg">
            ❤️ Amor
          </div>
        </div>
        
        <div className="absolute bottom-20 left-1/4 hidden lg:block">
          <div className="bg-gradient-to-r from-yellow-500 to-orange-500 text-white px-4 py-2 rounded-full text-sm font-semibold transform rotate-3 hover:rotate-0 transition-transform duration-500 shadow-lg">
            🏋️‍♂️ Fitness
          </div>
        </div>
      </section>

      {/* About Section */}
      <section id="section-1" className="py-20 relative">
        <div className="max-w-7xl mx-auto px-6">
          <div className="text-center mb-16">
            <h2 className="text-4xl md:text-5xl font-bold mb-6">
              <span className="bg-gradient-to-r from-blue-400 to-purple-400 bg-clip-text text-transparent">
                Sobre Mí
              </span>
            </h2>
            <p className="text-xl text-gray-300 max-w-3xl mx-auto">
              Mi viaje en el mundo del desarrollo tecnológico combina innovación, disciplina y pasión
            </p>
          </div>

          <div className="grid lg:grid-cols-2 gap-12 items-center">
            <div>
              <TechCard 
                title="Mi Filosofía" 
                description="Soy una persona apasionada por la tecnología y la innovación, que equilibra perfectamente el mundo del desarrollo con una vida fitness y una relación amorosa profunda. Mi carácter fuerte y lealtad son los pilares de todo lo que hago."
                icon="🎯"
                delay={0.1}
              />
              
              <div className="grid md:grid-cols-2 gap-6 mt-8">
                <TechCard 
                  title="Superación" 
                  description="Busco superarme constantemente en todos los aspectos de mi vida, tanto profesional como personal."
                  icon="🚀"
                  delay={0.3}
                />
                <TechCard 
                  title="Huella Digital" 
                  description="Mi objetivo es dejar una huella significativa en el mundo digital con proyectos únicos e innovadores."
                  icon="🌐"
                  delay={0.5}
                />
              </div>
            </div>
            
            <div className="relative">
              <div className="absolute inset-0 bg-gradient-to-tr from-blue-500/20 to-purple-500/20 rounded-2xl transform rotate-3"></div>
              <img 
                src="https://images.unsplash.com/photo-1555215695-3004980ad54e?ixlib=rb-4.0.3&ixid=M3wxMjA3fDB8MHxwaG90by1wYWdlfHx8fGVufDB8fHx8fA%3D%3D&auto=format&fit=crop&w=800&q=80" 
                alt="Anth'Zz Berrocal" 
                className="rounded-2xl shadow-2xl w-full relative z-10"
              />
              <div className="absolute -bottom-6 -right-6 bg-gradient-to-r from-blue-500 to-purple-600 text-white p-6 rounded-2xl shadow-lg transform hover:scale-110 transition-transform duration-300 cursor-pointer">
                <div className="text-3xl mb-2">❤️</div>
                <div className="font-bold">Jhorgina Briyidth</div>
                <div className="text-sm opacity-90">Mi mayor motivación</div>
              </div>
            </div>
          </div>

          {/* Stats */}
          <div className="grid md:grid-cols-4 gap-6 mt-16">
            {[
              { number: "5+", label: "Años de Experiencia", icon: "📅" },
              { number: "12+", label: "Proyectos Completados", icon: "🚀" },
              { number: "200+", label: "Horas de Código", icon: "💻" },
              { number: "365", label: "Días de Disciplina", icon: "🏋️‍♂️" }
            ].map((stat, index) => (
              <div 
                key={index}
                className="text-center p-6 bg-white/10 backdrop-blur-sm rounded-xl border border-white/20 hover:bg-white/15 transition-all duration-300"
                style={{ animationDelay: `${0.2 * index}s` }}
              >
                <div className="text-3xl mb-2">{stat.icon}</div>
                <div className="text-3xl font-bold bg-gradient-to-r from-blue-400 to-purple-400 bg-clip-text text-transparent mb-2">
                  {stat.number}
                </div>
                <div className="text-gray-300">{stat.label}</div>
              </div>
            ))}
          </div>
        </div>
      </section>

      {/* Projects Section */}
      <section id="section-2" className="py-20 relative">
        <div className="max-w-7xl mx-auto px-6">
          <div className="text-center mb-16">
            <h2 className="text-4xl md:text-5xl font-bold mb-6">
              <span className="bg-gradient-to-r from-blue-400 to-purple-400 bg-clip-text text-transparent">
                Proyectos Tecnológicos
              </span>
            </h2>
            <p className="text-xl text-gray-300 max-w-3xl mx-auto">
              Innovación constante en el desarrollo de soluciones tecnológicas con impacto real
            </p>
          </div>

          <div className="grid md:grid-cols-2 lg:grid-cols-3 gap-8">
            {[
              {
                title: "⚡ BerMat-Bot MD",
                description: "Bot de WhatsApp con inteligencia artificial avanzada, juegos interactivos, creación automática de stickers y menú con diseño romántico. Prefijo: .BerMat.",
                icon: "🤖",
                details: ["IA Avanzada", "Juegos Interactivos", "Stickers Automáticos", "Menú con Corazones"],
                color: "from-blue-500 to-cyan-500"
              },
              {
                title: "BerMat_Mods",
                description: "Bot de WhatsApp creado en Termux con integración de inteligencia artificial básica y sistema de stickers personalizados mediante comandos.",
                icon: "📱",
                details: ["Desarrollado en Termux", "IA Básica", "Stickers Personalizados", "Comandos Especiales"],
                color: "from-green-500 to-emerald-500"
              },
              {
                title: "BerMatModZ_ProyecBot",
                description: "Prototipo inicial de bots que implementa el clásico juego XO (Tres en Raya) y otras funcionalidades básicas de automatización.",
                icon: "🎮",
                details: ["Juego XO", "Automatización", "Prototipo Inicial", "Pruebas de Concepto"],
                color: "from-purple-500 to-pink-500"
              },
              {
                title: "FAMA",
                description: "Proyecto con filosofía Anonymous que representa poder, unidad y mentes brillantes trabajando juntas por causas justas.",
                icon: "🌐",
                details: ["Filosofía Anonymous", "Unidad", "Poder Colectivo", "Mentes Brillantes"],
                color: "from-indigo-500 to-purple-500"
              },
              {
                title: "Presentación Hacker",
                description: "Página web con animaciones en 3D/4D/5D, estilo cyberpunk y ciberseguridad, representando mi identidad digital completa.",
                icon: "🖥️",
                details: ["Animaciones 3D/4D/5D", "Estilo Cyberpunk", "Ciberseguridad", "Identidad Digital"],
                color: "from-red-500 to-orange-500"
              },
              {
                title: "WhatsApp Web Personalizada",
                description: "Interfaz de WhatsApp Web modificada con mi identidad digital (BerMatModZ), colores propios y menús exclusivos.",
                icon: "🎨",
                details: ["Identidad Digital", "Colores Personalizados", "Decoraciones Visuales", "Menús Exclusivos"],
                color: "from-yellow-500 to-pink-500"
              }
            ].map((project, index) => (
              <TechCard 
                key={index}
                title={project.title}
                description={project.description}
                icon={project.icon}
                delay={0.1 * index}
              >
                <div className="mt-4 pt-4 border-t border-gray-700">
                  <div className="flex flex-wrap gap-2">
                    {project.details.map((detail, i) => (
                      <span key={i} className={`bg-gradient-to-r ${project.color} text-white px-2 py-1 rounded text-xs`}>
                        {detail}
                      </span>
                    ))}
                  </div>
                </div>
              </TechCard>
            ))}
          </div>
        </div>
      </section>

      {/* Development Journey */}
      <section id="section-3" className="py-20 relative">
        <div className="max-w-7xl mx-auto px-6">
          <div className="text-center mb-16">
            <h2 className="text-4xl md:text-5xl font-bold mb-6">
              <span className="bg-gradient-to-r from-blue-400 to-purple-400 bg-clip-text text-transparent">
                Mi Desarrollo Personal
              </span>
            </h2>
            <p className="text-xl text-gray-300 max-w-3xl mx-auto">
              Un camino de crecimiento constante en tecnología, fitness y vida personal
            </p>
          </div>

          <div className="grid lg:grid-cols-2 gap-12">
            <div>
              <div className="bg-white/10 backdrop-blur-sm rounded-2xl p-8 border border-white/20 mb-8">
                <h3 className="text-2xl font-bold text-blue-400 mb-6 flex items-center">
                  <span className="mr-3">💻</span> Desarrollo Tecnológico
                </h3>
                <div className="space-y-4">
                  <div className="flex items-start space-x-3">
                    <div className="text-blue-400 mt-1">•</div>
                    <div>
                      <strong>Termux:</strong> Base fundamental para mis proyectos de bots y automatización
                    </div>
                  </div>
                  <div className="flex items-start space-x-3">
                    <div className="text-blue-400 mt-1">•</div>
                    <div>
                      <strong>AIDE:</strong> Desarrollo de aplicaciones Android en Java con API 23
                    </div>
                  </div>
                  <div className="flex items-start space-x-3">
                    <div className="text-blue-400 mt-1">•</div>
                    <div>
                      <strong>GitHub:</strong> Repositorios, colaboración y almacenamiento de todos mis proyectos
                    </div>
                  </div>
                  <div className="flex items-start space-x-3">
                    <div className="text-blue-400 mt-1">•</div>
                    <div>
                      <strong>APIs:</strong> Integración con inteligencia artificial para funcionalidades avanzadas
                    </div>
                  </div>
                  <div className="flex items-start space-x-3">
                    <div className="text-blue-400 mt-1">•</div>
                    <div>
                      <strong>Estilo:</strong> Interfaces llamativas con arte ASCII, emojis y tipografías decoradas
                    </div>
                  </div>
                </div>
              </div>

              <div className="bg-white/10 backdrop-blur-sm rounded-2xl p-8 border border-white/20">
                <h3 className="text-2xl font-bold text-green-400 mb-6 flex items-center">
                  <span className="mr-3">🏋️‍♂️</span> Vida Fitness
                </h3>
                <div className="space-y-4">
                  <p className="text-gray-300">
                    Practicante constante de gimnasio con un físico atlético y músculos definidos gracias a la disciplina diaria.
                  </p>
                  <div className="bg-gray-800/50 p-4 rounded-lg">
                    <strong>Philosophy:</strong> "El cuerpo fuerte refleja la mente fuerte. Cada entrenamiento es un paso hacia la mejor versión de uno mismo."
                  </div>
                  <div className="grid grid-cols-2 gap-4 mt-4">
                    <div className="text-center p-3 bg-gray-800/50 rounded">
                      <div className="text-2xl mb-1">💪</div>
                      <div className="text-sm">Disciplina</div>
                    </div>
                    <div className="text-center p-3 bg-gray-800/50 rounded">
                      <div className="text-2xl mb-1">🔥</div>
                      <div className="text-sm">Consistencia</div>
                    </div>
                    <div className="text-center p-3 bg-gray-800/50 rounded">
                      <div className="text-2xl mb-1">🧠</div>
                      <div className="text-sm">Mente Fuerte</div>
                    </div>
                    <div className="text-center p-3 bg-gray-800/50 rounded">
                      <div className="text-2xl mb-1">🏆</div>
                      <div className="text-sm">Superación</div>
                    </div>
                  </div>
                </div>
              </div>
            </div>

            <div>
              <div className="relative mb-8">
                <div className="absolute inset-0 bg-gradient-to-tr from-purple-500/20 to-pink-500/20 rounded-2xl transform -rotate-2"></div>
                <img 
                  src="https://images.unsplash.com/photo-1498050108023-c5249f4df085?ixlib=rb-4.0.3&ixid=M3wxMjA3fDB8MHxwaG90by1wYWdlfHx8fGVufDB8fHx8fA%3D%3D&auto=format&fit=crop&w=800&q=80" 
                  alt="Development" 
                  className="rounded-2xl shadow-2xl w-full relative z-10"
                />
              </div>
              
              <div className="bg-gradient-to-r from-blue-900/50 to-purple-900/50 backdrop-blur-sm rounded-2xl p-8 border border-white/20">
                <h3 className="text-2xl font-bold text-pink-400 mb-6 flex items-center">
                  <span className="mr-3">❤️</span> Mi Estilo Personal
                </h3>
                <div className="space-y-3 text-gray-300">
                  <p><strong>Combinación única:</strong> Hacker profesional + Romántico dedicado</p>
                  <p><strong>Características:</strong> Diseños con colores vivos, efectos visuales brillantes, arte ASCII</p>
                  <p><strong>Identidad visual:</strong> Fuerte y reconocible como BerMatModZ</p>
                  <p><strong>Preferencias:</strong> Interfaces llamativas con decoraciones artísticas</p>
                </div>
              </div>
            </div>
          </div>
        </div>
      </section>

      {/* Testimonials */}
      <section className="py-20 relative">
        <div className="max-w-6xl mx-auto px-6">
          <div className="text-center mb-16">
            <h2 className="text-4xl md:text-5xl font-bold mb-6">
              <span className="bg-gradient-to-r from-pink-400 to-purple-400 bg-clip-text text-transparent">
                Palabras de Amor
              </span>
            </h2>
            <p className="text-xl text-gray-300">
              Mensajes que definen mi relación con Jhorgina Briyidth
            </p>
          </div>

          <div className="grid md:grid-cols-2 gap-8">
            <TestimonialCard 
              quote="TE AMO MUCHÍSIMO MI REINA Briyidth Jhorgina 💕🌹"
              author="Anth'Zz Berrocal"
              role="Mensaje Romántico Corto"
            />
            
            <TestimonialCard 
              quote="Te amo mucho mi amor, mi reina hermosa. Te doy gracias por llegar a mi vida, eres lo más valioso que tengo y tengo miedo a perderte. Siempre te voy a amar en las buenas y en las malas, y sé que juntos vamos a salir adelante. 💕 Te amo muchísimo mi mami."
              author="Anth'Zz Berrocal"
              role="Mensaje Romántico Profundo"
            />
          </div>

          {/* Love timeline */}
          <div className="mt-16 relative">
            <div className="absolute left-1/2 transform -translate-x-1/2 h-full w-0.5 bg-gradient-to-b from-blue-400 to-purple-400"></div>
            
            <div className="space-y-12">
              {[
                { year: "2020", event: "Inicio de nuestra relación", icon: "💘" },
                { year: "2021", event: "Creación del bot BerMat-Bot MD en tu honor", icon: "🤖" },
                { year: "2022", event: "Proyecto FAMA inspirado en nuestro amor", icon: "🌐" },
                { year: "2023", event: "Desarrollo de proyectos con tu nombre en el código", icon: "💻" },
                { year: "2024", event: "Nuestro amor crece con cada proyecto tecnológico", icon: "❤️" }
              ].map((item, index) => (
                <div key={index} className={`flex items-center ${index % 2 === 0 ? 'flex-row' : 'flex-row-reverse'}`}>
                  <div className={`w-5/12 ${index % 2 === 0 ? 'text-right pr-8' : 'text-left pl-8'}`}>
                    <div className="bg-white/10 backdrop-blur-sm rounded-xl p-6 border border-white/20">
                      <div className="text-2xl mb-2">{item.icon}</div>
                      <div className="text-2xl font-bold text-blue-400 mb-2">{item.year}</div>
                      <div className="text-gray-300">{item.event}</div>
                    </div>
                  </div>
                  <div className="w-1/12 flex justify-center">
                    <div className="w-4 h-4 bg-gradient-to-r from-blue-400 to-purple-400 rounded-full border-4 border-black"></div>
                  </div>
                  <div className="w-5/12"></div>
                </div>
              ))}
            </div>
          </div>
        </div>
      </section>

      {/* Skills Section */}
      <section id="section-5" className="py-20 relative">
        <div className="max-w-7xl mx-auto px-6">
          <div className="text-center mb-16">
            <h2 className="text-4xl md:text-5xl font-bold mb-6">
              <span className="bg-gradient-to-r from-blue-400 to-purple-400 bg-clip-text text-transparent">
                Habilidades Técnicas
              </span>
            </h2>
            <p className="text-xl text-gray-300 max-w-3xl mx-auto">
              Dominio de múltiples lenguajes y herramientas para crear soluciones innovadoras
            </p>
          </div>

          <div className="grid lg:grid-cols-2 gap-12">
            <div>
              <h3 className="text-2xl font-bold text-blue-400 mb-8 flex items-center">
                <span className="mr-3">🐍</span> Lenguajes de Programación
              </h3>
              <div className="space-y-6">
                <SkillBar name="Python" level={90} color="from-green-500 to-blue-500" />
                <SkillBar name="JavaScript" level={85} color="from-yellow-500 to-orange-500" />
                <SkillBar name="Java" level={75} color="from-red-500 to-pink-500" />
                <SkillBar name="HTML/CSS" level={80} color="from-orange-500 to-red-500" />
                <SkillBar name="React" level={70} color="from-cyan-500 to-blue-500" />
              </div>
            </div>

            <div>
              <h3 className="text-2xl font-bold text-purple-400 mb-8 flex items-center">
                <span className="mr-3">🛠️</span> Herramientas y Entornos
              </h3>
              <div className="grid md:grid-cols-2 gap-6">
                {[
                  { name: "Termux", icon: "📱", color: "bg-green-500", desc: "Desarrollo móvil" },
                  { name: "AIDE", icon: "💻", color: "bg-blue-500", desc: "Android API 23" },
                  { name: "GitHub", icon: "🐙", color: "bg-gray-500", desc: "Repositorios" },
                  { name: "APIs", icon: "🔗", color: "bg-purple-500", desc: "Integración IA" },
                  { name: "Android Studio", icon: "📱", color: "bg-green-600", desc: "Desarrollo móvil" },
                  { name: "VS Code", icon: "⌨️", color: "bg-blue-600", desc: "Editor principal" }
                ].map((tool, index) => (
                  <div 
                    key={index}
                    className="bg-white/10 backdrop-blur-sm rounded-xl p-6 border border-white/20 hover:bg-white/20 transition-all duration-300 group cursor-pointer"
                  >
                    <div className={`w-12 h-12 ${tool.color} rounded-lg flex items-center justify-center text-white text-xl mb-4 mx-auto group-hover:scale-110 transition-transform duration-300`}>
                      {tool.icon}
                    </div>
                    <div className="text-center">
                      <div className="font-semibold text-white group-hover:text-blue-300 transition-colors duration-300">{tool.name}</div>
                      <div className="text-sm text-gray-400 mt-1">{tool.desc}</div>
                    </div>
                  </div>
                ))}
              </div>
            </div>
          </div>

          <div className="mt-16 bg-white/10 backdrop-blur-sm rounded-2xl p-8 border border-white/20">
            <h3 className="text-2xl font-bold text-yellow-400 mb-6">Estilo de Programación</h3>
            <div className="grid md:grid-cols-2 gap-8">
              <div>
                <h4 className="text-lg font-semibold text-blue-400 mb-4 flex items-center">
                  <span className="mr-2">🎨</span>
                  Interfaces Llamativas
                </h4>
                <p className="text-gray-300">
                  Prefiero interfaces decoradas con arte ASCII, emojis y tipografías llamativas que hagan que mis proyectos sean únicos y memorables.
                </p>
              </div>
              <div>
                <h4 className="text-lg font-semibold text-pink-400 mb-4 flex items-center">
                  <span className="mr-2">❤️</span>
                  Combinación de Estilos
                </h4>
                <p className="text-gray-300">
                  Me gusta combinar el estilo oscuro (hacker) con elementos románticos en el mismo diseño, creando una identidad visual única.
                </p>
              </div>
            </div>
          </div>
        </div>
      </section>

      {/* Vision Section */}
      <section className="py-20 relative">
        <div className="max-w-7xl mx-auto px-6">
          <div className="text-center mb-16">
            <h2 className="text-4xl md:text-5xl font-bold mb-6">
              <span className="bg-gradient-to-r from-blue-400 to-purple-400 bg-clip-text text-transparent">
                Visión y Metas
              </span>
            </h2>
            <p className="text-xl text-gray-300 max-w-3xl mx-auto">
              Mi camino hacia el futuro con objetivos claros en tecnología, ciberseguridad y vida personal
            </p>
          </div>

          <div className="grid lg:grid-cols-3 gap-8">
            {[
              {
                title: "Tecnología",
                items: [
                  "Crear bots de WhatsApp con inteligencia artificial avanzada",
                  "Expandir proyectos a aplicaciones completas (Android/Web)",
                  "Desarrollar soluciones innovadoras con impacto real",
                  "Construir comunidades alrededor de mis proyectos"
                ],
                icon: "🚀",
                color: "from-blue-500 to-cyan-500"
              },
              {
                title: "Ciberseguridad",
                items: [
                  "Profundizar en hacking ético",
                  "Construir identidad sólida como BerMatModZ",
                  "Contribuir a la seguridad digital",
                  "Proteger la privacidad en el mundo digital"
                ],
                icon: "🛡️",
                color: "from-green-500 to-emerald-500"
              },
              {
                title: "Vida Personal",
                items: [
                  "Mantener disciplina en el gimnasio",
                  "Cuidar a Jhorgina Briyidth",
                  "Ser ejemplo de constancia y superación",
                  "Compartir mis logros con mi compañera de vida"
                ],
                icon: "❤️",
                color: "from-pink-500 to-rose-500"
              }
            ].map((category, index) => (
              <div 
                key={index}
                className="bg-white/10 backdrop-blur-sm rounded-2xl p-8 border border-white/20 hover:bg-white/15 transition-all duration-300 group cursor-pointer"
              >
                <div className={`w-16 h-16 bg-gradient-to-r ${category.color} rounded-xl flex items-center justify-center text-2xl mb-6 mx-auto group-hover:scale-110 transition-transform duration-300`}>
                  {category.icon}
                </div>
                <h3 className="text-2xl font-bold text-center mb-6 group-hover:text-blue-300 transition-colors duration-300">{category.title}</h3>
                <ul className="space-y-3">
                  {category.items.map((item, i) => (
                    <li key={i} className="flex items-start text-gray-300 group-hover:text-white transition-colors duration-300">
                      <span className="text-green-400 mr-2 mt-1">✓</span>
                      {item}
                    </li>
                  ))}
                </ul>
              </div>
            ))}
          </div>
        </div>
      </section>

      {/* Contact Section */}
      <section id="section-7" className="py-20 relative">
        <div className="max-w-5xl mx-auto px-6 text-center">
          <div className="mb-12">
            <h2 className="text-4xl md:text-5xl font-bold mb-6">
              <span className="bg-gradient-to-r from-blue-400 to-purple-400 bg-clip-text text-transparent">
                Contacto
              </span>
            </h2>
            <p className="text-xl text-gray-300">
              Conectemos y colaboremos en proyectos innovadores
            </p>
          </div>

          <div className="grid md:grid-cols-3 gap-8 mb-12">
            <div className="bg-white/10 backdrop-blur-sm rounded-2xl p-8 border border-white/20 hover:scale-105 transition-all duration-300 group cursor-pointer">
              <div className="text-4xl mb-4 group-hover:scale-110 transition-transform duration-300">📱</div>
              <h3 className="text-xl font-bold mb-2">Teléfono</h3>
              <p className="text-gray-300">937556459</p>
            </div>
            <div className="bg-white/10 backdrop-blur-sm rounded-2xl p-8 border border-white/20 hover:scale-105 transition-all duration-300 group cursor-pointer">
              <div className="text-4xl mb-4 group-hover:scale-110 transition-transform duration-300">📧</div>
              <h3 className="text-xl font-bold mb-2">Email</h3>
              <p className="text-gray-300">anthzz.berrocal@email.com</p>
            </div>
            <div className="bg-white/10 backdrop-blur-sm rounded-2xl p-8 border border-white/20 hover:scale-105 transition-all duration-300 group cursor-pointer">
              <div className="text-4xl mb-4 group-hover:scale-110 transition-transform duration-300">📍</div>
              <h3 className="text-xl font-bold mb-2">Ubicación</h3>
              <p className="text-gray-300">Andahuaylas, Perú</p>
            </div>
          </div>

          <div className="bg-gradient-to-r from-blue-900/50 to-purple-900/50 backdrop-blur-sm rounded-2xl p-8 border border-white/20">
            <h3 className="text-2xl font-bold text-blue-400 mb-4">Alias Oficial</h3>
            <div className="text-3xl font-bold bg-gradient-to-r from-blue-400 to-purple-400 bg-clip-text text-transparent mb-4 flex items-center justify-center">
              BerMatModZ 🕶️
            </div>
            <p className="text-gray-300">
              "Apasionado por la tecnología y la innovación, balanceando el mundo hacker 
              con el romántico y fitness. Persona leal, disciplinada y de carácter fuerte."
            </p>
          </div>
        </div>
      </section>

      {/* Footer */}
      <footer className="relative py-12 border-t border-white/10">
        <div className="max-w-7xl mx-auto px-6">
          <div className="flex flex-col md:flex-row justify-between items-center">
            <div className="mb-6 md:mb-0">
              <div className="text-2xl font-bold bg-gradient-to-r from-blue-400 to-purple-400 bg-clip-text text-transparent mb-2">
                Anth'Zz Berrocal
              </div>
              <div className="text-gray-400 text-sm">
                Innovador tecnológico • Apasionado por el fitness • Romántico empedernido
              </div>
            </div>
            
            <div className="flex flex-wrap justify-center gap-6 text-sm text-gray-500">
              <span>© 2024 Anth'Zz Berrocal</span>
              <span>•</span>
              <span>Todos los derechos reservados</span>
              <span>•</span>
              <span>Andahuaylas, Perú</span>
              <span>•</span>
              <span>Jhorgina Briyidth ❤️</span>
            </div>
          </div>
          
          {/* Back to top */}
          <button 
            onClick={() => window.scrollTo({ top: 0, behavior: 'smooth' })}
            className="fixed bottom-8 right-8 bg-gradient-to-r from-blue-500 to-purple-600 text-white p-3 rounded-full shadow-lg hover:scale-110 transition-transform duration-300"
          >
            <svg xmlns="http://www.w3.org/2000/svg" className="h-6 w-6" fill="none" viewBox="0 0 24 24" stroke="currentColor">
              <path strokeLinecap="round" strokeLinejoin="round" strokeWidth={2} d="M5 10l7-7m0 0l7 7m-7-7v18" />
            </svg>
          </button>
        </div>
      </footer>
    </div>
  );
};

export default App;
```
