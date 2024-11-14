<!DOCTYPE html>
<html lang="es">
<head>
    <meta charset="UTF-8">
    <title>Tienda de Camisetas Estampadas</title>
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
        <form id="pedidoForm" action="https://formspree.io/f/xvgorbja" method="POST">
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

    <div id="miModal">
        <p>¡Gracias por realizar su pedido!</p>
        <div>
            <p>Para más información contáctanos</p>
            <a href="https://wa.me/5491154943154" target="_blank">+54 9 11 5494-3154</a>
        </div>
    </div>

    <footer>
        <p>Contacto:</p>
        <a href="https://wa.me/5491154943154" target="_blank">+54 9 11 5494-3154</a>
    </footer>
</body>
</html>
