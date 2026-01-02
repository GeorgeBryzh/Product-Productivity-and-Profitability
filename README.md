> Гнучкість — це контроль. Параметри дозволяють користувачу миттєво змінювати перспективу аналізу, не перевантажуючи інтерфейс.

| Параметр | Функція (The Strategy) |
| :--- | :--- |
| `Select_Month` | **The Wayback Machine:** Defines period for MoM , YoY, PY & CY Methrics (Sales, Profit)|
| `Select_Region` | **Success Geo Radar:** Analyses Regional Performance & Trends |
| `Select_Segment` | **Success Human Radar:**  Catches Scalable & Profitable Audiences"|

---

## ⏳ 2. Тимчасові фільтри (Time Intelligence)
> **Pre-frame:** Щоб зрозуміти майбутнє, треба чітко сегментувати минуле. Ці поля створюють логічні "контейнери" для порівняння періодів.

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
   YE
* **CY (Current Year)** - Extracted Current Year from CD
  
  ```tableau
  YEAR([CD])
* **PY (Previous Year)** - Extracted Previous Year from CD
  
  ```tableau
  YEAR([CD])-1

### **Sales & Profit Metrics** 

> **Fixed**This methrics calculate Fixed Year-to-Date (YTD) Sales since JAN (even you selected other month).

**The Sales Engines**
* `CY_Sales` - calculates CY Sales for products or categories
  ```tableau
* `PY_Sales` - calculates PY Sales for products or categories
  ```tableau
**The Profit Engines**
* `CY_Profit` - calculates CY Profitability for products or categories
  ```tableau
  [Select_Month]
* `PY_Profit` - calculates PY Profitability for products or categories
  
### **Growth & Momentum** 

> Whether we are grow, or degrading? Methrics showes Month-over-Year (MoM) growth momentum and Year-over-Year (YoY) growth performance.

**Year over Year**
* `YoY_Profit %` - Profit Performance indicator
  ```tableau
* `YoY_Sales %` -  Sales Performamce indicator
  ```tableau
* 'YoY_Sales_Arrow %' or `YoY_Profit_Arrow %` or - Visual Triggers. These are immediate Signal on growth (Blue/Green) versus decline (Red) trends
  ```tableau


  
  
  


  

