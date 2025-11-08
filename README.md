<!DOCTYPE html>
<html lang="pt-BR">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Consultoria LR 2.0 - Transformação Estruturada</title>
    <link href="https://fonts.googleapis.com/css2?family=Montserrat:wght@400;500;600;700&family=Inter:wght@300;400;500;600&display=swap" rel="stylesheet">
    <style>
        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
        }

        :root {
            --preto: #1A1A1A;
            --preto-escuro: #0D0D0D;
            --branco: #FFFFFF;
            --cinza-medio: #B0B0B0;
            --cinza-claro: #808080;
            --verde-lima: #7FD700;
            --verde-quente: #6EC800;
        }

        html {
            scroll-behavior: smooth;
        }

        body {
            font-family: 'Inter', sans-serif;
            background-color: var(--preto);
            color: var(--branco);
            line-height: 1.6;
            overflow-x: hidden;
        }

        /* ==================== HEADER STICKY ==================== */
        header {
            position: fixed;
            top: 0;
            width: 100%;
            height: 60px;
            background-color: rgba(26, 26, 26, 0.95);
            border-bottom: 1px solid rgba(127, 253, 0, 0.2);
            display: flex;
            justify-content: space-between;
            align-items: center;
            padding: 0 40px;
            z-index: 1000;
            backdrop-filter: blur(10px);
            transition: all 0.3s ease;
        }

        header .logo {
            display: flex;
            align-items: center;
            gap: 12px;
            text-decoration: none;
            color: var(--verde-lima);
            font-weight: 700;
            font-size: 18px;
            letter-spacing: 1px;
        }

        header .logo svg {
            width: 40px;
            height: 40px;
        }

        header .spacer {
            flex: 1;
        }

        header .cta-btn {
            background-color: var(--verde-quente);
            color: var(--branco);
            padding: 10px 25px;
            border: none;
            border-radius: 4px;
            font-weight: 700;
            font-size: 14px;
            cursor: pointer;
            transition: all 0.3s ease;
            text-decoration: none;
            display: inline-block;
            font-family: 'Montserrat', sans-serif;
            letter-spacing: 0.5px;
        }

        header .cta-btn:hover {
            background-color: #5FB300;
            box-shadow: 0 4px 12px rgba(110, 200, 0, 0.3);
            transform: translateY(-2px);
        }

        @media (max-width: 768px) {
            header {
                padding: 0 20px;
            }

            header .logo {
                font-size: 14px;
            }

            header .cta-btn {
                padding: 8px 16px;
                font-size: 12px;
            }
        }

        /* ==================== HERO SECTION ==================== */
        .hero {
            margin-top: 60px;
            min-height: 550px;
            background-color: var(--preto);
            padding: 100px 60px;
            display: flex;
            align-items: center;
            gap: 60px;
            position: relative;
            overflow: hidden;
        }

        .hero::before {
            content: '';
            position: absolute;
            top: 0;
            left: 0;
            right: 0;
            bottom: 0;
            background: radial-gradient(circle at 20% 50%, rgba(127, 253, 0, 0.05) 0%, transparent 50%);
            pointer-events: none;
        }

        .hero-content {
            flex: 1;
            z-index: 10;
            max-width: 500px;
        }

        .hero h1 {
            font-family: 'Montserrat', sans-serif;
            font-size: 48px;
            font-weight: 700;
            line-height: 1.2;
            margin-bottom: 20px;
            letter-spacing: -1px;
            color: var(--branco);
        }

        .hero h1 .emoji {
            font-size: 1.1em;
            margin-right: 10px;
        }

        .hero .subtitle {
            font-size: 18px;
            color: var(--cinza-medio);
            line-height: 1.6;
            margin-bottom: 30px;
            font-weight: 400;
        }

        .hero .highlights {
            display: flex;
            flex-direction: column;
            gap: 12px;
            margin-bottom: 30px;
        }

        .hero .highlight-item {
            display: flex;
            align-items: flex-start;
            gap: 12px;
            font-size: 14px;
            color: var(--branco);
        }

        .hero .highlight-item .icon {
            color: var(--verde-lima);
            font-weight: 700;
            flex-shrink: 0;
        }

        .hero .cta-primary {
            background-color: var(--verde-quente);
            color: var(--branco);
            padding: 14px 40px;
            border: none;
            border-radius: 4px;
            font-weight: 700;
            font-size: 16px;
            cursor: pointer;
            transition: all 0.3s ease;
            font-family: 'Montserrat', sans-serif;
            letter-spacing: 0.5px;
            display: inline-block;
            text-decoration: none;
        }

        .hero .cta-primary:hover {
            background-color: #5FB300;
            box-shadow: 0 6px 20px rgba(110, 200, 0, 0.4);
            transform: translateY(-3px);
        }

        .hero-visual {
            flex: 1;
            display: flex;
            justify-content: center;
            align-items: center;
            z-index: 10;
        }

        .hero-visual img {
            width: 100%;
            max-width: 400px;
            height: auto;
            border: 2px solid var(--verde-lima);
            border-radius: 8px;
            box-shadow: 0 10px 40px rgba(127, 253, 0, 0.15);
            animation: float 3s ease-in-out infinite;
        }

        @keyframes float {
            0%, 100% { transform: translateY(0px); }
            50% { transform: translateY(-10px); }
        }

        @media (max-width: 1024px) {
            .hero {
                gap: 40px;
                padding: 80px 40px;
            }

            .hero h1 {
                font-size: 36px;
            }

            .hero .subtitle {
                font-size: 16px;
            }

            .hero-visual {
                display: none;
            }
        }

        @media (max-width: 768px) {
            .hero {
                min-height: 700px;
                padding: 40px 20px;
                text-align: center;
            }

            .hero-content {
                max-width: 100%;
            }

            .hero h1 {
                font-size: 32px;
            }

            .hero .subtitle {
                font-size: 14px;
            }

            .hero .highlights {
                align-items: center;
            }

            .hero .cta-primary {
                width: 90%;
            }
        }

        /* ==================== SEÇÃO DORES ==================== */
        .dores-section {
            background-color: var(--preto);
            padding: 80px 60px;
            margin-top: 40px;
            border-top: 1px solid rgba(127, 253, 0, 0.2);
        }

        .section-title {
            font-family: 'Montserrat', sans-serif;
            font-size: 32px;
            font-weight: 600;
            text-align: center;
            margin-bottom: 50px;
            letter-spacing: -0.5px;
            line-height: 1.3;
            color: var(--branco);
        }

        .cards-grid {
            display: grid;
            grid-template-columns: repeat(3, 1fr);
            gap: 30px;
        }

        .card {
            background-color: rgba(110, 200, 0, 0.08);
            border: 1px solid rgba(127, 253, 0, 0.3);
            border-radius: 6px;
            padding: 25px;
            min-height: 200px;
            display: flex;
            flex-direction: column;
            justify-content: space-between;
            transition: all 0.3s ease;
            box-shadow: 0 2px 8px rgba(0, 0, 0, 0.1);
        }

        .card:hover {
            border-color: var(--verde-lima);
            background-color: rgba(110, 200, 0, 0.12);
            transform: translateY(-5px);
        }

        .card-icon {
            font-size: 24px;
            color: var(--verde-lima);
            margin-bottom: 15px;
            font-weight: 700;
        }

        .card-title {
            font-family: 'Montserrat', sans-serif;
            font-size: 20px;
            font-weight: 500;
            margin-bottom: 12px;
            color: var(--branco);
            line-height: 1.3;
        }

        .card-description {
            font-size: 14px;
            color: var(--cinza-medio);
            line-height: 1.5;
            font-weight: 400;
        }

        @media (max-width: 1024px) {
            .cards-grid {
                grid-template-columns: repeat(2, 1fr);
            }
        }

        @media (max-width: 768px) {
            .dores-section {
                padding: 60px 20px;
            }

            .section-title {
                font-size: 24px;
            }

            .cards-grid {
                grid-template-columns: 1fr;
                gap: 20px;
            }
        }

        /* ==================== SEÇÃO SOLUÇÃO ==================== */
        .solucao-section {
            background-color: var(--preto-escuro);
            padding: 80px 60px;
            margin-top: 40px;
            border-top: 1px solid rgba(127, 253, 0, 0.2);
            display: flex;
            gap: 60px;
            align-items: center;
        }

        .solucao-visual {
            flex: 1;
            display: flex;
            justify-content: center;
        }

        .solucao-visual img {
            width: 100%;
            max-width: 400px;
            height: auto;
            border: 2px solid var(--verde-lima);
            border-radius: 8px;
            box-shadow: 0 10px 40px rgba(127, 253, 0, 0.2);
        }

        .solucao-content {
            flex: 1;
            max-width: 450px;
        }

        .solucao-content h2 {
            font-family: 'Montserrat', sans-serif;
            font-size: 32px;
            font-weight: 600;
            margin-bottom: 15px;
            line-height: 1.3;
            color: var(--branco);
        }

        .solucao-description {
            font-size: 16px;
            color: var(--cinza-medio);
            line-height: 1.6;
            margin-bottom: 30px;
            font-weight: 400;
        }

        .benefits-list {
            display: flex;
            flex-direction: column;
            gap: 20px;
        }

        .benefit-item {
            display: flex;
            align-items: flex-start;
            gap: 15px;
        }

        .benefit-icon {
            color: var(--verde-lima);
            font-weight: 700;
            font-size: 22px;
            flex-shrink: 0;
            margin-top: 2px;
        }

        .benefit-content {
            display: flex;
            flex-direction: column;
            gap: 5px;
        }

        .benefit-title {
            font-family: 'Montserrat', sans-serif;
            font-size: 16px;
            font-weight: 600;
            color: var(--branco);
            line-height: 1.3;
        }

        .benefit-description {
            font-size: 13px;
            color: var(--cinza-medio);
            line-height: 1.5;
            font-weight: 400;
        }

        @media (max-width: 1024px) {
            .solucao-section {
                flex-direction: column;
                gap: 40px;
                padding: 60px 40px;
            }

            .solucao-visual,
            .solucao-content {
                flex: 1;
                max-width: 100%;
            }

            .solucao-visual img {
                max-width: 350px;
            }
        }

        @media (max-width: 768px) {
            .solucao-section {
                padding: 60px 20px;
            }

            .solucao-visual {
                display: none;
            }

            .solucao-content h2 {
                font-size: 24px;
            }
        }

        /* ==================== SEÇÃO SUPORTE ==================== */
        .suporte-section {
            background-color: var(--preto);
            padding: 80px 60px;
            margin-top: 40px;
            border-top: 1px solid rgba(127, 253, 0, 0.2);
        }

        .steps-grid {
            display: grid;
            grid-template-columns: repeat(3, 1fr);
            gap: 25px;
            position: relative;
        }

        .step-card {
            background-color: rgba(110, 200, 0, 0.08);
            border: 1px solid rgba(127, 253, 0, 0.3);
            border-radius: 6px;
            padding: 30px 20px;
            min-height: 220px;
            text-align: center;
            display: flex;
            flex-direction: column;
            justify-content: space-between;
            transition: all 0.3s ease;
        }

        .step-card:hover {
            border-color: var(--verde-lima);
            background-color: rgba(110, 200, 0, 0.12);
        }

        .step-number {
            font-family: 'Montserrat', sans-serif;
            font-size: 40px;
            font-weight: 700;
            color: var(--verde-lima);
            margin-bottom: 15px;
            opacity: 0.9;
        }

        .step-title {
            font-family: 'Montserrat', sans-serif;
            font-size: 20px;
            font-weight: 600;
            color: var(--branco);
            margin-bottom: 12px;
            line-height: 1.3;
        }

        .step-divisor {
            height: 2px;
            width: 30px;
            background-color: var(--verde-lima);
            margin: 15px auto;
            opacity: 0.8;
        }

        .step-description {
            font-size: 14px;
            color: var(--cinza-medio);
            line-height: 1.5;
            font-weight: 400;
        }

        @media (max-width: 1024px) {
            .steps-grid {
                grid-template-columns: repeat(2, 1fr);
            }
        }

        @media (max-width: 768px) {
            .suporte-section {
                padding: 60px 20px;
            }

            .steps-grid {
                grid-template-columns: 1fr;
                gap: 20px;
            }
        }

        /* ==================== SEÇÃO DEPOIMENTOS ==================== */
        .depoimentos-section {
            background-color: var(--preto-escuro);
            padding: 80px 60px;
            margin-top: 40px;
            border-top: 1px solid rgba(127, 253, 0, 0.2);
        }

        .testimonials-grid {
            display: grid;
            grid-template-columns: repeat(3, 1fr);
            gap: 25px;
        }

        .testimonial-card {
            background-color: rgba(110, 200, 0, 0.08);
            border: 1px solid rgba(127, 253, 0, 0.3);
            border-radius: 8px;
            padding: 25px;
            min-height: 260px;
            display: flex;
            flex-direction: column;
            justify-content: space-between;
            transition: all 0.3s ease;
            box-shadow: 0 4px 12px rgba(0, 0, 0, 0.3);
        }

        .testimonial-card:hover {
            border-color: var(--verde-lima);
            background-color: rgba(110, 200, 0, 0.12);
        }

        .stars {
            font-size: 14px;
            color: var(--verde-lima);
            margin-bottom: 15px;
            letter-spacing: 1px;
        }

        .testimonial-text {
            font-size: 14px;
            color: var(--branco);
            line-height: 1.6;
            margin-bottom: 15px;
            font-style: italic;
            font-weight: 400;
        }

        .testimonial-divisor {
            height: 1px;
            width: 100%;
            background-color: rgba(127, 253, 0, 0.3);
            margin: 15px 0;
        }

        .testimonial-author-section {
            display: flex;
            flex-direction: column;
            align-items: flex-start;
            gap: 5px;
        }

        .testimonial-author {
            font-family: 'Montserrat', sans-serif;
            font-size: 15px;
            font-weight: 600;
            color: var(--branco);
        }

        .testimonial-result {
            font-size: 12px;
            color: var(--verde-lima);
            font-weight: 500;
        }

        @media (max-width: 1024px) {
            .testimonials-grid {
                grid-template-columns: repeat(2, 1fr);
            }
        }

        @media (max-width: 768px) {
            .depoimentos-section {
                padding: 60px 20px;
            }

            .testimonials-grid {
                grid-template-columns: 1fr;
            }
        }

        /* ==================== SEÇÃO PROMO ==================== */
        .promo-section {
            background: linear-gradient(135deg, var(--preto) 0%, var(--preto-escuro) 100%);
            padding: 60px 60px;
            margin-top: 40px;
            border-top: 2px solid var(--verde-lima);
            border-bottom: 2px solid var(--verde-lima);
            text-align: center;
        }

        .promo-title {
            font-family: 'Montserrat', sans-serif;
            font-size: 28px;
            font-weight: 600;
            color: var(--branco);
            margin-bottom: 15px;
            line-height: 1.3;
        }

        .promo-urgency {
            font-family: 'Montserrat', sans-serif;
            font-size: 18px;
            font-weight: 700;
            color: var(--verde-quente);
            letter-spacing: 1px;
            text-transform: uppercase;
            background-color: rgba(110, 200, 0, 0.1);
            padding: 10px 20px;
            border-radius: 4px;
            display: inline-block;
            margin: 20px 0 30px 0;
        }

        .promo-description {
            font-size: 15px;
            color: var(--branco);
            line-height: 1.6;
            margin-bottom: 25px;
            max-width: 600px;
            margin-left: auto;
            margin-right: auto;
        }

        .promo-btn {
            background-color: var(--verde-quente);
            color: var(--branco);
            padding: 16px 50px;
            border: none;
            border-radius: 4px;
            font-weight: 700;
            font-size: 18px;
            cursor: pointer;
            transition: all 0.3s ease;
            font-family: 'Montserrat', sans-serif;
            display: inline-block;
            text-decoration: none;
            letter-spacing: 0.5px;
            box-shadow: 0 6px 20px rgba(110, 200, 0, 0.3);
        }

        .promo-btn:hover {
            background-color: #5FB300;
            box-shadow: 0 8px 25px rgba(110, 200, 0, 0.4);
            transform: translateY(-3px);
        }

        @media (max-width: 768px) {
            .promo-section {
                padding: 40px 20px;
            }

            .promo-title {
                font-size: 22px;
            }

            .promo-btn {
                width: 90%;
                font-size: 16px;
            }
        }

        /* ==================== SEÇÃO CTA FINAL ==================== */
        .cta-final-section {
            background-color: var(--preto);
            padding: 60px 60px;
            margin-top: 40px;
            text-align: center;
        }

        .cta-final-title {
            font-family: 'Montserrat', sans-serif;
            font-size: 28px;
            font-weight: 600;
            color: var(--branco);
            margin-bottom: 15px;
            line-height: 1.3;
        }

        .cta-final-subtitle {
            font-family: 'Montserrat', sans-serif;
            font-size: 20px;
            font-weight: 600;
            color: var(--verde-lima);
            margin-bottom: 30px;
        }

        .cta-final-btn {
            background-color: var(--verde-quente);
            color: var(--branco);
            padding: 14px 45px;
            border: none;
            border-radius: 4px;
            font-weight: 700;
            font-size: 16px;
            cursor: pointer;
            transition: all 0.3s ease;
            font-family: 'Montserrat', sans-serif;
            display: inline-block;
            text-decoration: none;
            letter-spacing: 0.5px;
            margin-bottom: 15px;
        }

        .cta-final-btn:hover {
            background-color: #5FB300;
            box-shadow: 0 6px 16px rgba(110, 200, 0, 0.3);
            transform: translateY(-2px);
        }

        .cta-final-description {
            font-size: 13px;
            color: var(--cinza-medio);
            font-weight: 400;
        }

        @media (max-width: 768px) {
            .cta-final-section {
                padding: 40px 20px;
            }

            .cta-final-title {
                font-size: 24px;
            }

            .cta-final-btn {
                width: 90%;
            }
        }

        /* ==================== FOOTER ==================== */
        footer {
            background-color: var(--preto-escuro);
            padding: 40px 60px;
            margin-top: 40px;
            border-top: 1px solid rgba(127, 253, 0, 0.2);
            display: grid;
            grid-template-columns: repeat(3, 1fr);
            gap: 40px;
        }

        .footer-column h3 {
            font-family: 'Montserrat', sans-serif;
            font-size: 13px;
            font-weight: 600;
            color: var(--branco);
            text-transform: uppercase;
            letter-spacing: 0.5px;
            margin-bottom: 12px;
        }

        .footer-logo {
            width: 40px;
            height: 40px;
            background-color: var(--verde-lima);
            border-radius: 4px;
            margin-bottom: 10px;
        }

        .footer-brand {
            font-family: 'Montserrat', sans-serif;
            font-size: 14px;
            font-weight: 700;
            color: var(--branco);
            margin-bottom: 5px;
            letter-spacing: 0.5px;
        }

        .footer-tagline {
            font-size: 12px;
            color: var(--cinza-medio);
            font-weight: 400;
        }

        .footer-link {
            display: block;
            font-size: 12px;
            color: var(--cinza-medio);
            text-decoration: none;
            margin-bottom: 8px;
            transition: color 0.2s ease;
        }

        .footer-link:hover {
            color: var(--verde-lima);
        }

        .footer-copyright {
            font-size: 11px;
            color: var(--cinza-claro);
            font-weight: 400;
            margin-bottom: 12px;
        }

        @media (max-width: 768px) {
            footer {
                grid-template-columns: 1fr;
                gap: 30px;
                padding: 40px 20px;
            }
        }

        /* ==================== UTILITIES ==================== */
        .container {
            max-width: 1200px;
            margin: 0 auto;
        }

        @media (max-width: 768px) {
            .hero h1 .emoji {
                display: block;
                margin-bottom: 10px;
            }
        }
    </style>
</head>
<body>

    <!-- ==================== HEADER ==================== -->
    <header>
        <a href="#" class="logo">
            <span style="font-size: 20px; color: var(--verde-lima);">■</span>
            LR 2.0
        </a>
        <div class="spacer"></div>
        <a href="https://wa.me/seu_numero_whatsapp" class="cta-btn">ENTRAR NO GRUPO</a>
    </header>

    <!-- ==================== HERO SECTION ==================== -->
    <section class="hero">
        <div class="hero-content">
            <h1>
                <span class="emoji">🚀</span>
                Transformação Estruturada Sai Hoje<br>
                <span style="color: var(--verde-lima);">−25% Black Friday</span>
            </h1>
            
            <p class="subtitle">
                Chega de treinar sem ter resultados.<br>
                Aqui o acompanhamento é de <strong>VERDADE</strong>.
            </p>

            <div class="highlights">
                <div class="highlight-item">
                    <span class="icon">✅</span>
                    <span>Treino 100% personalizado (não ficha pronta)</span>
                </div>
                <div class="highlight-item">
                    <span class="icon">✅</span>
                    <span>Aprenda a progressão (fica sabendo forever)</span>
                </div>
                <div class="highlight-item">
                    <span class="icon">✅</span>
                    <span>Suporte &lt;2h garantido</span>
                </div>
            </div>

            <a href="https://wa.me/seu_numero_whatsapp" class="cta-primary">ENTRAR NO GRUPO AGORA</a>
        </div>

        <div class="hero-visual">
            <img src="https://via.placeholder.com/400x500/1a1a1a/7FD700?text=Sua+Foto+Aqui" alt="Consultoria LR 2.0">
        </div>
    </section>

    <!-- ==================== SEÇÃO DORES ==================== -->
    <section class="dores-section">
        <h2 class="section-title">Você Enfrenta Algum Desses Problemas?</h2>

        <div class="cards-grid">
            <!-- Card 1 -->
            <div class="card">
                <div>
                    <div class="card-icon">❌</div>
                    <h3 class="card-title">Segue Treino Genérico</h3>
                </div>
                <p class="card-description">
                    Ficha pronta da internet não funciona pra você. Sem progressão, platô eterno, frustração.
                </p>
            </div>

            <!-- Card 2 -->
            <div class="card">
                <div>
                    <div class="card-icon">❌</div>
                    <h3 class="card-title">Não Aprende a Treinar</h3>
                </div>
                <p class="card-description">
                    Sabe fazer o exercício, mas não sabe PROGREDIR. Platô eterno, desmotivação.
                </p>
            </div>

            <!-- Card 3 -->
            <div class="card">
                <div>
                    <div class="card-icon">❌</div>
                    <h3 class="card-title">Suporte Ruim ou Inexistente</h3>
                </div>
                <p class="card-description">
                    Dúvida fica sem resposta. Executa errado e se machuca. Lesão, insegurança, desistência.
                </p>
            </div>
        </div>
    </section>

    <!-- ==================== SEÇÃO SOLUÇÃO ==================== -->
    <section class="solucao-section">
        <div class="solucao-visual">
            <img src="https://via.placeholder.com/400x500/0d0d0d/7FD700?text=Transformação" alt="Transformação">
        </div>

        <div class="solucao-content">
            <h2>Consultoria LR 2.0: A Solução</h2>
            
            <p class="solucao-description">
                Não vendemos fichas. Entregamos educação, personalização e suporte que TRANSFORMA.<br><br>
                Você aprende a treinar certo. E isso fica pra sempre.
            </p>

            <div class="benefits-list">
                <!-- Benefit 1 -->
                <div class="benefit-item">
                    <div class="benefit-icon">✅</div>
                    <div class="benefit-content">
                        <div class="benefit-title">Treino 100% Seu</div>
                        <div class="benefit-description">Personalizado para sua biomecânica e objetivo real</div>
                    </div>
                </div>

                <!-- Benefit 2 -->
                <div class="benefit-item">
                    <div class="benefit-icon">✅</div>
                    <div class="benefit-content">
                        <div class="benefit-title">Aprenda a Progressão</div>
                        <div class="benefit-description">6 meses e você sabe exatamente como evoluir sozinho</div>
                    </div>
                </div>

                <!-- Benefit 3 -->
                <div class="benefit-item">
                    <div class="benefit-icon">✅</div>
                    <div class="benefit-content">
                        <div class="benefit-title">Suporte &lt;2h Garantido</div>
                        <div class="benefit-description">Responde rápido. Vídeos seus exercícios. Sempre presente.</div>
                    </div>
                </div>
            </div>
        </div>
    </section>

    <!-- ==================== SEÇÃO SUPORTE ==================== -->
    <section class="suporte-section">
        <h2 class="section-title">Como Funciona o Suporte</h2>

        <div class="steps-grid">
            <!-- Step 1 -->
            <div class="step-card">
                <div>
                    <div class="step-number">1️⃣</div>
                    <h3 class="step-title">Você Envia Dúvida</h3>
                    <div class="step-divisor"></div>
                </div>
                <p class="step-description">
                    "Como aumento carga sem me lesionar?" Via WhatsApp (rápido mesmo)
                </p>
            </div>

            <!-- Step 2 -->
            <div class="step-card">
                <div>
                    <div class="step-number">2️⃣</div>
                    <h3 class="step-title">Resposta em &lt;2h</h3>
                    <div class="step-divisor"></div>
                </div>
                <p class="step-description">
                    Você recebe mensagem estruturada com resposta. Se for dúvida de execução, recebe vídeo SEU exercício.
                </p>
            </div>

            <!-- Step 3 -->
            <div class="step-card">
                <div>
                    <div class="step-number">3️⃣</div>
                    <h3 class="step-title">Você Evolui com Segurança</h3>
                    <div class="step-divisor"></div>
                </div>
                <p class="step-description">
                    Confiante, seguro, sabendo exatamente o que fazer. Resultado: Transformação real, consistência mantida.
                </p>
            </div>
        </div>
    </section>

    <!-- ==================== SEÇÃO DEPOIMENTOS ==================== -->
    <section class="depoimentos-section">
        <h2 class="section-title">Histórias Reais de Transformação</h2>

        <div class="testimonials-grid">
            <!-- Testimonial 1 -->
            <div class="testimonial-card">
                <div>
                    <div class="stars">⭐⭐⭐⭐⭐</div>
                    <p class="testimonial-text">
                        "Mudou meu conceito sobre treino. Agora eu treino com PROPÓSITO, não só movimentos aleatórios."
                    </p>
                </div>
                <div class="testimonial-divisor"></div>
                <div class="testimonial-author-section">
                    <div class="testimonial-author">Ana Silva, 34 anos</div>
                    <div class="testimonial-result">└─ −8kg em 3 meses</div>
                </div>
            </div>

            <!-- Testimonial 2 -->
            <div class="testimonial-card">
                <div>
                    <div class="stars">⭐⭐⭐⭐⭐</div>
                    <p class="testimonial-text">
                        "Aprendi a treinar CERTO. Agora sei quando aumentar carga, quando aumentar volume. Sou independente."
                    </p>
                </div>
                <div class="testimonial-divisor"></div>
                <div class="testimonial-author-section">
                    <div class="testimonial-author">Julia Santos, 29 anos</div>
                    <div class="testimonial-result">└─ −12kg + ganho de massa</div>
                </div>
            </div>

            <!-- Testimonial 3 -->
            <div class="testimonial-card">
                <div>
                    <div class="stars">⭐⭐⭐⭐⭐</div>
                    <p class="testimonial-text">
                        "Suporte rápido = resultado rápido. Resposta em menos de 2h resolveu minha insegurança. Recomendo muito!"
                    </p>
                </div>
                <div class="testimonial-divisor"></div>
                <div class="testimonial-author-section">
                    <div class="testimonial-author">Maria Oliveira, 41 anos</div>
                    <div class="testimonial-result">└─ Transformação completa</div>
                </div>
            </div>
        </div>
    </section>

    <!-- ==================== SEÇÃO PROMO ==================== -->
    <section class="promo-section">
        <h2 class="promo-title">🚀 Black Friday - Consultoria LR 2.0</h2>
        
        
        <p class="promo-description">
            Treino 100% seu + Educação + Suporte &lt;2h + Biblioteca
        </p>

        <a href="https://wa.me/seu_numero_whatsapp" class="promo-btn">ENTRAR NO GRUPO AGORA</a>
    </section>

    <!-- ==================== SEÇÃO CTA FINAL ==================== -->
    <section class="cta-final-section">
        <h2 class="cta-final-title">Pronto(a) para Transformar?</h2>
        
        <h3 class="cta-final-subtitle">Consultoria LR 2.0 — Transformação Estruturada</h3>
        
        <a href="https://wa.me/seu_numero_whatsapp" class="cta-final-btn">ENTRA NO GRUPO</a>
        
        <p class="cta-final-description">
            Grupo privado com oferta exclusiva + dúvidas respondidas
        </p>
    </section>

    <!-- ==================== FOOTER ==================== -->
    <footer>
        <!-- Column 1 - Brand -->
        <div class="footer-column">
            <div class="footer-logo"></div>
            <div class="footer-brand">Consultoria LR 2.0</div>
            <div class="footer-tagline">Transformação Estruturada</div>
        </div>

        <!-- Column 2 - Redes Sociais -->
        <div class="footer-column">
            <h3>Siga Nosso Trabalho</h3>
            <a href="https://instagram.com/seu_instagram" class="footer-link">📱 Instagram</a>
            <a href="https://wa.me/seu_numero_whatsapp" class="footer-link">💬 WhatsApp</a>
            <a href="https://linkedin.com/in/seu_linkedin" class="footer-link">💼 LinkedIn</a>
        </div>

        <!-- Column 3 - Legal -->
        <div class="footer-column">
            <h3>Legal</h3>
            <div class="footer-copyright">© 2024 Consultoria LR 2.0. Todos os direitos reservados.</div>
            <a href="#" class="footer-link">Política de Privacidade</a>
            <a href="#" class="footer-link">Termos de Uso</a>
        </div>
    </footer>

    <script>
        // Smooth scroll for anchor links
        document.querySelectorAll('a[href^="#"]').forEach(anchor => {
            anchor.addEventListener('click', function (e) {
                e.preventDefault();
                const target = document.querySelector(this.getAttribute('href'));
                if (target) {
                    target.scrollIntoView({
                        behavior: 'smooth'
                    });
                }
            });
        });

        // Add animation on scroll
        const observerOptions = {
            threshold: 0.1,
            rootMargin: '0px 0px -100px 0px'
        };

        const observer = new IntersectionObserver(function(entries) {
            entries.forEach(entry => {
                if (entry.isIntersecting) {
                    entry.target.style.animation = 'fadeIn 0.6s ease-out';
                }
            });
        }, observerOptions);

        document.querySelectorAll('.card, .step-card, .testimonial-card').forEach(el => {
            observer.observe(el);
        });

        // Add fade-in animation to CSS
        const style = document.createElement('style');
        style.textContent = `
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
        `;
        document.head.appendChild(style);
    </script>

</body>
</html>
