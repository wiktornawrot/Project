# Executive Sales & Profitability Dashboard (BI Portfolio Project)

This repository contains a professional-grade, interactive Tableau dashboard designed to provide a comprehensive C-suite view of business performance. The project showcases skills in data modeling, advanced visualization, and user-centric dashboard design.

<img width="1517" height="853" alt="image" src="https://github.com/user-attachments/assets/c8707a1d-1bfd-4e26-8123-6647efd721c2" />


## 🎯 Project Objective & Business Requirements

The primary objective was to deliver a "single source of truth" for the executive team at a national retail company. The business requirement was to move beyond static spreadsheets and create a dynamic, self-service tool to answer critical business questions.

The key requirements from leadership were:

* **Top-Line Monitoring:** "I need to see our core KPIs: **Total Sales**, **Total Profit**, and **Gross Margin**"
* **Performance Context:** "I don't just want to see the number; I need to know if it's good or bad. Show me how we're trending monthly and **compare it directly to last year (YoY)**."
* **Driver Analysis:** "When I see a spike or a dip in profit, I need to know *why*. Give me an easy way to see which **products, categories, customer segments, and regions** are responsible."
* **Metric Flexibility:** "Our focus shifts between growth (Sales) and efficiency (Profit). I want to be able to toggle the entire detailed analysis between these two metrics with **a single click**."
* **Interactivity:** "If I see 'Bookcases' are underperforming, I want to click on it and see its specific impact on our total profit, margin, and regional performance instantly."

## 🛠️ Methodology & Technical Implementation

The dashboard was built in Tableau Desktop, following a structured process from data preparation to final deployment.

### 1. Data Preparation & Modeling (ETL)

**Data Source:** This project utilizes the well-known **Sample - Superstore** dataset, which is bundled with Tableau. This dataset effectively models the complex sales operations of a typical retail enterprise, making it ideal for building a comprehensive business dashboard.

Before visualization, the data required significant preparation to support the dashboard's complex features.
* **Data Cleaning:** Connected to the source data, hiding all non-essential columns (e.g., row IDs, redundant fields) to optimize workbook performance and streamline the development process.
* **Custom Functions (Calculated Fields):**
    * **YoY Performance:** Created robust table calculations to compute the Year-over-Year (YoY) variance in both value ($) and percentage (%).
    * **Core KPIs:** Developed foundational calculations for `Gross Margin %` and other key metrics.
* **Parameter Implementation:**
    * **Date Control:** Implemented a `Select Year` **Parameter** (e.g., 2023, 2024, 2025). This parameter is the foundation for all time-based analysis. It dynamically drives the 'current year' view for all charts and serves as the essential base for all 'Previous Year' and 'YoY %' calculations, ensuring the entire dashboard updates from one central control.
    * **Metric Selection:** Created a core **Parameter** named `Select Metric`. This allows the user to dynamically switch the measures displayed in the "Sales by category & sub-category" and "Sales by segment & region" charts, toggling them between `SUM(Sales)` and `SUM(Profit)`. This is governed by a `CASE` statement calculation.
### 2. Visualization & Dashboard Design

Each visualization was chosen purposefully to answer a specific business question in the most effective way.

* **KPIs (Line Charts):**
    * **Why:** A **Line Chart** is the most effective way to visualize a continuous trend over time (months).
    * **Impact:** It clearly displays seasonality, monthly performance, and the relationship between the current year (2024) and the previous year (2023).

* **Sales by category & sub-category (Bar Chart):**
    * **Why:** A horizontal **Bar Chart** is ideal for comparing the performance of numerous nominal categories, as the labels are easy to read.
    * **Enhancement:** An **Average Reference Line** was added. This simple addition instantly segments all sub-categories into "above average" and "below average" performers, allowing for immediate identification of outliers (both positive and negative).

* **Sales by segment & region (Slope Charts):**
    * **Why:** Instead of a complex multi-line chart, a grid of **Slope Charts** (small multiples) was used.
    * **Impact:** This design is exceptionally effective at comparing the change between two points in time (2023 vs. 2024) across multiple categories simultaneously. A user can instantly scan all four regions and three segments to see where growth was strongest (steepest upward slope) or where performance declined.

### 3. UI/UX & Design Principles

A clean and intuitive interface is critical for user adoption.

* **De-cluttering:** All non-essential visual elements, such as excessive gridlines, borders, and redundant labels, were removed. This maximizes the "data-ink ratio" and directs the user's focus to the data itself.
* **Strategic Color Use:** Color is used with intent and precision, not for decoration, to guide the user's attention.
    * **Primary Theme:** A neutral, professional **blue** is used as the primary color for all current-year data and standard visualizations. This creates a clean, consistent, and highly visible theme.
    * **Contextual Data:** The previous year's data (on the KPI line charts) is shown in a **faded, light blue**. This makes it clearly visible for comparison but ensures it does not visually compete with the current year's data, which is the primary focus.
    * **Performance (KPIs):** In the bar chart, a diverging palette is used to highlight performance against the average. **Red** and **Green** are used sparingly *only* to draw attention to the most significant outliers (e.g., "Bookcases" at -31.4% or "Supplies" at 631.3%). All other bars are colored with gray to show their value without distracting the user, preventing a confusing "rainbow" effect.
    * **Categorical:** In the "Sales by segment & region" chart, color is used specifically to encode the **Customer Segment** (Consumer, Corporate, Home Office). This consistent use of color allows the user to easily track and compare a *specific segment* (e.g., "Corporate") across all four different regions.
* **Interactivity (Dashboard Actions):** **Filter Actions** are enabled on the detail charts. This transforms the dashboard from a static report into a true analytical tool. Clicking on "Chairs" filters all other charts—including the top-line KPIs—to show data *only* for that sub-category, facilitating a powerful drill-down analysis.

## 📊 Final Result

The final product is a high-performance, fully interactive dashboard that serves as a central hub for business analysis. It empowers executives and managers to move from "what" happened to "why" it happened, enabling faster, data-driven decision-making.

### 🔗 Interactive Dashboard

**Interact with the live dashboard on Tableau Public:**

https://public.tableau.com/app/profile/wiktor.nawrot/viz/Salesinteractivedashboard/Salesdashboards
