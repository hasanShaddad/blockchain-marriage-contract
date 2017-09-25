# Blockchain Marriage Contract

![Image of running tests](https://c1.staticflickr.com/5/4489/37051814350_ec86ec9098_o.gif)

An Ethereum blockchain smart contract for [Love-Block](https://github.com/adoolaeghe/Love-Block), my final project at Makers Academy. This contract is an experiment in creating self-executed and self-enforced marriage contracts beyond any existing central authority.


## How to run

1. Clone the repo to your computer.

2. Install testrpc blockchain simulator and truffle - solidity test&development framework.
```
npm install -g ethereumjs-testrpc
npm install -g truffle
```

3. Run testrpc in a separate terminal window.
```
testrpc
```

4. Deploy the contract to your test blockchain. To do so in your main terminal window run.
```
truffle migrate
```

5. Run the tests.
```
truffle test
```


## Contract API

### Create proposal
Creates a proposal record, an intention of person1 to marry person2.
```
proposalNew(address1, address2) => bool
```

### Check for matching proposal
Returns true if person2 also proposed to person2.
```
proposalMatch(address1, address2) => bool
```

### Create a marriage
Creates a marriage record and returns a unique marriage ID (marId). Requires a proposal match between person1 and person2 in order to create the marriage. At this stage the newly marriage is not complete and requires person1 and person2 to provide their details.
```
marriageNew(address1, address2) => bytes32
```

### Add person
```
addPerson(marId, address, firstName, middleName, lastName, dateOfBirth, id) => bool
```

### Check if the marriage is complete
Returns true or false depending on whether the marriage with given marId is complete or not.
```
marriageIsComplete(marId) => bool
```

### Return person's marId
Returns the last marId associated with person.
```
marriageGetMarIdForPerson(address) => bytes32
```

For the marriage certificate methods please refer to Marriage certificate methods of `Marriages.sol`


## Tech Stack

* Ethereum/Testrpc

* Truffle

* Solidity


## Team
The [Love-Block](https://github.com/adoolaeghe/Love-Block) project was developed over a 9 day period as a final project at Makers Academy, a software development bootcamp. The team consisted of the following lovely people:

[Kathryn Downes](https://github.com/kitkat119), [Antoine Doolaeghe](https://github.com/adoolaeghe), [Funmi Adewodu](https://github.com/funmia), [Oleg Lukyanov](https://github.com/oleglukyanov)
