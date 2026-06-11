<!DOCTYPE html>
<html lang="es">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0, viewport-fit=cover">
  <title>Senderismo | Mi historia en Colombia</title>
  <!-- Tailwind CSS v3 + Font Awesome (redes) -->
  <script src="https://cdn.tailwindcss.com"></script>
  <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.0.0-beta3/css/all.min.css">
  <style>
    @import url('https://fonts.googleapis.com/css2?family=Inter:opsz,wght@14..32,300;14..32,400;14..32,600;14..32,700&display=swap');
    body { font-family: 'Inter', sans-serif; }
    .card-hover { transition: transform 0.2s ease, box-shadow 0.2s ease; }
    .card-hover:hover { transform: translateY(-4px); box-shadow: 0 12px 20px -12px rgba(0,0,0,0.2); }
    html { scroll-behavior: smooth; }
  </style>
</head>
<body class="bg-gradient-to-b from-[#fef9f0] to-[#e9f5e9] text-gray-800">

  <!-- Header con menú hamburguesa -->
  <header class="sticky top-0 z-30 bg-white/80 backdrop-blur-md shadow-sm">
    <div class="container mx-auto px-4 py-3 flex justify-between items-center">
      <h1 class="text-xl font-bold text-green-800">🌲 Huella Verde</h1>
      <button id="menu-btn" class="block md:hidden text-green-800 focus:outline-none">
        <svg class="w-6 h-6" fill="none" stroke="currentColor" viewBox="0 0 24 24"><path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M4 6h16M4 12h16M4 18h16"/></svg>
      </button>
      <nav id="menu" class="hidden md:flex space-x-6 text-sm font-medium">
        <a href="#historia" class="hover:text-green-700">Historia</a>
        <a href="#beneficios" class="hover:text-green-700">Beneficios</a>
        <a href="#gamificacion" class="hover:text-green-700">Desafío</a>
        <a href="#galeria" class="hover:text-green-700">Galería</a>
        <a href="#recursos" class="hover:text-green-700">Recursos</a>
        <a href="#contacto" class="hover:text-green-700">Contacto</a>
      </nav>
    </div>
    <div id="mobile-menu" class="hidden md:hidden bg-white border-t border-gray-200 py-2 px-4 flex flex-col space-y-3">
      <a href="#historia" class="hover:text-green-700 py-1">Historia</a>
      <a href="#beneficios" class="hover:text-green-700 py-1">Beneficios</a>
      <a href="#gamificacion" class="hover:text-green-700 py-1">Desafío</a>
      <a href="#galeria" class="hover:text-green-700 py-1">Galería</a>
      <a href="#recursos" class="hover:text-green-700 py-1">Recursos</a>
      <a href="#contacto" class="hover:text-green-700 py-1">Contacto</a>
    </div>
  </header>

  <main>
    <!-- Hero con tu imagen de portada (Imgur) -->
    <section class="relative min-h-[85vh] flex items-center justify-center text-center px-4 bg-cover bg-center" 
             style="background-image: linear-gradient(0deg, rgba(0,0,0,0.5), rgba(0,0,0,0.3)), url('https://i.imgur.com/3ZIGABM.jpeg');">
      <div class="text-white max-w-2xl">
        <span class="inline-block px-3 py-1 bg-green-700/70 rounded-full text-sm backdrop-blur-sm mb-4">🏔️ Desde los 3 años en la montaña</span>
        <h2 class="text-4xl md:text-6xl font-extrabold mb-4 drop-shadow">Senderismo: mi primera aventura</h2>
        <p class="text-lg md:text-xl mb-8 drop-shadow">Descubre cómo caminar por la naturaleza transformó mi vida y cómo tú también puedes empezar.</p>
        <a href="#historia" class="bg-amber-600 hover:bg-amber-700 text-white font-semibold px-7 py-3 rounded-full shadow-lg transition">Empieza a explorar →</a>
      </div>
    </section>

    <!-- Mi historia (texto actualizado) + video de YouTube -->
    <section id="historia" class="py-16 px-4 max-w-6xl mx-auto">
      <div class="grid md:grid-cols-2 gap-10 items-center">
        <div>
          <span class="text-green-700 font-semibold tracking-wide">📖 Mi historia</span>
          <h3 class="text-3xl font-bold mt-2 mb-4">De las primeras caminatas a las cumbres</h3>
          <p class="text-gray-700 mb-4 leading-relaxed">Todo comenzó a los 3 años al subir el imponente cerro Cristo Rey en Támesis Antioquia con mi madre. Desde ese día, cada fin de semana se convirtió en un ritual donde descubría un nuevo árbol, un río, y sentía esa libertad que hoy quiero compartir contigo.</p>
          <p class="text-gray-700 mb-6">A lo largo de los años he recorrido más de <strong class="text-green-700" id="kmCounter">1,000</strong> km por rutas de toda Colombia. ¡Tú también puedes sumar kilómetros a tu vida!</p>
          <!-- Mini gamificación -->
          <div class="bg-white p-5 rounded-2xl shadow-md border border-green-100">
            <p class="font-semibold text-green-800 flex items-center gap-2">🎮 Desafío semanal: ¡Suma km virtuales!</p>
            <div class="flex items-center gap-4 mt-3 flex-wrap">
              <button id="sumarKmBtn" class="bg-green-600 hover:bg-green-700 text-white px-4 py-2 rounded-full text-sm">➕ Caminar +5 km</button>
              <p class="text-sm text-gray-500">Km acumulados: <span id="kmUser">0</span> <span class="text-xs">(loguea tu progreso)</span></p>
            </div>
            <p id="logroMsg" class="text-xs text-amber-600 mt-2 italic"></p>
          </div>
        </div>
        <div class="rounded-2xl overflow-hidden shadow-xl aspect-video">
          <!-- Video de YouTube (ID: eGdUdpaXjxk) -->
          <iframe class="w-full h-full" src="https://www.youtube.com/embed/eGdUdpaXjxk" title="Mi primera gran travesía: Cerro Cristo Rey, Támesis" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture" allowfullscreen></iframe>
          <p class="text-center text-sm text-gray-500 mt-2">🎥 Mi primera gran travesía: Cerro Cristo Rey, Támesis</p>
        </div>
      </div>
    </section>

    <!-- Beneficios, retos y tendencias -->
    <section id="beneficios" class="bg-white/60 py-16 px-4">
      <div class="max-w-6xl mx-auto">
        <div class="text-center mb-12">
          <h3 class="text-3xl font-bold">🌿 ¿Por qué el senderismo?</h3>
          <p class="text-gray-600 mt-2">Beneficios, obstáculos reales y lo que viene en ecoturismo</p>
        </div>
        <div class="grid sm:grid-cols-2 lg:grid-cols-3 gap-8">
          <div class="bg-white rounded-xl p-6 shadow-md card-hover border-l-4 border-green-500">
            <div class="text-4xl mb-3">❤️‍🔥</div>
            <h4 class="text-xl font-bold">Beneficios</h4>
            <p class="text-gray-600 mt-2">Reduce estrés, mejora capacidad cardiovascular y conecta con la naturaleza. Ideal para desconectar del celular.</p>
          </div>
          <div class="bg-white rounded-xl p-6 shadow-md card-hover border-l-4 border-amber-500">
            <div class="text-4xl mb-3">⚠️</div>
            <h4 class="text-xl font-bold">Retos comunes</h4>
            <p class="text-gray-600 mt-2">Falta de tiempo, equipo inadecuado, clima impredecible. Pero con planificación se superan.</p>
          </div>
          <div class="bg-white rounded-xl p-6 shadow-md card-hover border-l-4 border-emerald-500">
            <div class="text-4xl mb-3">📈</div>
            <h4 class="text-xl font-bold">Nuevas tendencias</h4>
            <p class="text-gray-600 mt-2">Senderismo nocturno, apps de identificación de flora, turismo regenerativo y retiros de bienestar en montaña.</p>
          </div>
        </div>
      </div>
    </section>

    <!-- Gamificación principal: sube la montaña -->
    <section id="gamificacion" class="py-16 px-4 max-w-5xl mx-auto">
      <div class="bg-gradient-to-r from-amber-50 to-green-50 rounded-3xl p-6 md:p-10 shadow-lg text-center">
        <h3 class="text-2xl md:text-3xl font-bold">⛰️ Sube la montaña virtual</h3>
        <p class="mt-2 mb-6">Haz clic en el botón para subir escalones. Cada 10 clics obtienes una insignia.</p>
        <div class="bg-white w-48 h-48 rounded-full mx-auto flex items-center justify-center shadow-inner border-4 border-green-300">
          <span id="alturaDisplay" class="text-4xl font-bold text-green-800">0 m</span>
        </div>
        <div class="mt-6 flex gap-4 justify-center">
          <button id="subirBtn" class="bg-green-700 hover:bg-green-800 text-white font-bold py-3 px-8 rounded-full transition text-lg">🚶‍♂️ Subir +10 m</button>
          <button id="resetBtn" class="bg-gray-400 hover:bg-gray-500 text-white px-5 rounded-full">Reiniciar</button>
        </div>
        <p id="insigniaMsg" class="mt-5 text-amber-700 font-semibold"></p>
        <div class="flex justify-center gap-2 mt-4 text-2xl" id="medallas"></div>
      </div>
    </section>

    <!-- Galería "Momentos en la naturaleza" con tus 4 imágenes de Imgur -->
    <section id="galeria" class="py-16 px-4 max-w-6xl mx-auto">
      <h3 class="text-3xl font-bold text-center mb-4">📸 Momentos en la naturaleza</h3>
      <div class="grid grid-cols-2 md:grid-cols-4 gap-3">
        <img class="rounded-xl w-full h-40 object-cover shadow" src="https://i.imgur.com/vUgHvuG.jpeg" alt="Momento 1">
        <img class="rounded-xl w-full h-40 object-cover shadow" src="https://i.imgur.com/YcIXwtJ.jpeg" alt="Momento 2">
        <img class="rounded-xl w-full h-40 object-cover shadow" src="https://i.imgur.com/uBSrfpg.jpeg" alt="Momento 3">
        <img class="rounded-xl w-full h-40 object-cover shadow" src="https://i.imgur.com/3m7m7e5.jpeg" alt="Momento 4">
      </div>
      <!-- Video final: nueva aventura en YouTube -->
      <div class="mt-8 aspect-video rounded-2xl overflow-hidden shadow-xl">
        <iframe class="w-full h-full" src="https://www.youtube.com/embed/p1mzqklFrL0" title="Mi nueva aventura en el senderismo" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture" allowfullscreen></iframe>
      </div>
    </section>

    <!-- Recursos académicos (links proporcionados) -->
    <section id="recursos" class="py-16 px-4 bg-gradient-to-r from-green-50 to-amber-50">
      <div class="max-w-5xl mx-auto">
        <h3 class="text-3xl font-bold text-center mb-8">📚 Saber más: recursos académicos</h3>
        <div class="grid sm:grid-cols-2 gap-5">
          <a href="http://dspace.unach.edu.ec/handle/51000/16693" target="_blank" rel="noopener noreferrer" class="bg-white p-4 rounded-xl shadow hover:shadow-lg transition flex items-center gap-3">
            <span class="text-2xl">📄</span>
            <span>Beneficios del senderismo - Estudio UNACH</span>
          </a>
          <a href="https://chile.as.com/masdeporte/neuronaturaleza-lo-que-el-senderismo-le-hace-a-tu-cerebro-y-no-sabias-n/" target="_blank" rel="noopener noreferrer" class="bg-white p-4 rounded-xl shadow hover:shadow-lg transition flex items-center gap-3">
            <span class="text-2xl">🧠</span>
            <span>Neuronaturaleza: lo que el senderismo le hace a tu cerebro</span>
          </a>
          <a href="https://pubmed.ncbi.nlm.nih.gov/26124129/" target="_blank" rel="noopener noreferrer" class="bg-white p-4 rounded-xl shadow hover:shadow-lg transition flex items-center gap-3">
            <span class="text-2xl">🔬</span>
            <span>Efectos psicológicos del ejercicio en naturaleza (PubMed)</span>
          </a>
          <a href="https://pubmed.ncbi.nlm.nih.gov/27668460/" target="_blank" rel="noopener noreferrer" class="bg-white p-4 rounded-xl shadow hover:shadow-lg transition flex items-center gap-3">
            <span class="text-2xl">🌳</span>
            <span>Bienestar y contacto con espacios verdes (PubMed)</span>
          </a>
          <a href="https://journals.plos.org/plosone/article?id=10.1371/journal.pone.0051474" target="_blank" rel="noopener noreferrer" class="bg-white p-4 rounded-xl shadow hover:shadow-lg transition flex items-center gap-3 sm:col-span-2">
            <span class="text-2xl">📊</span>
            <span>PLOS ONE: Naturaleza y salud mental - Revisión sistemática</span>
          </a>
        </div>
      </div>
    </section>

    <!-- Redes sociales + contacto (con tus datos reales y Formspree funcional) -->
    <section id="contacto" class="bg-white/80 py-16 px-4">
      <div class="max-w-5xl mx-auto">
        <div class="text-center mb-10">
          <h3 class="text-3xl font-bold">🌐 Conéctate conmigo</h3>
          <p class="text-gray-600 mt-1">Sígueme en mis aventuras o escríbeme para compartir rutas</p>
        </div>
        <div class="grid md:grid-cols-2 gap-8">
          <!-- Redes sociales reales -->
          <div class="flex flex-col items-center md:items-start gap-5">
            <div class="flex gap-6 text-3xl">
              <a href="https://youtube.com/@LucasEscobarSepúlveda08" target="_blank" class="text-green-700 hover:text-green-500 transition" aria-label="YouTube"><i class="fab fa-youtube"></i></a>
              <a href="https://instagram.com/lucass.hybrid" target="_blank" class="text-green-700 hover:text-green-500 transition" aria-label="Instagram"><i class="fab fa-instagram"></i></a>
              <a href="https://wa.me/573008633690" target="_blank" class="text-green-700 hover:text-green-500 transition" aria-label="WhatsApp"><i class="fab fa-whatsapp"></i></a>
            </div>
            <p class="text-gray-500 text-sm">@LucasEscobarSepúlveda08 · lucass.hybrid · +57 3008633690</p>
          </div>
          <!-- Formulario de contacto con Formspree real -->
          <form id="contactForm" action="https://formspree.io/f/xgobvnno" method="POST" class="space-y-3 bg-[#f7f3ec] p-5 rounded-2xl shadow">
            <input type="text" name="nombre" placeholder="Nombre" required class="w-full p-2 rounded-lg border border-gray-300 focus:ring-green-500">
            <input type="email" name="_replyto" placeholder="Correo electrónico" required class="w-full p-2 rounded-lg border border-gray-300">
            <textarea name="mensaje" rows="3" placeholder="Cuéntame tu experiencia o duda..." class="w-full p-2 rounded-lg border border-gray-300"></textarea>
            <input type="hidden" name="_subject" value="Nuevo mensaje desde la web de senderismo">
            <button type="submit" class="bg-green-700 hover:bg-green-800 text-white px-5 py-2 rounded-full w-full font-semibold">Enviar mensaje ✉️</button>
            <p id="formFeedback" class="text-xs text-green-600 text-center"></p>
          </form>
        </div>
      </div>
    </section>
  </main>

  <footer class="bg-gray-800 text-gray-300 py-6 text-center text-sm">
    <p>🌱 Inspirado en las montañas de Colombia. Cada paso cuenta — 2026</p>
  </footer>

  <!-- Script de interactividad (scroll suave, gamificación, menú, formulario) -->
  <script>
    (function () {
      // Smooth scroll
      document.querySelectorAll('a[href^="#"]').forEach(anchor => {
        anchor.addEventListener('click', function(e) {
          const targetId = this.getAttribute('href');
          if (targetId === "#") return;
          const target = document.querySelector(targetId);
          if (target) {
            e.preventDefault();
            target.scrollIntoView({ behavior: 'smooth', block: 'start' });
          }
        });
      });

      // Menú hamburguesa
      const menuBtn = document.getElementById('menu-btn');
      const mobileMenu = document.getElementById('mobile-menu');
      if (menuBtn && mobileMenu) {
        menuBtn.addEventListener('click', () => mobileMenu.classList.toggle('hidden'));
        mobileMenu.querySelectorAll('a').forEach(link => {
          link.addEventListener('click', () => mobileMenu.classList.add('hidden'));
        });
      }

      // Gamificación 1: km usuario
      let userKm = 0;
      const sumarBtn = document.getElementById('sumarKmBtn');
      const kmUserSpan = document.getElementById('kmUser');
      const logroMsg = document.getElementById('logroMsg');
      if (sumarBtn) {
        sumarBtn.addEventListener('click', () => {
          userKm += 5;
          kmUserSpan.innerText = userKm;
          if (userKm >= 50 && userKm < 100) logroMsg.innerText = "🎉 ¡Logro: Caminante ocasional! +50 km";
          else if (userKm >= 100) logroMsg.innerText = "🏆 ¡Explorador leyenda! +100 km virtuales. ¡Súmate a la travesía real!";
          else logroMsg.innerText = "¡Sigue sumando! Cada 50 km obtienes medalla virtual.";
        });
      }

      // Gamificación 2: subir montaña
      let altura = 0;
      let medallasDesbloqueadas = 0;
      const subirBtn = document.getElementById('subirBtn');
      const resetBtn = document.getElementById('resetBtn');
      const alturaDisplay = document.getElementById('alturaDisplay');
      const insigniaMsg = document.getElementById('insigniaMsg');
      const medallasDiv = document.getElementById('medallas');

      function actualizarMedallas() {
        if (!medallasDiv) return;
        medallasDiv.innerHTML = '';
        for (let i = 0; i < medallasDesbloqueadas; i++) {
          const medalla = document.createElement('span');
          medalla.textContent = '🏅';
          medalla.title = `Medalla ${i+1}`;
          medalla.classList.add('text-2xl');
          medallasDiv.appendChild(medalla);
        }
      }

      function revisarLogros(alturaNueva) {
        let nuevoLogro = false;
        if (alturaNueva >= 100 && medallasDesbloqueadas < 1) { medallasDesbloqueadas = 1; nuevoLogro = true; insigniaMsg.innerText = "✨ ¡Medalla de Bronce! Llegaste a 100 m"; }
        if (alturaNueva >= 300 && medallasDesbloqueadas < 2) { medallasDesbloqueadas = 2; nuevoLogro = true; insigniaMsg.innerText = "🥈 ¡Medalla de Plata! 300 metros de perseverancia"; }
        if (alturaNueva >= 600 && medallasDesbloqueadas < 3) { medallasDesbloqueadas = 3; nuevoLogro = true; insigniaMsg.innerText = "🥇 ¡Medalla de Oro! Eres una cumbre"; }
        if (nuevoLogro) actualizarMedallas();
        else if (alturaNueva % 50 === 0 && alturaNueva !== altura && alturaNueva < 600) insigniaMsg.innerText = "📈 Vas bien, sigue subiendo...";
        else if (!nuevoLogro && alturaNueva < 600) insigniaMsg.innerText = "";
      }

      if (subirBtn) {
        subirBtn.addEventListener('click', () => {
          altura += 10;
          alturaDisplay.innerText = altura + " m";
          revisarLogros(altura);
          if (altura >= 1000) {
            alturaDisplay.innerText = "🏁 ¡Cumbre!";
            subirBtn.disabled = true;
          }
        });
        resetBtn.addEventListener('click', () => {
          altura = 0;
          medallasDesbloqueadas = 0;
          alturaDisplay.innerText = "0 m";
          insigniaMsg.innerText = "";
          actualizarMedallas();
          subirBtn.disabled = false;
        });
        actualizarMedallas();
      }

      // Formulario con Formspree (feedback visual de envío)
      const contactForm = document.getElementById('contactForm');
      const formFeedback = document.getElementById('formFeedback');
      if (contactForm) {
        contactForm.addEventListener('submit', function(e) {
          formFeedback.innerText = "✅ Enviando... serás redirigido a Formspree.";
          setTimeout(() => {
            formFeedback.innerText = "";
          }, 3000);
        });
      }
    })();
  </script>
</body>
</html>
