# Degrees Of Separation Finding The Shortest Path AI

## Overview

**Degrees** is a Python program that determines how many degrees of separation exist between two actors. The concept is based on the popular "Six Degrees of Kevin Bacon" game, which posits that any two actors can be connected through their movie roles in six steps or fewer. This project solves the problem by using a **Breadth-First Search (BFS)** algorithm to find the shortest path between two actors through the movies they've starred in.

## Project Structure

The project contains the following files:
- `degrees.py`: The main program that handles user input and calculates the shortest path between two actors.
- `util.py`: Contains utility classes for implementing the search algorithm.
- CSV data:
  - `people.csv`: Contains information about actors, including their unique IDs and names.
  - `movies.csv`: Contains movie details, including their unique IDs and titles.
  - `stars.csv`: Maps actors to movies they have starred in.

## Usage

### To Run The Program:
1. Clone the repo: `git clone https://github.com/musty-ess/Degrees-Of-Separation-Finding-The-Shortest-Path-AI.git`
2. Run the game by executing: `python degrees.py small`

This will load a smaller dataset from the small directory, which contains actor-movie relationships. After loading the data, you can enter the names of two actors, and the program will compute the shortest path between them in terms of movies they've starred in.

### Example Output

```bash
Loading data...
Data loaded.
Name: Emma Watson
Name: Jennifer Lawrence
3 degrees of separation.
1: Emma Watson and Brendan Gleeson starred in Harry Potter and the Order of the Phoenix
2: Brendan Gleeson and Michael Fassbender starred in Trespass Against Us
3: Michael Fassbender and Jennifer Lawrence starred in X-Men: First Class
```

## Problem Description

Given two actors, the goal is to find the shortest path connecting them through a sequence of movies, where each movie connects one actor to another. This problem is framed as a search problem where:

- **States** are actors.
- **Actions** are movies that connect actors.

**Breadth-First Search (BFS)** algorithm was used to find the shortest path between two actors, ensuring that the solution returned is the path with the fewest "degrees of separation."

## Implementation

The key function implemented in this project is `shortest_path`, which:

- Takes the IDs of the source and target actors.
- Returns a list of `(movie_id, person_id)` tuples representing the shortest path.
- Uses BFS to explore actors and movies, ensuring the shortest path is found.

Example return value of shortest_path: `[(movie1_id, actor1_id), (movie2_id, actor2_id), ...]`

If no path is found between the two actors, the function returns `None`.

## CSV Data Structure

- **people.csv**: Contains actor information (ID, name, birth year).
- **movies.csv**: Contains movie information (ID, title, release year).
- **stars.csv**: Maps actors to movies via actor and movie IDs.

## Additional Features

- Efficiently handles large datasets using BFS to find the shortest path.
- Can process multiple paths of equal length and return any valid shortest path.

## How the Solution Works

1. **Data Loading**: The program first loads actor and movie data from CSV files into memory.
2. **User Input**: Prompts the user for two actor names.
3. **Path Finding**: Uses BFS to search for the shortest path between the two actors by exploring the movies they've starred in.
4. **Output**: Displays the number of degrees of separation and the sequence of movies and actors that connect them.

## Conclusion

This project demonstrates a practical application of search algorithms in the context of the entertainment industry, showing how actors can be connected through their roles in movies. By implementing the `shortest_path` function, the program successfully finds the shortest connection between two actors using movie data.
