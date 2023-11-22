
-- --------------------------------------------------------------------------------------
-- ------------------------------- Bonus Queries from Danny ----------------------------------------

-- Recreate a Comprehensive Customer Data Table using the available data 

SELECT s.customer_id, s.order_date, m.product_name, m.price,
	(CASE 
		WHEN s.order_date >= mb.join_date THEN 'Y'
		ELSE 'N' 
		END) AS member
FROM sales s
	JOIN menu m ON s.product_id = m.product_id
	LEFT JOIN members mb ON s.customer_id = mb.customer_id
ORDER BY s.customer_id, s.order_date;


-- Rank the products of member customers

WITH customers_data AS (
  SELECT s.customer_id, s.order_date,  m.product_name, m.price,
    CASE
      WHEN s.order_date < mb.join_date THEN 'N'
      WHEN s.order_date >= mb.join_date THEN 'Y'
      ELSE 'N' 
	  END AS member
  FROM sales s
  LEFT JOIN members mb
    ON s.customer_id = mb.customer_id
  JOIN menu m
    ON s.product_id = m.product_id)
SELECT *, 
  CASE
    WHEN member = 'N' THEN NULL
    ELSE RANK () OVER(PARTITION BY customer_id, member ORDER BY order_date) 
	END AS ranking
FROM customers_data
ORDER BY customer_id, order_date;
