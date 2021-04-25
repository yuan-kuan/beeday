<script>
  import 'bulma/css/bulma.css'
  import { fade, fly } from 'svelte/transition';

  let greet = false;
  const greeting = () => {greet = true}
</script>

{ #if greet}
<main in:fade class="hero is-primary">
  <div class="hero-body">
    <h1 class="title">Happy Birthday!</h1>
    <h2 class="subtitle">Dear 爱爱美美 </h2>
  </div>
</main>
{ /if }

<div class="foot">
  <button class="button is-large is-rounded is-warning" on:click={greeting}>
      <span class="icon is-large">
        <i class="fa fa-forumbee"></i>
      </span>
  </button>

</div>

<style>
  .foot {
    position: fixed;
    bottom: 10px;
    width: 100%;
    text-align: center;
  }
  
</style>