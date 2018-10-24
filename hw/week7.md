## Homework 7 (due Friday, October 26, 2018)

You will be submitting each homework assignment into a new GitHub repository each week. [Here are instructions on how to do so.](https://github.com/zamfi/github-guide/blob/master/README.md) Please email me if you have any questions.

### Music & Motion mini-project

Your assignment this week is to submit a **working prototype** of your
Music and Motion mini-project.  Your goal is to combine motion and
music in one sketch.  You can use code we've gone over in class as a
starting point, but the mini-project should be significantly different
to be your own creation.

[freesound.org](freesound.org) and [soundbible.com](soundbible.com)
are two websites where you can find lots of fun sound effects to
add to your sketch.  If you download a sound from there, put a comment
in your code indicating the URL where you found it.  If a `wav` and an `mp3` version of the same file is available, download the `mp3` version.

We're halfway through the semester.  There will not be a written
midterm test, but your mini-project has a higher weight than a normal
homework assignment, so you can think of it as a midterm project.

**Assignment**: Upload your mini-project to GitHub and email me a link

#### Sound review example

For your reference, here's the code we worked on together in class, `Dripping with Sound`, which adds a sound effect to the `Dripping` code we've gone over in previous weeks.

Remember, in order for the sketch to run and play sounds, it must be run from a web server, such as the atom-live-server we've been using in class.  You'll also need to download the **splash.mp3** file.

```javascript
// The sound file splash.mp3 came from
// http://soundbible.com/1139-Water-Drop-Low.html

var splash;

function preload() {
  soundFormats('mp3', 'ogg');
  splash = loadSound('splash.mp3');
}

var x = 230;
var y = 220;
var tripped = false;

function setup() {
  createCanvas(400, 400);
}

function draw() {
  background(0);
  noStroke();

  // draw pipe
  rect(0, 200, x, 20);

  // draw drip
  ellipse(x, y, 10);

  // down 3 pixels each frame, but maybe should be accelerating?
  y = y + 3;

  // Play a sound if the drop has hit the bottom of the screen
  if (y >= height) {
      // Only play the sound the first time it passes the edge
      // of the screen.  Use the "tripped" variable to remember
      // if this is the first time or not.
      if (tripped == false) {
          splash.play();
          tripped = true;
      }
  }

  // if invisible for a full “height” amount…
  if (y > height*2) {
    // reset
    y = 220;
    tripped = false;
  }
}
```


### APIs prep

Next class, we'll be talking about APIs.  If you haven't already done so, watch Daniel Shiffman's videos [10.1 - 10.5](https://www.youtube.com/watch?v=rJaXOFfwGVw&index=1&list=PLRqwX-V7Uu6a-SQiI4RtIwuOrLJGnel0r). We'll do a workshop in class to solidify these ideas, but this will be good background to draw upon.

You should be able to answer these questions:

1. What is an API?
2. What is "JSON"? Why do developers use this?
3. What does `data.birds[1].members[2]` do?
4. What is a "callback"?
