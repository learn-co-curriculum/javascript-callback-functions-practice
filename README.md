# Practice - Callback Functions

## Overview

This practice lesson will help you understand the concepts surrounding Callback Functions.

Flatiron Movie Theater wants to use callback functions to optimize the code for their website, Flatdango, that allows its users to view movie details for a movie that they want to see at the Flatiron Movie Theater.

## Tools and Resources

It is recommended that you use the Visual Studio Code (VSCode) IDE for this practice lesson.

Useful considerations and terminology:

**Function**: A special block of code that contains a set of statements that performs a task or calculates a value. A function can be called / invoked to execute its code.

**Callback Function**: A function that is passed in as an argument to another function and called / invoked within the other function.

Here are some resources from the [MDN Web Docs](https://developer.mozilla.org/en-US/) website that will provide you with additional knowledge about functions and callback functions:
- MDN
  - [Functions](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Guide/Functions)
  - [Callback function](https://developer.mozilla.org/en-US/docs/Glossary/Callback_function)

## Instructions

**Fork and clone** this practice lesson into your local environment. Navigate into its
directory in the terminal, then run `code .` to open the files in Visual Studio
Code.

Then, open the `index.html` file on your browser to run the application.

Write your code in the `index.js` file. There is some starter code provided in `index.js`.

These are your tasks:

1. `getMovieDetails(movieTitle, getMovieMessage)`: Create a `function` named `getMovieDetails` that has 2 parameters. The first parameter is named `movieTitle` and its value should be a `string` when the correct value is passed as an argument into the `getMovieDetails()` function. The second parameter is named `getMovieMessage` and its value should be a `function` when the correct value is passed as an argument into the `getMovieDetails()` function. When the `getMovieDetails()` function is called, the following actions should take place:
    - An `object` is created and stored into a variable named `movie`. The `object` contains a key of `title` whose value is set to the value of the `movieTitle` parameter.
    - If the movie’s title is `"The Giant Gila Monster"`, the following key and value pairs are added to the `object` referenced by the variable named `movie`:
      - A key of `runtime` whose value is set to `"108 minutes"`.
      - A key of `showtime` whose value is set to `"04:00PM"`.
      - A key of `description` whose value is set to `"A giant lizard terrorizes a rural Texas community and a heroic teenager attempts to destroy the creature."`
    - If the movie’s title is `"Manos: The Hands Of Fate"`, the following key and value pairs are added to the `object` referenced by the variable named `movie`:
      - A key of `runtime` whose value is set to `"118 minutes"`.
      - A key of `showtime` whose value is set to `"06:45PM"`.
      - A key of `description` whose value is set to `"A family gets lost on the road and stumbles upon a hidden, underground, devil-worshiping cult led by the fearsome Master and his servant Torgo."`
    - If the movie’s title is `"Time Chasers"`, the following key and value pairs are added to the `object` referenced by the variable named `movie`:
      - A key of `runtime` whose value is set to `"93 minutes"`.
      - A key of `showtime` whose value is set to `"09:30PM"`.
      - A key of `description` whose value is set to `"An inventor comes up with a time machine, but must prevent its abuse at the hands of an evil C.E.O."`
    - The `function` referenced by the `getMovieMessage` parameter is called and its `return` value is returned from the `getMovieDetails()` function.
      - For example: If the `return` value of `getMovieMessage()` is "Hello World", the `getMovieDetails()` function should return "Hello World" as well.
2. `movieMessage`: Call the `getMovieDetails()` function and store its `return` value into a variable named `movieMessage`. When calling the `getMovieDetails()` function, the following 2 arguments should be passed into the `getMovieDetails()` function:
    - The first argument passed into the `getMovieDetails()` function is the value of the first movie title from the array stored in the `movieTitles` variable.
    - The second argument passed into the `getMovieDetails()` function is an anonymous `function` that has one parameter named `movie` whose value should be an `object` that contains the following keys: `title`, `runtime`, `showtime`, and `description`, when the correct value is passed as an argument into the anonymous function. When the anonymous function is called, a `string` in the following format is returned from the anonymous function: `"[title] is [runtime] long and starts at [showtime]. Here is the movie description: [description]"` — where `[title]` should be replaced with the movie’s title, `[runtime]` should be replaced with the movie’s runtime, etc.

## Solution

```javascript
// Task # 1 solution code
function getMovieDetails(movieTitle, getMovieMessage){
    const movie = {
        title: movieTitle
    };

    if(movie.title === "The Giant Gila Monster"){
        movie.runtime = "108 minutes";
        movie.showtime = "04:00PM";
        movie.description = "A giant lizard terrorizes a rural Texas community and a heroic teenager attempts to destroy the creature.";
    }
    else if(movie.title === "Manos: The Hands Of Fate"){
        movie.runtime = "118 minutes";
        movie.showtime = "06:45PM";
        movie.description = "A family gets lost on the road and stumbles upon a hidden, underground, devil-worshiping cult led by the fearsome Master and his servant Torgo.";
    }
    else if(movie.title === "Time Chasers"){
        movie.runtime = "93 minutes";
        movie.showtime = "09:30PM";
        movie.description = "An inventor comes up with a time machine, but must prevent its abuse at the hands of an evil C.E.O.";
    }

    return getMovieMessage(movie);
}

// Task # 2 solution code
const movieMessage = getMovieDetails(movieTitles[0], (movie) => {
    return `${movie.title} is ${movie.runtime} long and starts at ${movie.showtime}. Here is the movie description: ${movie.description}`;
});
```