# Event Sourcing 

## Abstract
    
    Data conversion for evolving events in an Event Sourcing System is a complex
issue and needs to be maintainable. There are suggested ways handling
data conversion today which combine different methods into a framework.
However, there is a lack of exploration of different and alternative methods
to handle the complicated matter.
This thesis explores data conversion with account  balance events. The purpose is to explore methods and broaden knowledge for handling data conversion .
 The goal is to build that preserves the attributes reliability and
availability and can handle data conversion of these specific events.

### Introduction 

 *Event sourcing is a powerful architecture pattern that record all change made to an application state.

 *In event sourcing state is store as series of events.

 *Event is simple object that describe some action.

 *It is a combination of entities,command & events.

 *Bank account system & order services are best example of event sourcing .
   
   Order services

     These are different stage of storing related to user

     If some person taking one services order and all the services access to perform
     step 1: Any user come and initiated the order.                                       Initiated
     step 2: Then if it is not completed then its pending state                           Pending
     step 3: All remaining form fill by the user then it show completed.                  Completed
     step 4: If transaction is completed it update on inventory.                        Inventory update
     step 5: Conform Mail goes to user                                                    Mail to user
     step 6: After that ask for feedback                                         Asked for feedback    
     step 7: Archive                                                                       Archive


*Any record is about the state change from previous one.

*We can always replace events to get the state at any point.

*It follow asynchronous communication.
           Fig 1:(see in reference)

         Another example (Account Balance)
            How does Event Sourcing work?

Consider a simple banking example of a current account. In such a system there is a single entity, 

Representing a bank account. 
                       fig:2(see in reference)
For simplicity, we assume there is a single account, so it does not need to be explicitly identifiable 

via an account number or otherwise. 
          

The account contains the current account balance.

Two commands are available – instructions to deposit and withdraw money, and these need to specify the 

amount of money to either deposit or withdraw. 

A business rule ensures a withdrawal command can only be processed if the amount requested is equal to 

or less than the current account balance.

Given this design, two events can be identified – Account Credited and Account Debited. These events 

include the amount of money that was deposited or withdrawn. 

This could even be simplified to a single event with either a positive or negative amount, but for the 

sake of this example they are kept separate.
          fig 3:(see in reference)
          fig 4:(see in reference)

  

##### Conclusion

The goal of this study was to evaluate Event Sourcing and provide a proof-of-
concept using account balance and order services events and explore how the choice of events might
affect the implementation of the system.
The study resulted in a working proof-of-concept, that handles data con-
versions by using a transform method. The goal of preserving both required attributes reliability and availability.
By using account balance events, it was also found that some complex operations were no longer in need, which reduced system complexity drastically. 


##### Reference

fig 1: ( https://engineering.grab.com/democratising-fare-storage-at-scale-using-event-sourcing)
fig 2: ( https://wp.sitepen.com/wp-content/uploads/2020/03/image2-1-768x596.png)
fig 3:(  https://wp.sitepen.com/wp-content/uploads/2020/03/image3-1.png)
fig 4:(https://wp.sitepen.com/wp-content/uploads/2020/03/image1-1.png )
