<script>
  export let name = "world";
  let count = 0;
  // reactive declaration. Like a computed property in Vue
  $: doubled = count * 2;

  // reactive statements
  $: console.log("count is", count);

  $: {
    console.log("nested")
    console.log("nested2")
  }

  $: if (count > 10) {
    count = 0;
  }

  function increment() {
    count += 1;
  }

  const clear = () => {
    count = 0;
  };
  
</script>

<button on:click={increment}>
  Clicked {count} {count === 1 ? 'time' : 'times'}
</button>
<button on:click={clear}>Clear Count</button>

<div>
  <p>
    {count} doubled is {doubled}
  </p>
</div>

<h1>{name}</h1>