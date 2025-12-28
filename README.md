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
* **PMY (Previous Month Year)** - Extracted Year of previous month. If PM is January - Year 
  
  ```tableau
  
* **CY (Current Year)** - Extracted Current Year from CD
  
  ```tableau
  YEAR([CD])
* **PY (Previous Year)** - Extracted Previous Year from CD
  
  ```tableau
  YEAR([CD])-1

  

