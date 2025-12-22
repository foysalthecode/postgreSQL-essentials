# NULL

    select * from students where email is null ---> will provide the null email

    select * from students where email is not null --> will provide the valid email (exist email)

# COALESCE

    select coalesce(null,null,2,2)  --> this checks every arguments and checks that which on is not null then return the not null value (return only one not null value)
