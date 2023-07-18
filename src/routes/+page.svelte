<script>
  import Header from "$lib/Header.svelte"
  let src = ""
  let player1
  let player2
  let result = ""

  function paper() {
    src = "/paper 3.png"
    player1 = src
    player2 = ""
  }

  function scissors() {
    src = "/scissors 3.png"
    player1 = src
    player2 = ""
  }

  function rock() {
    src = "/rock 2.png"
    player1 = src
    player2 = ""
  }

  function play() {
    let choices = ["/paper 3.png", "/scissors 3.png", "/rock 2.png"]
    let index = Math.floor(Math.random(0) * choices.length)
    player2 = choices[index]

    if (player1 == player2) {
      result = "it's a tie"
    } else if (player1 == "/paper 3.png") {
      if (player2 == "/scissors 3.png") {
        result = "you lost"
      } else {
        result = "you won"
      }
    } else if (player1 == "scissors 3.png") {
      if (player2 == "/rock 2.png") {
        result = "you lost"
      } else {
        result = "you won"
      }
    } else {
      if (player2 == "/scissors 3.png") {
        result = "you lost"
      } else {
        result = "you won"
      }
    }
  }
</script>

<Header />

<main>
  <h2>Paper, Scissors, Rock</h2>

  <p>Choose one:</p>
  <button on:click={paper}><img src="/paper 3.png" alt="" /></button>
  <button on:click={scissors}><img src="/scissors 3.png" alt="" /></button>
  <button on:click={rock}><img src="rock 2.png" alt="" /></button>

  <p>Your choice:</p>
  <img {src} alt="" /><br />
  <button on:click={play}>Generate Opponents choice</button>
  <p>Opponents Choice:</p>
  <img src={player2} alt="" /><br />

  {result}
  <!-- {#if player1 == "paper" && player2 == "/paper 3.png"}
    <p>Tie</p>
  {:else if player1 == "paper" && player2 == "/scissors 3.png"}
    <p>You lost</p>
  {:else if player1 == "paper" && player2 == "/rock 2.png"}
    <p>You won</p>
  {/if}

  {#if player1 == "scissors" && player2 == "/paper 3.png"}
    <p>You won</p>
  {:else if player1 == "scissors" && player2 == "/scissors 3.png"}
    <p>Tie</p>
  {:else if player1 == "scissors" && player2 == "/rock 2.png"}
    <p>You lost</p>
  {/if}

  {#if player1 == "rock" && player2 == "/paper 3.png"}
    <p>You lost</p>
  {:else if player1 == "rock" && player2 == "/scissors 3.png"}
    <p>You won</p>
  {:else if player1 == "rock" && player2 == "/rock 2.png"}
    <p>Tie</p>
  {/if} -->
</main>

<footer>
  <p>&copy; Craighead Diocesan School 2023</p>
</footer>

<style>
  img {
    width: 10em;
  }
</style>
