<!DOCTYPE html>
<html>
<head>
    <title>Benvenuto Su DeaService</title>
    <!-- Importazione Font: Inter -->
    <link href="https://fonts.googleapis.com" rel="stylesheet">
    
    <style>
        /* --- STILI BASE --- */
        .top-bar { 
            background-color: #000000; 
            color: #ffffff;          
            padding: 12px 30px; 
            font-family: 'Inter', sans-serif; 
            display: flex;
            justify-content: center; 
            align-items: center;     
            gap: 30px;               
            position: fixed;          
            top: 0;
            left: 0;
            width: 100%;
            z-index: 1000;
            border-bottom: 2px solid #00FF00; 
            box-sizing: border-box;
        }

        .bar-item {
            color: #ffffff;
            text-decoration: none;
            font-weight: 700;
            font-size: 18px; 
            text-transform: uppercase;
            padding: 8px 15px;
            border: 1px solid transparent;
            border-radius: 5px;
            transition: all 0.3s ease;
            font-family: 'Inter', sans-serif;
            letter-spacing: 1px;
            white-space: nowrap;
            display: flex;
            align-items: center;
        }

        a.bar-item:hover {
            color: #00FF00;
            border-color: #00FF00;
            background-color: rgba(0, 255, 0, 0.05);
        }

        .icon-green { 
            color: #00FF00; 
            margin-right: 10px;
            filter: drop-shadow(0 0 2px rgba(0, 255, 0, 0.5));
        }

        body { background-color: #ffffff; margin: 0; padding-top: 130px; font-family: 'Inter', sans-serif; scroll-behavior: smooth; }
        .main-container { padding-left: 50px; padding-right: 50px; }
        
        /* --- BOX PER IL TITOLO --- */
        .title-box {
            display: inline-block; 
            border: 4px solid #00FF00; 
            padding: 15px 30px;
            margin-bottom: 30px;
            box-shadow: 0 0 15px rgba(0, 255, 0, 0.2); 
        }

        h1 { 
            font-family: 'Inter', sans-serif; 
            font-size: 70px; 
            font-weight: 900; 
            margin: 0; 
            color: #00FF00; 
            line-height: 1.0; 
            text-transform: none; 
        }

        .descrizione { color: #1a1a1a; font-size: 20px; margin-top: 25px; max-width: 750px; line-height: 1.8; border-left: 5px solid #00FF00; padding-left: 25px; font-weight: 400; margin-bottom: 40px; }
        /* Classe per il testo verde */
        b { color: #008000; } 

        /* --- SISTEMA FAQ --- */
        .faq-item {
            max-width: 750px;
            margin-bottom: 15px;
            background-color: #f9f9f9;
            border: 1px solid #ddd;
            border-radius: 12px;
            overflow: hidden;
            transition: border-color 0.3s ease;
        }
        .faq-item:hover { border-color: #00FF00; }
        summary { list-style: none; outline: none; }
        summary::-webkit-details-marker { display: none; }
        .faq-question {
            font-weight: 700;
            padding: 20px;
            display: flex;
            justify-content: space-between;
            align-items: center;
            user-select: none;
            cursor: pointer;
        }
        .faq-question::after {
            content: '▼'; 
            font-size: 12px;
            transition: transform 0.4s cubic-bezier(0.4, 0, 0.2, 1);
            color: #00FF00;
        }
        .faq-item[open] .faq-question::after { transform: rotate(180deg); }
        .faq-content-wrapper {
            display: grid;
            grid-template-rows: 0fr; 
            transition: grid-template-rows 0.4s cubic-bezier(0.4, 0, 0.2, 1), padding 0.4s cubic-bezier(0.4, 0, 0.2, 1), opacity 0.3s ease;
            padding: 0 20px;
            opacity: 0;
        }
        .faq-item.is-open .faq-content-wrapper {
            grid-template-rows: 1fr;
            padding-bottom: 20px;
            opacity: 1;
        }
        .faq-answer { overflow: hidden; color: #555; font-size: 16px; line-height: 1.6; margin: 0; }


        /* --- STILI BOX CONTATTI, VISITATORI E INFO UTILI (Stile unificato) --- */
        .contact-section {
            background-color: #ffffff;
            padding: 40px 30px;
            max-width: 400px;
            text-align: center;
            border-radius: 12px; 
            box-shadow: 0 4px 20px rgba(0, 0, 0, 0.1);
            border: 1px solid #ddd;
            flex: 1 1 300px; 
        }
        
        /* Stili interni condivisi */
        .cs-icon-box {
            background-color: #e0f2fe; 
            border-radius: 50%;
            width: 80px;
            height: 80px;
            margin: 0 auto 20px auto;
            display: flex;
            justify-content: center;
            align-items: center;
        }

        .cs-title {
            color: #008000; 
            font-size: 24px;
            font-weight: 700;
            margin: 0 0 10px 0;
        }

        .cs-subtitle {
            color: #555555;
            font-size: 16px;
            margin: 0 0 30px 0;
        }

        .cs-phone-number {
            color: #008000;
            font-size: 28px;
            font-weight: 900;
            margin: 0 0 15px 0;
            text-decoration: none;
            display: block;
        }

        .cs-email-address {
            color: #008000;
            font-size: 18px;
            font-weight: 600;
            margin: 0 0 40px 0;
            text-decoration: none;
            display: block;
        }

        .cs-button {
            background-color: #f0f0f0;
            color: #444444;
            padding: 12px 25px;
            border-radius: 6px;
            text-decoration: none;
            font-weight: 600;
            font-size: 14px;
            display: inline-block;
            transition: background-color 0.3s;
        }
        
        .hammer-circle {
            background-color: #e8f5e9;
            border-radius: 50%;
            width: 80px; 
            height: 80px;
            display: flex;
            justify-content: center;
            align-items: center;
            margin: 0 auto 20px auto;
        }

        .hammer-emoji {
            font-size: 40px; 
            color: #008000;
        }
        
        .info-text {
            margin: 0;
            text-align: center; 
            color: #333;
            font-size: 16px;
        }


    </style>
</head>
<body id="top">

    <div class="top-bar">
        <a href="mailto:deaservice@gmail.com" class="bar-item">
            <span class="icon-green">✉</span>deaservice@gmail.com
        </a>
        <a href="#top" class="bar-item">
            <span class="icon-green">🏠</span>Home
        </a>
        <a href="tel:+390000000000" class="bar-item">
            <span class="icon-green">📞</span>+39 --- --- ----
        </a>
    </div>

    <div class="main-container">
        
        <!-- Box Titolo Standard -->
        <div class="title-box">
            <h1>Dea Service</h1>
        </div>
        
        <p class="descrizione">
            <b>DeaService</b> è il tuo hub multiservizi digitale. Dalla consulenza tecnica alle soluzioni creative, 
            offriamo assistenza a 360° per ogni tua esigenza. Velocità, precisione e disponibilità 24/7 
            al servizio dei tuoi progetti.
        </p>

        <details class="faq-item">
            <summary class="faq-question">Quanto costano i servizi di un tuttofare?</summary>
            <div class="faq-content-wrapper">
                <div class="faq-answer">
                    I costi dei servizi di un tuttofare partono da <b>Momentaneo</b>. Ogni progetto viene valutato singolarmente.
                </div>
            </div>
        </details>

        <details class="faq-item">
            <summary class="faq-question">Quali sono i tempi di risposta?</summary>
            <div class="faq-content-wrapper">
                <div class="faq-answer">
                    Garantiamo una risposta entro <b>30 minuti</b> durante l'orario operativo.
                </div>
            </div>
        </details>

        <!-- Punto di inserimento per gli script JS 
        <div id="script-target"></div>
        

    </div>

    <script>

        document.querySelectorAll('.faq-item').forEach((el) => {
            const summary = el.querySelector('summary');
            summary.addEventListener('click', (e) => {
                e.preventDefault();
                if (el.open) {
                    el.classList.remove('is-open');
                    setTimeout(() => { el.open = false; }, 400);
                } else {
                    el.open = true;
                    requestAnimationFrame(() => { el.classList.add('is-open'); });
                }
            });
        });



        const KEY = 'deaservice_visitors';
        let visitors = localStorage.getItem(KEY);
        visitors = visitors ? parseInt(visitors) + 1 : 1;
        localStorage.setItem(KEY, visitors);

        const contactBoxHTML = `
            <div class="contact-section">
                <div class="cs-icon-box">
                     <svg xmlns="http://www.w3.org" width="40" height="40" viewBox="0 0 24 24" fill="none" stroke="#008000" stroke-width="2" stroke-linecap="round" stroke-linejoin="round">
                        <path d="M11 11h2v2h-2z"></path><path d="M11 14h2v2h-2z"></path><path d="M8 11h2v2h-2z"></path><path d="M8 14h2v2h-2z"></path><path d="M14 11h2v2h-2z"></path><path d="M14 14h2v2h-2z"></path><path d="M11 8h2v2h-2z"></path><path d="M8 8h2v2h-2z"></path><path d="M14 8h2v2h-2z"></path><path d="M16 2h4l2 4v14a2 2 0 0 1-2 2H4a2 2 0 0 1-2-2V6l2-4h4"></path>
                    </svg>
                </div>
                <h2 class="cs-title">Contatti</h2>
                <p class="cs-subtitle">Chiamaci o scrivici subito</p>
                <a href="tel:0119654400" class="cs-phone-number">011 965 4400</a>
                <a href="mailto:" class="cs-email-address"></a>
                <a href="#" class="cs-button">Tutti i contatti</a>
            </div>
        `;
        
        const visitorBoxHTML = `
            <div class="contact-section">
                <div class="hammer-circle">
                    <span class="hammer-emoji">👤</span>
                </div>
                <h2 class="cs-title">Visitatori</h2>
                <p class="cs-subtitle">Utenti che hanno visitato il sito</p>
                <div class="cs-phone-number">${visitors}</div>
            </div>
        `;


        const infoText = `Per <b>informazioni utili</b> sui nostri <b>servizi</b>, <b>modalità di intervento</b>, <b>tempi di risposta</b> e <b>preventivi personalizzati</b>, ti invitiamo a <b>contattarci</b> in qualsiasi momento: siamo sempre disponibili per valutare ogni esigenza e trovare la soluzione più adatta a te.`;

        const infoBoxHTML = `
             <div class="contact-section">
                <div class="hammer-circle">
                    <span class="hammer-emoji">🔨</span>
                </div>
                <h2 class="cs-title">INFORMAZIONI UTILI</h2>
                <p class="info-text">${infoText}</p>
            </div>
        `;



        const dualBoxWrapper = document.createElement('div');
        dualBoxWrapper.style.display = 'flex';
        dualBoxWrapper.style.gap = '40px';
        dualBoxWrapper.style.flexWrap = 'wrap';
        dualBoxWrapper.style.justifyContent = 'center';
        dualBoxWrapper.style.marginTop = '100px';
        dualBoxWrapper.style.marginBottom = '50px'; 



        dualBoxWrapper.innerHTML = contactBoxHTML + visitorBoxHTML + infoBoxHTML;
        

        document.getElementById('script-target').parentNode.insertBefore(dualBoxWrapper, document.getElementById('script-target'));

    </script>

</body>
</html>
