# Cleaned datasets for CS4048 Assignment 2 (Netflix and Supermarket Sales)

**Version:** v1.0  
**Date:** 18 October 2026  
**Author:** Khadija A-Rahim (23L-1008)

This repository holds the two cleaned datasets from my Assignment 2 (Exploratory Data Analysis). Assignment 3 will load these exact files, so please use the v1.0 release.

## Files
| File | Rows × columns | Source |
| --- | --- | --- |
| `23L_1008_A2_netflix_cleaned.csv` | 8,807 × 22 | Netflix Movies and TV Shows (Kaggle, standard version, 8,807 × 12): https://www.kaggle.com/datasets/shivamb/netflix-shows |
| `23L_1008_A2_supermarket_cleaned.csv` | 1,000 × 22 | `supermarket_Sales.csv`, the file provided by the course instructor (1,000 × 17) |

The original data belongs to its authors. Please see the source pages for their licence and credit them if you reuse the data.

## What I changed

### Netflix
- Missing `director`, `cast` and `country` filled with "Unknown" (they were never recorded).
- 10 missing `date_added` values left empty.
- 3 durations that were stored in `rating` moved to `duration`; `rating` set to "Unknown". 4 missing ratings set to "Unknown". UR merged into NR.
- Removed extra spaces and converted `date_added` to a real date (YYYY-MM-DD).
- Split `duration` into `duration_min` (movies) and `n_seasons` (TV shows).
- Tidied the multi-value fields and added `n_countries`, `n_genres`, `n_cast`, `primary_country` and `primary_genre`.
- Added `year_added`, `month_added`, `year_gap` (year added minus release year) and `added_before_release` (flags 14 titles).
- No rows removed. Outliers kept.

### Supermarket Sales
- `Date` converted to a real date (YYYY-MM-DD); `Time` kept as HH:MM.
- Added `hour`, `weekday`, `is_weekend`, `month` and `time_of_day` (Morning 10–12, Afternoon 13–16, Evening 17–20).
- No missing values or duplicates were found. No rows removed. Original columns and names kept.
- Cost of goods sold, Tax 5%, Total and Gross income can be calculated from Unit price and Quantity, and Gross margin percentage is constant. I kept them on purpose and did not drop them.
- 9 high `Total` values kept (real large purchases).

## Notes for Assignment 3
- Unknown values in the Netflix file mean "not recorded" (`n_countries` = 0 means missing country).
- `duration_min` is empty for TV shows and `n_seasons` is empty for movies, on purpose.
- The rating scale in the Supermarket file is not documented; I assume 1–10.

If I change the cleaning later, I will publish a new version and describe the change here. I will not overwrite v1.0.
