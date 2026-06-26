## EmporiUm Regional Sales Analysis - Maryland & Maine

Author: Onur Karaer
Course: Year Up United - Data Analytics Training Academy (Week 12 Capstone: Power BI)


## Project Overview

This project analyzes four years of sales data (2022-2025) for EmporiUm, a virtual student bookstore. The Power BI report focuses on the store (in-person) performance of two assigned territories - Maryland and Maine - comparing them to surface insights and recommendations for the regional sales team. Online sales are handled by a separate team and are kept out of the territory analysis.


## Data Sources


Capstone3_Sample_Sales.xlsx - Store Sales, Online Sales, Products, Store Locations, Management Team, and Shipper List sheets.
book_list.txt - Titles and authors for general-audience (non-textbook) books.



## Data Cleaning & Modeling

The two transaction sheets were combined into a single Sales table, and supporting tables were cleaned and reshaped in Power Query.

Combining the sales data


Added a Store ID value of "Online" to the Online Sales rows so they could be distinguished from physical store rows after combining.
Combined the separate Year / Month / Day columns in Online Sales into a single Transaction Date field.
Appended Store Sales and Online Sales into one Sales table. Store rows carry a State (the store's location); online rows carry a Ship-to State (the delivery destination). These are kept as two separate columns so the two concepts are never mixed - territory analysis uses State and excludes online rows.


Cleaning the supporting tables


Store Details: built from Store Locations, standardizing inconsistent state abbreviations (e.g. "ME" → "Maine") so merges would match, then merging in Store Manager, Region, and Regional Director from the Management Team sheet.
Management Team: split the single sheet into three clean reference tables - Region→Director, State→Manager, and State→Region - and joined them into Store Details.
Products: extracted author names from book_list.txt (parsing the "Title by Author" text) and merged them in, so general books carry an author while textbooks and other items do not.


Modeling


The Sales table connects to Products (Prod Num), Store Details (Store ID), Shipper List (Ship-to State), and a dedicated DateTable (Transaction Date) marked as the official date table.
Measures were written as needed for sales by state, average order value, year-over-year growth, and transaction counts - all scoped to store sales for the territory analysis.


## Tools Used

- **Power BI Desktop** - data modeling, DAX measures, and report design
- **Power Query** - data cleaning and transformation
- **Power BI Service** - online publishing
- **GitHub** - version control

---

## Links

- **Video Presentation:** https://yearuptemp-my.sharepoint.com/:v:/g/personal/okaraer_my_yearupunited_org/IQADvjlEFW2gRp7ER7AXvkYTAbmj2yKab26_yOBJ1kyar0k?e=DZqFnA
- **Published Power BI Report:** https://app.powerbi.com/links/r-1TAmSNKH?ctid=bbce5c37-f181-4d0c-9310-7f877336e1cf&pbi_source=linkShare&bookmarkGuid=de6b64a4-1588-4d59-833f-886b4aff6130

---

## Repository Contents

- `Karaer_Capstone_3.pbix` - Power BI report file
- `Capstone3_Sample_Sales.xlsx` - source sales data
- `book_list.txt` - source book/author list
- `README.md` - this file
