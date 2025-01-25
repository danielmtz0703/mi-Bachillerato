<!DOCTYPE html>
<html lang="es">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Bachillerato Tecnológico</title>
    <!-- Inclusión de Font Awesome para los íconos -->
    <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.0.0-beta3/css/all.min.css">
    <style>
        /* Colores personalizados */
        :root {
            --color-amarillo: #FFD700; /* Amarillo */
            --color-azul-rey: #003366; /* Azul rey */
            --color-guinda: #8B0000; /* Guinda */
        }

        /* Estilos generales */
        body {
            margin: 0;
            font-family: Arial, sans-serif;
            background-color: #f4f4f4;
            color: #333;
            
        }

        /* Encabezado */
        header {
            background-color: var(--color-azul-rey); /* Azul rey */
            color: #fff;
            padding: 10px 20px;
            display: flex;
            justify-content: space-between;
            align-items: center;
        }

        header .logo {
            font-size: 1.5rem;
            font-weight: bold;
        }

        nav {
            display: flex; /* Usar flexbox para el layout */
            justify-content: flex-end; /* Alinea los enlaces a la derecha */
            align-items: center; /* Alinea los elementos verticalmente */
        }

        nav a {
            color: #000000;
            text-decoration: none;
            margin: 0 15px;
            font-weight: bold;
        }

        /* Sección Principal */
        .hero {
            height: 70vh;
            color: #000000;
            display: flex;
            flex-direction: column;
            justify-content: center;
            align-items: center;
            text-align: center;
        }

        .hero h1 {
            font-size: 3rem;
            margin: 0;
        }

        .hero p {
            font-size: 1.5rem;
            margin-top: 10px;
        }

        /* Secciones de contenido */
        .section {
            padding: 50px 20px;
            text-align: center;
            opacity: 0;
            transform: translateY(20px);
            transition: opacity 0.5s ease, transform 0.5s ease;
        }

        .section:nth-child(even) {
            background-color: var(--color-guinda); /* Fondo guinda para secciones pares */
            color: #fff; /* Texto blanco */
        }

        .section h2 {
            font-size: 2rem;
            color: var(--color-amarillo); /* Título en amarillo */
        }

        .section p {
            margin-top: 10px;
            font-size: 1.2rem;
            color: #fff;
        }

        /* Pie de página */
        footer {
            background-color: var(--color-azul-rey); /* Azul rey */
            color: #fff;
            text-align: center;
            padding: 20px 0;
        }

        /* Contenedor para los logotipos */
        .logos {
            display: flex; /* Para alinear los logos horizontalmente */
            gap: 10px; /* Espaciado entre los logos */
        }

        .logos img {
            height: 50px; /* Tamaño uniforme para los logotipos */
        }

        /* Estilos responsivos */
        @media (max-width: 768px) {
            header {
                flex-direction: column;
                align-items: flex-start;
            }

            nav {
                margin-top: 10px;
            }

            .hero h1 {
                font-size: 2rem;
            }

            .hero p {
                font-size: 1.2rem;
            }

            .section h2 {
                font-size: 1.5rem;
            }

            .section p {
                font-size: 1rem;
            }
        }

        .section.in-view {
            opacity: 1;
            transform: translateY(0);
        }
        .imagen-izquierda {
            display: block;
            margin-left: 0;
            margin-right: auto; /* Esto asegura que la imagen quede alineada a la izquierda */
        }
        
    </style>
</head>
<body>
    <!-- Encabezado -->
    <header>
        <!-- Contenedor de logotipos alineados a la izquierda -->
        <div class="logos">
            <img src="logotipo-circular-de-facebook.png" alt="Logo de Facebook">
            <img src="correo-electronico.png" alt="Logo de Correo Electrónico">
        </div>

    </header>
    <nav>
        <img src="Photoroom-20250125_145627.png" height="250" class="imagen-izquierda">
        <a href="#mi-escuela"><i class="fa fa-school"></i> Mi Escuela</a>
        <a href="#oferta-educativa"><i class="fa fa-book"></i> Oferta Educativa</a>
        <a href="#vida-educativa"><i class="fa fa-calendar"></i> Vida Educativa</a>
    </nav>

    <!-- Sección Principal -->
    <section class="hero">
        <h1>Bienvenidos al Bachillerato Tecnológico</h1>
        <p>Formando jóvenes con entusiasmo por aprender</p>
    </section>

    <!-- Sección Mi Escuela -->
    <section id="mi-escuela" class="section">
        <h2>Mi Escuela</h2>
        <p>Conoce nuestras instalaciones, misión y visión.</p>
    </section>

    <!-- Sección Oferta Educativa -->
    <section id="oferta-educativa" class="section">
        <h2>Oferta Educativa</h2>
        <p>Explora nuestras áreas tecnológicas y académicas.</p>
    </section>

    <!-- Sección Vida Educativa -->
    <section id="vida-educativa" class="section">
        <h2>Vida Educativa</h2>
        <p>Descubre nuestras actividades, eventos y logros.</p>
    </section>

    <!-- Pie de página -->
    <footer>
        <p>&copy; 2025 Bachillerato Tecnológico. Todos los derechos reservados.</p>
    </footer>

    <script>
        document.addEventListener('DOMContentLoaded', () => {
            const sections = document.querySelectorAll('.section');

            const options = {
                root: null,
                rootMargin: '0px',
                threshold: 0.5
            };

            const observer = new IntersectionObserver((entries, observer) => {
                entries.forEach(entry => {
                    if (entry.isIntersecting) {
                        entry.target.classList.add('in-view');
                    }
                });
            }, options);

            sections.forEach(section => {
                observer.observe(section);
            });
        });
    </script>
</body>
</html>
