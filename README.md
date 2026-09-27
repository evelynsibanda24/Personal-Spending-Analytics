# Personal Spending Analytics & Transaction Categorization

## Project Overview

This Power BI project analyzes transaction data derived from a personal bank statement to uncover spending patterns, identify major expenditure categories and examine changes in spending over time.

The original PDF statement required extensive cleaning and restructuring in Power Query before it could be analyzed. DAX was then used to support transaction categorization and analysis, with the results presented through an interactive Power BI dashboard.

To protect financial privacy, sensitive banking information and the original bank statement are not included in this public repository.

## Problem Statement

Although the PDF bank statement was visually well structured, its layout did not translate cleanly when extracted for analysis. Transaction records became fragmented across rows and columns, while transaction descriptions required further processing and categorization before meaningful spending analysis could be performed.

This project aims to transform raw banking transaction data into an analytical dataset and use it to understand spending behaviour, identify the major drivers of expenditure, and examine how spending changes over time.

## Analysis Objectives

The analysis seeks to answer the following questions:

- Which spending categories account for the largest share of expenditure?
- How does spending change from month to month?
- Which individual purchases have the greatest impact on total spending?
- How many transactions occur during the period, and what does this reveal about transaction activity?
- What broader spending patterns can be identified after separating actual expenditure from transfers and income?
 

 ## Data Preparation & Transformation

The bank statement PDF was imported into Power Query, where the extracted data required significant restructuring before analysis.

Key transformation steps included:

- Combined transaction data extracted across multiple PDF pages into a single table.
- Removed repeated headers and non-transaction rows created during PDF extraction.
- Standardized column names and assigned appropriate data types.
- Filled down transaction dates where PDF extraction had separated dates from their corresponding transaction details.
- Reconstructed fragmented transactions so that each transaction was represented by a single row.
- Consolidated transaction description fragments into a complete `Transaction Details` field.
- Extracted transaction time from the transaction descriptions and created a separate `Time` field.
- Cleaned and validated the Debit, Credit, and Balance fields for analysis.
- Produced a final structured dataset containing **448 transaction records** with Date, Time, Transaction Details, Debit, Credit, and Balance fields.

## Transaction Categorization & DAX

After the transaction data was cleaned and structured, DAX was used to create a `Spending Category` calculated column based on keywords found within the 
transaction descriptions.
Transactions were classified into meaningful analytical categories including:

- Food & Dining
- Shopping
- Transport
- Hotels
- Education / Fees
- Transfers
- Income

Transfers and income were retained in the underlying dataset but excluded from spending-focused visuals where appropriate. This prevented movements of money 
between accounts and incoming funds from being interpreted as actual expenditure.
The categorization transformed unstructured merchant and transaction descriptions into groups that could be used to analyze spending patterns across the dataset.

## Power BI Dashboard & Analysis

An interactive Power BI dashboard was developed to present the cleaned and categorized transaction data and answer the key analytical questions defined for the project.

The dashboard includes:

- **Total Credits** – summarizes incoming funds during the analyzed period.
- **Total Debits** – summarizes outgoing transaction amounts.
- **Total Transactions** – shows the overall volume of transaction activity.
- **Largest Purchase** – identifies the highest individual purchase after excluding transfers and income.
- **Spending by Category** – compares expenditure across major spending categories.
- **Monthly Spending Trend** – shows how actual expenditure changes over time.

Transfers and income were excluded from spending-focused visuals to provide a clearer view of actual expenditure.
