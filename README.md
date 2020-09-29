# RainbowWars Demo

## Description
This is the RainbowWars [demo][demo]. RainbowWars is a cross-chain game.

In RainbowWars, you can "attack" near from etherum via rainbow-bridge, or "attack" ethereum from near.

If you attack from ethereum, you need to sign a `Attack` transaction with 1 wei and send it to ethereum. When the `Attack` transaction is confirmed, we will get the proof data of the transaction result, and relay it to near side via rainbow bridge. The contract on near side will verfiy the proof data and execute the `onAttackEvent` logic. If your attack is effective, you will get 1000000 NRC20 tokens as rewards.  
Vice versa, but attack from near don't need pay and nears and you get the 1000000 ERC20 tokens as rewards.

Your attacks are not always effective. The contract will calculate two random numbers based on your attack information and target, one is attack value another is defence value. When `attack < defence`, your attack is effective. As the number of attacks increases, the probability of success decreases.

Now, the game contract has deployed in Rinkeby testnet and Near testnet. There's also a front end, you can play the demo in [here][demo], it requires metamask browser plug-in and switch it to Rinkeby network.

> In this demo, the contract only check the receipt by merkel tree or mp tree, but don't verify the tree root hash is valid. Deploy a light client (wrote by near guys) to verify the tree root hash is easy, but maintaining the light client is a very troublesome thing.

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
