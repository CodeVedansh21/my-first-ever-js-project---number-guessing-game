# my-first-ever-js-project---number-guessing-game
this project is about a number guessing game which stores your previous guesses and also displays it while updating , i know its very very basic but this is my first project and this is just a start 

 // the code goes here 

 // total number of guesses = 10 so making a variable for it 
let totalNoOfAttempts = 10;
// the random number generater
const noToGuess = Math.round(Math.random(0, 1) * 100 + 1);
// button holder ;
const buttonHolder = document.getElementById('subt');
// Or by query seelect button also we can do = doc.getelemebyclassName(// calss name);
// value by user holder element
const userInputHolderElement = document.getElementById('guessField');
// the values to change the text and display
let changeTheTxtans = document.getElementById('guess');
// array display
let arrayDisplay = document.querySelector('.guesses');
// the no of attemplts
let updateguessRemain = document.querySelector('.lastResult');
let wrongResDisplay = document.querySelector('.lowOrHi');
// the main event of clicking the button
// first defining the array that stores user input
let userInputArray = [];
// now  main event
buttonHolder.addEventListener('click', (e) => {
  e.preventDefault(); // i dont know exactly what does it do but i saw this in tutorial  
  // user input value
  const userInputValue = userInputHolderElement.value;
  // first pushing the guess by user into array "userInputArray"
  userInputArray.push(userInputValue);
  // updating the prev attempts
  arrayDisplay.textContent = `${userInputArray.toString()}`;
  // iterating the total number of attempts
  totalNoOfAttempts--;
  // updating the guess remain
  updateguessRemain.textContent = `${totalNoOfAttempts}`;
  // now checking the number of guess are zero or not
  if (totalNoOfAttempts <= 0) {
    changeTheTxtans.textContent = `GAME OVER ! REFRESH THE PAGE TO PLAY AGAIN ,THE NUMBER WAS ${noToGuess}`;
  }
  if (userInputValue === noToGuess) {
    // code to say you guessed the right number
    changeTheTxtans.textContent = `CONGO YOU GUESSED IT RIGHT`;
  } else {
    // code to say you guessed it wrong
    if (userInputValue < noToGuess) {
      wrongResDisplay.textContent = `Wrong guess guess again the number you guessed is lower than the actual number `;
    } else {
      wrongResDisplay.textContent = `Wrong guess guess again the number you guessed is higher than the actual number`;
    }
  }
});
