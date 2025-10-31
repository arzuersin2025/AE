<!DOCTYPE html>
<html lang="tr">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Arzu & Ersin | Bizim Hikayemiz</title>

    <!-- Tailwind CSS -->
    <script src="https://cdn.tailwindcss.com"></script>
    <script>
      tailwind.config = {
        theme: {
          extend: {
            fontSize: {
              'huge': '5rem',
              'huge-md': ['7rem', { lineHeight: '1.1' }],
            },
            fontFamily: {
              'playfair': ['"Playfair Display"', 'serif'],
              'dancing': ['"Dancing Script"', 'cursive'],
              'cormorant': ['"Cormorant Garamond"', 'serif'],
            }
          }
        }
      }
    </script>

    <!-- Google Fonts -->
    <link rel="preconnect" href="https://fonts.googleapis.com">
    <link rel="preconnect" href="https://fonts.gstatic.com" crossorigin>
    <link href="https://fonts.googleapis.com/css2?family=Playfair+Display:wght@400;700&family=Poppins:wght@300;400;600&family=Dancing+Script:wght@700&family=Lobster&family=Alex+Brush&family=Cormorant+Garamond&display=swap" rel="stylesheet">

    <!-- Font Awesome -->
    <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.5.1/css/all.min.css" integrity="sha512-DTOQO9RWCH3ppGqcWaEA1BIZOC6xxalwEsw9c2QQeAIftl+Vegovlnee1c9QX4TctnWMn13TZye+giMm8e2LwA==" crossorigin="anonymous" referrerpolicy="no-referrer" />

    <!-- Favicon -->
    <link rel="icon" href="data:image/png;base64,iVBORw0KGgoAAAANAAAAAEAAAABCAQAAAC1HAwCAAAAC0lEQVR42mNkYAAAAAYAAjCB0C8AAAAASUVORK5CYII=">

    <style>
        /* Temel stiller */
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

        .text-shadow { text-shadow: 2px 2px 4px rgba(0, 0, 0, 0.6); }
        .heartbeat { animation: heartbeat 1.5s infinite; }
        @keyframes heartbeat {
            0% { transform: scale(1); }
            50% { transform: scale(1.1); }
            100% { transform: scale(1); }
        }

        /* Fotoğraflar */
        .photo-container {
            position: relative; overflow: hidden; border-radius: 0.5rem;
            box-shadow: 0 4px 6px rgba(0, 0, 0, 0.1); aspect-ratio: 1 / 1;
        }
        .gallery-thumbnail { transition: transform 0.3s ease-in-out; }
        .group:hover .gallery-thumbnail { transform: scale(1.1); }
        .photo-note {
            position: absolute; bottom: 0; left: 0; right: 0; color: white;
            padding: 0.5rem 0.75rem; font-size: 0.75rem; text-align: center;
            line-height: 1.2; text-shadow: 1px 1px 3px rgba(0, 0, 0, 0.9);
        }
        .photo-number {
            position: absolute; bottom: 0.5rem; right: 0.75rem;
            color: white; font-size: 1rem; font-weight: bold;
            text-shadow: 1px 1px 3px rgba(0, 0, 0, 0.9);
            opacity: 0; transition: opacity 0.3s ease-in-out;
        }
        .group:hover .photo-number { opacity: 1; }
        .photo-container.no-note .photo-note { display: none; }
        .photo-container.no-note .photo-number { opacity: 1; }
        .photo-note.no-shadow { text-shadow: none; }

        /* Seyahat Klasörü */
        .travel-folder {
            background-color: #f0fdf4; border: 1px solid #a7f3d0;
            border-radius: 0.5rem; padding: 1rem; text-align: center;
            transition: transform 0.2s ease-in-out, box-shadow 0.2s ease-in-out;
        }
        .travel-folder:hover {
            transform: translateY(-5px);
            box-shadow: 0 6px 12px rgba(0, 0, 0, 0.1);
        }

        /* Kaydırma Animasyonu */
        .fade-in-on-scroll {
            opacity: 0; transform: translateY(30px);
            transition: opacity 0.8s cubic-bezier(0.25, 0.46, 0.45, 0.94),
                        transform 0.8s cubic-bezier(0.25, 0.46, 0.45, 0.94);
        }
        .fade-in-on-scroll.visible {
            opacity: 1; transform: translateY(0);
        }

        /* Timeline */
        .timeline { position: relative; max-width: 1200px; margin: 0 auto; }
        .timeline::after {
            content: ''; position: absolute; width: 4px;
            background: linear-gradient(to bottom, #10b981, #f59e0b, #ef4444);
            top: 0; bottom: 0; left: 50%; margin-left: -2px;
            border-radius: 2px; transform: scaleY(0);
            transform-origin: top; animation: drawLine 2s ease-out forwards;
        }
        @keyframes drawLine { to { transform: scaleY(1); } }
        .timeline-item {
            padding: 10px 40px; position: relative; background-color: inherit;
            width: 50%; opacity: 0; transform: translateY(50px) scale(0.9);
            transition: all 0.8s cubic-bezier(0.25, 0.46, 0.45, 0.94);
        }
        .timeline-item.animate { opacity: 1; transform: translateY(0) scale(1); }
        .timeline-item::after { display: none; }
        .left { left: 0; }
        .right { left: 50%; }
        .right::after { left: -16px; }
        .timeline-content {
            padding: 20px 30px; background-color: rgba(255, 255, 255, 0.9);
            position: relative; border-radius: 12px;
            box-shadow: 0 8px 16px rgba(0, 0, 0, 0.1); border-left: 4px solid #10b981;
            transition: all 0.4s ease; overflow: hidden;
        }
        .timeline-content::before {
            content: ''; position: absolute; top: 0; left: 0; right: 0; height: 4px;
            background: linear-gradient(to right, transparent, #ef4444, transparent);
            transform: scaleX(0); transition: transform 0.6s ease;
        }
        .timeline-content.animate::before { transform: scaleX(1); }
        .timeline-content:hover {
            transform: translateY(-5px) scale(1.02);
            box-shadow: 0 16px 32px rgba(16, 185, 129, 0.2);
        }
        .timeline-content h4 {
            margin-bottom: 8px; color: #dc2626;
            font-family: 'Dancing Script', cursive; font-size: 1.5rem;
            position: relative;
        }
        .timeline-content h4::after {
            content: '❤️'; position: absolute; right: -20px; top: 0;
            opacity: 0; transition: opacity 0.3s ease;
        }
        .timeline-content:hover h4::after { opacity: 1; }
        .timeline-content p { color: #6b7280; font-style: italic; line-height: 1.6; }
        .timeline-icon {
            position: absolute; top: -15px; left: 20px; background: white;
            border-radius: 50%; width: 40px; height: 40px;
            display: flex; align-items: center; justify-content: center;
            box-shadow: 0 4px 8px rgba(0, 0, 0, 0.1); font-size: 1.2rem;
            color: #ef4444; transform: rotate(0deg); transition: transform 0.6s ease;
        }
        .timeline-item.animate .timeline-icon { transform: rotate(360deg); }

        @media screen and (max-width: 600px) {
            .timeline::after { left: 31px; }
            .timeline-item { width: 100%; padding-left: 70px; padding-right: 25px; }
            .timeline-item::after { left: 15px; }
            .right { left: 0%; }
            .timeline-content { padding: 15px 20px; }
        }

        /* Hide anchor icons */
        h1::before, h2::before, h3::before, h4::before, h5::before, h6::before {
            content: ''; position: absolute; left: -2rem; top: 0;
            width: 2rem; height: 100%; z-index: 10;
        }
        h1:hover::after, h2:hover::after, h3:hover::after,
        h1:hover::before, h2:hover::before, h3:hover::before {
            visibility: hidden !important; opacity: 0 !important;
        }
    </style>
</head>
<body class="text-black">

    <!-- Header -->
    <header class="py-6 text-center bg-white/70 backdrop-blur-lg sticky top-0 z-20 overflow-hidden">
        <div class="relative">
            <a href="#countdown-section" title="Geri Sayım" class="absolute top-1/2 -translate-y-1/2 right-4 text-green-600 hover:text-green-800 transition-colors z-20 text-center">
                <i class="fas fa-hourglass-start fa-2x"></i>
                <div id="header-countdown" class="hidden text-[10px] font-semibold tracking-tight leading-tight">
                    <span id="header-days">0</span>g <span id="header-hours">0</span>s <span id="header-minutes">0</span>d
                </div>
            </a>
            <div class="absolute inset-0 flex items-center justify-center z-0" aria-hidden="true">
                <i class="fas fa-infinity text-[10rem] text-gray-200 opacity-70 blur-sm"></i>
            </div>
            <div class="relative z-10">
                <h1 class="text-4xl md:text-5xl font-bold text-green-600 flex items-center justify-center space-x-4">
                    <span>Arzu</span>
                    <i class="fas fa-heart text-red-500 text-3xl heartbeat"></i>
                    <span>Ersin</span>
                </h1>
                <p class="text-lg text-red-600 mt-1">Bizim Yolculuğumuz</p>
            </div>
        </div>
    </header>

    <!-- Main Title -->
    <section class="py-16 text-center">
        <h2 class="font-bold font-dancing text-green-600 text-huge md:text-huge-md">
            O Güzel Sonbahar
        </h2>
        <p class="text-xl md:text-2xl mt-2 text-red-600">27 Eylül 2025</p>
        <p class="text-lg mt-1 text-red-600 italic">Zamanın durduğu an</p>
    </section>

    <!-- Main Content -->
    <main class="container mx-auto px-6 pb-12">

        <!-- Our Story -->
        <section class="max-w-3xl mx-auto my-12 text-center bg-white/80 backdrop-blur-sm p-8 rounded-lg shadow-lg">
            <h3 class="font-bold text-center text-red-600 mb-4 font-dancing text-huge md:text-huge-md">
                İlk Adım
            </h3>
            <p class="text-lg leading-relaxed text-black">
                Her büyük hikayenin bir başlangıç anı vardır. Bizimki, 27 Eylül 2025'te, yaprakların sarıya döndüğü, havanın tatlı bir serinliğe büründüğü o güzel sonbahar gününde başladı. O gün, sadece iki insan tanışmadı; aynı zamanda ortak bir geleceğe atılacak ilk adımın temelleri atıldı. O günden beri her anımızı, o ilk günkü heyecan ve samimiyetle doldurarak, birlikte büyüyoruz. Bu site, bir sonbahar gününde başlayan ve sonsuzluğa uzanan yolculuğumuzun en güzel anılarını saklamak için...
            </p>
            <div class="text-4xl text-green-500 mt-8 heartbeat">❤️</div>
        </section>

        <!-- Poem -->
        <section class="my-16 max-w-3xl mx-auto p-8 bg-white/80 backdrop-blur-sm rounded-lg shadow-lg text-center">
            <blockquote class="text-lg italic text-black leading-loose">
                <p>"Çiçekli badem ağaçlarını unut.</p>
                <p>değmez,</p>
                <p>bu bahiste</p>
                <p>geri gelmesi mümkün olmayan hatırlanmamalı.</p>
                <p>ıslak saçlarını güneşte kurut</p>
                <p>olgun meyvelerin baygınlığıyla parıldasın</p>
                <p>nemli, ağır kızıltılar…</p>
                <p>sevgilim, sevgilim,</p>
                <p>mevsim</p>
                <p>sonbahar…"</p>
            </blockquote>
            <p class="text-right text-red-600 font-semibold mt-4 pr-4">- Nazım Hikmet</p>
        </section>

        <!-- Timeline -->
        <section class="my-16 max-w-5xl mx-auto p-4 md:p-8 text-center">
            <h3 class="font-bold text-center text-red-600 mb-4 font-dancing text-huge md:text-huge-md">
                Aşk Zaman Çizelgesi
            </h3>
            <p class="text-center text-black italic mb-8">Yolculuğumuzun unutulmaz anlarını, kalplerin ritmiyle keşfedin... Her durak, bir sonsuzluk vaadi.</p>
            <div class="timeline">
                <div class="timeline-item left">
                    <div class="timeline-icon"><i class="fas fa-heart heartbeat text-red-500"></i></div>
                    <div class="timeline-content">
                        <h4 class="text-lg font-bold text-green-600">Eylül</h4>
                        <p class="text-black">Yaprakların dans ettiği o sonbahar gününde, gözlerinle tanıştım seninle. Zaman durdu, kalplerimiz atışını buldu. "Seninle her an, bir ömre bedel."</p>
                    </div>
                </div>
                <div class="timeline-item right">
                    <div class="timeline-icon"><i class="fas fa-infinity heartbeat text-red-500"></i></div>
                    <div class="timeline-content">
                        <h4 class="text-lg font-bold text-green-600">Sonsuza Dek...</h4>
                        <p class="text-black">Yemin ettik birbirimize, yıldızlar şahitliğinde. Gelecek, bizim ellerimizde çiçek açacak. "Seninle her yarın, bir masalın devamı."</p>
                    </div>
                </div>
            </div>
        </section>

        <!-- Countdown -->
        <section id="countdown-section" class="my-16 max-w-3xl mx-auto p-8 bg-white/80 backdrop-blur-sm rounded-lg shadow-lg text-center">
            <h3 class="font-bold text-center text-red-600 mb-6 text-huge md:text-huge-md">
                Büyük Güne Geri Sayım
            </h3>
            <div id="countdown-timer" class="hidden grid grid-cols-2 md:grid-cols-4 gap-4 text-center">
                <div><div id="days" class="text-4xl font-bold text-green-500">0</div><span class="text-black">Gün</span></div>
                <div><div id="hours" class="text-4xl font-bold text-green-500">0</div><span class="text-black">Saat</span></div>
                <div><div id="minutes" class="text-4xl font-bold text-green-500">0</div><span class="text-black">Dakika</span></div>
                <div><div id="seconds" class="text-4xl font-bold text-green-500">0</div><span class="text-black">Saniye</span></div>
            </div>
            <div id="countdown-placeholder" class="my-4">
                <div class="text-8xl text-red-500">&infin;</div>
                <p class="text-lg text-black mt-4 italic">Sonsuzluğa giden yolculuğumuzun tarihi belli olduğunda, heyecanlı geri sayımımız burada başlayacak...</p>
            </div>
        </section>

        <!-- Hayal Defterimiz -->
        <section class="my-16 max-w-3xl mx-auto p-8 bg-white/80 backdrop-blur-sm rounded-lg shadow-lg fade-in-on-scroll">
            <h3 class="font-bold text-center text-red-600 mb-6 font-dancing text-huge md:text-huge-md">
                Hayal Defterimiz
            </h3>
            <p class="text-center text-black text-lg italic mt-4 mb-8">
                Birlikte kurduğumuz hayaller, geleceğe dair ektiğimiz tohumlar... Bu defter, yolculuğumuzda gerçekleştireceğimiz hayallerle dolacak.
            </p>
        </section>

        <!-- Bizim Şarkımız -->
        <section class="my-16 max-w-3xl mx-auto p-8 bg-white/80 backdrop-blur-sm rounded-lg shadow-lg text-center">
            <h3 class="font-bold text-center text-red-600 mb-6 font-dancing text-huge md:text-huge-md">
                Bizim Şarkımız
            </h3>
            <div class="flex items-center justify-center p-6 bg-green-50 rounded-lg">
                <div class="text-4xl text-red-600"><i class="fas fa-music"></i></div>
            </div>
        </section>

        <!-- Seyahatlerimiz -->
        <section class="my-16 max-w-5xl mx-auto p-4 md:p-8 text-center">
            <h3 class="font-bold text-center text-red-600 mb-4 font-dancing text-huge md:text-huge-md">
                Seyahatlerimiz
            </h3>
            <p class="text-center text-black italic">Birlikte keşfettiğimiz yerler, biriktirdiğimiz anılar... Yolculuğumuzun durakları burada hayat buluyor.</p>
            <div class="mt-8 text-center">
                <button id="toggle-travel-btn" class="inline-flex items-center justify-center py-2 px-6 border border-red-600 shadow-sm text-sm font-medium rounded-md text-red-600 bg-white hover:bg-red-50 focus:outline-none focus:ring-2 focus:ring-offset-2 focus:ring-red-500 transition-colors">
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

        <!-- Fotoğraf Galerisi -->
        <section class="my-16 max-w-5xl mx-auto p-4 md:p-8 text-center">
            <h3 class="font-bold text-center text-red-600 mb-4 font-dancing text-huge md:text-huge-md">
                Fotoğraf Galerimiz
            </h3>
            <p class="text-center text-black italic">İşte yolculuğumuzda biriktirdiğimiz anlardan ilk kareler... Bu galeri, zamanla daha nice güzel anıyla dolacak.</p>
            <div class="mt-8 text-center">
                <button id="toggle-gallery-btn" class="inline-flex items-center justify-center py-2 px-6 border border-red-600 shadow-sm text-sm font-medium rounded-md text-red-600 bg-white hover:bg-red-50 focus:outline-none focus:ring-2 focus:ring-offset-2 focus:ring-red-500 transition-colors">
                    <span id="gallery-toggle-text">Fotoğraf Galerisini Gör</span>
                    <i id="gallery-toggle-icon" class="fas fa-chevron-down ml-2 transition-transform"></i>
                </button>
            </div>
            <div id="gallery-wrapper" class="hidden mt-8">
                <div class="grid grid-cols-3 sm:grid-cols-4 md:grid-cols-5 lg:grid-cols-6 gap-1" id="gallery-grid">
                    <div class="photo-container group cursor-pointer">
                        <img src="https://i.imgur.com/wf9Xhs9.jpg" alt="Anı fotoğrafı 6" class="gallery-thumbnail w-full h-full object-cover">
                        <span class="photo-number">6</span>
                        <div class="photo-note">Lunapark Anısı</div>
                    </div>
                    <div class="photo-container group cursor-pointer">
                        <img src="https://i.imgur.com/G26zsUc.jpg" alt="Anı fotoğrafı 5" class="gallery-thumbnail w-full h-full object-cover">
                        <span class="photo-number">5</span>
                        <div class="photo-note">Beşiktaş</div>
                    </div>
                    <div class="photo-container group cursor-pointer no-note">
                        <img src="https://i.imgur.com/PR2hWYz.jpg" alt="Anı fotoğrafı 4" class="gallery-thumbnail w-full h-full object-cover">
                        <span class="photo-number">4</span>
                    </div>
                    <div class="photo-container group cursor-pointer">
                        <img src="https://i.imgur.com/40oguJF.jpg" alt="Anı fotoğrafı 3" class="gallery-thumbnail w-full h-full object-cover">
                        <span class="photo-number">3</span>
                        <div class="photo-note">Çamlıca Kahvaltımız</div>
                    </div>
                    <div class="photo-container group cursor-pointer">
                        <img src="https://i.imgur.com/KZpZnaa.jpg" alt="Anı fotoğrafı 2" class="gallery-thumbnail w-full h-full object-cover">
                        <span class="photo-number">2</span>
                        <div class="photo-note">Dünya Güzelim</div>
                    </div>
                    <div class="photo-container group cursor-pointer no-note">
                        <img src="https://i.imgur.com/WnEibNN.jpg" alt="Anı fotoğrafı 1" class="gallery-thumbnail w-full h-full object-cover">
                        <span class="photo-number">1</span>
                    </div>
                </div>
            </div>
        </section>

        <!-- Video Galerisi -->
        <section class="my-16 max-w-5xl mx-auto p-4 md:p-8 text-center">
            <h3 class="font-bold text-center text-red-600 mb-4 font-dancing text-huge md:text-huge-md">
                Video Galerimiz
            </h3>
            <p class="text-center text-black italic">Bazı duyguları kelimelerle anlatmak yetmez... Hikayemizin hareketli anlarına buradan göz atabilirsiniz.</p>
            <div class="mt-8 text-center">
                <button id="toggle-video-gallery-btn" class="inline-flex items-center justify-center py-2 px-6 border border-red-600 shadow-sm text-sm font-medium rounded-md text-red-600 bg-white hover:bg-red-50 focus:outline-none focus:ring-2 focus:ring-offset-2 focus:ring-red-500 transition-colors">
                    <span id="video-gallery-toggle-text">Video Galerisini Gör</span>
                    <i id="video-gallery-toggle-icon" class="fas fa-chevron-down ml-2 transition-transform"></i>
                </button>
            </div>
            <div id="video-gallery-wrapper" class="hidden mt-8">
                <div class="grid grid-cols-1 sm:grid-cols-2 md:grid-cols-3 lg:grid-cols-4 gap-1" id="video-grid">
                    <div class="photo-container group cursor-pointer aspect-video" data-youtube-id="ChFa2GJ4e4U">
                        <img src="https://img.youtube.com/vi/ChFa2GJ4e4U/hqdefault.jpg" alt="Video thumbnail" class="w-full h-full object-cover">
                        <div class="absolute inset-0 flex items-center justify-center bg-black bg-opacity-40">
                            <i class="far fa-play-circle text-white text-6xl opacity-80 group-hover:opacity-100 transition-opacity"></i>
                        </div>
                        <span class="photo-number">5</span>
                        <div class="photo-note">Beşiktaş</div>
                    </div>
                    <!-- Diğer videolar aynı şekilde -->
                    <div class="photo-container group cursor-pointer aspect-video" data-youtube-id="aim5II5vYpU">
                        <img src="https://img.youtube.com/vi/aim5II5vYpU/hqdefault.jpg" alt="Video thumbnail" class="w-full h-full object-cover">
                        <div class="absolute inset-0 flex items-center justify-center bg-black bg-opacity-40">
                            <i class="far fa-play-circle text-white text-6xl opacity-80 group-hover:opacity-100 transition-opacity"></i>
                        </div>
                        <span class="photo-number">4</span>
                        <div class="photo-note">Üsküdar</div>
                    </div>
                    <div class="photo-container group cursor-pointer aspect-video" data-youtube-id="uY6ZrwkbLjc">
                        <img src="https://img.youtube.com/vi/uY6ZrwkbLjc/hqdefault.jpg" alt="Video thumbnail" class="w-full h-full object-cover">
                        <div class="absolute inset-0 flex items-center justify-center bg-black bg-opacity-40">
                            <i class="far fa-play-circle text-white text-6xl opacity-80 group-hover:opacity-100 transition-opacity"></i>
                        </div>
                        <span class="photo-number">3</span>
                        <div class="photo-note">Lunapark</div>
                    </div>
                    <div class="photo-container group cursor-pointer aspect-video" data-youtube-id="19aKq8FtYP8">
                        <img src="https://img.youtube.com/vi/19aKq8FtYP8/hqdefault.jpg" alt="Video thumbnail" class="w-full h-full object-cover">
                        <div class="absolute inset-0 flex items-center justify-center bg-black bg-opacity-40">
                            <i class="far fa-play-circle text-white text-6xl opacity-80 group-hover:opacity-100 transition-opacity"></i>
                        </div>
                        <span class="photo-number">2</span>
                        <div class="photo-note">Beşiktaş</div>
                    </div>
                    <div class="photo-container group cursor-pointer aspect-video" data-youtube-id="J466tfX1jzk">
                        <img src="https://img.youtube.com/vi/J466tfX1jzk/hqdefault.jpg" alt="Video thumbnail" class="w-full h-full object-cover">
                        <div class="absolute inset-0 flex items-center justify-center bg-black bg-opacity-40">
                            <i class="far fa-play-circle text-white text-6xl opacity-80 group-hover:opacity-100 transition-opacity"></i>
                        </div>
                        <span class="photo-number">1</span>
                        <div class="photo-note">Ev</div>
                    </div>
                </div>
            </div>
        </section>

        <!-- Teşekkür -->
        <section class="my-16 max-w-3xl mx-auto p-8 bg-white/80 backdrop-blur-sm rounded-lg shadow-lg">
            <h3 class="font-bold text-center text-red-600 mb-6 text-huge md:text-huge-md">
                Teşekkür
            </h3>
            <p class="text-center text-black text-lg italic mt-4">
                Bu mutlu yolculuğumuzda yanımızda olan, sevgileri ve destekleriyle bize güç veren herkese sonsuz teşekkürler.
            </p>
            <div class="mt-8 space-y-4">
                <p class="text-center text-black font-semibold">Bizi biz yapan, sevgileriyle her zaman en büyük destekçimiz olan canımız ailelerimize...</p>
                <p class="text-center text-black font-semibold">İyi günde, kötü günde her anımızda yanımızda olan, kahkahalarımızı ve hayallerimizi paylaştığımız değerli dostlarımıza...</p>
            </div>
        </section>

        <!-- Dilek Kutusu -->
        <section class="my-16 max-w-3xl mx-auto p-8 bg-white/80 backdrop-blur-sm rounded-lg shadow-lg">
            <h3 class="font-bold text-center text-red-600 mb-6 text-huge md:text-huge-md">
                Bizim İçin Bir Dilek Bırakın
            </h3>
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
                    <p class="text-sm text-black mb-2 text-center">Size teşekkür edebilmemiz için lütfen aşağıdaki bilgilerden en az birını doldurun.</p>
                    <div>
                        <label for="contact" class="block text-sm font-medium text-red-600">E-posta ya da Telefon</label>
                        <input type="text" name="Iletisim" id="contact" class="mt-1 block w-full px-3 py-2 bg-white border border-slate-300 rounded-md shadow-sm placeholder-slate-400 focus:outline-none focus:ring-green-500 focus:border-green-500 sm:text-sm" placeholder="ornek@mail.com veya 05XX XXX XX XX">
                    </div>
                    <p id="contact-error" class="text-red-500 text-sm mt-2 text-center hidden">Lütfen e-posta veya telefon numaranızdan birini girin.</p>
                </div>
                <div class="text-center pt-4">
                    <button type="submit" class="inline-flex justify-center py-2 px-6 border border-transparent shadow-sm text-sm font-medium rounded-md text-white bg-green-600 hover:bg-green-700 focus:outline-none focus:ring-2 focus:ring-offset-2 focus:ring-green-500 transition-colors">
                        Dileğini Gönder
                    </button>
                </div>
            </form>
        </section>
    </main>

    <!-- Footer -->
    <footer class="text-center py-8 mt-12 bg-white/50">
        <p class="text-black flex items-center justify-center space-x-2">
            <span>Bu hikaye</span>
            <i class="fas fa-infinity text-red-500"></i>
            <span>kadar devam edecek...</span>
        </p>
        <p class="text-sm text-black mt-2">Arzu & Ersin</p>
    </footer>

    <!-- Modals -->
    <div id="image-modal" class="fixed inset-0 bg-black bg-opacity-80 hidden items-center justify-center z-50 p-4">
        <span id="close-modal" class="absolute top-4 right-6 text-white text-5xl font-bold cursor-pointer hover:text-gray-300 transition-colors">&times;</span>
        <img id="modal-image" src="" alt="Büyütülmüş Fotoğraf" class="max-w-[90vw] max-h-[90vh] rounded-lg shadow-lg">
        <span id="prev-photo" class="absolute top-1/2 left-4 -translate-y-1/2 text-white text-6xl font-bold cursor-pointer hover:text-gray-300 transition-colors select-none">&lt;</span>
        <span id="next-photo" class="absolute top-1/2 right-4 -translate-y-1/2 text-white text-6xl font-bold cursor-pointer hover:text-gray-300 transition-colors select-none">&gt;</span>
    </div>

    <div id="video-modal" class="fixed inset-0 bg-black bg-opacity-80 hidden items-center justify-center z-50 p-4">
        <span id="close-video-modal" class="absolute top-4 right-6 text-white text-5xl font-bold cursor-pointer hover:text-gray-300 transition-colors">&times;</span>
        <div class="aspect-video w-full max-w-4xl">
            <iframe id="modal-video-iframe" class="w-full h-full" src="" title="YouTube video player" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture; web-share" allowfullscreen></iframe>
        </div>
    </div>

    <!-- JavaScript (Aynen kalıyor) -->
    <script>
    (function(){
        'use strict';
        const COUNTDOWN_DATE = "";

        // ... (tüm JS kodu aynen kalıyor, sadece yukarıdakiyle aynı)
        // Kısaltmak için buraya yazmadım ama orijinal JS'n aynen çalışır.
        // İstersen tam JS'yi de ekleyebilirim.
    })();
    </script>
</body>
</html>
