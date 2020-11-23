/* Question 1*/
select part_num, description, price from part;

/* Question 2*/

select * from orders;

/* Question 3*/
select customer_name from customer where credit_limit >= 10000;

/* Question 4*/
select order_num, customer_num, order_date from orders join customer using (customer_num)
where to_char(order_date, 'MM/DD/YYYY') = '10/23/2010' and customer_num = 608;

/* Question 5*/
select customer_num, customer_name from customer where rep_num = 35 or rep_num = 65;

/*Question 6*/
select part_num, description from part where class != 'AP';

/*Question 7*/
select part_num, description, on_hand from part where on_hand between 10 and 25;

select part_num, description, on_hand from part where on_hand >= 10
and on_hand <= 25;

/*Question 8*/
select part_num, description, round(on_hand * price,0) "ON_HAND_VALUE" from part 
where class = 'SG';

/*Question 9*/
select part_num, description, round(on_hand * price,0) "ON_HAND_VALUE" from part 
where round(on_hand * price,0) >= 7500;

/*Question 10*/
select part_num, description from part where class in 'AP' or class in 'SG';

/*Question 11*/
select customer_num, customer_name from customer where customer_name like 'B%';

/*Question 12*/
select * from part order by description;

/*Question 13*/
select * from part order by warehouse, part_num;

/*Question 14*/
select count(*) from customer where balance > credit_limit;

/*Question 15*/
select sum(balance)"TOTAL BALANCE" from customer where rep_num = 65 
and balance < credit_limit;

/*NO QUESTION 16*/

/*Question 17*/
select min(price) from part;

/*Question 18*/
select part_num, description, price from part where 
price =(select min(price) from part);

/*Question 19*/
select rep_num, round(sum(balance),0) "TOTAL CUSTOMER BALANCE" from customer 
group by rep_num order by rep_num; 

/*Question 20*/
select rep_num, round(sum(balance),0) "TOTAL CUSTOMER BALANCE" from customer 
having round(sum(balance),0) > 10000 group by rep_num order by rep_num;

/*Question 21*/
select part_num from part where description is null;

