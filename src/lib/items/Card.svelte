<script>
	import { Card, Button, Toggle } from 'flowbite-svelte';
	let hCard = false;
</script>

<div class="relative flex-auto justify-items-center grid">
	<Card img="flipside_logo.png" target="_blank" href="https://flipsidecrypto.xyz/satsih/base-testnet-activity--V4Jz-" horizontal reverse={hCard}>
		<h5 class="mb-2 text-2xl font-bold tracking-tight text-gray-900 dark:text-white">
			Flipside Dashboard
		</h5>
		<p class="mb-3 font-normal text-gray-700 dark:text-gray-400 leading-tight">
			Link to accompanying Base Testnet Activity flipside dashboard.
		</p>
	</Card>
</div>
