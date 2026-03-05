# Data Model Design – Revenue Insights (Atliq Grands)

## Objective

Design a clean star schema model to support KPI tracking:
Revenue, ADR, RevPAR, Occupancy %, and Realization %.

---

## Fact Tables

### fact_bookings
Grain: One row per booking.

Key columns:
- booking_id
- property_id
- room_category
- booking_date
- check_in_date
- checkout_date
- revenue
- booking_status
- booking_platform

This is the primary fact table used for revenue and booking-related KPIs.

---

### fact_aggregated_bookings
Grain: Aggregated booking data.

Used for:
- Capacity analysis
- Successful vs cancelled bookings
- Occupancy calculations

---

## Dimension Tables

### dim_date
Used for time-based analysis:
- Day
- Week
- Month
- Weekday vs weekend

---

### dim_hotels
Connected via property_id.

Attributes:
- property_name
- city

---

### dim_rooms
Connected via room_category.

Attributes:
- room_class
- capacity

---

## Relationships (Star Schema)

dim_hotels (1) → fact_bookings (many)  
dim_rooms (1) → fact_bookings (many)  
dim_date (1) → fact_bookings (many)

---

## Modeling Rules

- fact_bookings is the central table.
- All dimensions must have one-to-many relationships with the fact table.
- Use single-direction filtering (dimension to fact).
- Avoid many-to-many relationships.
- Keep the model simple and readable.
