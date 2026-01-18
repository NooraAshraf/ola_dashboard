# OLA Data Analyst Project — Power BI Dashboard

## 📌 **Project Overview**

This project analyzes ride data for OLA in Bengaluru city over one month.
The purpose of the dashboard is to identify operational patterns, cancellations, revenue trends, and customer/driver ratings to provide actionable insights.

---

## 🎯 **Project Goals**

* Understand booking success and cancellation patterns
* Analyze vehicle type performance and ride distances
* Measure customer & driver experience through ratings
* Visualize revenue and payment method distribution
* Identify key customer segments & behavioral trends

---

## 🛠 **Tech Stack**

* **Power BI Desktop**
* **DAX**
* **Power Query**
* **Excel / CSV (Generated synthetic dataset)**
* **SQL** (for analytical queries)

---

## 🗂 **Dataset Details**

The dataset consists of **100,000 rows** for Bengaluru with the following key fields:

| Category          | Columns                                                         |
| ----------------- | --------------------------------------------------------------- |
| Booking Info      | Date, Time, Booking_ID, Booking_Status                          |
| Customer & Driver | Customer_ID, Driver_Ratings, Customer_Rating                    |
| Vehicle           | Vehicle_Type                                                    |
| Trip Details      | Pickup_Location, Drop_Location, Ride_Distance                   |
| Timings           | V_TAT (Vehicle Time to Arrive), C_TAT (Customer Time to Arrive) |
| Completion        | Cancelled by Customer, Cancelled by Driver, Incomplete_Rides    |
| Finance           | Booking_Value, Payment_Method                                   |

---

## 📊 **Power BI Dashboard Insights**

Dashboard covers the following visuals:

### **📈 Overall Analytics**

* Ride Volume Over Time
* Booking Status Breakdown

### **🚗 Vehicle Analytics**

* Top 5 Vehicle Types by Ride Distance
* Average Customer Ratings by Vehicle Type

### **💰 Revenue Insights**

* Revenue by Payment Method
* Top 5 Customers by Total Booking Value

### **❌ Cancellation Insights**

* Cancelled Rides by Customer Reason
* Cancelled Rides by Driver Reason

### **⭐ Ratings**

* Driver Ratings Distribution
* Customer Rating Distribution
* Customer vs Driver Ratings Correlation

---

## 🧮 **Business Rules Applied**

* Successful bookings: **62%**
* Cancelled by Customer: **< 7%**
* Cancelled by Driver: **< 18%**
* Incomplete rides: **< 6%**
* Higher ride demand on **weekends & match days**
* Higher booking value on weekends

---

## 🧑‍💻 **SQL Analysis**

Some analytical queries used:

```sql
-- Successful bookings
SELECT * FROM bookings WHERE Booking_Status = 'Success';

-- Average ride distance by vehicle type
SELECT Vehicle_Type, AVG(Ride_Distance) 
FROM bookings
GROUP BY Vehicle_Type;

-- Total cancellations by customer
SELECT COUNT(*) 
FROM bookings 
WHERE Booking_Status = 'cancelled by Customer';

-- Top 5 customers by ride count
SELECT Customer_ID, COUNT(Booking_ID) AS total_rides
FROM bookings
GROUP BY Customer_ID
ORDER BY total_rides DESC
LIMIT 5;
```

---

## 📁 **Project Files**

* `ola_data.pbix` — Power BI Dashboard file
* `ola_dataset.xlsx` — Generated data source (1 lakh rows)
* `SQL_Queries.sql` — Analysis queries
* `README.md` — Project documentation (this file)

---

## 🏁 **Key Outcomes**

✔ Identified demand spikes during weekends & match days
✔ Segmented top customers by booking value
✔ Found major cancellation reasons for drivers & customers
✔ Rated vehicle types based on average customer satisfaction
✔ Linked revenue patterns to payment methods

---

##  📊 **Dashboard Demo Preview**
 



--
✔ Dataset download link
✔ Live Power BI Service link (optional)
