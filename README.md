# DSN Bootcamp Qualification Hackathon 2026 — ML Track

Predicting total sales for a product at a store, for DSN Mart — built as
the qualifying hackathon for the DSN AI Bootcamp.

## Problem

DSN Mart operates stores across Nigeria, from corner shops to
hypermarkets. This project predicts `total_sales` for a given
product-store pair, using information about the product (weight, price,
category, etc.) and the store (size, age, location, format). It's a
regression problem, scored with RMSE.

## Approach

1. **Cleaning** — fixed inconsistent capitalization in `product_category`
   (48 messy variants collapsed to 16 real categories), handled missing
   values in `product_weight_kg` and `store_size`.
2. **Modeling** — compared a mean baseline, Random Forest, and CatBoost.
   CatBoost performed best.
3. **Tuning** — tested different CatBoost depths and learning rates using
   a held-out validation split.
4. **Extra experiments** — tried a log-transformed target, target
   encoding for store/product identity, an engineered `price_per_kg`
   feature, and blending CatBoost with Random Forest. None of these
   improved the validation RMSE, so none were used in the final model —
   details and numbers are in the notebook's "Further Experiments"
   section.
5. **Final model** — CatBoost (depth 3, learning rate 0.03, 500
   iterations), trained 5 times with different random seeds and
   averaged, to make the predictions a bit more stable.

## Result

Validation RMSE: **~1067.5**

## Repo structure
