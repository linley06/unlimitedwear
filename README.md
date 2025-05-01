<!DOCTYPE html><html lang="en">
<head>
  <meta charset="UTF-8" />
  <meta name="viewport" content="width=device-width, initial-scale=1.0" />
  <title>UnlimitedWear 3D</title>
  <style>
    body, html {
      margin: 0;
      overflow: hidden;
      background: #000;
      font-family: sans-serif;
      color: white;
    }
    #info {
      position: absolute;
      top: 20px;
      left: 20px;
      z-index: 1;
      background: rgba(0,0,0,0.5);
      padding: 10px 20px;
      border-radius: 10px;
    }
    canvas {
      display: block;
    }
  </style>
</head>
<body>
  <div id="info">
    <h1>UnlimitedWear</h1>
    <p>Scroll, drag, and explore your 3D space.</p>
  </div>
  <script src="https://cdn.jsdelivr.net/npm/three@0.150.1/build/three.min.js"></script>
  <script src="https://cdn.jsdelivr.net/npm/three@0.150.1/examples/js/controls/OrbitControls.js"></script>
  <script>
    const scene = new THREE.Scene();
    scene.background = new THREE.Color(0x003366); // Deep blue backgroundconst camera = new THREE.PerspectiveCamera(
  75,
  window.innerWidth / window.innerHeight,
  0.1,
  1000
);
camera.position.z = 5;

const renderer = new THREE.WebGLRenderer();
renderer.setSize(window.innerWidth, window.innerHeight);
document.body.appendChild(renderer.domElement);

const controls = new THREE.OrbitControls(camera, renderer.domElement);

// Create stars
function createStar() {
  const geometry = new THREE.SphereGeometry(0.01, 12, 12);
  const material = new THREE.MeshBasicMaterial({ color: 0xffffff });
  const star = new THREE.Mesh(geometry, material);
  star.position.set(
    (Math.random() - 0.5) * 50,
    (Math.random() - 0.5) * 50,
    (Math.random() - 0.5) * 50
  );
  scene.add(star);
}

for (let i = 0; i < 300; i++) {
  createStar();
}

// Main object
const geometry = new THREE.BoxGeometry();
const material = new THREE.MeshStandardMaterial({ color: 0xffffff });
const cube = new THREE.Mesh(geometry, material);
scene.add(cube);

const light = new THREE.PointLight(0xffffff, 1, 100);
light.position.set(10, 10, 10);
scene.add(light);

function animate() {
  requestAnimationFrame(animate);
  cube.rotation.x += 0.01;
  cube.rotation.y += 0.01;
  controls.update();
  renderer.render(scene, camera);
}
animate();

window.addEventListener("resize", () => {
  camera.aspect = window.innerWidth / window.innerHeight;
  camera.updateProjectionMatrix();
  renderer.setSize(window.innerWidth, window.innerHeight);
});

  </script>
</body>
</html>
