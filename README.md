# SmartCart-Predicting-E-Commerce-Conversions

The Problem 
Most online shoppers just window-shop, making it tough to pinpoint who will actually buy. Because actual sales are rare, normal AI models cheat by guessing "nobody buys" just to look accurate.

The Fix:
Data Prep I built a pipeline to clean up messy data, fixing missing numbers like age and session duration. I also converted text categories (like device types) into numbers so the model could read them.

The Engine: 
XGBoost I skipped basic models and went straight to XGBoost. It’s a powerhouse for spreadsheet data because it builds decision trees sequentially, with each new tree correcting the mistakes of the last one.

The Strategy: 
Gaming the F1 Score To force the model to care about the rare buyers, I took two crucial steps:

Weighting:
I calculated the exact buyer-to-browser ratio and used it to penalize the model heavily whenever it missed a real sale.

Threshold Tuning:
Instead of a basic 50/50 guess, I tested dozens of cutoffs to find the exact probability sweet spot that maximized our true success rate (the F1 score).

The Results I trained the model on the main data, used a separate public test set to lock in the perfect threshold, and generated a clean two-column spreadsheet predicting the final hidden data.
