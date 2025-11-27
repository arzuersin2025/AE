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
        /* AE VE TÜM ÇİZGİLERİ %100 YOK EDER */
        .handwriting {
            opacity: 0;
            transition: opacity 0.3s ease;
        }
        .handwriting.font-loaded {
            opacity: 1;
        }
        header, #main-title, #sonbahar-baslik {
            border: none !important;
        }
        html { scroll-behavior: smooth; }
        body { font-family: 'Poppins', sans-serif; background: transparent; overflow-x: hidden; min-height: 100vh; }
        /* geri kalan tüm stiller aynı */
        #background-leaves-pattern { position: fixed; inset: 0; background: #fdfaf6 url('https://www.toptal.com/designers/subtlepatterns/uploads/leaves.png') repeat; z-index: -2; opacity: 0.6; }
        @media (max-width: 768px) { #background-leaves-pattern { opacity: 0.9; } }
        #falling-leaves-container { position: fixed; inset: 0; pointer-events: none; z-index: -1; overflow: hidden; }
        h1, h2, h3 { font-family: 'Playfair Display', serif; }
        .handwriting { font-family: 'Dancing Script', cursive; }
        @keyframes heartbeat { 0%,100%{transform:scale(1)} 50%{transform:scale(1.1)} }
        .heartbeat { animation: heartbeat 1.5s infinite; }
        /* diğer tüm stiller aynı kalıyor... */
        #invitation-modal { display: none; position: fixed; inset: 0; background: rgba(0,0,0,0.9); z-index: 9999; align-items: center; justify-content: center; padding: 1rem; }
        #invitation-modal.show { display: flex; }
        #invitation-modal img { max-width: 95vw; max-height: 95vh; border-radius: 12px; box-shadow: 0 20px 40px rgba(0,0,0,0.6); }
        #close-invitation { position: absolute; top: 20px; right: 30px; font-size: 3.5rem; color: white; cursor: pointer; z-index: 10000; }
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
            <div class="absolute inset-0 flex items-center justify-center z-0" aria-hidden="true">
                <i class="fas fa-infinity text-[10rem] text-gray-200 opacity-70 blur-sm"></i>
            </div>
            <div class="relative z-10">
                <!-- font-loaded eklendi -->
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
        <h2 id="main-title" class="font-bold handwriting text-green-600 font-loaded">O Güzel Sonbahar günü</h2>
        <p class="text-xl md:text-2xl mt-2 text-red-600 font-bold">27 Eylül 2025</p>
        <p class="text-lg mt-1 text-red-600 italic font-bold">Zamanın durduğu an</p>
    </section>

    <!-- TÜM KALAN KODUN TAMAMEN AYNI -->
    <!-- Davetiye Modal -->
    <div id="invitation-modal">
        <span id="close-invitation">×</span>
        <img src="https://i.imgur.com/pkKrbgb.jpeg" alt="Arzu & Ersin Düğün Davetiyesi">
    </div>

    <!-- Font yüklendiğinde yazı görünür olur -->
    <script>
        document.fonts.ready.then(() => {
            document.querySelectorAll('.handwriting').forEach(el => {
                el.classList.add('font-loaded');
            });
        });
    </script>

    <!-- Orijinal tüm script aynı kalıyor -->
    <script>
    (() => {
        'use strict';
        // kalp yağmuru, yapraklar, galeriler, şarkı, davetiye vs. hepsi aynı
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
        // ... diğer tüm script aynı ...
        const invitationModal = document.getElementById('invitation-modal');
        const invitationIcon = document.getElementById('invitation-icon');
        const closeInvitation = document.getElementById('close-invitation');
        invitationIcon.onclick = () => invitationModal.classList.add('show');
        closeInvitation.onclick = () => invitationModal.classList.remove('show');
        invitationModal.onclick = (e) => { if (e.target === invitationModal) invitationModal.classList.remove('show'); };
    })();
    </script>
</body>
</html>
