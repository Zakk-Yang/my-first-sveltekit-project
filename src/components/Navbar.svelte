<script>
	let isMenuOpen = false;
	function toggleMenue() {
		isMenuOpen = !isMenuOpen;
	}

	let current = 0;
</script>

<div class="navbar">
	<a href="/" class="logo"><h1>Logo</h1> </a>
	<nav class:open={isMenuOpen}>
		<ul>
			<li on:click={() => (isMenuOpen = false)}>
				<a class:current={current === 0} on:click={() => (current = 0)} href="/">Home</a>
			</li>
			<li on:click={() => (isMenuOpen = false)}>
				<a class:current={current === 1} on:click={() => (current = 1)} href="/">Features</a>
			</li>
			<li on:click={() => (isMenuOpen = false)}>
				<a class:current={current === 2} on:click={() => (current = 2)} href="/">Pricing</a>
			</li>
			<li on:click={() => (isMenuOpen = false)}>
				<a class:current={current === 3} on:click={() => (current = 3)} href="/">Blog</a>
			</li>
			<li on:click={() => (isMenuOpen = false)} class="sign-in-btn"><a href="/">Sign In</a></li>
		</ul>
	</nav>
	<button class="burger" on:click={toggleMenue}>
		<div class="bar-1" />
		<div class="bar-2" />
		<div class="bar-3" />
	</button>
</div>

<style>
	.navbar {
		background-color: var(--dark);
		display: flex;
		justify-content: space-between;
		align-items: center;
		position: relative;
		height: 4rem;
	}

	.logo {
		margin-left: 6vw;
	}
	/* when in desktop and when menu is open */
	@media only screen and (max-width: 767px) {
		nav {
			display: none;
		}
		nav.open {
			display: block;
			position: absolute;
			top: 100%;
			left: 0;
			background-color: var(--dark);
			width: 100%;
		}
	}

	/* nav {
		display: none;
	}
	nav.open {
		display: block;
		position: absolute;
		top: 100%;
		left: 0;
		background-color: var(--dark);
		width: 100%;
	} */

	ul {
		display: flex;
		flex-direction: column;
		justify-content: space-between;
		align-items: center;
		gap: 5vh;
		margin-top: 2vh;
		margin-bottom: 4vh;
		list-style: none;
		font: size 1.1rem;
	}

	.current {
		position: relative;
	}

	.current::after {
		content: '';
		position: absolute;
		bottom: 0;
		left: 0;
		width: 100%;
		height: 2px;
		background-color: var(--secondary);
	}

	.sign-in-btn {
		background-color: var(--primary);
		padding: 0.4rem 1rem;
		border-radius: 10px;
		font-weight: 500;
	}
	.burger {
		height: 28px;
		aspect-ratio: 1;
		border: 2px solid var(--light);
		background-color: transparent;
		border-radius: 5px;
		margin-right: 3vw;
		display: flex;
		justify-content: center;
		align-items: center;
	}

	.burger > div {
		height: 2px;
		width: 14px;
		background-color: var(--light);
		position: absolute;
	}

	.bar-1 {
		transform: translateY(-5px);
	}

	.bar-3 {
		transform: translateY(5px);
	}

	@media only screen and (min-width: 768px) {
		.logo {
			margin-left: 12vm;
		}
		.burger {
			display: none;
		}

		nav {
			display: block;
			position: relative;
		}

		ul {
			margin: 0;
			flex-direction: row;
			gap: 2vw;
		}

		.sign-in-btn {
			margin-inline: 2vw;
		}
	}
</style>
