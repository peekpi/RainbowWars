# RainbowWars Demo

## Description
This is the RainbowWars [demo][demo]. RainbowWars is a cross-chain game.  
The [video][video] is below, sorry for the AI voice, because English is not my first language.
[![the Video](https://img.youtube.com/vi/YTD7MGh-Vtw/0.jpg)](https://www.youtube.com/watch?v=YTD7MGh-Vtw)

In RainbowWars, you can "attack" near from etherum via rainbow-bridge or "attack" ethereum from near.

If you attack from ethereum, you need to sign an `Attack` transaction with 1 wei and send it to ethereum. When the `Attack` transaction is confirmed, we will get the proof data of the transaction result, and relay it to the near side via the rainbow bridge. The contract on the near side will verify the proof data and execute the `onAttackEvent` logic. If your attack is effective, you will get 10000000 NRC20 tokens as rewards, otherwise you only get 1/10.
Vice versa, but the attack from near don't need to pay any nears and you get the ERC20 tokens as rewards.

Your attacks are not always effective. The contract will calculate two random numbers based on your attack information and target, one is the attack value another is the defense value. When `attack < defense`, your attack is effective. As the number of attacks increases, the probability of success decreases.

Now, the game contract has been deployed in Rinkeby testnet and Near testnet. There's also a front end, you can play the demo in [here][demo], it requires Metamask browser plug-in and switches it to the Rinkeby network, also needs some eth tokens of the Rinkeby testnet.

> In this demo, the contract only checks the receipt by Merkel tree or MP tree, but don't verify the tree root hash is valid. Deploy a light client (wrote by near guys) to verify the tree root hash is easy, but maintaining the light client is a very troublesome thing.

## project and source code
The RainbowWars project consists of three parts:
- [ethereum solidity contract][ethcontract]
- [near assembly contract][nearcontract]
- [vue frontend][frontend]

[demo]: https://peekpi.github.io/RainbowWars/dist
[ethcontract]: https://github.com/peekpi/RainbowWars-Solidity
[nearcontract]: https://github.com/peekpi/RainbowWars-Assembly
[frontend]: https://github.com/peekpi/RainbowWars-Vue
[describe]: https://github.com/peekpi/RainbowWars
[video]: https://youtu.be/YTD7MGh-Vtw
