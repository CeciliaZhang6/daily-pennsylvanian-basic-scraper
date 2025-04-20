# Step 5: GitHub Actions Schedule Explanation

The original cron expression used in our GitHub Actions workflow is:

    0 20 * * *

## ** What This Means**
This means that the scraper runs **automatically at 8:00 PM UTC every day**. The cron syntax consists of five fields:
- `0` → Runs at **minute 0** 
- `20` → Runs at **hour 20** (8:00 PM UTC).
- `*` → Runs **every day of the month**.
- `*` → Runs **every month**.
- `*` → Runs **every day of the week**.

## **Modifications**
modify the cron expression in `.github/workflows/scraper.yaml`: 

- `0 12 * * *` → Runs **every day at 12:00 PM UTC**
- `0 0 * * 0` → Runs **every Sunday at midnight UTC**
- `0 0,12 * * *` → Runs **at 00:00 UTC and 12:00 UTC every day** (twice a day, 12 hours between)
