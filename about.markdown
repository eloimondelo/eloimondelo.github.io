---
layout: page
title: About Me
permalink: /about/
---

# About Me

Hello there! I'm Eloi, a passionate Software Developer with a love for animation and teaching. I'm thrilled to welcome you to my personal website, where I share my journey and expertise in the digital realm.

## My Journey

Ever since I wrote my first line of code, I knew I had found my true calling. My journey as a Software Developer has been marked by continuous learning and a drive to create captivating digital experiences. From crafting intricate algorithms to building engaging user interfaces, I thrive on pushing the boundaries of what technology can achieve.

## Animation Enthusiast

Animation has a special place in my heart. The ability to bring objects and characters to life through code is a form of art that never ceases to amaze me. Whether it's creating dynamic visual effects or crafting interactive animations, I'm dedicated to harnessing the power of technology to tell compelling stories through motion.

## Teaching and Sharing Knowledge

Passing on knowledge is a responsibility I take seriously. I find immense joy in teaching others about the wonders of programming and animation. Through workshops, tutorials, and talks, I aim to inspire the next generation of developers and animators. Empowering others to bring their creative visions to life is incredibly rewarding.

## Connect with Me

Let's embark on this exciting journey together! If you're as passionate about software development, animation, or teaching as I am, I'd love to connect with you. Feel free to reach out via [email](mailto:eloimondelo+dev@gmail.com) or connect with me on [LinkedIn](https://www.linkedin.com/in/eloi-mondelo-singla-75a581210) to stay updated on my latest projects and insights.

---

<div style="text-align: center;">
  <script type="module">
    import * as THREE from 'https://cdnjs.cloudflare.com/ajax/libs/three.js/r128/three.module.min.js';

    // Set up scene, camera, and renderer
    const scene = new THREE.Scene();
    const camera = new THREE.PerspectiveCamera(75, window.innerWidth / window.innerHeight, 0.1, 1000);
    const renderer = new THREE.WebGLRenderer();
    renderer.setSize(200, 200); // Set the desired size of the animation
    document.querySelector('#globe-animation').appendChild(renderer.domElement);

    // Create a globe
    const geometry = new THREE.SphereGeometry(1, 32, 32);
    const material = new THREE.MeshBasicMaterial({ color: 0x0077ff, wireframe: true });
    const globe = new THREE.Mesh(geometry, material);
    scene.add(globe);

    // Set camera position
    camera.position.z = 5;

    // Animation loop
    const animate = () => {
      requestAnimationFrame(animate);
      globe.rotation.x += 0.005;
      globe.rotation.y += 0.005;
      renderer.render(scene, camera);
    };

    animate();
  </script>
  <div id="globe-animation"></div>
</div>
