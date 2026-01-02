> Flexibility - is a control. Parameters empower users to scale analysis details in real time.

| Параметр | Функція (The Strategy) |
| :--- | :--- |
| `Select_Month` | **The Wayback Machine:** Defines period for MoM , YoY, PY & CY Methrics (Sales, Profit)|
| `Select_Region` | **Success Geo Radar:** Analyses Regional Performance & Trends |
| `Select_Segment` | **Success Human Radar:**  Catches Scalable & Profitable Audiences"|

---

## ⏳ 2. Time Intelligence
> **Pre-frame:** We performed granular historical segmentation. These fields is pre-configured Date pieces to calculate KPI's

### **Current and Past Periods** 
* **CD (Current Date)** - Reference point for metrics  
  
  ```tableau
  [Select_Month]
* **CM (Current Month)** - Extracted month from CD (Only for MoM related calculations)
  
  ```tableau
  MONTH([CD])
* **PM (Previous Month)** - Extracted previous month from CD (Only for MoM related calculations)
  
  ```tableau
  MONTH(DATEADD('month',-1,[CD]))
* **PMY (Previous Month Year)** - Extracted Year of Previous Month. If PM is January - year is shifts back
  
  ```tableau
   YEAR((DATEADD('month',-1,[CD])))
* **CY (Current Year)** - Extracted Current Year from CD
  
  ```tableau
  YEAR([CD])
* **PY (Previous Year)** - Extracted Previous Year from CD
  
  ```tableau
  YEAR([CD])-1

### **Sales & Profit Metrics** 

> This methrics calculate Year-to-Date (YTD) Sales since JAN (even you selected other month).

**The Sales Engines**
* `CY_Sales` - calculates CY Sales for products or categories
  
  ```tableau
  IF [YEAR] = [CY] THEN [Sales] END
* `PY_Sales` - calculates PY Sales for products or categories
  
  ```tableau
  ZN(IF [YEAR]=[PY] THEN [Sales] END)
**The Profit Engines**
* `CY_Profit` - calculates CY Profitability for products or categories
  
  ```tableau
  IF [YEAR] = [CY] THEN [Profit] END
* `PY_Profit` - calculates PY Profitability for products or categories
  
  ```tableau
  IF [YEAR]=[PY] THEN [Profit] END
### **Growth & Momentum** 

> Whether we are grow, or degrading? Methrics showes Month-over-Year (MoM) growth momentum and Year-over-Year (YoY) growth performance.

**Year over Year**
* `YoY_Profit (%)` - Profit Performance indicator
  
  ```tableau
  (SUM([CY_Profit])-SUM([PY_Profit]))/SUM([PY_Profit])
* `YoY_Sales (%)` -  Sales Performamce indicator
  
  ```tableau
  (SUM([CY_Sales])-SUM([PY_Sales]))/SUM([PY_Sales])
* `YoY_Sales_Arrow` or `YoY_Profit_Arrow` - Visual Triggers. These are Immediate Signal on growth (Blue/Green) versus decline (Red) trends
  
  * for Sales one
    
    ```tableau
     IF [YoY_Sales (%) ] > 0 THEN '▲' ELSE '▼' END
  * for Profit one
    
    ```tableau
    IF [YoY_Profit (%) ] > 0 THEN '▲' ELSE '▼' END
**Month over Month**
* `MoM_Profit (%)` - Profit Variance indicates on short-term tactic
  
  ```tableau
   ZN((SUM([CM_Profit])-SUM([PM_Profit]))/SUM([PM_Profit]))
* `MoM_Sales (%)` - Sales Variance indicates on short-term tactic

  ```tableau
   (SUM([CM_Sales])-SUM([PM_Sales]))/SUM([PM_Sales])
  ```







  
  
  


  

