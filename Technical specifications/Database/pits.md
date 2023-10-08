# Technical specifications: pits table

## Table
|PK|Name       |  Type  |NULL |   Description
|--|-----------|--------|-----|-----------------------
| 1|uuid       |UUID    |NO   |Unique identifier of the event.
|  |millenium  |INTEGER |NO   |Millenium of the event.
|  |day_of_mil |INTEGER |NO   |Day number of the millenium (365,242.5 days per millenium).
|  |time       |TIME    |NO   |Time of day of the event.

## Constraints
**CK_day_of_mil_365243**: *day_of_mil* must be less or equal to 365243.  
**CK_day_of_mil_pos**: *day_of_mil* must be greater than zero.

## Index
```PGSQL
CREATE INDEX IX_pit ON pits USING B-TREE (
  millenium,
  day_of_mil,
  time
)
```
