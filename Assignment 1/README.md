# DAA-Lab-Assignmentss
124B1F155(Design and Analysis of Algorithms Lab Submissions)
# Merge Sort on Customer Dataset

## 1. Aim

To design and implement the **Merge Sort algorithm in C++** for efficiently sorting customer records based on their **Annual Income (k$)** in ascending order.

## 2. Problem Statement

A customer dataset consists of various details such as **Customer ID, Gender, Age, Annual Income, and Spending Score**.

The main objective of this project is to implement the **Merge Sort algorithm** to arrange customer records in ascending order according to their **Annual Income (k$)**.

This project demonstrates the practical application of the **Divide and Conquer** technique for efficiently sorting customer records.

## 3. Dataset

### Dataset Name

**Mall Customer Segmentation Dataset**

### Dataset Source

**Kaggle – Mall Customer Segmentation Dataset**

### Number of Records

The dataset consists of **200 customer records**.

### Dataset Attributes

| Attribute              | Description                                                       |
| ---------------------- | ----------------------------------------------------------------- |
| CustomerID             | Unique identification number assigned to each customer            |
| Gender                 | Gender of the customer                                            |
| Age                    | Age of the customer                                               |
| Annual Income (k$)     | Annual income of the customer represented in thousands of dollars |
| Spending Score (1-100) | Spending score assigned to the customer                           |

### Sorting Attribute

The customer records are sorted using:

**Annual Income (k$)**

### Sorting Order

**Ascending Order**

## 4. Algorithm Used

### Merge Sort

Merge Sort is an efficient **Divide and Conquer** sorting algorithm.

It works by repeatedly dividing the given dataset into smaller portions, sorting those portions recursively, and then combining them to obtain the final sorted dataset.

The algorithm consists of three primary stages:

1. **Divide** – Split the dataset into two smaller halves.
2. **Conquer** – Recursively sort both halves.
3. **Merge** – Combine the sorted halves into one sorted sequence.

## 5. Why Merge Sort?

Merge Sort was chosen for this project because of the following advantages:

* It provides a guaranteed **O(n log n)** time complexity.
* It is suitable for processing large datasets.
* Its worst-case performance remains **O(n log n)**.
* It is a **stable sorting algorithm**.
* Its efficiency is not significantly affected by the initial ordering of the data.
* It is based on the efficient **Divide and Conquer** strategy.

## 6. Pseudocode

MERGE_SORT(array, left, right)

    IF left >= right
        RETURN

    mid = left + (right - left) / 2

    MERGE_SORT(array, left, mid)

    MERGE_SORT(array, mid + 1, right)

    MERGE(array, left, mid, right)


MERGE(array, left, mid, right)

    Create temporary array

    i = left
    j = mid + 1

    WHILE i <= mid AND j <= right

        IF array[i].income <= array[j].income

            Add array[i] to temporary array
            i = i + 1

        ELSE

            Add array[j] to temporary array
            j = j + 1

    Copy remaining elements from left half

    Copy remaining elements from right half

    Copy temporary array back into original array
```

## 7. Working of the Program

The program follows the steps given below to sort the customer records:

```text
Customer Dataset
       |
       v
Read Customer Records
       |
       v
Store Records in Vector
       |
       v
Select Sorting Attribute
(Annual Income)
       |
       v
Apply Merge Sort
       |
       v
Divide Records into Two Halves
       |
       v
Recursively Sort Both Halves
       |
       v
Merge Sorted Halves
       |
       v
Display Sorted Customer Records
```

## 8. Example

### Before Sorting

| CustomerID | Annual Income |
| ---------: | ------------: |
|          1 |            39 |
|          2 |            15 |
|          3 |            81 |
|          4 |            42 |
|          5 |            30 |

### After Sorting

| CustomerID | Annual Income |
| ---------: | ------------: |
|          2 |            15 |
|          5 |            30 |
|          1 |            39 |
|          4 |            42 |
|          3 |            81 |

Thus, the customer records are successfully arranged according to their **Annual Income** from lowest to highest.

## 9. Time Complexity Analysis

Merge Sort continuously divides the dataset into two approximately equal parts.

The number of division levels is approximately:

```text
log₂(n)
```

At every level, all elements are processed during the merging operation, resulting in:

```text
O(n)
```

### Best Case

```text
O(n log n)
```

### Average Case

```text
O(n log n)
```

### Worst Case

```text
O(n log n)
```

### Overall Time Complexity

```text
O(n log n)
```

For a dataset containing approximately **1,000,000 records**, the number of recursive levels is approximately:

```text
log₂(1,000,000) ≈ 20
```

Hence, Merge Sort continues to provide efficient performance even when the dataset size becomes very large.

## 10. Space Complexity

During the merging phase, Merge Sort requires a temporary array for storing intermediate results.

Therefore:

```text
Auxiliary Space Complexity = O(n)
```

The recursive function calls additionally require stack space of approximately:

```text
O(log n)
```

However, the overall auxiliary space requirement is dominated by the temporary array:

```text
Overall Space Complexity = O(n)
```

## 11. Comparison with Traditional Sorting Algorithms

| Algorithm      | Best Case  | Average Case | Worst Case | Suitable for Large Dataset |
| -------------- | ---------- | ------------ | ---------- | -------------------------- |
| Bubble Sort    | O(n)       | O(n²)        | O(n²)      | No                         |
| Selection Sort | O(n²)      | O(n²)        | O(n²)      | No                         |
| Insertion Sort | O(n)       | O(n²)        | O(n²)      | Limited                    |
| Quick Sort     | O(n log n) | O(n log n)   | O(n²)      | Yes                        |
| Merge Sort     | O(n log n) | O(n log n)   | O(n log n) | Yes                        |

Merge Sort offers a guaranteed **O(n log n)** worst-case time complexity. This makes it a dependable choice when working with large datasets where predictable sorting performance is important.

## 12. Program Output

The program reads all customer records from the dataset and sorts them in **ascending order of Annual Income (k$)**.

The complete execution output is stored in:

```text
output.txt
```

### Sample Output

```text
========================================
       MERGE SORT - CUSTOMER DATA
========================================

Dataset: Mall Customer Segmentation Dataset
Sorting Attribute: Annual Income (k$)
Sorting Order: Ascending

----------------------------------------
SORTED CUSTOMER DATA
----------------------------------------

CustomerID    Gender    Age    Income    SpendingScore

1             Male      19     15        39
2             Male      21     15        81
3             Female    20     16        6
4             Female    23     16        77
5             Female    31     17        40
...

----------------------------------------
RESULT
----------------------------------------

Total Records: 200
Sorting completed successfully.

Time Complexity: O(n log n)
Space Complexity: O(n)
```

## 13. Project Files

```text
## 13. Project Files

Assignment 1/
│
├── customer_order_merge_sort.cpp
│   └── C++ implementation of Merge Sort
│
├── output.png
│   └── Screenshot of the program execution output
│
├── 124B1F155_DAA_Assignment_1_Merge_Sort.pdf
│   └── Complete assignment report
│
└── README.md
    └── Project documentation

## 14. Technologies Used

* **Programming Language:** C++
* **Algorithm:** Merge Sort
* **Dataset:** Mall Customer Segmentation Dataset
* **IDE:** Visual Studio Code
* **Version Control:** Git and GitHub

## 15. Key Features

* Reads customer information from the dataset.
* Sorts customer records numerically.
* Uses **Annual Income (k$)** as the sorting key.
* Implements Merge Sort using the **Divide and Conquer** approach.
* Arranges records in ascending order.
* Displays the sorted customer information.
* Provides guaranteed **O(n log n)** time complexity.
* Uses additional **O(n)** space during the merging process.
* Can efficiently handle large datasets.
* Includes complete program execution output.

## 16. Conclusion

The **Merge Sort algorithm** was successfully implemented in C++ to arrange customer records according to their **Annual Income (k$)**. The project demonstrates the practical use of the **Divide and Conquer** strategy in solving sorting problems.

Merge Sort provides a guaranteed **O(n log n)** time complexity for the best, average, and worst cases, making it an efficient and reliable algorithm for handling large amounts of customer data.

Although the algorithm requires **O(n)** additional memory for the merging process, its predictable performance makes it preferable for large datasets compared with traditional quadratic sorting algorithms such as Bubble Sort, Selection Sort, and Insertion Sort.

Overall, this project demonstrates how a fundamental Data Structures and Algorithms concept can be applied to a real-world customer dataset to efficiently organize and process information.


## 17. Author

**Student Project – Data Structures and Algorithms**

**Language:** C++

**Algorithm:** Merge Sort
