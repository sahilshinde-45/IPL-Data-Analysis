# IPL-Data-Analysis
IPL Data Analysis is a data-driven project that utilizes the power of Apache Spark (PySpark) to analyze Indian Premier League (IPL) cricket match datasets. The aim is to extract meaningful insights such as team performance trends, top-performing players, and season-based statistics by processing large datasets efficiently.

Using PySpark’s distributed computing capabilities, the project performs data cleaning, transformation, and complex aggregations. It also leverages window functions to generate advanced metrics like player rankings and cumulative scores. Visualizations are generated using Matplotlib and Seaborn to make the insights intuitive and compelling.

Whether you're a data enthusiast, a cricket fan, or a Spark learner, this project provides a comprehensive walkthrough of end-to-end big data analysis using Python.

# Technologies Used

1. Python – Core programming language for logic and scripting

2. Apache Spark (PySpark) – Distributed data processing for handling large datasets efficiently

3. Pandas – Additional data manipulation for flexibility in small-to-medium transformations

4. Matplotlib / Seaborn – Visualization libraries for plotting trends, comparisons, and summaries

5. Databricks – Collaborative environment for interactive Spark-based data analysis and visualization

# Features

1. Data cleaning and preprocessing using PySpark.

2. Filtering valid deliveries and aggregating key statistics.

3. Using window functions to calculate running totals and rankings.

4. Visualizing key trends like team performances, player rankings, and season-wise analysis.

# Future Enhancements

1. Advanced player performance predictions using machine learning.

2. Web-based dashboard for interactive data visualization.

3. More granular insights into bowling performances.

# Example Code Snippet
    from pyspark.sql import SparkSession
    from pyspark.sql.functions import col, sum, avg, row_number
    from pyspark.sql.window import Window

    # Initialize Spark Session
    spark = SparkSession.builder.appName("IPL Data Analysis").getOrCreate()

    # Load Dataset
    ipl_df = spark.read.csv("ipl_matches.csv", header=True, inferSchema=True)

    # Aggregation: Total and average runs per match
    aggregated_data = ipl_df.groupBy("match_id").agg(sum("total_runs").alias("Total Runs"), avg("total_runs").alias("Average Runs"))
    aggregated_data.show()

# Contributors

Sahil Shinde

# License

This project is licensed under the MIT License.

