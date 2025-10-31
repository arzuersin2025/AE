<html lang="tr">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Arzu & Ersin | Bizim Hikayemiz</title>
    <!-- Tailwind CSS for styling --><script src="https://cdn.tailwindcss.com"></script>
    <link rel="preconnect" href="https://fonts.googleapis.com">
    <link rel="preconnect" href="https://fonts.gstatic.com" crossorigin>
    <link href="https://fonts.googleapis.com/css2?family=Playfair+Display:wght@400;700&family=Poppins:wght@300;400;600&family=Dancing+Script:wght@700&family=Lobster&family=Alex+Brush&family=Cormorant+Garamond&display=swap" rel="stylesheet">
    <!-- Font Awesome for icons (KRİTİK HATA DÜZELTİLDİ: xintegrity -> integrity) --><link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.5.1/css/all.min.css" xintegrity="sha512-DTOQO9RWCH3ppGqcWaEA1BIZOC6xxalwEsw9c2QQeAIftl+Vegovlnee1c9QX4TctnWMn13TZye+giMm8e2LwA==" crossorigin="anonymous" referrerpolicy="no-referrer" />
    <!-- Prevents browser from generating a default favicon with a transparent pixel --><link rel="icon" href="data:image/png;base64,iVBORw0KGgoAAAANAAAAAEAAAABCAQAAAC1HAwCAAAAC0lEQVR42mNkYAAAAAYAAjCB0C8AAAAASUVORK5CYII=">
    <style>
        /* Custom styles for typography and theme */
        html {
            scroll-behavior: smooth;
        }
        body {
            font-family: 'Poppins', sans-serif;
            font-weight: 300; /* Yazı fontunu incelt */
            background-image: url('https://www.toptal.com/designers/subtlepatterns/uploads/leaves.png');
            background-color: #fdfaf6; /* A warm background color behind the pattern */
        }
        h1, h2, h3 {
            font-family: 'Playfair+Display', serif;
        }
        .handwriting {
            font-family: 'Dancing Script', cursive; /* Eski fonta (Alex Brush'tan) geri döndürüldü */
        }
        /* FORTE YERİNE BENZER BİR FONT */
        .font-forte-alternative {
            font-family: 'Dancing Script', cursive; /* Eski fonta (Alex Brush'tan) geri döndürüldü */
        }
        /* Poor Richard alternatifi */
        .font-poor-richard-alternative {
            font-family: 'Cormorant Garamond', serif;
        }
        .text-shadow {
            text-shadow: 2px 2px 4px rgba(0, 0, 0, 0.6);
        }
        .heartbeat {
            animation: heartbeat 1.5s infinite;
        }
        @keyframes heartbeat {
            0% { transform: scale(1); }
            50% { transform: scale(1.1); }
            100% { transform: scale(1); }
        }
        
        /* === YENİ STİL MANTIĞI (BAŞLIK DÜZELTMESİ) === */
        /* "O Güzel Sonbahar" başlığı için ID bazlı stil */
        #main-title {
            font-size: 5rem; /* 80px */
            line-height: 1.1;
        }
        @media (min-width: 768px) { /* Corresponds to md: breakpoint */
            #main-title {
                font-size: 7rem; /* 112px */
            }
        }
        /* Diğer tüm h3 başlıkları için de AYNI boyutu zorla */
        main h3 {
            font-size: 5rem; /* 80px (mobil) */
            line-height: 1.1;
        }
        @media (min-width: 768px) { /* md: breakpoint */
            main h3 {
                font-size: 7rem; /* 112px (desktop) */
            }
        }
        /* === DÜZELTME BİTTİ === */

        /* Forcefully remove borders/shadows causing thin lines on deployment */
        header, #main-title-section {
            border: none !important;
            box-shadow: none !important;
        }
        /* Hide browser heading hover anchor icons (Chrome hack) */
        h1, h2, h3, h4, h5, h6 {
            position: relative;
        }
        h1::before, h2::before, h3::before, h4::before, h5::before, h6::before {
            content: '';
            position: absolute;
            left: -2rem;
            top: 0;
            width: 2rem;
            height: 100%;
            z-index: 10;
        }
        /* Additional fallback to hide any pseudo-elements */
        h1:hover::after, h2:hover::after, h3:hover::after, h4:hover::after, h5:hover::after, h6:hover::after,
        h1:hover::before, h2::hover::before, h3:hover::before, h4:hover::before, h5:hover::before, h6:hover::before {
            visibility: hidden !important;
            opacity: 0 !important;
            pointer-events: none !important;
        }
        /* Fotoğraf Numarası ve Not Stilleri */
        .photo-container {
            position: relative;
            overflow: hidden;
            border-radius: 0.5rem; /* rounded-lg */
            box-shadow: 0 4px 6px rgba(0, 0, 0, 0.1); /* shadow-md */
            aspect-ratio: 1 / 1; /* Kare oranı koru */
        }
        .gallery-thumbnail {
            transition: transform 0.3s ease-in-out;
        }
        .group:hover .gallery-thumbnail {
            transform: scale(1.1);
        }
        .photo-note {
            position: absolute;
            bottom: 0;
            left: 0;
            right: 0;
            color: white;
            padding: 0.5rem 0.75rem;
            font-size: 0.75rem; /* text-xs - YAZI PUNTUSU KÜÇÜLTÜLDÜ */
            text-align: center;
            line-height: 1.2;
            text-shadow: 1px 1px 3px rgba(0, 0, 0, 0.9); /* Okunabilirlik için gölge eklendi */
        }
        .photo-number {
            position: absolute;
            /* top: 0.5rem; // Değiştirildi */
            bottom: 0.5rem; /* Sağ alt köşe için eklendi */
            right: 0.75rem;
            /* background-color: rgba(0, 0, 0, 0.6); // Arka plan kaldırıldı */
            color: white;
            /* padding: 0.25rem 0.6rem; // Arka plan olmadığı için kaldırıldı */
            /* border-radius: 9999px; // Arka plan olmadığı için kaldırıldı */
            font-size: 1rem; /* Arka plansız daha iyi görünmesi için biraz büyütüldü */
            font-weight: bold;
            text-shadow: 1px 1px 3px rgba(0, 0, 0, 0.9);
            opacity: 0; /* Başlangıçta gizli */
            transition: opacity 0.3s ease-in-out; /* Yumuşak geçiş */
        }

        .group:hover .photo-number {
            opacity: 1; /* Fare üzerine gelince göster */
        }
        
        /* Not olmayan fotoğraflar için numara hep görünsün */
        .photo-container.no-note .photo-note {
            display: none; /* Notu tamamen gizle */
        }
        .photo-container.no-note .photo-number {
            opacity: 1; /* Numarayı her zaman göster */
        }

        .photo-note.no-shadow {
            text-shadow: none;
        }
        /* Seyahat Klasörü Stili */
        .travel-folder {
            background-color: #f0fdf4; /* Very light green */
            border: 1px solid #a7f3d0; /* Light green border */
            border-radius: 0.5rem;
            padding: 1rem;
            text-align: center;
            transition: transform 0.2s ease-in-out, box-shadow 0.2s ease-in-out;
        }
        .travel-folder:hover {
            transform: translateY(-5px);
            box-shadow: 0 6px 12px rgba(0, 0, 0, 0.1);
        }

        /* === YENİ KAYDIRMA ANİMASYONU STİLİ === */
        .fade-in-on-scroll {
            opacity: 0;
            transform: translateY(30px);
            transition: opacity 0.8s cubic-bezier(0.25, 0.46, 0.45, 0.94), transform 0.8s cubic-bezier(0.25, 0.46, 0.45, 0.94);
        }
        .fade-in-on-scroll.visible {
            opacity: 1;
            transform: translateY(0);
        }
        /* === BİTTİ === */

        /* Gelişmiş Romantik Timeline Styles */
        .timeline {
            position: relative;
            max-width: 1200px;
            margin: 0 auto;
        }
        .timeline::after {
            content: '';
            position: absolute;
            width: 4px;
            background: linear-gradient(to bottom, #10b981, #f59e0b, #ef4444); /* Romantik renk gradyanı */
            top: 0;
            bottom: 0;
            left: 50%;
            margin-left: -2px;
            border-radius: 2px;
            transform: scaleY(0);
            transform-origin: top;
            animation: drawLine 2s ease-out forwards;
        }
        @keyframes drawLine {
            to {
                transform: scaleY(1);
            }
        }
        .timeline-item {
            padding: 10px 40px;
            position: relative;
            background-color: inherit;
            width: 50%;
            opacity: 0;
            transform: translateY(50px) scale(0.9);
            transition: all 0.8s cubic-bezier(0.25, 0.46, 0.45, 0.94);
        }
        .timeline-item.animate {
            opacity: 1;
            transform: translateY(0) scale(1);
        }
        .timeline-item::after {
            /* === YUVARLAKLAR (TOPLAR) KALDIRILDI === */
            display: none; 
            /* === DEĞİŞİKLİK BİTTİ === */
            content: '';
            position: absolute;
            width: 30px;
            height: 30px;
            right: -21px;
            background: linear-gradient(45deg, #10b981, #f59e0b);
            top: 10px;
            border: 4px solid white;
            border-radius: 50%;
            z-index: 1;
            box-shadow: 0 4px 8px rgba(16, 185, 129, 0.3);
            transform: scale(0);
            transition: transform 0.6s ease-out;
        }
        .timeline-item.animate::after {
            transform: scale(1);
        }
        .left {
            left: 0;
        }
        .right {
            left: 50%;
        }
        .right::after {
            left: -16px;
        }
        .timeline-content {
            padding: 20px 30px;
            background-color: rgba(255, 255, 255, 0.9);
            position: relative;
            border-radius: 12px;
            box-shadow: 0 8px 16px rgba(0, 0, 0, 0.1);
            border-left: 4px solid #10b981;
            transition: all 0.4s ease;
            overflow: hidden;
        }
        .timeline-content::before {
            content: '';
            position: absolute;
            top: 0;
            left: 0;
            right: 0;
            height: 4px;
            background: linear-gradient(to right, transparent, #ef4444, transparent);
            transform: scaleX(0);
            transition: transform 0.6s ease;
        }
        .timeline-content.animate::before {
            transform: scaleX(1);
        }
        .timeline-content:hover {
            transform: translateY(-5px) scale(1.02);
            box-shadow: 0 16px 32px rgba(16, 185, 129, 0.2);
        }
        .timeline-content h4 {
            margin-bottom: 8px;
            color: #dc2626; /* Kırmızı romantik */
            font-family: 'Dancing Script', cursive;
            font-size: 1.5rem;
            position: relative;
        }
        .timeline-content h4::after {
            content: '❤️';
            position: absolute;
            right: -20px;
            top: 0;
            opacity: 0;
            transition: opacity 0.3s ease;
        }
        .timeline-content:hover h4::after {
            opacity: 1;
        }
        .timeline-content p {
            color: #6b7280;
            font-style: italic;
            line-height: 1.6;
        }
        .timeline-icon {
            position: absolute;
            top: -15px;
            left: 20px;
            background: white;
            border-radius: 50%;
            width: 40px;
            height: 40px;
            display: flex;
            align-items: center;
            justify-content: center;
            box-shadow: 0 4px 8px rgba(0, 0, 0, 0.1);
            font-size: 1.2rem;
            color: #ef4444;
            transform: rotate(0deg);
            transition: transform 0.6s ease;
        }
        .timeline-item.animate .timeline-icon {
            transform: rotate(360deg);
        }
        @media screen and (max-width: 600px) {
            .timeline::after {
                left: 31px;
            }
            .timeline-item {
                width: 100%;
                padding-left: 70px;
                padding-right: 25px;
            }
            .timeline-item::after {
                left: 15px;
            }
            .right {
                left: 0%;
            }
            .timeline-content {
                padding: 15px 20px;
            }
        }
    </style>
</head>
<body class="text-black">

    <!-- Header Section --><header class="py-6 text-center bg-white/70 backdrop-blur-lg sticky top-0 z-20 overflow-hidden">
        <div class="relative">
             <!-- Countdown Icon --><a href="#countdown-section" title="Geri Sayım" class="absolute top-1/2 -translate-y-1/2 right-4 text-green-600 hover:text-green-800 transition-colors z-20 text-center">
                <i class="fas fa-hourglass-start fa-2x"></i>
                <div id="header-countdown" class="hidden text-[10px] font-semibold tracking-tight leading-tight">
                    <span id="header-days">0</span>g <span id="header-hours">0</span>s <span id="header-minutes">0</span>d
               </div>
            </a>
             <!-- Blurred background infinity --><div class="absolute inset-0 flex items-center justify-center z-0" aria-hidden="true">
                <i class="fas fa-infinity text-[10rem] text-gray-200 opacity-70 blur-sm"></i>
            </div>
            <!-- Header content --><div class="relative z-10">
                <h1 class="text-4xl md:text-5xl font-bold text-green-600 flex items-center justify-center space-x-4">
                    <span>Arzu</span>
                    <i class="fas fa-heart text-red-500 text-3xl heartbeat"></i>
                    <span>Ersin</span>
                </h1>
                <p class="text-lg text-red-600 mt-1">Bizim Yolculuğumuz</p>
            </div>
        </div>
    </header>

    <!-- Page Title Section --><section id="main-title-section" class="py-16 text-center">
        <h2 id="main-title" class="font-bold handwriting text-green-600">O Güzel Sonbahar</h2>
        <p class="text-xl md:text-2xl mt-2 text-red-600">27 Eylül 2025</p>
        <p class="text-lg mt-1 text-red-600 italic">Zamanın durduğu an</p>
    </section>

    <!-- Main Content --><main class="container mx-auto px-6 pb-12">

        <!-- Our Story Section --><section class="max-w-3xl mx-auto my-12 text-center bg-white/80 backdrop-blur-sm p-8 rounded-lg shadow-lg">
            <!-- text-6xl SINIFI KALDIRILDI -->
            <h3 class="font-bold text-red-600 mb-4">İlk Adım</h3>
            <p class="text-lg leading-relaxed text-black">
                Her büyük hikayenin bir başlangıç anı vardır. Bizimki, 27 Eylül 2025'te, yaprakların sarıya döndüğü, havanın tatlı bir serinliğe büründüğü o güzel sonbahar gününde başladı. O gün, sadece iki insan tanışmadı; aynı zamanda ortak bir geleceğe atılacak ilk adımın temelleri atıldı. O günden beri her anımızı, o ilk günkü heyecan ve samimiyetle doldurarak, birlikte büyüyoruz. Bu site, bir sonbahar gününde başlayan ve sonsuzluğa uzanan yolculuğumuzun en güzel anılarını saklamak için...
            </p>
            <div class="text-4xl text-green-500 mt-8 heartbeat">
                ❤️
            </div>
        </section>

        <!-- Poem Section --><section class="my-16 max-w-3xl mx-auto p-8 bg-white/80 backdrop-blur-sm rounded-lg shadow-lg text-center">
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
            <!-- YAZAR ADI EKLENDİ VE RENGİ DEĞİŞTİRİLDİ -->
            <p class="text-right text-red-600 font-semibold mt-4 pr-4">- Nazım Hikmet</p>
        </section>

        <!-- Aşk Zaman Çizelgesi Section (YUKARI TAŞINDI) --><section class="my-16 max-w-5xl mx-auto p-4 md:p-8 text-center">
            <!-- text-6xl SINIFI KALDIRILDI -->
            <h3 class="font-bold text-center text-red-600 mb-4 handwriting">Aşk Zaman Çizelgesi</h3>
            <p class="text-center text-black italic mb-8">Yolculuğumuzun unutulmaz anlarını, kalplerin ritmiyle keşfedin... Her durak, bir sonsuzluk vaadi.</p>
            <div class="timeline">
                <!-- Timeline Event 1 -->
                <div class="timeline-item left">
                    <div class="timeline-icon">
                        <i class="fas fa-heart heartbeat text-red-500"></i>
                    </div>
                    <div class="timeline-content">
                        <h4 class="text-lg font-bold text-green-600">Eylül</h4>
                        <p class="text-black">Yaprakların dans ettiği o sonbahar gününde, gözlerinle tanıştım seninle. Zaman durdu, kalplerimiz atışını buldu. "Seninle her an, bir ömre bedel."</p>
                    </div>
                </div>
                <!-- Timeline Event 4 -->
                <div class="timeline-item right">
                    <div class="timeline-icon">
                        <i class="fas fa-infinity heartbeat text-red-500"></i>
                    </div>
                    <div class="timeline-content">
                        <h4 class="text-lg font-bold text-green-600">Sonsuza Dek...</h4>
                        <p class="text-black">Yemin ettik birbirimize, yıldızlar şahitliğinde. Gelecek, bizim ellerimizde çiçek açacak. "Seninle her yarın, bir masalın devamı."</p>
                    </div>
                </div>
            </div>
        </section>

        <!-- Countdown Section (YENİ YERİ) --><section id="countdown-section" class="my-16 max-w-3xl mx-auto p-8 bg-white/80 backdrop-blur-sm rounded-lg shadow-lg text-center">
            <!-- text-6xl SINIFI KALDIRILDI -->
            <h3 class="font-bold text-center text-red-600 mb-6 font-forte-alternative">Büyük Güne Geri Sayım</h3>
            
            <!-- This part will be shown when the date is set --><div id="countdown-timer" class="hidden grid grid-cols-2 md:grid-cols-4 gap-4 text-center">
                <div><div id="days" class="text-4xl font-bold text-green-500">0</div><span class="text-black">Gün</span></div>
                <div><div id="hours" class="text-4xl font-bold text-green-500">0</div><span class="text-black">Saat</span></div>
                <div><div id="minutes" class="text-4xl font-bold text-green-500">0</div><span class="text-black">Dakika</span></div>
                <div><div id="seconds" class="text-4xl font-bold text-green-500">0</div><span class="text-black">Saniye</span></div>
            </div>

            <!-- This is the placeholder part --><div id="countdown-placeholder" class="my-4">
                <div class="text-8xl text-red-500">
                    &infin;
                </div>
                <p class="text-lg text-black mt-4 italic">
                    Sonsuzluğa giden yolculuğumuzun tarihi belli olduğunda, heyecanlı geri sayımımız burada başlayacak...
                </p>
            </div>
        </section>

        <!-- Hayal Defterimiz Section (Animasyon sınıfı eklendi) -->
        <section class="my-16 max-w-3xl mx-auto p-8 bg-white/80 backdrop-blur-sm rounded-lg shadow-lg fade-in-on-scroll">
            <!-- text-6xl SINIFI KALDIRILDI -->
            <h3 class="font-bold text-center text-red-600 mb-6 handwriting">Hayal Defterimiz</h3>
            <p class="text-center text-black text-lg italic mt-4 mb-8">
                Birlikte kurduğumuz hayaller, geleceğe dair ektiğimiz tohumlar... Bu defter, yolculuğumuzda gerçekleştireceğimiz hayallerle dolacak.
            </p>
        </section>

        <!-- Bizim Şarkımız Section --><section class="my-16 max-w-3xl mx-auto p-8 bg-white/80 backdrop-blur-sm rounded-lg shadow-lg text-center">
            <!-- text-6xl SINIFI KALDIRILDI -->
            <h3 class="font-bold text-center text-red-600 mb-6 handwriting">Bizim Şarkımız</h3>
            <div class="flex items-center justify-center p-6 bg-green-50 rounded-lg">
                 <div class="text-4xl text-red-600">
                    <i class="fas fa-music"></i>
                </div>
            </div>
        </section>

        <!-- Seyahatlerimiz Section (YENİ YAPI) --><section class="my-16 max-w-5xl mx-auto p-4 md:p-8 text-center">
            <!-- text-6xl SINIFI KALDIRILDI -->
            <h3 class="font-bold text-center text-red-600 mb-4 handwriting">Seyahatlerimiz</h3>
            <p class="text-center text-black italic">Birlikte keşfettiğimiz yerler, biriktirdiğimiz anılar... Yolculuğumuzun durakları burada hayat buluyor.</p>

            <div class="mt-8 text-center">
                <!-- DÜĞME RENKLERİ KIRMIZI OLARAK GÜNCELLENDİ -->
                <button id="toggle-travel-btn" class="inline-flex items-center justify-center py-2 px-6 border border-red-600 shadow-sm text-sm font-medium rounded-md text-red-600 bg-white hover:bg-red-50 focus:outline-none focus:ring-2 focus:ring-offset-2 focus:ring-red-500 transition-colors">
                    <span id="travel-toggle-text">Seyahatlerimizi Gör</span>
                    <i id="travel-toggle-icon" class="fas fa-chevron-down ml-2 transition-transform"></i>
                </button>
            </div>

            <!-- Collapsible Travel Container --><div id="travel-wrapper" class="hidden mt-8">
                <!-- Travel Folders Grid --><div class="grid grid-cols-1 sm:grid-cols-2 md:grid-cols-3 gap-6">
                    
                    <!-- Seyahat Klasörü 1 (Yer Tutucu) -->
                    <div class="travel-folder">
                        <div class="text-4xl text-green-500 mb-3">
                            <i class="fas fa-map-marked-alt"></i> <!-- Klasör ikonu -->
                        </div>
                        <h4 class="font-semibold text-lg text-black mb-1">Kapadokya Gezisi</h4>
                        <p class="text-sm text-black italic mt-2">Fotoğraflar buraya eklenecek...</p>
                        <!-- Buraya Kapadokya fotoğrafları için bir galeri eklenebilir -->
                    </div>

                    <!-- Seyahat Klasörü 2 (Yer Tutucu) -->
                    <div class="travel-folder">
                        <div class="text-4xl text-green-500 mb-3">
                            <i class="fas fa-map-marked-alt"></i>
                        </div>
                        <h4 class="font-semibold text-lg text-black mb-1">Ege Sahilleri</h4>
                        <p class="text-sm text-black italic mt-2">Fotoğraflar buraya eklenecek...</p>
                         <!-- Buraya Ege fotoğrafları için bir galeri eklenebilir -->
                    </div>

                    <!-- Seyahat Klasörü 3 (Yeni Eklendi - Yer Tutucu) -->
                    <div class="travel-folder">
                        <div class="text-4xl text-green-500 mb-3">
                             <i class="fas fa-ship"></i> <!-- Akdeniz için gemi ikonu -->
                        </div>
                        <h4 class="font-semibold text-lg text-black mb-1">Akdeniz Turu</h4>
                        <p class="text-sm text-black italic mt-2">Fotoğraflar buraya eklenecek...</p>
                         <!-- Buraya Akdeniz fotoğrafları için bir galeri eklenebilir -->
                    </div>

                </div>
            </div>
        </section>

        <!-- Photo Gallery Section --><section class="my-16 max-w-5xl mx-auto p-4 md:p-8 text-center">
            <!-- text-6xl SINIFI KALDIRILDI -->
            <h3 class="font-bold text-center text-red-600 mb-4 handwriting">Fotoğraf Galerimiz</h3>
            <p class="text-center text-black italic">İşte yolculuğumuzda biriktirdiğimiz anlardan ilk kareler... Bu galeri, zamanla daha nice güzel anıyla dolacak.</p>

            <div class="mt-8 text-center">
                <!-- DÜĞME RENKLERİ KIRMIZI OLARAK GÜNCELLENDİ -->
                <button id="toggle-gallery-btn" class="inline-flex items-center justify-center py-2 px-6 border border-red-600 shadow-sm text-sm font-medium rounded-md text-red-600 bg-white hover:bg-red-50 focus:outline-none focus:ring-2 focus:ring-offset-2 focus:ring-red-500 transition-colors">
                    <span id="gallery-toggle-text">Fotoğraf Galerisini Gör</span>
                    <i id="gallery-toggle-icon" class="fas fa-chevron-down ml-2 transition-transform"></i>
                </button>
            </div>

            <!-- Collapsible Gallery Container --><div id="gallery-wrapper" class="hidden mt-8">
                <!-- Photo Grid - Adjusted for larger photos --><div class="grid grid-cols-3 sm:grid-cols-4 md:grid-cols-5 lg:grid-cols-6 gap-1" id="gallery-grid">
                    
                    <!-- YENİ FOTOĞRAFLARI HEP BU ALANIN EN BAŞINA EKLEYİN --><!-- Yeni fotoğraf eklediğinizde, numarasını toplam fotoğraf sayısına göre ayarlayın. --><!-- Fotoğraf 6 (En Yeni) --><div class="photo-container group cursor-pointer">
                        <img src="https://i.imgur.com/wf9Xhs9.jpg" alt="Anı fotoğrafı 6" class="gallery-thumbnail w-full h-full object-cover">
                        <span class="photo-number">6</span>
                        <div class="photo-note">Lunapark Anısı</div>
                    </div>

                    <!-- Fotoğraf 5 (En Yeni) --><div class="photo-container group cursor-pointer">
                        <img src="https://i.imgur.com/G26zsUc.jpg" alt="Anı fotoğrafı 5" class="gallery-thumbnail w-full h-full object-cover">
                        <span class="photo-number">5</span>
                        <div class="photo-note">Beşiktaş</div>
                    </div>

                    <!-- Fotoğraf 4 (URL DÜZELTİLDİ VE NOT KALDIRILDI) --><div class="photo-container group cursor-pointer no-note">
                        <img src="https://i.imgur.com/PR2hWYz.jpg" alt="Anı fotoğrafı 4" class="gallery-thumbnail w-full h-full object-cover">
                        <span class="photo-number">4</span>
                        <!-- <div class="photo-note no-shadow">Aksaray</div> --> <!-- BU SATIR KALDIRILDI -->
                    </div>

                    <!-- Fotoğraf 3 --><div class="photo-container group cursor-pointer">
                        <img src="https://i.imgur.com/40oguJF.jpg" alt="Anı fotoğrafı 3" class="gallery-thumbnail w-full h-full object-cover">
                        <span class="photo-number">3</span>
                        <div class="photo-note">Çamlıca Kahvaltımız</div>
                    </div>

                    <!-- Fotoğraf 2 --><div class="photo-container group cursor-pointer">
                        <img src="https://i.imgur.com/KZpZnaa.jpg" alt="Anı fotoğrafı 2" class="gallery-thumbnail w-full h-full object-cover">
                        <span class="photo-number">2</span>
                        <div class="photo-note">Dünya Güzelim</div>
                    </div>
                    
                    <!-- Fotoğraf 1 (NOT OLMADIĞI İÇİN no-note SINIFI EKLENDİ) --><div class="photo-container group cursor-pointer no-note">
                        <img src="https://i.imgur.com/WnEibNN.jpg" alt="Anı fotoğrafı 1" class="gallery-thumbnail w-full h-full object-cover">
                        <span class="photo-number">1</span>
                    </div>
                
                </div>
            </div>
        </section>

        <!-- Video Galerimiz Section --><section class="my-16 max-w-5xl mx-auto p-4 md:p-8 text-center">
            <!-- text-6xl SINIFI KALDIRILDI -->
            <h3 class="font-bold text-center text-red-600 mb-4 handwriting">Video Galerimiz</h3>
            <!-- DÜZENLENEN METİN -->
            <p class="text-center text-black italic">Bazı duyguları kelimelerle anlatmak yetmez... Hikayemizin hareketli anlarına buradan göz atabilirsiniz.</p>

            <div class="mt-8 text-center">
                <!-- DÜĞME RENKLERİ KIRMIZI OLARAK GÜNCELLENDİ -->
                <button id="toggle-video-gallery-btn" class="inline-flex items-center justify-center py-2 px-6 border border-red-600 shadow-sm text-sm font-medium rounded-md text-red-600 bg-white hover:bg-red-50 focus:outline-none focus:ring-2 focus:ring-offset-2 focus:ring-red-500 transition-colors">
                    <span id="video-gallery-toggle-text">Video Galerisini Gör</span>
                    <i id="video-gallery-toggle-icon" class="fas fa-chevron-down ml-2 transition-transform"></i>
                </button>
            </div>

            <!-- Collapsible Video Gallery Container --><div id="video-gallery-wrapper" class="hidden mt-8">
                <!-- Video Grid - Adjusted for larger videos --><div class="grid grid-cols-1 sm:grid-cols-2 md:grid-cols-3 lg:grid-cols-4 gap-1" id="video-grid">
                    
                    <!-- YENİ VİDEOLARI HEP BU ALANIN EN BAŞINA EKLEYİN. En yeni video en yüksek numarayı alır. -->
                    <!-- Video 5 (En Yeni) --><div class="photo-container group cursor-pointer aspect-video" data-youtube-id="ChFa2GJ4e4U">
                        <img src="https://img.youtube.com/vi/ChFa2GJ4e4U/hqdefault.jpg" alt="Video thumbnail" class="w-full h-full object-cover">
                        <div class="absolute inset-0 flex items-center justify-center bg-black bg-opacity-40">
                            <i class="far fa-play-circle text-white text-6xl opacity-80 group-hover:opacity-100 transition-opacity"></i>
                        </div>
                        <span class="photo-number">5</span>
                        <div class="photo-note">Beşiktaş</div>
                    </div>
                    
                    <!-- Video 4 (En Yeni) --><div class="photo-container group cursor-pointer aspect-video" data-youtube-id="aim5II5vYpU">
                        <img src="https://img.youtube.com/vi/aim5II5vYpU/hqdefault.jpg" alt="Video thumbnail" class="w-full h-full object-cover">
                        <div class="absolute inset-0 flex items-center justify-center bg-black bg-opacity-40">
                            <i class="far fa-play-circle text-white text-6xl opacity-80 group-hover:opacity-100 transition-opacity"></i>
                        </div>
                        <span class="photo-number">4</span>
                        <div class="photo-note">Üsküdar</div>
                    </div>
                    
                    <!-- Video 3 (En Yeni) --><div class="photo-container group cursor-pointer aspect-video" data-youtube-id="uY6ZrwkbLjc">
                        <img src="https://img.youtube.com/vi/uY6ZrwkbLjc/hqdefault.jpg" alt="Video thumbnail" class="w-full h-full object-cover">
                        <div class="absolute inset-0 flex items-center justify-center bg-black bg-opacity-40">
                            <i class="far fa-play-circle text-white text-6xl opacity-80 group-hover:opacity-100 transition-opacity"></i>
                        </div>
                        <span class="photo-number">3</span>
                        <div class="photo-note">Lunapark</div>
                    </div>

                    <!-- Video 2 (En Yeni) --><div class="photo-container group cursor-pointer aspect-video" data-youtube-id="19aKq8FtYP8">
                        <img src="https://img.youtube.com/vi/19aKq8FtYP8/hqdefault.jpg" alt="Video thumbnail" class="w-full h-full object-cover">
                        <div class="absolute inset-0 flex items-center justify-center bg-black bg-opacity-40">
                            <i class="far fa-play-circle text-white text-6xl opacity-80 group-hover:opacity-100 transition-opacity"></i>
                        </div>
                        <span class="photo-number">2</span>
                        <div class="photo-note">Beşiktaş</div>
                    </div>

                    <!-- Video 1 (En Eski) --><div class="photo-container group cursor-pointer aspect-video" data-youtube-id="J466tfX1jzk">
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
        
        <!-- Teşekkür Section --><section class="my-16 max-w-3xl mx-auto p-8 bg-white/80 backdrop-blur-sm rounded-lg shadow-lg">
            <!-- text-6xl SINIFI KALDIRILDI -->
            <h3 class="font-bold text-center text-red-600 mb-6">Teşekkür</h3>
            <p class="text-center text-black text-lg italic mt-4">
                Bu mutlu yolculuğumuzda yanımızda olan, sevgileri ve destekleriyle bize güç veren herkese sonsuz teşekkürler.
            </p>
            <div class="mt-8 space-y-4">
                <p class="text-center text-black font-semibold">Bizi biz yapan, sevgileriyle her zaman en büyük destekçimiz olan canımız ailelerimize...</p>
                <p class="text-center text-black font-semibold">İyi günde, kötü günde her anımızda yanımızda olan, kahkahalarımızı ve hayallerimizi paylaştığımız değerli dostlarımıza...</p>
            </div>
        </section>

        <!-- Wish Box Section --><section class="my-16 max-w-3xl mx-auto p-8 bg-white/80 backdrop-blur-sm rounded-lg shadow-lg">
            <!-- text-6xl SINIFI KALDIRILDI -->
            <h3 class="font-bold text-center text-red-600 mb-6">Bizim İçin Bir Dilek Bırakın</h3>
             <form id="wish-form" action="https://formsubmit.co/arzuersin2025@gmail.com" method="POST" class="space-y-4">
                <!-- FormSubmit Ayarları --><input type="hidden" name="_subject" value="Arzu & Ersin Web Sitenizden Yeni Dilek!">
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
                 <!-- İletişim Bilgileri --><div class="pt-4 border-t border-slate-200">
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

    <!-- Footer --><footer class="text-center py-8 mt-12 bg-white/50">
        <p class="text-black flex items-center justify-center space-x-2">
            <span>Bu hikaye</span>
            <i class="fas fa-infinity text-red-500"></i>
            <span>kadar devam edecek...</span>
        </p>
        <p class="text-sm text-black mt-2">Arzu & Ersin</p>
    </footer>
    
    <!-- Image Modal --><div id="image-modal" class="fixed inset-0 bg-black bg-opacity-80 hidden items-center justify-center z-50 p-4">
        <span id="close-modal" class="absolute top-4 right-6 text-white text-5xl font-bold cursor-pointer hover:text-gray-300 transition-colors">&times;</span>
        <img id="modal-image" src="" alt="Büyütülmüş Fotoğraf" class="max-w-[90vw] max-h-[90vh] rounded-lg shadow-lg">
        <!-- Navigation Arrows --><span id="prev-photo" class="absolute top-1/2 left-4 -translate-y-1/2 text-white text-6xl font-bold cursor-pointer hover:text-gray-300 transition-colors select-none">&lt;</span>
        <span id="next-photo" class="absolute top-1/2 right-4 -translate-y-1/2 text-white text-6xl font-bold cursor-pointer hover:text-gray-300 transition-colors select-none">&gt;</span>
    </div>
    
    <!-- Video Modal --><div id="video-modal" class="fixed inset-0 bg-black bg-opacity-80 hidden items-center justify-center z-50 p-4">
        <span id="close-video-modal" class="absolute top-4 right-6 text-white text-5xl font-bold cursor-pointer hover:text-gray-300 transition-colors">&times;</span>
        <div class="aspect-video w-full max-w-4xl">
            <iframe id="modal-video-iframe" class="w-full h-full" src="" title="YouTube video player" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture; web-share" allowfullscreen></iframe>
        </div>
    </div>

    <!-- === Tek, Tamamlanmış JS Bloğu (orijinalle uyumlu) === -->
    <script>
    (function(){
        'use strict';

        /* =============== KULLANICI İSTEDİĞİ GÜNÜ BURADAN AYARLAYABİLİRSİN ===============
           Tarih örneği: "June 15, 2026 19:00:00" veya ISO: "2026-06-15T19:00:00"
           Eğer boş bırakılırsa (""), placeholder gösterilmeye devam eder.
         */
        const COUNTDOWN_DATE = ""; // <-- buraya tarih girersen countdown görünür

        /* ---------- Toggle butonları (gallery, video gallery, travel) ---------- */
        const toggleGalleryBtn = document.getElementById('toggle-gallery-btn');
        const galleryWrapper = document.getElementById('gallery-wrapper');
        const galleryToggleIcon = document.getElementById('gallery-toggle-icon');
        const galleryToggleText = document.getElementById('gallery-toggle-text');

        if (toggleGalleryBtn) {
            toggleGalleryBtn.addEventListener('click', () => {
                galleryWrapper.classList.toggle('hidden');
                const isHidden = galleryWrapper.classList.contains('hidden');
                galleryToggleIcon.classList.toggle('rotate-180', !isHidden);
                galleryToggleText.textContent = isHidden ? 'Fotoğraf Galerisini Gör' : 'Galeriyi Gizle';
            });
        }

        const toggleVideoGalleryBtn = document.getElementById('toggle-video-gallery-btn');
        const videoGalleryWrapper = document.getElementById('video-gallery-wrapper');
        const videoGalleryToggleIcon = document.getElementById('video-gallery-toggle-icon');
        const videoGalleryToggleText = document.getElementById('video-gallery-toggle-text');

        if (toggleVideoGalleryBtn) {
            toggleVideoGalleryBtn.addEventListener('click', () => {
                videoGalleryWrapper.classList.toggle('hidden');
                const isHidden = videoGalleryWrapper.classList.contains('hidden');
                videoGalleryToggleIcon.classList.toggle('rotate-180', !isHidden);
                videoGalleryToggleText.textContent = isHidden ? 'Video Galerisini Gör' : 'Galeriyi Gizle';
            });
        }

        const toggleTravelBtn = document.getElementById('toggle-travel-btn');
        const travelWrapper = document.getElementById('travel-wrapper');
        const travelToggleIcon = document.getElementById('travel-toggle-icon');
        const travelToggleText = document.getElementById('travel-toggle-text');

        if (toggleTravelBtn) {
            toggleTravelBtn.addEventListener('click', () => {
                travelWrapper.classList.toggle('hidden');
                const isHidden = travelWrapper.classList.contains('hidden');
                travelToggleIcon.classList.toggle('rotate-180', !isHidden);
                travelToggleText.textContent = isHidden ? 'Seyahatlerimizi Gör' : 'Seyahatleri Gizle';
            });
        }

        /* ---------- Fotoğraf galerisi / modal ---------- */
        const galleryGrid = document.getElementById('gallery-grid');
        const galleryPhotosSelector = '.gallery-thumbnail';
        let galleryPhotos = [];
        let currentPhotoIndex = 0;

        function refreshGalleryPhotos() {
            const photoEls = galleryGrid ? Array.from(galleryGrid.querySelectorAll(galleryPhotosSelector)) : [];
            galleryPhotos = photoEls.map(img => img.src || img.getAttribute('data-src') || img.currentSrc);
            return photoEls;
        }

        function openImageModalByIndex(index) {
            const imageModal = document.getElementById('image-modal');
            const modalImage = document.getElementById('modal-image');
            if (!galleryPhotos.length) refreshGalleryPhotos();
            currentPhotoIndex = (index + galleryPhotos.length) % galleryPhotos.length;
            modalImage.src = galleryPhotos[currentPhotoIndex];
            imageModal.classList.remove('hidden');
            imageModal.classList.add('flex');
        }

        function closeImageModal() {
            const imageModal = document.getElementById('image-modal');
            const modalImage = document.getElementById('modal-image');
            if (imageModal) {
                imageModal.classList.add('hidden');
                imageModal.classList.remove('flex');
            }
            if (modalImage) modalImage.src = "";
        }

        function showNextPhoto() {
            if (!galleryPhotos.length) refreshGalleryPhotos();
            currentPhotoIndex = (currentPhotoIndex + 1) % galleryPhotos.length;
            document.getElementById('modal-image').src = galleryPhotos[currentPhotoIndex];
        }
        function showPrevPhoto() {
            if (!galleryPhotos.length) refreshGalleryPhotos();
            currentPhotoIndex = (currentPhotoIndex - 1 + galleryPhotos.length) % galleryPhotos.length;
            document.getElementById('modal-image').src = galleryPhotos[currentPhotoIndex];
        }

        // Attach click events to thumbnails (initial load + if dynamic new imgs added later call refreshEvents())
        function refreshGalleryEvents() {
            const photoEls = refreshGalleryPhotos();
            photoEls.forEach((imgEl, idx) => {
                // Avoid adding multiple listeners
                imgEl.removeEventListener('click', imgEl._clickHandler || (()=>{}));
                const handler = () => openImageModalByIndex(idx);
                imgEl.addEventListener('click', handler);
                imgEl._clickHandler = handler;
            });
        }

        // initialize
        refreshGalleryEvents();

        // Modal controls
        const closeModalBtn = document.getElementById('close-modal');
        const prevBtn = document.getElementById('prev-photo');
        const nextBtn = document.getElementById('next-photo');

        if (closeModalBtn) closeModalBtn.addEventListener('click', closeImageModal);
        if (prevBtn) prevBtn.addEventListener('click', (e)=>{ e.stopPropagation(); showPrevPhoto(); });
        if (nextBtn) nextBtn.addEventListener('click', (e)=>{ e.stopPropagation(); showNextPhoto(); });

        // click outside to close image modal
        const imageModalEl = document.getElementById('image-modal');
        if (imageModalEl) {
            imageModalEl.addEventListener('click', (e) => {
                if (e.target === imageModalEl) closeImageModal();
            });
        }

        /* ---------- Video modal ---------- */
        const videoModal = document.getElementById('video-modal');
        const videoIframe = document.getElementById('modal-video-iframe');
        const closeVideoModalBtn = document.getElementById('close-video-modal');
        const videoGrid = document.getElementById('video-grid');

        function openVideoModal(videoId) {
            if (!videoId) return;
            // YouTube embed linkini -nocookie olarak değiştirdim. Bu, kısıtlama sorunlarına yardımcı olabilir.
            if (videoIframe) videoIframe.src = `https://www.youtube-nocookie.com/embed/${videoId}?autoplay=1&rel=0`;
            if (videoModal) {
                videoModal.classList.remove('hidden');
                videoModal.classList.add('flex');
            }
        }
        function closeVideoModal() {
            if (videoIframe) videoIframe.src = '';
            if (videoModal) {
                videoModal.classList.add('hidden');
                videoModal.classList.remove('flex');
            }
        }

        if (videoGrid) {
            videoGrid.addEventListener('click', (e) => {
                const item = e.target.closest('[data-youtube-id]');
                if (item) {
                    const vid = item.dataset.youtubeId;
                    openVideoModal(vid);
                }
            });
        }
        if (closeVideoModalBtn) closeVideoModalBtn.addEventListener('click', closeVideoModal);
        if (videoModal) {
            videoModal.addEventListener('click', (e) => {
                if (e.target === videoModal) closeVideoModal();
            });
        }

        /* ---------- Keyboard escape to close modals & arrow navigation for images ---------- */
        document.addEventListener('keydown', (e) => {
            const imageModal = document.getElementById('image-modal');
            const videoModalLocal = document.getElementById('video-modal');
            if (e.key === 'Escape') {
                if (imageModal && !imageModal.classList.contains('hidden')) closeImageModal();
                if (videoModalLocal && !videoModalLocal.classList.contains('hidden')) closeVideoModal();
            }
            // left/right arrows for image navigation when modal is open
            if (e.key === 'ArrowRight') {
                if (imageModal && !imageModal.classList.contains('hidden')) showNextPhoto();
            }
            if (e.key === 'ArrowLeft') {
                if (imageModal && !imageModal.classList.contains('hidden')) showPrevPhoto();
            }
        });

        /* ---------- Wish form validation (orijinal #contact-error kullanılıyor) ---------- */
        const wishForm = document.getElementById('wish-form');
        if (wishForm) {
            wishForm.addEventListener('submit', function(e){
                const contactInput = document.getElementById('contact');
                const errorElement = document.getElementById('contact-error');
                const isContactFilled = contactInput && contactInput.value.trim() !== '';
                if (!isContactFilled) {
                    e.preventDefault();
                    if (errorElement) errorElement.classList.remove('hidden');
                    // focus contact input for convenience
                    if (contactInput) contactInput.focus();
                } else {
                    // hide error and allow submit
                    if (errorElement) errorElement.classList.add('hidden');
                    // form will submit to formsubmit.co as configured
                }
            });
        }

        /* ---------- Countdown logic: COUNTDOWN_DATE ayarlıysa göster, değilse placeholder kalsın ---------- */
        (function setupCountdown(){
            if (!COUNTDOWN_DATE) {
                // keep placeholder (do nothing)
                return;
            }
            const countDownDate = new Date(COUNTDOWN_DATE).getTime();
            const countdownTimer = document.getElementById("countdown-timer");
            const countdownPlaceholder = document.getElementById("countdown-placeholder");
            const headerCountdown = document.getElementById("header-countdown");

            if (countdownTimer && countdownPlaceholder && headerCountdown) {
                countdownPlaceholder.classList.add("hidden");
                countdownTimer.classList.remove("hidden");
                countdownTimer.classList.add("grid");
                headerCountdown.classList.remove("hidden");
            }

            const interval = setInterval(function() {
                const now = new Date().getTime();
                const distance = countDownDate - now;

                const days = Math.floor(distance / (1000 * 60 * 60 * 24));
                const hours = Math.floor((distance % (1000 * 60 * 60 * 24)) / (1000 * 60 * 60));
                const minutes = Math.floor((distance % (1000 * 60 * 60)) / (1000 * 60));
                const seconds = Math.floor((distance % (1000 * 60)) / 1000);

                if (document.getElementById("days")) {
                    document.getElementById("days").innerText = Math.max(days,0);
                    document.getElementById("hours").innerText = Math.max(hours,0);
                    document.getElementById("minutes").innerText = Math.max(minutes,0);
                    document.getElementById("seconds").innerText = Math.max(seconds,0);
                    document.getElementById("header-days").innerText = Math.max(days,0);
                    document.getElementById("header-hours").innerText = Math.max(hours,0);
                    document.getElementById("header-minutes").innerText = Math.max(minutes,0);
                }

                if (distance < 0) {
                    clearInterval(interval);
                    if (countdownTimer) countdownTimer.innerHTML = '<p class="col-span-full text-xl text-green-600">Ve o güzel gün geldi!</p>';
                    if (headerCountdown) headerCountdown.innerHTML = '❤️';
                }
            }, 1000);
        })();

        /* ---------- IntersectionObserver for travel items (already styled) ---------- */
        /* .fade-in-on-scroll sınıfı buraya eklendi */
        const journeyItems = document.querySelectorAll(".travel-folder, .journey-item, .fade-in-on-scroll");
        if ('IntersectionObserver' in window) {
            const observer = new IntersectionObserver(entries => {
                entries.forEach(entry => {
                    if (entry.isIntersecting) {
                        entry.target.classList.add('visible');
                    }
                });
            }, {threshold: 0.15});
            journeyItems.forEach(item => observer.observe(item));
        } else {
            // fallback: just add visible
            journeyItems.forEach(it => it.classList.add('visible'));
        }

        /* ---------- Timeline Animation Observer ---------- */
        const timelineObserver = new IntersectionObserver((entries) => {
            entries.forEach((entry, index) => {
                if (entry.isIntersecting) {
                    setTimeout(() => {
                        entry.target.classList.add('animate');
                        entry.target.querySelector('.timeline-content').classList.add('animate');
                    }, index * 300); // Staggered delay
                }
            });
        }, { threshold: 0.5 });

        const timelineItems = document.querySelectorAll('.timeline-item');
        timelineItems.forEach(item => timelineObserver.observe(item));

        /* ---------- If you dynamically add gallery images later, call refreshEvents() ---------- */
        window.refreshGalleryEvents = refreshGalleryEvents;
        /* örnek kullanım: yeni fotoğraf ekledikten sonra window.refreshGalleryEvents(); çağır */
    })();
    </script>

    <!-- (Orijinal sayfanda eski, kısmi/eksik script blokları kaldırıldı ve yukarıdaki tek blokla değiştirildi.) -->
</body>
</html>

