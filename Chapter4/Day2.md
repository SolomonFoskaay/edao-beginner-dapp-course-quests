## CHAPTER 4

### DAY 1
Feel free to answer in a language you're most comfortable in.


#### QUESTION 1: 
How did we get the address of the user? Please explain in words and then in code.

#### ANSWER: 
In Word:

We get the address of the users after user successfully approve login through their wallet like Blockto. The user authAccount access details received via Blockto is passed and saved in the dApp variable we declared named "User".

From the "User" variable, we can check for things like, is user loggedin? If YES, then check the wallet details logged in with, which contains details like the address, storage and more. From there we display the address (which actually replaces the Login button text).

But, If user is not logged-in, our user variable is empty and so the button text have to show default login text.


In Code:
<img src="https://github.com/SolomonFoskaay/edao-beginner-dapp-course-quests/blob/main/Media/Screenshots/edao-beginner-dapp-course-Ch4Day1a-Code-wallet.png" width="100%" height="100%">

<br>
<hr>
<br>

#### QUESTION 2: 
What do fcl.authenticate and fcl.unauthenticate do?
#### ANSWER: 
fcl.authenticate is use to login user

fcl.unauthenticate is use to logout user

<br>
<hr>
<br>

#### QUESTION 3: 
Why did we make a config.js file? What does it do?
#### ANSWER: 
We make the config.js file to connect our App to the Blockchain which turn it to a dApp

In addition, it does the work of allowing user login/logout in our dApp via Flow Client Discovery using integrated wallets like Blockto

<br>
<hr>
<br>

#### QUESTION 4: 
What does our useEffect do?

#### ANSWER: 
UseEffect is a react function which runs a set of code in it everytime a condition set inside it [ ] is fulfilled. In our dApp case it is empty, which means at every refresh of the page, it triggers useEffect to run the code block in its { } which is fcl.currentUser.subscribe(setUser).

<br>
<hr>
<br>

#### QUESTION 5: 
How do we import FCL?

#### ANSWER: 
We import FCL using the following line of code in our Nav.jsx to enable us call functions to login/logout user in our dApp:
~~~cadence
import * as fcl from "@onflow/fcl";
~~~

<br>
<hr>
<br>

#### QUESTION 6: 
What does fcl.currentUser.subscribe(setUser); do?

#### ANSWER: 
fcl.currentUser.subscribe(setUser); do help preserve state of variable (in our case, the "user" variable) consistently.

For example, if a use login into our dApp with multiple pages, then scroll to another page within the dApp, normally the user might be logged out because the variable state would also changed back to logged out. To avoid this frustrating issue, when combined with useEffect, it help keep the variable state as expected. So, even if user navigate and refresh pages multiple times without logging out, they remain loggedin too as long as useEffect runs our fcl.currentUser.subscribe(setUser);. 



  
