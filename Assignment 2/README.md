Quick Sort on Movie Dataset
1. Aim

To design and implement the Quick Sort algorithm in C++ to efficiently sort a real-world movie dataset according to movie ratings.

The project reads movie records from a CSV file, applies Quick Sort using the movie rating as the sorting key, and displays the sorted movie records.

2. Problem Statement
A movie dataset contains information such as movie title, rating, release year, and popularity.

The objective of this project is to implement the Quick Sort algorithm to arrange movies in ascending order according to their rating.

The program reads the movie data from a CSV file, stores the records using a C++ vector, applies Quick Sort, and displays the sorted movie information.

3. Dataset
Dataset Name
Real Movie Titles Dataset

Dataset File
movies_real_titles.csv
Dataset Format
The CSV file contains the following attributes:

Attribute	Description
Title	Name of the movie
Rating	Movie rating
Release Year	Year in which the movie was released
Popularity	Popularity value of the movie
Example Dataset
Title,Rating,Release Year,Popularity
The Shawshank Redemption,9.3,1994,98
The Godfather,9.2,1972,95
The Dark Knight,9.0,2008,97
Pulp Fiction,8.9,1994,94
Forrest Gump,8.8,1994,92
Sorting Attribute
The movie records are sorted according to:

Rating

Sorting Order
Ascending Order

4. Algorithm Used
Quick Sort
Quick Sort is a Divide and Conquer sorting algorithm.

It selects an element as a pivot and partitions the array so that:

Elements smaller than or equal to the pivot are placed on the left.
Elements greater than the pivot are placed on the right.
The pivot is placed in its correct position.
Quick Sort is then recursively applied to the left and right portions.

5. Working of the Algorithm
The implementation uses the last element as the pivot.

For example:

Ratings:

8.5   9.1   7.8   8.9   7.5
                         ↑
                       Pivot
The partition operation places values smaller than or equal to the pivot on the left.

After partitioning:

7.5   7.8   8.5   9.1   8.9
              ↑
            Pivot
Quick Sort then recursively sorts the left and right portions.

6. Steps Performed by the Program
Movie CSV Dataset
       |
       v
Read CSV File
       |
       v
Store Movie Records in Vector
       |
       v
Select Last Element as Pivot
       |
       v
Partition According to Rating
       |
       v
Place Pivot at Correct Position
       |
       v
Recursively Sort Left Part
       |
       v
Recursively Sort Right Part
       |
       v
Display Sorted Movies
7. Pseudocode
Quick Sort
QUICKSORT(movies, low, high)

    IF low >= high
        RETURN

    pivotIndex = PARTITION(movies, low, high)

    QUICKSORT(movies, low, pivotIndex - 1)

    QUICKSORT(movies, pivotIndex + 1, high)
Partition
PARTITION(movies, low, high)

    pivot = movies[high].rating

    i = low - 1

    FOR j = low TO high - 1

        IF movies[j].rating <= pivot

            i = i + 1

            SWAP movies[i] and movies[j]

    SWAP movies[i + 1] and movies[high]

    RETURN i + 1
8. CSV File Handling
The program uses C++ file handling to read the movie dataset.

The following libraries are used:

#include <fstream>
#include <sstream>
The CSV file is opened using:

ifstream file(filename);
Each line is read using:

getline(file, line);
The individual values are separated using:

stringstream ss(line);
The movie attributes are then extracted:

Title
Rating
Release Year
Popularity
and stored in a Movie structure.

9. Data Structure Used
A structure named Movie is used to store the movie information.

struct Movie {
    string title;
    float rating;
    int rel_year;
    int popul;
};
A vector is used to store all movie records:

vector<Movie> movies;
This allows the Quick Sort algorithm to directly rearrange the movie records.

10. Pivot Selection
In this implementation, the last movie's rating is selected as the pivot.

float pivot = movies[high].rating;
For example:

Ratings:

8.2  9.0  7.5  8.8  8.0
                     ↑
                   Pivot
Here, 8.0 is selected as the pivot.

The partition function rearranges the elements around this pivot.

11. Time Complexity
The time complexity of Quick Sort depends on how the pivot divides the dataset.

Best Case
When the pivot divides the dataset into approximately equal halves:

O(n log n)
Average Case
For a reasonably balanced partition:

O(n log n)
Worst Case
If the pivot repeatedly becomes the smallest or largest element:

O(n²)
Complexity Summary
Case	Time Complexity
Best Case	O(n log n)
Average Case	O(n log n)
Worst Case	O(n²)
12. Space Complexity
The Quick Sort implementation is recursive.

The additional space depends on the recursion depth.

Average Case
O(log n)
Worst Case
O(n)
Therefore, Quick Sort generally requires less additional memory than Merge Sort.

13. Comparison with Other Sorting Algorithms
Algorithm	Best Case	Average Case	Worst Case	Extra Space
Bubble Sort	O(n)	O(n²)	O(n²)	O(1)
Selection Sort	O(n²)	O(n²)	O(n²)	O(1)
Insertion Sort	O(n)	O(n²)	O(n²)	O(1)
Merge Sort	O(n log n)	O(n log n)	O(n log n)	O(n)
Quick Sort	O(n log n)	O(n log n)	O(n²)	O(log n) average
Quick Sort is generally very efficient in practice, but its worst-case performance can become O(n²) when poor pivot choices repeatedly produce unbalanced partitions.

14. Program Output
The program displays the movies sorted according to their rating.

The output format is:

Movies sort by Rating using Quick Sort:

Title                                                       Rating    Release Year    Popularity
------------------------------------------------------------------------------------------------
Movie 1                                                     7.2       2010            75
Movie 2                                                     7.5       2015            81
Movie 3                                                     8.0       2008            90
Movie 4                                                     8.5       1999            93
Movie 5                                                     9.0       2008            97
The complete execution output is stored in:

output.txt
15. Sample Input
The program reads the following file:

movies_real_titles.csv
Example:

Title,Rating,Release Year,Popularity
The Shawshank Redemption,9.3,1994,98
The Godfather,9.2,1972,95
The Dark Knight,9.0,2008,97
Pulp Fiction,8.9,1994,94
Forrest Gump,8.8,1994,92
16. Sample Sorted Output
After applying Quick Sort:

Movies sort by Rating using Quick Sort:

Title                                                       Rating    Release Year    Popularity
------------------------------------------------------------------------------------------------
Forrest Gump                                                8.8       1994            92
Pulp Fiction                                                8.9       1994            94
The Dark Knight                                             9.0       2008            97
The Godfather                                               9.2       1972            95
The Shawshank Redemption                                    9.3       1994            98
The movies are arranged in ascending order of rating.

17. Technologies Used
Programming Language: C++
Algorithm: Quick Sort
Data Structure: Vector
Dataset Format: CSV
IDE: Visual Studio Code
Version Control: Git and GitHub
18. C++ Libraries Used
The following libraries are used:

#include <iostream>
#include <vector>
#include <string>
#include <fstream>
#include <sstream>
#include <chrono>
#include <algorithm>
#include <iomanip>
Purpose
Library	Purpose
iostream	Input and output
vector	Store movie records
string	Handle movie titles
fstream	Read CSV file
sstream	Parse CSV data
chrono	Time measurement support
algorithm	Swap and sorting-related operations
iomanip	Formatted output
19. Key Features
Reads movie records from a CSV file.
Stores movie data using a C++ structure.
Uses a vector to manage movie records.
Uses the last element as the pivot.
Implements the partition operation.
Recursively applies Quick Sort.
Sorts movies according to rating.
Displays title, rating, release year, and popularity.
Uses efficient Divide and Conquer technique.
Provides O(n log n) average-case performance.
20. Project Structure
QuickSort/
│
├── quick_sort.cpp
│   └── C++ implementation of Quick Sort
│
├── movies_real_titles.csv
│   └── Movie dataset
│
├── output.txt
│   └── Program execution output
│
└── README.md
    └── Project documentation
21. How to Run the Program
Step 1: Open the project in VS Code
Open the Quick Sort project folder.

Step 2: Make sure the CSV file is present
The following files should be in the same directory:

quick_sort.cpp
movies_real_titles.csv
Step 3: Compile
Using g++:

g++ quick_sort.cpp -o quick_sort
Step 4: Run
On Windows:

quick_sort
or:

.\quick_sort
Step 5: View Output
The sorted movie records will be displayed in the terminal.

The output can also be saved in:

output.txt
22. Conclusion
The Quick Sort algorithm was successfully implemented in C++ to sort a real-world movie dataset according to movie ratings.

The program reads movie records from a CSV file, stores them in a vector, selects the last element as a pivot, partitions the records, and recursively sorts the resulting subarrays.

Quick Sort provides an average-case time complexity of O(n log n) and uses relatively low additional memory compared with algorithms such as Merge Sort. However, its worst-case time complexity is O(n²) when the pivot selection produces highly unbalanced partitions.

This project demonstrates the practical application of the Divide and Conquer strategy to efficiently process and sort real-world movie data.

23. Author
Student Project - Data Structures and Algorithms

Language: C++

Algorithm: Quick Sort

Sorting Attribute: Movie Rating
