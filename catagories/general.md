# General

<details>
<summary>Define or Explain what is an API</summary><br><b>

I like this definition from [here](https://blog.christianposta.com/microservices/api-gateways-are-going-through-an-identity-crisis):

"An explicitly and purposefully defined interface designed to be invoked over a network that enables software developers to get programmatic access to data and functionality within an organization in a controlled and comfortable way."
</b></details>

<details>
<summary>What is latency?</summary><br><b>
</b></details>

<details>
<summary>What is bandwidth?</summary><br><b>
</b></details>

<details>
<summary>What is throughput?</summary><br><b>
</b></details>

<details>
<summary>When performing a search query, what is more important, latency or throughput? And how to assure that what managing global infrastructure?</summary><br><b>

Latency. To have a good latency, a search query should be forwarded to the closest datacenter.
</b></details>

<details>
<summary>When uploading a video, what is more important, latency or throughput? And how to assure that?</summary><br><b>

Throughput. To have a good throughput, the upload stream should be routed to an underutilized link.
</b></details>

<details>
<summary>What other considerations (except latency and throughput) are there when forwarding requests?</summary><br><b>

- Keep caches updated (which means the request could be forwarded not to the closest datacenter)
  </b></details>

#### Jira

<details>
<summary>Explain/Demonstrate the following types in Jira:

- Epic
- Story
- Task</summary><br><b>
  </b></details>

<details>
<summary>What is a project in Jira?</summary><br><b>
</b></details>

#### HTTP

<details>
<summary>What is HTTP?</summary><br><b>
</b></details>

<details>
<summary>Describe HTTP request lifecycle</summary><br><b>

- Resolve host by request to DNS resolver
- Client SYN
- Server SYN+ACK
- Client SYN
- HTTP request
- HTTP response
  </b></details>

<details>
<summary>True or False? HTTP is stateful</summary><br><b>

False. Server doesn't maintain state for incoming request.
</b></details>

<details>
<summary>How HTTP request looks like?</summary><br><b>

It consits of:

- Request line - request type
- Headers - content info like length, enconding, etc.
- Body (not always included)
  </b></details>

<details>
<summary>What HTTP method types are there?</summary><br><b>

- GET
- POST
- HEAD
- PUT
- DELETE
- CONNECT
- OPTIONS
- TRACE
  </b></details>

<details>
<summary>What HTTP response codes are there?</summary><br><b>

- 1xx - informational
- 2xx - Success
- 3xx - Redirect
- 4xx - Error, client fault
- 5xx - Error, server fault
  </b></details>

<details>
<summary>What is HTTPS?</summary><br><b>
</b></details>

<details>
<summary>Explain HTTP Cookies</summary><br><b>

HTTP is stateless. To share state, we can use Cookies.

TODO: explain what is actually a Cookie
</b></details>

<details>
<summary>What is HTTP Pipelining?</summary><br><b> 
</b></details>

<details>
<summary>What is a proxy?</summary><br><b> 
</b></details>

<details>
<summary>What is a reverse proxy?</summary><br><b> 
</b></details>

<details>
<summary>What is CDN?</summary><br><b> 
</b></details>

<details>
<summary>When you publish a project, you usually publish it with a license. What types of licenses are you familiar with and which one do you prefer to use?</summary><br><b>
</b></details>

#### Load Balancers

<details>
<summary>What is a load balancer?</summary><br><b> 
</b></details>

<details>
<summary>What load balancer algorithms are you familiar with?</summary><br><b>
</b></details>

<details>
<summary>What is an Application Load Balancer?</summary><br><b>
</b></details>

<details>
<summary>What is DNS load balancing? What its advantages? When would you use it?</summary><br><b>
</b></details>

#### Random

<details>
<summary>How a search engine works?</summary><br><b>
</b></details>

<details>
<summary>What is faster than RAM?</summary><br><b>
</b></details>

<details>
<summary>What is a memory leak?</summary><br><b>
</b></details>

<details>
<summary>What is your favorite protocol?</summary><br><b>

SSH
HTTP
DHCP
DNS
...
</b></details>

<details>
<summary>What is Cache API?</summary><br><b>
</b></details>

<details>
<summary>What is the C10K problem? Is it relevant today?</summary><br><b>

https://idiallo.com/blog/c10k-2016
</b></details>
