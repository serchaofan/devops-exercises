# Jenkins

<details>
<summary>What is Jenkins? What have you used it for?</summary><br><b>

Jenkins is an open source automation tool written in Java with plugins built for Continuous Integration purpose. Jenkins is used to build and test your software projects continuously making it easier for developers to integrate changes to the project, and making it easier for users to obtain a fresh build. It also allows you to continuously deliver your software by integrating with a large number of testing and deployment technologies.

Jenkins integrates development life-cycle processes of all kinds, including build, document, test, package, stage, deploy, static analysis and much more.

</b></details>

<details>
<summary>What are the advantages of Jenkins over its competitors? Can you compare it to one of the following systems?

- Travis
- Bamboo
- Teamcity
- CircleCI</summary><br><b>
  </b></details>

<details>
<summary>What are the limitations or disadvantages of Jenkins?</summary><br><b>
</b></details>

<details>
<summary>Explain the following:

- Job
- Build
- Plugin
- Slave
- Executor</summary><br><b>
  </b></details>

<details>
<summary>What plugins have you used in Jenkins?</summary><br><b>
</b></details>

<details>
<summary>Explain CI/CD and how you implemented it in Jenkins</summary><br><b>
</b></details>

<details>
<summary>What type of jobs are there? Which types have you used?</summary><br><b>
</b></details>

<details>
<summary>How did you report build results to users? What ways are you familiar with for reporting results?</summary><br><b>
</b></details>

<details>
<summary>You need to run unit tests every time a change submitted to a given project. Describe in details how your pipeline would look like and what will be executed in each stage</summary><br><b>
</b></details>

<details>
<summary>How to secure Jenkins?</summary><br><b>
</b></details>

<details>
<summary>Can you describe some of Jenkins best practices?</summary><br><b>
</b></details>

<details>
<summary>Describe how do you add new slaves to Jenkins</summary><br><b>

You can describe the UI way to add new slaves but better to explain how to do in a way that scales like a script or using dynamic source for slaves like one of the existing clouds.
</b></details>

<a name="jenkins-advanced"></a>

<details>
<summary>How to acquire multiple slaves for one specific build?</summary><br><b>
</b></details>

<details>
<summary>There are four teams in your organization. How to prioritize the builds of each team? So the jobs of team x will always run before team y for example</summary><br><b>
</b></details>

<details>
<summary>If you are managing a dozen of jobs, you can probably use the Jenkins UI. How do you manage the creation and deletion of hundreds of jobs every week/month?</summary><br><b>
</b></details>

<details>
<summary>What are some of Jenkins limitations?</summary><br><b>

- Testing cross-dependencies (changes from multiple projects together)
- Starting builds from any stage (although cloudbees implemented something called checkpoints)
  </b></details>

<details>
<summary>How would you implement an option of a starting a build from a certain stage and not from the beginning?</summary><br><b>
</b></details>

#### Jenkins Dev

<details>
<summary>Do you have experience with developing a Jenkins plugin? Can you describe this experience?</summary><br><b>
</b></details>

<details>
<summary>Have you written Jenkins scripts? If yes, what for and how they work?</summary><br><b>
</b></details>

#### Jenkins Integration

<details>
<summary>How would you collect logs from Jenkins builds (not master) and display them to user via Kibana? Describe the process, components, etc.<br>
<img src="images/jenkins/jenkins-to-kibana.png" width="621x;" height="171px;"/>
</summary><br><b>
</b></details>
