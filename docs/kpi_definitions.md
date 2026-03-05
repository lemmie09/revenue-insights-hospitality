# KPI Definitions – Revenue Insights (Atliq Grands)

## Objective

Define business logic for all KPIs before implementing them in DAX.

---

## 1. Total Revenue

Definition:
Sum of revenue generated from successful bookings.

Formula (Business Logic):
Total Revenue = Sum of revenue where booking_status = "Checked Out"

---

## 2. Total Bookings

Definition:
Total number of booking records.

Formula:
Total Bookings = Count of booking_id

---

## 3. Successful Bookings

Definition:
Bookings where guests completed their stay.

Formula:
Count of booking_id where booking_status = "Checked Out"

---

## 4. Occupancy %

Definition:
Percentage of available rooms that were successfully booked.

Formula:
Occupancy % = Successful Bookings / Total Available Rooms

---

## 5. ADR (Average Daily Rate)

Definition:
Average revenue earned per successful booking.

Formula:
ADR = Total Revenue / Successful Bookings

---

## 6. RevPAR (Revenue Per Available Room)

Definition:
Revenue generated per available room.

Formula:
RevPAR = Total Revenue / Total Available Rooms

Alternative formula:
RevPAR = ADR × Occupancy %

---

## 7. Realization %

Definition:
Percentage of bookings realized out of total capacity.

Formula:
Realization % = Successful Bookings / Total Capacity

---

## Business Questions to Answer

- Which city contributes the most revenue?
- Which property has declining occupancy?
- Are weekends performing better than weekdays?
- Which booking platform generates the highest revenue?
- Where is revenue leakage occurring?
