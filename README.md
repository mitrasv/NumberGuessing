# NUS FinTech DevOps Course - CI/CD Show & Tell

Standard CI/CD pipeline </br>
![image](https://user-images.githubusercontent.com/116928781/206625888-4353aeed-ede0-44a1-8033-4f7577989a9e.png)

For this task, I've modified a simple guess-the-number/higher-or-lower project that I found interesting on Github, from **Aanchal1201/NumberGuessing** . 

CI/CD pipeline

(to insert info once I come up with it)







# Learnings:
1) Time management + Flask </br>
I first tried to **code the entire programme from scratch**, which proved to be (obviously) very time-consuming, and not feasible to complete within a few days at my current skill level. Hence, I decided to piggyback off of others' code for the same programme, which showed me how unoriginal my idea was. I spent some time working on a forked version of cmlohr/flask_higher_lower, which used **Flask, a micro web framework** which should have allowed me to publish a static page directly from GitHub Pages or Netlify without need for a backend to be hosted. However, I could not get it to run on either despite troubleshooting, so I instead opted for a JS + HTML + CSS one I was more familiar with. 

2) Web hosting </br>
I hosted my programme in both GitHub Pages and Netlify

3) CI/CD stuff, I guess </br>
I copied the basic CI workflow template for Node.js projects from GitHub, but it failed due to exit code 254, as below:
![image](https://user-images.githubusercontent.com/116928781/206542988-3b3bdae7-ed36-4990-bf78-1ba384d49bf0.png)

Looking at the error, it was due to the lack of the package.json , which my project wasn't using. 
![image](https://user-images.githubusercontent.com/116928781/206543153-1a25e515-8f3d-4388-8cc3-c673162ddc67.png)

A quick Google search showed that I didn't need to install and test for npm, so I commented out those lines of code.
![image](https://user-images.githubusercontent.com/116928781/206543585-f76fd72d-73e5-4b25-bc82-90f39041d565.png)

And it worked fine after that!
![image](https://user-images.githubusercontent.com/116928781/206543824-88a0ee3d-5b9e-4207-b556-ad556b91bdfe.png)

______________________________________________________________________________________________________________________________________________________


Project requirements:
![image](https://user-images.githubusercontent.com/116928781/206533948-3b2380d6-ea1b-4d92-a0ec-3a6ea4d1c68e.png)
