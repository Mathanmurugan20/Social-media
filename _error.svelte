<script>
  export let status;
  export let error;

  const dev = process.env.NODE_ENV === "development";
</script>

<svelte:head>
  <title>{status}</title>
</svelte:head>

<h1>{status}</h1>
<h2>{error.message}</h2>

{#if dev && error.stack}
  <pre>{error.stack}</pre>
{/if}

<style>
  h1 {
    color: #fff;
    margin-top: 130px;
    font-size: 2rem;
    text-align: center;
    letter-spacing: 4px;
    font-family: monospace;
  }

  h2 {
    color: #fff;
    margin-top: 14px;
    font-size: 1.5rem;
    text-align: center;
    letter-spacing: 2px;
  }

  pre {
    color: #fff;
    margin-top: 130px;
    text-align: center;
  }
</style>
