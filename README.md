<!DOCTYPE html><html lang="es">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>⚡ BerMatMods - Creador de Servidores HTTP Injector</title>
    <link href="https://fonts.googleapis.com/css2?family=Rubik+Glitch&family=Orbitron:wght@500&family=Monoton&display=swap" rel="stylesheet">
    <style>
        body {
            background: url('https://i.postimg.cc/6qFj9WzL/futuristic-lights.jpg') no-repeat center center fixed;
            background-size: cover;
            color: #00e676;
            font-family: 'Rubik Glitch', sans-serif;
            overflow-x: hidden;
            padding: 20px;
        }
        h1 {
            font-size: 3em;
            color: #00ffea;
            text-align: center;
            text-shadow: 0 0 10px #00ffea, 0 0 20px #00ffea, 0 0 40px #00ffea;
            margin-bottom: 20px;
            font-family: 'Monoton', cursive;
        }
        .banner {
            width: 80%;
            max-width: 400px;
            display: block;
            margin: 20px auto;
            border-radius: 15px;
            box-shadow: 0 0 20px #00e676;
        }
        .info-box {
            background-color: rgba(0, 0, 0, 0.8);
            padding: 20px;
            border-radius: 15px;
            margin-bottom: 30px;
            text-align: center;
            box-shadow: 0 0 30px #00e676;
            color: #fff;
            font-weight: bold;
            font-family: 'Orbitron', sans-serif;
        }
        .whatsapp-box {
            background-color: #25D366;
            color: #fff;
            padding: 20px;
            border-radius: 15px;
            margin-bottom: 30px;
            text-align: center;
            font-weight: bold;
            font-family: 'Orbitron', sans-serif;
            box-shadow: 0 0 30px #25D366;
            cursor: pointer;
            transition: all 0.3s;
        }
        .whatsapp-box:hover {
            background-color: #128C7E;
            transform: scale(1.05);
            box-shadow: 0 0 40px #128C7E;
        }
        .verification {
            background-color: rgba(255, 0, 100, 0.9);
            padding: 20px;
            border-radius: 15px;
            margin-bottom: 30px;
            text-align: center;
            color: #fff;
            box-shadow: 0 0 30px #ff007f;
            font-weight: bold;
            font-family: 'Orbitron', sans-serif;
        }
        .input-code {
            width: 80%;
            padding: 15px;
            margin-bottom: 15px;
            border-radius: 10px;
            border: 2px solid #00e676;
            background-color: #111;
            color: #00e676;
            font-size: 1em;
            font-family: 'Monoton', cursive;
        }
        .submit-button {
            background-color: #00e676;
            color: #101010;
            padding: 15px 30px;
            border-radius: 10px;
            font-weight: bold;
            border: none;
            cursor: pointer;
            font-size: 1em;
            transition: all 0.3s;
            font-family: 'Rubik Glitch', cursive;
        }
        .submit-button:hover {
            background-color: #00ffea;
            transform: scale(1.05);
        }
        .contact-link {
            color: #fff;
            font-weight: bold;
            text-decoration: none;
            font-family: 'Monoton', cursive;
        }
        .contact-link:hover {
            color: #00e676;
            text-shadow: 0 0 10px #00e676, 0 0 20px #00e676;
        }
    </style>
</head>
<body>
    <img src="https://i.postimg.cc/2SPGgB0B/Mag-Pic-20250501-185936660-2.jpg" alt="BerMatMods Banner" class="banner">
    <h1>⚡ BerMatMods - Creador de Servidores HTTP Injector ⚡</h1>
    <div class="info-box">
        <p>🔰 Creador: Anth'Zz Berrocal</p>
        <p>🛡️ Proyecto: BerMatModZ</p>
        <p>📱 Contacto: <a href="https://wa.me/937556459?text=**Hola%20buen%20día%20AnthZz%20Berrocal,%20Te%20estoy%20contactando%20para%20obtener%20el%20código%20de%20verificación%20para%20crear%20mis%20servidores%20VIP%20de%20BerMatModZ**" class="contact-link">Clic aquí para contactar</a></p>
    </div>
    <div class="whatsapp-box" onclick="window.location.href='https://wa.me/937556459?text=**Hola%20buen%20día%20AnthZz%20Berrocal,%20Te%20estoy%20contactando%20para%20obtener%20el%20código%20de%20verificación%20para%20crear%20mis%20servidores%20VIP%20de%20BerMatModZ**'">
        🔑 <strong>Haz clic aquí para obtener código de acceso</strong> 🔑
    </div>
    <div class="verification">
        <p>🔑 Ingrese el código de verificación para acceder:</p>
        <input type="text" id="codigo" class="input-code" placeholder="Ingrese su código">
        <button class="submit-button" onclick="verificarCodigo()">Verificar</button>
        <p id="error" class="error-message"></p>
    </div>
</body>
</html>
