<script>
	// properties, generally shortened to 'props'. In Svelte, we do that with the export keyword.
	// you can specify a default value for a prop
	export let answer = 'a mystery';
</script>

<p>The answer is {answer}</p>