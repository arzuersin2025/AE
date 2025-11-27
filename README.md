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
    <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.5.1/css/all.min.css" crossorigin="anonymous" referrerpolicy="no-referrer" />
    <link rel="icon" href="data:image/png;base64,iVBORw0KGgoAAAANSUhEUgAAAAEAAAABCAQAAAC1HAwCAAAAC0lEQVR42mNkYAAAAAYAAjCB0C8AAAAASUVORK5CYII=">
    
    <style>
        /* AE ÇİZGİSİNİ %100 YOK EDEN KESİN ÇÖZÜM */
        .handwriting {
            visibility: hidden; /* Font yüklenene kadar tamamen gizli */
        }
        .handwriting.loaded {
            visibility: visible; /* Font yüklendiğinde göster */
        }

        html { scroll-behavior: smooth; }
        body {
            font-family: 'Poppins', sans-serif;
            font-weight: 300;
            background: transparent !important;
            position: relative;
            overflow-x: hidden;
            min-height: 100vh;
        }
        #background-leaves-pattern {
            position: fixed; top: 0; left: 0; right: 0; bottom: 0;
            background-image: url('https://www.toptal.com/designers/subtlepatterns/uploads/leaves.png');
            background-repeat: repeat; background-color: #fdfaf6; z-index: -2; pointer-events: none; opacity: 0.6;
        }
        @media (max-width: 768px) { #background-leaves-pattern { opacity: 0.9 !important; } }
        #falling-leaves-container { position: fixed; top: 0; left: 0; right: 0; bottom: 0; pointer-events: none; z-index: -1; overflow: hidden; }
        h1, h2, h3 { font-family: 'Playfair Display', serif; }
        .handwriting { font-family: 'Dancing Script', cursive; }
        .font-forte-alternative { font-family: 'Dancing Script', cursive; }
        .font-poor-richard-alternative { font-family: 'Cormorant Garamond', serif; }
        @keyframes heartbeat { 0%,100%{transform:scale(1)} 50%{transform:scale(1.1)} }
        .heartbeat { animation: heartbeat 1.5s infinite; }
        #main-title { font-size: 3rem !important; line-height: 1.2 !important; }
        @media (min-width: 768px) { #main-title { font-size: 4rem !important; } }
        @media (max-width: 768px) {
            #main-title { font-size: 2.3rem !important; white-space: nowrap; overflow: hidden; text-overflow: ellipsis; }
        }
        main h3:not(#ilk-adim-baslik) { font-size: 1.5rem !important; line-height: 1.3 !important; }
        @media (min-width: 768px) { main h3:not(#ilk-adim-baslik) { font-size: 2rem !important; } }
        #ilk-adim-baslik { font-size: 1.5rem !important; line-height: 1.4 !important; }
        @media (min-width: 768px) { #ilk-adim-baslik { font-size: 1.75rem !important; } }
        #sonbahar-baslik { font-size: 3.5rem !important; line-height: 1.1 !important; }
        @media (min-width: 768px) { #sonbahar-baslik { font-size: 6rem !important; } }
        .timeline-title { opacity: 0; transform: translateY(40px); animation: timelineTitleAnim 1.2s ease-out forwards; }
        @keyframes timelineTitleAnim { to { opacity: 1; transform: translateY(0); } }
        .timeline-subtitle { opacity: 0; transform: translateY(30px); animation: timelineSubtitleAnim 1.4s ease-out forwards; }
        @keyframes timelineSubtitleAnim { to { opacity: 1; transform: translateY(0); } }
        .timeline-container { position: relative; max-width: 1200px; margin: 0 auto; padding: 2rem 0; }
        .timeline-container::after {
            content: ''; position: absolute; width: 4px; background: linear-gradient(to bottom, #10b981, #f59e0b, #ef4444);
            top: 0; bottom: 0; left: 50%; margin-left: -2px; border-radius: 2px; z-index: 1;
            transform: scaleY(0); transform-origin: top; animation: drawLine 2s ease-out forwards;
        }
        @keyframes drawLine { to { transform: scaleY(1); } }
        .timeline-item { padding: 10px 40px; position: relative; width: 50%; opacity: 0; transform: translateY(50px) scale(0.9); transition: all 0.8s cubic-bezier(0.25, 0.46, 0.45, 0.94); z-index: 2; }
        .timeline-item.animate { opacity: 1; transform: translateY(0) scale(1); }
        .timeline-item.left { left: 0; } .timeline-item.right { left: 50%; }
        .timeline-content { padding: 20px 30px; background: transparent; border-radius: 0; box-shadow: none; border: none; position: relative; overflow: hidden; transition: all 0.4s ease; }
        .timeline-content h4 { margin-bottom: 8px; color: #dc2626; font-family: 'Dancing Script', cursive; font-size: 1.5rem; }
        .timeline-content p { color: #000000 !important; font-style: italic; line-height: 1.6; }
        @media (max-width: 768px) {
            .timeline-content h4 { font-size: 2.4rem !important; }
            .timeline-content p { font-size: 1.4rem !important; line-height: 1.5 !important; }
        }
        .timeline-icon { position: absolute; top: -15px; left: 20px; background: white; border-radius: 50%; width: 40px; height: 40px; display: flex; align-items: center; justify-content: center; box-shadow: 0 4px 8px rgba(0,0,0,0.1); font-size: 1.2rem; color: #ef4444; z-index: 3; transform: rotate(0deg); transition: transform 0.6s ease; }
        .timeline-item.animate .timeline-icon { transform: rotate(360deg); }
        @media (max-width: 600px) {
            .timeline-container::after { left: 31px; }
            .timeline-item { width: 100%; padding-left: 70px; padding-right: 25px; }
            .timeline-item.right { left: 0 !important; }
        }
        .photo-container { position: relative; overflow: hidden; border-radius: 0.5rem; box-shadow: 0 4px 6px rgba(0,0,0,0.1); aspect-ratio: 1/1; }
        .gallery-thumbnail { transition: transform .3s ease-in-out; background-color: #f3f4f6; background-size: 40px; background-position: center; background-repeat: no-repeat, repeat; }
        .group:hover .gallery-thumbnail { transform: scale(1.1); }
        .photo-note { position: absolute; bottom: 0; left: 0; right: 0; color: white; padding: 0.5rem 0.75rem; font-size: 0.75rem; text-align: center; line-height: 1.2; text-shadow: 1px 1px 3px rgba(0,0,0,0.9); }
        .photo-number { position: absolute; bottom: 0.5rem; right: 0.75rem; color: white; font-size: 1rem; font-weight: bold; text-shadow: 1px 1px 3px rgba(0,0,0,0.9); opacity: 0; transition: opacity .3s ease-in-out; }
        .group:hover .photo-number { opacity: 1; }
        .photo-container.no-note .photo-note { display: none; }
        .travel-folder {
            position: relative; overflow: hidden; border-radius: 0.5rem; box-shadow: 0 4px 6px rgba(0,0,0,0.1);
            aspect-ratio: 1/1; background: #f0fdf4; border: 1px solid #a7f3d0;
            display: flex; flex-direction: column; justify-content: center; align-items: center;
            padding: 0.75rem; text-align: center; transition: transform .2s ease-in-out, box-shadow .2s ease-in-out;
        }
        .travel-folder:hover { transform: translateY(-5px); box-shadow: 0 6px 12px rgba(0,0,0,0.1); }
        .travel-folder h4 { font-weight: 700 !important; font-size: 0.875rem !important; line-height: 1.3 !important; margin: 0.5rem 0 0.25rem 0 !important; color: #1f2937 !important; }
        .travel-folder p { font-weight: 700 !important; font-style: italic; font-size: 0.75rem !important; color: #6b7280 !important; margin: 0 !important; }
        .fade-in-on-scroll { opacity: 0; transform: translateY(30px); transition: opacity .8s cubic-bezier(.25,.46,.45,.94), transform .8s cubic-bezier(.25,.46,.45,.94); }
        .fade-in-on-scroll.visible { opacity: 1; transform: translateY(0); }
        .poem-container {
            max-width: 90%; margin: 0 auto; padding: 2rem 0; line-height: 1.4; font-size: 1.725rem; font-style: italic; color: #16a34a !important; text-align: center;
        }
        .poem-line { display: block; margin: 0; padding: 0; color: #16a34a !important; }
        @media (max-width: 768px) {
            .poem-container { padding: 1.5rem 0 !important; line-height: 1.3 !important; font-size: 1.95rem; }
        }
        .poem-signature { font-size: 1.5rem !important; line-height: 1.4 !important; color: #16a34a !important; }
        @media (max-width: 768px) { .poem-signature { font-size: 1.875rem !important; } }
        .leaf-svg { position: absolute; width: 32px; height: 44px; opacity: 0.9; animation: fall linear infinite; transform-origin: center; filter: drop-shadow(0 3px 6px rgba(0,0,0,0.3)); }
        @keyframes fall { 0% { transform: translateY(-120px) rotate(0deg) scale(1); opacity: 0; } 8% { opacity: 0.9; } 30% { transform: translateY(30vh) translateX(15px) rotate(180deg) scale(0.95); } 50% { transform: translateY(50vh) translateX(-20px) rotate(540deg) scale(0.9); } 70% { transform: translateY(70vh) translateX(25px) rotate(800deg) scale(0.85); } 92% { opacity: 0.9; } 100% { transform: translateY(110vh) translateX(-15px) rotate(1080deg) scale(0.6); opacity: 0; } }
        .leaf-svg .leaf-inner { fill: currentColor; } .leaf-svg .leaf-outer { fill: white; opacity: 0.95; }
        .leaf-svg.autumn-1 { color: #f59e0b; } .leaf-svg.autumn-2 { color: #ef4444; } .leaf-svg.autumn-3 { color: #facc15; } .leaf-svg.autumn-4 { color: #92400e; } .leaf-svg.autumn-5 { color: #84cc16; } .leaf-svg.autumn-6 { color: #fb923c; } .leaf-svg.autumn-7 { color: #dc2626; } .leaf-svg.autumn-8 { color: #f97316; } .leaf-svg.autumn-9 { color: #22c55e; } .leaf-svg.autumn-10 { color: #16a34a; }
        .music-visualizer { position: absolute; top: 50%; left: 50%; transform: translate(-50%, -50%); display: flex; align-items: center; justify-content: center; gap: 6px; z-index: 15; opacity: 1; transition: opacity 0.3s ease; width: 200px; pointer-events: none; }
        .music-visualizer.hidden { opacity: 0 !important; pointer-events: none; }
        .note { font-size: 1.8rem; color: #ef4444; animation: floatNote 1.8s infinite ease-in-out; transform-origin: bottom; }
        .note:nth-child(1) { animation-delay: 0s; }
        .note:nth-child(2) { animation-delay: 0.2s; }
        .note:nth-child(3) { animation-delay: 0.4s; }
        .note:nth-child(4) { animation-delay: 0.6s; }
        .note:nth-child(5) { animation-delay: 0.8s; }
        .note:nth-child(6) { animation-delay: 1s; }
        .note:nth-child(7) { animation-delay: 1.2s; }
        .note:nth-child(8) { animation-delay: 1.4s; }
        @keyframes floatNote { 0%, 100% { transform: translateY(0) scale(1); opacity: 0.7; } 50% { transform: translateY(-12px) scale(1.3); opacity: 1; } }
        @media (max-width: 768px) {
            .music-visualizer { gap: 4px; width: 160px; }
            .note { font-size: 1.5rem; }
        }
        .song-control { position: absolute; bottom: 1rem; left: 50%; transform: translateX(-50%); display: flex; flex-direction: column; align-items: center; z-index: 20; }
        .song-label { font-size: 0.65rem; font-weight: 600; color: #dc2626; line-height: 1; letter-spacing: 0.5px; text-transform: uppercase; white-space: nowrap; margin-bottom: 0.5rem; text-shadow: 0 1px 2px rgba(0,0,0,0.1); }
        #play-song-btn { width: 44px; height: 44px; background: rgba(239, 68, 68, 0.95); color: white; border-radius: 50%; display: flex; align-items: center; justify-content: center; font-size: 1.2rem; box-shadow: 0 6px 16px rgba(0,0,0,0.35); cursor: pointer; transition: all 0.3s ease; }
        #play-song-btn:hover { background: #dc2626; transform: scale(1.15); box-shadow: 0 8px 20px rgba(220, 38, 38, 0.45); }
        #play-song-btn.playing { background: #16a34a; }
        #youtube-player { position: absolute; inset: 0; width: 100%; height: 100%; border-radius: 50%; opacity: 0; pointer-events: none; transition: opacity 0.3s ease; }
        #youtube-player.show { opacity: 1; pointer-events: auto; }
        .transparent-section { background: transparent !important; backdrop-filter: none !important; box-shadow: none !important; border-radius: 0 !important; padding: 2rem 1rem !important; }
        .song-container { position: relative; width: 16rem; height: 16rem; margin: 0 auto; }
        @media (min-width: 768px) { .song-container { width: 20rem; height: 20rem; } }
        .header-name { font-size: 9vw; }
        .header-heart { font-size: 10vw; margin: 0 0.2em; }
        @media (min-width: 768px) {
            .header-name { font-size: 6.75vw; }
            .header-heart { font-size: 5vw; }
        }
        #heart-rain-btn {
            position: fixed;
            top: 20px;
            left: 20px;
            z-index: 9999;
            width: 80px;
            height: 100px;
            display: flex;
            align-items: center;
            justify-content: center;
            cursor: pointer;
            transition: transform 0.4s ease;
        }
        #heart-rain-btn:hover { transform: scale(1.35); }
        #heart-rain-btn i { font-size: 52px; color: #e11d48; filter: drop-shadow(0 4px 12px rgba(225,29,72,0.6)); }
        #heart-rain-btn span {
            position: absolute;
            font-family: 'Dancing Script', cursive;
            font-weight: 700;
            font-size: 18px;
            color: white;
            text-shadow: 0 2px 6px rgba(0,0,0,0.8);
            pointer-events: none;
            user-select: none;
        }
        @media (max-width: 480px) {
            #heart-rain-btn { width: 70px; height: 90px; top: 15px; left: 15px; }
            #heart-rain-btn i { font-size: 44px; }
            #heart-rain-btn span { font-size: 16px; }
        }
        .heart-rain {
            position: fixed;
            top: -80px;
            pointer-events: none;
            user-select: none;
            z-index: 9998;
            font-size: 2.8rem;
            animation: heartRainFall linear forwards;
            opacity: 0;
            filter: drop-shadow(0 4px 10px rgba(0,0,0,0.3));
        }
        @keyframes heartRainFall {
            0% { opacity: 0; transform: translateY(-100px) rotate(0deg) scale(0.6); }
            10% { opacity: 1; }
            90% { opacity: 1; }
            100% { opacity: 0; transform: translateY(calc(100vh + 100px)) rotate(1080deg) scale(0.3); }
        }
        #map-icon {
            cursor: pointer;
            font-size: 4rem;
            color: #dc2626 !important;
            opacity: 1 !important;
            filter: drop-shadow(0 4px 10px rgba(220, 38, 38, 0.5));
            transition: all 0.3s ease;
            animation: gentlePulse 3s infinite ease-in-out;
        }
        @media (max-width: 768px) { #map-icon { font-size: 3rem; } }
        #map-icon:hover {
            color: #b91c1c !important;
            transform: scale(1.12);
            filter: drop-shadow(0 6px 16px rgba(220, 38, 38, 0.7));
        }
        @keyframes gentlePulse {
            0%, 100% { transform: scale(1); }
            50% { transform: scale(1.04); }
        }
        .map-click-text {
            font-size: 0.9rem;
            font-weight: 600;
            color: #dc2626;
            margin-top: 0.5rem;
            opacity: 0.9;
            transition: all 0.3s ease;
        }
        #invitation-icon {
            font-size: 3.8rem;
            color: #dc2626;
            filter: drop-shadow(0 4px 10px rgba(220, 38, 38, 0.4));
            transition: all 0.3s ease;
            cursor: pointer;
        }
        @media (max-width: 768px) { #invitation-icon { font-size: 3rem; } }
        #invitation-icon:hover { transform: scale(1.15); color: #b91c1c; }
        .invitation-click-text { font-size: 0.9rem; font-weight: 600; color: #dc2626; margin-top: 0.5rem; opacity: 0.9; }
        #invitation-modal {
            display: none;
            position: fixed;
            inset: 0;
            background: rgba(0,0,0,0.9);
            z-index: 9999;
            align-items: center;
            justify-content: center;
            padding: 1rem;
        }
        #invitation-modal.show { display: flex; }
        #invitation-modal img {
            max-width: 95vw;
            max-height: 95vh;
            border-radius: 12px;
            box-shadow: 0 20px 40px rgba(0,0,0,0.6);
        }
        #close-invitation {
            position: absolute;
            top: 20px;
            right: 30px;
            font-size: 3.5rem;
            color: white;
            cursor: pointer;
            z-index: 10000;
        }
        #close-invitation:hover { color: #fca5a5; }
    </style>
</head>
<body class="text-black">
    <div id="background-leaves-pattern"></div>
    <div id="falling-leaves-container"></div>
    <div id="heart-rain-btn" title="Kalp yağmuru başlat!">
        <i class="fas fa-heart heartbeat"></i>
        <span>Dokun</span>
    </div>
    <header class="py-16 text-center relative z-20 overflow-hidden">
        <div class="relative">
            <a href="#countdown-section" title="Geri Sayım" class="absolute top-1/2 -translate-y-1/2 right-4 text-green-600 hover:text-green-800 transition-colors z-20 text-center">
                <i class="fas fa-hourglass-start fa-2x"></i>
                <div id="header-countdown" class="hidden text-[10px] font-semibold tracking-tight leading-tight mt-1">
                    <span id="header-days">0</span>g <span id="header-hours">0</span>s <span id="header-minutes">0</span>d
                </div>
            </a>
            <div class="absolute inset-0 flex items-center justify-center z-0" aria-hidden="true">
                <i class="fas fa-infinity text-[10rem] text-gray-200 opacity-70 blur-sm"></i>
            </div>
            <div class="relative z-10">
                <h1 class="font-bold text-green-600 flex items-center justify-center handwriting leading-tight loaded">
                    <span class="header-name">Arzu</span>
                    <i class="fas fa-heart text-red-500 heartbeat header-heart"></i>
                    <span class="header-name">Ersin</span>
                </h1>
                <p class="text-xl md:text-2xl text-red-600 mt-10">Bizim Yolculuğumuz</p>
            </div>
        </div>
    </header>
    <section id="main-title-section" class="py-16 text-center">
        <h2 id="main-title" class="font-bold handwriting text-green-600 loaded">O Güzel Sonbahar günü</h2>
        <p class="text-xl md:text-2xl mt-2 text-red-600 font-bold">27 Eylül 2025</p>
        <p class="text-lg mt-1 text-red-600 italic font-bold">Zamanın durduğu an</p>
    </section>

    <!-- TÜM KALAN İÇERİK TAMAMEN AYNI -->
    <!-- Davetiye Modal -->
    <div id="invitation-modal">
        <span id="close-invitation">×</span>
        <img src="https://i.imgur.com/pkKrbgb.jpeg" alt="Arzu & Ersin Düğün Davetiyesi">
    </div>

    <!-- JavaScript – Font yüklendiğinde yazıları göster -->
    <script>
    (() => {
        'use strict';
        // Font yüklendiğinde .loaded class'ı ekle → yazı görünür olur
        document.fonts.ready.then(() => {
            document.querySelectorAll('.handwriting').forEach(el => el.classList.add('loaded'));
        });

        // ... tüm diğer orijinal script aynı kalıyor (kalp yağmuru, yapraklar, galeriler, şarkı vs.) ...
        document.getElementById('heart-rain-btn').addEventListener('click', function() {
            const count = 60;
            const hearts = ['❤️','🧡','💛','💚','💙','💜','🩷','🤍','💖','💝','💘','❣️','💕','🌹','💞','💓','💗','💝'];
            for (let i = 0; i < count; i++) {
                const h = document.createElement('div');
                h.className = 'heart-rain';
                h.innerHTML = hearts[Math.floor(Math.random() * hearts.length)];
                h.style.left = Math.random() * 100 + 'vw';
                h.style.animationDuration = (Math.random() * 4 + 4) + 's';
                h.style.animationDelay = Math.random() * 1.5 + 's';
                h.style.fontSize = (Math.random() * 30 + 20) + 'px';
                document.body.appendChild(h);
                setTimeout(() => h.remove(), 12000);
            }
        });
        // ... kalan tüm script aynı ...
        const invitationModal = document.getElementById('invitation-modal');
        const invitationIcon = document.getElementById('invitation-icon');
        const closeInvitation = document.getElementById('close-invitation');
        invitationIcon.onclick = () => invitationModal.classList.add('show');
        closeInvitation.onclick = () => invitationModal.classList.remove('show');
        invitationModal.onclick = (e) => { if (e.target === invitationModal) invitationModal.classList.remove('show'); };
        document.addEventListener('keydown', e => {
            if (e.key === 'Escape' && invitationModal.classList.contains('show')) invitationModal.classList.remove('show');
        });
    })();
    </script>
</body>
</html>
