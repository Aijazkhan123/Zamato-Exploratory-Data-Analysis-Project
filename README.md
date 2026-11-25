# Zomato Exploratory Data Analysis (EDA)

## Project Overview
This project explores a Zomato restaurant dataset (`zomato_data(1).csv`) at the restaurant-record level using Python. The analysis focuses on restaurant categories, customer votes, ratings, online ordering, table booking, and approximate cost for two people.

## Objectives
* Inspect the dataset structure and summary statistics.
* Prepare the rating values and column names for analysis.
* Check for missing values and duplicate records.
* Compare restaurant types by customer votes, record count, average rating, and estimated cost.
* Explore ratings against customer votes and online-ordering availability.

## Tools & Libraries
* **Language & Environment:** Python, Jupyter Notebook
* **Data Manipulation:** Pandas, NumPy
* **Data Visualization:** Matplotlib, Seaborn

## Dataset Overview
The dataset contains **148 rows and 7 columns** (with 145 unique restaurant names):

| Field | Meaning |
| :--- | :--- |
| `Restaurant Name` | Restaurant name |
| `Online_Order` | Online order availability (`Yes` / `No`) |
| `Book_Table` | Table booking availability (`Yes` / `No`) |
| `Rate` | Rating in `x/5` format |
| `Votes` | Number of customer votes |
| `Approx_Cost(For Two People)` | Approximate cost for two people |
| `Listed_In(Type)` | Restaurant category (`Buffet`, `Cafes`, `Dining`, `other`) |

## Data Cleaning & Preparation
1. **Numeric Rating Conversion:** Extracted the numeric rating before the `/` in the `Rate` column (e.g., converting `4.1/5` to `4.1`) and cast the column to `float64`.
2. **Column Standardization:** Converted all column names to lowercase and renamed `approx_cost(for two people)` to `approx_cost`.
3. **Data Quality Checks:** Verified that the dataset contains **0 missing values** and **0 duplicate rows**.

## Exploratory Data Analysis (EDA) Questions
1. How many customer votes has each restaurant type received?
2. How many restaurants offer table booking?
3. Which five restaurants have the highest number of votes?
4. Is there a relationship between restaurant ratings and customer votes?
5. What is the average rating for each restaurant type?
6. Which restaurant type is most common in the dataset?
7. What ratings do restaurants most commonly receive?
8. Which restaurant type has the highest average cost for two people?
9. Do restaurants offering online ordering have higher ratings?
10. Which restaurant types have more records without online ordering?

## Key Findings
* **Category Distribution & Votes:** `Dining` is the most common category, representing **74.3%** (110 of 148) of records, and received the highest total customer votes (**20,363**), followed by `other` (9,367), `Cafes` (6,434), and `Buffet` (3,028).
  ![Restaurant Count by Type](images/restaurant_type_count.png)
* **Table Booking Availability:** Table booking is uncommon—only **8 restaurants (5.4%)** offer it, while **140 (94.6%)** do not.
  ![Table Booking Availability](images/table_booking_pie.png)
* **Most Voted Restaurants:** **Empire Restaurant** leads with **4,884 votes**, followed by **Meghana Foods** (4,401), **Onesta** (2,556 across two separate records), and **Kabab Magic** (1,720).
  ![Top 5 Voted Restaurants](images/top5_voted_restaurants.png)
* **Ratings Overview:** Ratings range from **2.6 to 4.6**, with an overall mean of **3.63**, median of **3.7**, and mode of **3.8**.
  ![Rating Distribution](images/rating_distribution.png)
* **Ratings vs. Votes:** Restaurant ratings and customer votes show a moderate positive correlation (**r ≈ 0.49**).
  ![Ratings vs Votes Scatter Plot](images/ratings_vs_votes.png)
* **Average Rating by Type:** The `other` category has the highest mean rating (**3.91**), followed by `Buffet` (**3.84**), `Cafes` (**3.77**), and `Dining` (**3.57**).
* **Approximate Cost for Two:** `Buffet` has the highest average cost for two people (**671.43**), followed by `other` (**668.75**), `Cafes` (**545.65**), and `Dining` (**357.27**).
* **Online Ordering Impact:** Restaurants offering online ordering have a higher average rating (**3.86**, median **3.9**) than those without online ordering (**3.49**, median **3.4**). `Dining` has the highest number of records without online ordering (**77** `No` vs. **33** `Yes`).
  ![Online Order vs Rating Boxplot](images/online_order_rating_boxplot.png)
  ![Online Order by Category Heatmap](images/online_order_heatmap.png)

## Conclusion
In this sample of 148 Zomato records, `Dining` is the largest restaurant category and generates the highest total customer votes, whereas `Buffet` has the highest average cost for two people. Although the `other` category holds the highest mean rating, it represents a small number of records. Overall, table booking is rare, and online-ordering availability is associated with higher restaurant ratings. *(Note: These findings describe the 148 supplied records and should not be generalized to all Zomato restaurants.)*

## Author
  Aijaz Ahmed
