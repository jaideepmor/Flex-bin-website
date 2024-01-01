# Data Normalization:
    What? Normalization is the process of minimizing redundancy from a relation or set of relations. 
    Why? Redundancy in relation may cause insertion, deletion, and update anomalies.
    How? 

# 1NF
    W? Each table cell should contain only a single value, and each column should have a unique name.
    W? Eliminate duplicate data and simplify queries.

    ex: Booking Pickup

         ----------------------------------------------------------------
        |   PickUpId   |  PickUpTiming |   CustomerId   |  CustomerName  |
        |--------------|---------------|----------------|----------------|
        |       1      |     7 -  8 AM |  101, 119, 122 |  XYZ, PQR, UVW | 
        |       2      |    10 - 11 AM |            344 |            TVW |
         ---------------------------------------------------------------- 


         ----------------------------------------------------------------
        |   PickUpId   |  PickUpTiming |   CustomerId   |  CustomerName  |
        |--------------|---------------|----------------|----------------|
        |       1      |    7 -  8 AM  |       101      |      XYZ       |  
        |       1      |    7 -  8 AM  |       119      |      PQR       |
        |       1      |    7 -  8 AM  |       122      |      UVW       | 
        |       2      |    10 - 11 AM |       344      |      TVW       |
         ---------------------------------------------------------------- 


         ------------------------------
        |   PickUpId   |  PickUpTiming | 
        |--------------|---------------|
        |       1      |     7 -  8 AM |
        |       2      |    10 - 11 AM |
         ------------------------------

         ------------------------------------------
        |  BookingId   |   PickUpId  |  CustomerId | 
        |--------------|-------------|-------------|
        |     101      |         1   |         101 |
        |     112      |         2   |         344 |
        |     113      |         1   |         122 |
        |     134      |         1   |         129 |
         ------------------------------------------

         ---------------------------------
        |   CustomerId   |  CustomerName  |
        |----------------|----------------|
        |         101    |         XYZ    | 
        |         119    |         PQR    |
        |         122    |         UVW    | 
        |         344    |         TVW    |
         ---------------------------------  

# 2NF
    W? Each non-key attribute should be dependent on the primary key.
    W? Eliminates redundant data.

# 3NF
    W? All non-key attributes are independent of each other.
    W? 2NF 

# BCNF


Booking, PickUpTiming, Customers, PickUpAvailability

    --------------------------------------------------------------------------------------
   | PickUpAvailabilityId  |     Date      | TotalAvailableBooking | CurrentAvailableBook |
   |-----------------------|---------------|-----------------------|----------------------|
   |             1001      |               |                       |                      |
   |             1002      |               |                       |                      |
   |             1003      |               |                       |                      |
    --------------------------------------------------------------------------------------       