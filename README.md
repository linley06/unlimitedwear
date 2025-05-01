<!DOCTYPE html><html lang="en">
<head>
  <meta charset="UTF-8" />
  <meta name="viewport" content="width=device-width, initial-scale=1.0" />
  <title>UnlimitedWear</title>
  <script src="https://cdn.jsdelivr.net/npm/gsap@3.12.2/dist/gsap.min.js"></script>
  <script src="https://cdn.jsdelivr.net/npm/gsap@3.12.2/dist/ScrollTrigger.min.js"></script>
  <link href="https://cdn.jsdelivr.net/npm/tailwindcss@2.2.19/dist/tailwind.min.css" rel="stylesheet">
  <style>
    body {
      margin: 0;
      overflow-x: hidden;
      background: radial-gradient(ellipse at center, #000428, #004e92);
    }
    .stars {
      width: 100%;
      height: 100%;
      background: transparent;
      position: absolute;
      top: 0;
      left: 0;
      z-index: 0;
    }
    .star {
      position: absolute;
      width: 2px;
      height: 2px;
      background: white;
      border-radius: 50%;
      opacity: 0.8;
      animation: twinkle 2s infinite ease-in-out;
    }
    @keyframes twinkle {
      0%, 100% { opacity: 0.8; }
      50% { opacity: 0.2; }
    }
  </style>
</head>
<body class="relative">
  <div class="stars" id="stars"></div>
  <div class="flex items-center justify-center h-screen z-10 relative">
    <h1 id="title" class="text-white text-5xl md:text-7xl font-bold opacity-0 transform scale-75">UnlimitedWear</h1>
  </div>  <!-- Product Section -->  <section class="relative z-10 bg-black text-white py-16 px-4">
    <div class="max-w-5xl mx-auto text-center">
      <h2 class="text-4xl font-bold mb-8">Featured Product</h2>
      <div class="flex flex-col md:flex-row items-center justify-center gap-8">
        <img src="file-K8gcGcGX3qLHwgk6UnCoJs" alt="Front view" class="w-64 rounded-lg shadow-lg" />
        <img src="file-Hh1X9ikMXNkxFpn8mw552b" alt="Back view" class="w-64 rounded-lg shadow-lg" />
      </div>
      <div class="mt-8">
        <h3 class="text-2xl font-semibold">Made of Money Tee</h3>
        <p class="text-lg">Rs 600</p>
        <button class="mt-4 bg-white text-black px-6 py-2 rounded-lg font-bold hover:bg-gray-200 transition">Buy Now</button>
      </div>
    </div>
  </section>  <script>
    // Animate text
    gsap.to("#title", {
      duration: 2,
      opacity: 1,
      scale: 1,
      rotationY: 360,
      ease: "power4.out"
    });

    // Generate stars
    const starsContainer = document.getElementById("stars");
    for (let i = 0; i < 100; i++) {
      const star = document.createElement("div");
      star.className = "star";
      star.style.top = `${Math.random() * 100}%`;
      star.style.left = `${Math.random() * 100}%`;
      starsContainer.appendChild(star);
    }
  </script></body>
</html>
