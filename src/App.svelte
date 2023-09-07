<script>
	import Sidebar from './components/Sidebar.svelte'
	import Sideba from './components/Sideba.svelte';
	import Header from './components/Header.svelte'
	import Footer from './components/Footer.svelte';
	import Filters from './components/Filters.svelte';
	import Static from './components/Static.svelte';

	let open = true

</script>

<main>
	<Header/>
	<Sidebar bind:open/>
	<Static/>
	<Filters/>
	<Footer/>
</main>

<svelte:head>
	<link href="https://unpkg.com/tailwindcss@^1.0/dist/tailwind.min.css" rel="stylesheet"/>
</svelte:head>

<style>
	:global(body) {
		padding: 0;
		background-color: whitesmoke;
		
			}
</style>