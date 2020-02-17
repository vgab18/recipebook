<script>
  import Recipe from "./Recipe.svelte";
  import Spinner from "./Spinner.svelte";
  let fetching = false;
</script>

<style>
  main {
    padding: 1em;
    max-width: 240px;
    margin: 0 auto;
    background-color: #071a52;
    color: #a7ff83;
    height: 100%;
  }

  .recipes-container {
    display: flex;
    margin-top: 50px;
  }

  .search-container {
    text-align: center;
  }

  .search-input {
    width: 30%;
    color: #071a52;
    padding: 10px;
    font-size: 20px;
  }

  .btn-search {
    padding: 10px;
    font-size: 20px;
  }

  .spinner-container {
    margin-top: 100px;
  }

  @media (min-width: 640px) {
    main {
      max-width: none;
    }
  }
</style>

<main>
  <div class="search-container">
    <h1>Recipebook App</h1>
    <input type="text" placeholder="Search for Recipe" class="search-input" />
    <input type="submit" value={'🔍'} class="btn-search" />
  </div>
  {#if fetching}
    <center>
      <div class="spinner-container">
        <h4>Searching..</h4>
        <br />
        <Spinner />
      </div>
    </center>
  {:else}
    <div class="recipes-container">
      <Recipe />
      <Recipe />
    </div>
  {/if}
</main>
