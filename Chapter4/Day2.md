## CHAPTER 4

### DAY 2
You have a lot of tools under your belt now, in fact much more than you think you do. Let's see what you're capable of...


#### QUESTION 1: 
Instead of console logging the result after the script executes, I want you to:

- Make a new variable named greeting using useState
- Set the greeting variable to the response of the script call
- Create a <p> tag after the <div className={styles.flex}> tag
- Put the greeting variable inside of that <p> tag. This will make the result of your script show on your webpage! It should look something like this:

#### ANSWER: 
Done as seen below:

<img src="https://github.com/SolomonFoskaay/edao-beginner-dapp-course-quests/blob/main/Media/Screenshots/edao-beginner-dapp-course-Ch4Day2a-Home-Goodbye-Text.png" width="100%" height="100%">

<br>
<hr>
<br>

#### QUESTION 2A: 
I deployed a contract called SimpleTest to an account with an address of 0x6c0d53c676256e8c. I want you to make a button that, when clicked, executes a script to read the number variable from that contract. If you're curious, you can see the contract here: https://flow-view-source.com/testnet/account/0x6c0d53c676256e8c/contract/SimpleTest

Submit all the code you used to call the script, and the result of the script.
#### ANSWER: 
Smart contract number variable value uncovered as magic number below:



https://user-images.githubusercontent.com/83863629/195992611-e9b20f90-71e7-495b-9676-cf59e89ffcd6.mp4


  

 Source code used to create above is:
  
~~~javascript
import Head from 'next/head'
import styles from '../styles/Home.module.css'
import Nav from '../components/Nav.jsx'; //Import Nav component
import { useState, useEffect } from 'react'; //Import useState/UseEffect
import * as fcl from "@onflow/fcl" //Import FCL (Flow Client Library)



export default function Home() {

  // declare variable newGreeting
  const [newGreeting, setNewGreeting] = useState('');

  // declare variable greeting
  let [greeting, setGreeting] = useState('');

  // js runTransaction function for Run Transaction button
  function runTransaction() {
    console.log(newGreeting)
  }

  // Execute script on flow using FCL
  // async function executeScript() {
  //   const response = await fcl.query({
  //     // Cadence code in form of string goes in here
  //     cadence: `
  //       import HelloWorld from 0xb3e2d05cf2cdb97a

  //       pub fun main(): String {
  //           return HelloWorld.greeting
  //       }
  //     `,
  //     // Arguments used in above cadence code string goes in here
  //     args: (arg, t) => [] 
  //   })
  //   // set greeting variable to value of response
  //   greeting = response;
  //   document.getElementById("greeting").innerHTML=greeting; //create ID to access greeting value in html
  //   console.log("Response from our script is: " + greeting); //console log greeting value
  // }

    // Execute script on flow using FCL 2 for SimpleTest Quest
    async function executeScript() {
      const response = await fcl.query({
        // Cadence code in form of string goes in here
        cadence: `
          import SimpleTest from 0x6c0d53c676256e8c
  
          pub fun main(): Int {
              return SimpleTest.number
          }
        `,
        // Arguments used in above cadence code string goes in here
        args: (arg, t) => [] 
      })
      // set greeting variable to value of response
      greeting = response;
      document.getElementById("greeting").innerHTML=greeting; //create ID to access greeting value in html
      console.log("Magic Number Response From Our Script Is: " + greeting); //console log greeting value
    }

  // calling the script at every page refresh using useEffect
  // useEffect(() => {
  //   executeScript()
  // }, [])


  return (
    <div className={styles.container}>
      <Head>
        <title>Emerald DApp</title>
        <meta name="description" content="Created by Emerald Academy" />
        <link rel="icon" href="https://i.imgur.com/hvNtbgD.png" />
      </Head>

      {/* add nav bar component*/}
      <Nav />

      <main className={styles.main}>

        <h1 className={styles.title}>
          Welcome to my <a href="https://github.com/SolomonFoskaay/beginner-emerald-dapp" target="_blank">Emerald DApp!</a>
        </h1>

        {/* adding p tag from chap2day2 quest */}
        <p>
          Foskaay is Learning Cadence dApp Development For Flow Blockchain At Emerald DAO
        </p>

        {/* added div and buttons */}
        <div className={styles.flex}>
          <button onClick={runTransaction}>
            Run Transaction
          </button>

          {/* search keyword input */}
          <input onChange={(e) => setNewGreeting(e.target.value)} placeholder="Hello, Idiots!" />
        </div>

        {/* print greeting on homepage */}
        <p id="greeting"> Click Button Below To Uncover The Magic Number</p>

        {/* added div and buttons ... */}
        <div>
          <button onClick={executeScript}>
            Magic Number
          </button>
        </div>

      </main>
    </div>
  )
}
~~~

<br>
<hr>
<br>

#### QUESTION 2B: 
Then, I want you to remove the button, and make the script execute every time the page refreshes.

Submit all the code you used to do this.
#### ANSWER: 
Displaying the script execute every time the page refreshes:



https://user-images.githubusercontent.com/83863629/195996349-07bee414-1764-4515-885c-6fcc9c0e83e4.mp4


  
 
Source code:


~~~javascript
import Head from 'next/head'
import styles from '../styles/Home.module.css'
import Nav from '../components/Nav.jsx'; //Import Nav component
import { useState, useEffect } from 'react'; //Import useState/UseEffect
import * as fcl from "@onflow/fcl" //Import FCL (Flow Client Library)



export default function Home() {

  // declare variable newGreeting
  const [newGreeting, setNewGreeting] = useState('');

  // declare variable greeting
  let [greeting, setGreeting] = useState('');

  // js runTransaction function for Run Transaction button
  function runTransaction() {
    console.log(newGreeting)
  }

  // Execute script on flow using FCL
  // async function executeScript() {
  //   const response = await fcl.query({
  //     // Cadence code in form of string goes in here
  //     cadence: `
  //       import HelloWorld from 0xb3e2d05cf2cdb97a

  //       pub fun main(): String {
  //           return HelloWorld.greeting
  //       }
  //     `,
  //     // Arguments used in above cadence code string goes in here
  //     args: (arg, t) => [] 
  //   })
  //   // set greeting variable to value of response
  //   greeting = response;
  //   document.getElementById("greeting").innerHTML=greeting; //create ID to access greeting value in html
  //   console.log("Response from our script is: " + greeting); //console log greeting value
  // }

    // Execute script on flow using FCL 2 for SimpleTest Quest
    async function executeScript() {
      const response = await fcl.query({
        // Cadence code in form of string goes in here
        cadence: `
          import SimpleTest from 0x6c0d53c676256e8c
  
          pub fun main(): Int {
              return SimpleTest.number
          }
        `,
        // Arguments used in above cadence code string goes in here
        args: (arg, t) => [] 
      })
      // set greeting variable to value of response
      greeting = response;
      document.getElementById("greeting").innerHTML=greeting; //create ID to access greeting value in html
      console.log("Magic Number Response From Our Script Is: " + greeting); //console log greeting value
    }

  // calling the script at every page refresh using useEffect
  useEffect(() => {
    executeScript()
  }, [])


  return (
    <div className={styles.container}>
      <Head>
        <title>Emerald DApp</title>
        <meta name="description" content="Created by Emerald Academy" />
        <link rel="icon" href="https://i.imgur.com/hvNtbgD.png" />
      </Head>

      {/* add nav bar component*/}
      <Nav />

      <main className={styles.main}>

        <h1 className={styles.title}>
          Welcome to my <a href="https://github.com/SolomonFoskaay/beginner-emerald-dapp" target="_blank">Emerald DApp!</a>
        </h1>

        {/* adding p tag from chap2day2 quest */}
        <p>
          Foskaay is Learning Cadence dApp Development For Flow Blockchain At Emerald DAO
        </p>

        {/* added div and buttons */}
        <div className={styles.flex}>
          <button onClick={runTransaction}>
            Run Transaction
          </button>

          {/* search keyword input */}
          <input onChange={(e) => setNewGreeting(e.target.value)} placeholder="Hello, Idiots!" />
        </div>

        {/* print greeting on homepage */}
        <p id="greeting"> Autoloading...... The Magic Number</p>

        {/* added div and buttons ... */}
        {/* <div>
          <button onClick={executeScript}>
            Magic Number
          </button>
        </div> */}

      </main>
    </div>
  )
}
~~~

