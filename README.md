### **1. Overall Context**

* The image shows a **Power BI dashboard design interface**.
* It is likely part of an internship or project focused on **seasonal sales analysis**.
* The dashboard appears to be in the early stage, with a **home/index page** and navigation setup.

---

### **2. Top Menu Bar**

* Options available:

  * **Get Data** (Excel, SQL Server, Dataverse, etc.) → for connecting to datasets.
  * **Transform Data / Refresh** → for cleaning and updating data.
  * **Insert Tools** (New Visual, Text box, More visuals) → for adding charts and elements.
  * **Publish** → to share the report online.
* Indicates that the dashboard is in **edit mode** where visuals are being built.

---

### **3. Seasonal Buttons (SUMMER, WINTER, RAINY)**

* These look like **bookmark buttons** or **slicers**.
* Purpose: To filter or navigate to season-specific sales dashboards.
  Example:

  * *SUMMER* → Sales insights during summer campaigns.
  * *WINTER* → Discounts and revenue during the winter season.
  * *RAINY* → Seasonal trends in monsoon.

---

### **4. Central Visual**

* A colorful image with text **“Special Sale!”**.
* This acts as a **landing page highlight/logo**.
* Likely serves as a **visual cue for promotions** and seasonal offers.

---

### **5. Bottom Navigation Tabs**

* Tabs visible:

  * **Index (current tab)** → Acts as homepage with navigation.
  * **SUMMER, WINTER, RAINY** → Each tab probably has detailed dashboards.
  * **+** → Add a new report page.

This structure is similar to **website navigation** but inside Power BI.

---

### **6. Visualization Pane (Right Side)**

* Shows different chart options:

  * Bar, line, pie, scatter, waterfall, maps, funnel, etc.
* This suggests the report will include **multiple visualization styles** once data is added.

---

### **7. Filters & Drill-through (Bottom Right)**

* Drill-through: **OFF** (not enabled yet).
* Filters: Not applied yet.
* This means **no advanced filtering or drill-through** has been implemented at this stage.

---

### **Detailed Analysis**

* This is the **index/intro page** of a Power BI dashboard project.
* The **seasonal buttons** suggest a focus on **comparing sales across different seasons**.
* The **Special Sale logo** indicates the theme is related to **promotions and discounts**.
* Likely, the **sub-pages (SUMMER, WINTER, RAINY)** will contain actual visuals like bar charts, line graphs, and KPI indicators showing revenue, units sold, discounts, etc.
* Current stage = **Design layout setup**, not fully populated with data visuals.

## **1. Dashboard on Winter Season**

* **KPIs (Cards):**

  * Total Sales: **120.19K**
  * Total Profit: **26.24K**
  * Total Cost: **93.95K**

* **Visuals:**

  * **Pie Chart (Sales by Segment):**

    * Consumer: 34.12%
    * Corporate: 32.82%
    * Home Office: 33.06%
  * **Bar Chart (Sales by City):** Top cities are **New Delhi, Kolkata, Coimbatore, Mumbai, Chennai**.
  * **Sales by Ship Mode:** Sales distributed across **First Class, Same Day, Second Class, Standard Class** (almost equal).
  * **Sales by Day:** Sales are fluctuating, with peaks around mid and end of the month.
  * **Sales by State:** Maharashtra, Karnataka, Tamil Nadu, West Bengal dominate.
  * **Sales by Sub-Category:** High sales in **Phones, Chairs, Storage** categories.

---

## **2. Dashboard on Summer Season**

* **KPIs (Cards):**

  * Total Sales: **120.19K**
  * Total Profit: **26.24K**
  * Total Cost: **93.95K**

* **Visuals (almost identical to Winter):**

  * **Pie Chart (Sales by Segment):** Similar distribution as Winter (Consumer slightly higher).
  * **Sales by City:** Same cities dominate (**New Delhi, Kolkata, Coimbatore, Mumbai**).
  * **Sales by Ship Mode:** Even spread across all shipping classes.
  * **Sales by Day:** Noticeable peaks in mid-month and slight dip at end.
  * **Sales by State:** Maharashtra, Karnataka, Tamil Nadu, West Bengal again are top.
  * **Sales by Sub-Category:** Phones, Chairs, Storage still top-selling.

📌 Insight: *Summer and Winter dashboards look nearly identical in values and structure – meaning sales remain consistent across these seasons.*

---

## **3. Dashboard on Rainy Season**

* **KPIs (Cards):**

  * Total Sales: **21.85K**
  * Total Profit: **4.37K**
  * Total Cost: **17.49K**

* **Visuals:**

  * **Pie Chart (Sales by Segment):**

    * Corporate: 42.34% (largest share)
    * Home Office: 31.13%
    * Consumer: 26.53%
  * **Sales by City:** Only **Coimbatore and Chennai** are significant contributors.
  * **Sales by Ship Mode:** Equal distribution across all modes.
  * **Sales by Day:** Lower sales volume with spikes towards end of month.
  * **Sales by State:** Only **Tamil Nadu** is visible → means sales are concentrated in one state.
  * **Sales by Sub-Category:** Phones, Chairs, and Accessories dominate.

📌 Insight: *Rainy season has **much lower sales and profit** compared to Summer/Winter. Business activity is concentrated in Tamil Nadu, mainly in Coimbatore and Chennai.*

---

## **Overall Comparison**

* **High Sales & Profit:** Summer and Winter (both \~120K sales, \~26K profit).
* **Low Sales & Profit:** Rainy Season (\~21K sales, \~4.3K profit).
* **Geographical Spread:**

  * Summer & Winter → Pan-India (Delhi, Kolkata, Mumbai, Chennai, Bangalore, etc.).
  * Rainy → Mainly Tamil Nadu.
* **Segment Distribution:**

  * Summer/Winter → Balanced across Consumer, Corporate, Home Office.
  * Rainy → Corporate dominates.
* **Key Categories:** Phones, Chairs, and Storage consistently drive sales.

---

## **DAX Calculations for KPIs**

Here are the likely DAX formulas used:

```DAX
-- Total Sales
Total_Sales = SUM(Sales[SalesAmount])

-- Total Profit
Total_Profit = SUM(Sales[Profit])

-- Total Cost
Total_Cost = SUM(Sales[Cost])

-- Sales by Segment
Sales_By_Segment = CALCULATE(SUM(Sales[SalesAmount]), Sales[Segment])

-- Sales by City
Sales_By_City = CALCULATE(SUM(Sales[SalesAmount]), Sales[City])

-- Sales by State
Sales_By_State = CALCULATE(SUM(Sales[SalesAmount]), Sales[State])

-- Sales by Ship Mode
Sales_By_ShipMode = CALCULATE(SUM(Sales[SalesAmount]), Sales[ShipMode])

-- Sales by Sub-Category
Sales_By_SubCategory = CALCULATE(SUM(Sales[SalesAmount]), Sales[SubCategory])

-- Sales by Day
Sales_By_Day = CALCULATE(SUM(Sales[SalesAmount]), Sales[Day])
```

If profitability needs to be calculated:

```DAX
Profit = SUM(Sales[SalesAmount]) - SUM(Sales[Cost])
``
✅ In summary:

* **Summer & Winter:** High and stable performance.
* **Rainy:** Low sales, profit, and geographic reach.
* **DAX:** Standard SUM and CALCULATE measures across dimensions like Segment, City, State, Ship Mode, Sub-Category, Day.
