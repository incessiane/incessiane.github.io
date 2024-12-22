<script lang="ts">
	import { onMount } from 'svelte';
	import { page } from '$app/stores'; // Importing the 'page' store to get the current route
  
	let showButton = true;
  
	// Check if the current page is "happyB" on mount
	onMount(() => {
	  // Check if the current route is the "happyB" page
	  if ($page.url.pathname === '/happyB') {
		showButton = false;
	  }
	});
  </script>
  
  <main>
	<!-- Render children components -->
	<slot />
	
	<!-- Redirect Button (conditionally shown) -->
	{#if showButton}
	  <div style="text-align: center; margin-top: 30px;">
		<button on:click={() => window.location.href = './happyB'} style="background-color: #FF80AB; color: white; padding: 12px 24px; border: none; border-radius: 8px; font-size: 1.1rem; cursor: pointer; box-shadow: 0 4px 6px rgba(0, 0, 0, 0.1); transition: background-color 0.3s ease, transform 0.3s ease, box-shadow 0.3s ease;">
		  🎉 Go to Criszel's Birthday Page 🎂
		</button>
	  </div>
	{/if}
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
	  font-size: 4vw;
	  padding: 2vw 4vw;
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
	  padding: 5vw;
	}
  
	/* Media Queries for additional responsiveness */
	@media (max-width: 600px) {
	  button {
		font-size: 5vw;
		padding: 3vw 6vw;
	  }
	}
  </style>
  