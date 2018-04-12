-----------------------------------|----------|----------|----------|----------|----------------|
File                               |  % Stmts | % Branch |  % Funcs |  % Lines |Uncovered Lines |
-----------------------------------|----------|----------|----------|----------|----------------|
 contracts/                        |      100 |       75 |      100 |      100 |                |
  ERC677.sol                       |      100 |      100 |      100 |      100 |                |
  ERC677Receiver.sol               |      100 |      100 |      100 |      100 |                |
  IBridgeValidators.sol            |      100 |      100 |      100 |      100 |                |
  IBurnableMintableERC677Token.sol |      100 |      100 |      100 |      100 |                |
  POA20.sol                        |      100 |       75 |      100 |      100 |                |
 contracts/libraries/              |     82.5 |    55.56 |    83.33 |    86.54 |                |
  Helpers.sol                      |      100 |       80 |      100 |      100 |                |
  Message.sol                      |      100 |      100 |      100 |      100 |                |
  SafeMath.sol                     |    41.67 |       25 |       50 |    41.67 |... 18,19,27,29 |
 contracts/upgradeability/         |       70 |       30 |       75 |    72.73 |                |
  EternalStorage.sol               |      100 |      100 |      100 |      100 |                |
  EternalStorageProxy.sol          |      100 |      100 |      100 |      100 |                |
  OwnedUpgradeabilityProxy.sol     |    44.44 |    16.67 |    66.67 |       50 | 47,48,49,70,71 |
  Proxy.sol                        |      100 |       50 |      100 |      100 |                |
  UpgradeabilityOwnerStorage.sol   |      100 |      100 |      100 |      100 |                |
  UpgradeabilityProxy.sol          |      100 |       50 |      100 |      100 |                |
  UpgradeabilityStorage.sol        |       50 |      100 |       50 |       50 |             20 |
 contracts/upgradeable_contracts/  |    94.05 |    77.91 |    92.11 |    94.19 |                |
  Ownable.sol                      |    66.67 |       50 |       75 |    71.43 |          41,42 |
  U_BridgeValidators.sol           |      100 |    88.89 |      100 |      100 |                |
  U_ForeignBridge.sol              |    94.19 |    76.32 |    91.89 |    94.19 |... 100,101,102 |
  U_HomeBridge.sol                 |    93.18 |    72.73 |       90 |    93.33 |       42,62,63 |
  U_Validatable.sol                |      100 |      100 |      100 |      100 |                |
-----------------------------------|----------|----------|----------|----------|----------------|
All files                          |    90.21 |    70.34 |    89.52 |    91.09 |                |
-----------------------------------|----------|----------|----------|----------|----------------|

     ✓ should initialize (3269ms)
    #deposit
      ✓ should allow validator to deposit (224ms)
      ✓ test with 2 signatures required (1557ms)
      ✓ should not allow to double submit (250ms)
      ✓ should not allow non-authorities to execute deposit (53ms)
    #onTokenTransfer
      ✓ can only be called from token contract (837ms)
      ✓ should not allow to burn more than the limit (1235ms)
      ✓ should only let to send within maxPerTx limit (1286ms)
      ✓ should not let to withdraw less than minPerTx (1021ms)
    #submitSignature
      ✓ allows a validator to submit a signature (338ms)
      ✓ when enough requiredSignatures are collected, CollectedSignatures event is emitted (876ms)
    #setting limits
      ✓ #setMaxPerTx allows to set only to owner and cannot be more than daily limit (183ms)
      ✓ #setMinPerTx allows to set only to owner and cannot be more than daily limit and should be less than maxPerTx (206ms)

  Contract: HomeBridge
    #initialize
      ✓ sets variables (576ms)
      ✓ cant set maxPerTx > homeDailyLimit (333ms)
    #fallback
      ✓ should accept POA (513ms)
      ✓ doesnt let you send more than max amount per tx (565ms)
      ✓ should not let to deposit less than minPerTx (413ms)
    #withdraw
      ✓ should allow to withdraw (968ms)
      ✓ should allow second withdraw with different transactionHash but same recipient and value (1261ms)
      ✓ should not allow if there are not enough funds in the contract (647ms)
      ✓ should not allow second withdraw (replay attack) with same transactionHash but different recipient (987ms)
    #withdraw with 2 minimum signatures
      ✓ withdraw should fail if not enough signatures are provided (1279ms)
      ✓ withdraw should fail if duplicate signature is provided (612ms)
    #setting limits
      ✓ #setMaxPerTx allows to set only to owner and cannot be more than daily limit (168ms)
      ✓ #setMinPerTx allows to set only to owner and cannot be more than daily limit and should be less than maxPerTx (175ms)

  Contract: POA20
    ✓ default values (97ms)
    #mint
      ✓ can mint by owner (111ms)
      ✓ cannot mint by non-owner (85ms)
      ✓ can stop minting by owner (144ms)
    #transfer
      ✓ sends tokens to recipient (153ms)
    #burn
      ✓ can burn (161ms)
    #pause
      ✓ owner can stop transfer (242ms)
    #transferAndCall
      ✓ calls contractFallback (541ms)

  Contract: BridgeValidators
    #initialize
      ✓ sets values (620ms)
    #addValidator
      ✓ adds validator (193ms)
      ✓ cannot add already existing validator (212ms)
    #removeValidator
      ✓ removes validator (211ms)
      ✓ cannot remove if it will break requiredSignatures (277ms)
      ✓ cannot remove non-existent validator (172ms)
    #setRequiredSignatures
      ✓ sets req signatures (134ms)
      ✓ cannot set more than  validators count (82ms)


  42 passing (41s)
