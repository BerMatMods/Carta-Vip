# Crear-Servidores-Net
Para crear servidores VIP personalizados
<!DOCTYPE html><html lang="es">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>⚡ BerMatMods - Creador de Servidores HTTP Injector</title>
    <link href="https://fonts.googleapis.com/css2?family=Roboto+Mono:wght@300;700&family=Orbitron:wght@400;700&display=swap" rel="stylesheet">
    <style>
        body {
            background-color: #0f0f0f;
            color: #00ff7f;
            font-family: 'Roboto Mono', monospace;
            padding: 20px;
            overflow-x: hidden;
            animation: background-glow 5s infinite alternate;
        }
        @keyframes background-glow {
            0% { background-color: #0f0f0f; }
            100% { background-color: #0b3d0b; }
        }
        h1 {
            font-family: 'Orbitron', sans-serif;
            font-size: 3em;
            color: #00ff7f;
            text-align: center;
            margin-bottom: 20px;
            animation: glow 2s infinite alternate;
        }
        @keyframes glow {
            0% { text-shadow: 0 0 10px #00ff7f, 0 0 20px #00ff7f, 0 0 30px #00ff7f, 0 0 40px #00ff7f, 0 0 50px #00ff7f, 0 0 60px #00ff7f, 0 0 70px #00ff7f; }
            100% { text-shadow: 0 0 20px #00cc66, 0 0 30px #00cc66, 0 0 40px #00cc66, 0 0 50px #00cc66, 0 0 60px #00cc66, 0 0 70px #00cc66, 0 0 80px #00cc66; }
        }
        .server-container {
            background-color: #1a1a1a;
            border-radius: 15px;
            padding: 30px;
            box-shadow: 0 0 20px #00ff7f;
            margin-bottom: 20px;
            transition: transform 0.3s, box-shadow 0.3s;
        }
        .server-container:hover {
            transform: scale(1.02);
            box-shadow: 0 0 30px #00ff7f, 0 0 40px #00ff7f;
        }
        .server-button {
            background-color: #00ff7f;
            color: #0f0f0f;
            border: none;
            padding: 15px 30px;
            font-size: 1em;
            border-radius: 10px;
            cursor: pointer;
            font-weight: bold;
            margin: 10px 0;
            width: 100%;
        }
        .server-button:hover {
            background-color: #00cc66;
            transform: scale(1.05);
        }
        .verification {
            margin-top: 20px;
            background-color: #333;
            padding: 20px;
            border-radius: 10px;
            text-align: center;
            box-shadow: 0 0 15px #00ff7f;
        }
        .input-code {
            width: 80%;
            padding: 15px;
            font-size: 1em;
            margin-bottom: 15px;
            border-radius: 10px;
            border: 2px solid #00ff7f;
            background-color: #222;
            color: #00ff7f;
        }
        .submit-button {
            background-color: #00ff7f;
            color: #0f0f0f;
            padding: 15px 30px;
            border-radius: 10px;
            font-weight: bold;
            border: none;
            cursor: pointer;
            font-size: 1em;
        }
        .submit-button:hover {
            background-color: #00cc66;
            transform: scale(1.05);
        }
        .contact-link {
            color: #ff4500;
            font-weight: bold;
            text-decoration: none;
        }
        .social-container {
            margin-top: 30px;
            text-align: center;
            animation: fadeIn 2s ease-in-out;
        }
        .social-icon {
            width: 60px;
            margin: 10px;
            transition: transform 0.3s;
        }
        .social-icon:hover {
            transform: scale(1.2) rotate(10deg);
        }
        @keyframes fadeIn {
            from { opacity: 0; }
            to { opacity: 1; }
        }
    </style>
</head>
<body>
    <h1>⚡ BerMatMods - Creador de Servidores HTTP Injector ⚡</h1>
    <div class="server-container">
        <button class="server-button">Crear Servidor Bitel</button>
        <button class="server-button">Crear Servidor Entel</button>
        <button class="server-button">Crear Servidor Claro</button>
        <button class="server-button">Crear Servidor Movistar</button>
    </div>
    <div class="verification">
        <h2>🔒 Verificación</h2>
        <input type="text" placeholder="Ingresa tu código" id="code" class="input-code">
        <button onclick="verifyCode()" class="submit-button">Verificar</button>
        <p id="error-message" style="color: #ff4500; font-weight: bold;"></p>
    </div>
    <div class="social-container">
        <a href="https://wa.me/937556459"><img src="https://cdn-icons-png.flaticon.com/512/2111/2111728.png" class="social-icon" alt="WhatsApp"></a>
        <a href="https://www.instagram.com/anthzberrocal"><img src="https://cdn-icons-png.flaticon.com/512/2111/2111463.png" class="social-icon" alt="Instagram"></a>
        <a href="https://github.com/anthzberrocal"><img src="https://cdn-icons-png.flaticon.com/512/733/733609.png" class="social-icon" alt="GitHub"></a>
    </div>
    <script>
        function verifyCode() {
            const code = document.getElementById('code').value;
            if (code === 'BerMat123') {
                alert('✅ Código correcto. Bienvenido a BerMatMods.');
            } else {
                document.getElementById('error-message').innerHTML = "❌ Código incorrecto. <a href='https://wa.me/937556459' class='contact-link'>Contactar con mi creador</a>";
            }
        }
    </script>
</body>
</html>
