# mytoken.sol
This repositry contains the solidity code for creating a new token as a assesment of a course solidity beginner course.
This course is in Metacrafters.
------------------------------------------------------------------------------------------------------------------------

**SOLIDITY**
Solidity is a language for smart contracts in EVM used to create dapps.

*MY TOKEN*
This Solidity program is a simple token program that demonstrates the basic syntax and functionality of the Solidity programming language. The purpose of this program is to create simple token.

*Getting Started*

To run this program, you can use Remix, an online Solidity IDE. To get started, go to the Remix website at https://remix.ethereum.org/.

```//SPDX-License-Identifier: MIT

pragma solidity ^0.8.0;

contract MyToken {
    string public name;
    string public symbol;
    uint256 public totalSupply;

    mapping(address => uint256) public balances;

    constructor(string memory _name, string memory _symbol, uint256 _totalSupply) {
        name = _name;
        symbol = _symbol;
        totalSupply = _totalSupply;
        balances[msg.sender] = _totalSupply;
    }

    function mint(address _to, uint256 _value) public {
        totalSupply += _value;
        balances[_to] += _value;
    }

    function burn(address _from, uint256 _value) public {
        require(balances[_from] >= _value, "Insufficient balance");
        totalSupply -= _value;
        balances[_from] -= _value;
    }
}
```
