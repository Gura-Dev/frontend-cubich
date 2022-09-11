<script>
	import Header from '$lib/header/Header.svelte';
	import Footer from '$lib/footer/Footer.svelte';
	import '../app.scss';
</script>

<Header/>

<main>
	<slot />
</main>

<Footer />

<style>
	main {
		font-family: Montserrat;
		flex: 1;
		display: flex;
		flex-direction: column;
		align-items: center;
		justify-content: flex-start;
		width: 100%;
		margin: 0px;
		box-sizing: border-box;
	}
</style>
