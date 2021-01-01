<script>
	import Header from './components/Header.svelte';

	export let name;
	let count = 0;

	const increment = () => {
		count += 1
	}
	
	$: doubled = count * 2
	$: console.log(`Count is ${count}`)
</script>

<main>
	<Header />

	<h2>Hello {name}!</h2>
	<h2>{count} doubled is {doubled}</h2>
	<button on:click={increment}>Increment</button>

</main>

<style>
	main {
		text-align: center;
		padding: 1em;
		max-width: 240px;
		margin: 0 auto;
	}

	h2 {
		color: #ff3e00;
		text-transform: uppercase;
		font-size: 2em;
		font-weight: 100;
	}

	@media (min-width: 640px) {
		main {
			max-width: none;
		}
	}
</style>