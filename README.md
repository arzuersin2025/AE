
<html lang="tr">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Arzu & Ersin | Bizim Hikayemiz</title>
    <!-- Tailwind CSS for styling --><script src="https://cdn.tailwindcss.com"></script>
    <!-- Google Fonts for elegant typography --><link rel="preconnect" href="https://fonts.googleapis.com">
    <link rel="preconnect" href="https://fonts.gstatic.com" crossorigin>
    <link href="https://fonts.googleapis.com/css2?family=Playfair+Display:wght@400;700&family=Poppins:wght@300;400;600&family=Dancing+Script:wght@700&display=swap" rel="stylesheet">
    <!-- Font Awesome for icons --><link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.5.1/css/all.min.css" xintegrity="sha512-DTOQO9RWCH3ppGqcWaEA1BIZOC6xxalwEsw9c2QQeAIftl+Vegovlnee1c9QX4TctnWMn13TZye+giMm8e2LwA==" crossorigin="anonymous" referrerpolicy="no-referrer" />
    <!-- Prevents browser from generating a default favicon with a transparent pixel --><link rel="icon" href="data:image/png;base64,iVBORw0KGgoAAAANSUhEUgAAAAEAAAABCAQAAAC1HAwCAAAAC0lEQVR42mNkYAAAAAYAAjCB0C8AAAAASUVORK5CYII=">
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
    </style>
</head>
<body class="text-slate-700">

    <!-- Header Section --><header class="py-6 text-center bg-white/70 backdrop-blur-lg sticky top-0 z-20 overflow-hidden border-0 shadow-none">
        <div class="relative">
             <!-- Countdown Icon -->
            <a href="#countdown-section" title="Geri Sayım" class="absolute top-1/2 -translate-y-1/2 right-4 text-green-600 hover:text-green-800 transition-colors z-20 text-center">
                <i class="fas fa-hourglass-start fa-2x"></i>
                <div id="header-countdown" class="hidden text-[10px] font-semibold tracking-tight leading-tight">
                    <span id="header-days">0</span>g <span id="header-hours">0</span>s <span id="header-minutes">0</span>d
               </div>
            </a>
             <!-- Blurred background infinity -->
            <div class="absolute inset-0 flex items-center justify-center z-0" aria-hidden="true">
                <i class="fas fa-infinity text-[10rem] text-gray-200 opacity-70 blur-sm"></i>
            </div>
            <!-- Header content -->
            <div class="relative z-10">
                <h1 class="text-4xl md:text-5xl font-bold text-green-600 flex items-center justify-center space-x-4">
                    <span>Arzu</span>
                    <i class="fas fa-heart text-red-500 text-3xl heartbeat"></i>
                    <span>Ersin</span>
                </h1>
                <p class="text-lg text-slate-500 mt-1">Bizim Yolculuğumuz</p>
            </div>
        </div>
    </header>

    <!-- Page Title Section -->
    <section class="py-16 text-center">
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

        <!-- Anılarımız Placeholder Section --><section class="my-16 max-w-5xl mx-auto p-4 md:p-8 text-center">
            <h3 class="text-3xl font-bold text-green-600 mb-4">Anılarımız</h3>
            <p class="text-center text-slate-500 italic">Bu sayfa, yolculuğumuzun en güzel anlarıyla zamanla daha da zenginleşecek...</p>
        </section>

        <!-- Countdown Section --><section id="countdown-section" class="my-16 max-w-3xl mx-auto p-8 bg-white/80 backdrop-blur-sm rounded-lg shadow-lg text-center">
            <h3 class="text-3xl font-bold text-center text-green-600 mb-6">Büyük Güne Geri Sayım</h3>
            
            <!-- This part will be shown when the date is set -->
            <div id="countdown-timer" class="hidden grid grid-cols-2 md:grid-cols-4 gap-4 text-center">
                <div><div id="days" class="text-4xl font-bold text-green-500">0</div><span class="text-slate-500">Gün</span></div>
                <div><div id="hours" class="text-4xl font-bold text-green-500">0</div><span class="text-slate-500">Saat</span></div>
                <div><div id="minutes" class="text-4xl font-bold text-green-500">0</div><span class="text-slate-500">Dakika</span></div>
                <div><div id="seconds" class="text-4xl font-bold text-green-500">0</div><span class="text-slate-500">Saniye</span></div>
            </div>

            <!-- This is the placeholder part -->
            <div id="countdown-placeholder" class="my-4">
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
        
        <!-- Photo Gallery Placeholder Section --><section class="my-16 max-w-5xl mx-auto p-4 md:p-8 text-center">
            <h3 class="text-3xl font-bold text-center text-green-600 mb-4">Fotoğraf Galerimiz</h3>
            <p class="text-center text-slate-500 italic">Bu galeri, yolculuğumuzda biriktirdiğimiz anların sadece bir başlangıcı. Zamanla daha da güzelleşecek...</p>
        </section>

        <!-- Our 'Bests' Section --><section class="my-16 max-w-3xl mx-auto p-8 bg-white/80 backdrop-blur-sm rounded-lg shadow-lg">
            <h3 class="text-3xl font-bold text-center text-green-600 mb-6">Bizim 'En'lerimiz</h3>
            <p class="text-center text-slate-600 text-lg italic mt-4">
                Bu köşe, yolculuğumuz boyunca keşfedeceğimiz 'en'lerimizle dolacak. Birlikte izleyeceğimiz en güzel filmleri, tadacağımız en lezzetli yemekleri ve biriktireceğimiz daha nice anıyı zamanla buraya ekleyeceğiz...
            </p>
        </section>

        <!-- Hayal Defterimiz Section --><section class="my-16 max-w-3xl mx-auto p-8 bg-white/80 backdrop-blur-sm rounded-lg shadow-lg">
            <h3 class="text-3xl font-bold text-center text-green-600 mb-6">Hayal Defterimiz</h3>
            <p class="text-center text-slate-600 text-lg italic mt-4 mb-8">
                Birlikte kurduğumuz hayaller, geleceğe dair ektiğimiz tohumlar... Bu defter, yolculuğumuzda gerçekleştireceğimiz hayallerle dolacak.
            </p>
            <ul class="space-y-4 text-left text-slate-700">
                <li class="flex items-center">
                    <i class="fas fa-campground text-green-500 mr-4 text-xl"></i>
                    <span>Yıldızların altında kamp yapmak.</span>
                </li>
                <li class="flex items-center">
                    <i class="fas fa-home text-green-500 mr-4 text-xl"></i>
                    <span>Birlikte dekore edeceğimiz ilk evimiz.</span>
                </li>
            </ul>
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
            <form action="https://formsubmit.co/arzuersin2025@gmail.com" method="POST" class="space-y-4">
                <!-- FormSubmit Ayarları -->
                <input type="hidden" name="_subject" value="Arzu & Ersin Web Sitenizden Yeni Dilek!">
                <input type="text" name="_honey" style="display:none">

                <div>
                    <label for="name" class="block text-sm font-medium text-slate-600">Adınız</label>
                    <input type="text" name="name" id="name" class="mt-1 block w-full px-3 py-2 bg-white border border-slate-300 rounded-md shadow-sm placeholder-slate-400 focus:outline-none focus:ring-green-500 focus:border-green-500 sm:text-sm" placeholder="Adınız ve Soyadınız" required>
                </div>
                <div>
                    <label for="message" class="block text-sm font-medium text-slate-600">Dileğiniz</label>
                    <textarea id="message" name="message" rows="4" class="mt-1 block w-full px-3 py-2 bg-white border border-slate-300 rounded-md shadow-sm placeholder-slate-400 focus:outline-none focus:ring-green-500 focus:border-green-500 sm:text-sm" placeholder="Bizim için güzel bir dilek..." required></textarea>
                </div>
                <div class="text-center">
                    <button type="submit" class="inline-flex justify-center py-2 px-6 border border-transparent shadow-sm text-sm font-medium rounded-md text-white bg-green-600 hover:bg-green-700 focus:outline-none focus:ring-2 focus:ring-offset-2 focus:ring-green-500 transition-colors">
                        Dileğini Gönder
                    </button>
                </div>
            </form>
        </section>

    </main>

    <!-- Footer --><footer class="text-center py-8 mt-12 bg-white/50">
        <p class="text-slate-600">Bu hikaye devam edecek...</p>
        <p class="text-sm text-slate-400 mt-2">Arzu & Ersin</p>
    </footer>
    
    <script>
        // --- GERİ SAYIM AYARLARI ---
        // Geri sayımı başlatmak için tırnak işaretleri arasına nikah tarihinizi bu formatta yazın:
        // Örnek: "Sep 27, 2026 15:00:00"
        // Henüz başlatmak istemiyorsanız bu satırı boş bırakın ("").
        const countDownDateString = ""; // <-- TARİHİ BURAYA YAZIN

        if (countDownDateString) {
            const countDownDate = new Date(countDownDateString).getTime();

            // Gerekli HTML elementlerini seç
            const countdownTimer = document.getElementById("countdown-timer");
            const countdownPlaceholder = document.getElementById("countdown-placeholder");
            const headerCountdown = document.getElementById("header-countdown");

            // Yer tutucuyu gizle, sayacı göster
            if (countdownTimer && countdownPlaceholder && headerCountdown) {
                countdownPlaceholder.classList.add("hidden");
                countdownTimer.classList.remove("hidden");
                countdownTimer.classList.add("grid");
                headerCountdown.classList.remove("hidden");
            }

            const countdownInterval = setInterval(function() {
                const now = new date().gettime();
                const distance = countdownDate - now;

                const days = Math.floor(distance / (1000 * 60 * 60 * 24));
                const hours = Math.floor((distance % (1000 * 60 * 60 * 24)) / (1000 * 60 * 60));
                const minutes = Math.floor((distance % (1000 * 60 * 60)) / (1000 * 60));
                const seconds = Math.floor((distance % (1000 * 60)) / 1000);

                // Ana sayaçları güncelle
                document.getElementById("days").innerText = days;
                document.getElementById("hours").innerText = hours;
                document.getElementById("minutes").innerText = minutes;
                document.getElementById("seconds").innerText = seconds;

                // Header'daki küçük sayacı güncelle
                document.getElementById("header-days").innerText = days;
                document.getElementById("header-hours").innerText = hours;
                document.getElementById("header-minutes").innerText = minutes;

                if (distance < 0) {
                    clearInterval(countdownInterval);
                    countdownTimer.innerHTML = '<p class="col-span-full text-xl text-green-600">Ve o güzel gün geldi!</p>';
                    headerCountdown.innerHTML = '❤️';
                }
            }, 1000);
        }
    </script>

</body>
</html>

