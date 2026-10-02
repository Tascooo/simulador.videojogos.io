# simulador.videojogos.io
<title>PAP | Simulador de Jogos de Condução</title>

<style>
    * {
        margin: 0;
        padding: 0;
        box-sizing: border-box;
        scroll-behavior: smooth;
    }

    :root {
        --vermelho: #e10600;
        --vermelho-claro: #ff3b30;
        --preto: #080808;
        --cinza: #151515;
        --cinza-claro: #222;
        --branco: #ffffff;
        --texto: #cccccc;
    }

    body {
        font-family: Arial, Helvetica, sans-serif;
        background: var(--preto);
        color: var(--branco);
        line-height: 1.6;
    }

    /* MENU */

    header {
        position: fixed;
        top: 0;
        width: 100%;
        z-index: 1000;
        background: rgba(8, 8, 8, 0.95);
        border-bottom: 1px solid #292929;
        backdrop-filter: blur(10px);
    }

    nav {
        max-width: 1200px;
        margin: auto;
        padding: 18px 25px;
        display: flex;
        justify-content: space-between;
        align-items: center;
    }

    .logo {
        font-size: 22px;
        font-weight: bold;
        color: var(--vermelho);
        letter-spacing: 2px;
    }

    nav ul {
        display: flex;
        list-style: none;
        gap: 25px;
    }

    nav a {
        color: white;
        text-decoration: none;
        font-size: 14px;
        transition: 0.3s;
    }

    nav a:hover {
        color: var(--vermelho);
    }

    /* HERO */

    .hero {
        min-height: 100vh;
        display: flex;
        align-items: center;
        justify-content: center;
        text-align: center;
        padding: 120px 20px 80px;

        background:
            linear-gradient(rgba(0,0,0,0.7), rgba(0,0,0,0.9)),
            radial-gradient(circle at center, #3a0808, #050505 70%);
    }

    .hero-content {
        max-width: 900px;
    }

    .tag {
        display: inline-block;
        border: 1px solid var(--vermelho);
        color: var(--vermelho-claro);
        padding: 8px 18px;
        border-radius: 30px;
        margin-bottom: 25px;
        font-size: 13px;
        text-transform: uppercase;
        letter-spacing: 2px;
    }

    .hero h1 {
        font-size: clamp(45px, 8vw, 90px);
        line-height: 1;
        text-transform: uppercase;
        margin-bottom: 25px;
    }

    .hero h1 span {
        color: var(--vermelho);
    }

    .hero p {
        color: var(--texto);
        font-size: 19px;
        max-width: 700px;
        margin: auto;
    }

    .btn {
        display: inline-block;
        margin-top: 35px;
        padding: 14px 30px;
        background: var(--vermelho);
        color: white;
        text-decoration: none;
        border-radius: 5px;
        font-weight: bold;
        transition: 0.3s;
    }

    .btn:hover {
        background: var(--vermelho-claro);
        transform: translateY(-3px);
    }

    /* GERAL */

    section {
        max-width: 1200px;
        margin: auto;
        padding: 100px 25px;
    }

    .section-title {
        margin-bottom: 50px;
    }

    .section-title small {
        color: var(--vermelho);
        text-transform: uppercase;
        letter-spacing: 3px;
        font-weight: bold;
    }

    .section-title h2 {
        font-size: 42px;
        margin-top: 10px;
    }

    .section-title p {
        color: #999;
        max-width: 650px;
        margin-top: 10px;
    }

    /* SOBRE */

    .sobre {
        background: #0d0d0d;
    }

    .sobre-content {
        display: grid;
        grid-template-columns: 1fr 1fr;
        gap: 50px;
        align-items: center;
    }

    .sobre-texto p {
        color: var(--texto);
        margin-bottom: 20px;
    }

    .info-box {
        background: var(--cinza);
        padding: 30px;
        border-left: 4px solid var(--vermelho);
        border-radius: 8px;
    }

    .info-box div {
        margin-bottom: 18px;
    }

    .info-box div:last-child {
        margin-bottom: 0;
    }

    .info-box strong {
        display: block;
        color: white;
    }

    .info-box span {
        color: #999;
    }

    /* OBJETIVOS */

    .objetivos {
        display: grid;
        grid-template-columns: repeat(3, 1fr);
        gap: 20px;
    }

    .card {
        background: var(--cinza);
        padding: 30px;
        border-radius: 10px;
        border: 1px solid #292929;
        transition: 0.3s;
    }

    .card:hover {
        transform: translateY(-8px);
        border-color: var(--vermelho);
    }

    .icon {
        width: 50px;
        height: 50px;
        background: rgba(225, 6, 0, 0.15);
        color: var(--vermelho);
        display: flex;
        align-items: center;
        justify-content: center;
        border-radius: 8px;
        font-size: 25px;
        margin-bottom: 20px;
    }

    .card h3 {
        margin-bottom: 10px;
    }

    .card p {
        color: #999;
        font-size: 15px;
    }

    /* TECNOLOGIAS */

    .tecnologias {
        background: #0d0d0d;
    }

    .tech-list {
        display: grid;
        grid-template-columns: repeat(4, 1fr);
        gap: 20px;
    }

    .tech {
        background: var(--cinza);
        padding: 25px;
        text-align: center;
        border-radius: 10px;
    }

    .tech .tech-icon {
        font-size: 35px;
        margin-bottom: 10px;
    }

    .tech h3 {
        margin-bottom: 5px;
    }

    .tech p {
        color: #888;
        font-size: 14px;
    }

    /* FUNCIONALIDADES */

    .funcionalidades {
        display: grid;
        grid-template-columns: 1fr 1fr;
        gap: 25px;
    }

    .feature {
        background: var(--cinza);
        padding: 25px;
        border-radius: 8px;
        display: flex;
        gap: 20px;
        align-items: flex-start;
    }

    .feature-number {
        color: var(--vermelho);
        font-size: 25px;
        font-weight: bold;
    }

    .feature p {
        color: #999;
        margin-top: 5px;
    }

    /* PROCESSO */

    .timeline {
        border-left: 2px solid var(--vermelho);
        padding-left: 30px;
    }

    .timeline-item {
        margin-bottom: 40px;
        position: relative;
    }

    .timeline-item::before {
        content: "";
        position: absolute;
        left: -39px;
        top: 5px;
        width: 14px;
        height: 14px;
        background: var(--vermelho);
        border-radius: 50%;
    }

    .timeline-item h3 {
        margin-bottom: 8px;
    }

    .timeline-item p {
        color: #999;
    }

    /* GALERIA */

    .galeria {
        display: grid;
        grid-template-columns: repeat(3, 1fr);
        gap: 20px;
    }

    .imagem {
        height: 220px;
        border-radius: 10px;
        background:
            linear-gradient(135deg, #1c1c1c, #090909);
        border: 1px dashed #444;
        display: flex;
        justify-content: center;
        align-items: center;
        text-align: center;
        color: #777;
        padding: 20px;
    }

    /* CONCLUSÃO */

    .conclusao {
        text-align: center;
        background:
            linear-gradient(rgba(225,6,0,0.1), rgba(225,6,0,0.02)),
            #0d0d0d;
        max-width: none;
    }

    .conclusao-content {
        max-width: 800px;
        margin: auto;
    }

    .conclusao h2 {
        font-size: 45px;
        margin-bottom: 20px;
    }

    .conclusao p {
        color: #aaa;
        font-size: 18px;
    }

    /* FOOTER */

    footer {
        background: #050505;
        border-top: 1px solid #222;
        text-align: center;
        padding: 35px 20px;
        color: #777;
    }

    footer strong {
        color: var(--vermelho);
    }

    /* RESPONSIVO */

    @media (max-width: 900px) {

        nav ul {
            display: none;
        }

        .sobre-content,
        .funcionalidades {
            grid-template-columns: 1fr;
        }

        .objetivos {
            grid-template-columns: 1fr 1fr;
        }

        .tech-list {
            grid-template-columns: 1fr 1fr;
        }

        .galeria {
            grid-template-columns: 1fr 1fr;
        }
    }

    @media (max-width: 600px) {

        section {
            padding: 70px 20px;
        }

        .hero h1 {
            font-size: 48px;
        }

        .section-title h2 {
            font-size: 32px;
        }

        .objetivos,
        .tech-list,
        .galeria {
            grid-template-columns: 1fr;
        }
    }
</style>

</head> <body>
<!-- MENU -->
<header>
    <nav>
        <div class="logo">PAP // DRIVE SIM</div>

        <ul>
            <li><a href="#inicio">Início</a></li>
            <li><a href="#sobre">Projeto</a></li>
            <li><a href="#objetivos">Objetivos</a></li>
            <li><a href="#tecnologias">Tecnologias</a></li>
            <li><a href="#processo">Desenvolvimento</a></li>
            <li><a href="#conclusao">Conclusão</a></li>
        </ul>
    </nav>
</header>

<!-- INÍCIO -->
<div class="hero" id="inicio">

    <div class="hero-content">

        <span class="tag">Prova de Aptidão Profissional</span>

        <h1>
            Simulador de<br>
            <span>Jogos de Condução</span>
        </h1>

        <p>
            Projeto desenvolvido no âmbito da minha PAP,
            com o objetivo de criar uma experiência de condução
            virtual interativa e envolvente.
        </p>

        <a href="#sobre" class="btn">
            Conhecer o projeto ↓
        </a>

    </div>

</div>

<!-- SOBRE O PROJETO -->
<section id="sobre">

    <div class="section-title">
        <small>01 — O Projeto</small>
        <h2>Sobre a minha PAP</h2>
        <p>
            Uma breve apresentação do projeto e dos seus principais objetivos.
        </p>
    </div>

    <div class="sobre-content">

        <div class="sobre-texto">

            <p>
                A minha Prova de Aptidão Profissional consiste no desenvolvimento
                de um simulador de jogos de condução, criado com o objetivo de
                proporcionar ao utilizador uma experiência de condução virtual.
            </p>

            <p>
                O projeto combina programação, desenvolvimento de jogos,
                design e interação com o utilizador, permitindo aplicar
                conhecimentos adquiridos ao longo do curso.
            </p>

            <p>
                O simulador pretende criar uma experiência simples,
                intuitiva e divertida, permitindo ao jogador controlar
                um veículo e explorar diferentes ambientes de condução.
            </p>

        </div>

        <div class="info-box">

            <div>
                <strong>Projeto</strong>
                <span>Simulador de Jogos de Condução</span>
            </div>

            <div>
                <strong>Tipo</strong>
                <span>Prova de Aptidão Profissional</span>
            </div>

            <div>
                <strong>Área</strong>
                <span>Desenvolvimento de Jogos / Programação</span>
            </div>

            <div>
                <strong>Autor</strong>
                <span>Tiago Cunha </span>
            </div>

            <div>
                <strong>Ano</strong>
                <span>2026</span>
            </div>

        </div>

    </div>

</section>

<!-- OBJETIVOS -->
<section id="objetivos">

    <div class="section-title">
        <small>02 — Objetivos</small>
        <h2>O que pretendo alcançar</h2>
        <p>
            Principais objetivos definidos para o desenvolvimento do projeto.
        </p>
    </div>

    <div class="objetivos">

        <div class="card">
            <div class="icon">🎮</div>
            <h3>Experiência Interativa</h3>
            <p>
                Criar uma experiência de condução interativa,
                intuitiva e agradável para o utilizador.
            </p>
        </div>

        <div class="card">
            <div class="icon">💻</div>
            <h3>Aplicar Conhecimentos</h3>
            <p>
                Aplicar conhecimentos de programação, design,
                desenvolvimento e resolução de problemas.
            </p>
        </div>

        <div class="card">
            <div class="icon">🏎️</div>
            <h3>Simulação de Condução</h3>
            <p>
                Desenvolver mecânicas que representem,
                de forma simplificada, uma experiência de condução.
            </p>
        </div>

    </div>

</section>

<!-- TECNOLOGIAS -->
<section class="tecnologias" id="tecnologias">

    <div class="section-title">
        <small>03 — Tecnologias</small>
        <h2>Ferramentas utilizadas</h2>
        <p>
            Tecnologias e ferramentas utilizadas durante o desenvolvimento
            do projeto.
        </p>
    </div>

    <div class="tech-list">

        <div class="tech">
            <div class="tech-icon">💻</div>
            <h3>Programação</h3>
            <p>
                Linguagens e ferramentas utilizadas
                no desenvolvimento do simulador.
            </p>
        </div>

        <div class="tech">
            <div class="tech-icon">🎮</div>
            <h3>Game Engine</h3>
            <p>
                Ambiente utilizado para criar
                a experiência de jogo.
            </p>
        </div>

        <div class="tech">
            <div class="tech-icon">🎨</div>
            <h3>Design</h3>
            <p>
                Criação da interface e elementos
                visuais do projeto.
            </p>
        </div>

        <div class="tech">
            <div class="tech-icon">🗂️</div>
            <h3>Gestão</h3>
            <p>
                Organização das tarefas, ficheiros
                e etapas do desenvolvimento.
            </p>
        </div>

    </div>

</section>

<!-- FUNCIONALIDADES -->
<section id="funcionalidades">

    <div class="section-title">
        <small>04 — Funcionalidades</small>
        <h2>O que o simulador oferece</h2>
        <p>
            Algumas das principais funcionalidades desenvolvidas
            para o projeto.
        </p>
    </div>

    <div class="funcionalidades">

        <div class="feature">
            <div class="feature-number">01</div>
            <div>
                <h3>Controlo do veículo</h3>
                <p>
                    Sistema de controlo que permite ao jogador
                    conduzir o veículo durante a experiência.
                </p>
            </div>
        </div>

        <div class="feature">
            <div class="feature-number">02</div>
            <div>
                <h3>Ambiente de condução</h3>
                <p>
                    Cenários desenvolvidos para proporcionar
                    um ambiente de jogo envolvente.
                </p>
            </div>
        </div>

        <div class="feature">
            <div class="feature-number">03</div>
            <div>
                <h3>Interface</h3>
                <p>
                    Interface criada para apresentar ao jogador
                    as informações necessárias durante o jogo.
                </p>
            </div>
        </div>

        <div class="feature">
            <div class="feature-number">04</div>
            <div>
                <h3>Interação</h3>
                <p>
                    Elementos interativos que permitem ao jogador
                    controlar e interagir com o simulador.
                </p>
            </div>
        </div>

    </div>

</section>

<!-- DESENVOLVIMENTO -->
<section id="processo">

    <div class="section-title">
        <small>05 — Desenvolvimento</small>
        <h2>Processo de criação</h2>
        <p>
            As principais etapas realizadas durante o desenvolvimento da PAP.
        </p>
    </div>

    <div class="timeline">

        <div class="timeline-item">
            <h3>01. Planeamento</h3>
            <p>
                Definição da ideia, objetivos, funcionalidades
                e características principais do projeto.
            </p>
        </div>

        <div class="timeline-item">
            <h3>02. Pesquisa</h3>
            <p>
                Pesquisa de referências, tecnologias e soluções
                que poderiam ser utilizadas no projeto.
            </p>
        </div>

        <div class="timeline-item">
            <h3>03. Desenvolvimento</h3>
            <p>
                Implementação das funcionalidades e construção
                do simulador.
            </p>
        </div>

        <div class="timeline-item">
            <h3>04. Testes</h3>
            <p>
                Testes realizados para identificar erros,
                corrigir problemas e melhorar a experiência.
            </p>
        </div>

        <div class="timeline-item">
            <h3>05. Resultado final</h3>
            <p>
                Finalização do projeto e preparação da apresentação
                da Prova de Aptidão Profissional.
            </p>
        </div>

    </div>

</section>

<!-- GALERIA -->
<section id="galeria">

    <div class="section-title">
        <small>06 — Projeto</small>
        <h2>Galeria</h2>
        <p>
            Coloca aqui imagens e screenshots reais do teu simulador.
        </p>
    </div>

    <div class="galeria">

        <div class="imagem">
            <span>📷<br><br>
            Screenshot do menu principal</span>
        </div>

        <div class="imagem">
            <span>📷<br><br>
            Screenshot do simulador</span>
        </div>

        <div class="imagem">
            <span>📷<br><br>
            Screenshot do veículo</span>
        </div>

    </div>

</section>

<!-- CONCLUSÃO -->
<section class="conclusao" id="conclusao">

    <div class="conclusao-content">

        <div class="section-title">
            <small>07 — Conclusão</small>
            <h2>O resultado</h2>
        </div>

        <p>
            O desenvolvimento desta PAP permitiu colocar em prática
            conhecimentos adquiridos ao longo do curso e enfrentar
            diferentes desafios relacionados com programação,
            desenvolvimento de jogos e design.
        </p>

        <p style="margin-top: 20px;">
            Este projeto representa não só o resultado do trabalho
            desenvolvido, mas também todo o processo de aprendizagem,
            experimentação e evolução realizado durante a sua criação.
        </p>

    </div>

</section>

<!-- FOOTER -->
<footer>

    <p>
        PAP — <strong>Simulador de Jogos de Condução</strong>
    </p>

    <p style="margin-top: 8px;">
        Desenvolvido por <strong>Tiago Cunha</strong> · 2026
    </p>

</footer>
