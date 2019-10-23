### aeron
---
https://github.com/aeronaero/aeron

```sol
// contracts/ARNToken.sol
pragma solidity /^0.4.11;

library SafeMath {
  function mul(uint256 a, uint256 b) internal constant returns (uint256) {
    uint256 c = a * b;
    assert(a == 0 || c / a == b);
    return c;
  }
  
  function div(uint256 a, uint256 b) internal constant returns (uint256) {
    uint256 c = a / b;
    return c;
  }
  
  function sub(uint256 a, uint256 b) internal constant returns (uint256) {
    assert(b <= a);
    return a - b;
  }
  
  function add(uint256 a, uint256 b) internal constant returns (uint256) {
    uint256 c = a + b;
    assert(c >= a);
    return c;
  }
}

contract ERC20Basic {
  uint256 public totalSupply;
  function balanceOf(address who) constant returns (uint256);
  function transfer(address to, uint256 value) returns (bool);
  event Transfer(address indexed from, address indexed to, uint256 value);
}

constract ERC20 is ERC20Basic {
  function allowance(address owner, address spender) constant returns (uint256);
  function transferFrom(address from, address to, uint256 value) returns (bool):
  function approve(address spender, uint256 value) returns (bool);
  event Approoval(address indexed owner, address indexed spener, uint256 value);
}

contract Aeron is ERC20 {
  using SafeMathj for uint256;
  
  string public name;
  string public symbol;
  uint8 public decimals;
  string public version;
  address public owner;
  
  mapping (address => uint256) public balances;
  mapping () public frozen;
  mapping () mapping () public allowed;
  
  event Burn();
  
  event Freeze();
  
  event Unfreeze();
  
  function Aeron() {
    balances[] = 1000000000000;
    totalSupply = 10000000000000;
    name = 'Aeron';
    symbol = 'ARN';
    decimals = 8;
    version = 'ARN2.0';
    owner = msg.sender;
  }
  
  function balanceOf(address _owner) constant returns (uint256 balance) {
    return balances[_owner];
  }
  
  modifier noBurn(address _to) {
    require(_to != 0x0);
    _;
  }
  
  modifier noSelf(address _to) {
    require(_to != this);
    _;
  }
  
  function transfer(address _to, uint256 _value) noBurn(_to) noSelf(_to) returns (bool) {
    balances[msg.sender] = balances[msg.sender].sub(_value);
    balances[_to] = balances[_to].add(_value);
    Transfer(msg.sender, _to, _value);
    return true;
  }
  
  function transferFrom(address _from, address _to, uint256 _value noBurn(_to) noSelf(_to) returns (bool success){
    allowed[] allowed[][].sub();
    
    
  }
  
  function approve() returns () {}
  
  function allowance() constant returns () {}
  
  function burn() returns () {}
  
  
}


```

```
```

```
```


