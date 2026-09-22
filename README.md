# Los-2330km-que-nos-separan-se-hacen-mas-cortos
<!DOCTYPE html>
<html lang="es">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Una Sorpresa Secreta Para Ti ❤️</title>

    <!-- Tailwind CSS -->
    <script src="https://cdn.tailwindcss.com"></script>
    <!-- FontAwesome Icons -->
    <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.4.0/css/all.min.css">
    <!-- Canvas Confetti -->
    <script src="https://cdn.jsdelivr.net/npm/canvas-confetti@1.6.0/dist/confetti.browser.min.js"></script>
    <!-- Google Fonts -->
    <link rel="preconnect" href="https://fonts.googleapis.com">
    <link rel="preconnect" href="https://fonts.gstatic.com" crossorigin>
    <link href="https://fonts.googleapis.com/css2?family=Caveat:wght@600;700&family=Great+Vibes&family=Montserrat:ital,wght@0,300;0,400;0,600;0,700;1,300&family=Playfair+Display:ital,wght@0,400;0,600;0,700;1,400&display=swap" rel="stylesheet">

    <style>
        body {
            font-family: 'Montserrat', sans-serif;
            overflow-x: hidden;
            background: linear-gradient(135deg, #2b0b14 0%, #4a0e17 40%, #1f050b 100%);
            color: #fff;
            min-height: 100vh;
        }

        .font-serif-title {
            font-family: 'Playfair Display', serif;
        }

        .font-romantic {
            font-family: 'Great Vibes', cursive;
        }

        .font-handwriting {
            font-family: 'Caveat', cursive;
        }

        /* Ambient Glow effect */
        .ambient-glow {
            box-shadow: 0 0 50px rgba(244, 114, 182, 0.25), inset 0 0 20px rgba(251, 207, 232, 0.1);
        }

        /* Gold accents */
        .gold-border {
            border: 1px solid rgba(212, 175, 55, 0.4);
        }

        .gold-text {
            background: linear-gradient(135deg, #ffe599 0%, #d4af37 50%, #aa7c11 100%);
            -webkit-background-clip: text;
            -webkit-text-fill-color: transparent;
        }

        /* Glassmorphic Cards */
        .glass-card {
            background: rgba(43, 11, 20, 0.65);
            backdrop-filter: blur(16px);
            -webkit-backdrop-filter: blur(16px);
            border: 1px solid rgba(244, 114, 182, 0.2);
            box-shadow: 0 20px 50px rgba(0, 0, 0, 0.5);
        }

        /* Shake animation for wrong password */
        @keyframes shake {
            0%, 100% { transform: translateX(0); }
            20%, 60% { transform: translateX(-12px); }
            40%, 80% { transform: translateX(12px); }
        }

        .shake-animation {
            animation: shake 0.5s ease-in-out;
        }

        /* Polaroid Frame style */
        .polaroid-frame {
            background: #ffffff;
            padding: 16px 16px 48px 16px;
            box-shadow: 0 15px 35px rgba(0, 0, 0, 0.4), 0 5px 15px rgba(0, 0, 0, 0.2);
            transform: rotate(-2deg);
            transition: all 0.4s cubic-bezier(0.175, 0.885, 0.32, 1.275);
            position: relative;
        }

        .polaroid-frame:hover {
            transform: rotate(0deg) scale(1.02);
            box-shadow: 0 25px 45px rgba(244, 114, 182, 0.3);
        }

        /* Tape effect on top of photo */
        .polaroid-tape {
            position: absolute;
            top: -15px;
            left: 50%;
            transform: translateX(-50%) rotate(1deg);
            width: 110px;
            height: 32px;
            background: rgba(255, 255, 255, 0.65);
            backdrop-filter: blur(2px);
            border: 1px solid rgba(255, 255, 255, 0.4);
            box-shadow: 0 2px 5px rgba(0,0,0,0.1);
            z-index: 10;
        }

        /* Pulse glow animation for lock icon */
        @keyframes heartPulse {
            0% { transform: scale(1); filter: drop-shadow(0 0 5px rgba(244,114,182,0.5)); }
            50% { transform: scale(1.1); filter: drop-shadow(0 0 20px rgba(244,114,182,0.9)); }
            100% { transform: scale(1); filter: drop-shadow(0 0 5px rgba(244,114,182,0.5)); }
        }

        .heart-pulse {
            animation: heartPulse 2s infinite ease-in-out;
        }

        /* Custom scrollbar for letter */
        .custom-scrollbar::-webkit-scrollbar {
            width: 6px;
        }
        .custom-scrollbar::-webkit-scrollbar-track {
            background: rgba(255, 255, 255, 0.05);
            border-radius: 10px;
        }
        .custom-scrollbar::-webkit-scrollbar-thumb {
            background: rgba(244, 114, 182, 0.4);
            border-radius: 10px;
        }
        .custom-scrollbar::-webkit-scrollbar-thumb:hover {
            background: rgba(244, 114, 182, 0.7);
        }

        /* Fade transitions */
        .page-transition {
            transition: opacity 0.8s ease-in-out, transform 0.8s ease-in-out;
        }
    </style>
</head>
<body class="relative flex flex-col justify-between min-h-screen select-none antialiased">

    <!-- Canvas for floating particles (hearts & sparkles) -->
    <canvas id="bgCanvas" class="fixed inset-0 pointer-events-none z-0"></canvas>

    <!-- Top Navigation / Secret Config Trigger -->
    <header class="relative z-20 w-full p-4 flex justify-between items-center max-w-6xl mx-auto">
        <div class="flex items-center space-x-2">
            <span class="text-xl text-rose-400"><i class="fa-solid fa-heart"></i></span>
            <span class="text-xs uppercase tracking-widest text-rose-200/60 font-semibold">Para Mi Persona Favorita</span>
        </div>
        
        <!-- Discreet Settings Button for the boyfriend -->
        <button id="openConfigBtn" class="text-rose-300/60 hover:text-rose-200 hover:bg-white/10 p-2.5 rounded-full transition-all duration-300 flex items-center justify-center focus:outline-none" title="Personalizar sorpresa">
            <i class="fa-solid fa-gear text-lg"></i>
        </button>
    </header>

    <!-- MAIN CONTAINER -->
    <main class="relative z-10 flex-grow flex items-center justify-center p-4">

        <!-- 1. LOCK SCREEN (PANTALLA INICIAL) -->
        <div id="lockScreen" class="w-full max-w-md glass-card rounded-3xl p-8 text-center ambient-glow page-transition">
            <!-- Romantic Lock Header -->
            <div class="mb-6">
                <div class="w-20 h-20 mx-auto mb-4 bg-rose-950/60 rounded-full flex items-center justify-center border border-rose-500/30 heart-pulse">
                    <i class="fa-solid fa-lock text-3xl text-rose-400"></i>
                </div>
                <h1 id="lockTitle" class="font-serif-title text-2xl md:text-3xl font-bold text-rose-100 mb-2 leading-tight">
                    Una sorpresa secreta te espera ❤️
                </h1>
                <p class="text-sm text-rose-200/80 font-light">
                    Ingresa el código secreto para abrir tu regalo
                </p>
            </div>

            <!-- Lock Form -->
            <form id="unlockForm" onsubmit="event.preventDefault(); attemptUnlock();" class="space-y-5">
                <div class="relative">
                    <input 
                        type="password" 
                        id="passwordInput" 
                        placeholder="Escribe la clave secreta..." 
                        class="w-full px-5 py-3.5 bg-black/40 border border-rose-400/30 rounded-2xl text-center text-rose-100 placeholder-rose-300/40 focus:outline-none focus:border-rose-400 focus:ring-2 focus:ring-rose-400/20 transition-all text-lg tracking-wider"
                        autocomplete="off"
                    >
                    <button type="button" id="togglePasswordBtn" class="absolute right-4 top-1/2 -translate-y-1/2 text-rose-300/50 hover:text-rose-200 transition">
                        <i class="fa-solid fa-eye" id="eyeIcon"></i>
                    </button>
                </div>

                <!-- Error Message Container -->
                <div id="errorMessage" class="hidden text-rose-300 text-xs bg-rose-950/80 border border-rose-500/40 px-4 py-2.5 rounded-xl transition-all">
                    <i class="fa-solid fa-heart-crack mr-1 text-rose-400"></i>
                    <span id="errorText">¡Casi! Piensa en algo especial que nos una ❤️</span>
                </div>

                <button 
                    type="submit" 
                    id="unlockBtn"
                    class="w-full py-3.5 px-6 bg-gradient-to-r from-rose-600 via-pink-600 to-rose-500 hover:from-rose-500 hover:to-pink-500 text-white font-semibold rounded-2xl shadow-lg shadow-rose-900/50 transform active:scale-95 transition-all duration-200 flex items-center justify-center space-x-2 group"
                >
                    <span>Desbloquear</span>
                    <i class="fa-solid fa-key group-hover:rotate-45 transition-transform duration-300 text-sm"></i>
                </button>
            </form>

            <p class="mt-6 text-xs text-rose-300/40 italic">
                Pista por defecto: <span class="underline cursor-pointer" onclick="fillDefaultPassword()">teamo</span>
            </p>
        </div>

        <!-- 2. REVEAL SCREEN (PANTALLA DE REVELACIÓN) -->
        <div id="revealScreen" class="hidden w-full max-w-4xl glass-card rounded-3xl p-6 md:p-10 ambient-glow page-transition opacity-0 scale-95">
            
            <div class="text-center mb-8">
                <span class="inline-block px-4 py-1.5 rounded-full bg-rose-500/10 border border-rose-400/30 text-rose-300 text-xs font-semibold tracking-widest uppercase mb-3">
                    <i class="fa-solid fa-sparkles mr-1.5 text-amber-300"></i>Solo Para Tus Ojos
                </span>
                <h2 id="revealMainTitle" class="font-serif-title text-3xl md:text-5xl font-bold gold-text leading-tight">
                    Para la persona más especial de mi mundo
                </h2>
            </div>

            <!-- Content Grid: Photo + Romantic Letter -->
            <div class="grid grid-cols-1 lg:grid-cols-12 gap-8 items-center">
                
                <!-- Polaroid Photo Container (Cols 5) -->
                <div class="lg:col-span-5 flex flex-col items-center justify-center">
                    <div class="polaroid-frame w-full max-w-xs md:max-w-sm">
                        <div class="polaroid-tape"></div>
                        <div class="w-full h-64 md:h-80 overflow-hidden rounded bg-rose-100/50 relative group">
                            <img 
                                id="revealImage" 
                                src="https://images.unsplash.com/photo-1518199266791-5375a83190b7?q=80&w=1000&auto=format&fit=crop" 
                                alt="Foto Especial" 
                                class="w-full h-full object-cover transition-transform duration-700 group-hover:scale-105"
                                onerror="this.src='https://placehold.co/600x800/2b0b14/f472b6?text=Nuestra+Foto+Especial'"
                            >
                        </div>
                        <div class="mt-4 text-center">
                            <p id="polaroidCaption" class="font-handwriting text-2xl text-slate-800 leading-none">
                                Tú & Yo, Siempre ❤️
                            </p>
                        </div>
                    </div>
                </div>

                <!-- Love Letter Container (Cols 7) -->
                <div class="lg:col-span-7 flex flex-col justify-between h-full bg-black/30 rounded-2xl p-6 border border-rose-500/20">
                    <div>
                        <div class="flex items-center space-x-2 text-rose-400 mb-3 border-b border-rose-500/20 pb-3">
                            <i class="fa-solid fa-envelope-open-text text-xl"></i>
                            <h3 id="letterHeader" class="font-serif-title font-semibold text-lg text-rose-200">Mi Carta Para Ti</h3>
                        </div>
                        <div id="letterBody" class="text-rose-100/90 text-sm md:text-base leading-relaxed space-y-4 max-h-72 md:max-h-80 overflow-y-auto custom-scrollbar pr-2 font-light">
                            <!-- Letter text rendered here dynamically -->
                        </div>
                    </div>

                    <!-- Music Player Section inside Reveal Screen -->
                    <div class="mt-6 pt-4 border-t border-rose-500/20 flex items-center justify-between bg-rose-950/40 p-3.5 rounded-xl">
                        <div class="flex items-center space-x-3 overflow-hidden">
                            <div class="w-10 h-10 rounded-full bg-rose-500/20 border border-rose-400/30 flex items-center justify-center text-rose-300 flex-shrink-0" id="musicDisk">
                                <i class="fa-solid fa-music"></i>
                            </div>
                            <div class="truncate">
                                <p class="text-xs text-rose-300/70 font-medium">Nuestra Canción</p>
                                <p id="musicTitleText" class="text-sm font-semibold text-rose-100 truncate">Melodía Romántica</p>
                            </div>
                        </div>
                        <button id="toggleAudioBtn" onclick="toggleAudio()" class="w-10 h-10 rounded-full bg-rose-600 hover:bg-rose-500 text-white flex items-center justify-center transition shadow-md flex-shrink-0">
                            <i class="fa-solid fa-play text-sm ml-0.5" id="audioPlayIcon"></i>
                        </button>
                    </div>
                </div>
            </div>

            <!-- Bottom Action: Lock Again or Share -->
            <div class="mt-8 text-center flex justify-center space-x-4">
                <button onclick="lockAgain()" class="px-5 py-2.5 rounded-xl bg-white/5 hover:bg-white/10 text-rose-200 text-xs font-medium border border-rose-400/20 transition flex items-center space-x-2">
                    <i class="fa-solid fa-lock text-xs"></i>
                    <span>Volver a bloquear</span>
                </button>
            </div>
        </div>

    </main>

    <!-- 3. CONFIGURATION MODAL (PARA EL NOVIO) -->
    <div id="configModal" class="fixed inset-0 z-50 flex items-center justify-center p-4 bg-black/80 backdrop-blur-md opacity-0 pointer-events-none transition-opacity duration-300">
        <div class="glass-card rounded-3xl w-full max-w-lg p-6 md:p-8 max-h-[90vh] overflow-y-auto custom-scrollbar border border-rose-400/40 shadow-2xl relative">
            
            <button id="closeConfigBtn" class="absolute top-5 right-5 text-rose-300/60 hover:text-rose-100 text-xl transition">
                <i class="fa-solid fa-xmark"></i>
            </button>

            <div class="mb-6">
                <h3 class="font-serif-title text-2xl font-bold gold-text flex items-center gap-2">
                    <i class="fa-solid fa-sliders text-rose-400"></i> Personalizar Sorpresa
                </h3>
                <p class="text-xs text-rose-200/70 mt-1">Configura los detalles especiales para tu novia. Todo se guardará en este navegador.</p>
            </div>

            <form id="configForm" onsubmit="event.preventDefault(); saveConfiguration();" class="space-y-4 text-sm">
                <!-- Config Passcode -->
                <div>
                    <label class="block text-rose-200 font-medium mb-1">Clave o Contraseña Secreta</label>
                    <input type="text" id="cfgPassword" class="w-full px-4 py-2.5 bg-black/50 border border-rose-500/30 rounded-xl text-rose-100 focus:outline-none focus:border-rose-400">
                    <p class="text-[11px] text-rose-300/50 mt-0.5">Ej: "teamo", la fecha de aniversario "12/05/2023" o su apodo.</p>
                </div>

                <!-- Config Image Input (URL or File) -->
                <div>
                    <label class="block text-rose-200 font-medium mb-1">Fotografía a Revelar</label>
                    <div class="space-y-2">
                        <input type="text" id="cfgImageUrl" placeholder="URL de la imagen (https://...)" class="w-full px-4 py-2.5 bg-black/50 border border-rose-500/30 rounded-xl text-rose-100 focus:outline-none focus:border-rose-400">
                        <div class="flex items-center space-x-2">
                            <span class="text-xs text-rose-300/50">o subir desde tu dispositivo:</span>
                            <label class="cursor-pointer bg-rose-900/50 hover:bg-rose-800/60 text-rose-200 text-xs px-3 py-1.5 rounded-lg border border-rose-500/30 transition flex items-center gap-1.5">
                                <i class="fa-solid fa-upload"></i> Subir Foto Local
                                <input type="file" id="cfgImageFile" accept="image/*" class="hidden" onchange="handleImageUpload(event)">
                            </label>
                        </div>
                    </div>
                </div>

                <!-- Config Polaroid Caption -->
                <div>
                    <label class="block text-rose-200 font-medium mb-1">Texto en la Foto (Polaroid)</label>
                    <input type="text" id="cfgPolaroidCaption" class="w-full px-4 py-2.5 bg-black/50 border border-rose-500/30 rounded-xl text-rose-100 focus:outline-none focus:border-rose-400">
                </div>

                <!-- Config Title -->
                <div>
                    <label class="block text-rose-200 font-medium mb-1">Título de la Carta</label>
                    <input type="text" id="cfgTitle" class="w-full px-4 py-2.5 bg-black/50 border border-rose-500/30 rounded-xl text-rose-100 focus:outline-none focus:border-rose-400">
                </div>

                <!-- Config Love Letter -->
                <div>
                    <label class="block text-rose-200 font-medium mb-1">Carta / Mensaje de Amor</label>
                    <textarea id="cfgLetter" rows="5" class="w-full px-4 py-2.5 bg-black/50 border border-rose-500/30 rounded-xl text-rose-100 focus:outline-none focus:border-rose-400 custom-scrollbar"></textarea>
                </div>

                <!-- Config Music Audio Source -->
                <div>
                    <label class="block text-rose-200 font-medium mb-1">Enlace de Audio/Música (MP3 URL)</label>
                    <input type="text" id="cfgAudioUrl" placeholder="https://ejemplo.com/cancion.mp3" class="w-full px-4 py-2.5 bg-black/50 border border-rose-500/30 rounded-xl text-rose-100 focus:outline-none focus:border-rose-400">
                    <p class="text-[11px] text-rose-300/50 mt-0.5">Si se deja en blanco, sonarás un tono o melodía de piano por defecto.</p>
                </div>

                <!-- Submit and Reset Buttons -->
                <div class="pt-4 flex items-center justify-between gap-3">
                    <button type="button" onclick="resetDefaults()" class="px-4 py-2.5 rounded-xl bg-white/5 hover:bg-white/10 text-rose-300/70 text-xs font-medium transition">
                        Restablecer por defecto
                    </button>
                    <button type="submit" class="px-6 py-2.5 rounded-xl bg-rose-600 hover:bg-rose-500 text-white font-medium shadow-md shadow-rose-900/40 transition">
                        Guardar Cambios
                    </button>
                </div>
            </form>
        </div>
    </div>

    <!-- Hidden Audio Element -->
    <audio id="romanticAudio" loop></audio>

    <!-- Footer Footer -->
    <footer class="relative z-10 w-full py-4 text-center text-xs text-rose-300/40">
        Hecho con ❤️ para una ocasión muy especial
    </footer>

    <script>
        const DEFAULT_CONFIG = {
            password: "teamo",
            imageUrl: "https://images.unsplash.com/photo-1518199266791-5375a83190b7?q=80&w=1000&auto=format&fit=crop",
            polaroidCaption: "Tú & Yo, Siempre ❤️",
            title: "Para la persona que llena mi vida de luz ❤️",
            letter: "Desde que llegaste a mi vida, cada día tiene un brillo diferente. Gracias por regalarme tu sonrisa, tu compresión y esos abrazos que curan todo.\n\nEsta pequeña sorpresa es solo un recordatorio de lo mucho que significas para mí y de lo feliz que me hace caminar a tu lado.\n\nTe amo con todo mi corazón.",
            audioUrl: "https://cdn.pixabay.com/download/audio/2022/05/27/audio_1808fbf07a.mp3?filename=romantic-piano-112188.mp3"
        };

        let currentConfig = { ...DEFAULT_CONFIG };
        let audioContext = null;
        let isAudioPlaying = false;

        // Load configuration from localStorage on startup
        function loadSettings() {
            try {
                const saved = localStorage.getItem('romantic_surprise_config');
                if (saved) {
                    currentConfig = { ...DEFAULT_CONFIG, ...JSON.parse(saved) };
                }
            } catch (e) {
                console.error("Error loading settings from localStorage:", e);
            }
            applyConfigToUI();
        }

        // Apply settings variables to HTML components
        function applyConfigToUI() {
            document.getElementById('revealImage').src = currentConfig.imageUrl;
            document.getElementById('polaroidCaption').innerText = currentConfig.polaroidCaption;
            document.getElementById('revealMainTitle').innerText = currentConfig.title;
            
            // Format letter paragraphs
            const formattedLetter = currentConfig.letter
                .split('\n')
                .map(para => para.trim() ? `<p>${escapeHTML(para)}</p>` : '')
                .join('');
            document.getElementById('letterBody').innerHTML = formattedLetter || '<p>Te amo ❤️</p>';

            // Audio element source
            const audioElem = document.getElementById('romanticAudio');
            if (currentConfig.audioUrl) {
                audioElem.src = currentConfig.audioUrl;
            } else {
                audioElem.removeAttribute('src');
            }
        }

        function escapeHTML(str) {
            return str.replace(/[&<>'"]/g, 
                tag => ({ '&': '&amp;', '<': '&lt;', '>': '&gt;', "'": '&#39;', '"': '&quot;' }[tag] || tag)
            );
        }

        // Canvas floating hearts and sparkles background
        const canvas = document.getElementById('bgCanvas');
        const ctx = canvas.getContext('2d');
        let particles = [];

        function resizeCanvas() {
            canvas.width = window.innerWidth;
            canvas.height = window.innerHeight;
        }

        window.addEventListener('resize', resizeCanvas);
        resizeCanvas();

        class Particle {
            constructor() {
                this.reset();
            }

            reset() {
                this.x = Math.random() * canvas.width;
                this.y = canvas.height + Math.random() * 20;
                this.size = Math.random() * 14 + 8;
                this.speedY = Math.random() * 1.2 + 0.4;
                this.speedX = Math.sin(Math.random() * Math.PI) * 0.5;
                this.opacity = Math.random() * 0.5 + 0.2;
                this.type = Math.random() > 0.3 ? 'heart' : 'sparkle';
                this.rotation = Math.random() * Math.PI * 2;
                this.rotSpeed = (Math.random() - 0.5) * 0.02;
            }

            update() {
                this.y -= this.speedY;
                this.x += Math.sin(this.y * 0.01) * 0.5;
                this.rotation += this.rotSpeed;

                if (this.y < -30) {
                    this.reset();
                }
            }

            draw() {
                ctx.save();
                ctx.translate(this.x, this.y);
                ctx.rotate(this.rotation);
                ctx.globalAlpha = this.opacity;

                if (this.type === 'heart') {
                    ctx.fillStyle = '#f472b6';
                    ctx.beginPath();
                    const topCurveHeight = this.size * 0.3;
                    ctx.moveTo(0, topCurveHeight);
                    // Heart bezier curves
                    ctx.bezierCurveTo(
                        0, 0, 
                        -this.size / 2, 0, 
                        -this.size / 2, topCurveHeight
                    );
                    ctx.bezierCurveTo(
                        -this.size / 2, (this.size + topCurveHeight) / 2, 
                        0, this.size, 
                        0, this.size
                    );
                    ctx.bezierCurveTo(
                        0, this.size, 
                        this.size / 2, (this.size + topCurveHeight) / 2, 
                        this.size / 2, topCurveHeight
                    );
                    ctx.bezierCurveTo(
                        this.size / 2, 0, 
                        0, 0, 
                        0, topCurveHeight
                    );
                    ctx.closePath();
                    ctx.fill();
                } else {
                    // Draw Star/Sparkle
                    ctx.fillStyle = '#fbbf24';
                    ctx.beginPath();
                    for (let i = 0; i < 4; i++) {
                        ctx.lineTo(Math.cos((i * Math.PI) / 2) * this.size * 0.5, Math.sin((i * Math.PI) / 2) * this.size * 0.5);
                        ctx.lineTo(Math.cos((i * Math.PI) / 2 + Math.PI / 4) * this.size * 0.15, Math.sin((i * Math.PI) / 2 + Math.PI / 4) * this.size * 0.15);
                    }
                    ctx.closePath();
                    ctx.fill();
                }

                ctx.restore();
            }
        }

        function initParticles() {
            particles = [];
            const count = Math.min(Math.floor(window.innerWidth / 25), 45);
            for (let i = 0; i < count; i++) {
                const p = new Particle();
                p.y = Math.random() * canvas.height; // Spread initially
                particles.push(p);
            }
        }

        function animateParticles() {
            ctx.clearRect(0, 0, canvas.width, canvas.height);
            particles.forEach(p => {
                p.update();
                p.draw();
            });
            requestAnimationFrame(animateParticles);
        }

        initParticles();
        animateParticles();

        const lockScreen = document.getElementById('lockScreen');
        const revealScreen = document.getElementById('revealScreen');
        const passwordInput = document.getElementById('passwordInput');
        const errorMessage = document.getElementById('errorMessage');

        function fillDefaultPassword() {
            passwordInput.value = currentConfig.password;
            passwordInput.focus();
        }

        function attemptUnlock() {
            const entered = passwordInput.value.trim().toLowerCase();
            const correct = currentConfig.password.trim().toLowerCase();

            if (entered === correct) {
                // Success!
                errorMessage.classList.add('hidden');
                triggerHeartConfetti();
                
                // Transition Lock -> Reveal Screen
                lockScreen.classList.add('opacity-0', 'scale-95');
                setTimeout(() => {
                    lockScreen.classList.add('hidden');
                    revealScreen.classList.remove('hidden');
                    
                    // Smooth reveal
                    setTimeout(() => {
                        revealScreen.classList.remove('opacity-0', 'scale-95');
                        revealScreen.classList.add('opacity-100', 'scale-100');
                    }, 50);

                    // Try auto playing music
                    playAudio();
                }, 500);

            } else {
                // Error animation & message
                errorMessage.classList.remove('hidden');
                lockScreen.classList.add('shake-animation');
                
                // Play soft error sound synth
                playErrorSynth();

                setTimeout(() => {
                    lockScreen.classList.remove('shake-animation');
                }, 500);
            }
        }

        function lockAgain() {
            revealScreen.classList.remove('opacity-100', 'scale-100');
            revealScreen.classList.add('opacity-0', 'scale-95');
            
            pauseAudio();

            setTimeout(() => {
                revealScreen.classList.add('hidden');
                lockScreen.classList.remove('hidden');
                setTimeout(() => {
                    lockScreen.classList.remove('opacity-0', 'scale-95');
                    passwordInput.value = '';
                }, 50);
            }, 500);
        }

        function triggerHeartConfetti() {
            if (typeof confetti !== 'undefined') {
                const duration = 3 * 1000;
                const animationEnd = Date.now() + duration;

                const heartShapes = confetti.shapeFromPath({
                    path: 'M12 21.35l-1.45-1.32C5.4 15.36 2 12.28 2 8.5 2 5.42 4.42 3 7.5 3c1.74 0 3.41.81 4.5 2.09C13.09 3.81 14.76 3 16.5 3 19.58 3 22 5.42 22 8.5c0 3.78-3.4 6.86-8.55 11.54L12 21.35z'
                });

                (function frame() {
                    const timeLeft = animationEnd - Date.now();

                    confetti({
                        particleCount: 4,
                        angle: 60,
                        spread: 55,
                        origin: { x: 0, y: 0.7 },
                        colors: ['#f472b6', '#ec4899', '#fbbf24', '#ffffff'],
                        shapes: [heartShapes],
                        scalar: 1.8
                    });
                    confetti({
                        particleCount: 4,
                        angle: 120,
                        spread: 55,
                        origin: { x: 1, y: 0.7 },
                        colors: ['#f472b6', '#ec4899', '#fbbf24', '#ffffff'],
                        shapes: [heartShapes],
                        scalar: 1.8
                    });

                    if (timeLeft > 0) {
                        requestAnimationFrame(frame);
                    }
                })();
            }
        }

        const audioElem = document.getElementById('romanticAudio');
        const audioPlayIcon = document.getElementById('audioPlayIcon');
        const musicDisk = document.getElementById('musicDisk');

        function toggleAudio() {
            if (isAudioPlaying) {
                pauseAudio();
            } else {
                playAudio();
            }
        }

        function playAudio() {
            if (audioElem.src) {
                audioElem.play().then(() => {
                    isAudioPlaying = true;
                    updateAudioUI(true);
                }).catch(e => {
                    console.log("Audio play blocked by browser or failed source:", e);
                    // Fallback to simple soft synth chord
                    playRomanticSynthLoop();
                });
            } else {
                playRomanticSynthLoop();
            }
        }

        function pauseAudio() {
            audioElem.pause();
            isAudioPlaying = false;
            updateAudioUI(false);
        }

        function updateAudioUI(playing) {
            if (playing) {
                audioPlayIcon.className = "fa-solid fa-pause text-sm";
                musicDisk.classList.add('animate-spin');
                musicDisk.style.animationDuration = '4s';
            } else {
                audioPlayIcon.className = "fa-solid fa-play text-sm ml-0.5";
                musicDisk.classList.remove('animate-spin');
            }
        }

        // Simple Web Audio API Synthesizers for sound effects & backup romantic notes
        function getAudioContext() {
            if (!audioContext) {
                audioContext = new (window.AudioContext || window.webkitAudioContext)();
            }
            if (audioContext.state === 'suspended') {
                audioContext.resume();
            }
            return audioContext;
        }

        function playErrorSynth() {
            try {
                const ctx = getAudioContext();
                const osc = ctx.createOscillator();
                const gain = ctx.createGain();
                
                osc.type = 'sine';
                osc.frequency.setValueAtTime(180, ctx.currentTime);
                osc.frequency.exponentialRampToValueAtTime(110, ctx.currentTime + 0.3);
                
                gain.gain.setValueAtTime(0.15, ctx.currentTime);
                gain.gain.exponentialRampToValueAtTime(0.01, ctx.currentTime + 0.3);

                osc.connect(gain);
                gain.connect(ctx.destination);

                osc.start();
                osc.stop(ctx.currentTime + 0.3);
            } catch (e) {
                // Ignore audio context errors if uninitialized
            }
        }

        function playRomanticSynthLoop() {
            try {
                const ctx = getAudioContext();
                const notes = [261.63, 329.63, 392.00, 523.25]; // C, E, G, C
                notes.forEach((freq, idx) => {
                    const osc = ctx.createOscillator();
                    const gain = ctx.createGain();
                    
                    osc.type = 'sine';
                    osc.frequency.setValueAtTime(freq, ctx.currentTime + idx * 0.2);
                    
                    gain.gain.setValueAtTime(0.05, ctx.currentTime + idx * 0.2);
                    gain.gain.exponentialRampToValueAtTime(0.001, ctx.currentTime + idx * 0.2 + 1.5);

                    osc.connect(gain);
                    gain.connect(ctx.destination);

                    osc.start(ctx.currentTime + idx * 0.2);
                    osc.stop(ctx.currentTime + idx * 0.2 + 1.5);
                });
                isAudioPlaying = true;
                updateAudioUI(true);
            } catch(e) {}
        }

        const configModal = document.getElementById('configModal');
        const openConfigBtn = document.getElementById('openConfigBtn');
        const closeConfigBtn = document.getElementById('closeConfigBtn');

        openConfigBtn.addEventListener('click', () => {
            // Fill inputs with currentConfig
            document.getElementById('cfgPassword').value = currentConfig.password;
            document.getElementById('cfgImageUrl').value = currentConfig.imageUrl.startsWith('data:') ? '' : currentConfig.imageUrl;
            document.getElementById('cfgPolaroidCaption').value = currentConfig.polaroidCaption;
            document.getElementById('cfgTitle').value = currentConfig.title;
            document.getElementById('cfgLetter').value = currentConfig.letter;
            document.getElementById('cfgAudioUrl').value = currentConfig.audioUrl || '';

            configModal.classList.remove('opacity-0', 'pointer-events-none');
        });

        closeConfigBtn.addEventListener('click', () => {
            configModal.classList.add('opacity-0', 'pointer-events-none');
        });

        function handleImageUpload(event) {
            const file = event.target.files[0];
            if (file) {
                const reader = new FileReader();
                reader.onload = function(e) {
                    currentConfig.imageUrl = e.target.result;
                    document.getElementById('cfgImageUrl').value = '';
                };
                reader.readAsDataURL(file);
            }
        }

        function saveConfiguration() {
            const newPass = document.getElementById('cfgPassword').value.trim();
            const newImgUrl = document.getElementById('cfgImageUrl').value.trim();
            const newCaption = document.getElementById('cfgPolaroidCaption').value.trim();
            const newTitle = document.getElementById('cfgTitle').value.trim();
            const newLetter = document.getElementById('cfgLetter').value.trim();
            const newAudio = document.getElementById('cfgAudioUrl').value.trim();

            if (newPass) currentConfig.password = newPass;
            if (newImgUrl) currentConfig.imageUrl = newImgUrl;
            if (newCaption) currentConfig.polaroidCaption = newCaption;
            if (newTitle) currentConfig.title = newTitle;
            if (newLetter) currentConfig.letter = newLetter;
            currentConfig.audioUrl = newAudio;

            try {
                localStorage.setItem('romantic_surprise_config', JSON.stringify(currentConfig));
            } catch (e) {
                console.warn("Storage quota exceeded, changes applied in memory only.");
            }

            applyConfigToUI();
            configModal.classList.add('opacity-0', 'pointer-events-none');
        }

        function resetDefaults() {
            currentConfig = { ...DEFAULT_CONFIG };
            try {
                localStorage.removeItem('romantic_surprise_config');
            } catch (e) {}
            applyConfigToUI();
            configModal.classList.add('opacity-0', 'pointer-events-none');
        }

        // Toggle password visibility
        document.getElementById('togglePasswordBtn').addEventListener('click', () => {
            const eyeIcon = document.getElementById('eyeIcon');
            if (passwordInput.type === 'password') {
                passwordInput.type = 'text';
                eyeIcon.className = 'fa-solid fa-eye-slash';
            } else {
                passwordInput.type = 'password';
                eyeIcon.className = 'fa-solid fa-eye';
            }
        });

        // Initialize on window load
        window.onload = function() {
            loadSettings();
        };
    </script>
</body>
</html>
