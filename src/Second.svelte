<script>
    let name = 'World';
    let toggle = false;

    let fruits = ['Apple', 'Banana', 'Cherry', 'Orange', 'Mango'];

    function deleteFruit() {
        fruits = fruits.slice(1)
    }
</script>

<main>
    {#if toggle}
        <h1>Hello {name}</h1>
    {:else}
        <h1>No name</h1>
    {/if}
    <button on:click={() => {toggle = !toggle}}>
        Toggle
    </button>

    <ul>
        {#each fruits as fruit}
            <li>{fruit}</li>
        {/each}
    </ul>
    <button on:click={deleteFruit}>
        Eat it
    </button>
</main>

<style>
	main {
		padding: 30px;
	}
</style>