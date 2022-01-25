<script>
  let name = 'World';
  let isRed = false;

  function enter() {
    name = 'Enter';
  }

  function leave() {
    name = 'Leave';
  }

  let text = 'Text';
</script>

<h1>Hello {name}</h1>
<div
  class="box"
  style="background-color: {isRed ? 'red' : 'orange'}"
  on:click={() => {
    isRed = !isRed;
  }}
  on:mouseenter={enter}
  on:mouseleave={leave}
>
  Click Box
</div>

<h1>{text}</h1>
<input type="text" bind:value={text} />
<button
  on:click={() => {
    text = 'Button';
  }}>Click</button
>

<style>
  .box {
    width: 250px;
    height: 150px;
    margin: 0 0 30px;
  }
</style>
