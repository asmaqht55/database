# database
CREATE DATABASE store;
code int PRIMARY KEY,
name varchar(20),
  continent_name varchar(20),
);
create table users(
  id int primary key ,
  full_name varchar(20) ,
  email varchar(20) unique,
  gender char(1) check('F' or 'M'),
  date_of_birth varchar(15),
  created_at datetime,
  continent_code int ,
  foreign key (continent_code) references countries(code)
);
CREATE TABLE orddrs(
id int PRIMARY KEY,
 user_id int ,
  status varchar(6) check( 'start' or 'finish'),
  foreign key (user_id) references users(id)
);
CREATE TABLE order_product(
order_id int  ,
  product_id int ,
  quantity int default 0,
  primary key (order_id,product_id),
  foreign key (order_id) references orders(id),
  foreign key (product_id) references products(id)
);
        
