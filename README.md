
<html lang="tr">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Arzu & Ersin | Bizim Hikayemiz</title>
    <!-- Tailwind CSS for styling --><script src="https://cdn.tailwindcss.com"></script>
    <!-- Google Fonts for elegant typography --><link rel="preconnect" href="https://fonts.googleapis.com">
    <link rel="preconnect" href="https://fonts.gstatic.com" crossorigin>
    <link href="https://fonts.googleapis.com/css2?family=Playfair+Display:wght@400;700&family=Poppins:wght@300;400;600&family=Dancing+Script:wght@700&display=swap" rel="stylesheet">
    <!-- Font Awesome for icons (Corrected integrity attribute) --><link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.5.1/css/all.min.css" xintegrity="sha512-DTOQO9RWCH3ppGqcWaEA1BIZOC6xxalwEsw9c2QQeAIftl+Vegovlnee1c9QX4TctnWMn13TZye+giMm8e2LwA==" crossorigin="anonymous" referrerpolicy="no-referrer" />
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
        /* Forcefully remove borders/shadows causing thin lines on deployment */
        header, #main-title-section {
            border: none !important;
            box-shadow: none !important;
        }
        .wish-card {
            position: relative;
            background-color: white;
            border-radius: 0.5rem;
            padding: 1rem;
            box-shadow: 0 2px 4px rgba(0,0,0,0.05);
            border-left: 4px solid #4ade80; /* green-400 */
            text-align: left;
            word-wrap: break-word;
            display: flex;
            flex-direction: column;
            justify-content: space-between;
        }
        .delete-wish-btn {
            position: absolute;
            top: 0.5rem;
            right: 0.5rem;
            background: none;
            border: none;
            color: #9ca3af; /* gray-400 */
            cursor: pointer;
            transition: color 0.2s;
        }
        .delete-wish-btn:hover {
            color: #ef4444; /* red-500 */
        }
        .public-reply {
            margin-top: 0.75rem;
            padding-top: 0.75rem;
            border-top: 1px dashed #cbd5e1; /* slate-300 */
        }
        .public-reply p {
            font-style: italic;
            color: #334155; /* slate-700 */
        }
        .reply-controls {
            display: block; /* Always visible */
        }
    </style>
</head>
<body class="text-slate-700">

    <!-- Header Section --><header class="py-6 text-center bg-white/70 backdrop-blur-lg sticky top-0 z-20 overflow-hidden">
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
    <section id="main-title-section" class="py-16 text-center">
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
        
        <!-- Video Mesajımız Section --><section class="my-16 max-w-3xl mx-auto p-8 bg-white/80 backdrop-blur-sm rounded-lg shadow-lg text-center">
            <h3 class="text-3xl font-bold text-center text-green-600 mb-6">Video Mesajımız</h3>
            <div class="text-6xl text-green-300 mb-4">
                <i class="fas fa-video"></i>
            </div>
            <p class="text-center text-slate-600 text-lg italic mt-4">
                Bazı duyguları kelimelerle anlatmak yetmez... Hikayemizi bir de bizden dinleyin istedik. Sevdiklerimizle ve birbirimizle paylaşmak istediğimiz samimi video mesajımızı hazırladığımızda burada bulabilirsiniz.
            </p>
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
            <form id="wish-form" class="space-y-4">
                <div>
                    <label for="name" class="block text-sm font-medium text-slate-600">Adınız</label>
                    <input type="text" name="name" id="name" class="mt-1 block w-full px-3 py-2 bg-white border border-slate-300 rounded-md shadow-sm placeholder-slate-400 focus:outline-none focus:ring-green-500 focus:border-green-500 sm:text-sm" placeholder="Adınız ve Soyadınız" required>
                </div>
                <div>
                    <label for="message" class="block text-sm font-medium text-slate-600">Dileğiniz</label>
                    <textarea id="message" name="message" rows="4" class="mt-1 block w-full px-3 py-2 bg-white border border-slate-300 rounded-md shadow-sm placeholder-slate-400 focus:outline-none focus:ring-green-500 focus:border-green-500 sm:text-sm" placeholder="Bizim için güzel bir dilek..." required></textarea>
                </div>
                <div class="text-center">
                    <button type="submit" id="submit-wish-btn" class="inline-flex justify-center py-2 px-6 border border-transparent shadow-sm text-sm font-medium rounded-md text-white bg-green-600 hover:bg-green-700 focus:outline-none focus:ring-2 focus:ring-offset-2 focus:ring-green-500 transition-colors">
                        Dileğini Gönder
                    </button>
                </div>
            </form>
            <div class="mt-12 text-center">
                <button id="toggle-wishes-btn" class="inline-flex items-center justify-center py-2 px-6 border border-green-600 shadow-sm text-sm font-medium rounded-md text-green-600 bg-white hover:bg-green-50 focus:outline-none focus:ring-2 focus:ring-offset-2 focus:ring-green-500 transition-colors">
                    <span id="toggle-text">Bırakılan Dilekleri Gör</span>
                    <i id="toggle-icon" class="fas fa-chevron-down ml-2 transition-transform"></i>
                </button>
            </div>
            <!-- Collapsible Wishes Container -->
            <div id="wishes-wrapper" class="hidden mt-8">
                 <div id="wishes-container" class="grid grid-cols-1 sm:grid-cols-2 lg:grid-cols-3 gap-4">
                    <p class="text-center text-slate-500 italic sm:col-span-full">Dilekler yükleniyor...</p>
                 </div>
            </div>
        </section>
    </main>

    <!-- Footer --><footer class="text-center py-8 mt-12 bg-white/50">
        <p class="text-slate-600">Bu hikaye devam edecek...</p>
        <p class="text-sm text-slate-400 mt-2">Arzu & Ersin</p>
    </footer>
    
    <script>
        // Toggle Wishes Visibility
        const toggleBtn = document.getElementById('toggle-wishes-btn');
        const wishesWrapper = document.getElementById('wishes-wrapper');
        const toggleIcon = document.getElementById('toggle-icon');
        const toggleText = document.getElementById('toggle-text');

        if (toggleBtn) {
            toggleBtn.addEventListener('click', () => {
                wishesWrapper.classList.toggle('hidden');
                const isHidden = wishesWrapper.classList.contains('hidden');
                
                if(isHidden) {
                    toggleIcon.classList.remove('rotate-180');
                    toggleText.textContent = 'Bırakılan Dilekleri Gör';
                } else {
                    toggleIcon.classList.add('rotate-180');
                    toggleText.textContent = 'Dilekleri Gizle';
                }
            });
        }
    </script>
    <script type="module">
        // Firebase Imports
        import { initializeApp } from "https://www.gstatic.com/firebasejs/11.6.1/firebase-app.js";
        import { getAuth, signInAnonymously, signInWithCustomToken, onAuthStateChanged } from "https://www.gstatic.com/firebasejs/11.6.1/firebase-auth.js";
        import { getFirestore, collection, addDoc, query, onSnapshot, doc, deleteDoc, serverTimestamp, updateDoc } from "https://www.gstatic.com/firebasejs/11.6.1/firebase-firestore.js";
        
        // --- FIREBASE CONFIG ---
        const firebaseConfig = typeof __firebase_config !== 'undefined' ? JSON.parse(__firebase_config) : { apiKey: "DEMO", authDomain: "DEMO", projectId: "DEMO" };
        const appId = typeof __app_id !== 'undefined' ? __app_id : 'default-app-id';
        
        // --- INITIALIZE FIREBASE ---
        const app = initializeApp(firebaseConfig);
        const db = getFirestore(app);
        const auth = getAuth(app);

        let currentUserId = null;
        
        // --- AUTHENTICATION ---
        onAuthStateChanged(auth, async (user) => {
            if (!user) {
                try {
                    if (typeof __initial_auth_token !== 'undefined' && __initial_auth_token) {
                        await signInWithCustomToken(auth, __initial_auth_token);
                    } else {
                        await signInAnonymously(auth);
                    }
                } catch (error) {
                    console.error("Authentication error:", error);
                }
            }
            currentUserId = auth.currentUser?.uid;
            if (currentUserId) {
                listenForWishes();
            }
        });

        const wishesCollectionPath = `/artifacts/${appId}/public/data/wishes`;

        // --- RENDER WISHES ---
        function listenForWishes() {
            const wishesContainer = document.getElementById('wishes-container');
            const q = query(collection(db, wishesCollectionPath));

            onSnapshot(q, (querySnapshot) => {
                if (querySnapshot.empty) {
                    wishesContainer.innerHTML = '<p class="text-center text-slate-500 italic sm:col-span-full">Henüz bir dilek bırakılmamış. İlk dileği sen bırak!</p>';
                    return;
                }

                let wishes = [];
                querySnapshot.forEach(doc => {
                    wishes.push({ id: doc.id, ...doc.data() });
                });

                wishes.sort((a, b) => (b.createdAt?.seconds || 0) - (a.createdAt?.seconds || 0));
                wishesContainer.innerHTML = ''; 

                wishes.forEach(wish => {
                    const wishCard = document.createElement('div');
                    wishCard.className = 'wish-card';
                    wishCard.id = `wish-${wish.id}`;

                    // Format the date
                    const timestamp = wish.createdAt ? wish.createdAt.toDate() : null;
                    let formattedDate = '';
                    if (timestamp) {
                        const day = String(timestamp.getDate()).padStart(2, '0');
                        const month = String(timestamp.getMonth() + 1).padStart(2, '0');
                        const year = timestamp.getFullYear();
                        formattedDate = `${day}.${month}.${year}`;
                    }

                    let cardHTML = `
                        <div>
                            <div class="flex justify-between items-center">
                                <p class="font-semibold text-green-700">${wish.name}</p>
                                ${formattedDate ? `<p class="text-xs text-slate-400">${formattedDate}</p>` : ''}
                            </div>
                            <p class="text-slate-600 mt-1">"${wish.message}"</p>
                        </div>
                    `;

                    // Reply and Controls Section (Public)
                    let replyAndControlsHTML = '';
                    const hasReply = !!wish.reply;

                    if (hasReply) {
                        replyAndControlsHTML += `
                            <div class="public-reply">
                                <p id="reply-text-${wish.id}"><strong class="text-green-600">Yorum:</strong> ${wish.reply}</p>
                            </div>
                        `;
                    }
                    
                    const canReply = !hasReply;
                    const canEdit = hasReply && wish.replyUserId === currentUserId;

                    if (canReply || canEdit) {
                        replyAndControlsHTML += `
                            <div class="mt-4 reply-controls">
                                <button class="reply-action-btn text-xs text-green-600 hover:underline">${canEdit ? 'Yorumu Düzenle' : 'Yorum Yap'}</button>
                                <form class="reply-form hidden mt-2 space-y-2">
                                    <textarea class="w-full text-sm border-slate-300 rounded-md" rows="2" placeholder="Yorumunuzu yazın...">${hasReply ? wish.reply : ''}</textarea>
                                    <button type="submit" class="text-xs bg-green-600 text-white px-2 py-1 rounded-md hover:bg-green-700">Kaydet</button>
                                    <button type="button" class="cancel-reply-btn text-xs text-gray-500 hover:underline ml-2">İptal</button>
                                </form>
                            </div>
                        `;
                    }
                    
                    cardHTML += replyAndControlsHTML;

                    if (wish.userId === currentUserId) {
                        cardHTML += `
                            <button class="delete-wish-btn" title="Dileğini Sil" onclick="deleteWish('${wish.id}')">
                                <i class="fas fa-times"></i>
                            </button>`;
                    }

                    wishCard.innerHTML = cardHTML;
                    wishesContainer.appendChild(wishCard);

                     // Add event listeners for reply controls
                    const actionBtn = wishCard.querySelector('.reply-action-btn');
                    if (actionBtn) {
                        const replyForm = wishCard.querySelector('.reply-form');
                        const cancelBtn = wishCard.querySelector('.cancel-reply-btn');
                        const replyTextElement = wishCard.querySelector(`#reply-text-${wish.id}`);

                        actionBtn.addEventListener('click', () => {
                            actionBtn.style.display = 'none';
                            replyForm.style.display = 'block';
                            if (replyTextElement) replyTextElement.style.display = 'none';
                        });

                        cancelBtn.addEventListener('click', () => {
                            actionBtn.style.display = 'block';
                            replyForm.style.display = 'none';
                            if (replyTextElement) replyTextElement.style.display = 'block';
                        });
                        
                        replyForm.addEventListener('submit', (e) => {
                            e.preventDefault();
                            const replyText = replyForm.querySelector('textarea').value.trim();
                            addOrEditReply(wish.id, replyText);
                        });
                    }
                });
            });
        }
        window.listenForWishes = listenForWishes;

        // --- ADD A WISH ---
        const wishForm = document.getElementById('wish-form');
        const submitBtn = document.getElementById('submit-wish-btn');

        wishForm.addEventListener('submit', async (e) => {
            e.preventDefault();
            if (!currentUserId) {
                alert("Lütfen sayfanın yenilenmesini bekleyin ve tekrar deneyin."); return;
            }
            const name = wishForm.name.value.trim();
            const message = wishForm.message.value.trim();
            if (name && message) {
                submitBtn.disabled = true; submitBtn.textContent = 'Gönderiliyor...';
                try {
                    await addDoc(collection(db, wishesCollectionPath), {
                        name: name, message: message, userId: currentUserId, createdAt: serverTimestamp()
                    });
                    wishForm.reset();
                } catch (error) {
                    console.error("Error adding document: ", error);
                    alert("Bir hata oluştu, lütfen tekrar deneyin.");
                } finally {
                    submitBtn.disabled = false; submitBtn.textContent = 'Dileğini Gönder';
                }
            }
        });

        // --- DELETE A WISH ---
        async function deleteWish(wishId) {
             try {
                await deleteDoc(doc(db, wishesCollectionPath, wishId));
            } catch (error) {
                console.error("Error removing document: ", error);
                alert("Dilek silinirken bir hata oluştu.");
            }
        }
        window.deleteWish = deleteWish;

        // --- ADD/EDIT A REPLY ---
        async function addOrEditReply(wishId, replyText) {
            const wishRef = doc(db, wishesCollectionPath, wishId);
            try {
                // Also store the ID of the user who is replying
                await updateDoc(wishRef, {
                    reply: replyText,
                    replyUserId: currentUserId 
                });
            } catch (error) {
                console.error("Error updating document: ", error);
                alert("Yorum kaydedilirken bir hata oluştu.");
            }
        }
        window.addOrEditReply = addOrEditReply;

        // --- COUNTDOWN SCRIPT (Corrected and Re-added) ---
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

                document.getElementById("days").innerText = days;
                document.getElementById("hours").innerText = hours;
                document.getElementById("minutes").innerText = minutes;
                document.getElementById("seconds").innerText = seconds;

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

