# Database Queries

### Display the ProductName and CategoryName for all products in the database. Shows 76 records.

[x] SELECT p.productName , c.categoryName from products as p join categories as c on p.CategoryID = c.CategoryId

### Display the OrderID and ShipperName for all orders placed before January 9, 1997. Shows 161 records.

[x] SELECT o.orderId ,s.shipperName , o.orderDate 
from orders as o 
join shippers as s 
on o.shipperId = s.shipperId 
where orderDate < '1997-01-09'

### Display all ProductNames and Quantities placed on order 10251. Sort by ProductName. Shows 3 records.
[x] select p.productname , o.quantity from products as p join orderDetails as o on p.productId = o.productId where orderID=10251
order by p.productname desc
### Display the OrderID, CustomerName and the employee's LastName for every order. All columns should be labeled clearly. Displays 196 records.
[x] select o.orderid, c.customername , e.lastname from orders as o
left join customers as c on o.customerId = c.customerId 
left join employees as e on o.employeeid = e.employeeId

### (Stretch)  Displays CategoryName and a new column called Count that shows how many products are in each category. Shows 9 records.

[x] select c.categoryName , count(p.productName) from categories as c left join products as p on p.categoryId = c.categoryId group by c.categoryName

### (Stretch) Display OrderID and a  column called ItemCount that shows the total number of products placed on the order. Shows 196 records. 

[x] SELECT orderId, Sum(quantity) as ItemCount  from orderDetails group by  orderId