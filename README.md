# SimpleBankSystemUsingSmartContracts

This repository assumes that you already have a working knowledge of writing smart contracts using Solidity. 


The design used here is the 'Five Types Model' publicised by Eris Industries.

![Alt text](https://github.com/harshpokharna/The-5-Types-Model-Simple-Bank-System-Solidity/blob/master/res/application_flow.png "Optional title")

Here the approach taken is completely different. Categorise the contracts into following categories:

1. Database Contracts

2. Controller Contracts

3. Contracts Managing Contracts

4. Utility Contracts

5. Application Logic Contracts

Here we have 2 database contracts - PermssionDB and bankDB. They allow their respective controllers to write, update and get data.

We have 2 controller contracts - PermissionController and BankController. They interact with the storage (one or more than one) and can be advanced (do batch read/write)

The controller with fund manager function as application logic contracts

We do not have any utility contracts

Finally we have a contractRegistryContract which is the CMC. It contains the addresses of all contracts and can be queried by any contract.

This makes the design very modular. Now, we can update a contract without affecting others. (eg. If the permission model is changed, we just need to update the PermissionDB and reregister it with ContractNameRegistry and the rest of the system will work fine)

