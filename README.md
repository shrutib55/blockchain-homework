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

2- Create accounts for two nodes for the network with a separate `datadir` for each using `geth`.

    * ./geth account new --datadir node1
    * ./geth account new --datadir node2
        
3- Save passwords & addresses for nodes in txt file

    * echo 'node1' > node1/password.txt
    * echo 'node2' > node2/password.txt
    * echo 'f5bA60DDCC7b1Dd2B363eD0117700543C94645f1' >> accounts.txt
    * echo '9ad665A8155887F4aced7Fd15f1A22aD532901E3' >> accounts.txt

4- Run `puppeth`, name your network, and select the option to configure a new genesis block. 

   Choose the `Clique (Proof of Authority)` consensus algorithm. 

   Paste both account addresses from the first step one at a time into the list of accounts to seal.

   Paste them again in the list of accounts to pre-fund.


--- Network Name: bcnet
   
--- Network ID : 889

    * ./puppeth
    
    
5- Choose the `Manage existing genesis` option.

   Export genesis configurations.
   
   Use Ctrl + C to exit puppeth. 

6- Initialize node with the exported network name
    
    * ./geth init bcnet.json --datadir node1
    * ./geth init bcnet.json --datadir node2
   
7- Run the first node, unlock the account, enable mining, and the RPC flag. Only one node needs RPC enabled.

    * ./geth --datadir node1/ --mine --miner.threads 1 --unlock 'f5bA60DDCC7b1Dd2B363eD0117700543C94645f1' --password node1/password.txt --rpc.allow-unprotected-txs       --allow-insecure-unlock --port "35555" 
    
8- Set a different peer port for the second node and use the first node's `enode` address as the `bootnode` flag.

    * ./geth --datadir node2/ --port 0  --bootnodes 'enode://8858450562f634131b81d701d8bc932cc1cc27b11b0c4be1ab2794c20ddf9fcd1a8957641802f08b79dd0b6b859b30b31ee06608f902daebe7cf56216aa50567@127.0.0.1:35555'
    
### Test Transaction

1- Use the MyCrypto wallet to connect to the node with the exposed RPC port.

   You will need to use a custom network, and include the chain ID, and use ETH as the currency.
   
   
   
   
------------------------------------------------------------------------------------------------------------------------------------------------------------------   
   
*** Unfortunately, my MyCrypto wallet was unable to connect to the custom network. I have been told that many people with Macs faced this issue, but after 2 days of troubleshooting with my tutor, instructor, and the internet... this issue still was unable to be resolved. ***




