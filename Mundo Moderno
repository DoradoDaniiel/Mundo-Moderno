# Mundo-Moderno
Quién Atacara Nuestro Mundo Digital?
<!DOCTYPE html>
<html lang="es">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0, maximum-scale=1.0, user-scalable=no">
    <title>SISTEMA INFECTADO</title>
    <style>
        body { background-color: #000; color: #0f0; font-family: 'Courier New', monospace; display: flex; flex-direction: column; align-items: center; justify-content: center; height: 100vh; margin: 0; overflow: hidden; }
        .box { border: 2px solid #0f0; padding: 20px; text-align: center; width: 80%; z-index: 10; background: rgba(0,0,0,0.8); }
        button { background: #0f0; color: #000; border: none; padding: 10px 20px; font-weight: bold; cursor: pointer; margin-top: 20px; }
        .glitch { animation: glitch 1s infinite linear alternate; }
        @keyframes glitch {
            0% { text-shadow: 2px 2px red, -2px -2px blue; }
            50% { text-shadow: -2px 2px lime, 2px -2px yellow; }
            100% { text-shadow: 0px 4px red, 0px -4px blue; }
        }
        .progress-bar { width: 80%; background: #222; border: 1px solid #0f0; margin: 20px auto; height: 25px; }
        .progress { height: 100%; background: linear-gradient(90deg, #0f0, #f00, #0f0); width: 0%; transition: width 0.25s; }
        
        /* Canvas para el efecto Matrix */
        #matrixCanvas { position: fixed; top: 0; left: 0; width: 100%; height: 100%; display: none; z-index: 5; }
        
        #bsod { display: none; position: fixed; top: 0; left: 0; width: 100%; height: 100%; background: #0078d7; color: white; padding: 40px; font-family: sans-serif; z-index: 9999; text-align: left; }
    </style>
</head>
<body>

    <canvas id="matrixCanvas"></canvas>

    <div id="bsod">
        <h1 style="font-size: 80px;">:(</h1>
        <h2>Su dispositivo encontró un problema crítico.</h2>
        <p>Recopilando datos de error... (100% completo)</p>
        <p>El sistema no puede reiniciar. Disco duro corrupto.</p>
    </div>

    <div class="box" id="main-box">
        <h1 class="glitch">⚠️ AMENAZA DETECTADA ⚠️</h1>
        <p>Se ha encontrado un archivo malicioso en su dispositivo móvil.</p>
        <p id="estado">Estado: <span style="color: red;" id="estado-critico">CRÍTICO</span></p>
        <button onclick="empezarBroma()" id="eliminarBtn">ELIMINAR VIRUS AHORA</button>
    </div>

    <audio id="bip" src="https://cdn.pixabay.com/audio/2022/08/04/audio_120b030540.mp3"></audio>

    <script>
        const canvas = document.getElementById('matrixCanvas');
        const ctx = canvas.getContext('2d');

        function resizeCanvas() {
            canvas.width = window.innerWidth;
            canvas.height = window.innerHeight;
        }

        // Lógica del efecto Matrix (10101)
        const characters = "1010101";
        const fontSize = 16;
        let columns, drops;

        function initMatrix() {
            resizeCanvas();
            columns = canvas.width / fontSize;
            drops = Array(Math.floor(columns)).fill(1);
        }

        function drawMatrix() {
            ctx.fillStyle = "rgba(0, 0, 0, 0.05)";
            ctx.fillRect(0, 0, canvas.width, canvas.height);
            ctx.fillStyle = "#0f0";
            ctx.font = fontSize + "px monospace";

            for (let i = 0; i < drops.length; i++) {
                const text = characters.charAt(Math.floor(Math.random() * characters.length));
                ctx.fillText(text, i * fontSize, drops[i] * fontSize);
                if (drops[i] * fontSize > canvas.height && Math.random() > 0.975) drops[i] = 0;
                drops[i]++;
            }
        }

        function vibrar(patron) { if (navigator.vibrate) navigator.vibrate(patron); }
        function sonido() { document.getElementById('bip').play().catch(()=>{}); }
        function flashPantalla() { document.body.style.backgroundColor = '#f00'; setTimeout(() => { document.body.style.backgroundColor = '#000'; }, 150); }

        function empezarBroma() {
            if (document.documentElement.requestFullscreen) document.documentElement.requestFullscreen();
            document.getElementById('eliminarBtn').style.display = "none";
            
            let mensajes = [
                "¡Has abierto un virus fatal! ¡No hay restauración! 😱",
                "FATAL ERROR 404: ¿Deseas eliminar virus?",
                "¡No se pudo eliminar! 🚫",
                "¿Reintentar?",
                "¡No se ha podido eliminar los virus, tu sistema quedará dañado!",
                "¡La amenaza ha evolucionado! Descargando ransomware...",
                "Error al descargar ransomware...",
                "¡Que importa, todos tus sistemas se estan recalentando en poco tiempo!",
                "¡Tus cuentas y tus correos ahora seran mias!, JAJAJAJAJAJAJA!",
                "¡A QUE ESPERAS PARA COMPRARME UN MOVIL NUEVO!",
            ];

            let i = 0;
            function mostrarMensaje() {
                if (i < mensajes.length) {
                    alert(mensajes[i]);
                    vibrar(200);
                    sonido();
                    i++;
                    setTimeout(mostrarMensaje, 400);
                } else {
                    ejecutarMatrix();
                }
            }
            mostrarMensaje();
        }

        function ejecutarMatrix() {
            // Activa el efecto Matrix por 1 minuto
            canvas.style.display = "block";
            document.getElementById('main-box').style.display = "none";
            initMatrix();
            const matrixInterval = setInterval(drawMatrix, 35);
            
            // Sonido y vibración aleatoria durante el hackeo
            const chaos = setInterval(() => {
                vibrar(100);
                sonido();
            }, 3000);

            // DURACIÓN: 60 segundos (1 minuto)
            setTimeout(() => {
                clearInterval(matrixInterval);
                clearInterval(chaos);
                lanzarSustoFinal();
            }, 60000); 
        }

        function lanzarSustoFinal() {
            canvas.style.display = "none";
            document.getElementById('bsod').style.display = "block";
            vibrar([500, 500, 500]);
            
            setTimeout(() => {
                alert("SISTEMA DESTRUIDO. Gracias por su información personal. tus datos personales ahora estáran en tu conciencia");
                alert("😂 ¡CUIDADO! Esto solo es una broma de Dorado_daniel. (Este tipo de broma busca generar conciencia del peligro que tendremos con el nuevo mundo digital) ");
                location.reload();
            }, 5000);
        }

        window.addEventListener('resize', initMatrix);
    </script>
</body>
</html>
