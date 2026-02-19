# Agile Project Sample – Customer Retention Enhancement

## Methodology
This project follows Agile methodology using iterative sprints and continuous stakeholder feedback.

## Sample User Stories

### Epic: Improve Customer Retention

**User Story 1**
As a Marketing Manager,
I want to identify customers at risk of churn,
So that I can target them with retention campaigns.

**User Story 2**
As a Sales Manager,
I want to view customer engagement metrics,
So that I can prioritise high-value clients.

---

## Acceptance Criteria

- The system must flag customers inactive for 60+ days.
- Dashboard must display churn risk score.
- Monthly retention report must be downloadable.

---

## Sample SQL Query

```sql
SELECT customer_id,
       COUNT(order_id) AS total_orders,
       MAX(order_date) AS last_purchase_date
FROM orders
GROUP BY customer_id
HAVING MAX(order_date) < DATE_SUB(CURRENT_DATE, INTERVAL 60 DAY);
