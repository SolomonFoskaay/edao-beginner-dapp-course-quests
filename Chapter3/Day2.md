## CHAPTER 3

### DAY 2
For todays quest, please load up a new Flow playground by going to https://play.onflow.org just like we did in this lesson. You will use that for writing your code.


#### QUESTION 1: 
Explain why we wouldn't call changeGreeting in a script.
#### ANSWER: 
We wouldn't call changeGreeting in a script because it will change data on the Blockchain which script can not do since it can only read from the Blockchain

<br>
<hr>
<br>

#### QUESTION 2: 
What does the AuthAccount mean in the prepare phase of the transaction?
#### ANSWER: 
AuthAccount means requesting approval from address owner to access the account data/storage to be able to process transaction.

<br>
<hr>
<br>

#### QUESTION 3: 
What is the difference between the prepare phase and the execute phase in the transaction?
#### ANSWER: 
The difference between them is that prepare phase gain access to AuthAccount, then pass it down to execute phase where transaction can be executed

<br>
<hr>
<br>

#### QUESTION 4: 
This is the hardest quest so far, so if it takes you some time, do not worry! I can help you in the Discord if you have questions.

1. Add two new things inside your contract:

- A variable named myNumber that has type Int (set it to 0 when the contract is deployed)
- A function named updateMyNumber that takes in a new number named newNumber as a parameter that has type Int and updates myNumber to be newNumber

#### ANSWER: 
<img src="https://github.com/SolomonFoskaay/edao-beginner-dapp-course-quests/blob/main/Media/Screenshots/edao-beginner-dapp-course-Ch3Day2a-Contract.png" width="100%" height="100%">

2. Add a script that reads myNumber from the contract

#### ANSWER: 
<img src="https://github.com/SolomonFoskaay/edao-beginner-dapp-course-quests/blob/main/Media/Screenshots/edao-beginner-dapp-course-Ch3Day2b-Script.png" width="100%" height="100%">


3. Add a transaction that takes in a parameter named myNewNumber and passes it into the updateMyNumber function. Verify that your number changed by running the script again.
#### ANSWER: 
<img src="https://github.com/SolomonFoskaay/edao-beginner-dapp-course-quests/blob/main/Media/Screenshots/edao-beginner-dapp-course-Ch3Day2c1-Transaction.png" width="100%" height="100%">

Number updated:

<img src="https://github.com/SolomonFoskaay/edao-beginner-dapp-course-quests/blob/main/Media/Screenshots/edao-beginner-dapp-course-Ch3Day2c2-Script.png" width="100%" height="100%">


  
