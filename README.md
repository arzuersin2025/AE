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
    <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.5.1/css/all.min.css"
          integrity="sha512-DTOQO9RWCH3ppGqcWaEA1BIZOC6xxalwEsw9c2QQeAIftl+Vegovlnee1c9QX4TctnWMn13TZye+giMm8e2LwA=="
          crossorigin="anonymous" referrerpolicy="no-referrer" />
    <link rel="icon" href="data:image/png;base64,iVBORw0KGgoAAAANSUhEUgAAAAEAAAABCAQAAAC1HAwCAAAAC0lEQVR42mNkYAAAAAYAAjCB0C8AAAAASUVORK5CYII=">

    <!-- Firebase SDK -->
    <script src="https://www.gstatic.com/firebasejs/9.23.0/firebase-app-compat.js"></script>
    <script src="https://www.gstatic.com/firebasejs/9.23.0/firebase-database-compat.js"></script>

    <style>
        html { scroll-behavior: smooth; }
        body {
            font-family: 'Poppins', sans-serif;
            font-weight: 300;
            background-image: url('https://www.toptal.com/designers/subtlepatterns/uploads/leaves.png');
            background-color: #fdfaf6;
        }
        h1, h2, h3 { font-family: 'Playfair Display', serif; }
        .handwriting { font-family: 'Dancing Script', cursive; }
        .font-forte-alternative { font-family: 'Dancing Script', cursive; }
        .font-poor-richard-alternative { font-family: 'Cormorant Garamond', serif; }
        .text-shadow { text-shadow: 2px 2px 4px rgba(0,0,0,0.6); }

        /* KALP ATIŞI */
        @keyframes heartbeat {
            0% { transform: scale(1); }
            50% { transform: scale(1.1); }
            100% { transform: scale(1); }
        }
        .heartbeat { animation: heartbeat 1.5s infinite; }

        /* "O GÜZEL SONBAHAR" */
        #main-title { font-size: 3rem !important; line-height: 1.2 !important; }
        @media (min-width: 768px) { #main-title { font-size: 4rem !important; } }

        /* ANA BAŞLIKLAR */
        main h3:not(#ilk-adim-baslik) { font-size: 1.5rem !important; line-height: 1.3 !important; }
        @media (min-width: 768px) { main h3:not(#ilk-adim-baslik) { font-size: 2rem !important; } }

        /* İLK ADIM */
        #ilk-adim-baslik { font-size: 1.5rem !important; line-height: 1.4 !important; }
        @media (min-width: 768px) { #ilk-adim-baslik { font-size: 1.75rem !important; } }

        header, #main-title-section { border:none!important; box-shadow:none!important; }

        /* TIMELINE */
        .timeline-container { position: relative; max-width: 1200px; margin: 0 auto; padding: 2rem 0; }
        .timeline-container::after {
            content: ''; position: absolute; width: 4px; background: linear-gradient(to bottom, #10b981, #f59e0b, #ef4444);
            top: 0; bottom: 0; left: 50%; margin-left: -2px; border-radius: 2px; z-index: 1;
            transform: scaleY(0); transform-origin: top; animation: drawLine 2s ease-out forwards;
        }
        @keyframes drawLine { to { transform: scaleY(1); } }

        .timeline-item { padding: 10px 40px; position: relative; width: 50%; opacity: 0; transform: translateY(50px) scale(0.9); transition: all 0.8s cubic-bezier(0.25, 0.46, 0.45, 0.94); z-index: 2; }
        .timeline-item.animate { opacity: 1; transform: translateY(0) scale(1); }
        .timeline-item.left { left: 0; }
        .timeline-item.right { left: 50%; }

        .timeline-content {
            padding: 20px 30px; background: rgba(255, 255, 255, 0.95); border-radius: 12px;
            box-shadow: 0 8px 16px rgba(0, 0, 0, 0.1); border-left: 4px solid #10b981; position: relative; overflow: hidden;
            transition: all 0.4s ease;
        }
        .timeline-content::before {
            content: ''; position: absolute; top: 0; left: 0; right: 0; height: 4px;
            background: linear-gradient(to right, transparent, #ef4444, transparent); transform: scaleX(0); transition: transform 0.6s ease;
        }
        .timeline-content.animate::before { transform: scaleX(1); }
        .timeline-content:hover { transform: translateY(-5px) scale(1.02); box-shadow: 0 16px 32px rgba(16, 185, 129, 0.2); }
        .timeline-content h4 { margin-bottom: 8px; color: #dc2626; font-family: 'Dancing Script', cursive; font-size: 1.5rem; }
        .timeline-content p { color: #6b7280; font-style: italic; line-height: 1.6; }

        .timeline-icon {
            position: absolute; top: -15px; left: 20px; background: white; border-radius: 50%; width: 40px; height: 40px;
            display: flex; align-items: center; justify-content: center; box-shadow: 0 4px 8px rgba(0, 0, 0, 0.1);
            font-size: 1.2rem; color: #ef4444; z-index: 3; transform: rotate(0deg); transition: transform 0.6s ease;
        }
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
        .poem-container {
            max-width: 90%; margin: 0 auto; padding: 2rem 0; line-height: 2.3; font-size: 1.15rem; font-style: italic;
            color: #1f2937; text-align: center; position: relative; background: linear-gradient(135deg, rgba(253, 250, 246, 0.9) 0%, rgba(255, 255, 255, 0.95) 100%);
            border-radius: 12px; padding: 2rem; box-shadow: 0 8px 32px rgba(0, 0, 0, 0.1); overflow: hidden;
        }
        .poem-line {
            opacity: 0; transform: translateY(-30px) scale(0.95); display: block; position: relative; margin: 0.2rem 0;
            padding: 0.5rem; border-radius: 8px; font-family: 'Cormorant Garamond', serif;
            transition: all 0.4s cubic-bezier(0.25, 0.46, 0.45, 0.94);
        }
        .poem-line.visible { opacity: 1; transform: translateY(0) scale(1); animation: fadeInDown 0.8s ease-out forwards; }
        @keyframes fadeInDown { to { opacity: 1; transform: translateY(0) scale(1); } }

        .poem-container:hover .poem-line { color: #6b7280; font-weight: 300; font-size: 1.05rem; }
        .poem-container .poem-line:hover {
            color: #dc2626 !important; font-weight: 600 !important; font-size: 1.25rem !important;
            transform: translateY(-5px) scale(1.08) !important; text-shadow: 0 4px 8px rgba(220, 38, 38, 0.3);
            background: rgba(220, 38, 38, 0.05); box-shadow: 0 4px 12px rgba(220, 38, 38, 0.15); z-index: 10;
        }
        .poem-container:hover .poem-line:not(:hover) { opacity: 0.7; filter: blur(0.3px); transform: translateY(2px) scale(0.98); }
        .poem-line:nth-child(8) { font-weight: 500; color: #b91c1c; }
        .poem-line:nth-child(9) { font-style: italic; color: #92400e; }
        .poem-line:nth-child(10) { color: #dc2626; font-weight: 700; font-size: 1.2em; text-shadow: 1px 1px 2px rgba(220, 38, 38, 0.2); }

        .poem-container::before {
            content: ''; position: absolute; top: 0; left: 0; right: 0; height: 3px;
            background: linear-gradient(90deg, transparent, #dc2626, transparent); transform: scaleX(0); transition: transform 0.6s ease;
        }
        .poem-container:hover::before { transform: scaleX(1); }

        @media (max-width: 768px) {
            .poem-container { font-size: 1rem; line-height: 1.8; padding: 1rem; }
            .poem-line:hover { font-size: 1.15rem !important; transform: translateY(-3px) scale(1.05) !important; }
        }

        /* DİLEK PENCERESİ */
        .wish-card {
            background: white; border-radius: 1rem; box-shadow: 0 4px 12px rgba(0,0,0,0.1);
            transition: all 0.3s ease; overflow: hidden;
        }
        .wish-card:hover { transform: translateY(-4px); box-shadow: 0 12px 24px rgba(0,0,0,0.15); }
        .wish-toggle {
            cursor: pointer; padding: 1rem; border-bottom: 1px solid #f0f0f0;
            display: flex; justify-content: space-between; align-items: center;
        }
        .wish-content { padding: 1rem; border-bottom: 1px solid #f0f0f0; }
        .comments-section {
            max-height: 0; overflow: hidden; transition: max-height 0.4s ease, padding 0.4s ease;
        }
        .comments-section.open { max-height: 600px; padding: 1rem; }
        .comment-item {
            background: #f9f9f9; padding: 0.75rem; border-radius: 0.75rem; margin-bottom: 0.75rem; font-size: 0.9rem;
            display: flex; justify-content: space-between; align-items: flex-start;
        }
        .comment-form {
            margin-top: 1rem; display: flex; flex-direction: column; gap: 0.5rem;
        }

        /* SİLME BUTONLARI */
        .delete-btn {
            opacity: 0; transition: opacity 0.3s ease;
        }
        .wish-card:hover .delete-btn,
        .comment-item:hover .delete-btn {
            opacity: 1;
        }
        @media (max-width: 640px) {
            .delete-btn { opacity: 1; }
        }

        /* MODAL */
        #wish-modal .bg-white, #delete-modal .bg-white {
            transition: transform 0.3s ease, opacity 0.3s ease;
        }
    </style>
</head>
<body class="text-black">

<header class="py-6 text-center bg-white/70 backdrop-blur-lg sticky top-0 z-20 overflow-hidden">
    <div class="relative">
        <a href="#countdown-section" class="absolute top-1/2 -translate-y-1/2 right-4 text-green-600 hover:text-green-800">
            <i class="fas fa-hourglass-start fa-2x"></i>
        </a>
        <div class="absolute inset-0 flex items-center justify-center z-0">
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
    <p class="text-xl md:text-2xl mt-2 text-red-600">27 Eylül 2025</p>
    <p class="text-lg mt-1 text-red-600 italic">Zamanın durduğu an</p>
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
            <div class="poem-line" data-delay="0.2">Çiçekli badem ağaçlarını unut.</div>
            <div class="poem-line" data-delay="0.4">değmez,</div>
            <div class="poem-line" data-delay="0.6">bu bahiste</div>
            <div class="poem-line" data-delay="0.8">geri gelmesi mümkün olmayan hatırlanmamalı.</div>
            <div class="poem-line" data-delay="1.0">ıslak saçlarını güneşte kurut</div>
            <div class="poem-line" data-delay="1.2">olgun meyvelerin baygınlığıyla parıldasın</div>
            <div class="poem-line" data-delay="1.4">nemli, ağır kızıltılar…</div>
            <div class="poem-line" data-delay="1.7">sevgilim, sevgilim,</div>
            <div class="poem-line" data-delay="2.0">mevsim</div>
            <div class="poem-line" data-delay="2.3">sonbahar…</div>
        </div>
        <p class="text-right text-red-600 font-semibold mt-6 pr-4 font-forte-alternative">- Nazım Hikmet</p>
    </section>

    <!-- ZAMAN ÇİZELGESİ -->
    <section class="my-16 max-w-5xl mx-auto p-4 md:p-8 text-center">
        <h3 class="font-bold text-center text-red-600 mb-4 handwriting">Aşk Zaman Çizelgesi</h3>
        <p class="text-center text-black italic mb-8">Yolculuğumuzun unutulmaz anlarını, kalplerin ritmiyle keşfedin...</p>
        <div class="timeline-container">
            <div class="timeline-item left">
                <div class="timeline-icon"><i class="fas fa-heart heartbeat"></i></div>
                <div class="timeline-content">
                    <h4>Eylül</h4>
                    <p>Yaprakların dans ettiği o sonbahar gününde, gözlerinle tanıştım seninle...</p>
                </div>
            </div>
            <div class="timeline-item right">
                <div class="timeline-icon"><i class="fas fa-infinity heartbeat"></i></div>
                <div class="timeline-content">
                    <h4>Sonsuza Dek...</h4>
                    <p>Yemin ettik birbirimize, yıldızlar şahitliğinde...</p>
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
            <p class="text-lg text-black mt-4 italic">Sonsuzluğa giden yolculuğumuzun tarihi belli olduğunda...</p>
        </div>
    </section>

    <!-- Hayal Defterimiz -->
    <section class="my-16 max-w-3xl mx-auto p-8 bg-white/80 backdrop-blur-sm rounded-lg shadow-lg fade-in-on-scroll">
        <h3 class="font-bold text-center text-red-600 mb-6 handwriting">Hayal Defterimiz</h3>
        <p class="text-center text-black text-lg italic mt-4 mb-8">
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
        <p class="text-center text-black italic">Birlikte keşfettiğimiz yerler...</p>
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

    <!-- FOTOĞRAF GALERİSİ -->
    <section class="my-16 max-w-5xl mx-auto p-4 md:p-8 text-center">
        <h3 class="font-bold text-center text-red-600 mb-4 handwriting">Fotoğraf Galerimiz</h3>
        <p class="text-center text-black italic">
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
                    <img src="https://i.imgur.com/wf9Xhs9.jpg" alt="Anı fotoğrafı 6" class="gallery-thumbnail w-full h-full object-cover">
                    <span class="photo-number opacity-0 group-hover:opacity-100">6</span>
                    <div class="photo-note">Lunapark Anısı</div>
                </div>
                <div class="photo-container group cursor-pointer">
                    <img src="https://i.imgur.com/G26zsUc.jpg" alt="Anı fotoğrafı 5" class="gallery-thumbnail w-full h-full object-cover">
                    <span class="photo-number opacity-0 group-hover:opacity-100">5</span>
                    <div class="photo-note">Beşiktaş</div>
                </div>
                <div class="photo-container group cursor-pointer">
                    <img src="https://i.imgur.com/PR2hWYz.jpg" alt="Anı fotoğrafı 4" class="gallery-thumbnail w-full h-full object-cover">
                    <span class="photo-number opacity-0 group-hover:opacity-100">4</span>
                    <div class="photo-note">Çamlıca Kahvaltımız</div>
                </div>
                <div class="photo-container group cursor-pointer">
                    <img src="https://i.imgur.com/40oguJF.jpg" alt="Anı fotoğrafı 3" class="gallery-thumbnail w-full h-full object-cover">
                    <span class="photo-number opacity-0 group-hover:opacity-100">3</span>
                    <div class="photo-note">Çamlıca Kahvaltımız</div>
                </div>
                <div class="photo-container group cursor-pointer">
                    <img src="https://i.imgur.com/KZpZnaa.jpg" alt="Anı fotoğrafı 2" class="gallery-thumbnail w-full h-full object-cover">
                    <span class="photo-number opacity-0 group-hover:opacity-100">2</span>
                    <div class="photo-note">Dünya Güzelim</div>
                </div>
                <div class="photo-container group cursor-pointer no-note">
                    <img src="https://i.imgur.com/WnEibNN.jpg" alt="Anı fotoğrafı 1" class="gallery-thumbnail w-full h-full object-cover">
                    <span class="photo-number opacity-0 group-hover:opacity-100">1</span>
                </div>
            </div>
        </div>
    </section>

    <!-- DİLEK PENCERESİ -->
    <section class="my-16 max-w-4xl mx-auto">
        <h3 class="font-bold text-center text-red-600 mb-6 handwriting text-2xl md:text-3xl">Dilek Penceresi</h3>
        <p class="text-center text-black italic mb-6">Bir dilek bırakın, herkes görsün ve yorum yapsın!</p>

        <div class="text-center mb-8">
            <button id="open-wish-modal"
                    class="inline-flex items-center justify-center py-3 px-8 border border-transparent shadow-lg text-lg font-medium rounded-full text-white bg-gradient-to-r from-red-500 to-pink-500 hover:from-red-600 hover:to-pink-600 transition-all transform hover:scale-105">
                <i class="fas fa-gift mr-2"></i> Yeni Dilek
            </button>
        </div>

        <div id="wishes-container" class="space-y-4">
            <p class="text-center text-gray-500 italic">Yükleniyor...</p>
        </div>
    </section>

</main>

<footer class="text-center py-8 mt-12 bg-white/50">
    <p class="text-black flex items-center justify-center space-x-2">
        <span>Bu hikaye</span><i class="fas fa-infinity text-red-500"></i><span>kadar devam edecek...</span>
    </p>
    <p class="text-sm text-black mt-2">Arzu & Ersin</p>
</footer>

<!-- DİLEK MODALI -->
<div id="wish-modal" class="fixed inset-0 bg-black bg-opacity-60 hidden items-center justify-center z-50 p-4">
    <div class="bg-white rounded-2xl shadow-2xl max-w-lg w-full p-8 relative transform scale-95 opacity-0">
        <button id="close-wish-modal" class="absolute top-4 right-4 text-gray-400 hover:text-gray-600 text-2xl">
            <i class="fas fa-times"></i>
        </button>
        <h3 class="text-2xl font-bold text-center text-red-600 mb-6 handwriting">Yeni Dilek</h3>
        <form id="wish-form" class="space-y-5">
            <input type="text" id="wish-name" placeholder="Adınız" required class="w-full px-4 py-2 border rounded-lg focus:ring-2 focus:ring-red-500">
            <textarea id="wish-text" rows="3" placeholder="Dileğiniz..." required class="w-full px-4 py-2 border rounded-lg focus:ring-2 focus:ring-red-500"></textarea>
            <button type="submit" class="w-full py-3 bg-green-600 text-white rounded-lg hover:bg-green-700">
                <i class="fas fa-paper-plane mr-2"></i> Gönder
            </button>
        </form>
    </div>
</div>

<!-- SİLME MODALI -->
<div id="delete-modal" class="fixed inset-0 bg-black bg-opacity-60 hidden items-center justify-center z-50 p-4">
    <div class="bg-white rounded-2xl shadow-2xl max-w-sm w-full p-6 relative transform scale-95 opacity-0">
        <button id="close-delete-modal" class="absolute top-3 right-3 text-gray-400 hover:text-gray-600 text-xl">
            <i class="fas fa-times"></i>
        </button>
        <h3 class="text-xl font-bold text-center text-red-600 mb-4 handwriting">Sil</h3>
        <input type="password" id="admin-password" placeholder="Şifre" class="w-full px-4 py-2 border rounded-lg mb-4 focus:ring-2 focus:ring-red-500">
        <div class="flex justify-center space-x-3">
            <button id="confirm-delete" class="px-5 py-2 bg-red-600 text-white rounded-lg hover:bg-red-700">Sil</button>
            <button id="cancel-delete" class="px-5 py-2 bg-gray-300 text-gray-800 rounded-lg hover:bg-gray-400">İptal</button>
        </div>
    </div>
</div>

<script>
(() => {
    'use strict';

    // === FIREBASE ===
    const firebaseConfig = {
        apiKey: "AIzaSyB0T9tY0wZ1kX2v3Lm4n5Op6Qr7s8Tu9vA",
        authDomain: "arzu-ersin-wishes.firebaseapp.com",
        databaseURL: "https://arzu-ersin-wishes-default-rtdb.firebaseio.com",
        projectId: "arzu-ersin-wishes",
        storageBucket: "arzu-ersin-wishes.appspot.com",
        messagingSenderId: "1234567890",
        appId: "1:1234567890:web:abcdef123456"
    };
    firebase.initializeApp(firebaseConfig);
    const db = firebase.database();
    const wishesRef = db.ref('wishes');

    const ADMIN_PASSWORD = "arzuersin2025";

    // === ELEMANLAR ===
    const wishModal = document.getElementById('wish-modal');
    const openWishBtn = document.getElementById('open-wish-modal');
    const closeWishBtn = document.getElementById('close-wish-modal');
    const wishForm = document.getElementById('wish-form');
    const wishesContainer = document.getElementById('wishes-container');

    const deleteModal = document.getElementById('delete-modal');
    const adminPasswordInput = document.getElementById('admin-password');
    const confirmDeleteBtn = document.getElementById('confirm-delete');
    const cancelDeleteBtn = document.getElementById('cancel-delete');
    const closeDeleteModalBtn = document.getElementById('close-delete-modal');

    let deleteTarget = null;
    let deleteType = null;

    // === MODAL KONTROL ===
    const openModal = (modal) => {
        modal.classList.remove('hidden');
        setTimeout(() => {
            const card = modal.querySelector('.bg-white');
            card.classList.replace('scale-95', 'scale-100');
            card.style.opacity = '1';
        }, 10);
    };
    const closeModal = (modal) => {
        const card = modal.querySelector('.bg-white');
        card.classList.replace('scale-100', 'scale-95');
        card.style.opacity = '0';
        setTimeout(() => modal.classList.add('hidden'), 300);
    };

    openWishBtn.addEventListener('click', () => openModal(wishModal));
    closeWishBtn.addEventListener('click', () => closeModal(wishModal));
    wishModal.addEventListener('click', e => e.target === wishModal && closeModal(wishModal));

    // === DİLEK GÖNDER ===
    wishForm.addEventListener('submit', e => {
        e.preventDefault();
        const name = document.getElementById('wish-name').value.trim();
        const text = document.getElementById('wish-text').value.trim();
        if (!name || !text) return;

        const newWish = {
            name: escapeHtml(name),
            text: escapeHtml(text),
            timestamp: Date.now(),
            date: new Date().toLocaleDateString('tr-TR', { day: 'numeric', month: 'long', year: 'numeric', hour: '2-digit', minute: '2-digit' }),
            comments: {}
        };

        wishesRef.push(newWish).then(() => {
            wishForm.reset();
            closeModal(wishModal);
        }).catch(err => alert('Hata: ' + err.message));
    });

    // === YORUM EKLE ===
    const addComment = (wishId, name, text) => {
        const commentRef = wishesRef.child(wishId).child('comments').push();
        commentRef.set({
            name: escapeHtml(name),
            text: escapeHtml(text),
            timestamp: Date.now(),
            date: new Date().toLocaleTimeString('tr-TR', { hour: '2-digit', minute: '2-digit' })
        });
    };

    // === SİLME MODALI ===
    window.openDelete = (id, type) => {
        deleteTarget = id;
        deleteType = type;
        openModal(deleteModal);
        adminPasswordInput.value = '';
        adminPasswordInput.focus();
    };

    confirmDeleteBtn.onclick = () => {
        if (adminPasswordInput.value !== ADMIN_PASSWORD) {
            alert('Yanlış şifre!');
            return;
        }
        if (deleteType === 'wish') {
            wishesRef.child(deleteTarget).remove();
        } else {
            const [wishId, commentId] = deleteTarget.split('|');
            wishesRef.child(wishId).child('comments').child(commentId).remove();
        }
        closeModal(deleteModal);
    };

    [closeDeleteModalBtn, cancelDeleteBtn].forEach(btn => btn.onclick = () => closeModal(deleteModal));
    deleteModal.onclick = e => e.target === deleteModal && closeModal(deleteModal);

    // === DİLEKLERİ GÖSTER ===
    wishesRef.orderByChild('timestamp').on('value', snapshot => {
        const wishes = [];
        snapshot.forEach(child => {
            const data = child.val();
            data.id = child.key;
            wishes.unshift(data);
        });

        if (wishes.length === 0) {
            wishesContainer.innerHTML = `<p class="text-center text-gray-500 italic">Henüz dilek yok. İlk siz bırakın!</p>`;
            return;
        }

        wishesContainer.innerHTML = wishes.map(wish => {
            const comments = Object.entries(wish.comments || {}).map(([id, c]) => `
                <div class="comment-item">
                    <div>
                        <strong class="text-red-700 text-sm">${c.name}</strong>
                        <p class="text-gray-700 text-sm">${c.text}</p>
                        <span class="text-xs text-gray-500">${c.date}</span>
                    </div>
                    <button onclick="openDelete('${wish.id}|${id}', 'comment')" class="delete-btn text-red-500 text-xs">
                        <i class="fas fa-trash-alt"></i>
                    </button>
                </div>
            `).join('');

            return `
                <div class="wish-card">
                    <div class="wish-toggle" onclick="this.parentElement.querySelector('.comments-section').classList.toggle('open')">
                        <div>
                            <h4 class="font-semibold text-red-700">${wish.name}</h4>
                            <p class="text-gray-800">"${wish.text}"</p>
                            <span class="text-xs text-gray-500">${wish.date}</span>
                        </div>
                        <i class="fas fa-chevron-down transition-transform duration-300 ${wish.comments ? 'rotate-180' : ''}"></i>
                    </div>
                    <div class="wish-content">
                        <button onclick="openDelete('${wish.id}', 'wish')" class="delete-btn float-right text-red-500 text-sm">
                            <i class="fas fa-trash-alt"></i>
                        </button>
                    </div>
                    <div class="comments-section">
                        <div class="space-y-2">${comments}</div>
                        <form class="comment-form mt-4" onsubmit="event.preventDefault(); addComment('${wish.id}', this.name.value, this.text.value); this.reset();">
                            <input type="text" name="name" placeholder="Adınız" required class="w-full px-3 py-1 border rounded text-sm">
                            <textarea name="text" rows="1" placeholder="Yorumunuz..." required class="w-full px-3 py-1 border rounded text-sm"></textarea>
                            <button type="submit" class="w-full py-1 bg-green-600 text-white rounded text-sm hover:bg-green-700">Gönder</button>
                        </form>
                    </div>
                </div>
            `;
        }).join('');
    });

    const escapeHtml = text => {
        const div = document.createElement('div');
        div.textContent = text;
        return div.innerHTML;
    };

    // === DİĞER ÖZELLİKLER ===
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
    toggleBtn('toggle-travel-btn','travel-wrapper','travel-toggle-icon','travel-toggle-text','Seyahatlerimizi Gör','Seyahatleri Gizle');

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
                setTimeout(() => entry.target.classList.add('visible'), delay * 1000);
                poemObserver.unobserve(entry.target);
            }
        });
    }, { threshold: 0.6 });
    document.querySelectorAll('.poem-line').forEach(line => poemObserver.observe(line));

    const obs = new IntersectionObserver(entries => {
        entries.forEach(entry => { if (entry.isIntersecting) entry.target.classList.add('visible'); });
    }, {threshold:0.15});
    document.querySelectorAll('.fade-in-on-scroll').forEach(el => obs.observe(el));

    document.addEventListener('DOMContentLoaded', () => {
        wishesContainer.innerHTML = `<p class="text-center text-gray-500 italic">Yükleniyor...</p>`;
    });

})();
</script>

</body>
</html>
