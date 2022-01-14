# **Blockchain Construction**
**Target**:&nbsp; Construcrt blockchain stimulator on local server.  
**Package**:&nbsp; Geth: 1.10; Go: 1.17.  
**Environment**:&nbsp; Linux Ubuntu 20.04.
## **Constructive Process**
1. Install Go.  
2. Install geth.
3. Geth Simulation.
## **Phase 1: Go Installation**
Refer to official website of Go: https://go.dev/doc/install  
  
Step 1: Click "Download Go for Linux" button to download "Go" package.      
Step 2: Extract package to path "/usr/local".    
Step 3: Create a directory named "go" in "/usr/local".    
Step 4: Execute the following command in terminal "sudo rm -rf /usr/local/go &&  
&emsp; &emsp; &ensp; tar -C /usr/local -xzf go1.17.6.linux-amd64.tar.gz".  
Step 5: Execute the following command in terminal "export PATH=$PATH:/usr/local/go/bin".    
Step 6: Type "go version" to check it is installed sucessfully or not.     

## **Phase 2: Geth Installation**
Refer to official website of Geth Installation: https://geth.ethereum.org/docs/install-and-build/installing-geth 
  
Step 1: type "sudo add-apt-repository -y ppa:ethereum/ethereum" on terminal.  
Step 2: type "sudo apt-get update" on terminal.  
Step 3: type "sudo apt-get install ethereum" on terminal.

## **Phase 3: Geth Simulation**
Step 1: Create a directory named "geth" includes all blockchains.  
Step 2: Enter the directory "geth", and create directories with arbitary name (Each directory represents one blockchain).  
Step 3: Enter one of the directories.  
Step 4: Create a file name "genesis.json" with the given content of "genesis.json" template, only alter the value of chainId,    
&emsp; &emsp; &ensp; the genesis.json in each  direcotries can be arbitary but unqiue.  
Step 5: type "geth init genesis.json --datadir './db'" on terminal to initialize blockchain.  
Step 6: Type "geth --datadir "./db" --http --http.addr &lt;ip of machine&gt; --http.port &lt;one port between 8000 to 9000&gt; --port &emsp; &emsp; &ensp;&lt;one port between 30000 to 31000&gt; --http.corsdomain "*" --networkid &lt;one number&gt; --http.api  
&emsp; &emsp; &ensp;personal,miner,web3,eth,net --nodiscover --allow-insecure-unlock --rpc.allow-unprotected-txs --miner.gaslimit  
&emsp; &emsp; &ensp;'10000000000000' --miner.gasprice '0'" on terminal to launch blockchain (each blockchain should have unqiue  
&emsp; &emsp; &ensp;networkid, http.port, port)

## **Phase 4: Geth Blockchain Control**
Step 1: Open another terminal.  
Step 2: Type "geth attach http://&lt;ip of machine&gt;:&lt;http.port of blockchain&gt;" on terminal to enter controlled console of  
&emsp; &emsp; &ensp;blockchain.  
Step 3: Type "personal.newAccount()" on console to create a new account.  
Step 4: Type "miner.setEtherbase(web3.eth.accounts[0])" on console to specify account 0 to be the miner account.  
Step 5: Type "miner.start()" on console to start mining.

##**Phase 5: Activitation Procedure of Geth Blockchain**##  
Step 1: Enter the directory represents the blockchain you want to launch.  
Step 2: Type "geth --datadir "./db" --http --http.addr &lt;ip of machine&gt; --http.port &lt;one port between 8000 to 9000&gt; --port  
&emsp; &emsp; &ensp;&lt;one port between 30000 to 31000&gt; --http.corsdomain "*" --networkid &lt;one number&gt; --http.api  
&emsp; &emsp; &ensp;personal,miner,web3,eth,net --nodiscover --allow-insecure-unlock --rpc.allow-unprotected-txs --miner.gaslimit  
&emsp; &emsp; &ensp;'10000000000000' --miner.gasprice '0'" on terminal to launch blockchain.  
Step 3: Open another terminal and type "geth attach http://&lt;ip of machine&gt;:&lt;http.port of blockchain&gt;" on terminal to enter   &emsp; &emsp; &ensp;controlled console of blockchain.    
Step 4: Type "miner.start()" on console to start mining.  
Step 5: Type "eth.blockNumber" on console to check the number of block has increased or not.  
※Remark: If you want to create new Account, type "personal.newAccount()" to create new account.  
   

