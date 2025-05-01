<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8" />
  <meta name="viewport" content="width=device-width, initial-scale=1.0" />
  <title>UnlimitedWear</title>
  <script src="https://cdn.jsdelivr.net/npm/gsap@3.12.2/dist/gsap.min.js"></script>
  <link href="https://cdn.jsdelivr.net/npm/tailwindcss@2.2.19/dist/tailwind.min.css" rel="stylesheet">
  <style>
    body {
      margin: 0;
      overflow: hidden;
      background: radial-gradient(ellipse at center, #000428, #004e92);
    }
    .stars {
      width: 100%;
      height: 100%;
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
<body>
  <div class="stars" id="stars"></div>
  <div class="flex items-center justify-center h-screen z-10 relative">
    <h1 id="title" class="text-white text-6xl font-bold opacity-0 scale-75">UnlimitedWear</h1>
  </div>

  <script>
    // Animate title
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
      star.style.top = Math.random() * 100 + "%";
      star.style.left = Math.random() * 100 + "%";
      starsContainer.appendChild(star);
    }
  </script>
</body>
</html>
