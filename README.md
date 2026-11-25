# Zomato Exploratory Data Analysis (EDA)

## Project Overview
This project explores a Zomato restaurant dataset (`zomato_data(1).csv`) using Python to analyze restaurant categories, customer votes, ratings, online ordering, table booking, and approximate cost for two people[cite: 33, 34]. Pandas is used to prepare and summarize the data, while Matplotlib and Seaborn are used to visualize patterns[cite: 33].

## Objectives
* Inspect the dataset structure and summary statistics
* Prepare the rating and column names for analysis
* Check missing values and duplicate records
* Compare restaurant types by votes, count, average rating, and estimated cost
* Explore ratings against votes and online-ordering availability[cite: 33]

## Tools & Libraries
* Python
* Jupyter Notebook
* Pandas
* NumPy
* Matplotlib
* Seaborn[cite: 33]

## Dataset Overview
The supplied CSV (`zomato_data(1).csv`) contains **148 rows and 7 columns** examined at the restaurant-record level[cite: 33, 34]:

| Field | Meaning |
| :--- | :--- |
| `Restaurant Name` | Restaurant name |
| `Online_Order` | Online order availability |
| `Book_Table` | Table booking availability |
| `Rate` | Rating in x/5 format |
| `Votes` | Number of customer votes |
| `Approx_Cost(For Two People)` | Approximate cost for two |
| `Listed_In(Type)` | Restaurant category[cite: 33] |

## Data Cleaning
1. **Convert Ratings to Numeric Values:** Extracted the numeric score before `/5` in `Rate` and converted it from text to `float64`[cite: 36].
2. **Standardize Column Names:** Converted all column names to lowercase (`df.columns.str.lower()`)[cite: 37].
3. **Rename Cost Column:** Renamed `approx_cost(for two people)` to `approx_cost`[cite: 37].
4. **Data-Quality Checks:** Verified **0 missing values** across all 7 columns and **0 duplicate rows**[cite: 37].

## Exploratory Data Analysis (EDA) Questions

1. **How many customer votes has each restaurant type received?**
   * Dining received the highest total votes (`20,363`), followed by `other` (`9,367`), `Cafes` (`6,434`), and `Buffet` (`3,028`)[cite: 38].

2. **How many restaurants offer table booking?**
   * Table booking is available in `8` records (`5.4%`) and unavailable in `140` records (`94.6%`)[cite: 38].
   * ![Table Booking Availability](images/table_booking_pie.png)

3. **Which five restaurants have the highest number of votes?**
   * `Empire Restaurant` leads with `4,884` votes, followed by `Meghana Foods` (`4,401`), `Onesta` (two records with `2,556` votes each), and `Kabab Magic` (`1,720`)[cite: 38, 39].
   * ![Top 5 Restaurants by Votes](images/top5_restaurants_votes.png)

4. **Is there a relationship between restaurant ratings and customer votes?**
   * Rating and votes show a moderate positive correlation ($r \approx 0.49$); this association does not imply causation[cite: 39].
   * ![Rating vs Votes Scatter Plot](images/rating_vs_votes_scatter.png)

5. **What is the average rating for each restaurant type?**
   * Mean ratings are highest for `other` (`3.91`), followed by `Buffet` (`3.84`), `Cafes` (`3.77`), and `Dining` (`3.57`)[cite: 40].

6. **Which restaurant type is most common in the dataset?**
   * `Dining` represents `110` of `148` records (`74.3%`), followed by `Cafes` (`23`), `other` (`8`), and `Buffet` (`7`)[cite: 40].
   * ![Count of Restaurant by Type](images/restaurant_type_countplot.png)

7. **What ratings do restaurants most commonly receive?**
   * Observed ratings range from `2.6` to `4.6`, with a mean of `3.63`, median of `3.7`, and mode of `3.8`[cite: 41].
   * ![Rating Distribution Histogram](images/rating_distribution_hist.png)

8. **Which restaurant type has the highest average cost for two people?**
   * `Buffet` has the highest mean cost for two (`671.43`), followed by `other` (`668.75`), `Cafes` (`545.65`), and `Dining` (`357.27`)[cite: 41].

9. **Do restaurants offering online ordering have higher ratings?**
   * Restaurants offering online ordering average `3.86` (median `3.9`), compared to `3.49` (median `3.4`) for those without online ordering[cite: 42].
   * ![Online Order vs Rating Boxplot](images/online_order_rating_boxplot.png)

10. **Which restaurant types have more records without online ordering?**
    * `Dining` has the most records without online ordering (`77` No vs. `33` Yes), followed by `Cafes` (`8` No vs. `15` Yes), `Buffet` (`3` No vs. `4` Yes), and `other` (`2` No vs. `6` Yes)[cite: 42].
    * ![Online Order vs Restaurant Type Heatmap](images/online_order_heatmap.png)

## Key Findings
* **Category Dominance:** `Dining` restaurants make up `74.3%` of the dataset (`110` of `148` records) and hold the highest total customer votes (`20,363`)[cite: 42].
* **Table Booking:** Only `8` restaurants (`5.4%`) offer table booking, while `140` (`94.6%`) do not[cite: 42].
* **Top-Voted Restaurants:** `Empire Restaurant` (`4,884` votes) and `Meghana Foods` (`4,401` votes) lead in customer votes[cite: 42].
* **Ratings & Votes:** Ratings and votes exhibit a moderate positive correlation ($r \approx 0.49$), with an overall average rating of `3.63` and mode of `3.8`[cite: 42, 43].
* **Category Ratings & Cost:** The `other` category achieves the highest mean rating (`3.91`), whereas `Buffet` has the highest average cost for two (`671.43`)[cite: 42, 43].
* **Online Ordering Impact:** Restaurants with online ordering have a higher mean rating (`3.86`) than those without (`3.49`), and `Dining` accounts for the highest count of records without online ordering (`77`)[cite: 43].

## Conclusion
`Dining` is the largest restaurant category and generates the highest total votes, while `Buffet` carries the highest average cost for two[cite: 43]. The `other` category achieves the highest mean rating across a small number of records[cite: 43]. Across the `148` supplied records, table booking is uncommon, and online-ordering availability is associated with higher ratings[cite: 43]. These findings describe the `148` supplied records and should not be generalized to all Zomato restaurants[cite: 43].

## Author
  Aijaz Ahmed
