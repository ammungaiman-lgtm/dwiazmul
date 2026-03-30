<!DOCTYPE html>
<html lang="id">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>M.Dwi Azmulaiman | Beyond Limits</title>
    <script src="https://cdn.tailwindcss.com"></script>
    <link href="https://fonts.googleapis.com/css2?family=Space+Grotesk:wght@300;500;700&family=Syncopate:wght@400;700&display=swap" rel="stylesheet">
    <script src="https://cdnjs.cloudflare.com/ajax/libs/three.js/r128/three.min.js"></script>
    <script src="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.4.0/js/all.min.js"></script>
    <style>
        :root {
            --neon-blue: #00f3ff;
            --neon-purple: #bc13fe;
            --dark-bg: #050505;
        }

        body {
            background-color: var(--dark-bg);
            color: #ffffff;
            font-family: 'Space Grotesk', sans-serif;
            margin: 0;
            overflow-x: hidden;
        }

        .syncopate { font-family: 'Syncopate', sans-serif; }

        #canvas-container {
            position: fixed;
            top: 0;
            left: 0;
            width: 100%;
            height: 100%;
            z-index: -1;
            background: radial-gradient(circle at center, #111 0%, #000 100%);
        }

        .text-reveal {
            background: linear-gradient(to right, var(--neon-blue), var(--neon-purple), var(--neon-blue));
            background-size: 200% auto;
            -webkit-background-clip: text;
            -webkit-text-fill-color: transparent;
            animation: shine 3s linear infinite;
        }

        @keyframes shine {
            to { background-position: 200% center; }
        }

        .hero-title {
            font-size: clamp(3rem, 15vw, 12rem);
            line-height: 0.8;
            letter-spacing: -0.05em;
            text-transform: uppercase;
        }

        .glass-card {
            background: rgba(255, 255, 255, 0.02);
            backdrop-filter: blur(20px);
            border: 1px solid rgba(255, 255, 255, 0.1);
            transition: all 0.5s cubic-bezier(0.23, 1, 0.32, 1);
        }

        .glass-card:hover {
            background: rgba(255, 255, 255, 0.05);
            border-color: var(--neon-blue);
            box-shadow: 0 0 30px rgba(0, 243, 255, 0.2);
            transform: translateY(-10px);
        }

        .btn-cyber {
            position: relative;
            padding: 1rem 2.5rem;
            background: transparent;
            border: 2px solid var(--neon-blue);
            color: var(--neon-blue);
            font-weight: bold;
            text-transform: uppercase;
            overflow: hidden;
            transition: 0.3s;
            cursor: pointer;
        }

        .btn-cyber:hover {
            background: var(--neon-blue);
            color: black;
            box-shadow: 0 0 20px var(--neon-blue);
        }

        .nav-fixed {
            writing-mode: vertical-rl;
            position: fixed;
            right: 2rem;
            top: 50%;
            transform: translateY(-50%);
            z-index: 100;
        }

        .scroll-indicator {
            width: 2px;
            height: 100px;
            background: linear-gradient(to bottom, var(--neon-blue), transparent);
            margin: 20px auto;
        }

        section {
            min-height: 100vh;
            padding: 100px 5%;
            display: flex;
            flex-direction: column;
            justify-content: center;
        }

        .skill-grid {
            display: grid;
            grid-template-columns: repeat(auto-fit, minmax(250px, 1fr));
            gap: 20px;
        }

        .big-number {
            font-size: 8rem;
            font-weight: 900;
            opacity: 0.05;
            position: absolute;
            top: -2rem;
            right: 1rem;
        }

        ::-webkit-scrollbar { width: 5px; }
        ::-webkit-scrollbar-track { background: #000; }
        ::-webkit-scrollbar-thumb { background: var(--neon-blue); }
    </style>
</head>
<body>

    <div id="canvas-container"></div>

    <!-- Nav Bar Samping -->
    <div class="nav-fixed hidden md:flex items-center gap-8 uppercase tracking-[0.3em] text-[10px] font-bold text-gray-500">
        <a href="#home" class="hover:text-white transition">Home</a>
        <a href="#about" class="hover:text-white transition">About</a>
        <a href="#education" class="hover:text-white transition">Education</a>
        <a href="#skills" class="hover:text-white transition">Capabilities</a>
        <a href="#contact" class="hover:text-white transition">Contact</a>
        <div class="scroll-indicator"></div>
    </div>

    <!-- Home -->
    <section id="home">
        <div class="relative z-10">
            <p class="syncopate text-sm tracking-[0.5em] text-cyan-400 mb-4 animate-pulse">AVAILABLE FOR HIRE 2026</p>
            <h1 class="hero-title syncopate font-bold mb-4">
                M.DWI <br> <span class="text-reveal">AZMULAIMAN</span>
            </h1>
            <p class="text-2xl md:text-4xl font-light text-gray-400 max-w-3xl leading-tight">
                Mendefinisikan ulang batas antara <span class="text-white font-medium italic">Teknologi Jaringan</span> dan <span class="text-white font-medium italic">Kreativitas Visual</span>.
            </p>
            <div class="mt-12 flex gap-6">
                <button onclick="location.href='#contact'" class="btn-cyber">Bekerjasama</button>
                <button onclick="location.href='#about'" class="px-8 py-4 border border-white/10 hover:bg-white/5 transition uppercase font-bold text-xs tracking-widest">Detail Profil</button>
            </div>
        </div>
    </section>

    <!-- About -->
    <section id="about">
        <div class="grid lg:grid-cols-2 gap-20 items-center">
            <div class="glass-card p-12 relative overflow-hidden">
                <span class="big-number italic">01</span>
                <h2 class="text-4xl font-bold mb-10 syncopate">DATA <span class="text-cyan-400">PRIBADI</span></h2>
                <div class="space-y-8">
                    <div class="flex justify-between items-end border-b border-white/10 pb-4">
                        <span class="text-gray-500 uppercase tracking-widest text-xs">Full Name</span>
                        <span class="text-2xl font-bold">M.Dwi Azmulaiman</span>
                    </div>
                    <div class="flex justify-between items-end border-b border-white/10 pb-4">
                        <span class="text-gray-500 uppercase tracking-widest text-xs">Birth Date</span>
                        <span class="text-xl font-bold">14 Agustus 2008</span>
                    </div>
                    <div class="flex justify-between items-end border-b border-white/10 pb-4">
                        <span class="text-gray-500 uppercase tracking-widest text-xs">Origin</span>
                        <span class="text-xl font-bold text-right">Bumiayu, Brebes</span>
                    </div>
                    <div class="flex justify-between items-end border-b border-white/10 pb-4">
                        <span class="text-gray-500 uppercase tracking-widest text-xs">Identity</span>
                        <span class="text-xl font-bold">WNI / Pria</span>
                    </div>
                </div>
            </div>
            <div>
                <h3 class="text-6xl font-bold mb-6 italic text-reveal">FRESH GRADUATE.</h3>
                <p class="text-xl text-gray-400 leading-relaxed">
                    Berbekal latar belakang pendidikan di <span class="text-white">Teknik Jaringan Komputer</span>, saya menggabungkan logika sistem dengan estetika desain untuk menciptakan solusi digital yang berdampak luas.
                </p>
            </div>
        </div>
    </section>

    <!-- Education -->
    <section id="education">
        <div class="max-w-4xl">
            <h2 class="text-7xl font-bold mb-20 syncopate tracking-tighter">LEVEL <span class="text-purple-500">UP</span></h2>
            <div class="space-y-4">
                <div class="glass-card p-8 group hover:pl-12 transition-all">
                    <div class="flex flex-col md:flex-row md:items-center justify-between gap-4">
                        <div>
                            <h4 class="text-blue-400 font-bold mb-2 tracking-widest">2023 - 2026</h4>
                            <h3 class="text-3xl font-bold uppercase">SMK Al-Huda Bumiayu</h3>
                            <p class="text-gray-500">Teknik Jaringan Komputer Dan Telekomunikasi</p>
                        </div>
                        <i class="fas fa-arrow-right text-2xl opacity-0 group-hover:opacity-100 transition text-blue-500"></i>
                    </div>
                </div>
                <div class="glass-card p-8 opacity-60">
                    <h4 class="text-gray-500 font-bold mb-2">2020 - 2023</h4>
                    <h3 class="text-xl font-bold">SMP Islam Ta'alumul Huda Bumiayu</h3>
                </div>
                <div class="glass-card p-8 opacity-40">
                    <h4 class="text-gray-500 font-bold mb-2">2014 - 2020</h4>
                    <h3 class="text-xl font-bold">SD Negeri 03 Bumiayu</h3>
                </div>
            </div>
        </div>
    </section>

    <!-- Skills -->
    <section id="skills">
        <div class="text-right mb-20">
            <h2 class="text-7xl font-bold syncopate">SKILLS <span class="text-cyan-400">&</span> TOOLS</h2>
        </div>
        <div class="skill-grid">
            <div class="glass-card p-10 group">
                <div class="w-16 h-16 border-2 border-cyan-500 flex items-center justify-center mb-6 group-hover:rotate-45 transition-transform">
                    <i class="fas fa-pen-nib text-2xl"></i>
                </div>
                <h3 class="text-2xl font-bold mb-4">Desain Grafis</h3>
                <p class="text-gray-400">Ekspresi visual melalui komposisi warna dan bentuk yang presisi.</p>
            </div>
            <div class="glass-card p-10 group">
                <div class="w-16 h-16 border-2 border-purple-500 flex items-center justify-center mb-6 group-hover:rotate-45 transition-transform">
                    <i class="fas fa-film text-2xl"></i>
                </div>
                <h3 class="text-2xl font-bold mb-4">Editor Multimedia</h3>
                <p class="text-gray-400">Manipulasi foto dan video untuk narasi visual yang kuat.</p>
            </div>
            <div class="glass-card p-10 group">
                <div class="w-16 h-16 border-2 border-white flex items-center justify-center mb-6 group-hover:rotate-45 transition-transform">
                    <i class="fas fa-microchip text-2xl"></i>
                </div>
                <h3 class="text-2xl font-bold mb-4">IT Ops</h3>
                <p class="text-gray-400">Instalasi jaringan dan pengoperasian software perkantoran secara mahir.</p>
            </div>
        </div>
    </section>

    <!-- Experience PKL -->
    <section>
        <div class="glass-card p-20 text-center border-none bg-gradient-to-br from-blue-600/10 to-purple-600/10">
            <p class="text-blue-400 font-bold tracking-[0.5em] mb-6 uppercase">Professional Exposure</p>
            <h2 class="text-5xl md:text-7xl font-bold mb-8 italic">PKL @ KANTOR KEC. BUMIAYU</h2>
            <p class="text-2xl text-gray-400 max-w-2xl mx-auto font-light leading-relaxed">
                Transformasi teori administrasi dan teknologi menjadi aksi nyata dalam pelayanan publik.
            </p>
        </div>
    </section>

    <!-- Contact -->
    <section id="contact">
        <div class="text-center mb-20">
            <h2 class="text-8xl font-black syncopate tracking-tighter opacity-10">CONTACT</h2>
            <h3 class="text-4xl md:text-6xl font-bold -mt-16 text-reveal italic">READY TO BLAST OFF?</h3>
        </div>
        <div class="grid md:grid-cols-2 gap-6 max-w-5xl mx-auto w-full">
            <a href="mailto:azmulaiman290@gmail.com" class="btn-cyber flex items-center justify-center gap-4 py-8">
                <i class="fas fa-paper-plane text-xl"></i>
                azmulaiman290@gmail.com
            </a>
            <a href="tel:+6283823959657" class="btn-cyber flex items-center justify-center gap-4 py-8" style="border-color: white; color: white;">
                <i class="fas fa-phone-alt text-xl"></i>
                +62 838 2395 9657
            </a>
        </div>
        <div class="mt-20 text-center text-gray-600 text-xs tracking-[1em] uppercase">
            Bumiayu • Indonesia • Global
        </div>
    </section>

    <script>
        // Three.js Core Setup
        const scene = new THREE.Scene();
        const camera = new THREE.PerspectiveCamera(75, window.innerWidth / window.innerHeight, 0.1, 1000);
        const renderer = new THREE.WebGLRenderer({ antialias: true, alpha: true });
        
        renderer.setSize(window.innerWidth, window.innerHeight);
        document.getElementById('canvas-container').appendChild(renderer.domElement);

        // Geometri Animasi
        const particlesGeometry = new THREE.BufferGeometry();
        const particlesCount = 5000;
        const posArray = new Float32Array(particlesCount * 3);

        for(let i = 0; i < particlesCount * 3; i++) {
            posArray[i] = (Math.random() - 0.5) * 100;
        }

        particlesGeometry.setAttribute('position', new THREE.BufferAttribute(posArray, 3));
        const particlesMaterial = new THREE.PointsMaterial({
            size: 0.02,
            color: '#00f3ff',
            transparent: true,
            opacity: 0.5
        });

        const particlesMesh = new THREE.Points(particlesGeometry, particlesMaterial);
        scene.add(particlesMesh);

        camera.position.z = 30;

        // Mouse Interactivity
        let mouseX = 0;
        let mouseY = 0;

        document.addEventListener('mousemove', (event) => {
            mouseX = event.clientX;
            mouseY = event.clientY;
        });

        function animate() {
            requestAnimationFrame(animate);
            
            particlesMesh.rotation.y += 0.001;
            if (mouseX > 0) {
                particlesMesh.rotation.x += (mouseY * 0.00001);
                particlesMesh.rotation.y += (mouseX * 0.00001);
            }
            
            renderer.render(scene, camera);
        }

        animate();

        // Responsive
        window.addEventListener('resize', () => {
            camera.aspect = window.innerWidth / window.innerHeight;
            camera.updateProjectionMatrix();
            renderer.setSize(window.innerWidth, window.innerHeight);
        });

        // GSAP-like Scroll Reveal (Simple Vanilla)
        const observerOptions = { threshold: 0.1 };
        const observer = new IntersectionObserver((entries) => {
            entries.forEach(entry => {
                if (entry.isIntersecting) {
                    entry.target.style.opacity = "1";
                    entry.target.style.transform = "translateY(0)";
                }
            });
        }, observerOptions);

        document.querySelectorAll('section > div').forEach(el => {
            el.style.opacity = "0";
            el.style.transform = "translateY(30px)";
            el.style.transition = "all 1s ease-out";
            observer.observe(el);
        });
    </script>
</body>
</html>
