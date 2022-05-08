# Hi!

- Hello contributors, My name is Daniel. If you ever find yourself on this page, that means you are probably interesed in contributing to this project. If this is the case then you are noticing that this file is virtually empty. It means i have yet to find the time to write this MD. If you are reading this doc and are eager to contribute, feel free to create an issue on this repo and I will reply. Cheers!

For developers trying to get started developing, the first step is to know how to start the entire ecosystem in development mode, here are the tools to get you started:



1. Run the nameGenerator script. 

   Make sure you have the database MYSQL installed and have ```randnotex``` as a database. Then run step 4, this will generate the relevant tables in the database. Then proceed.

   Open the randnote-automator repo and run ``` python3 nameGenerator.py``` after installing all the pip dependencies that lie in the requirements.txt file. This will generate a bunch of users 

2. start randnote-blockchain:

   ```yarn run dev``` this will start the server on port 8033

   To make a test transaction, navigate to the directory ```  ./dist/tests/testTransaction.js ```  and run the file ``` node testTransaction.js ```. This will create a transaction to a particular address.

3. To make a mine, navigate to the directory ```./dist/tests/testMine.js``` and run ``` node testMine samuel``` , I used samuel here as the public address, this is an argument, the application takes one argument which is the public address and this address is the one that mines the block. So you can use any address you wish.

4. Start the website:

   Start by running the randnotex-backend. ```yarn run dev``` . This will run the application on port 8024

5.  Start the automator:

   In the randnote-automator directory, run ``` python3 main.py``` This will start the automator, at this point, the users have been created and stored in the database and they have been allocated some NOTES in the blockchain. This now enables these users to start transacting with one another and mining the NOTE. This is an automated process and no prints will appear on screen. To see these processes, its time to run the website.

6. Start the website:

   In the randnotex repository, run ``` yarn run dev``` this will start the nextJS application on port 3000. On the home page, the price of the NOTE should be going up and down at this point. This is a representative of price movements of a cryptoCurrency coin in the real world.

   