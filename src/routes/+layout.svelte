<script>
	import Navbar from '../components/Navbar.svelte';
</script>

<Navbar />
<slot />

<style>
	@import url('https://fonts.googleapis.com/css2?family=Poppins:wght@500&display=swap');
	:global(*) {
		font-family: 'Poppins', sans-serif;
		margin: 0;
		padding: 0;
		box-sizing: border-box;
		text-decoration: none;
		color: var(--light);
	}

	:global(:root) {
		--primary: #2a9d8f;
		--secondary: #f4a261;
		--dark: #264653;
		--light: #ebebeb;
	}

	:global(body) {
		background-color: #555555;
	}
</style>
