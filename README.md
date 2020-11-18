# SOFT-ENG-Train-station
# STRATHMORE INSTITUTE

# DIPLOMA IN BUSINESS INFORMATION TECHNOLOGY RAILWAY RESERVATION CASE STUDY RESOLVE
    DATE:04-11-2020                                                DUE: 18-11-2020



## Introduction to the Railway Reservation Case Study.


 ## Introduction


    Kenya has launched the Nairobi to Nanyuki Railway line. However, passengers are not able to book their trip in advance. Your company has been tasked with developing a    solution   that would enable passengers to book their trips in advance. You are currently playing the role of a Software Engineer in the company.

## Purpose


    The railway reservation system facilitates the passengers to enquire about the trains available on the basis of source and destination, booking and cancellation of tickets, enquire about the status of the booked ticket, etc.
    The aim of case study is to design and develop a database maintaining the records of different trains,    train    status,    and    passengers. The record of train includes its number, name, source, destination, and days on which it is available, whereas record of train status includes dates for
    which tickets can be booked, total
    number of seats available, and number of seats already booked.


## Description


    Passengers can book their tickets for the train in which seats are available. For this, passenger has to provide the desired train number and the date for which ticket is to be booked. Before booking a ticket for a passenger, the validity of train number and booking date is checked.
    Once the train number and booking date are validated, it is checked whether the seat is available. If yes, the ticket is booked with confirm status and corresponding ticket ID is generated which is stored along with other details of the passenger. After all the available tickets are booked,
    certain numbers of tickets are booked with waiting status. If waiting lot is also finished, then tick ets are not booked and a message of non‐availability of seats is displayed.
    The ticket once booked can be cancelled at any time. For this, the passenger has to provide the ticket ID (the unique key). The ticket ID is searched and the corresponding record is deleted. With this, the first ticket with waiting status also gets confirmed.

## Assumptions

    Since the reservation system is very large in reality, it is not feasible to develop the case study to that extent and prepare documentation at that level. Therefore, a small sample case study has been created to demonstrate the working of the reservation system. To implement this sample case study, some assumptions have been made, which are as follows:

     1.   The number of trains has been restricted to 3.

    2.   The booking is open only for next seven days from the current date.
 


    3.   Only two categories of tickets can be booked, namely, Economy Class (EC), Business

    Class (BC) and Premier Class (PC).

    4.   The total number of tickets that can be booked in each category (EC, BC and

    PC) is 30.

       5.   The total number of tickets that can be given the status of waiting is 10.
    6.   The in‐between stoppage stations and their bookings are not considered.
## Assignment I Resolved


    1.	Identify possible actors in the case study.
    •	Passengers
    •	Reservation Clerk
    •	Administrator

    2.   Identify possible classes in the case study.

    •	Passenger
    •	TrainList
    •	Train_status
    •	Booking
    •	Cancel

## Description of Tables and Procedures 
### Tables and procedures that will be created are as follows: 

    1. TrainList:  This  table  consists  of  details  about  all  the  available  trains.  The  information 
    stored  in  this  table  includes  train  number,  train  name,  source,  destination,  fair  for  BC,EC,PC
    ticket, fair for general ticket, and weekdays on which train is available. 
    Constraint: The train number is unique. 

    2. Train_Status:  This  table  consists  of  details  about  the  dates  on  which  ticket  can  be 
    booked  for  a  train  and  the  status  of  the  availability  of  tickets.  The  information  stored  int his  table  includes  train  number,  train  date,  total  number     of  BC,EC,PC  seats,  total  number  of general seats, number of AC seats booked, and number of general seats booked. 
    Constraint: Train number should exist in TrainList table.
 
    3. Passenger:  This  table  consists  of  details  about  the  booked  tickets.  The  information 
    stored  in  this  table  includes  ticket  ID,  train  number,  date  for  which  ticket  is  booked, 
    name,  age,  sex  and  address  of  the  passenger,  status  of  reservation  (either  confirmed  or 
    waiting), and category for which ticket is booked.
    Constraint: Ticket ID is unique and the train number should exist in TrainList table.
 
    4. Booking:  In  this  procedure,  the  train  number,  train  date,  and  category  is  read  from  the passenger.  On  the  basis  of  the  values  provided  by  the       passenger,  corresponding  record is retrieved from the Train_Status table. If the desired category is BC, then total number 
    of  EC,PC  seats  and  number  of  booked  BC  seats  are  compared  in  order  to  find  whether 
    ticket  can  be  booked  or  not.  Similarly,  it  can  be  checked  for  the  general  category.  If 
    ticket can be booked, then passenger details are read and stored in the Passenger table. 

    5. Cancel:  In  this  procedure,  ticket  ID  is  read  from  the  passenger  and  corresponding  record  is 
    searched  in  the  Passenger  table.  If  the  record  exists,  it  is  deleted  from  the  table.  After 
    deleting the record (if it is confirmed), first record with waiting status for the same train and 
    same category are searched from the Passenger table and its status is changed to confirm. 


Classes | ATTRIBUTES
-- | --
TRAINLIST | Train_no   Train_name   Source   Destination   Fair_for _BC,EC,PC_ticket   Fair_for_ general_ ticket
TRAIN_STATUS | train _date    total _number _of _BC,EC,PC _seats    total _number _of _general_seats    number_of BC,EC.PC_seats _booked    number_of _general _seats_ booked
PASSANGERS | Ticket _ ID    train _number    date _for _which _ticket _is _booked   name    age    sex     address _of _the _passenger   status _of _reservation (either    confirmed  or    waiting)   category_for _which_ ticket_ is _booked.
BOOKING | Train _no    train _date   category
CANCEL | Ticket_ID

## Draw a Use Case Diagram for the Railway Reservation System.

## Draw a Class Diagram.
![image](https://user-images.githubusercontent.com/64952843/99505325-bb0b2a80-2991-11eb-8cd5-7020c8b8168a.png)
 ## Draw a sequence Diagram
 ![image](https://user-images.githubusercontent.com/64952843/99505802-5a302200-2992-11eb-84fe-8c565f802558.png)
