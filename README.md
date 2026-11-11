# Supply Chain Analysis & Performance Report

This project analyzes a dataset of 100 products to identify supplier performance patterns, product inspection failure rates, inventory shortages, and regional analytics.

---

## 🛠️ Python Libraries Used

- **Pandas:** For loading (`read_csv`), exploring (`info`, `describe`), cleaning, aggregating (`groupby`), and merging (`merge`) dataset columns.
- **NumPy:** Used for fast vectorized numerical operations, such as rounding percentages (`np.round`).
- **Seaborn:** For high-level, aesthetic bar plots (`sns.barplot`) with custom palettes to visualize categorical relationships.
- **Matplotlib:** Used for customizing the figure layout, setting plot dimensions (`plt.subplots`), labeling graphs, and rendering the visualizations.

---

## 📈 Analysis Methods

1. **Data Exploration & Auditing:** Audited dataset dimensions, checked for missing values (`isnull().sum()`), and verified duplicates (`duplicated()`).
2. **Quality Risk Evaluation:** Filtered products with failed inspection results, combined them with total supplier counts via pandas database-style joins, and calculated defect ratios per supplier.
3. **Inventory Gap Analysis:** Programmatically identified items where current stock levels exceeded active availability (`Stock levels - Availability > 0`).
4. **Reorder Sufficiency Testing:** Calculated projected inventory after a standard shipment (`Availability + Order quantities`) and used conditional evaluation to flag items that still fall short of safe stock levels.
5. **Dynamic Plot Labeling:** Programmatically iterated over plotting containers (`ax.containers`) to dynamically overlay values directly on top of charts.

---

## 📊 Key Analytics & Results

### 1. Supplier Breakdown
- **Total Unique Suppliers:** 5
- **Top Supplier:** **Supplier 1** provides **27%** of all products in the inventory.

### 2. Quality Control & Inspection Failures
- **Total Defects:** 36 products failed inspection (a **36% overall failure rate**).
- **Highest Risk:** **Supplier 4** has an alarming **66.67% failure rate** (12 out of 18 supplied items failed inspection).
- **Best Performer:** **Supplier 3** maintains the lowest failure rate at **20.00%**.

### 3. Inventory Shortages
- **Products Below Stock Levels:** **51 products** currently have stock levels below their actual availability.
  - *Haircare:* 19 items
  - *Skincare:* 17 items
  - *Cosmetics:* 15 items
- **One-time Order Sufficiency:** For **21 products**, a single standard order is **not enough** to bring inventory back to safe stock levels. 
  - *Cosmetics* is the most critical department, making up **10 of these 21 severely depleted items**.

### 4. Financials & Regional Distribution
- **Revenue King:** **Skincare** generated the highest total revenue of **$241,628**, followed by Haircare ($174,455) and Cosmetics ($161,521).
- **Regional Lead:** **Kolkata** is the top distribution hub, managing **25%** of all items in the supply chain.
