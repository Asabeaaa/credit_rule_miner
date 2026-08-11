# Association Rule Mining for Loan Default Risk Patterns

## Overview
This project uses association rule mining to uncover patterns in loan client data that are linked to different levels of repayment risk. Rather than predicting a single risk score for each client, the goal is to surface human-readable "if this combination, then that risk level" rules, patterns that can support underwriting decisions and a general understanding of what tends to co-occur with risky loans.

## The Idea
Each data instance is treated as a basket made up of attributes: income level, employment status, debt-to-income ratio, loan size, tenor and so on. Association rule mining (FP-Growth) looks across all clients to find which combinations of these attributes tend to appear together more often than chance.

The outcome (how long a client has gone into arrears) is included as just another attribute in each basket, binned into risk levels: no arrears, low, medium, high, and critical risk. This lets the mining process surface which attribute combinations are associated with which severity of risk, for example:

`{self-employed, high debt-to-income, new client} → {high risk}`

## Why Association Rules (Not a Predictive Model)
The point of this project isn't to build the most accurate risk classifier. It's to find interpretable, explainable patterns in the data, the kind of insight you can hand to a non-technical stakeholder and have it make immediate sense. 

## Data
Loan-level data (~80,000 records) with client attributes and days in arrears as the outcome measure. All client data is anonymized.

## Output
- A set of ranked association rules (by lift and confidence) showing which attribute combinations are linked to elevated risk levels
- A short write-up of the most interesting/non-obvious findings
- A simple UI built to check whether a given client profile matches any known risky pattern

## Status
Work in progress.