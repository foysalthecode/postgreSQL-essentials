# NULL

    select * from students where email is null ---> will provide the null email

    select * from students where email is not null --> will provide the valid email (exist email)

# COALESCE

    select coalesce(null,null,2,2)  --> this checks every arguments and checks that which on is not null then return the not null value (return only one not null value)

    -----------------

    select coalesce(email,"not provided") from students
    this "Not provide" is stand for placeholder (for null value)

# limit (for pagination)

    select * from students limit 5 (eita shudu first 5 ta row dibe)

# offset

    select * from students limit 5 offset 2 (eita 5 ta row  dibe but first 2 ta bad diye dibe )

# what to do to show pagination data !!

    select * from students limit 5 offset 5 * 0  --> this will show first 5 data when user click 1
    select * from students limit 5 offset 5 * 1  --> this will show 2nd 5 data when user click 2
    select * from students limit 5 offset 5 * 2  --> this will show 3rd 5 data when user click 3

# UPDATE

    update students set email = "default@gmail.com" where email is  null
    -> this will change null value email as "default@gmail.com"

    -------------------------------------

    update students set first_name = "Ariful", age = 20 where student_id = 1
    -> this will change first student specified value

    ----------------------------------------------

    update students set grade = "C" where student_id in (1,2)
    -> this will change first and second student grade value to C

# DELETE

    delete from students where grade = "C"
    delete from students where age > 20 and grade = "B+"

# GROUP BY

    select country from students group by country

    select country,avg(age) from students group by country

## count students by country

    select country,count(*) from students group by country

## count students by grade

    select grade,count(*) from students group by grade

    <!-- group by operator cannot give multiple data .. it only return one data -->

## courses that minimum 4 student enrolled (je course e 4 jon er besi student ase)

> group by having

    select courses,count(*) from students group by courses having count(*) > 4

## countries where average student age is greater than 21

    select country,avg(age) from students group by country having avg(age) > 21

# FOREIGN KEY

    uniquley identifies row to another table which is connected to the row of this table

# INNER JOIN

    inner join ---> it contains only the value who maintain the conditions..if it gets any null
    value then inner join will remove the row

# LEFT JOIN

    left join --> it contains everything---like if we use this method then it will join 2 table
    and will include null value also ---- it will prioritize only the primary table and second
    table remain null

# RIGHT JOIN

    right join --> it is oposite of left join and remain left side table null if condition not met
    and data not found

# FULL JOIN

    full join ---> it will retrive all rows in a tableee if the value is null it will also
    retrive the null things
