<script>
	const convert = t =>
		t.replace(/([\wåäöÅÄÖøØ+]+)/g, w =>
			w.length > 3 ? w.at(0) + (w.length - 2) + w.at(-1) : w,
		)

	let text = 'Write here'

	$: translatedText = convert(text)
</script>

<main>
	<h1>Universal accessibility converter international™</h1>
	<ul>
		<li class="in">
			<h2>Input:</h2>
			<textarea name="" id="" cols="30" rows="10" bind:value={text} />
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
	}
	h1 {
	}
	h2 {
	}
	ul {
		list-style: none;
		display: flex;
		gap: 2rem;
		margin: auto;
	}
	textarea {
		font-family: system-ui, -apple-system, BlinkMacSystemFont, 'Segoe UI',
			Roboto, Oxygen, Ubuntu, Cantarell, 'Open Sans', 'Helvetica Neue',
			sans-serif;
		font-size: 1rem;
	}
</style>
