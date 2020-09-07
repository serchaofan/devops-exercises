# DNS

<details>
<summary>什么是DNS，用来作什么?</summary><br><b>

DNS (Domain Name Systems) is a protocol used for converting domain names into IP addresses.<br>
As you know computer networking is done with IP addresses (layer 3 of the OSI model) but for as humans it's hard to remember IP addresses, it's much easier to remember names. This why we need something such as DNS to convert any domain name we type into an IP address. You can think on DNS as a huge phonebook or database where each corresponding name has an IP.
</b></details>

<details>
<summary>DNS如何工作?</summary><br><b>

In general the process is as follows:

- The user types an address in the web browser (some_site.com)
- The operating system gets a request from the browser to translate the address the user entered
- A query created to check a local entry of the address exists in the system. In case it doesn't, the request is forwarded to the DNS resolver
- The Resolver is a server, usually configured by your ISP when you connect to the internet, that responsible for resolving your query by contacting other DNS servers
- The Resolver contacts the root nameserver (aka as .)
- The root nameserver responds with the address of the relevant Top Level Domain DNS server (if your address ends with org then the org TLD)
- The Resolver then contacts the TLD DNS and TLD DNS responds with the IP address that matches the address the user typed in the browser
- The Resolver passes this information to the browser
- The user is happy :D
  </b></details>

<details>
<summary>DNS记录有哪些类型?</summary><br><b>

- A
- PTR
- MX
- AAAA
  </b></details>

<details>
<summary>A记录是什么?</summary><br><b>

A (Address) Maps a host name to an IP address. When a computer has multiple adapter cards and IP addresses, it should have multiple address records.

</b></details>

<details>
<summary>AAAA记录是什么?</summary><br><b>
</b></details>

<details>
<summary>PTR记录是什么?</summary><br><b>

While an A record points a domain name to an IP address, a PTR record does the opposite and resolves the IP address to a domain name.
</b></details>

<details>
<summary>MX记录是什么?</summary><br><b>
MX (Mail Exchange) Specifies a mail exchange server for the domain, which allows mail to be delivered to the correct mail servers in the domain.

</b></details>

<details>
<summary>DNS用TCP还是UDP?</summary><br><b>

DNS 使用的是 UDP，端口 53。但如果请求头大于 512 字节，则会使用 TCP 发送，因为 UDP 头最大就 512 字节。TCP 端口也是 53
</b></details>

<details>
<summary>什么是轮询DNS?</summary><br><b>
</b></details>

<details>
<summary>什么是DNS记录的TTL，需要吗？</summary><br><b>
</b></details>

<details>
<summary>What is a zone? What types of zones are there?</summary><br><b>
</b></details>
