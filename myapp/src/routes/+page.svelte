<script>
    let count = 0;
    // Reactivity! Not just for variables, but for statements as well
    // Reactivity = do something whenever something changes
    $: doubled = count * 2;

    function incrementCount() {
        // event handler code goes here
        count += 1;
    }

    $: if (count >= 10) {
        console.log('the count is ' + count);
        alert('I SAID THE COUNT IS ' + count);
    }

    // Svelte's reactivity is triggered by assignments. Methods that mutate arrays or objects will not trigger updates by themselves.
    // assign numbers to itself to tell the compiler it has changed

    let numbers = [1, 2, 3, 4];

	function addNumber() {
		numbers.push(numbers.length + 1);
		numbers = numbers;
	}

	$: sum = numbers.reduce((t, n) => t + n, 0);
</script>

<h1>Welcome to SvelteKit</h1>
<p>Visit <a href="https://kit.svelte.dev">kit.svelte.dev</a> to read the documentation</p>

<button on:click="{incrementCount}">Clicked {count} {count === 1 ? 'time' : 'times'}</button>

<p>{count} doubled is {doubled}</p>

<p>{numbers.join(' + ')} = {sum}</p>

<button on:click={addNumber}>
	Add a number
</button>
