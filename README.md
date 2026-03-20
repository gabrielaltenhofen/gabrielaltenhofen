<!DOCTYPE html>
<html lang="pt-BR">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Gabriel Girardi Altenhofen - Desenvolvedor & Engenheiro</title>
    <style>
        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
        }

        :root {
            --primary: #1a3a52;
            --secondary: #00a8e8;
            --accent: #ff6b35;
            --light: #f0f4f8;
            --dark: #0f1419;
            --text-primary: #1a1a1a;
            --text-secondary: #666;
            --success: #06d6a0;
            --border: #e0e0e0;
        }

        html {
            scroll-behavior: smooth;
        }

        body {
            font-family: 'Segoe UI', 'Trebuchet MS', sans-serif;
            background: linear-gradient(135deg, #f5f7fa 0%, #e8ecf1 100%);
            color: var(--text-primary);
            line-height: 1.6;
            overflow-x: hidden;
        }

        /* Hero Section */
        .hero {
            background: linear-gradient(135deg, var(--primary) 0%, #2d5f7e 100%);
            color: white;
            padding: 80px 40px;
            text-align: center;
            position: relative;
            overflow: hidden;
            margin-bottom: 60px;
        }

        .hero::before {
            content: '';
            position: absolute;
            top: -50%;
            right: -10%;
            width: 500px;
            height: 500px;
            background: rgba(0, 168, 232, 0.1);
            border-radius: 50%;
            animation: float 6s ease-in-out infinite;
        }

        .hero::after {
            content: '';
            position: absolute;
            bottom: -30%;
            left: -5%;
            width: 400px;
            height: 400px;
            background: rgba(255, 107, 53, 0.08);
            border-radius: 50%;
            animation: float 8s ease-in-out infinite reverse;
        }

        @keyframes float {
            0%, 100% { transform: translateY(0px); }
            50% { transform: translateY(30px); }
        }

        .hero-content {
            position: relative;
            z-index: 2;
            max-width: 800px;
            margin: 0 auto;
            animation: slideInDown 0.8s ease-out;
        }

        @keyframes slideInDown {
            from {
                opacity: 0;
                transform: translateY(-30px);
            }
            to {
                opacity: 1;
                transform: translateY(0);
            }
        }

        .hero h1 {
            font-size: 3.5em;
            font-weight: 700;
            margin-bottom: 15px;
            letter-spacing: -1px;
            text-shadow: 0 2px 10px rgba(0, 0, 0, 0.2);
        }

        .hero .subtitle {
            font-size: 1.3em;
            margin-bottom: 10px;
            opacity: 0.95;
            font-weight: 500;
        }

        .contact-info {
            display: flex;
            gap: 25px;
            justify-content: center;
            margin-top: 25px;
            flex-wrap: wrap;
            font-size: 0.95em;
        }

        .contact-info span {
            display: flex;
            align-items: center;
            gap: 8px;
        }

        .contact-info a {
            color: #fff;
            text-decoration: none;
            border-bottom: 2px solid var(--secondary);
            transition: all 0.3s ease;
            padding-bottom: 2px;
        }

        .contact-info a:hover {
            color: var(--secondary);
            border-bottom-color: white;
        }

        /* Main Container */
        .container {
            max-width: 1000px;
            margin: 0 auto;
            padding: 0 40px;
        }

        /* Section Styles */
        section {
            margin-bottom: 70px;
        }

        .section-title {
            font-size: 2.2em;
            color: var(--primary);
            margin-bottom: 40px;
            position: relative;
            padding-bottom: 15px;
            font-weight: 700;
            letter-spacing: -0.5px;
        }

        .section-title::after {
            content: '';
            position: absolute;
            bottom: 0;
            left: 0;
            width: 60px;
            height: 4px;
            background: linear-gradient(90deg, var(--secondary), var(--accent));
            border-radius: 2px;
        }

        /* Card Grid */
        .cards-grid {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(300px, 1fr));
            gap: 25px;
            animation: fadeIn 0.8s ease-out 0.2s both;
        }

        @keyframes fadeIn {
            from {
                opacity: 0;
                transform: translateY(20px);
            }
            to {
                opacity: 1;
                transform: translateY(0);
            }
        }

        .card {
            background: white;
            border-radius: 12px;
            padding: 30px;
            border: 1px solid var(--border);
            transition: all 0.3s cubic-bezier(0.4, 0, 0.2, 1);
            position: relative;
            overflow: hidden;
        }

        .card::before {
            content: '';
            position: absolute;
            top: 0;
            left: -100%;
            width: 100%;
            height: 4px;
            background: linear-gradient(90deg, var(--secondary), var(--accent));
            transition: left 0.3s ease;
        }

        .card:hover {
            border-color: var(--secondary);
            box-shadow: 0 10px 40px rgba(26, 58, 82, 0.1);
            transform: translateY(-5px);
        }

        .card:hover::before {
            left: 0;
        }

        .card h3 {
            color: var(--primary);
            margin-bottom: 15px;
            font-size: 1.3em;
        }

        .card .job-period {
            font-size: 0.85em;
            color: var(--secondary);
            font-weight: 600;
            margin-bottom: 10px;
        }

        .card p {
            color: var(--text-secondary);
            font-size: 0.95em;
            line-height: 1.7;
        }

        .card ul {
            list-style: none;
            margin-top: 15px;
        }

        .card li {
            color: var(--text-secondary);
            padding: 8px 0 8px 25px;
            position: relative;
            font-size: 0.9em;
        }

        .card li::before {
            content: '→';
            position: absolute;
            left: 0;
            color: var(--secondary);
            font-weight: bold;
        }

        /* Skills Section */
        .skills-container {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(250px, 1fr));
            gap: 20px;
        }

        .skill-category {
            background: white;
            border-radius: 10px;
            padding: 25px;
            border-left: 4px solid var(--secondary);
            transition: all 0.3s ease;
        }

        .skill-category:hover {
            border-left-color: var(--accent);
            box-shadow: 0 5px 20px rgba(0, 0, 0, 0.08);
        }

        .skill-category h4 {
            color: var(--primary);
            margin-bottom: 15px;
            font-size: 1.1em;
            font-weight: 700;
        }

        .skill-tags {
            display: flex;
            flex-wrap: wrap;
            gap: 8px;
        }

        .skill-tag {
            background: linear-gradient(135deg, var(--light), #f5f7fa);
            color: var(--primary);
            padding: 6px 14px;
            border-radius: 20px;
            font-size: 0.85em;
            font-weight: 600;
            border: 1px solid var(--border);
            transition: all 0.3s ease;
        }

        .skill-tag:hover {
            background: linear-gradient(135deg, var(--secondary), #0088c2);
            color: white;
            border-color: transparent;
            transform: scale(1.05);
        }

        /* Timeline */
        .timeline {
            position: relative;
            padding-left: 30px;
        }

        .timeline::before {
            content: '';
            position: absolute;
            left: 0;
            top: 0;
            bottom: 0;
            width: 2px;
            background: linear-gradient(180deg, var(--secondary), var(--accent));
        }

        .timeline-item {
            margin-bottom: 40px;
            position: relative;
        }

        .timeline-item::before {
            content: '';
            position: absolute;
            left: -41px;
            top: 5px;
            width: 14px;
            height: 14px;
            background: var(--secondary);
            border-radius: 50%;
            border: 3px solid white;
            box-shadow: 0 0 0 3px var(--secondary);
        }

        /* Footer */
        footer {
            text-align: center;
            padding: 30px;
            color: var(--text-secondary);
            border-top: 1px solid var(--border);
            margin-top: 60px;
            background: white;
            font-size: 0.9em;
        }

        footer a {
            color: var(--secondary);
            text-decoration: none;
            font-weight: 600;
        }

        footer a:hover {
            text-decoration: underline;
        }

        /* Responsive */
        @media (max-width: 768px) {
            .hero {
                padding: 50px 20px;
            }

            .hero h1 {
                font-size: 2.2em;
            }

            .container {
                padding: 0 20px;
            }

            .section-title {
                font-size: 1.8em;
            }

            .cards-grid {
                grid-template-columns: 1fr;
            }

            .contact-info {
                flex-direction: column;
                gap: 10px;
            }
        }

        /* Animation for page load */
        .card {
            animation: slideUp 0.6s ease-out backwards;
        }

        .card:nth-child(1) { animation-delay: 0.1s; }
        .card:nth-child(2) { animation-delay: 0.2s; }
        .card:nth-child(3) { animation-delay: 0.3s; }
        .card:nth-child(4) { animation-delay: 0.4s; }
        .card:nth-child(5) { animation-delay: 0.5s; }

        @keyframes slideUp {
            from {
                opacity: 0;
                transform: translateY(30px);
            }
            to {
                opacity: 1;
                transform: translateY(0);
            }
        }

        /* Badge */
        .badge {
            display: inline-block;
            background: linear-gradient(135deg, var(--accent), #ff8c5a);
            color: white;
            padding: 4px 12px;
            border-radius: 15px;
            font-size: 0.75em;
            font-weight: 700;
            margin-top: 10px;
        }

        /* Highlight */
        .highlight {
            color: var(--secondary);
            font-weight: 700;
        }
    </style>
</head>
<body>
    <!-- Hero Section -->
    <section class="hero">
        <div class="hero-content">
            <h1>Gabriel Girardi Altenhofen</h1>
            <p class="subtitle">Desenvolvedor Full-Stack & Engenheiro de Sistemas</p>
            <div class="contact-info">
                <span>📍 São José do Inhacorá, RS</span>
                <span>📞 <a href="tel:+5555984048698">(55) 98404-8698</a></span>
                <span>✉️ <a href="mailto:gabrielgirardih@gmail.com">gabrielgirardih@gmail.com</a></span>
                <span>💼 <a href="https://www.linkedin.com/in/gabriel-altenhofen-a9ba1b235/" target="_blank">LinkedIn</a></span>
            </div>
        </div>
    </section>

    <div class="container">
        <!-- Sobre Mim -->
        <section>
            <h2 class="section-title">Sobre Mim</h2>
            <div class="card">
                <p>Profissional dedicado com experiência em <span class="highlight">desenvolvimento tecnológico</span>, focado em personalização de sistemas Protheus (ADVPL), criação de APIs REST e desenvolvimento web. Comprometido com eficiência, organização e <span class="highlight">melhoria contínua</span>, atuo com foco em resultados e integração de sistemas.</p>
            </div>
        </section>

        <!-- Formação -->
        <section>
            <h2 class="section-title">Formação</h2>
            <div class="cards-grid">
                <div class="card">
                    <h3>🎓 Bacharelado em Engenharia de Computação</h3>
                    <p><strong>SETREM</strong></p>
                    <p class="job-period">2022 - Atual</p>
                    <p>Formação em andamento com foco em desenvolvimento de software e engenharia de sistemas.</p>
                </div>
                <div class="card">
                    <h3>📚 Cursos Complementares</h3>
                    <ul>
                        <li>CAD/CREO e Windchill</li>
                        <li>JavaScript Avançado</li>
                        <li>Simbologia de Soldagem</li>
                    </ul>
                </div>
            </div>
        </section>

        <!-- Experiência Profissional -->
        <section>
            <h2 class="section-title">Experiência Profissional</h2>
            <div class="timeline">
                <div class="timeline-item">
                    <div class="card">
                        <h3>Assistente de TI</h3>
                        <p class="job-period">São José Industrial • 08/2024 - Atual</p>
                        <ul>
                            <li>Desenvolvimento de customizações Protheus (ADVPL)</li>
                            <li>Criação de APIs REST e integração com sistemas externos</li>
                            <li>Desenvolvimento de sites internos e suporte de TI</li>
                        </ul>
                        <span class="badge">ADVPL • REST API • Web Dev</span>
                    </div>
                </div>

                <div class="timeline-item">
                    <div class="card">
                        <h3>Auxiliar de TI</h3>
                        <p class="job-period">São José Industrial • 05/2024 - 08/2024</p>
                        <ul>
                            <li>Suporte a usuários e manutenção de sistemas</li>
                            <li>Atualização de softwares e organização documental</li>
                        </ul>
                        <span class="badge">Suporte Técnico • Infraestrutura</span>
                    </div>
                </div>

                <div class="timeline-item">
                    <div class="card">
                        <h3>Auxiliar de Engenharia</h3>
                        <p class="job-period">São José Industrial • 03/2022 - 05/2024</p>
                        <ul>
                            <li>Apoio em projetos e uso de softwares CAD (CREO, SolidWorks)</li>
                            <li>Impressão 3D e criação de documentos técnicos</li>
                        </ul>
                        <span class="badge">CAD • 3D • Projetos</span>
                    </div>
                </div>

                <div class="timeline-item">
                    <div class="card">
                        <h3>Jovem Aprendiz</h3>
                        <p class="job-period">São José Industrial • 03/2020 - 02/2022</p>
                        <ul>
                            <li>Apoio administrativo e técnico</li>
                            <li>Controle de planilhas e modelos CAD</li>
                        </ul>
                        <span class="badge">Administrativo • Técnico</span>
                    </div>
                </div>
            </div>
        </section>

        <!-- Habilidades Técnicas -->
        <section>
            <h2 class="section-title">Habilidades Técnicas</h2>
            <div class="skills-container">
                <div class="skill-category">
                    <h4>💻 Back-end & ERP</h4>
                    <div class="skill-tags">
                        <span class="skill-tag">ADVPL</span>
                        <span class="skill-tag">SQL Server</span>
                        <span class="skill-tag">Protheus</span>
                        <span class="skill-tag">APIs REST</span>
                    </div>
                </div>

                <div class="skill-category">
                    <h4>🌐 Front-end & Web</h4>
                    <div class="skill-tags">
                        <span class="skill-tag">JavaScript</span>
                        <span class="skill-tag">HTML/CSS</span>
                        <span class="skill-tag">Integração</span>
                    </div>
                </div>

                <div class="skill-category">
                    <h4>🛠️ Ferramentas & CAD</h4>
                    <div class="skill-tags">
                        <span class="skill-tag">CREO</span>
                        <span class="skill-tag">SolidWorks</span>
                        <span class="skill-tag">Windchill</span>
                        <span class="skill-tag">Impressão 3D</span>
                    </div>
                </div>

                <div class="skill-category">
                    <h4>🧠 Competências</h4>
                    <div class="skill-tags">
                        <span class="skill-tag">Análise</span>
                        <span class="skill-tag">Organização</span>
                        <span class="skill-tag">Resolução de Problemas</span>
                        <span class="skill-tag">Infraestrutura</span>
                    </div>
                </div>
            </div>
        </section>
    </div>

    <!-- Footer -->
    <footer>
        <p>© 2024 Gabriel Girardi Altenhofen • <a href="https://www.linkedin.com/in/gabriel-altenhofen-a9ba1b235/">Conecte-se comigo no LinkedIn</a></p>
        <p style="margin-top: 10px; font-size: 0.85em;">Aberto para novas oportunidades e desafios tecnológicos 🚀</p>
    </footer>
</body>
</html>
