# Katsu Zushi Business Management System

An integrated F&B business management skill for WorkBuddy AI, designed for **Katsu Zushi** (Japanese sushi restaurant).

## Features

### 1. Automatic Inventory Calculation
- Recipe-based ingredient deduction from daily sales
- Unit conversion across different pack sizes (g, ml, pieces)
- FEFO (First Expiry First Out) stock rotation
- Real-time stock balance tracking

### 2. Food Expiry Date Prediction & Warning
- Batch-level expiry tracking with estimated dates
- Shelf-life reference data integration
- 7-day and 1-day warning thresholds
- Expired stock flagging for review

### 3. Supplier Price Comparison
- Fair comparable unit-price calculation (price per g/ml/piece)
- Cheapest supplier auto-identification per ingredient
- Historical price tracking across all suppliers
- Savings potential calculation

### 4. Financial Reports & Net Profit
- COGS calculation using weighted average cost method
- Gross profit, operating profit, and net profit
- Expense tracking across 9 categories
- Menu item profitability ranking
- Period comparison (weekly/monthly/annual)

## Project Structure

```
business-solution/
├── SKILL.md                      # Skill definition and workflow documentation
├── business-solution.skill       # Skill manifest (packaged)
├── scripts/                      # Python scripts for all operations
│   ├── katsu_db.py               # Core database layer (JSON storage, CRUD, transactions)
│   ├── inventory_manager.py      # Inventory calculations, PO processing, sales deduction
│   ├── expiry_manager.py         # Batch tracking, expiry calculation, FEFO, warnings
│   ├── supplier_manager.py       # Supplier price records, comparison, savings
│   ├── financial_manager.py      # Financial reports, expenses, profit calculations
│   └── load_menu_data.py         # Menu data initialization helper
├── data/                         # Persistent JSON data storage
│   ├── config.json               # Business configuration
│   ├── recipes.json              # Menu items and ingredient quantities
│   ├── ingredients.json          # Ingredient definitions (48 ingredients)
│   ├── inventory.json            # Current stock balances
│   ├── batches.json              # Purchase batches with expiry info (50 batches)
│   ├── suppliers.json            # Supplier details and price records (3 suppliers, 50 records)
│   ├── sales.json                # Daily sales records
│   ├── transactions.json         # All inventory movements (84 transactions)
│   ├── expenses.json             # Business expense records
│   ├── expiry_ref.json           # Shelf-life reference data
│   ├── write_offs.json           # Expired/spoiled stock write-offs
│   └── processed_files.json      # File hashes for duplicate prevention
└── references/                   # Documentation
    ├── data_model.md             # JSON data structures and schemas
    ├── formulas.md               # Complete calculation formulas with examples
    └── business_rules.md         # Business rules, unit rules, FEFO, accounting rules
```

## Current Data Summary

| Metric | Value |
|---|---|
| Total Ingredients | 48 |
| Suppliers | 3 (Global Provisions Inc, Sunrise Foods, Nippon Restaurant Supplies) |
| Price Records | 50 |
| Inventory Batches | 50 |
| Transactions Logged | 84 |
| Multi-Supplier Comparisons | 4 ingredients |

## Suppliers

| Supplier | Cheapest For |
|---|---|
| Nippon Restaurant Supplies | 16 ingredients |
| Sunrise Foods | 15 ingredients |
| Global Provisions Inc | 14 ingredients |

## Technology

- **Storage**: JSON file-based persistent storage
- **Language**: Python 3.13
- **Platform**: WorkBuddy AI
- 
## How to use ?
Download the .zip file and extract it
Then go to Tencent WorkBuddy AI and open skills
After that, go to Add Skill and choose Upload Project
From the .zip file choose SKILL.md file and there should be ready to use

## License

This project is part of the Jommarathon Group7 Dormathon hackathon submission.
