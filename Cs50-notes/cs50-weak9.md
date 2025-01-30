# 1\. Internet
The **internet** is a worldwide system of computer networks that uses the **protocol suite** (*TCP/IP*) to communicate between networks and devices.

To transfer **data** from one network to another, we need to make *routing decisions*. The **data** could take multiple paths, such that when a router is congested, **data** can flow through another path.

*TCP/IP* are two protocols that allow computers to transfer **data** between them over the internet.

## 1\.1. IP
**IP** or **Internet Protocol** is a way by which computers can identify one another across the internet. Every computer has a unique address in the world, by this form #.#.#.#. Instead of the hashes, there are numbers that range from 0 to 255. **IP** addresses are 32-bits, meaning that these addresses could accomodate over 4 billion addresses. Newer versions of **IP** addresses can accomodate even more computers.

## 1\.2. TCP
**TCP** or **Transmission Control Protocol** is used to distinguish web services from one another. For example, 80 is used to denote *HTTP* and 443 is used to denote *HTTPS*. These numbers are **port numbers**. When information is sent from one location to another, an **IP** address and **TCP** port number are sent.

These protocols are also used to fragment large files into multiple parts called *packets*. For example, a large photo can be sent in multiple packets. When a packet is lost, **TCP/IP** can request missing packets again from the origin server. **TCP** will acknowledge when all the **data** has been transmitted and received.

## 1\.3. DNS
**DNS** or **Domain Name System** is a collection of servers on the internet that are used to route website addresses to a specific **IP** address, instead of needing the address for visiting the website.

**DNS** simply hold a table or database that links specific, fully qualified domain names to specific **IP** addresses.

## 1\.4. HTTP
**HTTP** or **Hypertext Transfer Protocol** is an application-level protocol that developers use to build things. When you see an address such as <https://www.example.com> you are actually implicitly visiting that address with a / at the end of it.

The **path** is what exists after that /. For example, <https://www.example.com/folder/file.html> visits example.com and browses for the folder and then visits the file named file.html.
### 1\.4.1. HTTP Methods
The **https** in the address is the protocol used to connect to that web address. **HTTP** utilizes *GET* or *POST* requests to ask for information from a server.

- *GET* is used to request **data** from a specified source. *GET* requests can be cached, remain in the browser history, can be bookmarked, should never be used when dealing with sensitive **data**, are only used to request **data**, not modify it.
- *POST* is used to send **data** to a server to create/update a resource. *POST* requests are never cached, do not remain in the browser history and cannot be bookmarked.
### 1\.4.2. HTTP Messages
When requesting a service from a web server, an error might occur, and the server might return an error code like 404 Not Found. The server always returns a message for every request. The most coomon message is 200 OK, which means that the request was successful.

List of all the HTTP status messages can be found here: <https://www.w3schools.com/tags/ref_httpmessages.asp>.

# 1\. HTML
**HTML** or **Hypertext Markup Language** is the standard markup language for web pages.

<!-- Demonstrates HTML -->

<!DOCTYPE html>

<html lang="en">
`    `<head>
`        `<title>Webpage - Title</title>
`    `</head>
`    `<body>
`        `Hello World!
`    `</body>

**HTML** is made up of *tags*, which may have some *attributes* that describe that *tag*.

- *tags* start end end with <>. Example: <title></title>.
- *attributes* provide additional information about *tags*. Example: <a href="https://www.example.com">Visit Example</a>.
# 1\. CSS
**CSS** or **Cascading Style Sheet** is another markup language that allows you to fine-tune the aesthetics of the **HTML** files.

<!-- Demonstrates inline CSS -->

<!DOCTYPE html>

<html lang="en">
`    `<head>
`        `<title>Webpage - Title</title>
`    `</head>
`    `<body style="text-align: center">
`        `<header style="font-size: large">
`            `Hello World!
`        `</header>
`        `<main style="font-size: medium">
`            `Homepage
`        `</main>
`        `<footer style="font-size: small">
`            `Copyright &#169; all rights reserved.
`        `</footer>
`    `</body>

<!DOCTYPE html>

<!-- Demonstrates external CSS -->

<html lang="en">
`    `<head>
`        `<link href="style.css" rel="stylesheet">
`        `<title>css</title>
`    `</head>
`    `<body class="centered">
`        `<header class="large">
`            `Hello World!
`        `</header>
`        `<main class="medium">
`            `Homepage
`        `</main>
`        `<footer class="small">
`            `Copyright &#169; all rights reserved.
`        `</footer>
`    `</body>
</html>
# 1\. JavaScript
**JavaScript** is the programming language of the web. It allows to dynamically read and modify the **HTML** document loaded into memory without the need to reload to see the changes. Similar to **CSS**, **JavaScript** can be used inside the **HTML** or in an external file.

<!-- Demonstrates the usage of JavaScript by dynamically changing the background color of the page -->

<!DOCTYPE html>

<html lang="en">
`    `<head>
`        `<title>background</title>
`    `</head>
`    `<body>
`        `<button id="red">R</button>
`        `<button id="green">G</button>
`        `<button id="blue">B</button>
`        `<script>

`            `let body = document.querySelector('body');
`            `document.querySelector('#red').addEventListener('click', function() {
`                `body.style.backgroundColor = 'red';
`            `});
`            `document.querySelector('#green').addEventListener('click', function() {
`                `body.style.backgroundColor = 'green';
`            `});
`            `document.querySelector('#blue').addEventListener('click', function() {
`                `body.style.backgroundColor = 'blue';
`            `});

`        `</script>
`    `</body>
</html>


