# NUS FinTech DevOps Course - CI/CD Show & Tell

## Standard CI/CD pipeline </br>
![image](https://user-images.githubusercontent.com/116928781/206625888-4353aeed-ede0-44a1-8033-4f7577989a9e.png)

For this task, I've modified a simple guess-the-number/higher-or-lower project that I found interesting on Github, from **Aanchal1201/NumberGuessing** . </br>
Link: https://mitrahigherlower.netlify.app/
<br/>In this project, the user can choose between 3 difficulty modes, and then has a fixed number of attempts to guess the randomly-generated number. It uses a JavaScript file for the number checking logic, a single HTML page, and a CSS file for aesthetics of the site. 

## Learnings:
1) Time management + Flask </br>
I first tried to **code the entire programme from scratch**, which proved to be (obviously) very time-consuming, and not feasible to complete within a few days at my current skill level. Hence, I decided to piggyback off of others' code for the same programme, which showed me how unoriginal my idea was. I spent some time working on a forked version of cmlohr/flask_higher_lower, which used **Flask, a micro web framework** which should have allowed me to publish a static page directly from GitHub Pages or Netlify without need for a backend to be hosted. However, I could not get it to run on either despite troubleshooting, so I instead opted for a JS + HTML + CSS one I was more familiar with. 

2) Web hosting </br>
I hosted my programme in both GitHub Pages (https://mitrasv.github.io/NumberGuessing/) and Netlify (https://mitrahigherlower.netlify.app/) . Both are simple and fuss-free for a small project like this.

3a) CI/CD implementation - Auto-compiling and testing </br>
I copied the basic CI workflow template for Node.js projects from GitHub, but it failed due to exit code 254, as below:
![image](https://user-images.githubusercontent.com/116928781/206542988-3b3bdae7-ed36-4990-bf78-1ba384d49bf0.png)

Looking at the error, it was due to the lack of the package.json , which my project wasn't using. 
![image](https://user-images.githubusercontent.com/116928781/206543153-1a25e515-8f3d-4388-8cc3-c673162ddc67.png)

A quick Google search showed that I didn't need to install and test for npm, so I commented out those lines of code.
![image](https://user-images.githubusercontent.com/116928781/206543585-f76fd72d-73e5-4b25-bc82-90f39041d565.png)

And it worked fine after that!
![image](https://user-images.githubusercontent.com/116928781/206543824-88a0ee3d-5b9e-4207-b556-ad556b91bdfe.png)

3b) CI/CD implementation - Telegram message when commits are made to this GitHub repo </br>
Following this guide (https://github.com/marketplace/actions/telegram-notify), I created a Telegram bot (@MitraGithubAction_bot), using that TELEGRAM_TOKEN and my personal Telegram Chat ID for the TELEGRAM_TO, as the secrets for this action. 

![image](https://user-images.githubusercontent.com/116928781/206648103-ef5424aa-dd48-407a-a08a-fa81ec90ae0c.png)

Successful implementation:
![image](https://user-images.githubusercontent.com/116928781/206648395-1b7939fe-ddf5-4761-b018-b1124ae75021.png)

______________________________________________________________________________________________________________________________________________________
