![Ironhack Logo](https://i.imgur.com/1QgrNNw.png)

# Answers

### 1. All the companies whose name match 'Babelgum'. Retrieve only their `name` field.

Name :{ name : 'Babelgum'}

### 2. All the companies that have more than 5000 employees. Limit the search to 20 companies and sort them by **number of employees**.

Filter : {number_of_employees : {$gte : 5000}}
Sort : {number_of_employees : 1}
Limit : 20

### 3. All the companies founded between 2000 and 2005, both years included. Retrieve only the `name` and `founded_year` fields.

{founded_year : {$gtegte : 2000}, founded_year : {$lte : 2005} } 

### 4. All the companies that had a Valuation Amount of more than 100.000.000 and have been founded before 2010. Retrieve only the `name` and `ipo` fields.

Filter : {"ipo.value_amount" : {$gt : 100000000}, founded_year : {$lt : 2010}}

### 5. All the companies that have less than 1000 employees and have been founded before 2005. Order them by the number of employees and limit the search to 10 companies.

Filter : {number_of_employees : {$lt : 1000}, founded_year : {$lt : 2005}}
Sort : { number_of_employees : 1 }
Limit : 10

### 6. All the companies that don't include the `partners` field.

Filter : {partners : {$exists : false}}

### 7. All the companies that have a null type of value on the `category_code` field.

Filter : {category_code : {$eq : null}}

### 8. All the companies that have at least 100 employees but less than 1000. Retrieve only the `name` and `number of employees` fields.

Filter : {number_of_employees : {$gte : 100}, number_of_employees : {$lte : 1000}}

### 9. Order all the companies by their IPO price in a descending order.

Sort : {"ipo.valuation_amount" : -1}

### 10. Retrieve the 10 companies with most employees, order by the `number of employees`

Sort : {number_of_employees : -1}
Limit : 10

### 11. All the companies founded on the second semester of the year. Limit your search to 1000 companies.

Filter : {founded_month : {$gte : 7}}
Limit : 1000

### 12. All the companies founded before 2000 that have an acquisition amount of more than 10.000.000

Filter : {$and : [{founded_year : {$lt : 2000}}, {"acquisition.price_amount" : {$gt : 10000000}}]}

### 13. All the companies that have been acquired after 2010, order by the acquisition amount, and retrieve only their `name` and `acquisition` field.

Filter : {founded_year : {$gt : 2010}}
Sort : {"acquisition.price_amount" : -1}

### 14. Order the companies by their `founded year`, retrieving only their `name` and `founded year`.

Sort : {founded_year : -1}

### 15. All the companies that have been founded on the first seven days of the month, including the seventh. Sort them by their `acquisition price` in a descending order. Limit the search to 10 documents.

Filter : {founded_day : {$lte : 7}}
Sort : {"acquisition.price_amount" : -1}

### 16. All the companies on the 'web' `category` that have more than 4000 employees. Sort them by the amount of employees in ascending order.

Filter : {$and : [{category_code : {$eq : 'web'}}, {number_of_employees : {$gt : 4000}}]}
Sort : {number_of_employees : 1}

### 17. All the companies whose acquisition amount is more than 10.000.000, and currency is 'EUR'.

Filter : {$and : [{ "acquisition.price_amount" : {$gt : 10000000}}, {"acquisition.price_currency_code" : {$eq : "EUR"}} ]}

### 18. All the companies that have been acquired on the first trimester of the year. Limit the search to 10 companies, and retrieve only their `name` and `acquisition` fields.

Filter : {"acquisition.acquired_month" : {$lte : 3}}
Limit : 10

### 19. All the companies that have been founded between 2000 and 2010, but have not been acquired before 2011.

Filter : {$and : [{founded_year : {$lte: 2010}}, {founded_year : {$gte : 2000}}, {"acquisition.acquired_year": {$gte : 2011}}]}
