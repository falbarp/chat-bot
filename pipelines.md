# default

## main
nlp.train

## onIntent(joke.chucknorris)
// compiler=javascript
const something = request.get('https://api.chucknorris.io/jokes/random');
if (something && something.value) {
  input.answer = something.value;
}

## onIntent(joke.broma)
// compiler=javascript
const something = request.get('https://v2.jokeapi.dev/joke/Any?lang=es&type=twopart');
if (something && something.setup && something.delivery) {
  input.answer = something.setup + '\n'+ something.delivery;
}


# bot1

# main
console.say "Say something!"

## console.hear
// compiler=javascript
if (message === 'quit') {
  return console.exit();
}
nlp.process();
this.say();