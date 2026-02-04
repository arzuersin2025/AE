<html lang="tr">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0, maximum-scale=1.0, user-scalable=no">
    <title>Arzu & Ersin | Bizim Hikayemiz</title>
    <script src="https://cdn.tailwindcss.com"></script>
    <link rel="preconnect" href="https://fonts.googleapis.com">
    <link rel="preconnect" href="https://fonts.gstatic.com" crossorigin>
    <link href="https://fonts.googleapis.com/css2?family=Playfair+Display:wght@400;700&family=Poppins:wght@300;400;500;600;700;800;900&family=Dancing+Script:wght@700&family=Cormorant+Garamond&display=swap" rel="stylesheet">
    <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.5.1/css/all.min.css" crossorigin="anonymous" referrerpolicy="no-referrer" />
    <link rel="icon" href="data:image/png;base64,iVBORw0KGgoAAAANSUhEUgAAAAEAAAABCAQAAAC1HAwCAAAAC0lEQVR42mNkYAAAAAYAAjCB0C8AAAAASUVORK5CYII=">
    <script src="https://cdn.jsdelivr.net/npm/canvas-confetti@1.9.3/dist/confetti.browser.min.js" defer></script>
    <style>
        body, p, h1, h2, h3, span, div, section, .poem-container, .poem-line,
        .header-name, .handwriting {
            caret-color: transparent !important;
        }
        /* Yeni Kaydırma Kilidi - Düzeni bozmaz, zıplamayı önler */
        .no-scroll {
            overflow: hidden !important;
            touch-action: none;
            -ms-touch-action: none;
        }
        
        a, button, [role="button"], .cursor-pointer,
        #play-song-btn, #toggle-gallery-btn, #toggle-video-gallery-btn,
        #map-icon, #invitation-icon,
        #close-invitation, #close-modal, #prev-photo, #next-photo {
            caret-color: auto !important;
            cursor: pointer !important;
        }
        header, header *, #main-title, #sonbahar-baslik, h1, h2 {
            border: none !important;
            outline: none !important;
            box-shadow: none !important;
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
        #falling-hearts-container { position: fixed; top: 0; left: 0; right: 0; bottom: 0; pointer-events: none; z-index: -1; overflow: hidden; }
        #falling-flowers-container { position: fixed; top: 0; left: 0; right: 0; bottom: 0; pointer-events: none; z-index: -1; overflow: hidden; }
        h1, h2, h3 { font-family: 'Playfair Display', serif; }
        .handwriting { font-family: 'Dancing Script', cursive; }
        .font-forte-alternative { font-family: 'Dancing Script', cursive; }
        .font-poor-richard-alternative { font-family: 'Cormorant Garamond', serif; }
        @keyframes heartbeat { 0%,100%{transform:scale(1)} 50%{transform:scale(1.15)} }
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
        .falling-heart {
            position: absolute;
            font-size: 2rem;
            pointer-events: none;
            animation: heartFall linear infinite;
            filter: drop-shadow(0 4px 10px rgba(0,0,0,0.3));
        }
        @keyframes heartFall {
            0% { opacity: 0; transform: translateY(-150px) rotate(0deg) scale(0.8); }
            5% { opacity: 1; }
            95% { opacity: 1; }
            100% { opacity: 0; transform: translateY(calc(100vh + 150px)) rotate(1080deg) scale(0.4); }
        }
        .falling-flower {
            position: absolute;
            font-size: 2.2rem;
            pointer-events: none;
            animation: flowerFall linear infinite;
            filter: drop-shadow(0 4px 10px rgba(0,0,0,0.3));
        }
        @keyframes flowerFall {
            0% { opacity: 0; transform: translateY(-150px) rotate(0deg) scale(0.8); }
            10% { opacity: 1; }
            90% { opacity: 1; }
            100% { opacity: 0; transform: translateY(calc(100vh + 150px)) rotate(1440deg) scale(0.5); }
        }
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
        .header-name {
            font-size: 11.7vw;
            color: #16a34a !important;
        }
        @media (min-width: 768px) {
            .header-name { font-size: 6.75vw; }
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
        #map-icon:hover + .map-click-text {
            opacity: 1;
            transform: translateY(-2px);
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
        #invitation-icon:hover + .invitation-click-text { opacity: 1; }
        #invitation-modal {
            display: none;
            position: fixed;
            inset: 0;
            background: rgba(0,0,0,0.9);
            z-index: 9999;
            align-items: center;
            justify-content: center;
            padding: 1rem;
            touch-action: none;
        }
        #invitation-modal.show { display: flex; }
        #invitation-modal img {
            max-width: 95vw;
            max-height: 95vh;
            border-radius: 12px;
            box-shadow: 0 20px 40px rgba(0,0,0,0.6);
            transform-origin: center center;
            transition: transform 0.1s ease-out;
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
        header {
            padding-bottom: 1rem !important;
        }
        .fade-in-on-scroll { opacity: 0; transform: translateY(30px); transition: opacity .8s cubic-bezier(.25,.46,.45,.94), transform .8s cubic-bezier(.25,.46,.45,.94); }
        .fade-in-on-scroll.visible { opacity: 1; transform: translateY(0); }
        .photo-container { position: relative; overflow: hidden; border-radius: 0.5rem; box-shadow: 0 4px 6px rgba(0,0,0,0.1); aspect-ratio: 1/1; }
        .gallery-thumbnail { transition: transform .3s ease-in-out; }
        .group:hover .gallery-thumbnail { transform: scale(1.1); }
        .photo-note { position: absolute; bottom: 0; left: 0; right: 0; color: white; padding: 0.5rem 0.75rem; font-size: 0.75rem; text-align: center; line-height: 1.2; text-shadow: 1px 1px 3px rgba(0,0,0,0.9); }
        .photo-number { position: absolute; bottom: 0.5rem; right: 0.75rem; color: white; font-size: 1rem; font-weight: bold; text-shadow: 1px 1px 3px rgba(0,0,0,0.9); opacity: 0; transition: opacity .3s ease-in-out; }
        .group:hover .photo-number { opacity: 1; }
        .photo-container.no-note .photo-note { display: none; }
        #toggle-gallery-btn {
            background: rgba(220, 38, 38, 0.5);
            color: #000000 !important;
            border: 1px solid rgba(185, 28, 28, 0.4);
            transition: all 0.2s ease;
            backdrop-filter: blur(4px);
        }
        #toggle-gallery-btn:hover {
            background: rgba(185, 28, 28, 0.65);
            border-color: rgba(153, 27, 27, 0.5);
            transform: translateY(-1px);
        }
        #toggle-video-gallery-btn {
            background: rgba(220, 38, 38, 0.5);
            color: #000000 !important;
            border: 1px solid rgba(185, 28, 28, 0.4);
            transition: all 0.2s ease;
            backdrop-filter: blur(4px);
        }
        #toggle-video-gallery-btn:hover {
            background: rgba(185, 28, 28, 0.65);
            border-color: rgba(153, 27, 27, 0.5);
            transform: translateY(-1px);
        }
        #toggle-gallery-btn i,
        #toggle-video-gallery-btn i {
            color: #000000 !important;
        }
        /* Kalp kabı - Mobil kesilmeyi önlemek için optimize edildi */
        .interlocked-hearts {
            position: relative;
            display: inline-flex;
            align-items: center;
            justify-content: center;
            width: 22vw; 
            height: 22vw;
            margin: 0 0.5em;
            overflow: visible;
            flex-shrink: 0;
        }
        .heart-photo-svg {
            width: 100%;
            height: 100%;
            filter: drop-shadow(0 0 5px rgba(0,0,0,0.3));
            overflow: visible;
        }
        .heart-border {
            fill: #dc2626;
            stroke: black;
            stroke-width: 0.6;
        }
        @media (min-width: 768px) {
            .interlocked-hearts {
                width: 12vw;
                height: 12vw;
                margin: 0 1.2em;
            }
            .heart-border {
                stroke-width: 0.4;
            }
        }
        #countdown-placeholder p {
            color: #e91e63 !important;
        }
        #map-section p {
            color: #556b2f !important;
        }
        .invitation-description p {
            color: #2563eb !important;
        }
        .photo-gallery-description p {
            color: #6b8e23 !important;
        }
        .video-gallery-description p {
            color: #9333ea !important;
        }
        .thank-you-message p {
            color: #06b6d4 !important;
        }
        main {
            padding-bottom: 0 !important;
        }
        section:last-of-type {
            padding-bottom: 2rem !important;
            margin-bottom: 0 !important;
        }
        #footer-qr .gallery-thumbnail {
            transition: none !important;
        }
        #footer-qr:hover .gallery-thumbnail {
            transform: none !important;
        }
        #footer-section {
            display: flex;
            flex-direction: column;
            align-items: center;
            gap: 2rem;
            padding: 2rem 1rem;
            position: relative;
        }
        #qr-wrapper {
            display: flex;
            flex-direction: column;
            align-items: center;
        }
        #site-address {
            margin-top: 1rem;
            font-size: 1.125rem;
            font-weight: 500;
            color: #dc2626;
            text-align: center;
        }
        /* Modal Görsel Sabitleme */
        #image-modal {
            touch-action: none;
            overflow: hidden;
        }
        #modal-image {
            transition: transform 0.1s ease-out;
            will-change: transform;
        }
    </style>
</head>
<body class="text-black">
    <div id="background-leaves-pattern"></div>
    <div id="falling-leaves-container"></div>
    <div id="falling-hearts-container"></div>
    <div id="falling-flowers-container"></div>
    <header class="py-16 text-center relative z-20 overflow-hidden">
        <div class="relative">
            <div class="relative z-10">
                <h1 class="font-bold flex items-center justify-center handwriting leading-tight">
                    <span class="header-name">Arzu</span>
                    <span class="interlocked-hearts heartbeat">
                        <svg viewBox="-2 -2 36 33.6" class="heart-photo-svg"> 
                            <defs>
                                <clipPath id="heart-clip">
                                    <path d="M23.6,0c-3.4,0-6.3,2.7-7.6,5.6C14.7,2.7,11.8,0,8.4,0C3.8,0,0,3.8,0,8.4c0,9.4,9.5,11.9,16,21.2c6.1-9.3,16-12.1,16-21.2C32,3.8,28.2,0,23.6,0z"/>
                                </clipPath>
                            </defs>
                            <path class="heart-border" d="M23.6,0c-3.4,0-6.3,2.7-7.6,5.6C14.7,2.7,11.8,0,8.4,0C3.8,0,0,3.8,0,8.4c0,9.4,9.5,11.9,16,21.2c6.1-9.3,16-12.1,16-21.2C32,3.8,28.2,0,23.6,0z"/>
                            <image href="https://i.imgur.com/kZSonbm.jpg" x="0" y="0" width="32" height="32" clip-path="url(#heart-clip)" preserveAspectRatio="xMidYMid slice" />
                        </svg>
                    </span>
                    <span class="header-name">Ersin</span>
                </h1>
                <p class="text-xl md:text-2xl text-red-600 mt-10">Bizim Yolculuğumuz</p>
            </div>
        </div>
    </header>
    <section id="main-title-section" class="py-8 text-center">
        <h2 id="main-title" class="font-bold handwriting text-green-600">O Güzel Sonbahar günü</h2>
        <p class="text-xl md:text-2xl mt-2 text-red-600 font-bold">27 Eylül 2025</p>
    </section>
    <main class="container mx-auto px-6 pb-12 relative z-20">
        <section class="max-w-3xl mx-auto my-12 text-center">
            <h3 id="ilk-adim-baslik" class="font-bold text-red-600 mb-4">İlk Adım</h3>
            <p class="text-lg leading-relaxed font-medium font-[550] text-black">
                Her büyük hikayenin bir başlangıç anı vardır. Bizimki, 27 Eylül 2025'te, yaprakların sarıya döndüğü,
                havanın tatlı bir serinliğe büründüğü o güzel sonbahar gününde başladı. Gözlerimiz kesiştiğinde,
                sanki zaman durdu. Kalbim ilk kez o kadar hızlı attı ki, sesini duyabiliyordum.
                O an, "Bu kişi hayatımın geri kalanını değiştirecek" dedim içimden.
            </p>
            <p class="text-lg leading-relaxed font-medium font-[550] text-black mt-4">
                İlk konuşmamız, ilk gülüşün, ilk dokunuşun... Her biri birer inci gibi dizildi hafızamıza.
                O gün, sadece iki kişi tanışmadı; iki ruh, birbirini buldu.
                Ve o andan itibaren, her adımımız birlikte atılmak üzereydi.
            </p>
            <div class="text-4xl text-red-500 mt-8 heartbeat"><i class="fas fa-heart"></i></div>
        </section>
        <section class="my-16 max-w-3xl mx-auto text-center">
            <h3 id="sonbahar-baslik" class="font-bold text-center text-red-600 mb-6 handwriting font-forte-alternative">Sonbahar şiiri</h3>
            <div class="poem-container">
                <div class="poem-line italic">Çiçekli badem ağaçlarını unut.</div>
                <div class="poem-line italic">değmez,</div>
                <div class="poem-line italic">bu bahiste</div>
                <div class="poem-line italic">geri gelmesi mümkün olmayan hatırlanmamalı.</div>
                <div class="poem-line italic">ıslak saçlarını güneşte kurut</div>
                <div class="poem-line italic">olgun meyvelerin baygınlığıyla parıldasın</div>
                <div class="poem-line italic">nemli, ağır kızıltılar…</div>
                <div class="poem-line italic">sevgilim, sevgilim,</div>
                <div class="poem-line italic">mevsim</div>
                <div class="poem-line italic">sonbahar…</div>
            </div>
            <p class="text-right text-green-600 font-semibold-bold mt-6 pr-4 font-forte-alternative poem-signature">- Nazım Hikmet</p>
        </section>
        <section class="my-16 max-w-3xl mx-auto text-center">
            <h3 class="font-bold text-red-600 mb-6 handwriting">Aramızda Geçen İki Güzel Söz</h3>
            <div class="max-w-2xl mx-auto space-y-6">
                <div>
                    <p class="text-xl md:text-2xl leading-relaxed italic text-blue-600 font-medium">
                        " Bana iyi hissettiriyorsun sen bu zamana kadar nerelerdeydin "
                    </p>
                </div>
                <div class="text-center text-4xl text-red-500 heartbeat mb-4"><i class="fas fa-heart"></i></div>
                <div>
                    <p class="text-xl md:text-2xl leading-relaxed italic text-blue-600 font-medium">
                        " Asıl sen neredeydin meğersem çok yakınmışız "
                    </p>
                </div>
            </div>
        </section>
        <section id="countdown-section" class="my-16 max-w-3xl mx-auto transparent-section text-center">
            <h3 class="font-bold text-red-600 mb-6 font-forte-alternative">Büyük Güne Geri Sayım</h3>
            <div id="countdown-placeholder" class="my-4">
                <div class="text-8xl text-red-500 heartbeat"><i class="fas fa-infinity"></i></div>
                <p class="text-center font-semibold italic text-lg mt-4">
                    Sonsuzluğa giden yolculuğumuzun tarihi belli olduğunda...
                </p>
            </div>
        </section>
        <section id="map-section" class="my-16 max-w-3xl mx-auto transparent-section text-center">
            <h3 class="font-bold text-red-600 mb-6 handwriting">Düğün Mekanımız</h3>
            <div class="flex flex-col items-center mb-8">
                <a href="https://www.google.com/maps/search/?api=1&query=Üsküdar, İstanbul, Türkiye" target="_blank" id="map-icon" title="Haritayı Aç">
                    <i class="fas fa-map-marker-alt"></i>
                </a>
                <div class="map-click-text">Tıkla</div>
            </div>
            <p class="text-center font-semibold italic text-lg mt-6 leading-relaxed px-6 max-w-2xl mx-auto">
                Seninle sonsuzluğa adım attığımız yer 💙
            </p>
        </section>
        <section class="my-16 max-w-3xl mx-auto transparent-section text-center">
            <h3 class="font-bold text-red-600 mb-6 handwriting">Davetiyemiz</h3>
            <div class="flex flex-col items-center">
                <div id="invitation-icon" title="Davetiyeyi Gör">
                    <i class="fas fa-envelope-open-text heartbeat"></i>
                </div>
                <div class="invitation-click-text">Tıkla</div>
            </div>
            <div class="mt-6 max-w-2xl mx-auto invitation-description">
                <p class="text-center font-semibold italic text-lg leading-relaxed px-6">
                    Bu bir davetiye değil, size yazdığımız bir mutluluk mektubu 💚
                </p>
            </div>
        </section>
        <div id="invitation-modal">
            <span id="close-invitation">X</span>
            <img id="invitation-image" src="https://i.imgur.com/2nywEc1.jpeg" alt="Arzu & Ersin Düğün Davetiyesi">
        </div>
        <section class="my-16 max-w-3xl mx-auto transparent-section text-center relative overflow-hidden">
            <h3 class="font-bold text-center text-red-600 mb-6 handwriting">Bizim Şarkımız</h3>
            <p class="text-center text-black font-semibold italic mt-2 mb-6">Tarkan - Beni Çok Sev</p>
            <div class="song-container">
                <iframe id="youtube-player"
                        src="https://www.youtube.com/embed/IYnu4-69fTA?autoplay=0&rel=0&modestbranding=1&playsinline=1&enablejsapi=1"
                        title="Tarkan - Beni Çok Sev"
                        frameborder="0"
                        allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture"
                        allowfullscreen></iframe>
                <div id="music-visualizer" class="music-visualizer">
                    <div class="note">♪</div><div class="note">♪</div><div class="note">♪</div><div class="note">♪</div>
                    <div class="note">♪</div><div class="note">♪</div><div class="note">♪</div><div class="note">♪</div>
                </div>
                <div class="song-control">
                    <div class="song-label">Dinle</div>
                    <button id="play-song-btn" title="Şarkıyı Çal"><i class="fas fa-play"></i></button>
                </div>
            </div>
        </section>
        <section class="my-16 max-w-5xl mx-auto p-4 md:p-8 text-center">
            <h3 class="font-bold text-center text-red-600 mb-4 handwriting">Fotoğraf Galerimiz</h3>
            <div class="photo-gallery-description">
                <p class="text-center text-xl md:text-2xl leading-relaxed max-w-4xl mx-auto italic font-medium">
                    İşte yolculuğumuzda biriktirdiğimiz Anılar..
                </p>
            </div>
            <div class="mt-8 text-center">
                <button id="toggle-gallery-btn" class="inline-flex items-center justify-center py-2 px-6 shadow-sm text-sm font-medium rounded-md transition-colors">
                    <span id="gallery-toggle-text">Fotoğraf Galerisini Gör</span>
                    <i id="gallery-toggle-icon" class="fas fa-chevron-down ml-2 transition-transform"></i>
                </button>
            </div>
            <div id="gallery-wrapper" class="hidden mt-8">
                <div class="grid grid-cols-3 sm:grid-cols-4 md:grid-cols-5 lg:grid-cols-6 gap-1" id="gallery-grid">
                    <!-- Photo containers start -->
                    <div class="photo-container group cursor-pointer">
                        <img data-src="https://i.imgur.com/D0I0h6C.jpeg" alt="Katibim Cafe" class="gallery-thumbnail w-full h-full object-cover" loading="lazy">
                        <span class="photo-number opacity-0 group-hover:opacity-100">18</span>
                        <div class="photo-note">Katibim Cafe</div>
                    </div>
                    <div class="photo-container group cursor-pointer">
                        <img data-src="https://i.imgur.com/dy7O9vT.jpeg" alt="Katibim" class="gallery-thumbnail w-full h-full object-cover" loading="lazy">
                        <span class="photo-number opacity-0 group-hover:opacity-100">17</span>
                        <div class="photo-note">Katibim</div>
                    </div>
                    <div class="photo-container group cursor-pointer">
                        <img data-src="https://i.imgur.com/HiXIafs.jpeg" alt="Katibim" class="gallery-thumbnail w-full h-full object-cover" loading="lazy">
                        <span class="photo-number opacity-0 group-hover:opacity-100">16</span>
                        <div class="photo-note">Katibim</div>
                    </div>
                    <div class="photo-container group cursor-pointer">
                        <img data-src="https://i.imgur.com/QXWb1oI.jpg" alt="Bostancı" class="gallery-thumbnail w-full h-full object-cover" loading="lazy">
                        <span class="photo-number opacity-0 group-hover:opacity-100">14</span>
                        <div class="photo-note">Bostancı</div>
                    </div>
                    <div class="photo-container group cursor-pointer">
                        <img data-src="https://i.imgur.com/PTYXm1S.jpg" alt="Nakkaştepe" class="gallery-thumbnail w-full h-full object-cover" loading="lazy">
                        <span class="photo-number opacity-0 group-hover:opacity-100">13</span>
                        <div class="photo-note">Nakkaştepe</div>
                    </div>
                    <div class="photo-container group cursor-pointer">
                        <img data-src="https://i.imgur.com/Q6ZF31K.jpg" alt="Katibim" class="gallery-thumbnail w-full h-full object-cover" loading="lazy">
                        <span class="photo-number opacity-0 group-hover:opacity-100">12</span>
                        <div class="photo-note">Katibim</div>
                    </div>
                    <div class="photo-container group cursor-pointer">
                        <img data-src="https://i.imgur.com/3yhwIIm.jpg" alt="Üsküdar" class="gallery-thumbnail w-full h-full object-cover" loading="lazy">
                        <span class="photo-number opacity-0 group-hover:opacity-100">11</span>
                        <div class="photo-note">Üsküdar</div>
                    </div>
                    <div class="photo-container group cursor-pointer">
                        <img data-src="https://i.imgur.com/8Vu50Vx.jpg" alt="Üsküdar" class="gallery-thumbnail w-full h-full object-cover" loading="lazy">
                        <span class="photo-number opacity-0 group-hover:opacity-100">10</span>
                        <div class="photo-note">Üsküdar</div>
                    </div>
                    <div class="photo-container group cursor-pointer">
                        <img data-src="https://i.imgur.com/cDWfV6z.jpg" alt="Güldür Güldür" class="gallery-thumbnail w-full h-full object-cover" loading="lazy">
                        <span class="photo-number opacity-0 group-hover:opacity-100">9</span>
                        <div class="photo-note">Güldür Güldür</div>
                    </div>
                    <div class="photo-container group cursor-pointer">
                        <img data-src="https://i.imgur.com/jlmfKQ6.jpg" alt="Nev Mekan" class="gallery-thumbnail w-full h-full object-cover" loading="lazy">
                        <span class="photo-number opacity-0 group-hover:opacity-100">8</span>
                        <div class="photo-note">Nev Mekan</div>
                    </div>
                    <div class="photo-container group cursor-pointer">
                        <img data-src="https://i.imgur.com/EI3PjiL.jpg" alt="Nev Mekan" class="gallery-thumbnail w-full h-full object-cover" loading="lazy">
                        <span class="photo-number opacity-0 group-hover:opacity-100">7</span>
                        <div class="photo-note">Nev Mekan</div>
                    </div>
                    <div class="photo-container group cursor-pointer">
                        <img data-src="https://i.imgur.com/wf9Xhs9.jpg" alt="Lunapark Anısı" class="gallery-thumbnail w-full h-full object-cover" loading="lazy">
                        <span class="photo-number opacity-0 group-hover:opacity-100">6</span>
                        <div class="photo-note">Lunapark Anısı</div>
                    </div>
                    <div class="photo-container group cursor-pointer">
                        <img data-src="https://i.imgur.com/G26zsUc.jpg" alt="Beşiktaş" class="gallery-thumbnail w-full h-full object-cover" loading="lazy">
                        <span class="photo-number opacity-0 group-hover:opacity-100">5</span>
                        <div class="photo-note">Beşiktaş</div>
                    </div>
                    <div class="photo-container group cursor-pointer">
                        <img data-src="https://i.imgur.com/PR2hWYz.jpg" alt="Aksaray" class="gallery-thumbnail w-full h-full object-cover" loading="lazy">
                        <span class="photo-number opacity-0 group-hover:opacity-100">4</span>
                        <div class="photo-note">Aksaray</div>
                    </div>
                    <div class="photo-container group cursor-pointer">
                        <img data-src="https://i.imgur.com/40oguJF.jpg" alt="Çamlıca Kahvaltımız" class="gallery-thumbnail w-full h-full object-cover" loading="lazy">
                        <span class="photo-number opacity-0 group-hover:opacity-100">3</span>
                        <div class="photo-note">Çamlıca Kahvaltımız</div>
                    </div>
                    <div class="photo-container group cursor-pointer">
                        <img data-src="https://i.imgur.com/KZpZnaa.jpg" alt="Dünya Güzelim" class="gallery-thumbnail w-full h-full object-cover" loading="lazy">
                        <span class="photo-number opacity-0 group-hover:opacity-100">2</span>
                        <div class="photo-note">Dünya Güzelim</div>
                    </div>
                    <div class="photo-container no-note group cursor-pointer">
                        <img data-src="https://i.imgur.com/WnEibNN.jpg" alt="Aksaray" class="gallery-thumbnail w-full h-full object-cover" loading="lazy">
                        <span class="photo-number opacity-0 group-hover:opacity-100">1</span>
                    </div>
                </div>
            </div>
        </section>
        <section class="my-16 max-w-5xl mx-auto p-4 md:p-8 text-center">
            <h3 class="font-bold text-center text-red-600 mb-4 handwriting">Video Galerimiz</h3>
            <div class="video-gallery-description">
                <p class="text-center text-xl md:text-2xl leading-relaxed max-w-4xl mx-auto italic font-medium">
                    Bazı duyguları kelimelerle anlatmak yetmez...
                </p>
            </div>
            <div class="mt-8 text-center">
                <button id="toggle-video-gallery-btn" class="inline-flex items-center justify-center py-2 px-6 shadow-sm text-sm font-medium rounded-md transition-colors">
                    <span id="video-gallery-toggle-text">Video Galerisini Gör</span>
                    <i id="video-gallery-toggle-icon" class="fas fa-chevron-down ml-2 transition-transform"></i>
                </button>
            </div>
            <div id="video-gallery-wrapper" class="hidden mt-8">
                <div class="grid grid-cols-3 sm:grid-cols-4 md:grid-cols-5 lg:grid-cols-6 gap-1" id="video-grid">
                    <div class="photo-container group cursor-pointer aspect-square" data-youtube-id="wcZOC94zAYw">
                        <img data-src="https://img.youtube.com/vi/wcZOC94zAYw/maxresdefault.jpg" alt="Güldür Güldür" class="w-full h-full object-cover gallery-thumbnail" loading="lazy">
                        <div class="absolute inset-0 flex items-center justify-center bg-black bg-opacity-40">
                            <i class="far fa-play-circle text-white text-5xl opacity-80 group-hover:opacity-100 transition-opacity"></i>
                        </div>
                        <span class="photo-number opacity-0 group-hover:opacity-100">6</span>
                        <div class="photo-note">Güldür Güldür</div>
                    </div>
                    <div class="photo-container group cursor-pointer aspect-square" data-youtube-id="ChFa2GJ4e4U">
                        <img data-src="https://img.youtube.com/vi/ChFa2GJ4e4U/maxresdefault.jpg" alt="Beşiktaş" class="w-full h-full object-cover gallery-thumbnail" loading="lazy">
                        <div class="absolute inset-0 flex items-center justify-center bg-black bg-opacity-40">
                            <i class="far fa-play-circle text-white text-5xl opacity-80 group-hover:opacity-100 transition-opacity"></i>
                        </div>
                        <span class="photo-number opacity-0 group-hover:opacity-100">5</span>
                        <div class="photo-note">Beşiktaş</div>
                    </div>
                    <div class="photo-container group cursor-pointer aspect-square" data-youtube-id="aim5II5vYpU">
                        <img data-src="https://img.youtube.com/vi/aim5II5vYpU/maxresdefault.jpg" alt="Üsküdar" class="gallery-thumbnail w-full h-full object-cover" loading="lazy">
                        <div class="absolute inset-0 flex items-center justify-center bg-black bg-opacity-40">
                            <i class="far fa-play-circle text-white text-5xl opacity-80 group-hover:opacity-100 transition-opacity"></i>
                        </div>
                        <span class="photo-number opacity-0 group-hover:opacity-100">4</span>
                        <div class="photo-note">Üsküdar</div>
                    </div>
                    <div class="photo-container group cursor-pointer aspect-square" data-youtube-id="uY6ZrwkbLjc">
                        <img data-src="https://img.youtube.com/vi/uY6ZrwkbLjc/maxresdefault.jpg" alt="Lunapark" class="gallery-thumbnail w-full h-full object-cover" loading="lazy">
                        <div class="absolute inset-0 flex items-center justify-center bg-black bg-opacity-40">
                            <i class="far fa-play-circle text-white text-5xl opacity-80 group-hover:opacity-100 transition-opacity"></i>
                        </div>
                        <span class="photo-number opacity-0 group-hover:opacity-100">3</span>
                        <div class="photo-note">Lunapark</div>
                    </div>
                    <div class="photo-container group cursor-pointer aspect-square" data-youtube-id="19aKq8FtYP8">
                        <img data-src="https://img.youtube.com/vi/19aKq8FtYP8/maxresdefault.jpg" alt="Beşiktaş" class="w-full h-full object-cover gallery-thumbnail" loading="lazy">
                        <div class="absolute inset-0 flex items-center justify-center bg-black bg-opacity-40">
                            <i class="far fa-play-circle text-white text-5xl opacity-80 group-hover:opacity-100 transition-opacity"></i>
                        </div>
                        <span class="photo-number opacity-0 group-hover:opacity-100">2</span>
                        <div class="photo-note">Beşiktaş</div>
                    </div>
                    <div class="photo-container group cursor-pointer aspect-square" data-youtube-id="J466tfX1jzk">
                        <img data-src="https://img.youtube.com/vi/J466tfX1jzk/maxresdefault.jpg" alt="Ev" class="gallery-thumbnail w-full h-full object-cover" loading="lazy">
                        <div class="absolute inset-0 flex items-center justify-center bg-black bg-opacity-40">
                            <i class="far fa-play-circle text-white text-5xl opacity-80 group-hover:opacity-100 transition-opacity"></i>
                        </div>
                        <span class="photo-number opacity-0 group-hover:opacity-100">1</span>
                        <div class="photo-note">Ev</div>
                    </div>
                </div>
            </div>
        </section>
        <section class="my-16 max-w-3xl mx-auto transparent-section">
            <h3 class="font-bold text-center text-red-600 mb-6 handwriting">Teşekkür</h3>
            <div class="thank-you-message">
                <p class="text-center text-xl md:text-2xl leading-relaxed max-w-4xl mx-auto italic font-medium mt-4">
                    Bu mutlu yolculuğumuzda yanımızda olan herkese sonsuz teşekkür ederiz
                </p>
            </div>
            <div class="mt-16 text-center">
                <p class="text-red-600 italic text-xl md:text-2xl mb-6 font-medium">
                    İletişim adresimiz
                </p>
                <div class="flex justify-center">
                    <div class="inline-flex items-center gap-4 bg-white/90 px-6 py-4 rounded-full shadow-lg border-2 border-pink-200">
                        <div>
                            <i class="fas fa-envelope text-4xl text-red-600"></i>
                        </div>
                        <span class="font-bold text-green-700 text-base md:text-lg select-all">
                            arzuersin2025@gmail.com
                        </span>
                    </div>
                </div>
                <div class="mt-16 text-center">
                    <p class="text-black text-xl md:text-2xl leading-relaxed text-center max-w-4xl mx-auto italic font-medium">
                        “ Yaprakların dansında buluştuk,<br>
                        yıldızların ışığında sonsuza dek yürüyeceğiz Sevgilim ”
                    </p>
                    <p class="text-green-600 mt-6 flex items-center justify-center gap-5 handwriting text-5xl md:text-6xl font-bold">
                        Arzu <i class="fas fa-infinity text-red-600 heartbeat text-4xl md:text-5xl"></i> Ersin
                    </p>
                </div>
            </div>
        </section>
        <section id="footer-section" class="my-12 text-center">
            <div id="qr-wrapper">
                <div id="footer-qr" class="photo-container inline-block">
                    <img src="https://i.imgur.com/j4i19v0.jpeg"
                         alt="Arzu & Ersin QR Kod"
                         class="gallery-thumbnail w-full h-full object-cover rounded-lg shadow-lg"
                         loading="lazy"
                         style="width: 160px; height: 160px;">
                </div>
                <p id="site-address" class="handwriting">
                    Web Sitemizin adresi ♡
                </p>
            </div>
        </section>
    </main>
    <div id="image-modal" class="fixed inset-0 bg-black bg-opacity-80 hidden items-center justify-center z-50 p-4">
        <span id="close-modal" class="absolute top-4 right-6 text-white text-5xl font-bold cursor-pointer hover:text-gray-300 transition-colors">×</span>
        <img id="modal-image" src="" alt="Büyütülmüş Fotoğraf" class="max-w-[90vw] max-h-[90vh] rounded-lg shadow-lg">
        <span id="prev-photo" class="absolute top-1/2 left-4 -translate-y-1/2 text-white text-6xl font-bold cursor-pointer hover:text-gray-300 transition-colors select-none"><</span>
        <span id="next-photo" class="absolute top-1/2 right-4 -translate-y-1/2 text-white text-6xl font-bold cursor-pointer hover:text-gray-300 transition-colors select-none">></span>
    </div>
    <div id="video-modal" class="fixed inset-0 bg-black bg-opacity-80 hidden items-center justify-center z-50 p-4">
        <span id="close-video-modal" class="absolute top-4 right-6 text-white text-5xl font-bold cursor-pointer hover:text-gray-300 transition-colors">×</span>
        <div class="aspect-video w-full max-w-4xl"><iframe id="modal-video-iframe" class="w-full h-full" src="" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture; web-share" allowfullscreen></iframe></div>
    </div>
    <script>
    document.addEventListener('DOMContentLoaded', () => {
        'use strict';
        
        let invitationCurrentScale = 1;
        let invitationCurrentTranslateX = 0;
        let invitationCurrentTranslateY = 0;
        let invitationIsDragging = false;
        let invitationStartX, invitationStartY;

        let currentScale = 1;
        let currentTranslateX = 0;
        let currentTranslateY = 0;
        let isDragging = false;
        let startX, startY;
        let initialDist = 0;

        let photoUrls = [];
        let currentPhotoIndex = 0;

        const modal = document.getElementById('image-modal');
        const modalImage = document.getElementById('modal-image');

        // Sabit Arka Plan Mantığı (Zıplama yapmaz)
        const lockScroll = () => {
            // Sadece overflow hidden kullanıyoruz, position fixed zıplamaya sebep oluyordu
            document.documentElement.style.overflow = 'hidden';
            document.body.style.overflow = 'hidden';
        };

        const unlockScroll = () => {
            document.documentElement.style.overflow = '';
            document.body.style.overflow = '';
        };

        const applyInvitationTransform = () => {
            const img = document.getElementById('invitation-image');
            if (img && img instanceof Element) {
                img.style.transform = `translate(${invitationCurrentTranslateX}px, ${invitationCurrentTranslateY}px) scale(${invitationCurrentScale})`;
            }
        };

        const applyTransform = () => {
            if (modalImage && modalImage instanceof Element) {
                modalImage.style.transform = `translate(${currentTranslateX}px, ${currentTranslateY}px) scale(${currentScale})`;
            }
        };

        const getDist = (touches) => {
            return Math.sqrt(Math.pow(touches[0].pageX - touches[1].pageX, 2) + Math.pow(touches[0].pageY - touches[1].pageY, 2));
        };

        // --- Efektler ---
        const heartContainer = document.getElementById('falling-hearts-container');
        if (heartContainer) {
            for (let i = 0; i < 2; i++) {
                const heart = document.createElement('div');
                heart.className = 'falling-heart';
                heart.innerHTML = '💛';
                heart.style.left = (30 + i * 40) + '%';
                heart.style.animationDuration = (55 + i * 10) + 's';
                heart.style.animationDelay = (i * 15) + 's';
                heart.style.fontSize = (2.0 + Math.random() * 0.8) + 'rem';
                heartContainer.appendChild(heart);
            }
        }

        const leafSVG = `<svg viewBox="0 0 100 140" class="w-full h-full" preserveAspectRatio="xMidYMid meet"><path class="leaf-outer" d="M50 10 C30 15, 20 35, 18 55 C16 75, 25 95, 35 115 C45 130, 48 135, 50 138 C52 135, 55 130, 65 115 C75 95, 84 75, 82 55 C80 35, 70 15, 50 10 Z" /><path class="leaf-inner" d="M50 15 C33 20, 25 38, 23 55 C21 72, 28 88, 36 108 C44 125, 48 132, 50 135 C52 132, 56 125, 64 108 C72 88, 79 72, 77 55 C75 38, 67 20, 50 15 Z" /><path d="M50 15 Q50 70 48 135" stroke="#fff" stroke-width="2.5" opacity="0.5" fill="none"/><path d="M50 15 Q35 40 28 48 M50 55 Q32 65 25 75 M50 80 Q30 90 23 105" stroke="#fff" stroke-width="1.8" opacity="0.4" fill="none"/><path d="M50 15 Q65 40 72 48 M50 55 Q68 65 75 75 M50 80 Q70 90 77 105" stroke="#fff" stroke-width="1.8" opacity="0.4" fill="none"/></svg>`;
        const leafColors = ['autumn-1','autumn-2','autumn-3','autumn-4','autumn-5','autumn-6','autumn-7','autumn-8','autumn-9','autumn-10'];
        const leafContainer = document.getElementById('falling-leaves-container');
        if (leafContainer) {
            for (let i = 0; i < 2; i++) {
                const leaf = document.createElement('div');
                const colorClass = leafColors[Math.floor(Math.random() * leafColors.length)];
                leaf.className = `leaf-svg ${colorClass}`;
                leaf.style.left = (30 + i * 40) + '%';
                leaf.style.animationDuration = (60 + Math.random() * 25) + 's';
                leaf.style.animationDelay = (Math.random() * 40) + 's';
                leaf.innerHTML = leafSVG;
                leafContainer.appendChild(leaf);
            }
        }

        // --- IntersectionObservers ---
        const lazyLoadObserver = new IntersectionObserver((entries) => {
            entries.forEach(entry => {
                if (entry.isIntersecting && entry.target instanceof Element && entry.target.dataset.src) {
                    entry.target.src = entry.target.dataset.src;
                    lazyLoadObserver.unobserve(entry.target);
                }
            });
        }, { rootMargin: '50px' });
        
        document.querySelectorAll('img[data-src]').forEach(img => {
            if (img instanceof Element) lazyLoadObserver.observe(img);
        });

        const fadeObserver = new IntersectionObserver(entries => {
            entries.forEach(entry => { 
                if (entry.isIntersecting && entry.target instanceof Element && entry.target.classList) {
                    entry.target.classList.add('visible'); 
                }
            });
        }, { threshold: 0.1 });
        
        document.querySelectorAll('.fade-in-on-scroll').forEach(el => {
            if (el instanceof Element) fadeObserver.observe(el);
        });

        // --- Galeri Mantığı ---
        const updateModalPhoto = () => {
            if (modalImage && modalImage instanceof Element && photoUrls[currentPhotoIndex]) {
                modalImage.src = photoUrls[currentPhotoIndex];
                currentScale = 1;
                currentTranslateX = 0;
                currentTranslateY = 0;
                applyTransform();
            }
        };

        const openPhoto = (index) => {
            const thumbs = document.querySelectorAll('#gallery-grid img[data-src]');
            photoUrls = Array.from(thumbs).map(img => img.dataset.src);
            currentPhotoIndex = index;
            updateModalPhoto();
            if (modal && modal instanceof Element) {
                modal.classList.replace('hidden', 'flex');
                lockScroll();
            }
        };

        const closePhoto = () => {
            if (modal && modal instanceof Element) {
                modal.classList.replace('flex', 'hidden');
                unlockScroll();
            }
            if (modalImage && modalImage instanceof Element) modalImage.src = '';
            currentScale = 1;
            currentTranslateX = 0;
            currentTranslateY = 0;
        };

        document.getElementById('next-photo')?.addEventListener('click', (e) => {
            e.stopPropagation();
            if (photoUrls.length) {
                currentPhotoIndex = (currentPhotoIndex + 1) % photoUrls.length;
                updateModalPhoto();
            }
        });

        document.getElementById('prev-photo')?.addEventListener('click', (e) => {
            e.stopPropagation();
            if (photoUrls.length) {
                currentPhotoIndex = (currentPhotoIndex - 1 + photoUrls.length) % photoUrls.length;
                updateModalPhoto();
            }
        });

        document.getElementById('close-modal')?.addEventListener('click', closePhoto);
        modal?.addEventListener('click', (e) => { if (e.target === modal) closePhoto(); });

        // Mobile Pinch-to-Zoom
        modal?.addEventListener('touchstart', (e) => {
            if (e.touches.length === 2) {
                initialDist = getDist(e.touches);
            } else if (e.touches.length === 1) {
                isDragging = true;
                startX = e.touches[0].pageX - currentTranslateX;
                startY = e.touches[0].pageY - currentTranslateY;
            }
        }, { passive: false });

        modal?.addEventListener('touchmove', (e) => {
            if (e.touches.length === 2) {
                e.preventDefault();
                const currentDist = getDist(e.touches);
                const scaleFactor = currentDist / initialDist;
                currentScale = Math.min(Math.max(0.5, currentScale * scaleFactor), 8);
                initialDist = currentDist;
                applyTransform();
            } else if (e.touches.length === 1 && isDragging && currentScale > 1) {
                currentTranslateX = e.touches[0].pageX - startX;
                currentTranslateY = e.touches[0].pageY - startY;
                applyTransform();
            }
        }, { passive: false });

        modal?.addEventListener('touchend', () => {
            isDragging = false;
        });

        // Desktop Wheel Zoom
        modal?.addEventListener('wheel', (e) => {
            e.preventDefault();
            const delta = e.deltaY > 0 ? 0.9 : 1.1;
            currentScale = Math.min(Math.max(0.5, currentScale * delta), 8);
            applyTransform();
        }, { passive: false });

        document.getElementById('toggle-gallery-btn')?.addEventListener('click', function() {
            const wrapper = document.getElementById('gallery-wrapper');
            const icon = document.getElementById('gallery-toggle-icon');
            const text = document.getElementById('gallery-toggle-text');
            if (!wrapper) return;

            wrapper.classList.toggle('hidden');
            if (wrapper.classList.contains('hidden')) {
                if (text) text.textContent = 'Fotoğraf Galerisini Gör';
                if (icon) icon.classList.remove('rotate-180');
            } else {
                if (text) text.textContent = 'Galeriyi Gizle';
                if (icon) icon.classList.add('rotate-180');
                document.querySelectorAll('#gallery-grid .photo-container').forEach((el, i) => {
                    el.onclick = () => openPhoto(i);
                });
            }
        });

        document.getElementById('toggle-video-gallery-btn')?.addEventListener('click', function() {
            const wrapper = document.getElementById('video-gallery-wrapper');
            const icon = document.getElementById('video-gallery-toggle-icon');
            const text = document.getElementById('video-gallery-toggle-text');
            if (!wrapper) return;

            wrapper.classList.toggle('hidden');
            if (wrapper.classList.contains('hidden')) {
                if (text) text.textContent = 'Video Galerisini Gör';
                if (icon) icon.classList.remove('rotate-180');
            } else {
                if (text) text.textContent = 'Video Galerisini Gizle';
                if (icon) icon.classList.add('rotate-180');
                document.querySelectorAll('#video-grid .photo-container').forEach(el => {
                    el.onclick = () => {
                        const iframe = document.getElementById('modal-video-iframe');
                        if (iframe && el.dataset.youtubeId) {
                            iframe.src = `https://www.youtube.com/embed/${el.dataset.youtubeId}?autoplay=1`;
                            document.getElementById('video-modal')?.classList.replace('hidden', 'flex');
                            lockScroll();
                        }
                    };
                });
            }
        });

        document.getElementById('close-video-modal')?.addEventListener('click', () => {
            document.getElementById('video-modal')?.classList.replace('flex', 'hidden');
            unlockScroll();
            const iframe = document.getElementById('modal-video-iframe');
            if (iframe) iframe.src = '';
        });

        const invitationModal = document.getElementById('invitation-modal');
        document.getElementById('invitation-icon')?.addEventListener('click', () => {
            if (invitationModal) {
                invitationModal.classList.add('show');
                lockScroll();
                invitationCurrentScale = 1;
                invitationCurrentTranslateX = 0;
                invitationCurrentTranslateY = 0;
                applyInvitationTransform();
            }
        });

        document.getElementById('close-invitation')?.addEventListener('click', () => {
            if (invitationModal) {
                invitationModal.classList.remove('show');
                unlockScroll();
            }
        });

        document.addEventListener('keydown', e => {
            if (e.key === 'Escape') {
                closePhoto();
                document.getElementById('close-video-modal')?.click();
                if (invitationModal && invitationModal.classList.contains('show')) {
                    invitationModal.classList.remove('show');
                    unlockScroll();
                }
            }
            if (modal && modal.classList.contains('flex')) {
                if (e.key === 'ArrowRight') document.getElementById('next-photo')?.click();
                if (e.key === 'ArrowLeft') document.getElementById('prev-photo')?.click();
            }
        });

        // Masaüstü Sürükleme
        modalImage?.addEventListener('mousedown', (e) => {
            if (currentScale <= 1) return;
            e.preventDefault();
            isDragging = true;
            startX = e.clientX - currentTranslateX;
            startY = e.clientY - currentTranslateY;
            if (modalImage instanceof Element) modalImage.style.cursor = 'grabbing';
        });

        const invImg = document.getElementById('invitation-image');
        invImg?.addEventListener('mousedown', (e) => {
            if (invitationCurrentScale <= 1) return;
            e.preventDefault();
            invitationIsDragging = true;
            invitationStartX = e.clientX - invitationCurrentTranslateX;
            invitationStartY = e.clientY - invitationCurrentTranslateY;
            if (invImg instanceof Element) invImg.style.cursor = 'grabbing';
        });

        document.addEventListener('mousemove', (e) => {
            if (isDragging) {
                currentTranslateX = e.clientX - startX;
                currentTranslateY = e.clientY - startY;
                applyTransform();
            }
            if (invitationIsDragging) {
                invitationCurrentTranslateX = e.clientX - invitationStartX;
                invitationCurrentTranslateY = e.clientY - invitationStartY;
                applyInvitationTransform();
            }
        });

        document.addEventListener('mouseup', () => {
            isDragging = false;
            invitationIsDragging = false;
            if (modalImage && modalImage instanceof Element) modalImage.style.cursor = currentScale > 1 ? 'grab' : 'default';
            if (invImg && invImg instanceof Element) invImg.style.cursor = invitationCurrentScale > 1 ? 'grab' : 'default';
        });

        // Confetti
        setTimeout(() => {
            if (typeof confetti === 'function') {
                confetti({ particleCount: 40, spread: 70, origin: { y: 0.6 } });
            }
        }, 500);

        // Youtube Init
        const tag = document.createElement('script');
        tag.src = 'https://www.youtube.com/iframe_api';
        const firstScriptTag = document.getElementsByTagName('script')[0];
        if (firstScriptTag && firstScriptTag.parentNode) {
            firstScriptTag.parentNode.insertBefore(tag, firstScriptTag);
        }

        window.onYouTubeIframeAPIReady = function() {
            const playBtn = document.getElementById('play-song-btn');
            const playerElement = document.getElementById('youtube-player');
            const musicVisualizer = document.getElementById('music-visualizer');
            let isPlaying = false;

            if (!playBtn || !playerElement) return;

            const player = new YT.Player('youtube-player', {
                events: {
                    'onStateChange': e => {
                        if (e.data === YT.PlayerState.PLAYING) {
                            isPlaying = true;
                            playBtn.innerHTML = '<i class="fas fa-pause"></i>';
                            playBtn.classList.add('playing');
                            playerElement.classList.add('show');
                            if (musicVisualizer) musicVisualizer.classList.add('hidden');
                        } else {
                            isPlaying = false;
                            playBtn.innerHTML = '<i class="fas fa-play"></i>';
                            playBtn.classList.remove('playing');
                            playerElement.classList.remove('show');
                            if (musicVisualizer) musicVisualizer.classList.remove('hidden');
                        }
                    }
                }
            });

            playBtn.onclick = (e) => {
                e.stopPropagation();
                if (isPlaying) player.pauseVideo();
                else player.playVideo();
            };
        };
    });
    </script>
</body>
</html>
