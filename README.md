<!DOCTYPE html>
<html lang="es">
<head>
  <meta charset="UTF-8" />
  <meta name="viewport" content="width=device-width, initial-scale=1.0"/>
  <title>Yape Fake Educativo</title>
  <style>
    body {
      margin: 0;
      font-family: 'Segoe UI', sans-serif;
      background: #f1f1f1;
    }

    .app {
      max-width: 400px;
      margin: 30px auto;
      background: white;
      border-radius: 15px;
      box-shadow: 0 0 15px rgba(0,0,0,0.1);
      overflow: hidden;
      padding: 20px;
    }

    .header {
      display: flex;
      align-items: center;
      gap: 15px;
    }

    .profile-pic {
      width: 60px;
      height: 60px;
      border-radius: 50%;
      object-fit: cover;
      border: 2px solid #7A00D9;
    }

    .balance {
      margin: 20px 0;
      text-align: center;
    }

    .balance h1 {
      color: #7A00D9;
      font-size: 2.5em;
    }

    #inputMonto {
      width: 100%;
      padding: 8px;
      margin-top: 8px;
      border: 1px solid #ccc;
      border-radius: 8px;
      font-size: 16px;
    }

    .formulario input {
      width: 100%;
      padding: 10px;
      margin: 10px 0;
      border: 1px solid #bbb;
      border-radius: 8px;
      font-size: 16px;
    }

    .formulario button {
      width: 100%;
      background: #7A00D9;
      color: white;
      padding: 12px;
      border: none;
      border-radius: 10px;
      font-size: 18px;
      cursor: pointer;
    }

    .formulario button:hover {
      background: #5e00aa;
    }

    .resultado {
      margin-top: 20px;
      text-align: center;
      font-weight: bold;
      color: green;
      animation: fade 1s ease-in-out;
    }

    footer {
      margin-top: 25px;
      font-size: 12px;
      color: #555;
      text-align: center;
      padding-top: 15px;
      border-top: 1px solid #ddd;
    }

    @keyframes fade {
      from { opacity: 0; }
      to { opacity: 1; }
    }
  </style>
</head>
<body>
  <div class="app">
    <div class="header">
      <img src="https://i.imgur.com/JyVmJ1e.jpg" alt="Foto de perfil" class="profile-pic">
      <div>
        <h2>Anth'Zz Berrocal</h2>
        <p>📱 937 556 459</p>
      </div>
    </div>

    <div class="balance">
      <p>Saldo disponible:</p>
      <h1>S/. <span id="monto">150.00</span></h1>
      <input type="number" id="inputMonto" placeholder="Editar monto...">
    </div>

    <div class="formulario">
      <input type="tel" id="numeroDestino" placeholder="Número de destino">
      <input type="number" id="montoEnvio" placeholder="Monto a enviar">
      <button onclick="simularYape()">✨ Yapear</button>
    </div>

    <div id="resultado" class="resultado"></div>

    <footer>
      ⚠️ Esta es una <strong>simulación educativa</strong>. No es una app real ni está afiliada a Yape.
    </footer>
  </div>

  <script>
    function simularYape() {
      const montoActual = document.getElementById("monto");
      const nuevoMonto = document.getElementById("inputMonto").value;
      if (nuevoMonto !== "") {
        montoActual.textContent = parseFloat(nuevoMonto).toFixed(2);
      }

      const numero = document.getElementById("numeroDestino").value;
      const monto = document.getElementById("montoEnvio").value;
      const resultado = document.getElementById("resultado");

      if (numero === "" || monto === "") {
        resultado.style.color = "red";
        resultado.textContent = "⚠️ Completa todos los campos.";
        return;
      }

      resultado.style.color = "green";
      resultado.innerHTML = `✅ Se ha enviado <strong>S/. ${monto}</strong> a <strong>${numero}</strong> exitosamente.`;

      // Reiniciar campos
      document.getElementById("numeroDestino").value = "";
      document.getElementById("montoEnvio").value = "";
    }
  </script>
</body>
</html>
