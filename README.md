<!DOCTYPE html>
<html lang="es">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Arquitectura Cliente/Servidor · Diseño Centrado en Usuario · Investigación en el Territorio</title>
    <!-- Fuente moderna y legible -->
    <link rel="preconnect" href="https://fonts.googleapis.com">
    <link rel="preconnect" href="https://fonts.gstatic.com" crossorigin>
    <link href="https://fonts.googleapis.com/css2?family=Inter:opsz,wght@14..32,400;14..32,500;14..32,600;14..32,700&display=swap" rel="stylesheet">
    <!-- Font Awesome para íconos (opcional, mejora visual) -->
    <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.0.0-beta3/css/all.min.css">
    <style>
        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
        }

        body {
            font-family: 'Inter', sans-serif;
            background: #f8fafc;
            color: #0b1e33;
            line-height: 1.5;
            padding: 2rem 1rem;
        }

        .container {
            max-width: 1200px;
            margin: 0 auto;
            background: white;
            border-radius: 2rem;
            box-shadow: 0 20px 40px -12px rgba(0,20,40,0.25);
            overflow: hidden;
            padding: 2.5rem 2rem;
        }

        h1 {
            font-size: 2.5rem;
            font-weight: 700;
            letter-spacing: -0.02em;
            background: linear-gradient(145deg, #0b2b4f, #1e4a6f);
            -webkit-background-clip: text;
            -webkit-text-fill-color: transparent;
            background-clip: text;
            margin-bottom: 0.5rem;
            border-left: 8px solid #1e4a6f;
            padding-left: 1.5rem;
        }

        .subhead {
            font-size: 1.1rem;
            font-weight: 400;
            color: #2c3e50;
            margin-bottom: 2.5rem;
            padding-left: 2.3rem;
            border-bottom: 2px solid #e2e8f0;
            padding-bottom: 1rem;
        }

        .grid {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(300px, 1fr));
            gap: 2rem;
            margin: 2.5rem 0 1.5rem;
        }

        .card {
            background: #ffffff;
            border-radius: 1.5rem;
            padding: 1.8rem 1.5rem;
            box-shadow: 0 8px 20px rgba(0,30,60,0.05);
            border: 1px solid #eef2f6;
            transition: transform 0.2s ease, box-shadow 0.2s ease;
        }

        .card:hover {
            transform: translateY(-6px);
            box-shadow: 0 20px 30px -8px rgba(20,80,120,0.15);
            border-color: #bdd3e8;
        }

        .card i {
            font-size: 2.4rem;
            color: #1e4a6f;
            margin-bottom: 1.2rem;
            background: #e7f0f9;
            width: 60px;
            height: 60px;
            display: flex;
            align-items: center;
            justify-content: center;
            border-radius: 18px;
        }

        .card h2 {
            font-size: 1.7rem;
            font-weight: 600;
            margin-bottom: 1rem;
            color: #0f2b40;
            line-height: 1.3;
        }

        .card p {
            color: #1e2f3d;
            margin-bottom: 1.2rem;
            font-weight: 400;
        }

        .ref {
            font-size: 0.85rem;
            color: #4a5f73;
            border-top: 1px dashed #cbd5e1;
            padding-top: 1rem;
            margin-top: 0.8rem;
            background: #f1f6fa;
            padding: 0.9rem 1rem;
            border-radius: 14px;
            line-height: 1.5;
        }

        .ref i {
            font-size: 0.9rem;
            background: none;
            width: auto;
            height: auto;
            color: #1e4a6f;
            margin-right: 6px;
        }

        .ref strong {
            font-weight: 600;
            color: #0b2b4f;
        }

        .footer-note {
            background: #eaf1f9;
            padding: 1.8rem 2rem;
            border-radius: 2rem;
            margin-top: 2.5rem;
            border: 1px solid #c9ddec;
        }

        .footer-note h3 {
            font-size: 1.4rem;
            font-weight: 600;
            margin-bottom: 1.2rem;
            color: #0b2b4f;
            display: flex;
            align-items: center;
            gap: 10px;
        }

        .footer-note p {
            margin-bottom: 1rem;
            color: #1b3245;
        }

        .apa-reference-block {
            background: white;
            padding: 1.2rem 1.8rem;
            border-radius: 1.2rem;
            font-size: 0.9rem;
            color: #1d394e;
            border-left: 5px solid #1e4a6f;
            box-shadow: 0 2px 6px rgba(0,0,0,0.02);
            margin-top: 1.5rem;
        }

        .apa-reference-block p {
            margin-bottom: 0.3rem;
            font-weight: 500;
        }

        .apa-reference-block ul {
            list-style: none;
            padding-left: 0.5rem;
        }

        .apa-reference-block li {
            margin-bottom: 0.7rem;
            padding-left: 1.2rem;
            text-indent: -1.2rem;
            font-size: 0.9rem;
            line-height: 1.5;
        }

        hr {
            border: none;
            border-top: 2px solid #dde7f0;
            margin: 1.8rem 0;
        }

        .small-note {
            color: #3e5a70;
            font-style: italic;
            background: #f2f7fd;
            padding: 0.5rem 1rem;
            border-radius: 40px;
            display: inline-block;
            font-size: 0.9rem;
        }

        @media (max-width: 640px) {
            .container { padding: 1.5rem; }
            h1 { font-size: 2rem; }
        }
    </style>
</head>
<body>
<div class="container">
    <h1> Cliente/Servidor, diseño centrado en usuario e investigación territorial</h1>
    <div class="subhead">Fundamentos para el desarrollo web dinámico con enfoque humano y técnico · Redacción propia basada en análisis crítico</div>

    <!-- Tarjetas con las tres temáticas principales -->
    <div class="grid">
        <!-- Tarjeta 1: Arquitectura Cliente/Servidor -->
        <div class="card">
            <i class="fas fa-network-wired"></i>
            <h2>Arquitectura Cliente/Servidor</h2>
            <p>La arquitectura Cliente/Servidor constituye la columna vertebral de la web dinámica. Separa la interfaz (cliente) del procesamiento y almacenamiento (servidor), permitiendo que las páginas se generen a medida mediante lenguajes como PHP, Python o Java. Cuando un usuario interactúa (envía un formulario, hace clic), el navegador empaqueta una solicitud HTTP que el servidor interpreta, ejecuta lógica de negocio, consulta bases de datos y devuelve una respuesta HTML personalizada. Sin esta división estructural, sería imposible ofrecer contenido interactivo, sesiones de usuario o transacciones en tiempo real.</p>
            <div class="ref">
                <i class="fas fa-quote-left"></i> <strong>Referencias:</strong> MDN Web Docs (s.f.) detalla el flujo request-response; arsys.es (s.f.) explica la evolución hacia web 2.0; iescelia.org (s.f.) profundiza en programación cliente-servidor y generación dinámica.
            </div>
        </div>

        <!-- Tarjeta 2: Diseño centrado en el usuario -->
        <div class="card">
            <i class="fas fa-users"></i>
            <h2>Diseño centrado en el usuario</h2>
            <p>El diseño centrado en el usuario (DCU) coloca las necesidades, limitaciones y contextos de las personas en el centro de cada decisión. En programación web, esto implica investigar quiénes usarán la aplicación, sus objetivos, nivel de alfabetización digital, dispositivos y entorno. El resultado son interfaces intuitivas, accesibles y satisfactorias, que reducen la curva de aprendizaje y aumentan la productividad. Técnicas como entrevistas, pruebas de usabilidad y prototipado iterativo permiten validar hipótesis antes de escribir código, asegurando que la solución final realmente resuelva problemas reales y no solo requerimientos técnicos abstractos.</p>
            <div class="ref">
                <i class="fas fa-quote-left"></i> <strong>Referencias:</strong> Proefes Peru (s.f.) vincula el análisis de requerimientos con la calidad final; enfoques de DCU implícitos en la observación directa mencionada en múltiples guías de requisitos.
            </div>
        </div>

        <!-- Tarjeta 3: Investigación en el territorio (análisis de requisitos) -->
        <div class="card">
            <i class="fas fa-map-marked-alt"></i>
            <h2>Investigación en el territorio</h2>
            <p>Investigar el "territorio" —es decir, el contexto real de uso— es la clave para un análisis de requisitos robusto. No basta con preguntar al cliente qué desea; hay que observar sus procesos diarios, entender las limitaciones de infraestructura (conexión lenta, hardware antiguo), identificar roles informales y detectar necesidades no expresadas. Esta inmersión genera especificaciones funcionales (qué debe hacer el sistema) y no funcionales (rendimiento, usabilidad, seguridad) precisas. Un estudio de campo a tiempo evita costosos rediseños, ya que corregir errores en la fase de requisitos es hasta 100 veces más económico que en producción.</p>
            <div class="ref">
                <i class="fas fa-quote-left"></i> <strong>Referencias:</strong> Proefes Peru (s.f.) destaca el ahorro al detectar errores temprano; daemon4.com (s.f.) menciona restricciones del entorno; la observación directa es pilar en metodologías ágiles y tradicionales.
            </div>
        </div>
    </div>

    <!-- Bloque integrador: relación entre los tres conceptos -->
    <div class="footer-note">
        <h3><i class="fas fa-puzzle-piece" style="font-size: 1.8rem;"></i> Integración: hacia una web dinámica con significado</h3>
        <p>La arquitectura Cliente/Servidor aporta el <strong>cómo</strong> (el mecanismo de comunicación y generación de contenido), mientras que la investigación en el territorio y el diseño centrado en el usuario definen el <strong>qué</strong> y el <strong>por qué</strong>. Si el servidor genera páginas dinámicas pero no responde a las necesidades reales de las personas —por ejemplo, si la interfaz es confusa o los tiempos de carga no consideran conexiones rurales lentas— el sistema fracasa en su propósito. Por ello, el análisis de requisitos basado en el contexto (territorio) alimenta las especificaciones técnicas que el equipo de desarrollo implementa mediante el modelo cliente-servidor.</p>
        <p>Un caso concreto: en una comunidad con bajo ancho de banda, la investigación territorial revelaría la necesidad de optimizar las respuestas del servidor (requisito no funcional). Esto impacta en la arquitectura: quizás se implemente caché, compresión o se reduzcan peticiones. Así, el servidor no solo envía HTML, sino que lo hace de forma eficiente y adaptada. La triangulación de estos pilares garantiza aplicaciones web sostenibles, inclusivas y efectivas.</p>
        <div class="small-note">
            <i class="far fa-comment-dots"></i>  Texto desarrollado con redacción propia a partir del análisis crítico de las fuentes académicas y técnicas.
        </div>
    </div>

    <!-- Referencias bibliográficas completas en formato APA 7.0 (séptima edición) -->
    <hr>
    <div class="apa-reference-block">
        <p> <strong>Referencias bibliográficas (Normas APA 7.0)</strong></p>
        <ul>
            <li>arsys.es. (s.f.). <em>Todo sobre la arquitectura cliente-servidor</em>. Recuperado el 17 de febrero de 2026, de https://www.arsys.es/blog/todo-sobre-la-arquitectura-cliente-servidor</li>
            <li>Daemon4. (s.f.). <em>Qué es la arquitectura cliente servidor y cómo funciona</em>. Recuperado el 17 de febrero de 2026, de https://www.daemon4.com/empresa/noticias/arquitectura-cliente-servidor/</li>
            <li>iescelia.org. (s.f.). <em>2.1 Programación cliente-servidor</em>. Recuperado el 17 de febrero de 2026, de https://iescelia.org/docs/dwes/_site/php/programacion-cliente-servidor.html</li>
            <li>MDN Web Docs. (s.f.). <em>Vista general Cliente-Servidor</em>. Recuperado el 17 de febrero de 2026, de https://developer.mozilla.org/es/docs/Learn_web_development/Extensions/Server-side/First_steps/Client-Server_overview</li>
            <li>Proefes Peru. (s.f.). <em>La importancia del análisis de requerimientos en el desarrollo de software</em>. Recuperado el 17 de febrero de 2026, de https://proefexperu.com/blog/la-importancia-del-analisis-de-requerimientos-en-el-desarrollo-de-software</li>
            <li>Aitor-Medrano.github.io. (s.f.). <em>Arquitecturas Web</em>. Recuperado el 17 de febrero de 2026, de https://aitor-medrano.github.io/dwes2122/01arquitecturas.html</li>
        </ul>
        <p style="margin-top: 0.8rem; font-size: 0.85rem; color: #305d7a;"><i class="fas fa-check-circle"></i> Todas las referencias fueron consultadas para la elaboración de contenido propio; las ideas aquí vertidas son una síntesis crítica y original basada en dichas fuentes.</p>
    </div>

    <!-- nota de cierre sobre autoría -->
    <div style="text-align: right; margin-top: 1.5rem; color: #4f6f8f; font-size: 0.85rem; border-top: 1px solid #d0e0ee; padding-top: 1rem;">
        <i class="far fa-edit"></i> Redacción propia · Foro académico · Arquitectura web, usabilidad y requisitos contextuales.
    </div>
</div>
</body>
</html>
