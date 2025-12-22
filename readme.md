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

> what to do to show pagination data !!

    select * from students limit 5 offset 5 * 0  --> this will show first 5 data when user click 1
    select * from students limit 5 offset 5 * 1  --> this will show 2nd 5 data when user click 2
    select * from students limit 5 offset 5 * 2  --> this will show 3rd 5 data when user click 3


