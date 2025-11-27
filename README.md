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
    <style>
        /* Diğer iki başlığın çizgisini de yok edelim */
        #main-title, #sonbahar-baslik {
            border-bottom: none !important;
        }
    </style>
</head>
<body class="text-black">
    <div id="background-leaves-pattern"></div>
    <div id="falling-leaves-container"></div>
    <div id="heart-rain-btn" title="Kalp yağmuru başlat!">
        <i class="fas fa-heart heartbeat"></i>
        <span>Dokun</span>
    </div>

    <!-- TEK DEĞİŞİKLİK: style="border: none !important;" -->
    <header class="py-16 text-center relative z-20 overflow-hidden" style="border: none !important; border-bottom: 0 !important;">
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
                <h1 class="font-bold text-green-600 flex items-center justify-center handwriting leading-tight">
                    <span class="header-name">Arzu</span>
                    <i class="fas fa-heart text-red-500 heartbeat header-heart"></i>
                    <span class="header-name">Ersin</span>
                </h1>
                <p class="text-xl md:text-2xl text-red-600 mt-10">Bizim Yolculuğumuz</p>
            </div>
        </div>
    </header>

    <section id="main-title-section" class="py-16 text-center">
        <h2 id="main-title" class="font-bold handwriting text-green-600">O Güzel Sonbahar günü</h2>
        <p class="text-xl md:text-2xl mt-2 text-red-600 font-bold">27 Eylül 2025</p>
        <p class="text-lg mt-1 text-red-600 italic font-bold">Zamanın durduğu an</p>
    </section>

    <!-- TÜM KALAN KOD TAMAMEN AYNI (davetiye, şarkı, galeriler, teşekkür vs.) -->
    <!-- Davetiye Modal -->
    <div id="invitation-modal">
        <span id="close-invitation">×</span>
        <img src="https://i.imgur.com/pkKrbgb.jpeg" alt="Arzu & Ersin Düğün Davetiyesi">
    </div>

    <!-- JavaScript aynı -->
    <script>
    (() => {
        'use strict';
        // Tüm script aynı kalıyor...
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
