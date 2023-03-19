<script>
    // Svelte's reactivity is triggered by assignments. Methods that mutate arrays or objects will not trigger updates by themselves.
    // assign numbers to itself to tell the compiler it has changed

    // A simple rule of thumb: the updated variable must directly appear on the left hand side of the assignment.
    let numbers = [1, 2, 3, 4];

    function addNumber() {
        numbers = [...numbers, numbers.length + 1];
    }

    $: sum = numbers.reduce((t, n) => t + n, 0);
</script>

<p>{numbers.join(' + ')} = {sum}</p>

<button on:click="{addNumber}">Add a number</button>
