<!DOCTYPE html><html lang="es">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>⚡ BerMatMods - Creador de Servidores HTTP Injector</title>
    <link href="https://fonts.googleapis.com/css2?family=Rubik+Glitch&family=Orbitron:wght@500&display=swap" rel="stylesheet">
    <style>
        body {
            background: url('https://i.postimg.cc/8czJWtZw/futuristic-bg.jpg') no-repeat center center fixed;
            background-size: cover;
            color: #00e676;
            font-family: 'Orbitron', sans-serif;
            overflow-x: hidden;
            padding: 20px;
        }
        h1 {
            font-size: 3em;
            color: #00ffea;
            text-align: center;
            text-shadow: 0 0 10px #00ffea, 0 0 20px #00ffea, 0 0 40px #00ffea;
            margin-bottom: 30px;
        }
        .banner {
            width: 100%;
            max-width: 500px;
            display: block;
            margin: 20px auto;
            border-radius: 15px;
            box-shadow: 0 0 20px #00e676;
            animation: float 6s ease-in-out infinite alternate;
        }
        @keyframes float {
            0% { transform: translateY(0); }
            100% { transform: translateY(-15px); }
        }
        .server-options {
            background-color: rgba(0, 0, 0, 0.8);
            padding: 20px;
            border-radius: 15px;
            margin-bottom: 30px;
            box-shadow: 0 0 30px #00e676;
        }
        .server-options button {
            background-color: #00e676;
            color: #101010;
            border: none;
            padding: 15px 30px;
            margin: 10px;
            border-radius: 10px;
            font-weight: bold;
            font-size: 1em;
            cursor: pointer;
            transition: all 0.3s;
        }
        .server-options button:hover {
            background-color: #00ffea;
            transform: scale(1.05);
        }
        .verification {
            background-color: rgba(255, 0, 100, 0.8);
            padding: 20px;
            border-radius: 15px;
            margin-bottom: 30px;
            text-align: center;
            color: #fff;
            box-shadow: 0 0 30px #ff007f;
            font-weight: bold;
        }
        .input-code {
            width: 80%;
            padding: 15px;
            margin-bottom: 15px;
            border-radius: 10px;
            border: 2px solid #00e676;
            background-color: #222;
            color: #00e676;
            font-family: 'Rubik Glitch', cursive;
            font-size: 1em;
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
        }
        .submit-button:hover {
            background-color: #00ffea;
            transform: scale(1.05);
        }
        .error-message {
            color: #ff007f;
            font-weight: bold;
            margin-top: 15px;
        }
    </style>
    <script>
        function verificarCodigo() {
            const codigo = document.getElementById('codigo').value;
            if (codigo === 'BerMat123') {
                alert('✅ Acceso concedido. Bienvenido a BerMatMods!');
            } else {
                document.getElementById('error').innerHTML = '❌ Código incorrecto. Para poder acceder a este contenido debes comprar el acceso a través de mi creador. <a href="https://wa.me/937556459?text=**Hola%20buen%20día%20AnthZz%20Berrocal,%20Te%20estoy%20contactando%20para%20obtener%20el%20código%20de%20verificación%20para%20crear%20mis%20servidores%20VIP%20de%20BerMatModZ**" style="color: #ff007f; font-weight: bold;">Clic aquí para comprar</a>';
            }
        }
    </script>
</head>
<body>
    <img src="https://i.postimg.cc/2SPGgB0B/Mag-Pic-20250501-185936660-2.jpg" alt="BerMatMods Banner" class="banner">
    <h1>⚡ BerMatMods - Creador de Servidores HTTP Injector ⚡</h1>
    <div class="server-options">
        <button>Crear Servidor para Bitel</button>
        <button>Crear Servidor para Entel</button>
        <button>Crear Servidor para Claro</button>
        <button>Crear Servidor para Movistar</button>
    </div>
    <div class="verification">
        <p>🔑 Ingrese el código de verificación para acceder:</p>
        <input type="text" id="codigo" class="input-code" placeholder="Ingrese su código">
        <button class="submit-button" onclick="verificarCodigo()">Verificar</button>
        <p id="error" class="error-message"></p>
    </div>
</body>
</html>
