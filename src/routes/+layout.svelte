<script lang="ts">
	import '../app.css'; // Import your styles
	let { children } = $props(); // Render children components
  </script>
  
  <main>
	<!-- Render children components -->
	{@render children()}
  
	<!-- Redirect Button -->
	<div style="text-align: center; margin-top: 30px;">
	  <!-- svelte-ignore event_directive_deprecated -->
	  <button on:click={() => window.location.href = './happyB'} style="background-color: #FF80AB; color: white; padding: 12px 24px; border: none; border-radius: 8px; font-size: 1.1rem; cursor: pointer; box-shadow: 0 4px 6px rgba(0, 0, 0, 0.1); transition: background-color 0.3s ease, transform 0.3s ease, box-shadow 0.3s ease;">
		🎉 Go to Criszel's Birthday Page 🎂
	  </button>
	</div>
  </main>
  
  <style>
	:global(body) {
	  font-family: 'Poppins', sans-serif;
	  background: linear-gradient(135deg, #FFDEE9, #B5E2F5); /* Soft pastel gradient */
	  background-size: 400% 400%;
	  animation: gradientBG 12s ease infinite;
	  margin: 0;
	  padding: 0;
	  height: 100vh;
	}
  
	@keyframes gradientBG {
	  0% {
		background-position: 0% 50%;
	  }
	  50% {
		background-position: 100% 50%;
	  }
	  100% {
		background-position: 0% 50%;
	  }
	}
  
	button {
	  transition: background-color 0.3s ease, transform 0.3s ease, box-shadow 0.3s ease;
	  font-weight: 600;
	}
  
	button:hover {
	  background-color: #F06292; /* A gentle, soft pink */
	  transform: scale(1.05); /* Slightly enlarges button on hover */
	  box-shadow: 0 8px 12px rgba(0, 0, 0, 0.2); /* Subtle shadow effect on hover */
	}
  
	/* Centering content and ensuring it fits well on screens */
	main {
	  display: flex;
	  justify-content: center;
	  align-items: center;
	  flex-direction: column;
	  height: 100vh;
	  text-align: center;
	}
  
	
  </style>
  