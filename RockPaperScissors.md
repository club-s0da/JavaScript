```javascript
# JavaScript for Rock Paper Scissors

let player = {
  currentChoice: null
};

let computer = {
  currentChoice: null
};

# an array of choices:
const gameChoices = ["Rock","Paper","Scissors"];

# ANOTHER function (or just instructions) to LISTEN for a CLick and then update the player.currentChoice!! (NEED DOM!!)
function playerChoice(e) {
  e.target.player.currentChoice = gameChoices[0];
  e.target.player.currentChoice = gameChoices[1];
  e.target.player.currentChoice = gameChoices[2];
}
const rock = document.getElementById('rock');
const paper = document.getElementById('paper');
const scissors = document.getElementById('scissors');

function playerChoice() {
rock.addEventListener('click',function(){player.currentChoice=gameChoices[0]});
paper.addEventListener('click',function(){player.currentChoice=gameChoices[1]});
scissors.addEventListener('click',function(){player.currentChoice=gameChoices[2]});
};

# Redefine separate pieces of action using functions!
const computerChooses = () => {
  let randomIndex = Math.floor(Math.random() * gameChoices.length);
  computer.currentChoice = gameChoices[randomIndex];
  //console.log("The computer chose: "+computer.currentChoice+ "."); 
}

# compareChoices() the conditional logic that compares the computer's and player's choices:
const compareChoices = () => {
  computerChooses();
  if (computer.currentChoice === player.currentChoice) {
  displayResult("It's a tie! Computer and Player both chose "+ computer.currentChoice+".");
} else if (computer.currentChoice === gameChoices[0]) {
  if (player.currentChoice === gameChoices[1]) {
    displayResult("Player wins! Player chose " +player.currentChoice+" and the computer chose "+computer.currentChoice+".");
  } else {
    displayResult("Computer wins! Computer chose "+ computer.currentChoice+" and the player chose "+player.currentChoice+".");
  }
} else if (computer.currentChoice === gameChoices[1]) {
  if (player.currentChoice === gameChoices[0]) {
    displayResult("Computer wins! Computer chose "+ computer.currentChoice+ " and the player chose "+ player.currentChoice+".");
  } else {
    displayResult("Player wins! Player chose " + player.currentChoice+ " and the computer chose "+ computer.currentChoice+".");
  }
} else if (computer.currentChoice === gameChoices[2]) {
  if (player.currentChoice === gameChoices[0]) {
    displayResult("Player wins! Player chose "+ player.currentChoice+" and the computer chose "+ computer.currentChoice+".");
  } else {
    displayResult("Computer wins! Computer chose "+ computer.currentChoice+ " and the player chose "+ player.currentChoice+".");
  }
}
}

# A Function to display the results ON the HTML webpage! (instead of console.log -ing the result!!)
const displayResult = (results) => { 
  const create = document.createElement('p');
  create.innerHTML = results;

  document.body.append(create);   //I HAVE TO put document here !!

}
compareChoices();

```
