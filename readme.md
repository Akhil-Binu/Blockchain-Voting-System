

npm install ethereumjs-testrpc web3

npm install solc

npm install ganache-cli -g

ganache-cli(This Could be run in Cmd)


replace your aadhar number in app.js file ui folder and also replace ganache first address at clist.js




$ node
> Web3 = require('web3')
> web3 = new Web3(new Web3.providers.HttpProvider("http://127.0.0.1:8545"));

Then ensure Web3js is initalized and can query all accounts on the blockchain

> web3.eth.accounts
Lastly, compile the contract by loading the code from Voting.sol in to a string variable and compiling it

> code = fs.readFileSync('Voting.sol').toString()
> solc = require('solc')
> compiledCode = solc.compile(code)


2nd Step


> abiDefinition = JSON.parse(compiledCode.contracts[':Voting'].interface)
> VotingContract = web3.eth.contract(abiDefinition)
> byteCode = compiledCode.contracts[':Voting'].bytecode
> deployedContract = VotingContract.new(['Akhil','Athira','Adithya','Rekhana'],{data: byteCode, from: web3.eth.accounts[0], gas: 4700000})
> deployedContract.address
> contractInstance = VotingContract.at(deployedContract.address)



To Get Count Of Vote


> contractInstance.totalVotesFor.call('Akhil').toLocaleString()


to run completing all these steps 

npm install 

node index.js

if any package dependency error occur

npm init


Thankyou From Akhil 






