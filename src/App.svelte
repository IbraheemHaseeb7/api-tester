<script>
  // @ts-nocheck

  let response = '';
  let url = ''

  async function checkApi() {
    await fetch(url, {
      method: "GET", headers: {"Content-type": "applicaton/json"}
    }).then((res) => res.json()).then((res) => response = JSON.stringify(res))
  } 
</script>

<main>
  <h1>API Tester</h1>
  <input type="url" placeholder="Enter API endpoint link..." value={url} on:change={(e)=>url=e.target.value} />
  <button on:click={checkApi}>check</button>
  <div>API RESPONDED: <br />{response}</div>
</main>

<style>
  main {
    display: flex;
    justify-content: center;
    align-items: center;
    flex-direction: column;
    gap: 1rem;
    transform: translateY(-2rem);
  }
</style>
