## Background

You have just landed a new job at ZBank, a small, innovative bank that is interested in exploring what
blockchain technology can do for them and their customers.

Your first project at the company is to set up a private testnet that you and your team of developers
can use to explore potentials for blockchain at ZBank.

You have decided on setting up a testnet because:

There is no real money involved, which will give your team of developers the freedom to experiment.

Testnets allows for offline development.

In order to set up a testnet, you will need to use the following skills/tools we learned in class:

* Puppeth, to generate your genesis block.

* Geth, a command-line tool, to create keys, initialize nodes, and connect the nodes together.

* The Clique Proof of Authority algorithm.

Tokens inherently have no value here, so we will provide pre-configured accounts and nodes for easy setup.

After creating the custom development chain, create documentation for others on how to start it using the pre-configured
nodes and accounts. You can name the network anything you want, have fun with it!

Be sure to include any preliminary setup information, such as installing dependencies and environment configuration.

# Proof of Authority Development Chain

For this assignment, you will take on the role of a new developer at a small bank.

Your mission, should you choose to accept it, will be to set up a testnet blockchain for your organization.

To do this, you will create and submit four deliverables:

* Set up your custom testnet blockchain.

* Send a test transaction.

* Create a repository.

* Write instructions on how to use the chain for the rest of your team.

## Creating Nodes

1- Create empty directories for both nodes

    * mkdir node1 
    * mkdir node2
    
    <img width="428" alt="Screen Shot 2021-12-18 at 12 36 22 PM" src="https://user-images.githubusercontent.com/88411429/146652662-2cca046a-4c06-410e-baf2-089121dc6e7e.png">


2- Create accounts for two nodes for the network with a separate `datadir` for each using `geth`.

    * ./geth account new --datadir node1
    * ./geth account new --datadir node2
        
3- Save passwords & addresses for nodes in txt file

    * echo 'node1' > node1/password.txt
    * echo 'node2' > node2/password.txt
    * echo 'DFA75550A43F59590966A4F2AE0D9Af2d43DC8DE' >> accounts.txt
    * echo '648Ac0ab0D9bA0e692C8A9104e7fb004fD05a0b2' >> accounts.txt
