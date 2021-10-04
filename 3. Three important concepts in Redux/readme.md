#   Three Important concepts For Redux

So, what are these three concepts ? & why they are so important?

Those three concept are :

| Redux Concept | Description |
|--- | --- |
| Store | Holds the `state` of your Application |
| Action | Describes the change in the state of the Application |
| Reducer | Carries out the `state transaction` depending upon the Action |

To understand these concepts let's take an example of a Cake Shop.

Let's consider the possible entities we have.

####   Entities
        -   Shop: Stores cakes on a Self.
        -   Shopkeeper: At the front of the Store.
        -   Customer: At the Stores Entrance.

And Now the Activities that can happens

####    Activities
        -   Customer: Buying a Cake.
        -   Shopkeeper: 
            -   Remove Cake from Shelf.
            -   Recipt to Keep Track.

So, Here compare the above concepts with Entities & Activities:

| Entities & Activities | Redux Concepts | Description |
| --- |---|---|
| Shop | Store | Holds the state of your Application |
| Intention Of Buying | Action | Describes what Happened |
|Shopkeeper | Reducer | Ties `Action` & `Store` togeather |


