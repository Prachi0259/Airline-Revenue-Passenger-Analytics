# ✈️ Airline Revenue & Passenger Behaviour Intelligence Dashboard

> An interactive 2-page Power BI dashboard analysing $645K in airline revenue across 250 bookings, 6 airlines, and 8 global cities — uncovering pricing patterns, passenger behaviour, and revenue drivers.

---

## 🔗 Links

[![Power BI](https://img.shields.io/badge/Power%20BI-Live%20Dashboard-yellow?style=flat&logo=powerbi)](https://app.powerbi.com/groups/me/reports/d1af0f15-4af0-4fe7-96e9-874b84047de1/58402d2b1828c7d30048?experience=power-bi)
[![LinkedIn](https://img.shields.io/badge/LinkedIn-Prachi-blue?style=flat&logo=linkedin)](https://www.linkedin.com/in/prachi252/)
[![GitHub](https://img.shields.io/badge/GitHub-Prachi0259-black?style=flat&logo=github)](https://github.com/Prachi0259)

---

## 📸 Dashboard Preview

### Page 1 — Revenue Drivers & Passenger Segmentation
![Page 1](screenshots/Page%201.png)

### Page 2 — Flight Duration & Pricing Pattern Analysis
![Page 2](screenshots/Page%202.png)

---

## 🎯 Project Objective

Airlines price tickets differently across routes, classes, and cities — but what actually drives revenue? This project analyses booking data to answer:

- Which airlines and cities generate the most revenue and why
- Whether ticket price actually correlates with flight distance
- How passenger age and payment behaviour varies across segments
- Which routes carry the highest duration variance

---

## 📂 Dataset Overview

| Column | Description |
|--------|-------------|
| Booking_ID | Unique booking identifier |
| Airline | 6 airlines (B Airways, S Airlines, E Airlines, L Airlines, Air I, Q Airways) |
| Departure_City | 8 cities (Mumbai, London, Delhi, Singapore, Frankfurt, Paris, Dubai, New York) |
| Travel_Class | Economy, Business, First, Premium Economy |
| Ticket_Price | Price in USD |
| Payment_Method | Credit Card, Cash, Net Banking, PayPal, Debit Card, UPI |
| Passenger_Age | Age of the traveller |
| Flight_Duration_hr | Duration in hours |
| Distance_km | Route distance in kilometres |

**Total Records:** 250 bookings · **Source:** flight_bookings.csv

---

## 💡 Key Findings

**B Airways leads revenue at $129K** — 46% higher than Q Airways at $88K, driven by premium class bookings on high-volume routes rather than sheer number of flights.

**Mumbai is the highest-grossing departure city**, with Delhi and London following closely — pointing to these as priority markets for capacity and pricing decisions.

**Ticket price has no linear relationship with flight distance** — scatter plot analysis across 1,889K km of routes confirms pricing is class-driven, not distance-driven. Business and First class consistently command higher fares regardless of route length.

**Payment preferences are evenly split across 6 methods (~18% each)** — no dominant channel exists, which means restricting payment options would directly hurt conversion across all customer segments.

**Air I operates the longest routes at 13 hrs avg duration** — likely running long-haul international corridors, whilst S Airlines at 9 hrs focuses on shorter regional routes.

**London and Frankfurt show the highest flight duration variance** — both cities handle a mix of short-haul European and long-haul intercontinental routes.

---

## 📈 Dashboard Pages

### Page 1 — Revenue Drivers & Passenger Segmentation
**KPIs:** Total Bookings · Total Revenue · Avg Ticket Price · Total Distance · Avg Duration

**Visuals:**
- Revenue by Airline (horizontal bar)
- Revenue by Departure City (column chart)
- Revenue by Payment Method (matrix)
- Revenue by Passenger Age Group (column)
- Booking Split by Payment Method (donut)
- Bookings by Travel Class (bar)
- Airline slicer for cross-filtering

### Page 2 — Flight Duration & Pricing Pattern Analysis
**KPIs:** Total Bookings · Avg Flight Duration · Longest Route · Most Common Duration

**Visuals:**
- Avg Flight Duration by Class (bar)
- Flight Duration Variance by City (clustered column)
- Ticket Price vs Flight Duration (scatter — coloured by Travel Class)
- Flight Duration by Airline (bar)
- Flight Duration by Age Group (column)
- Avg Duration by Payment Method (matrix)

---

## 🛠️ Tools & Techniques

| Tool | Usage |
|------|-------|
| Power BI Desktop | Dashboard development |
| DAX | Custom measures |
| Power Query | Data transformation |
| Custom JSON Theme | Visual branding (Navy + Sky Blue + Amber) |

**DAX Measures:**
```dax
Longest Route (hrs) = MAX(flight_bookings[Flight_Duration_hr])

Most Common Duration (hrs) =
MINX(
    TOPN(1,
        SUMMARIZE(flight_bookings,
            flight_bookings[Flight_Duration_hr],
            "Freq", COUNT(flight_bookings[Flight_Duration_hr])
        ),
        [Freq], DESC
    ),
    flight_bookings[Flight_Duration_hr]
)
```

---

## 📁 Repository Structure

```
Airline-Revenue-Passenger-Analytics/
│
├── Airline_Revenue_Passenger_Behavior_Intelligence_Dashboard.pbix
├── data/
│   └── flight_bookings.csv
├── screenshots/
│   ├── Page 1.png
│   └── Page 2.png
└── README.md
```

---

## 🚀 How to Run

1. Clone this repository
2. Open `Airline_Revenue_Passenger_Behavior_Intelligence_Dashboard.pbix` in Power BI Desktop
3. If data does not load, go to Home → Transform Data → Data Source Settings and repoint to `data/flight_bookings.csv`
4. Use the Airline slicer on both pages to filter by carrier

---

## 👩‍💻 Author

**Prachi**
📧 prachi7.work@gmail.com

[![LinkedIn](https://img.shields.io/badge/LinkedIn-blue?style=flat&logo=linkedin)](https://www.linkedin.com/in/prachi252/)
[![GitHub](https://img.shields.io/badge/GitHub-black?style=flat&logo=github)](https://github.com/Prachi0259)
