# Mobile testing w/ Appium + Java

Mobile automated testing using Appium and Java

> Before we start, open this in a new tab and let the container load.

[![Try in Gitpod](https://gitpod.io/button/open-in-gitpod.svg)](https://gitpod.io/#https://github.com/eyaly/mobile-appium-java-workshop)

## 🧠You will learn to

* What is Appium
* Create an automated Android test
* Create an automated iOS test
* Find element locators using Appium Inspector
* Run tests in Sauce Labs real devices
* Run tests in parallel

## Testing for Good

### 🌎Testing for Good enables great test automation engineering while shaping a more equitable society.👩‍💻

Today, we're asking for donations for [Environmental Working Group](https://buy.stripe.com/9AQdU42lj9i7bHGcMN)

### [About Environmental Working Group](https://www.ewg.org/)

We're advocates who won't quit. We're scientists that find solutions. We're people trying to make the safest choices for our health. At the Environmental Working Group, we believe that you should have easy access to the information you need to make smart, healthy choices. It’s this belief that inspired our president and co-founder, Ken Cook, to create EWG.  

Since 1993, we've worked tirelessly to protect public health. Whether it's spotlighting harmful industry standards, speaking out against outdated government legislation or empowering consumers with breakthrough education and research, we're in this fight. 

And we're not going anywhere.

👉 While the event is free, Sauce Labs encourages all attendees to 

👉 **[donate](https://buy.stripe.com/9AQdU42lj9i7bHGcMN)** 

Anything helps! 

100% of donations go to support the cause.

## Key

💡 this is a tip

🏋️‍♀️ this is an exercise for you to do

❓ this is a question for us to think and talk about. Try not to scroll beyond this question before we discuss


## Your Instructor: Eyal Yovel

<img src="./graphics/EyalAvatar.png" alt="me" width="200"/>


- 🏢 I’m a Sr Solutions Architect at Sauce Labs
- 😄 Pronouns: he/him
- 📫 &nbsp; Links: 
</br>[![LinkedIn](https://img.shields.io/badge/LinkedIn-0077B5?style=for-the-badge&logo=linkedin&logoColor=white)](https://www.linkedin.com/in/eyal-yovel-9786933/)
[![Twitter](https://img.shields.io/badge/Twitter-1DA1F2?style=for-the-badge&logo=twitter&logoColor=white)](https://twitter.com/eyalyovel)
[![Github](https://img.shields.io/badge/Github-100000?style=for-the-badge&logo=github&logoColor=white)](https://github.com/eyaly/)

## Your TA:

---
## Setup  

---
### Sauce Labs setup
1. Free [Sauce account](https://saucelabs.com/sign-up)
2. Make sure you know how to find your Sauce Labs Username and Access Key by going to the [Sauce Labs user settings page](https://app.saucelabs.com/user-settings)

---
### Appium setup
1. We will run our automated tests on Sauce Labs devices; therefore, there is no need to install Appium Server.
2. Please install [appium inspector](https://github.com/appium/appium-inspector#installation). Appium Inspector is basically just an Appium client (like WebdriverIO, Appium's Java client, etc...) with a user interface. 

---
### Gitpod setup

ℹ Gitpod lets you run an entire Dev environment from a browser! You can use this approach if you don't have time or you don't know how to setup a local Java environment.

1. Sign up for a free [GitHub account](https://github.com/)
2. [Fork this repository](https://docs.github.com/en/get-started/quickstart/fork-a-repo)
 * Make sure you are logged into GitHub
 * Click the Fork in the upper right of the GitHub.
 * Give the repo a ⭐ while you're here 🤩
3. In the browser address bar, your GitHub url (`https://github.com/USERNAME/this-repo-name`) with `https://gitpod.io/#`
    * The resulting url should look as follows:
   
      > https://gitpod.io/#https://github.com/USERNAME/mobile-appium-java-workshop
   
4. Once the Gitpod.io URL is loaded, you will need to sign in with the GitHub account you created earlier 
5. Once the development environment is loaded, you should see 'Ready to test!' in the Terminal window in the lower portion of the window, run the following commands in that Terminal to set your `SAUCE_USERNAME`, `SAUCE_ACCESS_KEY`:

```bash
eval $(gp env -e SAUCE_USERNAME=<sauce_username>)
eval $(gp env -e SAUCE_ACCESS_KEY=<sauce_access_key>)
```

> Replace <sauce_username>, <sauce_access_key> with your credentials

Once you have run those 2 commands, you can run the following commands to test your environment variables:

```bash
echo $SAUCE_USERNAME
echo $SAUCE_ACCESS_KEY
```

Run sanity tests

```bash
mvn clean test -DtestngXmlFile=myDemoTests.xml
```

<br/>
  <details>
    <summary>
      <strong>Click here</strong> to see an example console output.
    </summary>

    [INFO] -------------------------------------------------------
    [INFO]  T E S T S
    [INFO] -------------------------------------------------------
    [INFO] Running TestSuite
    *** BeforeMethod hook. Running method demoTest ***
    region is us
    *** Start demoTest test ***
    *** AfterMethod hook ***
    [INFO] Tests run: 1, Failures: 0, Errors: 0, Skipped: 0, Time elapsed: 0.488 s - in TestSuite
    [INFO] 
    [INFO] Results:
    [INFO] 
    [INFO] Tests run: 1, Failures: 0, Errors: 0, Skipped: 0
    [INFO] 
    [INFO] ------------------------------------------------------------------------
    [INFO] BUILD SUCCESS
    [INFO] ------------------------------------------------------------------------
    [INFO] Total time:  3.579 s
    [INFO] Finished at: 2022-07-04T12:05:35+01:00
    [INFO] ------------------------------------------------------------------------

  </details>

<br/>

#### In the next video I demo how to fork the repo and connect to Gitpod:

https://user-images.githubusercontent.com/6969588/177877688-f735e152-991d-4c7e-a326-0a9a2969fea9.mp4




***✅👏Environment setup is complete if tests passed***

---

### Local environment setup

1. Sign up for a free [GitHub account](https://github.com/)
2. [Fork this repository](https://docs.github.com/en/get-started/quickstart/fork-a-repo)
 * Make sure you are logged into GitHub
 * Click the Fork in the upper right of the GitHub.
 * Give the repo a ⭐ while you're here 🤩
3. Clone **your fork** of the repository to your machine. Must have [Git installed](https://git-scm.com/downloads)

```bash
git clone URL_OF_YOUR_FORK
```

Setup environment variables on your system
* [Mac/Linux](https://docs.saucelabs.com/basics/environment-variables/#setting-up-environment-variables-on-macos-and-linux-systems)
* [Windows](https://docs.saucelabs.com/basics/environment-variables/#setting-up-environment-variables-on-windows-systems)

Run sanity tests

```java
mvn clean test -DtestngXmlFile=myDemoTests.xml
```

<br/>
  <details>
    <summary>
      <strong>Click here</strong> to see an example console output.
    </summary>

    [INFO] -------------------------------------------------------
    [INFO]  T E S T S
    [INFO] -------------------------------------------------------
    [INFO] Running TestSuite
    *** BeforeMethod hook. Running method demoTest ***
    region is us
    *** Start demoTest test ***
    *** AfterMethod hook ***
    [INFO] Tests run: 1, Failures: 0, Errors: 0, Skipped: 0, Time elapsed: 0.488 s - in TestSuite
    [INFO] 
    [INFO] Results:
    [INFO] 
    [INFO] Tests run: 1, Failures: 0, Errors: 0, Skipped: 0
    [INFO] 
    [INFO] ------------------------------------------------------------------------
    [INFO] BUILD SUCCESS
    [INFO] ------------------------------------------------------------------------
    [INFO] Total time:  3.579 s
    [INFO] Finished at: 2022-07-04T12:05:35+01:00
    [INFO] ------------------------------------------------------------------------

  </details>

</br>

***✅👏Environment setup is complete if tests passed***

## Extra resources

- [Appium options for sauce](https://docs.saucelabs.com/dev/test-configuration-options/#mobile-app-appium-capabilities-required)
- [All appium capabilities](https://appium.io/docs/en/writing-running-appium/caps/)
- [More Appium resources](https://github.com/saucelabs-training/demo-java/blob/main/TRAINING.md)

## Conclusions
Please leave [quick and anonymous feedback on this workshop](https://docs.google.com/forms/d/e/1FAIpQLSfhKpfdRU9FuqYMfFyqD3GhjdYADzZikjes7boVErWlru4XBA/viewform)