# CS 225 Final Project
## Team members: Ashley Yeah, Brandon Oh, Jeha Chung, Jinpyo Lee


### Video Presentation
Here is a link to our [final presentation](https://www.youtube.com/watch?v=8XKLfOJ_9YA).
### Overview of Dataset
We obtained the data OpenFlights through the following link: *https://openflights.org/data.html*. From this link we used the [airports.dat](https://raw.githubusercontent.com/jpatokal/openflights/master/data/airports.dat) and [routes.dat](https://raw.githubusercontent.com/jpatokal/openflights/master/data/routes.dat) and converted them into text files. The text files are saved as `airports.txt` and `routedata.txt`, respectively. 

### How to compile
Compile the MakeFile with the following command:

    make

Once compiled, the executable created is called `flights`. You can run it as follows:

    ./flights --command [source] [landmark] [destination]

Parameters in the square bracket are optional and are only needed when running the landmark path functionality

`--command` should be replaced with an appropriate command:

* `-h` or `--help` : Lists the usage of the different commands
* `-m` or `--map` : Runs and outputs map of the busiest airports by most routes to `out.png`
* `-b` or `--bfs` : Run BFS, outputs the traversal path to `path.txt` and list of discovery/cross edges to `edges.txt`
* `-l` or `--landmarkpath` : Gives the shortest path from source airport to destination airport, through the landmark airport.  
Default airports are given as:
    - `source = "BOS"` (Boston)
    - `landmark = "CMI"` (Champaign)
    - `destination = "PVG"` (Shanghai)
    
    for custom routes, use your own airports by listing them after the `--landmarkpath` command, as shown above, and make sure to use the IATA code for each airport


### Testing
#### Overview
To run some of the given test files, simply compile:

    make test

Run the tests as follows:

    ./test


#### Dummy datasets
For the functions to run there are a few requirements for the datasets:
* The order of elements and details should follow the same format as the data we have in `airports.txt` and `routedata.txt`
    - For airport data, each line should have 14 elements, each separated with a comma, with no spaces in any of the lines. The 5th element is used as the airport name in IATA, and the 7th and 8th element is used as the latitude and longitude
    - For route data, each line should have 9 elements, with the 3rd and 5th element corresponding to the source airport and destination airport of each route in IATA code
* Unlike the elements in the link, each name does not have be in quotation marks
* A comma should not be included in any of the elements in both the datasets
* The elements of the datasets that include names should already be capilized if needed (The functions are case-sensitive)
* Each elements should be divided by commas
* Elements could be left blank if unavailable



