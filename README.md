# Interoperability Between Heterogeneous Blockchain Systems

A Real-World Application Demo Implementation

# Description
The project connects two heterogeneous blockchain networks, namely Hyperledger Fabric Blockchain and Ethereum Blockchain.

The Hyperledger Fabric Blockchain will hold assets. The Ethereum Blockchain will hold the cryptocurrency balance needed to purchase and sell the Hyperledger Fabric Blockchain assets.

# The Demo Application
The application consists of two connected parts:
* The car registration department part.
* The car selling/buying portal part.

## The Car Registration Department
* The car registration department keeps track of cars and car owners.
* The car owner has an account in the car registration department.
* The car registration department adds the cars the owner owns.
* The car owner can transfer the cars he owns to other owners.

## The Car Selling/Buying Portal
* The car seller and buyer have to open an account on the portal.
* The car seller and buyer have to connect it to their car registration department account holding the cars they own if any.
* The car seller and buyer have to connect it to their Ethereum wallets holding an amount of cryptocurrency they own if any.

### The Starting Scenario
* The car portal allows car owners to offer the cars they own for sale for an amount of Ethereum cryptocurrency (ETH).
* The portal will show a list of the cars the owners own retrieved from car registration department API.
* The car portal allow buyers to search the portal for the features of the cars, then add the cars to their carts.
* The buyers can pay using their Ethereum cryptocurrency balance. The required amount will be locked so that the buyer can’t spend it otherwise.

## The Forward Interaction Between Blockchains
* After locking required cryptocurrencies, the car portal will ask the car registration department to transfer the ownership of purchased car to the new owner.
* The car registration department will send a message to the current owner explaining the transaction and asking him to confirm or reject the transfer.

## The Backward Feedback Between Blockchains 
* If the owner accepted, then the car registration department will complete the transfer notifying the car portal about transaction success.
* If the owner rejected, then the car registration department will cancel the transfer notifying the car portal about transaction cancellation.

### The Ending Scenario
* After being notified about transaction success, the car portal transfers the locked cryptocurrencies to the seller.
* Being notified otherwise, the car portal unlocks the locked cryptocurrencies returning them to the buyer.

# The Car Registration Department Implementation

The car registration department part consists of:
* A backend written in GoLang with chain-codes written in GoLang and deployed on a Hyperledger Fabric testing network.
* A frontend written in VueJS that allows adding/editing cars and car owners with data stored in the Hyperledger Fabric Blockchain.

# The Car Registration Department Implementation

The the car portal part consists of:
* A backend written in NodeJS with smart contracts written in Solidity and deployed on an Ethereum testing network.
* A frontend written in VueJS that allows buying/selling cars with data stored in a MongoDB database.

# Conclusion
This application is an excellent real-world example about two ways interoperability between two heterogeneous blockchain systems
