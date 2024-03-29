# Tic-Tac-Toe-game-c++-
-Our game is a single player versus AI . it uses min-max algorithm to play the role of AI.<br />
## - In a high level view we can look to our app as seperated parts<br />
   - 1)Front-end which job is to communicate with the user in app we achieve that through the console.<br />
  <br />
     <img src="https://github.com/saeedmabrouk21/Tic-Tac-Toe-game-cpp/assets/73306180/dd5c5acc-2cf0-4943-b916-f13191f87dff">
     <img src="https://github.com/saeedmabrouk21/Tic-Tac-Toe-game-cpp/assets/73306180/a0ab80bb-d97e-4520-a421-e1bc40db4329">
     <img src="https://github.com/saeedmabrouk21/Tic-Tac-Toe-game-cpp/assets/73306180/677da32d-d105-46dc-93ff-1fcd94a36b24">
     <img src="https://github.com/saeedmabrouk21/Tic-Tac-Toe-game-cpp/assets/73306180/e6982b5e-84ac-4059-80a6-07f7a5071efe">
     <img src="https://github.com/saeedmabrouk21/Tic-Tac-Toe-game-cpp/assets/73306180/117f5536-aba2-474c-933c-6d52fb1fcbdc">
     <img src="https://github.com/saeedmabrouk21/Tic-Tac-Toe-game-cpp/assets/73306180/a7059490-216c-4ee7-8d71-ddcba01014e9">
  <br />

   - 2)Game-engine (The Device) it implements how the functionalites of game work (e.g. how to save, how to load ..etc)<br />
   - 3)min-max Algortihm which nessarily used by Game engine <br />
## - Now the Idea is how to connect these pieces<br />
   1)Conect Front-end With game-engine : we Achieved this using **Command design pattern** which  encapsulates a request as an object, thereby letting us parameterize other objects with different requests.<br />
      To implement that we created differnt classes<br />
      ☼ **Front-end** class <br />
      ☼ **Tic-Tac_Toe** class which represnts Game-engine. It will contains implmentions of all commands<br />
      ☼ **ICommand** Interface which include a method excute<br />
      ☼ Different class for each command (**play**, **Save**, **Load** and **reset**) .each command uses the implmention in the Device class so it needs a device object or reference to device object<br />
      ☼ **Invoker** which responsible for execute commands - The **front-end** class inevitably owns the Invoker object.<br />
    with this setup front end can instantiate objects for any command and just pass to it refernce to device object then use invoker to execute the command<br />
    ![image](https://github.com/saeedmabrouk21/Tic-Tac-Toe-game-cpp/assets/73306180/ee32d829-b3ff-4af7-b9bd-1412896e92d8)
   2)Conect game-engine to min-max algorithm : Utilizing the min-max algorithm with various depth levels allows us to offer different difficulty levels. We used **Strategy design pattern** which separates the behavior of an object from the object itself<br />
     To implement that we created differnt classes<br />
     ☼**IDecisionMaker** interface (the game engine has an object of that interface, which behaves differently)
     ☼**Easy**, **Medium** and **Hard** classes implment IDecsionMaker
       **Easy** : will play in the first available place in the board
       **Medium** : will use **min-max** algorithm with depth = 2 
       **Hard** : will use **min-max** algorithm with depth = 9(max depth for board)
    ![image](https://github.com/saeedmabrouk21/Tic-Tac-Toe-game-cpp/assets/73306180/28077119-9a64-45d7-a6a7-4e70b45ee1ae)



## Full system UML  
![image](https://github.com/saeedmabrouk21/Tic-Tac-Toe-game-cpp/assets/73306180/85298d2d-fb6a-40c1-9312-c0034d6c44c6)




