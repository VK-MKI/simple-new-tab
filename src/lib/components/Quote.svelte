<script lang="ts">
	const quote = fetch('/quotes.json')
		.then(res => res.json())
		.then(data => {
			const randomIndex = Math.floor(Math.random() * data.quotes.length);

			return data.quotes[randomIndex];
		});
</script>

<div>
	{#await quote then quote}
		<blockquote>
			{quote.quote}
		</blockquote>

		<cite>
			— {quote.author}
		</cite>
	{/await}
</div>
