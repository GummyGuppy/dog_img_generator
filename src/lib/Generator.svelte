<script>
	
	let src

	async function getDogs(){
		src = await fetch('https://dog.ceo/api/breeds/image/random')
		.then(res => res.json())
		.then(res => res.message)
		
		
	}
	
</script>

<section>
	
	{#await getDogs}
	...loading
	{:then}
		<img {src}/>
	{/await}
	
</section>
<button on:click={getDogs}>Generate</button>


<style>
	img {
		height: 300px;
		width: 300px;
	}
</style>
