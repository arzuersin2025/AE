<html lang="tr">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Arzu & Ersin | Bizim Hikayemiz</title>
    <!-- Tailwind CSS for styling --><script src="https://cdn.tailwindcss.com"></script>
    <link rel="preconnect" href="https://fonts.googleapis.com">
    <link rel="preconnect" href="https://fonts.gstatic.com" crossorigin>
    <link href="https://fonts.googleapis.com/css2?family=Playfair+Display:wght@400;700&family=Poppins:wght@300;400;600&family=Dancing+Script:wght@700&display=swap" rel="stylesheet">
    <!-- Font Awesome for icons (Corrected integrity attribute) --><link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.5.1/css/all.min.css" xintegrity="sha512-DTOQO9RWCH3ppGqcWaEA1BIZOC6xxalwEsw9c2QQeAIftl+Vegovlnee1c9QX4TctnWMn13TZye+giMm8e2LwA==" crossorigin="anonymous" referrerpolicy="no-referrer" />
    <!-- Prevents browser from generating a default favicon with a transparent pixel --><link rel="icon" href="data:image/png;base64,iVBORw0KGgoAAAANAAAAAEAAAABCAQAAAC1HAwCAAAAC0lEQVR42mNkYAAAAAYAAjCB0C8AAAAASUVORK5CYII=">
    <style>
        /* Custom styles for typography and theme */
        html {
            scroll-behavior: smooth;
        }
        body {
            font-family: 'Poppins', sans-serif;
            background-image: url('https://www.toptal.com/designers/subtlepatterns/uploads/leaves.png');
            background-color: #fdfaf6; /* A warm background color behind the pattern */
        }
        h1, h2, h3 {
            font-family: 'Playfair Display', serif;
        }
        .handwriting {
            font-family: 'Dancing Script', cursive;
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
        /* Specific rule to ensure main title is always large */
        #main-title {
            font-size: 5rem; /* 80px */
            line-height: 1.1;
        }
        @media (min-width: 768px) { /* Corresponds to md: breakpoint */
            #main-title {
                font-size: 7rem; /* 112px */
            }
        }
        /* Forcefully remove borders/shadows causing thin lines on deployment */
        header, #main-title-section {
            border: none !important;
            box-shadow: none !important;
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
    </style>
</head>
<body class="text-slate-700">

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
                <p class="text-lg text-slate-500 mt-1">Bizim Yolculuğumuz</p>
            </div>
        </div>
    </header>

    <!-- Page Title Section --><section id="main-title-section" class="py-16 text-center">
        <h2 id="main-title" class="font-bold handwriting text-green-600">O Güzel Sonbahar</h2>
        <p class="text-xl md:text-2xl mt-2 text-slate-500">27 Eylül 2025</p>
        <p class="text-lg mt-1 text-slate-500 italic">Zamanın durduğu an</p>
    </section>

    <!-- Main Content --><main class="container mx-auto px-6 pb-12">

        <!-- Our Story Section --><section class="max-w-3xl mx-auto my-12 text-center bg-white/80 backdrop-blur-sm p-8 rounded-lg shadow-lg">
            <h3 class="text-3xl font-bold text-green-600 mb-4">İlk Adım</h3>
            <p class="text-lg leading-relaxed text-slate-600">
                Her büyük hikayenin bir başlangıç anı vardır. Bizimki, 27 Eylül 2025'te, yaprakların sarıya döndüğü, havanın tatlı bir serinliğe büründüğü o güzel sonbahar gününde başladı. O gün, sadece iki insan tanışmadı; aynı zamanda ortak bir geleceğe atılacak ilk adımın temelleri atıldı. O günden beri her anımızı, o ilk günkü heyecan ve samimiyetle doldurarak, birlikte büyüyoruz. Bu site, bir sonbahar gününde başlayan ve sonsuzluğa uzanan yolculuğumuzun en güzel anılarını saklamak için...
            </p>
            <div class="text-4xl text-green-500 mt-8 heartbeat">
                ❤️
            </div>
        </section>

        <!-- Poem Section --><section class="my-16 max-w-3xl mx-auto p-8 bg-white/80 backdrop-blur-sm rounded-lg shadow-lg text-center">
            <blockquote class="text-lg italic text-slate-600 leading-loose">
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
        </section>

        <!-- Hayal Defterimiz Section --><section class="my-16 max-w-3xl mx-auto p-8 bg-white/80 backdrop-blur-sm rounded-lg shadow-lg">
            <h3 class="text-3xl font-bold text-center text-green-600 mb-6">Hayal Defterimiz</h3>
            <p class="text-center text-slate-600 text-lg italic mt-4 mb-8">
                Birlikte kurduğumuz hayaller, geleceğe dair ektiğimiz tohumlar... Bu defter, yolculuğumuzda gerçekleştireceğimiz hayallerle dolacak.
            </p>
        </section>

        <!-- Countdown Section --><section id="countdown-section" class="my-16 max-w-3xl mx-auto p-8 bg-white/80 backdrop-blur-sm rounded-lg shadow-lg text-center">
            <h3 class="text-3xl font-bold text-center text-green-600 mb-6">Büyük Güne Geri Sayım</h3>
            
            <!-- This part will be shown when the date is set --><div id="countdown-timer" class="hidden grid grid-cols-2 md:grid-cols-4 gap-4 text-center">
                <div><div id="days" class="text-4xl font-bold text-green-500">0</div><span class="text-slate-500">Gün</span></div>
                <div><div id="hours" class="text-4xl font-bold text-green-500">0</div><span class="text-slate-500">Saat</span></div>
                <div><div id="minutes" class="text-4xl font-bold text-green-500">0</div><span class="text-slate-500">Dakika</span></div>
                <div><div id="seconds" class="text-4xl font-bold text-green-500">0</div><span class="text-slate-500">Saniye</span></div>
            </div>

            <!-- This is the placeholder part --><div id="countdown-placeholder" class="my-4">
                <div class="text-8xl text-red-500">
                    ∞
                </div>
                <p class="text-lg text-slate-600 mt-4 italic">
                    Sonsuzluğa giden yolculuğumuzun tarihi belli olduğunda, heyecanlı geri sayımımız burada başlayacak...
                </p>
            </div>
        </section>

        <!-- Bizim Şarkımız Section --><section class="my-16 max-w-3xl mx-auto p-8 bg-white/80 backdrop-blur-sm rounded-lg shadow-lg text-center">
            <h3 class="text-3xl font-bold text-center text-green-600 mb-6">Bizim Şarkımız</h3>
            <div class="flex items-center justify-center p-6 bg-green-50 rounded-lg">
                 <div class="text-4xl text-green-500 mr-4">
                    <i class="fas fa-music"></i>
                </div>
                <div>
                    <p class="font-semibold text-lg text-slate-700">Şarkı Adı</p>
                    <p class="text-slate-500">Sanatçı Adı</p>
                </div>
            </div>
        </section>
        
        <!-- Photo Gallery Section --><section class="my-16 max-w-5xl mx-auto p-4 md:p-8 text-center">
            <h3 class="text-3xl font-bold text-center text-green-600 mb-4">Fotoğraf Galerimiz</h3>
            <p class="text-center text-slate-500 italic">İşte yolculuğumuzda biriktirdiğimiz anlardan ilk kareler... Bu galeri, zamanla daha nice güzel anıyla dolacak.</p>

            <div class="mt-8 text-center">
                <button id="toggle-gallery-btn" class="inline-flex items-center justify-center py-2 px-6 border border-green-600 shadow-sm text-sm font-medium rounded-md text-green-600 bg-white hover:bg-green-50 focus:outline-none focus:ring-2 focus:ring-offset-2 focus:ring-green-500 transition-colors">
                    <span id="gallery-toggle-text">Fotoğraf Galerisini Gör</span>
                    <i id="gallery-toggle-icon" class="fas fa-chevron-down ml-2 transition-transform"></i>
                </button>
            </div>

            <!-- Collapsible Gallery Container --><div id="gallery-wrapper" class="hidden mt-8">
                <!-- Photo Grid - Adjusted for larger photos --><div class="grid grid-cols-3 sm:grid-cols-4 md:grid-cols-5 lg:grid-cols-6 gap-1" id="gallery-grid">
                    
                    <!-- YENİ FOTOĞRAFLARI HEP BU ALANIN EN BAŞINA EKLEYİN --><!-- Yeni fotoğraf eklediğinizde, numarasını toplam fotoğraf sayısına göre ayarlayın. --><!-- Fotoğraf 5 (En Yeni) --><div class="photo-container group cursor-pointer">
                        <img src="https://i.imgur.com/G26zsUc.jpg" alt="Anı fotoğrafı 5" class="gallery-thumbnail w-full h-full object-cover">
                        <span class="photo-number">5</span>
                        <div class="photo-note">Beşiktaş</div>
                    </div>

                    <!-- Fotoğraf 4 --><div class="photo-container group cursor-pointer">
                        <img src="https://i.imgur.com/PR2hWYz.jpg" alt="Anı fotoğrafı 4" class="gallery-thumbnail w-full h-full object-cover">
                        <span class="photo-number">4</span>
                        <div class="photo-note">Aksaray</div>
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
                    
                    <!-- Fotoğraf 1 --><div class="photo-container group cursor-pointer">
                        <img src="https://i.imgur.com/WnEibNN.jpg" alt="Anı fotoğrafı 1" class="gallery-thumbnail w-full h-full object-cover">
                        <span class="photo-number">1</span>
                    </div>
                
                </div>
            </div>
        </section>

        <!-- Video Galerimiz Section --><section class="my-16 max-w-5xl mx-auto p-4 md:p-8 text-center">
            <h3 class="text-3xl font-bold text-center text-green-600 mb-4">Video Galerimiz</h3>
            <p class="text-center text-slate-500 italic">Bazı duyguları kelimelerle anlatmak yetmez... Hikayemizi bir de bizden dinleyin istedik. Sevdiklerimizle ve birbirimizle paylaşmak istediğimiz samimi videolarımızı hazırladığımızda burada bulabilirsiniz.</p>

            <div class="mt-8 text-center">
                <button id="toggle-video-gallery-btn" class="inline-flex items-center justify-center py-2 px-6 border border-green-600 shadow-sm text-sm font-medium rounded-md text-green-600 bg-white hover:bg-green-50 focus:outline-none focus:ring-2 focus:ring-offset-2 focus:ring-green-500 transition-colors">
                    <span id="video-gallery-toggle-text">Video Galerisini Gör</span>
                    <i id="video-gallery-toggle-icon" class="fas fa-chevron-down ml-2 transition-transform"></i>
                </button>
            </div>

            <!-- Collapsible Video Gallery Container --><div id="video-gallery-wrapper" class="hidden mt-8">
                <!-- Video Grid - Adjusted for larger videos --><div class="grid grid-cols-1 sm:grid-cols-2 md:grid-cols-3 lg:grid-cols-4 gap-1" id="video-grid">
                    
                    <!-- YENİ VİDEOLARI HEP BU ALANIN EN BAŞINA EKLEYİN. En yeni video en yüksek numarayı alır. --><!-- Video 2 (En Yeni) --><div class="photo-container group cursor-pointer aspect-video" data-youtube-id="19aKq8FtYP8">
                        <img src="https://img.youtube.com/vi/19aKq8FtYP8/hqdefault.jpg" alt="Video thumbnail" class="w-full h-full object-cover">
                        <div class="absolute inset-0 flex items-center justify-center bg-black bg-opacity-40">
                            <i class="far fa-play-circle text-white text-6xl opacity-80 group-hover:opacity-100 transition-opacity"></i>
                        </div>
                        <span class="photo-number">2</span>
                    </div>

                    <!-- Video 1 (En Eski) --><div class="photo-container group cursor-pointer aspect-video" data-youtube-id="J466tfX1jzk">
                        <img src="https://img.youtube.com/vi/J466tfX1jzk/hqdefault.jpg" alt="Video thumbnail" class="w-full h-full object-cover">
                        <div class="absolute inset-0 flex items-center justify-center bg-black bg-opacity-40">
                            <i class="far fa-play-circle text-white text-6xl opacity-80 group-hover:opacity-100 transition-opacity"></i>
                        </div>
                        <span class="photo-number">1</span>
                    </div>

                </div>
            </div>
        </section>
        
        <!-- Teşekkür Section --><section class="my-16 max-w-3xl mx-auto p-8 bg-white/80 backdrop-blur-sm rounded-lg shadow-lg">
            <h3 class="text-3xl font-bold text-center text-green-600 mb-6">Teşekkür</h3>
            <p class="text-center text-slate-600 text-lg italic mt-4">
                Bu mutlu yolculuğumuzda yanımızda olan, sevgileri ve destekleriyle bize güç veren herkese sonsuz teşekkürler.
            </p>
            <div class="mt-8 space-y-4">
                <p class="text-center text-slate-700 font-semibold">Bizi biz yapan, sevgileriyle her zaman en büyük destekçimiz olan canımız ailelerimize...</p>
                <p class="text-center text-slate-700 font-semibold">İyi günde, kötü günde her anımızda yanımızda olan, kahkahalarımızı ve hayallerimizi paylaştığımız değerli dostlarımıza...</p>
            </div>
        </section>

        <!-- Wish Box Section --><section class="my-16 max-w-3xl mx-auto p-8 bg-white/80 backdrop-blur-sm rounded-lg shadow-lg">
            <h3 class="text-3xl font-bold text-center text-green-600 mb-6">Bizim İçin Bir Dilek Bırakın</h3>
             <form id="wish-form" action="https://formsubmit.co/arzuersin2025@gmail.com" method="POST" class="space-y-4">
                <!-- FormSubmit Ayarları --><input type="hidden" name="_subject" value="Arzu & Ersin Web Sitenizden Yeni Dilek!">
                <input type="text" name="_honey" style="display:none">
                <input type="hidden" name="_captcha" value="false">

                <div>
                    <label for="name" class="block text-sm font-medium text-slate-600">Adınız</label>
                    <input type="text" name="name" id="name" class="mt-1 block w-full px-3 py-2 bg-white border border-slate-300 rounded-md shadow-sm placeholder-slate-400 focus:outline-none focus:ring-green-500 focus:border-green-500 sm:text-sm" placeholder="Adınız ve Soyadınız" required>
                </div>
                <div>
                    <label for="message" class="block text-sm font-medium text-slate-600">Dileğiniz</label>
                    <textarea id="message" name="message" rows="4" class="mt-1 block w-full px-3 py-2 bg-white border border-slate-300 rounded-md shadow-sm placeholder-slate-400 focus:outline-none focus:ring-green-500 focus:border-green-500 sm:text-sm" placeholder="Bizim için güzel bir dilek..." required></textarea>
                </div>
                 <!-- İletişim Bilgileri --><div class="pt-4 border-t border-slate-200">
                    <p class="text-sm text-slate-500 mb-2 text-center">Size teşekkür edebilmemiz için lütfen aşağıdaki bilgilerden en az birını doldurun.</p>
                    <div>
                         <label for="contact" class="block text-sm font-medium text-slate-600">E-posta ya da Telefon</label>
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
        <p class="text-slate-600 flex items-center justify-center space-x-2">
            <span>Bu hikaye</span>
            <i class="fas fa-infinity text-red-500"></i>
            <span>kadar devam edecek...</span>
        </p>
        <p class="text-sm text-slate-400 mt-2">Arzu & Ersin</p>
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

    <script>
        // Toggle Gallery Visibility
        const toggleGalleryBtn = document.getElementById('toggle-gallery-btn');
        const galleryWrapper = document.getElementById('gallery-wrapper');
        const galleryToggleIcon = document.getElementById('gallery-toggle-icon');
        const galleryToggleText = document.getElementById('gallery-toggle-text');

        if (toggleGalleryBtn) {
            toggleGalleryBtn.addEventListener('click', () => {
                galleryWrapper.classList.toggle('hidden');
                const isHidden = galleryWrapper.classList.contains('hidden');
                
                if(isHidden) {
                    galleryToggleIcon.classList.remove('rotate-180');
                    galleryToggleText.textContent = 'Fotoğraf Galerisini Gör';
                } else {
                    galleryToggleIcon.classList.add('rotate-180');
                    galleryToggleText.textContent = 'Galeriyi Gizle';
                }
            });
        }
        
        // Toggle Video Gallery Visibility
        const toggleVideoGalleryBtn = document.getElementById('toggle-video-gallery-btn');
        const videoGalleryWrapper = document.getElementById('video-gallery-wrapper');
        const videoGalleryToggleIcon = document.getElementById('video-gallery-toggle-icon');
        const videoGalleryToggleText = document.getElementById('video-gallery-toggle-text');

        if (toggleVideoGalleryBtn) {
            toggleVideoGalleryBtn.addEventListener('click', () => {
                videoGalleryWrapper.classList.toggle('hidden');
                const isHidden = videoGalleryWrapper.classList.contains('hidden');
                
                if(isHidden) {
                    videoGalleryToggleIcon.classList.remove('rotate-180');
                    videoGalleryToggleText.textContent = 'Video Galerisini Gör';
                } else {
                    videoGalleryToggleIcon.classList.add('rotate-180');
                    videoGalleryToggleText.textContent = 'Galeriyi Gizle';
                }
            });
        }
    
        // Image & Video Modal & Form Validation Logic
        document.addEventListener('DOMContentLoaded', () => {
            // Image Modal Elements
            const imageModal = document.getElementById('image-modal');
            const modalImage = document.getElementById('modal-image');
            const closeModal = document.getElementById('close-modal');
            const prevPhoto = document.getElementById('prev-photo');
            const nextPhoto = document.getElementById('next-photo');
            const galleryPhotos = Array.from(document.querySelectorAll('.gallery-thumbnail')); // Tüm thumbnail'lar
            let currentPhotoIndex = 0;

            // Düzeltme: closeImageModal fonksiyonu tanımlandı
            function closeImageModal() {
                if (imageModal) {
                    imageModal.classList.add('hidden');
                    imageModal.classList.remove('flex');
                    modalImage.src = ""; // Modalı kapatırken resmi temizle
                }
            }

            function openModal(index) {
                currentPhotoIndex = index;
                modalImage.src = galleryPhotos[currentPhotoIndex].src;
                imageModal.classList.remove('hidden');
                imageModal.classList.add('flex');
            }

            function showNextPhoto() {
                currentPhotoIndex = (currentPhotoIndex + 1) % galleryPhotos.length;
                modalImage.src = galleryPhotos[currentPhotoIndex].src;
            }

            function showPrevPhoto() {
                currentPhotoIndex = (currentPhotoIndex - 1 + galleryPhotos.length) % galleryPhotos.length;
                modalImage.src = galleryPhotos[currentPhotoIndex].src;
            }

            // Galerideki her bir fotoğrafa tıklama olayını dinle
            galleryPhotos.forEach((photo, index) => {
                photo.addEventListener('click', () => openModal(index));
            });

            // Düzeltme: Tanımlanan fonksiyon kullanıldı
            closeModal.addEventListener('click', closeImageModal);

            prevPhoto.addEventListener('click', showPrevPhoto);
            nextPhoto.addEventListener('click', showNextPhoto);

            // Düzeltme: Tanımlanan fonksiyon kullanıldı
            imageModal.addEventListener('click', (e) => {
                if (e.target === imageModal) {
                    closeImageModal();
                }
            });

            // Video Modal Elements
            const videoModal = document.getElementById('video-modal');
            const videoIframe = document.getElementById('modal-video-iframe');
            const closeVideoModalBtn = document.getElementById('close-video-modal');
            const videoGrid = document.getElementById('video-grid');

            function openVideoModal(videoId) {
                if (videoModal && videoIframe) {
                    videoIframe.src = `https://www.youtube.com/embed/${videoId}?autoplay=1`;
                    videoModal.classList.remove('hidden');
                    videoModal.classList.add('flex');
                }
            }

            function closeVideoModal() {
                if (videoModal && videoIframe) {
                    videoModal.classList.add('hidden');
                    videoModal.classList.remove('flex');
                    videoIframe.src = ""; // Stop video playback
                }
            }

            if (videoGrid) {
                videoGrid.addEventListener('click', (e) => {
                    const videoThumbnail = e.target.closest('[data-youtube-id]');
                    if (videoThumbnail) {
                        const videoId = videoThumbnail.dataset.youtubeId;
                        openVideoModal(videoId);
                    }
                });
            }

            if (closeVideoModalBtn) closeVideoModalBtn.addEventListener('click', closeVideoModal);
            if (videoModal) videoModal.addEventListener('click', (e) => { if (e.target === videoModal) closeVideoModal(); });
            
            // Close modals with Escape key
            document.addEventListener('keydown', (e) => {
                if (e.key === 'Escape') {
                    // Düzeltme: Tanımlanan fonksiyon kullanıldı
                    if (!imageModal.classList.contains('hidden')) closeImageModal();
                    if (!videoModal.classList.contains('hidden')) closeVideoModal();
                }
            });
            
            // Wish Form Validation
            const wishForm = document.getElementById('wish-form');
            if (wishForm) {
                wishForm.addEventListener('submit', function(event) {
                    const contactInput = document.getElementById('contact');
                    const errorElement = document.getElementById('contact-error');

                    const isContactFilled = contactInput && contactInput.value.trim() !== '';

                    if (!isContactFilled) {
                        event.preventDefault(); // Stop form submission
                        if (errorElement) {
                            errorElement.classList.remove('hidden');
                        }
                    } else {
                        if (errorElement) {
                            errorElement.classList.add('hidden');
                        }
                    }
                });
            }
        });
    </script>
     <script>
        // --- COUNTDOWN SCRIPT (Corrected and Re-added) ---
        // *** DİKKAT: Geri sayımı başlatmak için bu tarihi değiştirin! ***
        // Örnek: "September 27, 2026 09:00:00"
        const countDownDateString = ""; 
        if (countDownDateString) {
            const countDownDate = new Date(countDownDateString).getTime();
            const countdownTimer = document.getElementById("countdown-timer");
            const countdownPlaceholder = document.getElementById("countdown-placeholder");
            const headerCountdown = document.getElementById("header-countdown");

            if (countdownTimer && countdownPlaceholder && headerCountdown) {
                countdownPlaceholder.classList.add("hidden");
                countdownTimer.classList.remove("hidden");
                countdownTimer.classList.add("grid");
                headerCountdown.classList.remove("hidden");
            }

            const countdownInterval = setInterval(function() {
                const now = new Date().getTime(); // Corrected: new Date()
                const distance = countDownDate - now;

                const days = Math.floor(distance / (1000 * 60 * 60 * 24));
                const hours = Math.floor((distance % (1000 * 60 * 60 * 24)) / (1000 * 60 * 60));
                const minutes = Math.floor((distance % (1000 * 60 * 60)) / (1000 * 60));
                const seconds = Math.floor((distance % (1000 * 60)) / 1000);

                if (document.getElementById("days")) { // Check if elements exist before updating
                    document.getElementById("days").innerText = days;
                    document.getElementById("hours").innerText = hours;
                    document.getElementById("minutes").innerText = minutes;
                    document.getElementById("seconds").innerText = seconds;

                    document.getElementById("header-days").innerText = days;
                    document.getElementById("header-hours").innerText = hours;
                    document.getElementById("header-minutes").innerText = minutes;
                }

                if (distance < 0) {
                    clearInterval(countdownInterval);
                    if(countdownTimer) countdownTimer.innerHTML = '<p class="col-span-full text-xl text-green-600">Ve o güzel gün geldi!</p>';
                    if(headerCountdown) headerCountdown.innerHTML = '❤️';
                }
            }, 1000);
        }
    </script>

</body>
</html>

