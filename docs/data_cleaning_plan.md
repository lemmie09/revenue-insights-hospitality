# Data Cleaning Plan – Revenue Insights (Atliq Grands)

## Objective

Prepare raw hospitality data for accurate modeling and KPI calculation in Power BI.

---

## 1. fact_bookings Cleaning

Checks to perform:

- Ensure booking_id is unique.
- Remove duplicate rows if any.
- Standardize booking_status values (e.g., "Cancelled", "Checked Out", "No Show").
- Ensure revenue column is numeric and contains no negative values.
- Verify date columns are in proper date format:
  - booking_date
  - check_in_date
  - checkout_date
- Ensure checkout_date is after check_in_date.
- Handle missing values in revenue or booking_status.

---

## 2. fact_aggregated_bookings Cleaning

- Ensure property_id exists in dim_hotels.
- Ensure room_category exists in dim_rooms.
- Check for null or zero capacity values.
- Validate successful and cancelled booking counts.
- Remove duplicates if present.

---

## 3. dim_date Cleaning

- Ensure date column is unique.
- Validate weekday vs weekend classification.
- Ensure month and year fields are consistent.

---

## 4. dim_hotels Cleaning

- Ensure property_id is unique.
- Standardize city names (no spelling variations).
- Remove duplicate properties.

---

## 5. dim_rooms Cleaning

- Ensure room_category is unique.
- Validate capacity values are logical and non-negative.

---

## Data Integrity Rules

- No many-to-many relationships.
- All foreign keys must match primary keys.
- No orphan records in fact tables.
- All numeric KPI-related columns must be correctly typed.
