<script>
  import 'bulma/css/bulma.css'
  import { fade } from 'svelte/transition'

  let stage = 0
  let noGreet = false
  $: toyou = stage == 6 || stage == 7
  $: greet = stage >= 1 && stage < 6 && !noGreet
  $: ha = stage >= 2 && !toyou
  $: py = stage >= 3 && !toyou
  $: bi = stage >= 4 && !toyou
  $: da = stage >= 5 && !toyou
  $: to = stage == 6
  $: you = stage == 7
  const greeting = () => {
    stage++
    if (stage == 8) {
      noGreet
      stage = 2
    }
  }
</script>

{#if greet}
  <main in:fade class="hero is-primary">
    <div class="hero-body">
      <h1 class="title">Happy Birthday!</h1>
      <h2 class="subtitle">Dear 爱爱美美</h2>
    </div>
  </main>
{/if}

{#if ha}
  <div in:fade class="container">
    <div class="notification is-warning">HAP</div>
  </div>
{/if}
{#if py}
  <div in:fade class="container">
    <div class="notification is-info">PY</div>
  </div>
{/if}

{#if bi}
  <div in:fade class="container">
    <div class="notification is-error">BIRTH</div>
  </div>
{/if}
{#if da}
  <div in:fade class="container">
    <div class="notification is-success">DAY</div>
  </div>
{/if}

{#if to}
  <div in:fade class="container">
    <div class="notification is-link">MY</div>
  </div>
{/if}

{#if you}
  <div in:fade class="container">
    <div class="notification is-danger">LOVE</div>
  </div>
{/if}

<div class="foot">
  <button class="button is-large is-rounded is-warning" on:click={greeting}>
    <span class="icon is-large">
      <i class="fa fa-forumbee" />
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
