<!-- ========================= -->
<!-- index.html -->
<!-- ========================= -->
<!DOCTYPE html>
<html lang="es">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Mi Hoja de Vida Web</title>
    <link rel="stylesheet" href="style.css">
</head>
<body>

<header class="header">
    <div class="container hero">
        <img src="https://via.placeholder.com/150" alt="Foto de perfil" class="profile-pic">
        <h1>Daniel Mateo Cruz Orjuela</h1>
        <p class="tagline">Estudiante con Inglés desarrollado (intermedio)</p>
        <button id="darkModeToggle">🌙 Modo Oscuro</button>
    </div>
</header>

<section id="about" class="section">
    <div class="container">
        <h2>Sobre mí</h2>
        <p>
            Soy estudiante de grado décimo, tengo 16 años y me interesa aprender diferentes ramas del estudio. Me gusta jugar videojuegos, leer y plantar. Actualmente quiero aprender Bioquímica y seguir desarrollando nuevas habilidades académicas y personales.
        </p>
    </div>
</section>

<section id="skills" class="section">
    <div class="container">
        <h2>Habilidades</h2>

        <div class="skill">
            <span>HTML</span>
            <div class="progress">
                <div class="progress-bar" style="width: 80%"></div>
            </div>
        </div>

        <div class="skill">
            <span>CSS</span>
            <div class="progress">
                <div class="progress-bar" style="width: 70%"></div>
            </div>
        </div>

        <div class="skill">
            <span>Trabajo en equipo</span>
            <div class="progress">
                <div class="progress-bar" style="width: 60%"></div>
            </div>
        </div>

    </div>
</section>

<section id="projects" class="section">
    <div class="container">
        <h2>Proyectos</h2>

        <div class="projects-grid">

            <article class="card">
                <img src="https://via.placeholder.com/300x200" alt="Proyecto 1">
                <h3>Proyecto Robot</h3>
                <p>Construcción de un robot usando micro:bit.</p>
            </article>

            <article class="card">
                <img src="https://via.placeholder.com/300x200" alt="Proyecto 2">
                <h3>Página Web</h3>
                <p>Creación de una página web personal.</p>
            </article>

            <article class="card">
                <img src="https://via.placeholder.com/300x200" alt="Proyecto 3">
                <h3>Aplicación Escolar</h3>
                <p>Proyecto para organizar tareas escolares.</p>
            </article>

        </div>
    </div>
</section>

<section id="contact" class="section">
    <div class="container">
        <h2>Contacto</h2>

        <form id="contactForm">
            <input type="text" placeholder="Tu nombre" required>
            <input type="email" placeholder="Tu correo" required>
            <textarea placeholder="Tu mensaje" required></textarea>
            <button type="submit">Enviar</button>
        </form>

        <p id="mensaje" class="mensaje"></p>

    </div>
</section>

<footer class="footer">
    <p>© 2026 Daniel Mateo Cruz Orjuela</p>
</footer>

<script src="script.js"></script>
</body>
</html>


<!-- ========================= -->
<!-- style.css -->
<!-- ========================= -->

:root {
    --primary-color: #2563eb;
    --background-color: #ffffff;
    --text-color: #111827;
    --card-color: #f3f4f6;
}

body.dark {
    --primary-color: #60a5fa;
    --background-color: #111827;
    --text-color: #f9fafb;
    --card-color: #1f2937;
}

body {
    margin: 0;
    font-family: Arial, sans-serif;
    background-color: var(--background-color);
    color: var(--text-color);
}

.container {
    width: 90%;
    max-width: 1000px;
    margin: auto;
}

.header {
    text-align: center;
    padding: 30px 0;
}

.profile-pic {
    border-radius: 50%;
    width: 150px;
}

.section {
    padding: 40px 0;
}

h2 {
    text-align: center;
    margin-bottom: 20px;
}

.skill {
    margin-bottom: 15px;
}

.progress {
    background: #ddd;
    border-radius: 10px;
    overflow: hidden;
}

.progress-bar {
    height: 15px;
    background: var(--primary-color);
}

.projects-grid {
    display: grid;
    grid-template-columns: repeat(3, 1fr);
    gap: 20px;
}

.card {
    background: var(--card-color);
    padding: 15px;
    border-radius: 10px;
    text-align: center;
}

.card img {
    width: 100%;
    border-radius: 10px;
}

form {
    display: flex;
    flex-direction: column;
    gap: 10px;
}

input, textarea, button {
    padding: 10px;
    font-size: 16px;
}

button {
    background: var(--primary-color);
    color: white;
    border: none;
    cursor: pointer;
}

.footer {
    text-align: center;
    padding: 20px;
}

.mensaje {
    margin-top: 10px;
    font-weight: bold;
}

/* ========================= */
/* RESPONSIVE DESIGN */
/* ========================= */

@media (max-width: 600px) {
    .projects-grid {
        grid-template-columns: 1fr;
    }
}


<!-- ========================= -->
<!-- script.js -->
<!-- ========================= -->

// Modo oscuro

const toggleButton = document.getElementById("darkModeToggle");

if (toggleButton) {
    toggleButton.addEventListener("click", () => {
        document.body.classList.toggle("dark");
    });
}

// Mensaje al enviar formulario

const form = document.getElementById("contactForm");
const mensaje = document.getElementById("mensaje");

if (form) {
    form.addEventListener("submit", function (event) {
        event.preventDefault();
        mensaje.textContent = "Gracias por contactarme";
        form.reset();
    });
}
