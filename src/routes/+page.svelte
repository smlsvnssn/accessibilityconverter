<script>
	const convert = t =>
		t.replace(/([\wåäöÅÄÖøØ+]+)/g, w =>
			w.length > 3 ? w.at(0) + (w.length - 2) + w.at(-1) : w,
		)

	let text = ''

	$: translatedText = convert(text)
</script>

<main>
	<h1>Universal accessibility converter international™</h1>
	<ul>
		<li class="in">
			<h2>Input:</h2>
			<textarea
				placeholder="Write text that you want to accessibilityize here"
				bind:value={text}
			/>
		</li>

		<li class="out">
			<h2>Output:</h2>
			<p>{translatedText}</p>
		</li>
	</ul>
</main>

<style>
	:global(body) {
		font-family: system-ui, -apple-system, BlinkMacSystemFont, 'Segoe UI',
			Roboto, Oxygen, Ubuntu, Cantarell, 'Open Sans', 'Helvetica Neue',
			sans-serif;
		display: grid;
		justify-items: center;
		align-items: center;
		height: 100dvh;
		margin: 1rem;
	}
	h1 {
	}
	h2 {
	}
	ul {
		list-style: none;
		display: flex;
		gap: 1rem;
		padding: 0;
		margin: auto;
	}

	.out p {
		border: 1px solid #ddd;
		min-height: 6rem;
		padding: 0.5rem;
	}

	li {
		flex: 50%;
	}
	textarea {
		font-family: system-ui, -apple-system, BlinkMacSystemFont, 'Segoe UI',
			Roboto, Oxygen, Ubuntu, Cantarell, 'Open Sans', 'Helvetica Neue',
			sans-serif;
		font-size: 1rem;
		border: 1px solid #ddd;
		width: calc(100% - 1rem);
		min-height: 6rem;
		padding: 0.5rem;
	}
</style>
