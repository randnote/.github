# Randnote Documentation

## What is RandNote? 
1. RandNote is a virtual crypto currency and ecosystem that was created by Daniel Mamphekgo as a learning demonstaration.

## Before you read further:
- This application is a makeshift blockchain NOT intended to be used in production or anywhere else(except for learning purposes)... So don't be too hard on how I built the chain and the entire ecosystem for that matter, just read, learn and make pull requests if you will...

## What does this ecosystem consist of ?
1. The server application(which is the project you are currently viewing)
2. The website; where users will be able to login, generate a private key and purchase the crypto note. They will also be able to buy with their bank cards(will virtuall be implemented). The users will not need to login to see the price of the the Note as it will be on the homepage.
3. The Mining tool(C++ application) which will let the user provide thier private key(generated through their website accounts).
4. A python script that will serve as an automator, to make automatic transactions. These are auto requests sent to the backend of the website.

## How does the mining work?
1. A client requests the block to be mined, the server delivers.
2. The client solves the hash and sends another request to the server, this time with the solved hash as a param.
3. The server gets the hash and compares it to its own hash that it too has been solving in the meantime. It gets the answer from the client and if they match, the block is added.
- You might be wondering- what will happend if there are multipe clients trying to solve the hash = answer is - the first to send the hash is the winner. all the others will get a status 200 however with a 'sorry, did not mine' message, and so they will try again for the next block.
- This means that the server application will always be running solving hashes as well(which is absolutely insane)... it is what it is.

## How many transactions per block?
- Currently that amount varies, We have not added a timer that only loads a new block after every 10 minutes(like Bitcoin), instead there could be as little as 1 to as many as a billion+ transactions because mining only happens when a 3rd party node asks to mine the block... 
- This is obviously a big issue and will be solved(so, contribute and solve it yourself lol).

## How does it all work? 
- The users create an account and login, they then create a wallet where a public and private key will be generated for them through the website. The system will encrypt the private keys before storing it in the backend.
- Users will also be able to virtually add their bank card and purchase crypto on the platform(website). Users will be able to send RandNote to other users via a public key. If the user sends Notes to a non existant address, the coin will therfore be lost forever.
- A user can decide to mine the crpto using the C++ & QT developed desktop application that they would need to install on their windows computers. The application will only require the users public address and all the rewards will be allocated to that particular address. If the user provides the wrong address then the Notes generated will be lost forever.
- With the generated Notes, the user can then transact with other users. 
- Users can opt to sell their Notes on the platform and get cash in Dollars as a result. 

## How does the Automator(Python script) work?
- The automator script will start of by creating a randomized list of names, these names will be the users that will be making random transactions. The fake users are stored in the backend of the website and they have their public and private and public keys stored along with them. These fake users are distinguishable from real users by their email addresses which have the prefix `randnote` after the `@` symbol.
- e.g of email addresses: `john_stones@randote.com`
- These fake users will then be allocated 10 000 notes by the blockchain. The fake users then start to randomly start transacting(sending notes to other fake users).
- At random intervals, the same fake users will also try to mine the blocks(provided there are blocks to be mined). 

## Convertions and money allocations
- When a user deposits money into the system( They choose to deposit in what currency and choose the value) e.g Sipho deposits R15 or James deposits $1, 
Both are the same value and should both equally purchase 1 RandNote(assuming thats the value of the Note at the time). When the user deposits, their balance will be shown on the system however they would still need to convert their $/R to Notes. 
- The system will work just like how any normal system would. If a user decides to sell/buy thier Note, a charge will be made and the company(the website) will earn money.

## Extras
- This is an Open source project. Any new ideas and additions are always welcome.
- This project should never be turned into a real platform that accepts real money as it is not stable and has alot of security risks.
- Price is manipulated by change in supply and by buy/sells... Buy/sells by taking last n transactions in db and checking if there is more demand or supplys. if ther is more demand then we increase price by a calculated precentage. and vice versa.

## For Developers:
- To contribute to this open source project, please read the contributing docs first.
- There is a contributing file in this repository and contributing files will be created in each respective repository if interest if given.

### Application test keys:
Test the application with these json reqs:
```json
{
    "fromAddress": "f224f9e944b73c51ee9a8140b65e8f06e1422a3fecc4c79fc8577bc80a427ce0",
    "fromAddressPrivateKey": "0465f31d0233efa00f829098040de97d254922bc6730a2f59bee6525e203a5c3f10168be5391b28eb9fa81a0aa87583040c2e9542b7aad50666577b446239d6fc3",
    "toAddress": "dfgd",
    "amount": 1
}
```

## Solution on how to create a market...
- Demand and supply: 
- allocate a decent amount of funds to the websites account(both monetarily and notes in blockchain).

## How do we actually determine the price...
- firstly allow the first transaction(to purchase the note- via backend) to go through and then a price will be determined from that.
- secondly, for every new transaction, setup a limit for the randomly generated users. Setup an upper and a lower limit in order to control price fluctuations.


## How the mining automation algorithm works?

## How the transactions automation algorithm works?



## Problems with this application design and how it was developed...
- There are too many uneccessary requests. There are places were i could have made requests and saved the response, so that i can use it elsewhere.
- In frontend, some components hold too much code where it could have been split amongst others or split into the actual page component. - this causes dev to look hard for components instead of it being intuitive.
- This application does not simulate the website(as a business) charging fees on users when they perform transactions.
- How the randnote user actually gets its balance is botched... and its botched coz i intentionally manipulated it. e.g when a user buys Notes, i reduce users balance however i do not take that money and give it to the randnote user
- In real blockchains, even if your computer as a note gets disconnected, whenever you reconnect, you still will find your coins/transactions in the blockchain... however ON randnote, there is one sever and I do not store the blockchain externally. This means that if the server goes down for whatever reason, all your transactions also go down with it. lol. Meaning that a server restart will destroy your Notes balance.
- Some solutions that belongs to the backend, ive implemented in the frontend( E.g. In transactions page, when sending notes to another user from user, I call the backend api from backend and sort it out there).
- All applications in this ecosystem do not make use of the env variables. Instead, the URLs for communication across the apps are listed as varibles in the index pages.

### More flaws discovered after development:
- In the backend, We call the backend API to do backend work. This is wrong because I could have just called the function iteself- in the backend. How this is structured makes the application very slow.
