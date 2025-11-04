<!DOCTYPE html>
<html lang="tr">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Arzu & Ersin | Bizim Hikayemiz</title>
    <script src="https://cdn.tailwindcss.com"></script>
    <link rel="preconnect" href="https://fonts.googleapis.com">
    <link rel="preconnect" href="https://fonts.gstatic.com" crossorigin>
    <link href="https://fonts.googleapis.com/css2?family=Playfair+Display:wght@400;700&family=Poppins:wght@300;400;500;600;700;800;900&family=Dancing+Script:wght@700&family=Lobster&family=Alex+Brush&family=Cormorant+Garamond&display=swap" rel="stylesheet">
    <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.5.1/css/all.min.css"
          integrity="sha512-DTOQO9RWCH3ppGqcWaEA1BIZOC6xxalwEsw9c2QQeAIftl+Vegovlnee1c9QX4TctnWMn13TZye+giMm8e2LwA=="
          crossorigin="anonymous" referrerpolicy="no-referrer" />
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

        /* ARKA PLAN YAPRAK DESENİ - HER ZAMAN GÖRÜNÜR (MOBİL DAHİL) */
        #background-leaves-pattern {
            position: fixed;
            top: 0; left: 0; right: 0; bottom: 0;
            background-image: url('https://www.toptal.com/designers/subtlepatterns/uploads/leaves.png');
            background-repeat: repeat;
            background-color: #fdfaf6;
            z-index: -2;
            pointer-events: none;
            opacity: 0.6;
        }
        @media (max-width: 768px) {
            #background-leaves-pattern { opacity: 0.9 !important; }
        }

        #falling-leaves-container {
            position: fixed; top: 0; left: 0; right: 0; bottom: 0;
            pointer-events: none; z-index: -1; overflow: hidden;
        }

        h1, h2, h3 { font-family: 'Playfair Display', serif; }
        .handwriting { font-family: 'Dancing Script', cursive; }
        .font-forte-alternative { font-family: 'Dancing Script', cursive; }
        .font-poor-richard-alternative { font-family: 'Cormorant Garamond', serif; }
        .text-shadow { text-shadow: 2px 2px 4px rgba(0,0,0,0.6); }

        @keyframes heartbeat {
            0% { transform: scale(1); }
            50% { transform: scale(1.1); }
            100% { transform: scale(1); }
        }
        .heartbeat { animation: heartbeat 1.5s infinite; }

        #main-title { font-size: 3rem !important; line-height: 1.2 !important; }
        @media (min-width: 768px) { #main-title { font-size: 4rem !important; } }
        main h3:not(#ilk-adim-baslik) { font-size: 1.5rem !important; line-height: 1.3 !important; }
        @media (min-width: 768px) { main h3:not(#ilk-adim-baslik) { font-size: 2rem !important; } }
        #ilk-adim-baslik { font-size: 1.5rem !important; line-height: 1.4 !important; }
        @media (min-width: 768px) { #ilk-adim-baslik { font-size: 1.75rem !important; } }
        header, #main-title-section { border:none!important; box-shadow:none!important; }

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
        .timeline-content {
            padding: 20px 30px; background: rgba(255, 255, 255, 0.95); border-radius: 12px;
            box-shadow: 0 8px 16px rgba(0, 0, 0, 0.1); border-left: 4px solid #10b981; position: relative; overflow: hidden; transition: all 0.4s ease;
        }
        .timeline-content::before { content: ''; position: absolute; top: 0; left: 0; right: 0; height: 4px; background: linear-gradient(to right, transparent, #ef4444, transparent); transform: scaleX(0); transition: transform 0.6s ease; }
        .timeline-content.animate::before { transform: scaleX(1); }
        .timeline-content:hover { transform: translateY(-5px) scale(1.02); box-shadow: 0 16px 32px rgba(16, 185, 129, 0.2); }
        .timeline-content h4 { margin-bottom: 8px; color: #dc2626; font-family: 'Dancing Script', cursive; font-size: 1.5rem; position: relative; }
        .timeline-content h4::after { content: 'heart'; position: absolute; right: -20px; top: 0; opacity: 0; transition: opacity 0.3s ease; }
        .timeline-content:hover h4::after { opacity: 1; }
        .timeline-content p { color: #6b7280; font-style: italic; line-height: 1.6; }
        .timeline-icon { position: absolute; top: -15px; left: 20px; background: white; border-radius: 50%; width: 40px; height: 40px; display: flex; align-items: center; justify-content: center; box-shadow: 0 4px 8px rgba(0, 0, 0, 0.1); font-size: 1.2rem; color: #ef4444; z-index: 3; transform: rotate(0deg); transition: transform 0.6s ease; }
        .timeline-item.animate .timeline-icon { transform: rotate(360deg); }
        @media (max-width: 600px) {
            .timeline-container::after { left: 31px; }
            .timeline-item { width: 100%; padding-left: 70px; padding-right: 25px; }
            .timeline-item.right { left: 0 !important; }
            .timeline-content { padding: 15px 20px; }
        }

        /* FOTOĞRAF GALERİSİ */
        .photo-container { position:relative; overflow:hidden; border-radius:0.5rem; box-shadow:0 4px 6px rgba(0,0,0,0.1); aspect-ratio:1/1; }
        .gallery-thumbnail { transition:transform .3s ease-in-out; }
        .group:hover .gallery-thumbnail { transform:scale(1.1); }
        .photo-note { position:absolute; bottom:0; left:0; right:0; color:white; padding:0.5rem 0.75rem; font-size:0.75rem; text-align:center; line-height:1.2; text-shadow:1px 1px 3px rgba(0,0,0,0.9); }
        .photo-number { position:absolute; bottom:0.5rem; right:0.75rem; color:white; font-size:1rem; font-weight:bold; text-shadow:1px 1px 3px rgba(0,0,0,0.9); opacity:0; transition:opacity .3s ease-in-out; }
        .group:hover .photo-number { opacity:1; }
        .photo-container.no-note .photo-note { display:none; }
        .travel-folder { background:#f0fdf4; border:1px solid #a7f3d0; border-radius:0.5rem; padding:1rem; text-align:center; transition:transform .2s ease-in-out,box-shadow .2s ease-in-out; }
        .travel-folder:hover { transform:translateY(-5px); box-shadow:0 6px 12px rgba(0,0,0,0.1); }
        .fade-in-on-scroll { opacity:0; transform:translateY(30px); transition:opacity .8s cubic-bezier(.25,.46,.45,.94),transform .8s cubic-bezier(.25,.46,.45,.94); }
        .fade-in-on-scroll.visible { opacity:1; transform:translateY(0); }

        /* ŞİİR ANIMASYONU */
        .poem-container { max-width: 90%; margin: 0 auto; padding: 2rem 0; line-height: 2.3; font-size: 1.15rem; font-style: italic; color: #1f2937; text-align: center; position: relative; background: linear-gradient(135deg, rgba(253, 250, 246, 0.9) 0%, rgba(255, 255, 255, 0.95) 100%); border-radius: 12px; padding: 2rem; box-shadow: 0 8px 32px rgba(0, 0, 0, 0.1); overflow: hidden; }
        .poem-line { opacity: 0; transform: translateY(-30px) scale(0.95); display: block; position: relative; margin: 0.2rem 0; padding: 0.5rem; border-radius: 8px; font-family: 'Cormorant Garamond', serif; transition: all 0.4s cubic-bezier(0.25, 0.46, 0.45, 0.94); }
        .poem-line.visible { opacity: 1; transform: translateY(0) scale(1); animation: fadeInDown 0.8s ease-out forwards; }
        @keyframes fadeInDown { to { opacity: 1; transform: translateY(0) scale(1); } }
        .poem-container:hover .poem-line { color: #6b7280; font-weight: 300; font-size: 1.05rem; }
        .poem-container .poem-line:hover { color: #dc2626 !important; font-weight: 600 !important; font-size: 1.25rem !important; transform: translateY(-5px) scale(1.08) !important; text-shadow: 0 4px 8px rgba(220, 38, 38, 0.3); background: rgba(220, 38, 38, 0.05); box-shadow: 0 4px 12px rgba(220, 38, 38, 0.15); z-index: 10; }
        .poem-container:hover .poem-line:not(:hover) { opacity: 0.7; filter: blur(0.3px); transform: translateY(2px) scale(0.98); }
        .poem-line:nth-child(8), .poem-line:nth-child(9), .poem-line:nth-child(10) { font-weight: 600 !important; color: #dc2626 !important; }
        .poem-container::before { content: ''; position: absolute; top: 0; left: 0; right: 0; height: 3px; background: linear-gradient(90deg, transparent, #dc2626, transparent); transform: scaleX(0); transition: transform 0.6s ease; }
        .poem-container:hover::before { transform: scaleX(1); }
        @media (max-width: 768px) { .poem-container { font-size: 1rem; line-height: 1.8; padding: 1rem; } .poem-line:hover { font-size: 1.15rem !important; transform: translateY(-3px) scale(1.05) !important; } }

        /* YAPRAKLAR */
        .leaf-svg {
            position: absolute; width: 32px; height: 44px; opacity: 0.9;
            animation: fall linear infinite; transform-origin: center;
            filter: drop-shadow(0 3px 6px rgba(0,0,0,0.3));
        }
        @keyframes fall {
            0% { transform: translateY(-120px) rotate(0deg) scale(1); opacity: 0; }
            8% { opacity: 0.9; }
            30% { transform: translateY(30vh) translateX(15px) rotate(180deg) scale(0.95); }
            50% { transform: translateY(50vh) translateX(-20px) rotate(540deg) scale(0.9); }
            70% { transform: translateY(70vh) translateX(25px) rotate(800deg) scale(0.85); }
            92% { opacity: 0.9; }
            100% { transform: translateY(110vh) translateX(-15px) rotate(1080deg) scale(0.6); opacity: 0; }
        }
        .leaf-svg .leaf-inner { fill: currentColor; }
        .leaf-svg .leaf-outer { fill: white; opacity: 0.95; }
        .leaf-svg.autumn-1 { color: #f59e0b; }
        .leaf-svg.autumn-2 { color: #ef4444; }
        .leaf-svg.autumn-3 { color: #facc15; }
        .leaf-svg.autumn-4 { color: #92400e; }
        .leaf-svg.autumn-5 { color: #84cc16; }
        .leaf-svg.autumn-6 { color: #fb923c; }
        .leaf-svg.autumn-7 { color: #dc2626; }
        .leaf-svg.autumn-8 { color: #f97316; }
        .leaf-svg.autumn-9 { color: #22c55e; }
        .leaf-svg.autumn-10 { color: #16a34a; }
    </style>
</head>
<body class="text-black">
    <!-- ARKA PLAN YAPRAK DESENİ -->
    <div id="background-leaves-pattern"></div>

    <!-- DÜŞEN YAPRAKLAR -->
    <div id="falling-leaves-container"></div>

    <header class="py-6 text-center bg-white/70 backdrop-blur-lg sticky top-0 z-20 overflow-hidden">
        <div class="relative">
            <a href="#countdown-section" title="Geri Sayım"
               class="absolute top-1/2 -translate-y-1/2 right-4 text-green-600 hover:text-green-800 transition-colors z-20 text-center">
                <i class="fas fa-hourglass-start fa-2x"></i>
                <div id="header-countdown" class="hidden text-[10px] font-semibold tracking-tight leading-tight mt-1">
                    <span id="header-days">0</span>g <span id="header-hours">0</span>s <span id="header-minutes">0</span>d
                </div>
            </a>
            <div class="absolute inset-0 flex items-center justify-center z-0" aria-hidden="true">
                <i class="fas fa-infinity text-[10rem] text-gray-200 opacity-70 blur-sm"></i>
            </div>
            <div class="relative z-10">
                <h1 class="text-4xl md:text-5xl font-bold text-green-600 flex items-center justify-center space-x-4">
                    <span>Arzu</span><i class="fas fa-heart text-red-500 text-3xl heartbeat"></i><span>Ersin</span>
                </h1>
                <p class="text-lg text-red-600 mt-1">Bizim Yolculuğumuz</p>
            </div>
        </div>
    </header>

    <section id="main-title-section" class="py-16 text-center">
        <h2 id="main-title" class="font-bold handwriting text-green-600">O Güzel Sonbahar</h2>
        <p class="text-xl md:text-2xl mt-2 text-red-600 font-bold">27 Eylül 2025</p>
        <p class="text-lg mt-1 text-red-600 italic font-bold">Zamanın durduğu an</p>
    </section>

    <main class="container mx-auto px-6 pb-12">
        <!-- İLK ADIM -->
        <section class="max-w-3xl mx-auto my-12 text-center bg-white/80 backdrop-blur-sm p-8 rounded-lg shadow-lg">
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
        <section class="my-16 max-w-3xl mx-auto p-8 bg-white/80 backdrop-blur-sm rounded-lg shadow-lg text-center">
            <h3 class="font-bold text-center text-red-600 mb-6 handwriting font-forte-alternative">Sonbahar</h3>
            <div class="poem-container">
                <div class="poem-line font-semibold italic text-black" data-delay="0.2">Çiçekli badem ağaçlarını unut.</div>
                <div class="poem-line font-semibold italic text-black" data-delay="0.4">değmez,</div>
                <div class="poem-line font-semibold italic text-black" data-delay="0.6">bu bahiste</div>
                <div class="poem-line font-semibold italic text-black" data-delay="0.8">geri gelmesi mümkün olmayan hatırlanmamalı.</div>
                <div class="poem-line font-semibold italic text-black" data-delay="1.0">ıslak saçlarını güneşte kurut</div>
                <div class="poem-line font-semibold italic text-black" data-delay="1.2">olgun meyvelerin baygınlığıyla parıldasın</div>
                <div class="poem-line font-semibold italic text-black" data-delay="1.4">nemli, ağır kızıltılar…</div>
                <div class="poem-line font-semibold italic text-black" data-delay="1.7">sevgilim, sevgilim,</div>
                <div class="poem-line font-semibold italic text-black" data-delay="2.0">mevsim</div>
                <div class="poem-line font-semibold italic text-black" data-delay="2.3">sonbahar…</div>
            </div>
            <p class="text-right text-red-600 font-semibold mt-6 pr-4 font-forte-alternative">- Nazım Hikmet</p>
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
                        <p class="font-semibold italic text-black">
                            Yaprakların dans ettiği o sonbahar gününde, gözlerinle tanıştım seninle...
                        </p>
                    </div>
                </div>
                <div class="timeline-item right">
                    <div class="timeline-icon"><i class="fas fa-infinity heartbeat"></i></div>
                    <div class="timeline-content">
                        <h4>Sonsuza Dek...</h4>
                        <p class="font-semibold italic text-black">
                            Yemin ettik birbirimize, yıldızlar şahitliğinde...
                        </p>
                    </div>
                </div>
            </div>
        </section>

        <!-- GERİ SAYIM -->
        <section id="countdown-section" class="my-16 max-w-3xl mx-auto p-8 bg-white/80 backdrop-blur-sm rounded-lg shadow-lg text-center">
            <h3 class="font-bold text-center text-red-600 mb-6 font-forte-alternative">Büyük Güne Geri Sayım</h3>
            <div id="countdown-timer" class="hidden grid grid-cols-2 md:grid-cols-4 gap-4 text-center">
                <div><div id="days" class="text-4xl font-bold text-green-500">0</div><span class="text-black">Gün</span></div>
                <div><div id="hours" class="text-4xl font-bold text-green-500">0</div><span class="text-black">Saat</span></div>
                <div><div id="minutes" class="text-4xl font-bold text-green-500">0</div><span class="text-black">Dakika</span></div>
                <div><div id="seconds" class="text-4xl font-bold text-green-500">0</div><span class="text-black">Saniye</span></div>
            </div>
            <div id="countdown-placeholder" class="my-4">
                <div class="text-8xl text-red-500 heartbeat"><i class="fas fa-infinity"></i></div>
                <p class="text-center text-black font-semibold italic text-lg mt-4">
                    Sonsuzluğa giden yolculuğumuzun tarihi belli olduğunda...
                </p>
            </div>
        </section>

        <!-- Hayal Defterimiz -->
        <section class="my-16 max-w-3xl mx-auto p-8 bg-white/80 backdrop-blur-sm rounded-lg shadow-lg fade-in-on-scroll">
            <h3 class="font-bold text-center text-red-600 mb-6 handwriting">Hayal Defterimiz</h3>
            <p class="text-center text-black font-semibold italic text-lg mt-4 mb-8">
                Birlikte kurduğumuz hayaller, geleceğe dair ektiğimiz tohumlar...
            </p>
        </section>

        <!-- Bizim Şarkımız -->
        <section class="my-16 max-w-3xl mx-auto p-8 bg-white/80 backdrop-blur-sm rounded-lg shadow-lg text-center">
            <h3 class="font-bold text-center text-red-600 mb-6 handwriting">Bizim Şarkımız</h3>
            <div class="flex items-center justify-center p-6 bg-green-50 rounded-lg">
                <div class="text-4xl text-red-600"><i class="fas fa-music"></i></div>
            </div>
        </section>

        <!-- Seyahatlerimiz -->
        <section class="my-16 max-w-5xl mx-auto p-4 md:p-8 text-center">
            <h3 class="font-bold text-center text-red-600 mb-4 handwriting">Seyahatlerimiz</h3>
            <p class="text-center text-black font-semibold italic">
                Birlikte keşfettiğimiz yerler...
            </p>
            <div class="mt-8 text-center">
                <button id="toggle-travel-btn"
                        class="inline-flex items-center justify-center py-2 px-6 border border-red-600 shadow-sm text-sm font-medium rounded-md text-red-600 bg-white hover:bg-red-50 focus:outline-none focus:ring-2 focus:ring-offset-2 focus:ring-red-500 transition-colors">
                    <span id="travel-toggle-text">Seyahatlerimizi Gör</span>
                    <i id="travel-toggle-icon" class="fas fa-chevron-down ml-2 transition-transform"></i>
                </button>
            </div>
            <div id="travel-wrapper" class="hidden mt-8">
                <div class="grid grid-cols-1 sm:grid-cols-2 md:grid-cols-3 gap-6">
                    <div class="travel-folder">
                        <div class="text-4xl text-green-500 mb-3"><i class="fas fa-map-marked-alt"></i></div>
                        <h4 class="font-semibold text-lg text-black mb-1">Kapadokya Gezisi</h4>
                        <p class="text-sm text-black italic mt-2">Fotoğraflar buraya eklenecek...</p>
                    </div>
                    <div class="travel-folder">
                        <div class="text-4xl text-green-500 mb-3"><i class="fas fa-map-marked-alt"></i></div>
                        <h4 class="font-semibold text-lg text-black mb-1">Ege Sahilleri</h4>
                        <p class="text-sm text-black italic mt-2">Fotoğraflar buraya eklenecek...</p>
                    </div>
                    <div class="travel-folder">
                        <div class="text-4xl text-green-500 mb-3"><i class="fas fa-ship"></i></div>
                        <h4 class="font-semibold text-lg text-black mb-1">Akdeniz Turu</h4>
                        <p class="text-sm text-black italic mt-2">Fotoğraflar buraya eklenecek...</p>
                    </div>
                </div>
            </div>
        </section>

        <!-- FOTOĞRAF GALERİSİ - LAZY LOADING EKLENDİ -->
        <section class="my-16 max-w-5xl mx-auto p-4 md:p-8 text-center">
            <h3 class="font-bold text-center text-red-600 mb-4 handwriting">Fotoğraf Galerimiz</h3>
            <p class="text-center text-black font-semibold italic">
              İşte yolculuğumuzda biriktirdiğimiz anlardan ilk kareler...
              Bu galeri, zamanla daha nice güzel anıyla dolacak.
            </p>
            <div class="mt-8 text-center">
                <button id="toggle-gallery-btn"
                        class="inline-flex items-center justify-center py-2 px-6 border border-red-600 shadow-sm text-sm font-medium rounded-md text-red-600 bg-white hover:bg-red-50 focus:outline-none focus:ring-2 focus:ring-offset-2 focus:ring-red-500 transition-colors">
                    <span id="gallery-toggle-text">Fotoğraf Galerisini Gör</span>
                    <i id="gallery-toggle-icon" class="fas fa-chevron-down ml-2 transition-transform"></i>
                </button>
            </div>
            <div id="gallery-wrapper" class="hidden mt-8">
                <div class="grid grid-cols-3 sm:grid-cols-4 md:grid-cols-5 lg:grid-cols-6 gap-1" id="gallery-grid">
                    <div class="photo-container group cursor-pointer">
                        <img loading="lazy" src="https://i.imgur.com/wf9Xhs9.jpg" alt="Anı fotoğrafı 6" class="gallery-thumbnail w-full h-full object-cover">
                        <span class="photo-number opacity-0 group-hover:opacity-100">6</span>
                        <div class="photo-note">Lunapark Anısı</div>
                    </div>
                    <div class="photo-container group cursor-pointer">
                        <img loading="lazy" src="https://i.imgur.com/G26zsUc.jpg" alt="Anı fotoğrafı 5" class="gallery-thumbnail w-full h-full object-cover">
                        <span class="photo-number opacity-0 group-hover:opacity-100">5</span>
                        <div class="photo-note">Beşiktaş</div>
                    </div>
                    <div class="photo-container group cursor-pointer">
                        <img loading="lazy" src="https://i.imgur.com/PR2hWYz.jpg" alt="Anı fotoğrafı 4" class="gallery-thumbnail w-full h-full object-cover">
                        <span class="photo-number opacity-0 group-hover:opacity-100">4</span>
                        <div class="photo-note">Çamlıca Kahvaltımız</div>
                    </div>
                    <div class="photo-container group cursor-pointer">
                        <img loading="lazy" src="https://i.imgur.com/40oguJF.jpg" alt="Anı fotoğrafı 3" class="gallery-thumbnail w-full h-full object-cover">
                        <span class="photo-number opacity-0 group-hover:opacity-100">3</span>
                        <div class="photo-note">Çamlıca Kahvaltımız</div>
                    </div>
                    <div class="photo-container group cursor-pointer">
                        <img loading="lazy" src="https://i.imgur.com/KZpZnaa.jpg" alt="Anı fotoğrafı 2" class="gallery-thumbnail w-full h-full object-cover">
                        <span class="photo-number opacity-0 group-hover:opacity-100">2</span>
                        <div class="photo-note">Dünya Güzelim</div>
                    </div>
                    <div class="photo-container group cursor-pointer no-note">
                        <img loading="lazy" src="https://i.imgur.com/WnEibNN.jpg" alt="Anı fotoğrafı 1" class="gallery-thumbnail w-full h-full object-cover">
                        <span class="photo-number opacity-0 group-hover:opacity-100">1</span>
                    </div>
                </div>
            </div>
        </section>

        <!-- VİDEO GALERİSİ (ZATEN LAZY LOADING VAR) -->
        <section class="my-16 max-w-5xl mx-auto p-4 md:p-8 text-center">
            <h3 class="font-bold text-center text-red-600 mb-4 handwriting">Video Galerimiz</h3>
            <p class="text-center text-black font-semibold">
                Bazı duyguları kelimelerle anlatmak yetmez...
            </p>
            <div class="mt-8 text-center">
                <button id="toggle-video-gallery-btn"
                        class="inline-flex items-center justify-center py-2 px-6 border border-red-600 shadow-sm text-sm font-medium rounded-md text-red-600 bg-white hover:bg-red-50 focus:outline-none focus:ring-2 focus:ring-offset-2 focus:ring-red-500 transition-colors">
                    <span id="video-gallery-toggle-text">Video Galerisini Gör</span>
                    <i id="video-gallery-toggle-icon" class="fas fa-chevron-down ml-2 transition-transform"></i>
                </button>
            </div>
            <div id="video-gallery-wrapper" class="hidden mt-8">
                <div class="grid grid-cols-3 sm:grid-cols-4 md:grid-cols-5 lg:grid-cols-6 gap-1" id="video-grid">
                    <div class="photo-container group cursor-pointer aspect-square" data-youtube-id="ChFa2GJ4e4U">
                        <img loading="lazy" src="https://img.youtube.com/vi/ChFa2GJ4e4U/maxresdefault.jpg" alt="Video thumbnail" class="w-full h-full object-cover gallery-thumbnail">
                        <div class="absolute inset-0 flex items-center justify-center bg-black bg-opacity-40">
                            <i class="far fa-play-circle text-white text-5xl opacity-80 group-hover:opacity-100 transition-opacity"></i>
                        </div>
                        <span class="photo-number opacity-0 group-hover:opacity-100">5</span>
                        <div class="photo-note">Beşiktaş</div>
                    </div>
                    <div class="photo-container group cursor-pointer aspect-square" data-youtube-id="aim5II5vYpU">
                        <img loading="lazy" src="https://img.youtube.com/vi/aim5II5vYpU/maxresdefault.jpg" alt="Video thumbnail" class="w-full h-full object-cover gallery-thumbnail">
                        <div class="absolute inset-0 flex items-center justify-center bg-black bg-opacity-40">
                            <i class="far fa-play-circle text-white text-5xl opacity-80 group-hover:opacity-100 transition-opacity"></i>
                        </div>
                        <span class="photo-number opacity-0 group-hover:opacity-100">4</span>
                        <div class="photo-note">Üsküdar</div>
                    </div>
                    <div class="photo-container group cursor-pointer aspect-square" data-youtube-id="uY6ZrwkbLjc">
                        <img loading="lazy" src="https://img.youtube.com/vi/uY6ZrwkbLjc/maxresdefault.jpg" alt="Video thumbnail" class="w-full h-full object-cover gallery-thumbnail">
                        <div class="absolute inset-0 flex items-center justify-center bg-black bg-opacity-40">
                            <i class="far fa-play-circle text-white text-5xl opacity-80 group-hover:opacity-100 transition-opacity"></i>
                        </div>
                        <span class="photo-number opacity-0 group-hover:opacity-100">3</span>
                        <div class="photo-note">Lunapark</div>
                    </div>
                    <div class="photo-container group cursor-pointer aspect-square" data-youtube-id="19aKq8FtYP8">
                        <img loading="lazy" src="https://img.youtube.com/vi/19aKq8FtYP8/maxresdefault.jpg" alt="Video thumbnail" class="w-full h-full object-cover gallery-thumbnail">
                        <div class="absolute inset-0 flex items-center justify-center bg-black bg-opacity-40">
                            <i class="far fa-play-circle text-white text-5xl opacity-80 group-hover:opacity-100 transition-opacity"></i>
                        </div>
                        <span class="photo-number opacity-0 group-hover:opacity-100">2</span>
                        <div class="photo-note">Beşiktaş</div>
                    </div>
                    <div class="photo-container group cursor-pointer aspect-square" data-youtube-id="J466tfX1jzk">
                        <img loading="lazy" src="https://img.youtube.com/vi/J466tfX1jzk/maxresdefault.jpg" alt="Video thumbnail" class="w-full h-full object-cover gallery-thumbnail">
                        <div class="absolute inset-0 flex items-center justify-center bg-black bg-opacity-40">
                            <i class="far fa-play-circle text-white text-5xl opacity-80 group-hover:opacity-100 transition-opacity"></i>
                        </div>
                        <span class="photo-number opacity-0 group-hover:opacity-100">1</span>
                        <div class="photo-note">Ev</div>
                    </div>
                </div>
            </div>
        </section>

        <!-- Teşekkür -->
        <section class="my-16 max-w-3xl mx-auto p-8 bg-white/80 backdrop-blur-sm rounded-lg shadow-lg">
            <h3 class="font-bold text-center text-red-600 mb-6">Teşekkür</h3>
            <p class="text-center text-black text-lg italic mt-4">
                Bu mutlu yolculuğumuzda yanımızda olan herkese sonsuz teşekkürler.
            </p>
            <div class="mt-8 space-y-4">
                <p class="text-center text-black font-semibold">Bizi biz yapan, sevgileriyle her zaman en büyük destekçimiz olan canımız ailelerimize...</p>
                <p class="text-center text-black font-semibold">İyi günde, kötü günde her anımızda yanımızda olan değerli dostlarımıza...</p>
            </div>
        </section>

        <!-- Dilek Kutusu -->
        <section class="my-16 max-w-3xl mx-auto p-8 bg-white/80 backdrop-blur-sm rounded-lg shadow-lg">
            <h3 class="font-bold text-center text-red-600 mb-6">Bizim İçin Bir Dilek Bırakın</h3>
            <form id="wish-form" action="https://formsubmit.co/arzuersin2025@gmail.com" method="POST" class="space-y-4">
                <input type="hidden" name="_subject" value="Arzu & Ersin Web Sitenizden Yeni Dilek!">
                <input type="hidden" name="_honey" style="display:none">
                <input type="hidden" name="_captcha" value="false">
                <div>
                    <label for="name" class="block text-sm font-medium text-red-600">Adınız</label>
                    <input type="text" name="name" id="name" class="mt-1 block w-full px-3 py-2 bg-white border border-slate-300 rounded-md shadow-sm placeholder-slate-400 focus:outline-none focus:ring-green-500 focus:border-green-500 sm:text-sm" placeholder="Adınız ve Soyadınız" required>
                </div>
                <div>
                    <label for="message" class="block text-sm font-medium text-red-600">Dileğiniz</label>
                    <textarea id="message" name="message" rows="4" class="mt-1 block w-full px-3 py-2 bg-white border border-slate-300 rounded-md shadow-sm placeholder-slate-400 focus:outline-none focus:ring-green-500 focus:border-green-500 sm:text-sm" placeholder="Bizim için güzel bir dilek..." required></textarea>
                </div>
                <div class="pt-4 border-t border-slate-200">
                    <p class="text-sm text-black mb-2 text-center">Teşekkür için lütfen e-posta ya da telefon bırakın.</p>
                    <label for="contact" class="block text-sm font-medium text-red-600">E-posta ya da Telefon</label>
                    <input type="text" name="Iletisim" id="contact" class="mt-1 block w-full px-3 py-2 bg-white border border-slate-300 rounded-md shadow-sm placeholder-slate-400 focus:outline-none focus:ring-green-500 focus:border-green-500 sm:text-sm" placeholder="ornek@mail.com veya 05XX XXX XX XX">
                    <p id="contact-error" class="text-red-500 text-sm mt-2 text-center hidden">Lütfen e-posta veya telefon girin.</p>
                </div>
                <div class="text-center pt-4">
                    <button type="submit" class="inline-flex justify-center items-center py-2 px-6 border border-transparent shadow-sm text-sm font-medium rounded-md text-white bg-green-600 hover:bg-green-700 focus:outline-none focus:ring-2 focus:ring-offset-2 focus:ring-green-500 transition-colors">
                        <i class="fas fa-heart mr-2 heartbeat"></i> Dileğini Gönder
                    </button>
                </div>
            </form>
        </section>
    </main>

    <footer class="text-center py-8 mt-12 bg-white/50">
        <p class="text-black flex items-center justify-center space-x-2">
            <span>Bu hikaye</span><i class="fas fa-infinity text-red-500"></i><span>kadar devam edecek...</span>
        </p>
        <p class="text-sm text-black mt-2">Arzu & Ersin</p>
    </footer>

    <!-- Modallar -->
    <div id="image-modal" class="fixed inset-0 bg-black bg-opacity-80 hidden items-center justify-center z-50 p-4">
        <span id="close-modal" class="absolute top-4 right-6 text-white text-5xl font-bold cursor-pointer hover:text-gray-300 transition-colors">×</span>
        <img id="modal-image" src="" alt="Büyütülmüş Fotoğraf" class="max-w-[90vw] max-h-[90vh] rounded-lg shadow-lg">
        <span id="prev-photo" class="absolute top-1/2 left-4 -translate-y-1/2 text-white text-6xl font-bold cursor-pointer hover:text-gray-300 transition-colors select-none">&lt;</span>
        <span id="next-photo" class="absolute top-1/2 right-4 -translate-y-1/2 text-white text-6xl font-bold cursor-pointer hover:text-gray-300 transition-colors select-none">&gt;</span>
    </div>
    <div id="video-modal" class="fixed inset-0 bg-black bg-opacity-80 hidden items-center justify-center z-50 p-4">
        <span id="close-video-modal" class="absolute top-4 right-6 text-white text-5xl font-bold cursor-pointer hover:text-gray-300 transition-colors">×</span>
        <div class="aspect-video w-full max-w-4xl">
            <iframe id="modal-video-iframe" class="w-full h-full" src="" title="YouTube video player" frameborder="0"
                    allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture; web-share" allowfullscreen></iframe>
        </div>
    </div>

    <script>
    (() => {
        'use strict';
        const COUNTDOWN_DATE = "";

        const leafSVG = `
        <svg viewBox="0 0 100 140" class="w-full h-full" preserveAspectRatio="xMidYMid meet">
          <path class="leaf-outer" d="M50 10 C30 15, 20 35, 18 55 C16 75, 25 95, 35 115 C45 130, 48 135, 50 138 C52 135, 55 130, 65 115 C75 95, 84 75, 82 55 C80 35, 70 15, 50 10 Z" />
          <path class="leaf-inner" d="M50 15 C33 20, 25 38, 23 55 C21 72, 28 88, 36 108 C44 125, 48 132, 50 135 C52 132, 56 125, 64 108 C72 88, 79 72, 77 55 C75 38, 67 20, 50 15 Z" />
          <path d="M50 15 Q50 70 48 135" stroke="#fff" stroke-width="2.5" opacity="0.5" fill="none"/>
          <path d="M50 30 Q35 40 28 48 M50 55 Q32 65 25 75 M50 80 Q30 90 23 105" stroke="#fff" stroke-width="1.8" opacity="0.4" fill="none"/>
          <path d="M50 30 Q65 40 72 48 M50 55 Q68 65 75 75 M50 80 Q70 90 77 105" stroke="#fff" stroke-width="1.8" opacity="0.4" fill="none"/>
          <path d="M25 50 Q23 48 25 46 M30 70 Q28 68 30 66 M35 90 Q33 88 35 86 M75 50 Q77 48 75 46 M70 70 Q72 68 70 66 M65 90 Q67 88 65 86" stroke="#fff" stroke-width="1" opacity="0.3" fill="none"/>
        </svg>`;
        const leafColors = ['autumn-1','autumn-2','autumn-3','autumn-4','autumn-5','autumn-6','autumn-7','autumn-8','autumn-9','autumn-10'];
        const leafContainer = document.getElementById('falling-leaves-container');
        const leafCount = 7;
        for (let i = 0; i < leafCount; i++) {
            const leaf = document.createElement('div');
            const colorClass = leafColors[Math.floor(Math.random() * leafColors.length)];
            leaf.className = `leaf-svg ${colorClass}`;
            leaf.style.left = Math.random() * 100 + 'vw';
            const scale = 0.5 + Math.random() * 0.9;
            leaf.style.transform = `scale(${scale}) rotate(${Math.random() * 360}deg)`;
            const duration = 18 + Math.random() * 12;
            leaf.style.animationDuration = duration + 's';
            leaf.style.animationDelay = Math.random() * 10 + 's';
            leaf.innerHTML = leafSVG;
            leafContainer.appendChild(leaf);
        }

        const toggleBtn = (btnId, wrapperId, iconId, textId, openTxt, closeTxt) => {
            const btn = document.getElementById(btnId);
            const wrapper = document.getElementById(wrapperId);
            const icon = document.getElementById(iconId);
            const txt = document.getElementById(textId);
            if (!btn) return;
            btn.addEventListener('click', () => {
                const hidden = wrapper.classList.toggle('hidden');
                icon.classList.toggle('rotate-180', !hidden);
                txt.textContent = hidden ? openTxt : closeTxt;
            });
        };
        toggleBtn('toggle-gallery-btn','gallery-wrapper','gallery-toggle-icon','gallery-toggle-text','Fotoğraf Galerisini Gör','Galeriyi Gizle');
        toggleBtn('toggle-video-gallery-btn','video-gallery-wrapper','video-gallery-toggle-icon','video-gallery-toggle-text','Video Galerisini Gör','Galeriyi Gizle');
        toggleBtn('toggle-travel-btn','travel-wrapper','travel-toggle-icon','travel-toggle-text','Seyahatlerimizi Gör','Seyahatleri Gizle');

        const galleryGrid = document.getElementById('gallery-grid');
        const imgSelector = '.gallery-thumbnail';
        let imgs = [], curIdx = 0;
        const refreshImgs = () => { imgs = Array.from(galleryGrid.querySelectorAll(imgSelector)).map(i => i.src); };
        const openImg = idx => {
            if (!imgs.length) refreshImgs();
            curIdx = (idx + imgs.length) % imgs.length;
            document.getElementById('modal-image').src = imgs[curIdx];
            document.getElementById('image-modal').classList.replace('hidden','flex');
        };
        const closeImg = () => {
            const m = document.getElementById('image-modal');
            m.classList.replace('flex','hidden');
            document.getElementById('modal-image').src = '';
        };
        const nextImg = () => { curIdx = (curIdx + 1) % imgs.length; document.getElementById('modal-image').src = imgs[curIdx]; };
        const prevImg = () => { curIdx = (curIdx - 1 + imgs.length) % imgs.length; document.getElementById('modal-image').src = imgs[curIdx]; };
        const attachImgEvents = () => {
            refreshImgs();
            galleryGrid.querySelectorAll(imgSelector).forEach((el,i) => { el.onclick = () => openImg(i); });
        };
        attachImgEvents();
        document.getElementById('close-modal').onclick = closeImg;
        document.getElementById('prev-photo').onclick = e => { e.stopPropagation(); prevImg(); };
        document.getElementById('next-photo').onclick = e => { e.stopPropagation(); nextImg(); };
        document.getElementById('image-modal').onclick = e => { if (e.target === e.currentTarget) closeImg(); };

        const videoModal = document.getElementById('video-modal');
        const iframe = document.getElementById('modal-video-iframe');
        document.getElementById('video-grid').addEventListener('click', e => {
            const el = e.target.closest('[data-youtube-id]');
            if (el) {
                iframe.src = `https://www.youtube-nocookie.com/embed/${el.dataset.youtubeId}?autoplay=1&rel=0`;
                videoModal.classList.replace('hidden','flex');
            }
        });
        document.getElementById('close-video-modal').onclick = () => { iframe.src = ''; videoModal.classList.replace('flex','hidden'); };
        videoModal.onclick = e => { if (e.target === videoModal) { iframe.src=''; videoModal.classList.replace('flex','hidden'); } };

        document.addEventListener('keydown', e => {
            if (e.key === 'Escape') { closeImg(); iframe.src=''; videoModal.classList.replace('flex','hidden'); }
            if (e.key === 'ArrowRight' && !document.getElementById('image-modal').classList.contains('hidden')) nextImg();
            if (e.key === 'ArrowLeft' && !document.getElementById('image-modal').classList.contains('hidden')) prevImg();
        });

        document.getElementById('wish-form')?.addEventListener('submit', function (ev) {
            const contact = document.getElementById('contact').value.trim();
            const err = document.getElementById('contact-error');
            if (!contact) { ev.preventDefault(); err.classList.remove('hidden'); }
            else err.classList.add('hidden');
        });

        if (COUNTDOWN_DATE) {
            const target = new Date(COUNTDOWN_DATE).getTime();
            const timer = document.getElementById('countdown-timer');
            const placeholder = document.getElementById('countdown-placeholder');
            const header = document.getElementById('header-countdown');
            placeholder.classList.add('hidden'); timer.classList.remove('hidden'); header.classList.remove('hidden');
            const pad = n => n < 10 ? '0'+n : n;
            const update = () => {
                const diff = target - Date.now();
                if (diff <= 0) {
                    clearInterval(intv);
                    timer.innerHTML = '<p class="col-span-full text-xl text-green-600">Ve o güzel gün geldi!</p>';
                    header.innerHTML = 'heart';
                    return;
                }
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
            const intv = setInterval(update,1000);
        }

        const timelineObserver = new IntersectionObserver((entries) => {
            entries.forEach((entry, index) => {
                if (entry.isIntersecting) {
                    setTimeout(() => {
                        entry.target.classList.add('animate');
                        const content = entry.target.querySelector('.timeline-content');
                        if (content) content.classList.add('animate');
                    }, index * 300);
                }
            });
        }, { threshold: 0.3 });
        document.querySelectorAll('.timeline-item').forEach(item => timelineObserver.observe(item));

        const poemObserver = new IntersectionObserver((entries) => {
            entries.forEach(entry => {
                if (entry.isIntersecting) {
                    const delay = parseFloat(entry.target.getAttribute('data-delay')) || 0;
                    setTimeout(() => { entry.target.classList.add('visible'); }, delay * 1000);
                    poemObserver.unobserve(entry.target);
                }
            });
        }, { threshold: 0.6 });
        document.querySelectorAll('.poem-line').forEach(line => poemObserver.observe(line));

        const obs = new IntersectionObserver(entries => {
            entries.forEach(entry => { if (entry.isIntersecting) entry.target.classList.add('visible'); });
        }, {threshold:0.15});
        document.querySelectorAll('.fade-in-on-scroll, .travel-folder').forEach(el => obs.observe(el));
    })();
    </script>
</body>
</html>
