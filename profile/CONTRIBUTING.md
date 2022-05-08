# Hi!

- Hello contributors, My name is Daniel. If you ever find yourself on this page, that means you are probably interesed in contributing to this project. If this is the case then you are noticing that this file is virtually empty. It means i have yet to find the time to write this MD. If you are reading this doc and are eager to contribute, feel free to create an issue on this repo and I will reply. Cheers!

For developers trying to get started developing, the first step is to know how to start the entire ecosystem in development mode, here are the tools to get you started:

1. start randnote-blockchain:

   ```yarn run dev``` this will start the server on port 8033

   To make a test transaction, navigate to the directory ```  ./dist/tests/testTransaction.js ```  and run the file ``` node testTransaction.js ```. This will create a transaction to a particular address.

   To make a mine, navigate to the directory ```./dist/tests/testMine.js``` and run ``` node testMine samuel``` , I used samuel here as the public address, this is an argument, the application takes one argument which is the public address and this address is the one that mines the block. So you can use any address you wish.

2. Start the website

   Start by running the randnotex-backend. ```yarn run dev``` . This will run the application on port 8034