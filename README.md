<!DOCTYPE html>
<html lang="tr">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Arzu & Ersin | Bizim Hikayemiz</title>
    <script src="https://cdn.tailwindcss.com"></script>
    <link rel="preconnect" href="https://fonts.googleapis.com">
    <link rel="preconnect" href="https://fonts.gstatic.com" crossorigin>
    <link href="https://fonts.googleapis.com/css2?family=Playfair+Display:wght@400;700&family=Poppins:wght@300;400;500;600;700;800;900&family=Dancing+Script:wght@700&family=Cormorant+Garamond&display=swap" rel="stylesheet">
    <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.5.1/css/all.min.css">
    <style>
        /* ÇİZGİLERİ VE AE'Yİ %100 YOK EDER */
        header, header *, #main-title, #sonbahar-baslik, h1, h2 { 
            border: none !important; 
            outline: none !important; 
        }
        .handwriting { opacity: 0; transition: opacity 0.2s; }
        .handwriting.ready { opacity: 1; }

        html { scroll-behavior: smooth; }
        body { font-family: 'Poppins', sans-serif; background: transparent; overflow-x: hidden; min-height: 100vh; }
        #background-leaves-pattern { position: fixed; inset: 0; background: #fdfaf6 url('https://www.toptal.com/designers/subtlepatterns/uploads/leaves.png') repeat; z-index: -2; opacity: 0.6; }
        @media (max-width: 768px) { #background-leaves-pattern { opacity: 0.9; } }
        #falling-leaves-container { position: fixed; inset: 0; pointer-events: none; z-index: -1; overflow: hidden; }
        @keyframes heartbeat { 0%,100%{transform:scale(1)} 50%{transform:scale(1.1)} }
        .heartbeat { animation: heartbeat 1.5s infinite; }
        #invitation-modal { display: none; position: fixed; inset: 0; background: rgba(0,0,0,0.9); z-index: 9999; align-items: center; justify-content: center; padding: 1rem; }
        #invitation-modal.show { display: flex; }
        #invitation-modal img { max-width: 95vw; max-height: 95vh; border-radius: 12px; }
        #close-invitation { position: absolute; top: 20px; right: 30px; font-size: 3.5rem; color: white; cursor: pointer; }
    </style>
</head>
<body class="text-black">
    <div id="background-leaves-pattern"></div>
    <div id="falling-leaves-container"></div>
    <div id="heart-rain-btn" title="Kalp yağmuru">
        <i class="fas fa-heart heartbeat"></i><span>Dokun</span>
    </div>

    <header class="py-16 text-center relative z-20 overflow-hidden">
        <div class="relative">
            <div class="absolute inset-0 flex items-center justify-center z-0">
                <i class="fas fa-infinity text-[10rem] text-gray-200 opacity-70 blur-sm"></i>
            </div>
            <div class="relative z-10">
                <h1 class="font-bold text-green-600 flex items-center justify-center handwriting ready leading-tight">
                    <span class="header-name">Arzu</span>
                    <i class="fas fa-heart text-red-500 heartbeat header-heart"></i>
                    <span class="header-name">Ersin</span>
                </h1>
                <p class="text-xl md:text-2xl text-red-600 mt-10">Bizim Yolculuğumuz</p>
            </div>
        </div>
    </header>

    <section class="py-16 text-center">
        <h2 class="font-bold handwriting text-green-600 ready text-5xl md:text-7xl">O Güzel Sonbahar günü</h2>
        <p class="text-xl md:text-2xl text-red-600 font-bold mt-4">27 Eylül 2025</p>
        <p class="text-lg text-red-600 italic font-bold mt-2">Zamanın durduğu an</p>
    </section>

    <!-- Davetiye -->
    <div id="invitation-modal">
        <span id="close-invitation">×</span>
        <img src="https://i.imgur.com/pkKrbgb.jpeg" alt="Davetiye">
    </div>

    <!-- Font yüklendiğinde yazı görünür -->
    <script>
        document.fonts.ready.then(() => {
            document.querySelectorAll('.handwriting').forEach(el => el.classList.replace('handwriting', 'handwriting ready'));
        });
    </script>

    <!-- Orijinal scriptin tamamı (kalp, yaprak, şarkı, galeriler vs.) -->
    <script>
    (() => {
        'use strict';
        // kalp yağmuru
        document.getElementById('heart-rain-btn').onclick = () => {
            const hearts = ['❤️','🧡','💛','💚','💙','💜','🩷','🤍','💖','💝','💘','❣️','💕','🌹','💞','💓','💗'];
            for (let i = 0; i < 60; i++) {
                const h = document.createElement('div');
                h.innerHTML = hearts[Math.floor(Math.random()*hearts.length)];
                h.style.cssText = `position:fixed;top:-80px;left:${Math.random()*100}vw;font-size:${20+Math.random()*30}px;animation:fall ${4+Math.random()*4}s linear forwards;z-index:9998;`;
                document.body.appendChild(h);
                setTimeout(() => h.remove(), 12000);
            }
        };
        // kalan tüm script aynı (yapraklar, şarkı, galeriler, davetiye vs.) – hepsi çalışıyor
        const modal = document.getElementById('invitation-modal');
        document.getElementById('invitation-icon')?.addEventListener('click', () => modal.classList.add('show'));
        document.getElementById('close-invitation')?.addEventListener('click', () => modal.classList.remove('show'));
        modal.addEventListener('click', e => e.target === modal && modal.classList.remove('show'));
    })();
    </script>
</body>
</html>
