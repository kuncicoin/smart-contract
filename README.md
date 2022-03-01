# Kunci Coin smart contract

## Returns the amount of tokens in existence.
function totalSupply() external view returns (uint256);

## Returns the amount of tokens owned by `account`.
function balanceOf(address account) external view returns (uint256);

## Moves `amount` tokens from the caller's account to `recipient`.
function transfer(address recipient, uint256 amount) external returns (bool);

## Returns the remaining number of tokens that `spender` will be allowed to spend on behalf of `owner` through {transferFrom}. This is zero by default.
function allowance(address owner, address spender) external view returns (uint256);

## Sets `amount` as the allowance of `spender` over the caller's tokens.
function approve(address spender, uint256 amount) external returns (bool);

## Moves `amount` tokens from `sender` to `recipient` using the allowance mechanism. `amount` is then deducted from the caller's allowance.
function transferFrom(address sender, address recipient, uint256 amount) external returns (bool);

## Emitted when `value` tokens are moved from one account (`from`) to another (`to`).
event Transfer(address indexed from, address indexed to, uint256 value);

## Emitted when the allowance of a `spender` for an `owner` is set by a call to {approve}. `value` is the new allowance.
event Approval(address indexed owner, address indexed spender, uint256 value);

## Returns the name of the token.
function name() external view returns (string memory);

## Returns the symbol of the token.
function symbol() external view returns (string memory);

## Returns the decimals places of the token.
function decimals() external view returns (uint8);

## Returns the address of the current owner.
function owner() public view virtual returns (address);

## Leaves the contract without owner. It will not be possible to call `onlyOwner` functions anymore. Can only be called by the current owner.
function renounceOwnership() public virtual onlyOwner;

## Transfers ownership of the contract to a new account (`newOwner`).
function transferOwnership(address newOwner) public virtual onlyOwner;

## Returns the name of the token.
function name() public view virtual override returns (string memory);

## Returns the symbol of the token, usually a shorter version of the name.
function symbol() public view virtual override returns (string memory);

## Returns the number of decimals used to get its user representation.
function decimals() public view virtual override returns (uint8);

## Atomically increases the allowance granted to `spender` by the caller.
function increaseAllowance(address spender, uint256 addedValue) public virtual returns (bool);

## Atomically decreases the allowance granted to `spender` by the caller.
function decreaseAllowance(address spender, uint256 subtractedValue) public virtual returns (bool);

## Creates `amount` tokens and assigns them to `account`, increasing
function mint(address account, uint256 amount) public onlyOwner;

## Destroys `amount` tokens from `account`, reducing the
function burn(address account, uint256 amount) public onlyOwner;

## Airdrop tokens for specific addresses
function airdrop(address[] memory accounts, uint256 amount) public;

## Distribute tokens for a specified addresses
function distribute(address[] memory accounts, uint256[] memory amounts) public;
