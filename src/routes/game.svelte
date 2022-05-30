<script>
	let MyChoice = 'rock';
	let ComputerChoice = 'paper';
	let Input = 0;
	let message = '';
	
	let getComputerChoice = () => {
  Input = Math.floor(Math.random() * 3)
  if (Input === 0) {
    ComputerChoice = 'rock';
  } else if (Input === 1) {
    ComputerChoice = 'paper';
  } else if (Input === 2) {
    ComputerChoice = 'scissors';
}}
	
	function determineWinner() {
		Input = Math.floor(Math.random() * 3)
		if (Input === 0) {
			ComputerChoice = 'rock';
		} else if (Input === 1) {
			ComputerChoice = 'paper';
		} else if (Input === 2) {
			ComputerChoice = 'scissors';
	}	

  if(MyChoice === ComputerChoice) {
    message= "it's a tie :|"
  } else if (MyChoice === 'rock') {
    if (ComputerChoice === 'paper') {
      message= 'computer won :('
    } else {
      message= 'you won :D'
    }
  } else if (MyChoice === 'paper') {
    if (ComputerChoice === 'scissors') {
      message= 'computer won :('
    } else {
      message= 'you won :D'
    }
  } else if (MyChoice === 'scissors') {
    if (ComputerChoice === 'rock') {
      message= 'computer won :('
    } else {
      message= 'you won :D'
    }
  }
		{
		alert(`You played ${MyChoice} and computer played ${ComputerChoice}, ${message}`)
	}
}

</script>


<h2>Let's choose what to play first:</h2>
<label>
	<input type=radio bind:group={MyChoice} value={'rock'}>
	rock
</label>

<label>
	<input type=radio bind:group={MyChoice} value={'paper'}>
	paper
</label>

<label>
	<input type=radio bind:group={MyChoice} value={'scissors'}>
	scissors
</label>


<button on:click={determineWinner}>
	Click to see the result!
</button>

<style>
	h2 {
		color: #008080;
		font-family: courier;
	}
	label {
		color: #008080;
		font-family: courier;
	}
	button {
		color: #DEB887;
		font-family: courier;
		margin: 20px 50px 0 0
	}
</style>
