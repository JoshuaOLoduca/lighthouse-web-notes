# Resources
- [Lecture](https://vimeo.com/667988807/693c788aec)
- [Code](https://github.com/idbentley/lighthouse-lectures/tree/main/flex-w5d1-full-w2d3-networking)
- [Slide](https://github.com/idbentley/lighthouse-lectures/blob/main/flex-w5d1-full-w2d3-networking/flex-w5d1-full-w2d3-networking.pdf)

# Introduction to networking
Talking about the layers of computer communication and how to use it.

1. Physcial
   - Underground cables
   - stelites
2. Link
    - Modem
      - wifi
      - ethernet
3. Network
    - IP Address
      - Software Based
      - IPv4
      - IPv6
    - Mac address
      - Firmware based
        - mostly hardware based
        - software is involved
4. Transport Protocols
    - Software based
    - TCP
      - Cares about integrity regarding destination recieving entire message and its in the proper order
    - UDP
      - Just sends out message and doesnt check to see if it was recieved correctly or not.
5. Application Layer
    - software based
    - http
    - ftp
    - telnet
    - nfs
    - smtp (email ?)
    - ssh
## TCP/IP Segmentation
### General rules
- Integrity is easy to check if we keep all the packets the same size.
- the smaller the messages, the easier/faster it is for the server hops to deal/work with it
### Packet rules
- Made out of segmants of desired data
- ip info
- sequence number
  - also total number of sequence
- acknowledgement number
  - BIG PART
  - deep topic
  - used to confirm with sender that the data was recieved
- cheksum data

## What is HTTP
- request-response based communication profile
- tls for client-server communication
- http is stateless

### Anatomy of http
- head
- body
- some other stuff I mised it though

- method
  - GET
  - POST
    - Write to resource
  - PUT
    - Update resource
  - PATCH
    - Partial update to resource
  - DELETE
    - delete resource
  - OPTION

- header
  - client ver and server ver
  - authorization
  - cookie
  - caching
  - accept
    - type of acceptable responses
  - CORS
    - security preferences

- body
  - contains the data we are POSTING, PUTING, PATCHING, etc
  - usually JSON

- A Status
  - howd it go. success/failure etc
  - 200
    - generic success
  - 201
    - resource created
  - 202
    - resource accepted and being worked on
  - 300
    - redirect
  - 301
    - MOVED PERMANENTLY
  - 302
    - found, temp redirect
  - 400
    - BAD REQUEST
      - your request is bad
  - 401
    - Unauthorized
  - 404
    - Nothing found at location
  - 500
    - Internal server error
    - something went wrong on the server end

## Code
[Nodejs net API](https://nodejs.org/api/net.html)

### Server.js
```js
// import the built in module
const net = require('net');
// network port to use
const port = 9696;

// creates the server object
const server = net.createServer()
// sets server to recieve data on port. will run function once its finished setting up
server.listen(port, () => {
  console.log('Server is listening on port ', port);
});

const listOfClients = [];
// set listener on connection event, and execute callback on event 

// executes same time as its defined
const nextID = (() => {
  let id = 0;
  return () => {
    id++;
    return id;
  }
})()
server.on('connection', clientSocket => {
  // sets 'language' to talk in
  // utf8 is for texting
  clientSocket.setEncoding('utf8');

  // id is set so clients can be distenguished from each other.
  clientSocket.id = nextID();
  //clientSocket is a reference to a client.


  listOfClients.push(clientSocket);
  console.log(clientSocket.id, 'is connected to the server');
  // Sends message using TCP to clientSocket
  clientSocket.write('Welcome to the server!\n')
  // Sets callback to run on even trigger
  clientSocket.on('data', message => {
    console.log(clientSocket.id, message);

    // send to everyone but
    for (const socket of listOfClients) {
      // But dont send it to self
      if (socket.id !== clientSocket.id) socket.write(`${clientSocket.id}: ${message}`);
      // alternative that doesnt send sender ID
      // if (socket.id !== clientSocket.id) socket.write(data);
    }

  });
});
```
### Client.js
```js
const net = require('net');
const readline = require('readline');

const rl = readline.createInterface({
  input: process.stdin
});

const client = net.createConnection({
  host: 'localhost',
  port: 9696
});

client.setEncoding('utf8');

// What to do when you recieve data
client.on('data', data => console.log(data))

// sends message to server
rl.on('line', input => {
  client.write(input, '\n')
});

// on line will send the text entered between hitting enter
// rl.on('line', input => {})

```