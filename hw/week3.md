## Homework 3 (due Friday, September 28, 2018)

You will be submitting each homework assignment into a new GitHub repository each week. [Here are instructions on how to do so.](https://github.com/zamfi/github-guide/blob/master/README.md) Please [email me](mailto:michael.toren@cca.edu) if you have any questions.

### Classwork wrap-up

**Assignment**: In class, you created animations inspired by four example sketches. Post two of your favorites to your homework repository.

If you worked with a partner, you can both submit the same work -- but be sure to note at the top (in a comment, i.e., a line that starts with `//`) who your collaborators were.

### Animation practice

Let's start with this p5.js **Lawn Simulator™**:

```javascript
function setup() {
  createCanvas(400, 200);
  colorMode(HSB, 360, 100, 100, 100);
}

var x = 0;
var h = 10;

function draw() {
  stroke(random(60, 70), 100, 90);
  line(x, height-10, x + random(-10, 10), height-10-random(h));

  x = x + 10;

  if (x > width) {
    x = random(10);
    h = h + 3;
  }

  if (random() > 0.999) {
    noStroke();
    fill(255);
    rect(-1, -1, width+2, height-15);
    h = 10;
  }

  noStroke();
  fill(40, 100, 60);
  rect(0, height-10, width, 10);
}
```

Read through and make sure you understand what's going on. In particular:

1. What code draws the blades of grass?
2. What code makes the "lawnmower" come by? How often does it come by?
3. What's the point of the `h` variable?
4. What do the three numerical arguments of `colorMode` do?
5. What does the `-10` do in the second and fourth arguments of the `line` function, `height-10-random(h)`? Why is it there?

**Assignment**: Answer these questions in the `README.md` file in your homework repository.

With those answers in mind, make the following changes:

**Assignment**: Perhaps you prefer a much better maintained lawn. Make the lawnmower come by much more often. Save this in your homework repository as `speedy-lawnmower.js`.

**Assignment**: Make the lawnmower come when the grass reaches a pre-determined height. Save this in your homework repository as `height-lawnmower.js`.

**Assignment**: Make it a windy day! Change how the blades of grass are drawn so that they all slant towards the right. Save this in your homework repository as `windy-lawnmower.js`.

**Optional Challenge**: Of course, because this is a computer, you can make the lawnmower come whenever you want. Use the variable `mouseIsPressed` to make mouse clicks trigger the lawnmower. Save this in your homework repository as `clicky-lawnmower.js`.  (Hint: the `mouseIsPressed` variable is documented in the P5 reference, and was also used in the Bubbles program in the first day of class.)

**Optional Challenge**: Right now, the grass just **disappears** -- animate the lawnmwer coming through and cutting back the grass. (You might need a bunch of extra variables for this! Remember how you animate a shape moving across the screen.) Save this in your homework repository as `animated-lawnmower.js`.

**Optional Challenge**: Add flowers when the blades of grass reach a certain height. Save this in your homework repository as `flowery-lawnmower.js`.

### Loops, arrays, and other complexity

Watch the following Daniel Shiffman videos about loops and arrays in P5 and JavaScript:

* [4.1](https://www.youtube.com/watch?v=cnRD9o6odjk&list=PLRqwX-V7Uu6Zy51Q-x9tMWIv9cueOFTFA&index=16)
* [4.2](https://www.youtube.com/watch?v=1c1_TMdf8b8&list=PLRqwX-V7Uu6Zy51Q-x9tMWIv9cueOFTFA&index=17)
* [7.1](https://www.youtube.com/watch?v=VIQoUghHSxU&index=24&list=PLRqwX-V7Uu6Zy51Q-x9tMWIv9cueOFTFA)
* [7.2](https://www.youtube.com/watch?v=RXWO3mFuW-I&index=25&list=PLRqwX-V7Uu6Zy51Q-x9tMWIv9cueOFTFA)

We'll be going over arrays and loops during class next week.

*Aside: I am looking for a free online resource that contains the same content -- but I'm coming up empty. There is a book out there, [Getting Started with P5.js](https://p5js.org/books/), that covers similar content, and it's available at the [SF public library](https://sfpl.bibliocommons.com/item/show/3201528093). CCA's library doesn't have a copy yet, but I've requested that they purchase it.*

### Catching up on some older videos

This last part just needs to be completed before next Monday's class -- no need to do it by Friday.

We skipped these three videos earlier, but now's a good time to catch up. Watch these Daniel Shiffman videos about **objects**, the `map` function, and the `random` function:

* [2.3](https://www.youtube.com/watch?v=-e5h4IGKZRY&list=PLRqwX-V7Uu6Zy51Q-x9tMWIv9cueOFTFA&index=9)
* [2.4](https://www.youtube.com/watch?v=nicMAoW6u1g&list=PLRqwX-V7Uu6Zy51Q-x9tMWIv9cueOFTFA&index=10)
* [2.5](https://www.youtube.com/watch?v=nfmV2kuQKwA&list=PLRqwX-V7Uu6Zy51Q-x9tMWIv9cueOFTFA&index=11)

Answer these questions in your `README.md` file:

1. What's the point of an object?
2. What's an example of a range you might use for the `map` function?
3. What line of code would give me a random year in the last century?
