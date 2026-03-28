# MultiSender.sol
Base - Smart Contract Deployed by Remix MultiSender.sol
// SPDX-License-Identifier: MIT
pragma solidity ^0.8.20;

contract MultiSender {
    function send(address[] memory _receivers) public payable {
        uint amount = msg.value / _receivers.length;

        for (uint i = 0; i < _receivers.length; i++) {
            payable(_receivers[i]).transfer(amount);
        }
    }
}
