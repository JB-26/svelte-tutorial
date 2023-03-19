<script>
    import NumberArray from "./numberArray.svelte";
    import Nested from "./nested.svelte";
    import Info from "./info.svelte";
	import Logged from "./logged.svelte";
	import ElseIf from "./elseIf.svelte";

    const pkg = {
        name: 'svelte',
        version: 3,
        speed: 'blazing',
        website: 'https://svelte.dev'
    }

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
</script>

<h1>Welcome to SvelteKit</h1>
<p>Visit <a href="https://kit.svelte.dev">kit.svelte.dev</a> to read the documentation</p>

<button on:click="{incrementCount}">Clicked {count} {count === 1 ? 'time' : 'times'}</button>

<p>{count} doubled is {doubled}</p>


<NumberArray></NumberArray>

<Nested answer={'42'}/>

<Nested />

<Info name = {pkg.name} version = {pkg.version} speed = {pkg.speed} website = {pkg.website} />

<Info {...pkg}/>

<Logged></Logged>

<ElseIf></ElseIf>