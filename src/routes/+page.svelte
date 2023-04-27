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

<style lang="scss">
	@import url('https://fonts.googleapis.com/css2?family=Pathway+Extreme:wght@500&display=swap');
	* {
		-webkit-font-smoothing: antialiased;
		-moz-osx-font-smoothing: grayscale;
		text-rendering: optimizeLegibility;
	}
	:global(body) {
		--light: #f4ecec;
		--dark: #131313;
		--mid: #806d6d;
		--bg: var(--light);
		--text: var(--dark);
		--border: var(--mid);
		--font: 'Pathway Extreme', sans-serif;
		--radius: 0.25rem;
		@media (prefers-color-scheme: dark) {
			--bg: var(--dark);
			--text: var(--light);
		}
		font-family: var(--font);
		color: var(--text);
		background: var(--bg);
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
		border: 1px solid var(--border);
		border-radius: var(--radius);
		min-height: 6rem;
		padding: 0.5rem;
	}

	li {
		flex: 50%;
	}
	textarea {
		font-family: var(--font);
		font-size: 1rem;
		border: 1px solid var(--border);
		border-radius: var(--radius);
		background: var(--bg);
		width: calc(100% - 1rem);
		min-height: 6rem;
		padding: 0.5rem;
		&:focus {
			outline-color: var(--mid);
		}
		&::placeholder {
			color: var(--border);
			transition: all 0.3s;
		}
		&:focus::placeholder {
			color: transparent;
		}
	}
</style>
