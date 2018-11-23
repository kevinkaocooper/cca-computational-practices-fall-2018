## Homework 8 (due Saturday, November 3, 2018)

You will be submitting each homework assignment into a new GitHub repository each week. [Here are instructions on how to do so.](https://github.com/zamfi/github-guide/blob/master/README.md) Please email me if you have any questions.

### Music & Motion mini-project

Your final Music and Motion mini-project is due this week.  For extra credit,
you can optionally add an API component to your program to augment its
behavior.

We'll be doing in-class critiques on Monday.

**Assignment**: Upload your mini-project to GitHub and email me a link

#### API

A copy of the API example we went over in class is included below.  It fetches
the current windspeed for a given zip code and uses that to determine how long
to draw a set of wavy lines.  In order to run the program you'll need to get
your own API ID and Secret from [aerisweather.com](http://aerisweather.com).

**Assignment**: Register for an free account with
[aerisweather.com](http://aerisweather.com). Update the program to have it use your
own API ID and Secret so you can run it.

**Optional**: Modify the program to do something based on a different component
of the weather data, such as the temperature, or modify it to do something more
interesting with the weather data.

```javascript
var weather;
var windSpeed;

function preload() {
    // var zipCode = "paris, france";
    // var zipCode = "80303";
    var zipCode = "19107";

    var ID = "PUT_YOUR_API_ID_HERE";
    var SECRET = "PUT_YOUR_API_SECRET_HERE";
    var url = 'https://api.aerisapi.com/observations/' + zipCode +
              '?client_id=' + ID + '&client_secret=' + SECRET;
    print("Fetching", url);
    weather = loadJSON(url);
}

function setup() {
    createCanvas(400, 200);
    windSpeed = weather.response.ob.windMPH;
    print("Wind Speed:", windSpeed);
}

function draw() {
    background(220);
    for (var y = 20; y < height-10; y += 20) {
        line(20, y, 20+random(4) + windSpeed * 10, y+random(-2, 2));
    }
}
```
