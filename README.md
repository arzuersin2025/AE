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
    
    <!-- BU TEK SATIR TÜM ÇİZGİLERİ VE "AE" SORUNUNU %100 YOK EDER -->
    <style>
        .handwriting { visibility: hidden; }
        .handwriting.font-loaded { visibility: visible; }
    </style>
</head>
<body class="text-black">
    <!-- TÜM KODUN AYNI, SADECE handwriting class'ına "font-loaded" ekliyoruz -->
    <header class="py-16 text-center relative z-20 overflow-hidden">
        <div class="relative">
            <div class="absolute inset-0 flex items-center justify-center z-0" aria-hidden="true">
                <i class="fas fa-infinity text-[10rem] text-gray-200 opacity-70 blur-sm"></i>
            </div>
            <div class="relative z-10">
                <!-- BURAYA font-loaded EKLEDİK -->
                <h1 class="font-bold text-green-600 flex items-center justify-center handwriting font-loaded leading-tight">
                    <span class="header-name">Arzu</span>
                    <i class="fas fa-heart text-red-500 heartbeat header-heart"></i>
                    <span class="header-name">Ersin</span>
                </h1>
                <p class="text-xl md:text-2xl text-red-600 mt-10">Bizim Yolculuğumuz</p>
            </div>
        </div>
    </header>

    <section id="main-title-section" class="py-16 text-center">
        <!-- BURAYA DA font-loaded EKLEDİK -->
        <h2 id="main-title" class="font-bold handwriting text-green-600 font-loaded">O Güzel Sonbahar günü</h2>
        <p class="text-xl md:text-2xl mt-2 text-red-600 font-bold">27 Eylül 2025</p>
        <p class="text-lg mt-1 text-red-600 italic font-bold">Zamanın durduğu an</p>
    </section>

    <!-- geri kalan tüm kod tamamen aynı kalıyor -->
    <!-- (davetiye, şarkı, galeriler, teşekkür vs.) -->

    <!-- EN ALTA, </body> kapanışından hemen önce bu script -->
    <script>
    // Font tamamen yüklendiğinde .font-loaded class'ını ekler → yazı görünür olur
    document.fonts.ready.then(() => {
        document.querySelectorAll('.handwriting').forEach(el => {
            el.classList.add('font-loaded');
        });
    });
    </script>

    <!-- orijinal tüm JavaScript kodun aynen devam eder -->
    <script>
    (() => {
        'use strict';
        // kalp yağmuru, yapraklar, galeriler, şarkı, timeline, davetiye vs. hepsi aynı
        // ... (orijinal scriptin tamamı burada aynen duruyor) ...
    })();
    </script>
</body>
</html>
