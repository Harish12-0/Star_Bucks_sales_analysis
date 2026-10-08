# Star_Bucks_sales_analysis
Developed an interactive Starbucks Beverage Analytics Dashboard using Power BI. Cleaned and transformed data with Power Query and created DAX measures to analyze calories, sugar, caffeine, and beverage categories. Built KPIs and interactive visuals to identify product trends and generate insights for product development, customer segmentation

GitHub README — Short Professional Description

You can put this at the top of your repository:

Starbucks Beverage Analytics Dashboard | Power BI

An interactive Power BI dashboard developed to analyze beverage-level nutritional and product data. The project focuses on calories, sugar, caffeine, beverage categories, and product distribution to generate meaningful business insights.

The dashboard uses Power Query for data cleaning and transformation, DAX for KPI calculations and analytical measures, and Power BI for interactive visualization and reporting.

The analysis helps identify high-calorie and high-caffeine beverage categories, understand portfolio distribution, compare nutritional characteristics, and support data-driven decisions related to product development, marketing, customer segmentation, and menu optimization.

15. Resume Project Description

For your Data Analyst resume, I would write it like this:

Starbucks Beverage Analytics Dashboard | Power BI

* Developed an interactive Power BI dashboard to analyze 33 beverage products across calories, sugar, caffeine, protein, and beverage categories.
* Cleaned and transformed raw data using Power Query and created analytical measures using DAX.
* Built KPI cards, category comparisons, distribution charts, and Top 5 beverage analysis to identify key nutritional and product-level patterns.
* Identified significant differences in calorie and caffeine levels across beverage categories.
* Generated business insights supporting product development, customer segmentation, marketing strategy, and menu optimization.
* Designed a clean, business-focused dashboard with interactive filters for easier data exploration and decision-making.

⭐ One improvement I’d recommend

For your GitHub project, don’t stop at “I created this beautiful dashboard.”

Your strongest Data Analyst presentation is:

Data → Analysis → Insight → Business Recommendation

DAX FORMULAS



Total Beverages =
COUNTROWS('Beverages')



Average Calories =
AVERAGE('Beverages'[Calories])



Average Sugar =
AVERAGE('Beverages'[Sugar])



Average Caffeine =
AVERAGE('Beverages'[Caffeine])






col_chart =
VAR avgP =
    CALCULATE(
        [total Beverages],
        ALLSELECTED()
    )
VAR avgD =
    CALCULATE(
        [avg_caffeine],
        ALLSELECTED()
    )
RETURN
    SWITCH(
        TRUE(),
        [total Beverages] >= avgP && [avg_caffeine] < avgD, "#324032",
        [total Beverages] >= avgP && [avg_caffeine] >= avgD, "#475749",
        [total Beverages] < avgP && [avg_caffeine] < avgD, "#FAF9F4",
        [total Beverages] < avgP && [avg_caffeine] >= avgD, "#F5F4EE",
        "#FFFFFF"
    )
