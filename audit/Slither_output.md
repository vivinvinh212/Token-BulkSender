Compilation warnings/errors on .\BulkSender.sol:
.\BulkSender.sol:94:9: Warning: Invoking events without "emit" prefix is deprecated.   
        Transfer(msg.sender, _to, _value);
        ^-------------------------------^
.\BulkSender.sol:118:9: Warning: Invoking events without "emit" prefix is deprecated.  
        Transfer(_from, _to, _value);
        ^--------------------------^
.\BulkSender.sol:124:9: Warning: Invoking events without "emit" prefix is deprecated.  
        Approval(msg.sender, _spender, _value);
        ^------------------------------------^


StandardToken (BulkSender.sol#107-134) has incorrect ERC20 function interface:ERC20.transferFrom(address,address,uint256) (BulkSender.sol#71-75)
StandardToken (BulkSender.sol#107-134) has incorrect ERC20 function interface:ERC20.approve(address,uint256) (BulkSender.sol#77)
StandardToken (BulkSender.sol#107-134) has incorrect ERC20 function interface:ERC20Basic.transfer(address,uint256) (BulkSender.sol#60)
StandardToken (BulkSender.sol#107-134) has incorrect ERC20 function interface:BasicToken.transfer(address,uint256) (BulkSender.sol#91-95)
StandardToken (BulkSender.sol#107-134) has incorrect ERC20 function interface:StandardToken.transferFrom(address,address,uint256) (BulkSender.sol#110-119)
StandardToken (BulkSender.sol#107-134) has incorrect ERC20 function interface:StandardToken.approve(address,uint256) (BulkSender.sol#121-125)
Reference: https://github.com/crytic/slither/wiki/Detector-Documentation#incorrect-erc20-interface

Ownable.transferOwnership(address) (BulkSender.sol#153-157) should emit an event for:  
        - owner = newOwner (BulkSender.sol#155)
Reference: https://github.com/crytic/slither/wiki/Detector-Documentation#missing-events-access-control

BulkSender.setVIPFee(uint256) (BulkSender.sol#249-251) should emit an event for:       
        - VIPFee = _fee (BulkSender.sol#250)
Reference: https://github.com/crytic/slither/wiki/Detector-Documentation#missing-events-arithmetic

Reentrancy in BulkSender.getBalance(address) (BulkSender.sol#180-190):
        External calls:
        - balance = token.balanceOf(this) (BulkSender.sol#187)
        - token.transfer(_receiverAddress,balance) (BulkSender.sol#188)
        Event emitted after the call(s):
        - LogGetToken(_tokenAddress,_receiverAddress,balance) (BulkSender.sol#189)     
Reference: https://github.com/crytic/slither/wiki/Detector-Documentation#reentrancy-vulnerabilities-3

SafeMath.div(uint256,uint256) (BulkSender.sol#15-20) is never used and should be removed
SafeMath.max256(uint256,uint256) (BulkSender.sol#41-43) is never used and should be removed
SafeMath.max64(uint64,uint64) (BulkSender.sol#33-35) is never used and should be removed
SafeMath.min256(uint256,uint256) (BulkSender.sol#45-47) is never used and should be removed
SafeMath.min64(uint64,uint64) (BulkSender.sol#37-39) is never used and should be removed
Reference: https://github.com/crytic/slither/wiki/Detector-Documentation#dead-code     

Pragma version^0.4.0 (BulkSender.sol#1) allows old versions
solc-0.4.21 is not recommended for deployment
Reference: https://github.com/crytic/slither/wiki/Detector-Documentation#incorrect-versions-of-solidity

Parameter BasicToken.transfer(address,uint256)._to (BulkSender.sol#91) is not in mixedCase
Parameter BasicToken.transfer(address,uint256)._value (BulkSender.sol#91) is not in mixedCase
Parameter BasicToken.balanceOf(address)._owner (BulkSender.sol#97) is not in mixedCase 
Parameter StandardToken.transferFrom(address,address,uint256)._from (BulkSender.sol#111) is not in mixedCase
Parameter StandardToken.transferFrom(address,address,uint256)._to (BulkSender.sol#112) 
is not in mixedCase
Parameter StandardToken.transferFrom(address,address,uint256)._value (BulkSender.sol#113) is not in mixedCase
Parameter StandardToken.approve(address,uint256)._spender (BulkSender.sol#121) is not in mixedCase
Parameter StandardToken.approve(address,uint256)._value (BulkSender.sol#121) is not in 
mixedCase
Parameter StandardToken.allowance(address,address)._owner (BulkSender.sol#127) is not in mixedCase
Parameter StandardToken.allowance(address,address)._spender (BulkSender.sol#127) is not in mixedCase
Parameter BulkSender.getBalance(address)._tokenAddress (BulkSender.sol#180) is not in mixedCase
Parameter BulkSender.addToVIPList(address[])._vipList (BulkSender.sol#205) is not in mixedCase
Parameter BulkSender.removeFromVIPList(address[])._vipList (BulkSender.sol#214) is not 
in mixedCase
Parameter BulkSender.isVIP(address)._addr (BulkSender.sol#223) is not in mixedCase     
Parameter BulkSender.setReceiverAddress(address)._addr (BulkSender.sol#230) is not in mixedCase
Parameter BulkSender.setVIPFee(uint256)._fee (BulkSender.sol#249) is not in mixedCase  
Parameter BulkSender.setTxFee(uint256)._fee (BulkSender.sol#256) is not in mixedCase   
Parameter BulkSender.ethSendSameValue(address[],uint256)._to (BulkSender.sol#260) is not in mixedCase
Parameter BulkSender.ethSendSameValue(address[],uint256)._value (BulkSender.sol#260) is not in mixedCase
Parameter BulkSender.ethSendDifferentValue(address[],uint256[])._to (BulkSender.sol#283) is not in mixedCase
Parameter BulkSender.ethSendDifferentValue(address[],uint256[])._value (BulkSender.sol#283) is not in mixedCase
Parameter BulkSender.coinSendSameValue(address,address[],uint256)._tokenAddress (BulkSender.sol#308) is not in mixedCase
Parameter BulkSender.coinSendSameValue(address,address[],uint256)._to (BulkSender.sol#309) is not in mixedCase
Parameter BulkSender.coinSendSameValue(address,address[],uint256)._value (BulkSender.sol#310) is not in mixedCase
Parameter BulkSender.coinSendDifferentValue(address,address[],uint256[])._tokenAddress 
(BulkSender.sol#331) is not in mixedCase
Parameter BulkSender.coinSendDifferentValue(address,address[],uint256[])._to (BulkSender.sol#332) is not in mixedCase
Parameter BulkSender.coinSendDifferentValue(address,address[],uint256[])._value (BulkSender.sol#333) is not in mixedCase
Parameter BulkSender.sendEth(address[],uint256)._to (BulkSender.sol#357) is not in mixedCase
Parameter BulkSender.sendEth(address[],uint256)._value (BulkSender.sol#357) is not in mixedCase
Parameter BulkSender.bulksend(address[],uint256[])._to (BulkSender.sol#364) is not in mixedCase
Parameter BulkSender.bulksend(address[],uint256[])._value (BulkSender.sol#364) is not in mixedCase
Parameter BulkSender.bulkSendETHWithDifferentValue(address[],uint256[])._to (BulkSender.sol#372) is not in mixedCase
Parameter BulkSender.bulkSendETHWithDifferentValue(address[],uint256[])._value (BulkSender.sol#372) is not in mixedCase
Parameter BulkSender.bulkSendETHWithSameValue(address[],uint256)._to (BulkSender.sol#383) is not in mixedCase
Parameter BulkSender.bulkSendETHWithSameValue(address[],uint256)._value (BulkSender.sol#383) is not in mixedCase
Parameter BulkSender.bulkSendCoinWithSameValue(address,address[],uint256)._tokenAddress (BulkSender.sol#395) is not in mixedCase
Parameter BulkSender.bulkSendCoinWithSameValue(address,address[],uint256)._to (BulkSender.sol#396) is not in mixedCase
Parameter BulkSender.bulkSendCoinWithSameValue(address,address[],uint256)._value (BulkSender.sol#397) is not in mixedCase
Parameter BulkSender.bulkSendCoinWithDifferentValue(address,address[],uint256[])._tokenAddress (BulkSender.sol#406) is not in mixedCase
Parameter BulkSender.bulkSendCoinWithDifferentValue(address,address[],uint256[])._to (BulkSender.sol#407) is not in mixedCase
Parameter BulkSender.bulkSendCoinWithDifferentValue(address,address[],uint256[])._value (BulkSender.sol#408) is not in mixedCase
Parameter BulkSender.bulksendToken(address,address[],uint256[])._tokenAddress (BulkSender.sol#417) is not in mixedCase
Parameter BulkSender.bulksendToken(address,address[],uint256[])._to (BulkSender.sol#418) is not in mixedCase
Parameter BulkSender.bulksendToken(address,address[],uint256[])._value (BulkSender.sol#419) is not in mixedCase
Parameter BulkSender.drop(address,address[],uint256)._tokenAddress (BulkSender.sol#428) is not in mixedCase
Parameter BulkSender.drop(address,address[],uint256)._to (BulkSender.sol#429) is not in mixedCase
Parameter BulkSender.drop(address,address[],uint256)._value (BulkSender.sol#430) is not in mixedCase
Variable BulkSender.VIPFee (BulkSender.sol#172) is not in mixedCase
Reference: https://github.com/crytic/slither/wiki/Detector-Documentation#conformance-to-solidity-naming-conventions

Reentrancy in BulkSender.ethSendDifferentValue(address[],uint256[]) (BulkSender.sol#283-305):
        External calls:
        - require(bool)(_to[i].send(_value[i])) (BulkSender.sol#299)
        Event emitted after the call(s):
        - LogTokenBulkSent(0x000000000000000000000000000000000000bEEF,msg.value) (BulkSender.sol#301-304)
Reentrancy in BulkSender.ethSendSameValue(address[],uint256) (BulkSender.sol#260-281): 
        External calls:
        - require(bool)(_to[i].send(_value)) (BulkSender.sol#274)
        Event emitted after the call(s):
        - LogTokenBulkSent(0x000000000000000000000000000000000000bEEF,msg.value) (BulkSender.sol#277-280)
Reentrancy in BulkSender.registerVIP() (BulkSender.sol#195-200):
        External calls:
        - require(bool)(_receiverAddress.send(msg.value)) (BulkSender.sol#198)
        State variables written after the call(s):
        - vipList[msg.sender] = true (BulkSender.sol#199)
Reference: https://github.com/crytic/slither/wiki/Detector-Documentation#reentrancy-vulnerabilities-4

BulkSender.ethSendSameValue(address[],uint256) (BulkSender.sol#260-281) uses literals with too many digits:
        - LogTokenBulkSent(0x000000000000000000000000000000000000bEEF,msg.value) (BulkSender.sol#277-280)
BulkSender.ethSendDifferentValue(address[],uint256[]) (BulkSender.sol#283-305) uses literals with too many digits:
        - LogTokenBulkSent(0x000000000000000000000000000000000000bEEF,msg.value) (BulkSender.sol#301-304)
Reference: https://github.com/crytic/slither/wiki/Detector-Documentation#too-many-digits

ERC20Basic.totalSupply (BulkSender.sol#56) should be constant
Reference: https://github.com/crytic/slither/wiki/Detector-Documentation#state-variables-that-could-be-declared-constant

balanceOf(address) should be declared external:
        - BasicToken.balanceOf(address) (BulkSender.sol#97-99)
        - ERC20Basic.balanceOf(address) (BulkSender.sol#58)
transfer(address,uint256) should be declared external:
        - BasicToken.transfer(address,uint256) (BulkSender.sol#91-95)
        - ERC20Basic.transfer(address,uint256) (BulkSender.sol#60)
allowance(address,address) should be declared external:
        - ERC20.allowance(address,address) (BulkSender.sol#66-69)
        - StandardToken.allowance(address,address) (BulkSender.sol#127-133)
transferFrom(address,address,uint256) should be declared external:
        - ERC20.transferFrom(address,address,uint256) (BulkSender.sol#71-75)
        - StandardToken.transferFrom(address,address,uint256) (BulkSender.sol#110-119)
approve(address,uint256) should be declared external:
        - ERC20.approve(address,uint256) (BulkSender.sol#77)
        - StandardToken.approve(address,uint256) (BulkSender.sol#121-125)
transferOwnership(address) should be declared external:
        - Ownable.transferOwnership(address) (BulkSender.sol#153-157)
getBalance(address) should be declared external:
        - BulkSender.getBalance(address) (BulkSender.sol#180-190)
registerVIP() should be declared external:
        - BulkSender.registerVIP() (BulkSender.sol#195-200)
addToVIPList(address[]) should be declared external:
        - BulkSender.addToVIPList(address[]) (BulkSender.sol#205-209)
removeFromVIPList(address[]) should be declared external:
        - BulkSender.removeFromVIPList(address[]) (BulkSender.sol#214-218)
setReceiverAddress(address) should be declared external:
        - BulkSender.setReceiverAddress(address) (BulkSender.sol#230-233)
setVIPFee(uint256) should be declared external:
        - BulkSender.setVIPFee(uint256) (BulkSender.sol#249-251)
setTxFee(uint256) should be declared external:
        - BulkSender.setTxFee(uint256) (BulkSender.sol#256-258)
sendEth(address[],uint256) should be declared external:
        - BulkSender.sendEth(address[],uint256) (BulkSender.sol#357-359)
bulksend(address[],uint256[]) should be declared external:
        - BulkSender.bulksend(address[],uint256[]) (BulkSender.sol#364-366)
bulkSendETHWithDifferentValue(address[],uint256[]) should be declared external:
        - BulkSender.bulkSendETHWithDifferentValue(address[],uint256[]) (BulkSender.sol#372-377)
bulkSendETHWithSameValue(address[],uint256) should be declared external:
        - BulkSender.bulkSendETHWithSameValue(address[],uint256) (BulkSender.sol#383-388)
bulkSendCoinWithSameValue(address,address[],uint256) should be declared external:
        - BulkSender.bulkSendCoinWithSameValue(address,address[],uint256) (BulkSender.sol#394-400)
bulkSendCoinWithDifferentValue(address,address[],uint256[]) should be declared external:
        - BulkSender.bulkSendCoinWithDifferentValue(address,address[],uint256[]) (BulkSender.sol#405-411)     
bulksendToken(address,address[],uint256[]) should be declared external:
        - BulkSender.bulksendToken(address,address[],uint256[]) (BulkSender.sol#416-422)
drop(address,address[],uint256) should be declared external:
        - BulkSender.drop(address,address[],uint256) (BulkSender.sol#427-433)
Reference: https://github.com/crytic/slither/wiki/Detector-Documentation#public-function-that-could-be-declared-external
. analyzed (7 contracts with 78 detectors), 91 result(s) found