<script>
  let name = 'Criszel';
  
  // Function to create sparkles dynamically
  function createSparkle() {
    if (typeof window !== 'undefined') {
      const sparkle = document.createElement('div');
      sparkle.classList.add('sparkle');
      document.body.appendChild(sparkle);

      const size = Math.random() * 10 + 10; // Random size
      sparkle.style.width = `${size}px`;
      sparkle.style.height = `${size}px`;
      sparkle.style.left = `${Math.random() * window.innerWidth}px`;
      sparkle.style.top = `${Math.random() * window.innerHeight}px`;

      sparkle.style.animationDuration = `${Math.random() * 2 + 2}s`;

      sparkle.addEventListener('animationend', () => {
        sparkle.remove();
      });
    }
  }

  setInterval(createSparkle, 300); // Add sparkles periodically
</script>

<style>
  :global(body) {
    font-family: 'Poppins', sans-serif;
    background-color: #FFE4F4;
    margin: 0;
    padding: 0;
    overflow: hidden;
  }

  .birthday-container {
    position: relative;
    text-align: center;
    padding: 50px;
    margin: 100px auto;
    max-width: 800px;
    background: linear-gradient(145deg, #FFD6F6, #FFFAF1);
    border-radius: 25px;
    box-shadow: 0 10px 20px rgba(0, 0, 0, 0.1);
  }

  .birthday-message {
    font-size: 2.5rem;
    color: #FF5DA2;
    font-weight: bold;
  }

  .birthday-message span {
    color: #FF4081;
  }

  .balloons {
    font-size: 3rem;
    position: absolute;
    bottom: 0;
    animation: floatUp 5s linear infinite;
    cursor: pointer;
  }

  .balloons:hover {
    animation-play-state: paused;
  }

  @keyframes floatUp {
    0% {
      transform: translateY(0);
    }
    100% {
      transform: translateY(-100vh);
    }
  }

  /* Floating Balloons */
  .balloon-left {
    font-size: 3rem;
    position: absolute;
    bottom: 0;
    left: 5%;
    animation: floatLeft 6s linear infinite;
    cursor: pointer;
  }

  @keyframes floatLeft {
    0% {
      transform: translateY(0) translateX(0);
    }
    100% {
      transform: translateY(-100vh) translateX(-100vw);
    }
  }

  .balloon-right {
    font-size: 3rem;
    position: absolute;
    bottom: 0;
    right: 5%;
    animation: floatRight 6s linear infinite;
    cursor: pointer;
  }

  @keyframes floatRight {
    0% {
      transform: translateY(0) translateX(0);
    }
    100% {
      transform: translateY(-100vh) translateX(100vw);
    }
  }

  .balloon-diagonal {
    font-size: 3rem;
    position: absolute;
    bottom: 0;
    left: 50%;
    animation: floatDiagonal 7s linear infinite;
    cursor: pointer;
  }

  @keyframes floatDiagonal {
    0% {
      transform: translateY(0) translateX(0);
    }
    100% {
      transform: translateY(-100vh) translateX(100vw);
    }
  }

  /* Centered Balloons */
  .balloon-center-1 {
    font-size: 3rem;
    position: absolute;
    bottom: 10%;
    left: 30%;
    animation: floatCenter 6s linear infinite;
    cursor: pointer;
  }

  .balloon-center-2 {
    font-size: 3rem;
    position: absolute;
    bottom: 20%;
    left: 50%;
    animation: floatCenter 6s linear infinite;
    cursor: pointer;
  }

  .balloon-center-3 {
    font-size: 3rem;
    position: absolute;
    bottom: 30%;
    left: 70%;
    animation: floatCenter 6s linear infinite;
    cursor: pointer;
  }

  @keyframes floatCenter {
    0% {
      transform: translateY(0);
    }
    100% {
      transform: translateY(-100vh);
    }
  }

  /* Sparkles */
  :global(.sparkle) {
    position: absolute;
    background: radial-gradient(circle, rgba(255, 223, 244, 0.8), transparent);
    border-radius: 50%;
    animation: sparkleMove 4s linear infinite;
    pointer-events: none;
  }

  @keyframes sparkleMove {
    0% {
      transform: translateY(0) scale(1);
      opacity: 1;
    }
    100% {
      transform: translateY(-100vh) scale(0.5);
      opacity: 0;
    }
  }
</style>

<main>
  <div class="birthday-container">
    <!-- Birthday Message -->
    <div class="birthday-message">
      🎉 Happy Birthday, <span>{name}</span>! 🎂
    </div>

    <!-- Balloons -->
    <div class="balloons">🎈🎈🎈</div>
    <div class="balloon-left">🎈</div>
    <div class="balloon-right">🎈</div>
    <div class="balloon-diagonal">🎈</div>

    <!-- Centered Balloons -->
    <div class="balloon-center-1">🎈</div>
    <div class="balloon-center-2">🎈</div>
    <div class="balloon-center-3">🎈</div>

    <!-- Additional Random Balloons -->
    {#each Array(16) as _, i}
      <div class="balloon-{i % 3 === 0 ? 'left' : i % 3 === 1 ? 'right' : 'diagonal'}">
        🎈
      </div>
    {/each}
  </div>
</main>
