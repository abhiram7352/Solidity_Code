# Solidity_Code
ApnaBank Contract
// SPDX-License-Identifier: MIT
pragma solidity ^0.8.0;
 contract apnabank{
 mapping(address => uint) public balances;
 address public customerAccount;
 
 
  struct Details
{
    string name;
     string aadharNumbber;
     address accountNmuber;
}
mapping (address=>Details) public customerDetails;
function valueSet( string memory _name,string memory _aadharNumber,address _accountNumber) public {
        require(customerAccount==msg.sender,"Your not customer of this Bank.....");
        Details memory newcustomer=Details(_name,_aadharNumber,_accountNumber);
        customerDetails[_accountNumber]=newcustomer;
 
}
 
constructor(){
    customerAccount = msg.sender;
}
 
function deposit() public payable{
    require(msg.value > 0, "deposit amount must be greater than 0");
    balances[msg.sender] += msg.value;
}
function withdraw(uint amount) public {
    require(amount > 0, "withdreaw amount should be greater then o");
    require(balances[msg.sender] >= amount, " insufficient balance");
    balances[msg.sender] -= amount;
    payable(msg.sender).transfer(amount);
}
function checkbalance() public view returns (uint){
    return  balances[msg.sender];
}
 
 
}

#Contract
// SPDX-License-Identifier: MIT
pragma solidity ^0.8.0;
 
contract Bank {
    mapping(address => uint256) public balances;
    address public owner;
 
    constructor() {
        owner = msg.sender;
    }
 
    function deposit() public payable {
        require(msg.value > 0, "deposit amount should be greater than 0");
        balances[msg.sender] += msg.value;
    }
 
    function withdraw(uint256 amount) public {
        require(amount > 0, "withdrawal amount should be greater than 0");
        require(balances[msg.sender] >= amount, " insufficient balance");
        balances[msg.sender] -= amount;
        payable(msg.sender).transfer(amount);
    }
 
    function getBalance() public view returns (uint256) {
        return balances[msg.sender];
    }
}
