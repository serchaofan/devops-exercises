# Design

#### Architecture

<details>
<summary>Explain "3-Tier Architecture" (including pros and cons)</summary><br><b>
</b></details>

<details>
<summary>What are the drawbacks of monolithic architecture?</summary><br><b>

- Not suitable for frequent code changes and the ability to deploy new features
- Not designed for today's infrastructure (like public clouds)
- Scaling a team to work monolithic architecture is more challenging
  </b></details>

<details>
<summary>What are the advantages of micro-services architecture over a monolithic architecture?</summary><br><b>
</b></details>

#### Scalability

<details>
<summary>Explain Vertical Scaling</summary><br><b>

Vertical Scaling is the process of adding resources to increase power of existing servers. For example, adding more CPUs, adding more RAM, etc.
</b></details>

<details>
<summary>Explain Horizontal Scaling</summary><br><b>

Horizontal Scaling is the process of adding more resources that will be able handle requests as one unit
</b></details>

<details>
<summary>How would you update each of the services in the following drawing without having app (foo.com) downtime?<br>
<img src="images/design/cdn-no-downtime.png" width="300x;" height="400px;"/>
</summary><br><b>
</b></details>

<details>
<summary>What is the problem with the following architecture and how would you fix it?<br>
<img src="images/design/producers_consumers_issue.png" width="400x;" height="300px;"/>
</summary><br><b>

The load on the producers or consumers may be high which will then cause them to hang or crash.<br>
Instead of working in "push mode", the consumers can pull tasks only when they are ready to handle them. It can be fixed by using a streaming platform like Kafka, Kinesis, etc. This platform will make sure to handle the high load/traffic and pass tasks/messages to consumers only when the ready to get them.

<img src="images/design/producers_consumers_fix.png" width="300x;" height="200px;"/>
</b></details>

<details>
<summary>Users report that there is huge spike in process time when adding little bit more data to process as an input. What might be the problem?<br>
<img src="images/design/input-process-output.png" width="300x;" height="200px;"/>
</summary><br><b>
</b></details>

<details>
<summary>How would you scale the architecture from the previous question to hundreds of users?</summary><br><b>
</b></details>

#### Migrations

<details>
<summary>How you prepare for a migration? (or plan a migration)</summary><br><b>

You can mention:

roll-back & roll-forward
cut over
dress rehearsals
DNS redirection
</b></details>

<details>
<summary>Explain "Branch by Abstraction" technique</summary><br><b>
</b></details>
