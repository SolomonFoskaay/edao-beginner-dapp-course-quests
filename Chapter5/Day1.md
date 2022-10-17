## CHAPTER 5

### DAY 1
We have officially completed our Emerald DApp. The only remaining step is to deploy our DApp so everyone can see it....


#### QUESTION 1: 
List all the possible transaction status codes and what each of them mean.
#### ANSWER: 
Done as seen below (as seen on flow documentation):

<img src="https://github.com/SolomonFoskaay/edao-beginner-dapp-course-quests/blob/main/Media/Screenshots/edao-beginner-dapp-course-Ch5Day1a-Status-Code-For-Transaction.png" width="100%" height="100%">


<br>
<hr>
<br>

#### QUESTION 2A: 
What does setTimeout do?
#### ANSWER: 
setTime help to keep watch of time and ensure the txStatus changes back to default "Run Transaction" in 2seconds only after the transaction is successfully executed and sealed.




<br>
<hr>
<br>

#### QUESTION 2B: 
How would we change our code if we wanted the txStatus variable to reset back to its original state after 5 seconds?
#### ANSWER: 
We need to change the setTime code as follow:

~~~javascript
setTimeout(() => setTxStatus('Run Transaction'), 5000); // execute after 5 seconds
~~~

<br>
<hr>
<br>

#### QUESTION 3: 
What does the fcl.tx(transactionId).subscribe(res => {...}) function do?
#### ANSWER: 
The fcl.tx(transactionId).subscribe(res => {...}) function help access emitted transaction events from the Blockchain about the state of the transaction. And, it changes as the transaction goes from one processing state to another.

<br>
<hr>
<br>

#### QUESTION 4: 
Make at least 3 changes to the styling of the application. It can be anything (part of this quest is being creative!). List the 3 changes and point them out in a screenshot.
#### ANSWER: 
3 simple changes below (lazzzzzzzzzy me..lol):

<img src="https://github.com/SolomonFoskaay/edao-beginner-dapp-course-quests/blob/main/Media/Screenshots/edao-beginner-dapp-course-Ch5Day1b-Style-Changes.png" width="100%" height="100%">



