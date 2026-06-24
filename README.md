# EmporiUm Regional Sales Analysis - Maryland & Maine

**Author:** Onur Karaer
**Course:** Year Up United - Data Analytics Training Academy (Week 12 Capstone: Power BI)

---

## Project Overview

This project analyzes four years of sales data (2022–2025) for **EmporiUm**, a virtual student bookstore with both in-store and online sales. The Power BI report focuses on two assigned territories - **Maryland** and **Maine** - comparing their performance to surface insights and recommendations for the regional sales team.

---

## Data Sources

- **Capstone3_Sample_Sales.xlsx** - Store Sales, Online Sales, Products, Inventory Categories, Store Locations, Management Team, and Shipper List sheets.
- **book_list.txt** - Titles and authors for general-audience (non-textbook) books.

---

## Data Cleaning & Modeling

Key transformation steps performed in Power Query:

- **Store Sales:** removed error rows (`#N/A`) and standardized the category column, merging "General" into "Books (General)".
- **Online Sales:** combined separate Year/Month/Day columns into a single date field; renamed columns to align with Store Sales.
- **Store Locations:** replaced inconsistent state abbreviations (CT, ME, NY, MA) with full state names to prevent duplicate states in visuals.
- **Inventory Categories:** corrected misread header row.
- **Book List:** extracted author names from the raw text and merged the list into the Products table to attach authors to general books.

The data model connects Store Sales and Online Sales to Products and Store Locations, with a dedicated Date table supporting all time-based analysis. Measures were created for total sales by state, average order value, year-over-year growth, and transaction counts.

---

## Tools Used

- **Power BI Desktop** - data modeling, DAX measures, and report design
- **Power Query** - data cleaning and transformation
- **Power BI Service** - online publishing
- **GitHub** - version control

---

## Links

- **Video Presentation:** _[Add your recording link here]_
- **Published Power BI Report:** _[Add your Power BI Service link here]_

---

## Repository Contents

- `Karaer_capstone3.pbix` - Power BI report file
- `Capstone3_Sample_Sales.xlsx` - source sales data
- `book_list.txt` - source book/author list
- `README.md` - this file
