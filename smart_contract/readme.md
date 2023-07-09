# A simple / basic smart-contract:-
      // SPDX-License-Identifier: MIT
      pragma solidity ^0.8.0;

      contract TransactionContract {
        mapping(address => uint256) public balances;

        event Transfer(address indexed from, address indexed to, uint256 amount);

        function viewBalance(address account) public view returns (uint256) {
              return balances[account];
        }

         function transfer(address to, uint256 amount) public {
              require(balances[msg.sender] >= amount, "Insufficient balance");
        
              balances[msg.sender] -= amount;
              balances[to] += amount;
        
              emit Transfer(msg.sender, to, amount);
        }
     }
