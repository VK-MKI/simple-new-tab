<script lang="ts">
	const quote = fetch('https://dummyjson.com/quotes/random').then(res =>
		res.json()
	);
</script>

<div>
	{#await quote then quote}
		<blockquote>
			{quote.quote}
		</blockquote>
		<cite>
			{quote.author}
		</cite>
	{/await}
</div>
