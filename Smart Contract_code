/* Problem Statement 1: Basic Contact List
Objective: Create a contract named ContactList that allows users to store and retrieve
 phone numbers associated with names.
•   Use a struct named Contact to hold a person's name and phone number.
•   Implement a mapping to associate Ethereum addresses with their Contact.
•   Write a function to allow users to add or update their contact information.
•   Include a function to retrieve a user's contact information by their Ethereum address. */
 
// SPDX-License-Identifier: MIT
pragma solidity ^0.8.0;
 
contract Person
{
    struct contList
    {
        string name;
        uint contactNumber;
 
    }
     mapping (address=>contList) public Contacts;
 
     function setValue(string memory _name,uint _contactNumber)public {
 
        Contacts[msg.sender]=contList(_name,_contactNumber);
     }
     function getValue()public view returns (uint , string memory)
     {
        //return ( Contacts[msg.sender].contactNumber, Contacts[msg.sender].name);
 
       contList memory newcontList=Contacts[msg.sender];
       return (newcontList.contactNumber,newcontList.name);
     }
 
}
