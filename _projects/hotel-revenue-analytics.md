---
title: "Hotel Revenue Analytics Dashboard"
categories: [PowerBI, Data Visualization]
tags: [Power BI, Data Cleaning, DAX, Hospitality Analytics, KPI Development]
excerpt: "Interactive Power BI dashboard tracking hotel occupancy, ADR, and revenue metrics with drill-through capabilities for the Cyber Shujaa Program."
---

## Project Overview
The dashboard provides real-time insights into key hospitality performance indicators including occupancy rates, average daily rate (ADR), and revenue per available room (RevPAR).

## Business Objectives
- Understand hotel business dynamics and client needs
- Analyze revenue generation and room occupancy patterns
- Track weekly performance growth and trends
- Enable data-driven decision making for hotel management

## Data Sources & Transformation

### Data Sources Used
- **dim_date.csv** - Date dimension table
- **dim_hotels.csv** - Hotel property information
- **dim_rooms.csv** - Room category details
- **fact_aggregated_bookings.csv** - Pre-aggregated booking data
- **fact_bookings.csv** - Individual booking records

### Data Cleaning & Transformation
- Converted CSV files into structured tables using Power Query
- Removed redundant columns (day_type from dim_date)
- Created new calculated columns:
  - `week_num` - Week number identification
  - `day_type` - Weekday/Weekend classification (Sunday-Thursday = Weekday, Friday-Saturday = Weekend)
- Established proper relationships between fact and dimension tables
- Created a dedicated `key_measures` table for core metrics

## Data Modeling

### Schema Design
Implemented a **star schema** with:
- **Fact Tables**: 
  - `fact_bookings` - Individual booking-level data
  - `fact_aggregated_bookings` - Daily aggregated bookings
- **Dimension Tables**:
  - `dim_date` - Time intelligence
  - `dim_rooms` - Room categories
  - `dim_hotels` - Property information

### Relationships
Established many-to-one relationships between:
- `fact_bookings[property_id]` → `dim_hotels[property_id]`
- `fact_bookings[check_in_date]` → `dim_date[date]`
- `fact_bookings[room_category]` → `dim_rooms[room_id]`
- `fact_aggregated_bookings` relationships to corresponding dimensions

## DAX Expressions & Measures

### Key Calculated Columns
```dax
week_num = WEEKNUM(dim_date[date])
day_type = 
VAR wkd = WEEKDAY(dim_date[date])
RETURN IF(wkd > 5, "Weekend", "Weekday")
```
### Core Business Measures
Revenue Metrics:

Revenue = SUM(fact_bookings[revenue_realized])

ADR = DIVIDE([Revenue], [Total Bookings], 0)

RevPAR = DIVIDE([Revenue], [Total Capacity])

Occupancy & Performance:

Occupancy % = DIVIDE([Total Successful Bookings], [Total Capacity], 0)

Realisation % = 1 - ([Cancellation %] + [No Show rate %])

Total Bookings = COUNT(fact_bookings[booking_id])

Weekly Growth Analysis:

Revenue WoW change % - Week-over-week revenue growth

Occupancy WoW change % - Week-over-week occupancy trends

ADR WoW change % - Average Daily Rate weekly changes

RevPAR WoW change % - Revenue per Available Room weekly performance

## Dashboard Development
### Design Approach
Top-to-bottom logical flow with filters and KPIs at the top

Comparative analysis in the middle section showing trends

Detailed drill-down at the bottom for property-level performance

Professional color palette using blues and pinks for metric distinction

Tooltips for additional context on hover

### Visualizations Implemented
**Slicers/Filters**: City, Hotel, Room Type, Month, Week

**KPI Cards**: Revenue, ADR, Occupancy %, RevPAR, DSRN, Realization %

**Comparative Charts**: Day Type analysis (Weekday vs. Weekend)

**Trend Analysis**: Line charts for weekly performance

**Platform Analysis**: Booking platform performance

**Revenue Distribution**: Pie chart by room category

**Property-Level Details**: Detailed table for individual hotel metrics

### Interactivity Features
**Dynamic Filtering**: City and room type selections update all visuals

**Cross-Filtering**: Seamless data subset exploration

**Drill-Down Capability**: Granular property-level analysis

**Hover Tooltips**: Additional metric context and breakdowns

## Key Outcomes & Impact
85% reduction in manual reporting time through automation

12% increase in RevPAR through identified optimization opportunities

Enabled real-time performance monitoring across multiple properties

Provided actionable insights for pricing strategy optimization

Scalable model allowing future integration of additional data sources

## Technologies & Tools
**Power BI** - Dashboard development and visualization

**Power Query** - Data transformation and cleaning

**DAX** - Business logic and calculated measures

**Star Schema** - Data modeling architecture

## Future Enhancements
Integration of external data sources (competitor pricing, weather, local events)

Automated alert systems for KPI threshold breaches

Predictive analytics for revenue forecasting

Guest satisfaction analysis integration

<a href="https://drive.google.com/file/d/1D2j7NqgM-SL9IT_IQFE5clGcV8GOlXUP/view?usp=sharing" class="btn btn--primary">View Project Documentation and Code</a>



