
#linkedIn 


How I made sure only one person could buy the last item

This classic race condition happens when multiple users try purchasing the final unit of a product at the same time. Here's how I solved it using three different database techniques:


Approach 1: Atomic Update (Simple but Powerful)


------------------------------------------------
UPDATE inventory 
SET quantity = quantity - 1 
WHERE product_id = 123 AND quantity > 0

------------------------------------------------------------------------


Then check if rows_affected = 1 in your application code. If it returns 0, the item is out of stock.

This works because the database handles both the check and update in a single atomic operation. No race condition!




Approach 2: SELECT FOR UPDATE (Explicit Locking)


------------------------------------------------
BEGIN TRANSACTION;
  
SELECT * FROM inventory 
WHERE product_id = 123 
FOR UPDATE;
  
-- Check if quantity > 0
-- If yes, update it
  
COMMIT;

------------------------------------------------


This explicitly locks the row while you're working with it. Other transactions must wait their turn.



Approach 3: SERIALIZABLE Isolation

------------------------------------------------
SET TRANSACTION ISOLATION LEVEL SERIALIZABLE;
BEGIN TRANSACTION;
  
-- Read inventory and check quantity
-- Update if available
  
COMMIT;

------------------------------------------------

The database ensures your entire transaction happens as if it were the only one running.



Scaling to Billions of Requests

For massive scale, I added:

1. Database sharding by product category
2. Redis cache with atomic DECR operations
3. Request queuing with Kafka during traffic spikes
4. Inventory reservation with 5-minute expiration
5. Optimized write configurations and connection pooling


Each approach has tradeoffs:

- Atomic updates: Fastest but limited to simple operations
- FOR UPDATE: Most flexible but can create bottlenecks
- SERIALIZABLE: Strongest guarantees but more aborts/retries


What I love about database concurrency control is how much power exists in these simple patterns. No need for complex distributed locks when the database already has solutions built in.


What's your preferred way to handle race conditions in your systems? Have you encountered this "last item" problem before?

Save 💾 ➞ React 👍 ➞ Share ♻️  
  
& follow for everything related to System Design & Engineering