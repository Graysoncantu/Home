<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Grayson Cantu — Portfolio</title>
    <script src="https://cdn.jsdelivr.net/npm/@tailwindcss/browser@4"></script>
    <script src="https://cdnjs.cloudflare.com/ajax/libs/three.js/r128/three.min.js"></script>
    <style>
        @import url('https://fonts.googleapis.com/css2?family=Plus+Jakarta+Sans:wght@300;400;500;600&family=Space+Grotesk:wght@300;400;700&display=swap');
        
        body {
            background-color: #000000;
            color: #ffffff;
            font-family: 'Plus Jakarta Sans', sans-serif;
            overflow-x: hidden;
        }
        .mono-title {
            font-family: 'Space Grotesk', sans-serif;
            letter-spacing: -0.05em;
        }
        #canvas-container {
            position: fixed;
            top: 0;
            left: 0;
            width: 100vw;
            height: 100vh;
            z-index: 1;
            pointer-events: none;
            opacity: 0.25; /* Subtle background depth */
        }
        .content-layer {
            position: relative;
            z-index: 2;
        }
        .blur-panel {
            background: rgba(10, 10, 10, 0.7);
            backdrop-filter: blur(12px);
            border: 1px solid rgba(255, 255, 255, 0.05);
        }
    </style>
</head>
<body class="p-6 md:p-16 min-h-screen flex flex-col justify-between">

    <div id="canvas-container"></div>

    <div class="content-layer max-w-4xl w-full mx-auto flex-grow flex flex-col justify-between gap-16">
        
        <header class="flex justify-between items-start border-b border-white/5 pb-8">
            <div>
                <h1 class="mono-title text-4xl font-bold tracking-tight mb-1">GRAYSON CANTU</h1>
                <p class="text-xs uppercase tracking-widest text-white/40 font-medium">Technical Writer & Operations</p>
            </div>
            <div class="text-right text-xs text-white/40 font-mono">
                [ 2026 // PORTFOLIO ]
            </div>
        </header>

        <main class="grid md:grid-cols-5 gap-12 my-auto">
            <div class="md:col-span-2 space-y-4">
                <span class="text-xs font-mono text-white/30">// OVERVIEW</span>
                <p class="text-lg text-white/80 font-light leading-relaxed">
                    A curated repository of structured documentation, technical workflows, and operational architectures built for system efficiency.
                </p>
            </div>
            
            <div class="md:col-span-3 space-y-4">
                <span class="text-xs font-mono text-white/30">// COMPETENCIES</span>
                <ul class="space-y-3 text-sm">
                    <li class="flex items-baseline gap-3"><span class="font-mono text-white/30">01</span> <span><strong>Technical Writing:</strong> Low-friction, actionable internal documentation.</span></li>
                    <li class="flex items-baseline gap-3"><span class="font-mono text-white/30">02</span> <span><strong>Systems Optimization:</strong> Scaling complex, repeatable frameworks.</span></li>
                    <li class="flex items-baseline gap-3"><span class="font-mono text-white/30">03</span> <span><strong>Data Synthesis:</strong> Transforming raw metrics into high-level strategy.</span></li>
                </ul>
            </div>
        </main>

        <section class="space-y-4">
            <span class="text-xs font-mono text-white/30">// ARTIFACT MANIFEST</span>
            <div class="grid sm:grid-cols-2 gap-4">
                
                <div class="blur-panel p-6 rounded-lg transition-all duration-300 hover:border-white/20 group">
                    <div class="flex justify-between items-start mb-4">
                        <h3 class="font-medium text-sm text-white/90 group-hover:text-white">Transitioning Strategy</h3>
                        <span class="text-[10px] font-mono px-2 py-0.5 border border-white/10 rounded text-white/50">STRATEGY</span>
                    </div>
                    <p class="text-xs text-white/50 font-light">Change management, risk mitigation, and structural impact analysis.</p>
                </div>

                <div class="blur-panel p-6 rounded-lg transition-all duration-300 hover:border-white/20 group">
                    <div class="flex justify-between items-start mb-4">
                        <h3 class="font-medium text-sm text-white/90 group-hover:text-white">Exporting Analytics Data</h3>
                        <span class="text-[10px] font-mono px-2 py-0.5 border border-white/10 rounded text-white/50">DATA & BI</span>
                    </div>
                    <p class="text-xs text-white/50 font-light">Data extraction methodologies, pipeline processing, and reporting frameworks.</p>
                </div>

                <div class="blur-panel p-6 rounded-lg transition-all duration-300 hover:border-white/20 group">
                    <div class="flex justify-between items-start mb-4">
                        <h3 class="font-medium text-sm text-white/90 group-hover:text-white">Standard Operating Procedure</h3>
                        <span class="text-[10px] font-mono px-2 py-0.5 border border-white/10 rounded text-white/50">SYSTEMS</span>
                    </div>
                    <p class="text-xs text-white/50 font-light">Compliance protocols, QA frameworks, and cross-team execution guardrails.</p>
                </div>

                <div class="blur-panel p-6 rounded-lg transition-all duration-300 hover:border-white/20 group">
                    <div class="flex justify-between items-start mb-4">
                        <h3 class="font-medium text-sm text-white/90 group-hover:text-white">Frontend Environment Recovery</h3>
                        <span class="text-[10px] font-mono px-2 py-0.5 border border-white/10 rounded text-white/50">DEV OPS</span>
                    </div>
                    <p class="text-xs text-white/50 font-light">Technical debugging sequences and local dependency environment management.</p>
                </div>

            </div>
        </section>

        <footer class="text-[11px] font-mono text-white/20 flex justify-between border-t border-white/5 pt-6">
            <span>&copy; 2026 GRAYSON CANTU</span>
            <span>MINIMALIST OPERATIONAL PORTFOLIO v2.0</span>
        </footer>
    </div>

    <script>
        const container = document.getElementById('canvas-container');
        const scene = new THREE.Scene();
        
        const camera = new THREE.PerspectiveCamera(60, window.innerWidth / window.innerHeight, 0.1, 1000);
        camera.position.z = 40;

        const renderer = new THREE.WebGLRenderer({ alpha: true, antialias: true });
        renderer.setSize(window.innerWidth, window.innerHeight);
        container.appendChild(renderer.domElement);

        // Generate a 3D monochrome Wireframe Torus Knot for abstract tech visuals
        const geometry = new THREE.TorusKnotGeometry(12, 3, 120, 16);
        const material = new THREE.MeshBasicMaterial({
            color: 0xffffff,
            wireframe: true,
            transparent: true,
            opacity: 0.15
        });
        const mesh = new THREE.Mesh(geometry, material);
        scene.add(mesh);

        // Animation Loop
        function animate() {
            requestAnimationFrame(animate);
            mesh.rotation.x += 0.002;
            mesh.rotation.y += 0.003;
            renderer.render(scene, camera);
        }
        animate();

        // Responsive resizing
        window.addEventListener('resize', () => {
            camera.aspect = window.innerWidth / window.innerHeight;
            camera.updateProjectionMatrix();
            renderer.setSize(window.innerWidth, window.innerHeight);
        });
    </script>
</body>
</html>
