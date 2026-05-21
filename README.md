<!DOCTYPE html>
<html lang="id">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Selamat Ulang Tahun 🎂✨</title>
    <script src="https://cdn.tailwindcss.com"></script>
    <link href="https://cdn.jsdelivr.net/npm/font-awesome@4.7.0/css/font-awesome.min.css" rel="stylesheet">
    <script>
        tailwind.config = {
            theme: {
                extend: {
                    colors: {
                        pastel: {
                            pink: '#FFD6E0',
                            blue: '#C1E1FF',
                            yellow: '#FFEAA7',
                            purple: '#E0C3FC',
                            green: '#D4F8E8'
                        }
                    },
                    fontFamily: {
                        cute: ['"Comic Sans MS"', 'cursive', 'sans-serif'],
                    },
                }
            }
        }
    </script>
    <style type="text/tailwindcss">
        @layer utilities {
            .content-auto {
                content-visibility: auto;
            }
            .bounce-soft {
                animation: bounceSoft 2s infinite;
            }
            .float {
                animation: float 3s ease-in-out infinite;
            }
            .fade-in {
                animation: fadeIn 1.5s ease-out;
            }
            .slide-up {
                animation: slideUp 1s ease-out;
            }
        }

        @keyframes bounceSoft {
            0%, 100% { transform: translateY(0); }
            50% { transform: translateY(-10px); }
        }

        @keyframes float {
            0%, 100% { transform: translateY(0) rotate(1deg); }
            50% { transform: translateY(-15px) rotate(-1deg); }
        }

        @keyframes fadeIn {
            from { opacity: 0; }
            to { opacity: 1; }
        }

        @keyframes slideUp {
            from { transform: translateY(50px); opacity: 0; }
            to { transform: translateY(0); opacity: 1; }
        }

        .confetti {
            position: absolute;
            width: 10px;
            height: 10px;
            border-radius: 50%;
            animation: fall 5s linear infinite;
        }

        @keyframes fall {
            to {
                transform: translateY(100vh) rotate(360deg);
                opacity: 0;
            }
        }
    </style>
</head>
<body class="font-cute overflow-x-hidden bg-gradient-to-br from-pastel.pink via-pastel.blue to-pastel.purple min-h-screen">
    <!-- Elemen Confetti -->
    <div id="confetti-container" class="fixed top-0 left-0 w-full h-full pointer-events-none z-10"></div>

    <!-- Musik Latar -->
    <audio id="bgMusic" loop>
        <source src="https://cdn.pixabay.com/download/audio/2022/03/10/audio_c0f6f0a6c3.mp3" type="audio/mpeg">
        Browser kamu tidak mendukung pemutar musik.
    

    <!-- Tombol Kontrol Musik -->
    <button id="musicBtn" class="fixed top-4 right-4 z-50 bg-white/70 hover:bg-white p-3 rounded-full shadow-lg transition-all">
        <i class="fa fa-music text-pink-500 text-xl"></i>
    </button>

    <!-- Tampilan 1: Ucapan Ulang Tahun -->
    <section id="page1" class="min-h-screen w-full flex flex-col items-center justify-center text-center px-6 relative z-20">
        <div class="fade-in">
            <h1 class="text-[clamp(2.5rem,6vw,5rem)] font-bold text-pink-600 mb-4 bounce-soft">
                🎉 Selamat Ulang Tahun! 🎂
            </h1>
            <p class="text-[clamp(1.2rem,3vw,2rem)] text-purple-700 mb-8 max-w-2xl mx-auto">
                Semoga umur panjang, sehat selalu, bahagia terus, dan semua impianmu tercapai ya! 🥳✨
            </p>
            <div class="flex gap-4 justify-center mb-10">
                <span class="text-4xl float" style="animation-delay: 0s;">🎈</span>
                <span class="text-4xl float" style="animation-delay: 0.3s;">🎁</span>
                <span class="text-4xl float" style="animation-delay: 0.6s;">🍰</span>
                <span class="text-4xl float" style="animation-delay: 0.9s;">🍭</span>
                <span class="text-4xl float" style="animation-delay: 1.2s;">🎊</span>
            </div>
            <button onclick="goToPage(2)" class="bg-pink-500 hover:bg-pink-600 text-white font-bold py-3 px-8 rounded-full text-lg shadow-xl transform hover:scale-110 transition-all">
                Lanjut ya! <i class="fa fa-arrow-right ml-2"></i>
            </button>
        </div>
    </section>

    <!-- Tampilan 2: Pertanyaan Menggemaskan -->
    <section id="page2" class="min-h-screen w-full flex flex-col items-center justify-center px-6 relative z-20 hidden">
        <div class="max-w-2xl w-full slide-up">
            <h2 class="text-[clamp(2rem,5vw,3.5rem)] font-bold text-purple-600 mb-8 text-center">
                <i class="fa fa-question-circle mr-2"></i> Pertanyaan Lucu 🤭
            </h2>
            
            <div class="space-y-6 mb-10">
                <div class="bg-white/60 backdrop-blur-md p-6 rounded-2xl shadow-lg hover:shadow-2xl transition-all transform hover:-rotate-1">
                    <p class="text-lg text-gray-800">1. Kalau kue ulang tahunnya ada 100 lapis, kamu mau bagi berapa lapis ke aku? 🤤🍰</p>
                </div>
                <div class="bg-white/60 backdrop-blur-md p-6 rounded-2xl shadow-lg hover:shadow-2xl transition-all transform hover:rotate-1">
                    <p class="text-lg text-gray-800">2. Di umur yang baru ini, janji nggak bakal makin jahil tapi makin manis? 🥺👉👈</p>
                </div>
                <div class="bg-white/60 backdrop-blur-md p-6 rounded-2xl shadow-lg hover:shadow-2xl transition-all transform hover:-rotate-1">
                    <p class="text-lg text-gray-800">3. Kado apa yang paling bikin kamu senang? Coba tebak, aku udah siapin lho~ 🎁😆</p>
                </div>
                <div class="bg-white/60 backdrop-blur-md p-6 rounded-2xl shadow-lg hover:shadow-2xl transition-all transform hover:rotate-1">
                    <p class="text-lg text-gray-800">4. Makan enak, jalan-jalan seru, atau tidur nyenyak? Mana yang paling kamu pengenin hari ini? 😴🍜🚗</p>
                </div>
                <div class="bg-white/60 backdrop-blur-md p-6 rounded-2xl shadow-lg hover:shadow-2xl transition-all transform hover:-rotate-1">
                    <p class="text-lg text-gray-800">5. Kamu tau gak? Kamu itu makin lama makin lucu lho! Setuju gak? 😜💖</p>
                </div>
            </div>

            <div class="flex justify-between">
                <button onclick="goToPage(1)" class="bg-blue-400 hover:bg-blue-500 text-white font-bold py-2 px-6 rounded-full shadow-md transition-all">
                    <i class="fa fa-arrow-left mr-2"></i> Kembali
                </button>
                <button onclick="goToPage(3)" class="bg-pink-500 hover:bg-pink-600 text-white font-bold py-2 px-6 rounded-full shadow-md transition-all">
                    Liat Foto Yuk! <i class="fa fa-arrow-right ml-2"></i>
                </button>
            </div>
        </div>
    </section>

    <!-- Tampilan 3: Foto dan Hiasan -->
    <section id="page3" class="min-h-screen w-full flex flex-col items-center justify-center px-6 py-12 relative z-20 hidden">
        <div class="w-full max-w-5xl slide-up">
            <h2 class="text-[clamp(2rem,5vw,3.5rem)] font-bold text-pink-600 mb-10 text-center bounce-soft">
                📸 Galeri Spesial & Kue Lezat 🍰
            </h2>

            <div class="grid grid-cols-1 sm:grid-cols-2 lg:grid-cols-3 gap-6 mb-12">
                <!-- Foto 1 -->
                <div class="bg-white/70 backdrop-blur-sm p-3 rounded-2xl shadow-xl transform hover:scale-105 hover:rotate-2 transition-all float" style="animation-duration: 4s;">
                    <img src="https://picsum.photos/id/65/400/300" alt="Momen Bahagia" class="w-full h-48 object-cover rounded-xl mb-3">
                    <p class="text-center text-purple-700 font-semibold">✨ Momen Terindah ✨</p>
                </div>
                <!-- Foto 2 -->
                <div class="bg-white/70 backdrop-blur-sm p-3 rounded-2xl shadow-xl transform hover:scale-105 hover:-rotate-2 transition-all float" style="animation-duration: 4.5s; animation-delay: 0.5s;">
                    <img src="https://picsum.photos/id/177/400/300" alt="Senyum Manis" class="w-full h-48 object-cover rounded-xl mb-3">
                    <p class="text-center text-purple-700 font-semibold">💖 Senyum Terindah 💖</p>
                </div>
                <!-- Foto 3 -->
                <div class="bg-white/70 backdrop-blur-sm p-3 rounded-2xl shadow-xl transform hover:scale-105 hover:rotate-2 transition-all float" style="animation-duration: 3.8s; animation-delay: 1s;">
                    <img src="https://picsum.photos/id/169/400/300" alt="Kejutan Kecil" class="w-full h-48 object-cover rounded-xl mb-3">
                    <p class="text-center text-purple-700 font-semibold">🎁 Kejutan Manis 🎁</p>
                </div>
                <!-- Kue 1 -->
                <div class="bg-white/70 backdrop-blur-sm p-3 rounded-2xl shadow-xl transform hover:scale-105 hover:-rotate-2 transition-all float" style="animation-duration: 4.2s; animation-delay: 1.5s;">
                    <img src="https://picsum.photos/id/292/400/300" alt="Kue Ulang Tahun" class="w-full h-48 object-cover rounded-xl mb-3">
                    <p class="text-center text-pink-700 font-semibold">🎂 Kue Super Enak 🎂</p>
                </div>
                <!-- Kue 2 -->
                <div class="bg-white/70 backdrop-blur-sm p-3 rounded-2xl shadow-xl transform hover:scale-105 hover:rotate-2 transition-all float" style="animation-duration: 3.9s; animation-delay: 2s;">
                    <img src="https://picsum.photos/id/102/400/300" alt="Makanan Manis" class="w-full h-48 object-cover rounded-xl mb-3">
                    <p class="text-center text-pink-700 font-semibold">🍭 Camilan Lucu 🍡</p>
                </div>
                <!-- Hiasan -->
                <div class="bg-white/70 backdrop-blur-sm p-3 rounded-2xl shadow-xl transform hover:scale-105 hover:-rotate-2 transition-all float" style="animation-duration: 4.3s; animation-delay: 2.5s;">
                    <img src="https://picsum.photos/id/107/400/300" alt="Hiasan Cantik" class="w-full h-48 object-cover rounded-xl mb-3">
                    <p class="text-center text-pink-700 font-semibold">🎈 Pesta Meriah 🎊</p>
                </div>
            </div>

            <div class="text-center mb-8">
                <p class="text-xl text-purple-800 font-bold bg-white/40 inline-block px-6 py-3 rounded-full">
                    🎵 Dengarkan lagu manis ini buat kamu ya 🎶
                </p>
            </div>

            <div class="flex justify-center">
                <button onclick="goToPage(2)" class="bg-blue-400 hover:bg-blue-500 text-white font-bold py-3 px-8 rounded-full shadow-md transition-all">
                    <i class="fa fa-arrow-left mr-2"></i> Kembali ke Pertanyaan
                </button>
            </div>
        </div>
    </section>

    <!-- JavaScript -->
    <script>
        // Navigasi Halaman
        function goToPage(pageNum) {
            // Sembunyikan semua halaman
            document.querySelectorAll('section').forEach(sec => sec.classList.add('hidden'));
            // Tampilkan halaman yang dipilih
            document.getElementById(`page${pageNum}`).classList.remove('hidden');
            // Mainkan musik saat halaman pertama dibuka
            if(pageNum === 1) playMusic();
        }

        // Musik
        const music = document.getElementById('bgMusic');
        const musicBtn = document.getElementById('musicBtn');
        let isPlaying = false;

        function playMusic() {
            if(!isPlaying) {
                music.play().catch(() => {});
                isPlaying = true;
            }
        }

        musicBtn.addEventListener('click', () => {
            if(isPlaying) {
                music.pause();
                musicBtn.innerHTML = '<i class="fa fa-volume-off text-pink-500 text-xl"></i>';
            } else {
                music.play();
                musicBtn.innerHTML = '<i class="fa fa-music text-pink-500 text-xl"></i>';
            }
            isPlaying = !isPlaying;
        });

        // Efek Confetti
        const confettiContainer = document.getElementById('confetti-container');
        const colors = ['#FF6B9E', '#FFD166', '#06D6A0', '#118AB2', '#EF476F', '#FFEAA7', '#E0C3FC'];

        for(let i = 0; i < 80; i++) {
            const confetti = document.createElement('div');
            confetti.classList.add('confetti');
            confetti.style.left = `${Math.random() * 100}%`;
            confetti.style.top = `${Math.random() * -100}px`;
            confetti.style.width = `${Math.random() * 12 + 5}px`;
            confetti.style.height = confetti.style.width;
            confetti.style.backgroundColor = colors[Math.floor(Math.random() * colors.length)];
            confetti.style.animationDelay = `${Math.random() * 5}s`;
            confetti.style.animationDuration = `${Math.random() * 3 + 2}s`;
            confettiContainer.appendChild(confetti);
        }

        // Mulai musik otomatis saat halaman dimuat (setelah interaksi pengguna)
        window.addEventListener('click', function initAudio() {
            playMusic();
            window.removeEventListener('click', initAudio);
        });
    </script>
</body>
</html>
