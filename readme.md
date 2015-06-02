:shipit:

ANSWERS:


1)  How many users are there?  49
select count(*) from users;


2)  What are the 5 most expensive items?  
Gorgeous Plastic Pants
Intelligent Cotton Com
Small Concrete Pants
Gorgeous Granite Pants
Rustic Concrete Pants
select name from items order by price desc limit 5;


3)  What's the cheapest electronics item?
Answers could vary - if you mean Electronics and something else could be in the category the answer would be different.  I took it to mean the category is exactly Electronics.
Rustic Wooden Table.
select * from items order by price desc where category='Electronics';


4)  Who lives at "489 Fritsch Island"? Do they have another address?
Marty Schmidt, other adddress is 84642 Bosco Orchard
SELECT * from addresses join users on users.id = user_id where street="489 Fritsch Island"
SELECT * from addresses where user_id = 35;

5)  Correct Tevin Mitchell's New York zip code to 10108.
done - command is UPdate zip set quantity="10108" from addresses where user_id = 25;


6)  How much would it cost to buy one of each piece of jewelery?
$226.26
select sum(price) from items where category like '%Jewelery%';


7) How many total items did we sell?
817
select sum(quantity) from orders;


8)  How much was spent on health?
$40,542.07
select sum(price * quantity) from orders join items on item_id = items.id;



9)  Simulate buying an item by inserting a User for yourself and an Order for that User (do not include this in the figures above).
INSERT into users values(null, "Polly", "Gee", "pollysileo@gmail.com");
select * from users where first_name="Polly" (to find id)
insert into orders values(null, 51, 40, 2);


HARD MODE: 

10) What item was ordered most often? Grossed the most money?
Ordered the most often - 
Gorgeous Granite Pants
select name, item_id,sum(quantity) from orders join items on orders.item_id = items.id group by item_id order by sum(quantity) desc;


11) What user spent the most?



12) What were the top 3 highest grossing categories?



13) Which item was never ordered?


