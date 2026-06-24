 📊 DecodeLabs Data Analytics Internship Projects

Intern: Lordson Uchechukwu Godcares
Organization: DecodeLabs
Tools Used: Microsoft Excel · SQL Server · Power BI

---

 🗂️ Table of Contents

- [Project 1 – Data Cleaning & Preparation (Excel)](#project-1--data-cleaning--preparation-excel)
- [Project 2 – Sales Analysis Dashboard (Excel/Power BI)](#project-2--sales-analysis-dashboard-excelpower-bi)
- [Project 3 – SQL Data Cleaning & Quality Checks](#project-3--sql-data-cleaning--quality-checks)
- [Project 4 – Interactive Sales Dashboard (Power BI)](#project-4--interactive-sales-dashboard-power-bi)

---

Project 1 – Data Cleaning & Preparation (Excel)

Tool: Microsoft Excel

Overview
Raw sales transaction data for Lordson's store was imported into Excel and cleaned to prepare it for analysis. The dataset contained 1,200 rows covering orders from 2023–2025 across multiple product categories.

Dataset Columns
`OrderID` · `Date` · `CustomerID` · `Product` · `Quantity` · `UnitPrice` · `ShippingAddress` · `PaymentMethod` · `OrderStatus` · `TrackingNumber` · `ItemsInCart` · `CouponCode` · `ReferralSource` · `TotalPrice`

Key Cleaning Steps
- Standardized date formats across the `Date` column
- Replaced blank and empty `CouponCode` values with `"NO COUPON"` for consistency
- Removed duplicate and inconsistent entries
- Ensured numeric columns (`UnitPrice`, `TotalPrice`) were correctly formatted
- Sorted and filtered data for downstream dashboard use


Project 2 – Sales Analysis Dashboard (Excel)

Tool: Microsoft Excel (Pivot Charts + Dashboard Layout)

 Overview
Built a comprehensive sales analysis dashboard titled "Lordson's Sales Analysis Dashboard (DecodeLab Internship Project)" directly in Excel using pivot tables and charts.

Dashboard KPIs
| Metric | Value |
| Total Revenue | ₦1,264,762 |
| Total Quantity in Cart | 6,582 |
| Total Quantity Ordered | 3,535 |
Visualizations Included
- Quantity Sold by Coupon Code– No Coupon (941) led, followed by FREESHIP (914), SAVE10 (844), WINTER15 (836)
- Revenue per Product – Chair and Printer tied at ~₦196K, Phone lowest at ₦152K
- Order Status of Goods Sold – Cancelled (759) was highest; Shipped (680) lowest
- Number of Products Sold per Referral Source – Instagram led (770), Referral lowest (631)
- Revenue per Product (by Referral Source) – Instagram generated ₦275,285
- Revenue per Year– ₦552,643 (2023) → ₦480,236 (2024) → ₦231,883 (2025)
- Most Ordered Product – Chair (562), Phone (411)
  Order by Year– 510 (2023) → 459 (2024) → 231 (2025)
- Slicer filters for Referral Source, Coupon Code, Payment Method, and Product


Project 3 – SQL Data Cleaning & Quality Checks

Tool: SQL Server (Database: `Decodelabs`)
 Overview
Performed structured data cleaning and validation on the `[Dataset for Data Analytics (5)]` table using T-SQL queries across multiple stages.
 Cleaning Operations Performed
 1. Rounding Numeric Columns
UPDATE [Dataset for Data Analytics (5)]
SET UnitPrice = ROUND(UnitPrice, 2),
    TotalPrice = ROUND(TotalPrice, 2);
2. Standardizing CouponCode Nulls and Blanks
UPDATE [Dataset for Data Analytics (5)]
SET CouponCode = 'No coupon'
WHERE CouponCode = ' ' OR CouponCode IS NULL;
3. Trimming Whitespace from Text Columns
UPDATE [Dataset for Data Analytics (5)]
SET product = TRIM(product),
    ShippingAddress = TRIM(shippingaddress),
    PaymentMethod = TRIM(paymentmethod),
    OrderStatus = TRIM(orderstatus),
    ReferralSource = TRIM(referralsource);
 4. Checking the Date Column Data Type
SELECT date, SQL_VARIANT_PROPERTY(date, 'basetype') AS datatype
FROM [Dataset for Data Analytics (5)];
5. Identifying Duplicate OrderIDs
SELECT OrderID, COUNT(*) AS count
FROM [Dataset for Data Analytics (5)]
GROUP BY OrderID
HAVING COUNT(*) > 1;
 6. Checking for Negative Prices
SELECT 'negative prices', COUNT(*)
FROM [Dataset for Data Analytics (5)]
WHERE UnitPrice < 0 OR TotalPrice < 0;
 7. Final Data Preview
SELECT *
FROM [Dataset for Data Analytics (5)];

Query Outcome
- ✅ Query executed successfully — 1,200 rows returned
- ✅ No issues found (confirmed in editor status bar)


Project 4 – Interactive Sales Dashboard (Power BI)

Tool: Power BI

Overview
Developed a polished, interactive **Lordson's Sales Analysis Dashboard** in Power BI as the final deliverable of the DecodeLabs internship. The dashboard presents a full summary of sales performance across products, referral channels, payment methods, and time periods.

Dashboard KPIs
| Metric | Value |

| Total Revenue | ₦1.26M |
| Total Quantity Ordered | 4K |
| Total Customers | 1.2K |

Visualizations Included

 Chart | Insight 
| Revenue per Product | Chair & Printer led at ₦196K each; Phone lowest at ₦152K |
| Quantity Sold by Referral Source | Instagram (259) > Email (250) > Google (241) > Facebook (228) > Referral (222) |
| Quantity Sold by Coupon Code | FREESHIP (313) > No Coupon (309) > WINTER15 (292) > SAVE10 (286) |
| Quantity Sold by Payment Method | Online (258) > Cash (246) > Credit Card (234) > Debit Card (232) > Gift Card (230) |
| Total Revenue by Year (Line Chart) | ₦552.64K (2023) → ₦480.24K (2024) → ₦231.88K (2025) |
| Number of Products Sold (Bar Chart) | Chair (562) most sold; Phone (411) least sold |
| Quantity Sold by Year (Line Chart) | 510 (2023) → 459 (2024) → 231 (2025) — declining trend |

 Key Insights
- Revenue and order volume show a consistent year-on-year decline from 2023 to 2025, signalling a need for renewed marketing or customer retention strategies.
- Instagram is the top-performing referral source across both revenue and quantity metrics.
- Chair is the best-selling product by both revenue and quantity sold.
- Payment method distribution is nearly equal, suggesting customers have no strong preference — all channels should be maintained.
- FREESHIP coupon drives the highest quantity of purchases, indicating price sensitivity among buyers.

📁 Repository Structure
├── Project1_Excel_DataCleaning/
│   └── Lordson_Sales_Dataset_Cleaned.xlsx
├── Project2_Excel_Dashboard/
│   └── Lordson_Sales_Dashboard.xlsx
├── Project3_SQL_Cleaning/
│   └── SQLQuery3_DataCleaning.sql
├── Project4_PowerBI_Dashboard/
│   └── Lordson_Sales_Dashboard.pbix
└── README.md


About
This repository documents the end-to-end data analytics workflow completed during the DecodeLabs Internship, covering data cleaning in Excel and SQL, exploratory data validation, and business intelligence dashboarding in Power BI.
- 🔗 LinkedIn: [Uchechukwu Lordson](https://www.linkedin.com/in/uchechukwu-lordson-1b2a5531a)
- 📸 Instagram: [@themanlordson](https://instagram.com/themanlordson)
