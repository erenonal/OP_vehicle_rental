# VEHICLE RENTAL PROJECT (with object-oriented programming)

It is a project which includes there are car and bicycle rental options, also stock and price information is shown.
In this project, we can rent a bicycle or car, depending on the stock status, on a daily or hourly fixed price.
We can apply discounts on certain vehicles. We can provide feedback according to stock status.

### About Implementation

I created the `rent.py` file. After importing the `datetime` library for timeseries, I created our parent class (`VehicleRent`), child classes (`CarRent`, `BikeRent`) and `Customer` class.

VehicleRent includes `initializer`, `diplayStock`, `rentHourly`, `rentDaily` and `returnVehicle` methods.

Initializer contains self and `stock`, displayStock self, rentDailiy and rentHourly self and `n`, returnVehicle self,`request` and `brand` input parameters.

The `"n"` value in rentDailiy and rentHourly indicates how many vehicles are wanted to be rented.

The `request` in returnVehicle is a variable that expresses when we rent the vehicles, how long we rent and how many vehicles we rent.
`Brand` refers to whether it is a car or a bicycle.

The child class CarRent has the global discount_rate variable. In this way, we can calculate a 15% discount.
I have not applied such a discount on bike rental (BikeRent child class).
With `super().__init__(stock)` we can directly use the properties of our parent class.

`Customer` class includes init, requestVehicle, returnVehicle. init methods has brand,rentalBasis and rentalTime attributes as 0.
According to the request from the user, these values will be used in the invoice calculation.

As the last step, with the `returnVehicle` method in the `Customer`, we reset these values for the invoice when a vehicle returns from rent.

As the second file, we create our `main.py` file. As the name suggests, this is our main file where we will interact with the user.
For example, I set the CarRent, BikeRent and Customer classes, which we imported from the rent file, as our bike stock to 100 and our car stock to 10.

I set main_menu to True so that it is available for continuous use both in the header and in the interface.

I adjusted the main menu and submenus according to the choices to be made. These parts are clearly visible in the code. So I will explain directly on the user manual.


### User guide

From the main menu we can press the letter "A" for the bike menu or "B" for the car menu. Or we can exit directly with "Q".

            ***** Vehicle Rental Shop *****
            A. Bike Menu
            B. Car Menu
            Q. Exit
            
            
For example, we chose the bike by pressing "A" and this menu will appear.

            ***** BIKE MENU *****
            1. Display available Bikes
            2. Request a bike on hourly basis $ 5
            3. Request a bike on daily basis $ 84
            4. Return a bike
            5. Main Menu
            6. Exit

By pressing "1" from the menu here, we can instantly view the current number of vehicles in stock and return bike menu.

Enter choice: 1
100 vehicle available to rent
Thank you for using the vehicle rental shop

            ***** BIKE MENU *****
            1. Display available Bikes
            2. Request a bike on hourly basis $ 5
            3. Request a bike on daily basis $ 84
            4. Return a bike
            5. Main Menu
            6. Exit

By pressing "2" for daily rent, we can go to the stage asking how many bikes we want to rent and enter the amount we want and complete the rental stage.
After doing this, if we send a request to the stock, we can naturally view the deducted version of the amount we rented from the stock. Then return main menu.

            Enter choice: 2
            How many bikes would you like to rent? 45
            Rented a 45 vehicle for hourly at 19 hours
            -----------------------
            Thank you for using the vehicle rental shop

                        ***** Vehicle Rental Shop *****
                        A. Bike Menu
                        B. Car Menu
                        Q. Exit
            Enter choice: 

When we want to return bike we can follow same steps for entering bike menu. After that we can return rented bike by pressing "4". At this stage, informational texts about our invoice for how long we have rented are displayed.

Enter choice: 4
You have extra %20 discount
Thank you for returning your bike
Price : $ 6.9
Thank you for using the vehicle rental shop

As seen in the menu, we can return to the main menu by pressing "5" or exit the entire program by pressing "6".

The same steps apply to the car menu. 

Also, when a value other than the desired values is entered in these menus, it gives a warning and informs and returns to the main menu.
