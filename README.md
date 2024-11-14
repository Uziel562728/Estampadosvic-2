<!DOCTYPE html>
<html lang="es">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Tienda de Camisetas Estampadas</title>
    <link rel="stylesheet" href="styles.css">
    <style>
        /* Estilos para la ventana emergente */
        .modal {
            display: none; /* Oculta la ventana por defecto */
            position: fixed;
            z-index: 1; /* Asegura que esté sobre el contenido */
            left: 0;
            top: 0;
            width: 100%; /* Ancho completo */
            height: 100%; /* Alto completo */
            background-color: rgba(0, 0, 0, 0.5); /* Fondo semitransparente */
            overflow: auto; /* Permite desplazamiento si es necesario */
            padding-top: 100px;
        }

        /* Contenedor de la ventana emergente */
        .modal-content {
            background-color: #fff;
            margin: 5% auto;
            padding: 20px;
            border: 1px solid #888;
            width: 80%;
            max-width: 400px;
            text-align: center;
            border-radius: 10px;
        }

        /* Estilo del botón de cierre */
        .close {
            color: #aaa;
            float: right;
            font-size: 28px;
            font-weight: bold;
        }

        .close:hover,
        .close:focus {
            color: black;
            text-decoration: none;
            cursor: pointer;
        }

        .modal p {
            color: green; /* Mensaje de agradecimiento en color verde */
            font-size: 1.5em;
            font-weight: bold;
        }

        /* Estilos para el texto y el logo de WhatsApp */
        .whatsapp-info {
            margin-top: 20px;
            color: #333;
            font-size: 1.1em;
        }

        .whatsapp-info a {
            text-decoration: none;
            color: #25D366; /* Verde WhatsApp */
            font-weight: bold;
        }

        .whatsapp-info img {
            width: 30px;
            vertical-align: middle;
            margin-left: 10px;
        }
    </style>
    <script>
        // Función para mostrar la ventana emergente
        function mostrarMensaje(event) {
            event.preventDefault(); // Evita el envío del formulario de inmediato
            document.getElementById("miModal").style.display = "block"; // Muestra la ventana emergente

            // Después de mostrar la ventana emergente, enviamos el formulario
            setTimeout(function() {
                // Obtiene el formulario y envíalo a Formspree
                document.getElementById("pedidoForm").submit(); 
            }, 1000); // Espera 1 segundo antes de enviar para asegurar que el mensaje se vea
        }

        // Función para cerrar la ventana emergente y redirigir a la página principal
        function cerrarModal() {
            document.getElementById("miModal").style.display = "none"; // Cierra la ventana emergente
            window.location.href = '/'; // Redirige a la página principal (ajustar el enlace según sea necesario)
        }
    </script>
</head>
<body>
    <header>
        <h1>Tienda de Camisetas Estampadas</h1>
        <p>Encuentra camisetas con estampados de 1, 2 o 3 colores</p>
    </header>

    <section class="productos">
        <h2>Productos</h2>
        <div class="camiseta">
            <h3>Camiseta Estampada de 1 Color</h3>
            <p>Precio: $10.00</p>
        </div>
        <div class="camiseta">
            <h3>Camiseta Estampada de 2 Colores</h3>
            <p>Precio: $15.00</p>
        </div>
        <div class="camiseta">
            <h3>Camiseta Estampada de 3 Colores</h3>
            <p>Precio: $20.00</p>
        </div>
    </section>

    <section class="formulario">
        <h2>Realiza tu pedido</h2>
        <form id="pedidoForm" action="https://formspree.io/f/xvgorbja" method="POST" onsubmit="mostrarMensaje(event)">
            <label for="nombre">Nombre:</label>
            <input type="text" id="nombre" name="nombre" required placeholder="Ingresa tu nombre">

            <label for="color">Número de colores:</label>
            <select id="color" name="color" required>
                <option value="1">1 Color</option>
                <option value="2">2 Colores</option>
                <option value="3">3 Colores</option>
            </select>

            <label for="cantidad">Cantidad:</label>
            <input type="number" id="cantidad" name="cantidad" min="1" required placeholder="Ingresa la cantidad">

            <label for="telefono">Número de Teléfono (Argentina):</label>
            <input type="tel" id="telefono" name="telefono" pattern="^11\d{8}$" required placeholder="Ej: 1112345678">

            <label for="direccion">Dirección:</label>
            <input type="text" id="direccion" name="direccion" required placeholder="Ingresa tu dirección">

            <button type="submit">Enviar Pedido</button>
        </form>
    </section>

    <!-- Ventana emergente -->
    <div id="miModal" class="modal">
        <div class="modal-content">
            <span class="close" onclick="cerrarModal()">&times;</span>
            <p>¡Gracias por realizar su pedido!</p>
            <div class="whatsapp-info">
                <p>Para más información contáctanos</p>
                <a href="https://wa.me/5491154943154" target="_blank">
                    <img src="https://upload.wikimedia.org/wikipedia/commons/6/6b/WhatsApp.svg" alt="WhatsApp">
                    +54 9 11 5494-3154
                </a>
            </div>
        </div>
    </div>

    <!-- Sección de pie de página con el color de fondo negro -->
    <div class="contacto" style="background-color: #000; color: white; padding: 20px; width: 100%; text-align: center;">
        <footer>
            <p>Contacto:</p>
            <a href="https://wa.me/5491154943154" target="_blank" style="text-decoration: none;">
                <img src="https://upload.wikimedia.org/wikipedia/commons/6/6b/WhatsApp.svg" alt="WhatsApp" style="width: 30px; vertical-align: middle;">
                +54 9 11 5494-3154
            </a>
        </footer>
    </div>
</body>
</html>
