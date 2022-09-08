<svelte:head>
	<title>Кубыч</title>
</svelte:head>

<script>
	import PlayButton from '$lib/ui/Play.svelte';
</script>


<div class="home">
	<div class="content">
		<h1>Ламповый <br/> Майнкрафт <br/> Сервер</h1>
		<p>Майнкрафт проект для друзей и их друзей <br/>
			Ванильное выживание, где главное - сиськи <br/>
			Но гриферить всё равно нельзя</p>
		<PlayButton/>
	</div>
	<img src="wizard.png" alt="" class="wizard">
</div>

<style>
	.home {
		display: flex;
		flex-direction: row;
		justify-content: center;
		align-items: center;
		height: 100%;
		width: 100%;
		padding-top: 50px;
	}

	.wizard {
		margin-left: auto;
	}

	.content {
		padding: 0px 20px 0px 384px;
		display: flex;
		flex-direction: column;
		justify-content: center;
		align-items: left;
	}

	.content h1 {
		text-align: left;
		color: white;
		font-size: 3.5rem;
		font-weight: 600;
		margin: 0;
		padding: 0;
	}

	.content p {
		text-align: left;
		color: white;
		font-size: 1.3rem;
		font-weight: 250;
	}

</style>