<script>
  let name = 'World';
  let age = 50;

  function assign() {
    name = 'Developer';
    age = 30;
  }
</script>

<main>
  <h1>Hello {name}!</h1>
  <h2 class={age < 40 ? 'active' : ''}>{age}</h2>
  <input type="text" bind:value={name} />
  <button on:click={assign}>Assign</button>
</main>

<style>
  main {
    text-align: center;
    padding: 10px;
    max-width: 500px;
    margin: 0 auto;
  }

  .active {
    color: blue;
  }

  @media (min-width: 640px) {
    main {
      max-width: none;
    }
  }
</style>
