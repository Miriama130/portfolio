<!DOCTYPE html>
<html lang="fr">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0, user-scalable=no">
    <title>Mariem Tlili | Portfolio Cyber & Full-Stack</title>
    <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.0.0-beta3/css/all.min.css">
    <link href="https://fonts.googleapis.com/css2?family=Space+Grotesk:wght@300;400;500;600;700;800&display=swap" rel="stylesheet">
    <style>
        * { margin: 0; padding: 0; box-sizing: border-box; cursor: none; }
        body { font-family: 'Space Grotesk', sans-serif; background: linear-gradient(135deg, #0a0f1a 0%, #0c1220 100%); color: #eef5ff; line-height: 1.5; overflow-x: hidden; }
        .cursor { position: fixed; width: 32px; height: 32px; border: 2px solid #6c9eff; border-radius: 50%; pointer-events: none; z-index: 9999; transform: translate(-50%, -50%); transition: 0.08s linear; background-color: rgba(108, 158, 255, 0.05); backdrop-filter: blur(2px); }
        .cursor-dot { position: fixed; width: 6px; height: 6px; background-color: #6c9eff; border-radius: 50%; pointer-events: none; z-index: 9999; transform: translate(-50%, -50%); transition: 0.05s linear; box-shadow: 0 0 8px #6c9eff; }
        .container { max-width: 1400px; margin: 0 auto; padding: 0 5%; }
        nav { display: flex; justify-content: space-between; align-items: center; padding: 2rem 0 1rem; flex-wrap: wrap; gap: 1.5rem; border-bottom: 1px solid rgba(108, 158, 255, 0.2); }
        .logo { font-size: 1.8rem; font-weight: 700; background: linear-gradient(135deg, #ffffff, #8db5ff); -webkit-background-clip: text; background-clip: text; color: transparent; }
        .nav-links { display: flex; gap: 2.2rem; list-style: none; }
        .nav-links a { text-decoration: none; color: #ccddf8; font-weight: 500; transition: 0.3s; }
        .nav-links a:hover { color: #6c9eff; }
        .hero { min-height: 85vh; display: flex; align-items: center; justify-content: space-between; flex-wrap: wrap; gap: 2rem; padding: 2rem 0 3rem; }
        .hero-content { flex: 1; }
        .hero-content .greeting { font-size: 1rem; text-transform: uppercase; letter-spacing: 3px; color: #6c9eff; margin-bottom: 1rem; }
        .hero-content h1 { font-size: 4rem; font-weight: 700; line-height: 1.1; margin-bottom: 0.5rem; }
        .hero-content h1 span { background: linear-gradient(120deg, #ffffff, #91b6ff); -webkit-background-clip: text; background-clip: text; color: transparent; }
        .hero-content .title { font-size: 1.7rem; font-weight: 500; color: #b9d0ff; margin-bottom: 1.2rem; }
        .btn-group { display: flex; gap: 1.2rem; flex-wrap: wrap; margin-top: 1.5rem; }
        .btn { display: inline-flex; align-items: center; gap: 10px; padding: 12px 28px; border-radius: 40px; font-weight: 600; text-decoration: none; transition: all 0.25s; border: 1px solid rgba(108, 158, 255, 0.4); background: rgba(12, 20, 40, 0.7); backdrop-filter: blur(5px); color: white; cursor: pointer; }
        .btn-primary { background: #1e3a8a; border: none; box-shadow: 0 5px 15px rgba(30, 58, 138, 0.3); }
        .btn-primary:hover { background: #2c5fbb; transform: translateY(-3px); }
        .btn-outline { border: 1px solid #6c9eff; background: transparent; }
        .btn-outline:hover { background: rgba(108, 158, 255, 0.15); transform: translateY(-3px); }
        section { padding: 5rem 0; }
        .section-title { font-size: 2rem; font-weight: 600; margin-bottom: 2.5rem; position: relative; display: inline-block; }
        .section-title:after { content: ''; position: absolute; bottom: -12px; left: 0; width: 60px; height: 3px; background: #6c9eff; border-radius: 3px; }
        .projects-grid { display: grid; grid-template-columns: repeat(auto-fill, minmax(380px, 1fr)); gap: 2rem; }
        .project-card { background: rgba(20, 30, 55, 0.5); backdrop-filter: blur(8px); border: 1px solid rgba(108, 158, 255, 0.25); border-radius: 28px; padding: 1.5rem; transition: all 0.3s; }
        .project-card:hover { transform: translateY(-8px); border-color: #6c9eff; background: rgba(30, 45, 80, 0.7); }
        .project-icon { font-size: 2rem; color: #6c9eff; margin-bottom: 1rem; }
        .project-card h3 { font-size: 1.3rem; margin-bottom: 0.8rem; }
        .project-card p { color: #b4c6f0; font-size: 0.9rem; margin-bottom: 1rem; }
        .project-tags { display: flex; flex-wrap: wrap; gap: 0.5rem; margin: 0.8rem 0; }
        .tag { background: #1e2a44; padding: 0.2rem 0.8rem; border-radius: 20px; font-size: 0.7rem; font-weight: 600; color: #bbd7ff; }
        .github-link { display: inline-flex; align-items: center; gap: 8px; margin-top: 1rem; color: #6c9eff; text-decoration: none; font-size: 0.85rem; font-weight: 500; transition: 0.2s; cursor: pointer; }
        .github-link:hover { color: #ffffff; gap: 12px; }
        .microservice-list { list-style: none; padding-left: 1rem; margin-top: 0.5rem; }
        .microservice-list li { font-size: 0.8rem; color: #aac3ff; margin: 0.3rem 0; }
        .skills-wrapper { display: flex; flex-wrap: wrap; gap: 2rem; }
        .skills-category { flex: 1; min-width: 220px; background: rgba(15, 25, 45, 0.6); border-radius: 28px; padding: 1.6rem; border: 1px solid rgba(108, 158, 255, 0.2); }
        .skills-category h3 { margin-bottom: 1rem; }
        .skill-badge { background: #0f1a2f; border-radius: 30px; padding: 0.4rem 1.2rem; margin: 0.3rem; font-size: 0.85rem; display: inline-block; border: 1px solid #2a3a60; }
        .timeline { display: flex; flex-direction: column; gap: 1.8rem; }
        .timeline-item { border-left: 3px solid #6c9eff; padding-left: 1.5rem; }
        footer { border-top: 1px solid rgba(108, 158, 255, 0.2); text-align: center; padding: 2rem; }
        @media (max-width: 800px) { .hero-content h1 { font-size: 2.5rem; } .projects-grid { grid-template-columns: 1fr; } .cursor, .cursor-dot { display: none; } body { cursor: auto; } a, button, .btn { cursor: pointer; } }
        .toast { position: fixed; bottom: 20px; right: 20px; background: #1e3a8a; color: white; padding: 12px 24px; border-radius: 40px; z-index: 10000; animation: slideIn 0.3s ease; }
        @keyframes slideIn { from { transform: translateX(400px); opacity: 0; } to { transform: translateX(0); opacity: 1; } }
        .share-buttons { display: flex; gap: 10px; margin-top: 20px; }
        .share-btn { background: rgba(108, 158, 255, 0.2); border: 1px solid #6c9eff; padding: 8px 16px; border-radius: 30px; cursor: pointer; transition: 0.2s; }
        .share-btn:hover { background: #6c9eff; color: #0a0f1a; }
    </style>
</head>
<body>

<div class="cursor"></div>
<div class="cursor-dot"></div>

<div id="app"></div>

<script>
    // Données du portfolio
    const portfolioData = {
        name: "Mariem Tlili",
        title: "Ingénieure en Informatique & Expert Cyber Sécurité",
        projects: [
            {
                icon: "fab fa-devops",
                title: "Pipeline DevOps Complet",
                description: "CI/CD complet avec Jenkins, Docker, Kubernetes (EKS), Terraform, Prometheus & Grafana. Intégration de scans Nessus dans le pipeline, envoi d'emails de notification, build image Docker sécurisée.",
                tags: ["Jenkins", "Dockerfile", "K8s/EKS", "Terraform", "Prometheus", "Grafana", "Nessus Scan", "Mail Notif"],
                github: "https://github.com/mariemtlili/devops-pipeline"
            },
            {
                icon: "fab fa-java",
                title: "Architecture Microservices",
                description: "Spring Cloud Gateway, Eureka Discovery, Config Server, Resilience4j, Kafka, Zipkin.",
                microservices: ["Service Auth (JWT)", "Service Commandes (PostgreSQL)", "Service Paiement (MongoDB)", "Service Notification (Kafka)", "API Gateway + Resilience4j"],
                tags: ["Spring Boot", "Kafka", "Resilience4j", "Eureka"],
                github: "https://github.com/mariemtlili/microservices-spring"
            },
            {
                icon: "fas fa-shield-virus",
                title: "PFE : Nessus Scan & GLPI Security",
                description: "Application full-stack (Node.js/Express + React + MongoDB) pour centraliser vulnérabilités Nessus, synchronisation GLPI, génération rapports PDF.",
                tags: ["Node.js", "React", "MongoDB", "Nessus API", "GLPI", "Socket.io"],
                github: "https://github.com/mariemtlili/nessus-glpi"
            },
            {
                icon: "fas fa-code-branch",
                title: "Skill Swapp - Plateforme innovante",
                description: "Génération automatique de quiz par IA, système de recommandation, appel vidéo (WebRTC), messagerie instantanée, chatbot intelligent, mailing automatique.",
                tags: ["React/Spring Boot", "IA Quiz Gen", "WebRTC", "Chatbot", "Mailgun"],
                github: "https://github.com/mariemtlili/skill-swapp"
            },
            {
                icon: "fab fa-node-js",
                title: "Node.js Enterprise API",
                description: "API REST complète avec authentification JWT, CRUD avancé, upload fichiers, pagination, rate limiting, logging Winston, Docker.",
                tags: ["Express", "MongoDB/Mongoose", "JWT", "Redis", "Swagger"],
                github: "https://github.com/mariemtlili/nodejs-enterprise-api"
            },
            {
                icon: "fab fa-react",
                title: "Dashboard React / Tailwind",
                description: "Application SPA avec thème sombre, graphiques Recharts, authentification, Redux Toolkit, routes protégées.",
                tags: ["React 18", "TailwindCSS", "Redux Toolkit", "Vite"],
                github: "https://github.com/mariemtlili/react-dashboard"
            },
            {
                icon: "fab fa-python",
                title: "Django E-Commerce",
                description: "Plateforme e-commerce complète avec panier, Stripe, REST API (DRF), PostgreSQL, AWS EC2.",
                tags: ["Django", "DRF", "Stripe", "PostgreSQL"],
                github: "https://github.com/mariemtlili/django-ecommerce"
            },
            {
                icon: "fas fa-project-diagram",
                title: "Web Sémantique & SPARQL",
                description: "Ontologie RDF, requêtes SPARQL, application Flask pour DBpedia, GraphDB.",
                tags: ["RDF/OWL", "SPARQL", "Flask", "GraphDB"],
                github: "https://github.com/mariemtlili/semantic-web"
            },
            {
                icon: "fas fa-graphql",
                title: "GraphQL API Gateway",
                description: "Apollo Server, fédération de microservices, subscriptions en temps réel.",
                tags: ["GraphQL", "Apollo", "Node.js", "MongoDB"],
                github: "https://github.com/mariemtlili/graphql-gateway"
            },
            {
                icon: "fas fa-brain",
                title: "ML - Détection Anomalies Réseau",
                description: "Modèles LSTM / Isolation Forest pour cybersécurité, FastAPI, Streamlit.",
                tags: ["TensorFlow", "Scikit-learn", "FastAPI"],
                github: "https://github.com/mariemtlili/ml-security"
            }
        ],
        skills: {
            dev: ["Java/Spring Boot", "Angular", "React", "Node.js", "Django", "Tailwind", "GraphQL", "SPARQL/RDF"],
            devops: ["Docker/K8s", "Jenkins", "Terraform", "AWS Certified", "Prometheus/Grafana"],
            cyber: ["Nessus/OpenVAS", "GLPI", "Blockchain", "ISO 27001", "SIEM"],
            certs: ["AWS Solutions Architect", "Blockchain Certified (Hyperledger)", "CKA (Kubernetes)", "Nessus Certified"]
        },
        formation: [
            { title: "🎓 Ingénieur Informatique - ENSI", desc: "2021-2024 | Spécialité Cybersécurité & Cloud, Mention Très Bien" },
            { title: "📜 Blockchain & Smart Contracts", desc: "Certification professionnelle - Ethereum / Hyperledger Fabric" },
            { title: "🤖 AWS re/Start & Cloud Architect", desc: "Certification AWS Solutions Architect - Déploiements cloud haute disponibilité" }
        ]
    };

    // Fonction pour afficher un toast
    function showToast(message) {
        const toast = document.createElement('div');
        toast.className = 'toast';
        toast.textContent = message;
        document.body.appendChild(toast);
        setTimeout(() => toast.remove(), 3000);
    }

    // Fonction pour copier le lien
    function copyShareLink() {
        const url = window.location.href;
        navigator.clipboard.writeText(url).then(() => {
            showToast('✅ Lien copié ! Partagez-le avec vos amis');
        });
    }

    // Génération du HTML
    function renderPortfolio() {
        const app = document.getElementById('app');
        
        // Génération des projets
        const projectsHTML = portfolioData.projects.map(project => `
            <div class="project-card">
                <div class="project-icon"><i class="${project.icon}"></i></div>
                <h3>${project.title}</h3>
                <p>${project.description}</p>
                ${project.microservices ? `<ul class="microservice-list">${project.microservices.map(ms => `<li>🔹 ${ms}</li>`).join('')}</ul>` : ''}
                <div class="project-tags">${project.tags.map(tag => `<span class="tag">${tag}</span>`).join('')}</div>
                <a href="${project.github}" target="_blank" class="github-link"><i class="fab fa-github"></i> Voir sur GitHub →</a>
            </div>
        `).join('');

        // Génération des compétences
        const skillsHTML = `
            <div class="skills-category"><h3><i class="fas fa-laptop-code"></i> Dev & Frameworks</h3>${portfolioData.skills.dev.map(s => `<span class="skill-badge">${s}</span>`).join('')}</div>
            <div class="skills-category"><h3><i class="fas fa-cloud"></i> DevOps & Cloud</h3>${portfolioData.skills.devops.map(s => `<span class="skill-badge">${s}</span>`).join('')}</div>
            <div class="skills-category"><h3><i class="fas fa-shield-alt"></i> CyberSécurité</h3>${portfolioData.skills.cyber.map(s => `<span class="skill-badge">${s}</span>`).join('')}</div>
            <div class="skills-category"><h3><i class="fas fa-certificate"></i> Certifications</h3>${portfolioData.skills.certs.map(s => `<span class="skill-badge">${s}</span>`).join('')}</div>
        `;

        // Génération formation
        const formationHTML = portfolioData.formation.map(f => `
            <div class="timeline-item"><h4>${f.title}</h4><p>${f.desc}</p></div>
        `).join('');

        app.innerHTML = `
            <header>
                <div class="container">
                    <nav>
                        <div class="logo">M.TLILI</div>
                        <ul class="nav-links">
                            <li><a href="#accueil">Accueil</a></li>
                            <li><a href="#projets">Projets</a></li>
                            <li><a href="#competences">Compétences</a></li>
                            <li><a href="#formation">Formation</a></li>
                            <li><a href="#contact">Contact</a></li>
                        </ul>
                    </nav>
                </div>
            </header>

            <main>
                <section id="accueil">
                    <div class="container hero">
                        <div class="hero-content">
                            <div class="greeting">⚡ CYBER & FULL-STACK ENGINEER</div>
                            <h1>Bonjour, je suis <br><span>${portfolioData.name}</span></h1>
                            <div class="title">${portfolioData.title}</div>
                            <div class="btn-group">
                                <a href="#projets" class="btn btn-primary">Voir mes projets →</a>
                                <button id="downloadCvBtn" class="btn btn-outline"><i class="fas fa-download"></i> Télécharger CV</button>
                                <button id="shareBtn" class="btn btn-outline"><i class="fas fa-share-alt"></i> Partager</button>
                            </div>
                            <div class="share-buttons">
                                <button onclick="window.open('https://wa.me/?text=Découvrez%20mon%20portfolio%20!%20' + window.location.href)" class="share-btn"><i class="fab fa-whatsapp"></i> WhatsApp</button>
                                <button onclick="window.open('https://www.linkedin.com/sharing/share-offsite/?url=' + window.location.href)" class="share-btn"><i class="fab fa-linkedin"></i> LinkedIn</button>
                                <button onclick="copyShareLink()" class="share-btn"><i class="fas fa-link"></i> Copier lien</button>
                            </div>
                        </div>
                        <div class="hero-image">
                            <div style="width: 260px; height: 260px; border-radius: 50%; background: radial-gradient(circle at 30% 20%, #2a4b8c, #0a1428); display: flex; align-items: center; justify-content: center; box-shadow: 0 20px 35px -10px #00000055;">
                                <i class="fas fa-shield-haltered" style="font-size: 5rem; color: #9bbdff;"></i>
                            </div>
                        </div>
                    </div>
                </section>

                <section id="projets" style="background: rgba(0, 0, 0, 0.2);">
                    <div class="container">
                        <h2 class="section-title">Projets phares</h2>
                        <div class="projects-grid">${projectsHTML}</div>
                    </div>
                </section>

                <section id="competences">
                    <div class="container">
                        <h2 class="section-title">Compétences & Certifications</h2>
                        <div class="skills-wrapper">${skillsHTML}</div>
                    </div>
                </section>

                <section id="formation" style="background: rgba(0, 0, 0, 0.2);">
                    <div class="container">
                        <h2 class="section-title">Formation</h2>
                        <div class="timeline">${formationHTML}</div>
                    </div>
                </section>

                <section id="contact">
                    <div class="container">
                        <h2 class="section-title">Contact & Réseaux</h2>
                        <div style="display: flex; gap: 2rem; flex-wrap: wrap; justify-content: space-between; align-items: center;">
                            <div style="display: flex; gap: 2rem; flex-wrap: wrap;">
                                <a href="https://github.com/mariemtlili" target="_blank" style="color:#aac3ff; text-decoration: none;"><i class="fab fa-github"></i> github/mariemtlili</a>
                                <a href="#" style="color:#aac3ff; text-decoration: none;"><i class="fab fa-linkedin"></i> linkedin/in/mariem-tlili</a>
                                <a href="mailto:mariem.tlili@cybersec.tn" style="color:#aac3ff; text-decoration: none;"><i class="fas fa-envelope"></i> mariem.tlili@cybersec.tn</a>
                            </div>
                            <div><i class="fas fa-map-marker-alt"></i> Tunis, Tunisie</div>
                        </div>
                    </div>
                </section>
            </main>

            <footer>
                <p>© 2026 ${portfolioData.name} — Ingénieure Informatique | DevOps | Cyber Expert | Tous droits réservés</p>
            </footer>
        `;

        // Attacher les événements après le rendu
        attachEvents();
    }

    function attachEvents() {
        // Smooth scroll
        document.querySelectorAll('.nav-links a, .btn-primary').forEach(anchor => {
            anchor.addEventListener('click', function(e) {
                const targetId = this.getAttribute('href');
                if(targetId && targetId.startsWith('#')) {
                    e.preventDefault();
                    document.querySelector(targetId)?.scrollIntoView({ behavior: 'smooth' });
                }
            });
        });

        // Téléchargement CV
        document.getElementById('downloadCvBtn')?.addEventListener('click', () => {
            showToast('📄 Téléchargement CV - Mariem Tlili : Ingénieure Informatique, Expert Cyber, DevOps, certifiée AWS & Blockchain.');
        });

        // Bouton partager
        document.getElementById('shareBtn')?.addEventListener('click', () => {
            copyShareLink();
        });
    }

    // Curseur personnalisé
    function initCursor() {
        const cursor = document.querySelector('.cursor');
        const cursorDot = document.querySelector('.cursor-dot');
        if (cursor && cursorDot) {
            document.addEventListener('mousemove', (e) => {
                cursor.style.left = e.clientX + 'px';
                cursor.style.top = e.clientY + 'px';
                cursorDot.style.left = e.clientX + 'px';
                cursorDot.style.top = e.clientY + 'px';
            });
            const hoverElements = document.querySelectorAll('a, .btn, .project-card, button');
            hoverElements.forEach(el => {
                el.addEventListener('mouseenter', () => {
                    cursor.style.transform = 'translate(-50%, -50%) scale(1.6)';
                    cursorDot.style.transform = 'translate(-50%, -50%) scale(1.5)';
                });
                el.addEventListener('mouseleave', () => {
                    cursor.style.transform = 'translate(-50%, -50%) scale(1)';
                    cursorDot.style.transform = 'translate(-50%, -50%) scale(1)';
                });
            });
        }
    }

    // Initialisation
    renderPortfolio();
    setTimeout(initCursor, 100);
    window.copyShareLink = copyShareLink;
</script>
</body>
</html>
