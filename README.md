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
            position: fixed’an; top: 0; left: 0; right: 0; bottom: 0;
            background-image: url('https://www.toptal.com/designers/subtlepatterns/uploads/leaves.png');
            background-repeat: repeat; background-color: #fdfaf6; z-index: -2; pointer-events: none; opacity: 0.6;
        }
        @media (max-width: 768px) { #background-leaves-pattern { opacity: 0.9 !important; } }
        #falling-leaves-container { position: fixed; top: 0; left: 0; right: 0; bottom: 0; pointer-events: none; z-index: -1; overflow: hidden; }
        #top-left-leaf {
            position: fixed;
            top: 12px;
            left: 12px;
            width: 68px;
            height: 68px;
            background: url('https://i.imgur.com/4u0Z2kw.png') center/contain no-repeat;
            background-size: contain;
            z-index: 99999;
            cursor: pointer;
            transition: transform 0.4s ease;
            filter: drop-shadow(0 4px 12px rgba(0,0,0,0.3));
            border-radius: 16px;
            animation: gentleFloat 7s ease-in-out infinite;
        }
        #top-left-leaf:hover { transform: scale(1.35) rotate(12deg); }
        @keyframes gentleFloat {
            0%,100% { transform: translateY(0) rotate(0deg); }
            50% { transform: translateY(-10px) rotate(8deg); }
        }
        @media (max-width: 768px) {
            #top-left-leaf { width: 56px; height: 56px; top: 8px; left: 8px; }
        }
        h1, h2, h3 { font-family: 'Playfair Display', serif; }
        .handwriting { font-family: 'Dancing Script', cursive; }
        .font-forte-alternative { font-family: 'Dancing Script', cursive; }
        .font-poor-richard-alternative { font-family: 'Cormorant Garamond', serif; }
        @keyframes heartbeat { 0%,100%{transform:scale(1)} 50%{transform:scale(1.1)} }
        .heartbeat { animation: heartbeat 1.5s infinite; }
        #main-title { font-size: 3rem !important; line-height: 1.2 !important; }
        @media (min-width: 768px) { #main-title { font-size: 4rem !important; } }
        main h3:not(#ilk-adim-baslik) { font-size: 1.5rem !important; line-height: 1.3 !important; }
        @media (min-width: 768px) { main h3:not(#ilk-adim-baslik) { font-size: 2rem !important; } }
        #ilk-adim-baslik { font-size: 1.5rem !important; line-height: 1.4 !important; }
        @media (min-width: 768px) { #ilk-adim-baslik { font-size: 1.75rem !important; } }
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
        .timeline-icon { position: absolute; top: -15px; left: 20px; background: white; border-radius: 50%; width: 40px; height: 40px; display: flex; align-items: center; justify-content: center; box-shadow: 0 4px 8px rgba(0,0,we 0.1); font-size: 1.2rem; color: #ef4444; z-index: 3; transform: rotate(0deg); transition: transform 0.6s ease; }
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
        #sonbahar-baslik { font-size: 1.5rem !important; line-height: 1.3 !important; }
        @media (min-width: 768px) { #sonbahar-baslik { font-size: 2.25rem !important; } }
        .poem-container { max-width: 90%; margin: 0 auto; padding: 2rem 0; line-height: 2.3; font-size: 1.725rem; font-style: italic; color: #1f2937; text-align: center; }
        .poem-line { display: block; margin: 0.2rem 0; padding: 0.5rem; border-radius: 8px; font-family: 'Cormorant Garamond', serif; }
        @media (max-width: 768px) {
            .poem-line { font-size: 2.025rem !important; line-height: 2.6 !important; letter-spacing: 0.5px; }
            .poem-container { padding: 1.5rem 0 !important; font-size: 1.95rem; }
        }
        .poem-signature { font-size: 1.5rem !important; line-height: 1.4 !important; }
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
    </style>
</head>
<body class="text-black">
    <a href="#countdown-section">
        <div id="top-left-leaf" title="Büyük Güne Geri Sayım ❤️"></div>
    </a>
    <div id="background-leaves-pattern"></div>
    <div id="falling-leaves-container"></div>

    <!-- HEADER - KAYBOLUYOR + %75 BÜYÜK -->
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
                <h1 class="text-7xl md:text-9xl font-bold text-green-600 flex items-center justify-center space-x-8 handwriting leading-tight">
                    <span>Arzu</span>
                    <i class="fas fa-heart text-red-500 text-7xl md:text-9xl heartbeat"></i>
                    <span>Ersin</span>
                </h1>
                <p class="text-2xl md:text-3xl text-red-600 mt-4">Bizim Yolculuğumuz</p>
            </div>
        </div>
    </header>

    <!-- TÜM KALAN KOD DEĞİŞMEDEN AYNI -->
    <!-- (Senin verdiğin son kodun tamamı aşağıda devam ediyor) -->
    <section id="main-title-section" class="py-16 text-center">
        <h2 id="main-title" class="font-bold handwriting text-green-600">O Güzel Sonbahar</h2>
        <p class="text-xl md:text-2xl mt-2 text-red-600 font-bold">27 Eylül 2025</p>
        <p class="text-lg mt-1 text-red-600 italic font-bold">Zamanın durduğu an</p>
    </section>
    <main class="container mx-auto px-6 pb-12">
        <!-- İLK ADIM -->
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
        <!-- ŞİİR -->
        <section class="my-16 max-w-3xl mx-auto text-center">
            <h3 id="sonbahar-baslik" class="font-bold text-center text-red-600 mb-6 handwriting font-forte-alternative text-3xl md:text-5xl">Sonbahar</h3>
            <div class="poem-container">
                <div class="poem-line font-semibold italic text-black">Çiçekli badem ağaçlarını unut.</div>
                <div class="poem-line font-semibold italic text-black">değmez,</div>
                <div class="poem-line font-semibold italic text-black">bu bahiste</div>
                <div class="poem-line font-semibold italic text-black">geri gelmesi mümkün olmayan hatırlanmamalı.</div>
                <div class="poem-line font-semibold italic text-black">ıslak saçlarını güneşte kurut</div>
                <div class="poem-line font-semibold italic text-black">olgun meyvelerin baygınlığıyla parıldasın</div>
                <div class="poem-line font-semibold italic text-black">nemli, ağır kızıltılar…</div>
                <div class="poem-line font-semibold italic text-black">sevgilim, sevgilim,</div>
                <div class="poem-line font-semibold italic text-black">mevsim</div>
                <div class="poem-line font-semibold italic text-black">sonbahar…</div>
            </div>
            <p class="text-right text-red-600 font-semibold-bold mt-6 pr-4 font-forte-alternative poem-signature">- Nazım Hikmet</p>
        </section>
        <!-- AŞK ZAMAN ÇİZELGESİ -->
        <section class="my-16 max-w-5xl mx-auto p-4 md:p-8 text-center">
            <h3 class="font-bold text-center text-red-600 mb-4 handwriting">Aşk Zaman Çizelgesi</h3>
            <p class="text-center text-black font-semibold italic mb-8">
                Yolculuğumuzun unutulmaz anlarını, kalplerin ritmiyle keşfedin...
            </p>
            <div class="timeline-container">
                <div class="timeline-item left">
                    <div class="timeline-icon"><i class="fas fa-heart heartbeat"></i></div>
                    <div class="timeline-content">
                        <h4>Eylül</h4>
                        <p class="font-semibold italic">
                            Yaprakların dans ettiği o sonbahar gününde, gözlerinle tanıştım seninle...
                        </p>
                    </div>
                </div>
                <div class="timeline-item right">
                    <div class="timeline-icon"><i class="fas fa-infinity heartbeat"></i></div>
                    <div class="timeline-content">
                        <h4>Sonsuza Dek...</h4>
                        <p class="font-semibold italic">
                            Yemin ettik birbirimize, Yıldızlar eşliğinde...
                        </p>
                    </div>
                </div>
            </div>
        </section>
        <!-- BÜYÜK GÜNE GERİ SAYIM -->
        <section id="countdown-section" class="my-16 max-w-3xl mx-auto transparent-section text-center">
            <h3 class="font-bold text-red-600 mb-6 font-forte-alternative">Büyük Güne Geri Sayım</h3>
            <div id="countdown-placeholder" class="my-4">
                <div class="text-8xl text-red-500 heartbeat"><i class="fas fa-infinity"></i></div>
                <p class="text-center text-black font-semibold italic text-lg mt-4">
                    Sonsuzluğa giden yolculuğumuzun tarihi belli olduğunda...
                </p>
            </div>
            <div id="countdown-timer" class="hidden grid grid-cols-4 gap-4 text-center">
                <div><span id="days" class="block text-5xl font-bold text-green-600">0</span><span class="text-sm text-red-600">Gün</span></div>
                <div><span id="hours" class="block text-5xl font-bold text-green-600">00</span><span class="text-sm text-red-600">Saat</span></div>
                <div><span id="minutes" class="block text-5xl font-bold text-green-600">00</span><span class="text-sm text-red-600">Dakika</span></div>
                <div><span id="seconds" class="block text-5xl font-bold text-green-600">00</span><span class="text-sm text-red-600">Saniye</span></div>
            </div>
        </section>
        <!-- HAYAL DEFTERİMİZ -->
        <section class="my-16 max-w-3xl mx-auto transparent-section text-center fade-in-on-scroll">
            <h3 class="font-bold text-red-600 mb-6 handwriting">Hayal Defterimiz</h3>
            <p class="text-center text-black font-semibold italic text-lg mt-4">
                Birlikte kurduğumuz hayaller, geleceğe dair ektiğimiz tohumlar...
            </p>
        </section>
        <!-- BİZİM ŞARKIMIZ -->
        <section class="my-16 max-w-3xl mx-auto transparent-section text-center relative overflow-hidden">
            <h3 class="font-bold text-red-600 mb-6 handwriting">Bizim Şarkımız</h3>
            <p class="text-center text-black font-semibold italic mt-2 mb-6">Tarkan - Beni Çok Sev</p>
            <div class="song-container">
                <iframe id="youtube-player"
                        src="https://www.youtube.com/embed/IYnu4-69fTA?autoplay=0&rel=0&modestbranding=1&playsinline=1&enablejsapi=1"
                        title="Tarkan - Beni Çok Sev"
                        frameborder="0"
                        allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture"
                        allowfullscreen>
                </iframe>
                <div id="music-visualizer" class="music-visualizer">
                    <div class="note">♪</div><div class="note">♫</div><div class="note">♪</div><div class="note">♬</div>
                    <div class="note">♪</div><div class="note">♫</div><div class="note">♪</div><div class="note">♬</div>
                </div>
                <div class="song-control">
                    <div class="song-label">Dinle</div>
                    <button id="play-song-btn" title="Şarkıyı Çal"><i class="fas fa-play"></i></button>
                </div>
            </div>
        </section>
        <!-- SEYAHATLER -->
        <section class="my-16 max-w-5xl mx-auto p-4 md:p-8 text-center">
            <h3 class="font-bold text-center text-red-600 mb-4 handwriting">Seyahatlerimiz</h3>
            <p class="text-center text-black font-semibold italic">Birlikte keşfettiğimiz yerler...</p>
            <div class="mt-8 text-center">
                <button id="toggle-travel-btn" class="inline-flex items-center justify-center py-2 px-6 border border-red-600 shadow-sm text-sm font-medium rounded-md text-red-600 bg-white hover:bg-red-50 transition-colors">
                    <span id="travel-toggle-text">Seyahatlerimizi Gör</span>
                    <i id="travel-toggle-icon" class="fas fa-chevron-down ml-2 transition-transform"></i>
                </button>
            </div>
            <div id="travel-wrapper" class="hidden mt-8">
                <div class="grid grid-cols-2 sm:grid-cols-3 md:grid-cols-4 lg:grid-cols-6 gap-2 md:gap-1">
                    <div class="travel-folder group"><div class="text-4xl text-green-500"><i class="fas fa-map-marked-alt"></i></div><h4>Kapadokya Gezisi</h4><p>Balonlar arasında...</p></div>
                    <div class="travel-folder group"><div class="text-4xl text-green-500"><i class="fas fa-umbrella-beach"></i></div><h4>Ege Sahilleri</h4><p>Deniz, kum, güneş...</p></div>
                    <div class="travel-folder group"><div class="text-4xl text-green-500"><i class="fas fa-ship"></i></div><h4>Akdeniz Turu</h4><p>Mavi yolculuk...</p></div>
                </div>
            </div>
        </section>
        <!-- FOTOĞRAF GALERİSİ -->
        <section class="my-16 max-w-5xl mx-auto p-4 md:p-8 text-center">
            <h3 class="font-bold text-center text-red-600 mb-4 handwriting">Fotoğraf Galerimiz</h3>
            <p class="text-center text-black font-semibold italic">İşte yolculuğumuzda biriktirdiğimiz Anılar..</p>
            <div class="mt-8 text-center">
                <button id="toggle-gallery-btn" class="inline-flex items-center justify-center py-2 px-6 border border-red-600 shadow-sm text-sm font-medium rounded-md text-red-600 bg-white hover:bg-red-50 transition-colors">
                    <span id="gallery-toggle-text">Fotoğraf Galerisini Gör</span>
                    <i id="gallery-toggle-icon" class="fas fa-chevron-down ml-2 transition-transform"></i>
                </button>
            </div>
            <div id="gallery-wrapper" class="hidden mt-8">
                <div class="grid grid-cols-3 sm:grid-cols-4 md:grid-cols-5 lg:grid-cols-6 gap-1" id="gallery-grid">
                    <div class="photo-container group cursor-pointer"><img data-src="https://i.imgur.com/cDWfV6z.jpg" alt="Güldür Güldür" class="gallery-thumbnail w-full h-full object-cover" loading="lazy"><span class="photo-number opacity-0 group-hover:opacity-100">9</span><div class="photo-note">Güldür Güldür</div></div>
                    <div class="photo-container group cursor-pointer"><img data-src="https://i.imgur.com/jlmfKQ6.jpg" alt="Nev Mekan" class="gallery-thumbnail w-full h-full object-cover" loading="lazy"><span class="photo-number opacity-0 group-hover:opacity-100">8</span><div class="photo-note">Nev Mekan</div></div>
                    <div class="photo-container group cursor-pointer"><img data-src="https://i.imgur.com/EI3PjiL.jpg" alt="Nev Mekan" class="gallery-thumbnail w-full h-full object-cover" loading="lazy"><span class="photo-number opacity-0 group-hover:opacity-100">7</span><div class="photo-note">Nev Mekan</div></div>
                    <div class="photo-container group cursor-pointer"><img data-src="https://i.imgur.com/wf9Xhs9.jpg" alt="Anı 1" class="gallery-thumbnail w-full h-full object-cover" loading="lazy"><span class="photo-number opacity-0 group-hover:opacity-100">6</span><div class="photo-note">Lunapark Anısı</div></div>
                    <div class="photo-container group cursor-pointer"><img data-src="https://i.imgur.com/G26zsUc.jpg" alt="Anı 2" class="gallery-thumbnail w-full h-full object-cover" loading="lazy"><span class="photo-number opacity-0 group-hover:opacity-100">5</span><div class="photo-note">Beşiktaş</div></div>
                    <div class="photo-container group cursor-pointer"><img data-src="https://i.imgur.com/PR2hWYz.jpg" alt="Anı 3" class="gallery-thumbnail w-full h-full object-cover" loading="lazy"><span class="photo-number opacity-0 group-hover:opacity-100">4</span><div class="photo-note">Çamlıca Kahvaltımız</div></div>
                    <div class="photo-container group cursor-pointer"><img data-src="https://i.imgur.com/40oguJF.jpg" alt="Anı 4" class="gallery-thumbnail w-full h-full object-cover" loading="lazy"><span class="photo-number opacity-0 group-hover:opacity-100">3</span><div class="photo-note">Çamlıca Kahvaltımız</div></div>
                    <div class="photo-container group cursor-pointer"><img data-src="https://i.imgur.com/KZpZnaa.jpg" alt="Anı 5" class="gallery-thumbnail w-full h-full object-cover" loading="lazy"><span class="photo-number opacity-0 group-hover:opacity-100">2</span><div class="photo-note">Dünya Güzelim</div></div>
                    <div class="photo-container group cursor-pointer no-note"><img data-src="https://i.imgur.com/WnEibNN.jpg" alt="Anı 6" class="gallery-thumbnail w-full h-full object-cover" loading="lazy"><span class="photo-number opacity-0 group-hover:opacity-100">1</span></div>
                </div>
            </div>
        </section>
        <!-- VİDEO GALERİSİ -->
        <section class="my-16 max-w-5xl mx-auto p-4 md:p-8 text-center">
            <h3 class="font-bold text-center text-red-600 mb-4 handwriting">Video Galerimiz</h3>
            <p class="text-center text-black font-semibold">Bazı duyguları kelimelerle anlatmak yetmez...</p>
            <div class="mt-8 text-center">
                <button id="toggle-video-gallery-btn" class="inline-flex items-center justify-center py-2 px-6 border border-red-600 shadow-sm text-sm font-medium rounded-md text-red-600 bg-white hover:bg-red-50 transition-colors">
                    <span id="video-gallery-toggle-text">Video Galerisini Gör</span>
                    <i id="video-gallery-toggle-icon" class="fas fa-chevron-down ml-2 transition-transform"></i>
                </button>
            </div>
            <div id="video-gallery-wrapper" class="hidden mt-8">
                <div class="grid grid-cols-3 sm:grid-cols-4 md:grid-cols-5 lg:grid-cols-6 gap-1" id="video-grid">
                    <div class="photo-container group cursor-pointer aspect-square" data-youtube-id="wcZOC94zAYw"><img data-src="https://img.youtube.com/vi/wcZOC94zAYw/maxresdefault.jpg" alt="Güldür Güldür" class="w-full h-full object-cover gallery-thumbnail" loading="lazy"><div class="absolute inset-0 flex items-center justify-center bg-black bg-opacity-40"><i class="far fa-play-circle text-white text-5xl opacity-80 group-hover:opacity-100 transition-opacity"></i></div><span class="photo-number opacity-0 group-hover:opacity-100">6</span><div class="photo-note">Güldür Güldür</div></div>
                    <div class="photo-container group cursor-pointer aspect-square" data-youtube-id="ChFa2GJ4e4U"><img data-src="https://img.youtube.com/vi/ChFa2GJ4e4U/maxresdefault.jpg" alt="Video 1" class="w-full h-full object-cover gallery-thumbnail" loading="lazy"><div class="absolute inset-0 flex items-center justify-center bg-black bg-opacity-40"><i class="far fa-play-circle text-white text-5xl opacity-80 group-hover:opacity-100 transition-opacity"></i></div><span class="photo-number opacity-0 group-hover:opacity-100">5</span><div class="photo-note">Beşiktaş</div></div>
                    <div class="photo-container group cursor-pointer aspect-square" data-youtube-id="aim5II5vYpU"><img data-src="https://img.youtube.com/vi/aim5II5vYpU/maxresdefault.jpg" alt="Video 2" class="w-full h-full object-cover gallery-thumbnail" loading="lazy"><div class="absolute inset-0 flex items-center justify-center bg-black bg-opacity-40"><i class="far fa-play-circle text-white text-5xl opacity-80 group-hover:opacity-100 transition-opacity"></i></div><span class="photo-number opacity-0 group-hover:opacity-100">4</span><div class="photo-note">Üsküdar</div></div>
                    <div class="photo-container group cursor-pointer aspect-square" data-youtube-id="uY6ZrwkbLjc"><img data-src="https://img.youtube.com/vi/uY6ZrwkbLjc/maxresdefault.jpg" alt="Video 3" class="w-full h-full object-cover gallery-thumbnail" loading="lazy"><div class="absolute inset-0 flex items-center justify-center bg-black bg-opacity-40"><i class="far fa-play-circle text-white text-5xl opacity-80 group-hover:opacity-100 transition-opacity"></i></div><span class="photo-number opacity-0 group-hover:opacity-100">3</span><div class="photo-note">Lunapark</div></div>
                    <div class="photo-container group cursor-pointer aspect-square" data-youtube-id="19aKq8FtYP8"><img data-src="https://img.youtube.com/vi/19aKq8FtYP8/maxresdefault.jpg" alt="Video 4" class="w-full h-full object-cover gallery-thumbnail" loading="lazy"><div class="absolute inset-0 flex items-center justify-center bg-black bg-opacity-40"><i class="far fa-play-circle text-white text-5xl opacity-80 group-hover:opacity-100 transition-opacity"></i></div><span class="photo-number opacity-0 group-hover:opacity-100">2</span><div class="photo-note">Beşiktaş</div></div>
                    <div class="photo-container group cursor-pointer aspect-square" data-youtube-id="J466tfX1jzk"><img data-src="https://img.youtube.com/vi/J466tfX1jzk/maxresdefault.jpg" alt="Video 5" class="gallery-thumbnail w-full h-full object-cover" loading="lazy"><div class="absolute inset-0 flex items-center justify-center bg-black bg-opacity-40"><i class="far fa-play-circle text-white text-5xl opacity-80 group-hover:opacity-100 transition-opacity"></i></div><span class="photo-number opacity-0 group-hover:opacity-100">1</span><div class="photo-note">Ev</div></div>
                </div>
            </div>
        </section>
        <!-- TEŞEKKÜR -->
        <section class="my-16 max-w-3xl mx-auto transparent-section">
            <h3 class="font-bold text-center text-red-600 mb-6 handwriting">Teşekkür</h3>
            <p class="text-center text-black text-lg italic mt-4 font-bold">
                Bu mutlu yolculuğumuzda yanımızda olan herkese sonsuz teşekkürler.
            </p>
            <div class="mt-8 space-y-4">
                <p class="text-center text-black font-semibold">Bizi biz yapan, sevgileriyle her zaman en büyük destekçimiz olan canımız ailelerimize...</p>
                <p class="text-center text-black font-semibold">İyi günde, kötü günde her anımızda yanımızda olan değerli dostlarımıza...</p>
            </div>
            <div class="mt-16 text-center fade-in-on-scroll">
                <p class="text-red-600 italic text-xl md:text-2xl mb-6 font-medium">
                    Kalbinizden geçenleri bize yazmak isterseniz İletişim adresimiz ♡
                </p>
                <div class="flex justify-center">
                    <div class="inline-flex items-center gap-4 bg-white/90 px-6 py-4 rounded-full shadow-lg border-2 border-pink-200 group cursor-pointer">
                        <div class="relative">
                            <i class="fas fa-envelope text-4xl text-red-600 group-hover:text-red-700 transition-all duration-500 transform group-hover:scale-125"></i>
                            <i class="fas fa-heart absolute -top-2 -right-2 text-red-500 text-xl opacity-0 group-hover:opacity-100 animate-ping"></i>
                        </div>
                        <span class="font-bold text-green-700 text-base md:text-lg select-all group-hover:text-green-800 transition-colors">
                            arzuersin2025@gmail.com
                        </span>
                    </div>
                </div>
            </div>
        </section>
    </main>
    <footer class="text-center py-8 mt-12">
        <p class="text-black flex items-center justify-center space-x-2"><span>Bu hikaye</span><i class="fas fa-infinity text-red-500"></i><span>kadar devam edecek...</span></p>
        <p class="text-black mt-4 flex items-center justify-center gap-5 handwriting text-5xl md:text-6xl font-bold">
            Arzu <i class="fas fa-heart text-red-600 heartbeat text-3xl md:text-4xl"></i> Ersin
        </p>
    </footer>
    <!-- MODALLAR -->
    <div id="image-modal" class="fixed inset-0 bg-black bg-opacity-80 hidden items-center justify-center z-50 p-4">
        <span id="close-modal" class="absolute top-4 right-6 text-white text-5xl font-bold cursor-pointer hover:text-gray-300 transition-colors">×</span>
        <img id="modal-image" src="" alt="Büyütülmüş Fotoğraf" class="max-w-[90vw] max-h-[90vh] rounded-lg shadow-lg">
        <span id="prev-photo" class="absolute top-1/2 left-4 -translate-y-1/2 text-white text-6xl font-bold cursor-pointer hover:text-gray-300 transition-colors select-none">&lt;</span>
        <span id="next-photo" class="absolute top-1/2 right-4 -translate-y-1/2 text-white text-6xl font-bold cursor-pointer hover:text-gray-300 transition-colors select-none">&gt;</span>
    </div>
    <div id="video-modal" class="fixed inset-0 bg-black bg-opacity-80 hidden items-center justify-center z-50 p-4">
        <span id="close-video-modal" class="absolute top-4 right-6 text-white text-5xl font-bold cursor-pointer hover:text-gray-300 transition-colors">×</span>
        <div class="aspect-video w-full max-w-4xl"><iframe id="modal-video-iframe" class="w-full h-full" src="" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture; web-share" allowfullscreen></iframe></div>
    </div>
    <script>
    (() => {
        'use strict';
        const COUNTDOWN_DATE = "";
        const leafSVG = `<svg viewBox="0 0 100 140" class="w-full h-full" preserveAspectRatio="xMidYMid meet"><path class="leaf-outer" d="M50 10 C30 15, 20 35, 18 55 C16 75, 25 95, 35 115 C45 130, 48 135, 50 138 C52 135, 55 130, 65 115 C75 95, 84 75, 82 55 C80 35, 70 15, 50 10 Z" /><path class="leaf-inner" d="M50 15 C33 20, 25 38, 23 55 C21 72, 28 88, 36 108 C44 125, 48 132, 50 135 C52 132, 56 125, 64 108 C72 88, 79 72, 77 55 C75 38, 67 20, 50 15 Z" /><path d="M50 15 Q50 70 48 135" stroke="#fff" stroke-width="2.5" opacity="0.5" fill="none"/><path d="M50 15 Q35 40 28 48 M50 55 Q32 65 25 75 M50 80 Q30 90 23 105" stroke="#fff" stroke-width="1.8" opacity="0.4" fill="none"/><path d="M50 15 Q65 40 72 48 M50 55 Q68 65 75 75 M50 80 Q70 90 77 105" stroke="#fff" stroke-width="1.8" opacity="0.4" fill="none"/></svg>`;
        const leafColors = ['autumn-1','autumn-2','autumn-3','autumn-4','autumn-5','autumn-6','autumn-7','autumn-8','autumn-9','autumn-10'];
        const leafContainer = document.getElementById('falling-leaves-container');
        for (let i = 0; i < 7; i++) {
            const leaf = document.createElement('div');
            const colorClass = leafColors[Math.floor(Math.random() * leafColors.length)];
            leaf.className = `leaf-svg ${colorClass}`;
            leaf.style.left = Math.random() * 100 + 'vw';
            const scale = 0.5 + 0.9 * Math.random();
            leaf.style.transform = `scale(${scale}) rotate(${Math.random() * 360}deg)`;
            const duration = 18 + Math.random() * 12;
            leaf.style.animationDuration = duration + 's';
            leaf.style.animationDelay = Math.random() * 10 + 's';
            leaf.innerHTML = leafSVG;
            leafContainer.appendChild(leaf);
        }
        const lazyLoadObserver = new IntersectionObserver((entries) => {
            entries.forEach(entry => {
                if (entry.isIntersecting) {
                    const img = entry.target;
                    if (img.dataset.src) {
                        img.src = img.dataset.src;
                        img.onload = () => img.classList.add('loaded');
                    }
                    lazyLoadObserver.unobserve(img);
                }
            });
        }, { rootMargin: '50px' });
        document.querySelectorAll('img[data-src]').forEach(img => lazyLoadObserver.observe(img));
        let imgs = [], curIdx = 0, videoIds = [], curVideoIdx = 0;
        const refreshImgs = () => { imgs = Array.from(document.querySelectorAll('#gallery-grid img')).map(i => i.src).filter(s => s && !s.includes('svg')); };
        const refreshVideos = () => { videoIds = Array.from(document.querySelectorAll('#video-grid .photo-container')).map(el => el.dataset.youtubeId); };
        const openImg = idx => { refreshImgs(); curIdx = idx; document.getElementById('modal-image').src = imgs[curIdx]; document.getElementById('image-modal').classList.replace('hidden','flex'); };
        const closeImg = () => { document.getElementById('image-modal').classList.replace('flex','hidden'); document.getElementById('modal-image').src = ''; };
        const nextImg = () => { curIdx = (curIdx + 1) % imgs.length; document.getElementById('modal-image').src = imgs[curIdx]; };
        const prevImg = () => { curIdx = (curIdx - 1 + imgs.length) % imgs.length; document.getElementById('modal-image').src = imgs[curIdx]; };
        const openVideo = idx => { refreshVideos(); curVideoIdx = idx; document.getElementById('modal-video-iframe').src = `https://www.youtube.com/embed/${videoIds[curVideoIdx]}?autoplay=1`; document.getElementById('video-modal').classList.replace('hidden','flex'); };
        const closeVideo = () => { document.getElementById('video-modal').classList.replace('flex','hidden'); document.getElementById('modal-video-iframe').src = ''; };
        document.getElementById('toggle-gallery-btn').onclick = () => {
            const w = document.getElementById('gallery-wrapper');
            w.classList.toggle('hidden');
            document.getElementById('gallery-toggle-icon').classList.toggle('rotate-180', !w.classList.contains('hidden'));
            document.getElementById('gallery-toggle-text').textContent = w.classList.contains('hidden') ? 'Fotoğraf Galerisini Gör' : 'Galeriyi Gizle';
            if (!w.classList.contains('hidden')) setTimeout(() => document.querySelectorAll('#gallery-grid .photo-container').forEach((c,i) => c.onclick = () => openImg(i)), 100);
        };
        document.getElementById('toggle-travel-btn').onclick = () => {
            const w = document.getElementById('travel-wrapper');
            w.classList.toggle('hidden');
            document.getElementById('travel-toggle-icon').classList.toggle('rotate-180', !w.classList.contains('hidden'));
            document.getElementById('travel-toggle-text').textContent = w.classList.contains('hidden') ? 'Seyahatlerimizi Gör' : 'Seyahatleri Gizle';
        };
        document.getElementById('toggle-video-gallery-btn').onclick = () => {
            const w = document.getElementById('video-gallery-wrapper');
            w.classList.toggle('hidden');
            document.getElementById('video-gallery-toggle-icon').classList.toggle('rotate-180', !w.classList.contains('hidden'));
            document.getElementById('video-gallery-toggle-text').textContent = w.classList.contains('hidden') ? 'Video Galerisini Gör' : 'Video Galerisini Gizle';
            if (!w.classList.contains('hidden')) setTimeout(() => document.querySelectorAll('#video-grid .photo-container').forEach((c,i) => c.onclick = () => openVideo(i)), 100);
        };
        document.getElementById('close-modal').onclick = closeImg;
        document.getElementById('prev-photo').onclick = e => { e.stopPropagation(); prevImg(); };
        document.getElementById('next-photo').onclick = e => { e.stopPropagation(); nextImg(); };
        document.getElementById('image-modal').onclick = e => { if (e.target === e.currentTarget) closeImg(); };
        document.getElementById('close-video-modal').onclick = closeVideo;
        document.getElementById('video-modal').onclick = e => { if (e.target === e.currentTarget) closeVideo(); };
        document.addEventListener('keydown', e => {
            if (e.key === 'Escape') { closeImg(); closeVideo(); }
            if (e.key === 'ArrowRight' && document.getElementById('image-modal').classList.contains('flex')) nextImg();
            if (e.key === 'ArrowLeft' && document.getElementById('image-modal').classList.contains('flex')) prevImg();
        });
        if (COUNTDOWN_DATE) {
            const target = new Date(COUNTDOWN_DATE).getTime();
            const timer = document.getElementById('countdown-timer');
            const placeholder = document.getElementById('countdown-placeholder');
            const header = document.getElementById('header-countdown');
            placeholder.classList.add('hidden');
            timer.classList.remove('hidden');
            header.classList.remove('hidden');
            const pad = n => n < 10 ? '0'+n : n;
            const update = () => {
                const diff = target - Date.now();
                if (diff <= 0) { clearInterval(intv); timer.innerHTML = '<p class="col-span-full text-xl text-green-600">Ve o güzel gün geldi!</p>'; return; }
                const d = Math.floor(diff/(1000*60*60*24));
                const h = Math.floor((diff%(1000*60*60*24))/(1000*60*60));
                const m = Math.floor((diff%(1000*60*60))/(1000*60));
                const s = Math.floor((diff%(1000*60))/1000);
                document.getElementById('days').textContent = d;
                document.getElementById('hours').textContent = pad(h);
                document.getElementById('minutes').textContent = pad(m);
                document.getElementById('seconds').textContent = pad(s);
                document.getElementById('header-days').textContent = d;
                document.getElementById('header-hours').textContent = pad(h);
                document.getElementById('header-minutes').textContent = pad(m);
            };
            update();
            const intv = setInterval(update, 1000);
        }
        const timelineObserver = new IntersectionObserver((entries) => {
            entries.forEach((e,i) => {
                if (e.isIntersecting) setTimeout(() => e.target.classList.add('animate'), i * 300);
            });
        }, { threshold: 0.3 });
        document.querySelectorAll('.timeline-item').forEach(item => timelineObserver.observe(item));
        const obs = new IntersectionObserver(entries => {
            entries.forEach(entry => { if (entry.isIntersecting) entry.target.classList.add('visible'); });
        }, { threshold: 0.3 });
        document.querySelectorAll('.fade-in-on-scroll, .travel-folder').forEach(el => obs.observe(el));
        let player, isPlaying = false, userInteracted = false;
        const playBtn = document.getElementById('play-song-btn');
        const playerElement = document.getElementById('youtube-player');
        const musicVisualizer = document.getElementById('music-visualizer');
        const tag = document.createElement('script');
        tag.src = 'https://www.youtube.com/iframe_api';
        document.getElementsByTagName('script')[0].parentNode.insertBefore(tag, document.getElementsByTagName('script')[0]);
        window.onYouTubeIframeAPIReady = function() {
            player = new YT.Player('youtube-player', {
                events: {
                    'onReady': () => {
                        const unlock = () => { userInteracted = true; document.removeEventListener('click', unlock); document.removeEventListener('touchstart', unlock); };
                        document.addEventListener('click', unlock, { once: true });
                        document.addEventListener('touchstart', unlock, { once: true });
                    },
                    'onStateChange': event => {
                        if (event.data === YT.PlayerState.PLAYING) {
                            isPlaying = true;
                            playBtn.innerHTML = '<i class="fas fa-pause"></i>';
                            playBtn.classList.add('playing');
                            playerElement.classList.add('show');
                            musicVisualizer.classList.add('hidden');
                        } else {
                            isPlaying = false;
                            playBtn.innerHTML = '<i class="fas fa-play"></i>';
                            playBtn.classList.remove('playing');
                            playerElement.classList.remove('show');
                            musicVisualizer.classList.remove('hidden');
                        }
                    }
                }
            });
        };
        playBtn.onclick = e => {
            e.stopPropagation();
            if (!player) return;
            isPlaying ? player.pauseVideo() : player.playVideo();
        };
    })();
    </script>
</body>
</html>
