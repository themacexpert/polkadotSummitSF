# Remote EVM Calls via XCM!

### For a full guide on the workshop demo check out the [Moonbeam Docs site tutorial on Remote EVM Calls](https://docs.moonbeam.network/builders/xcm/remote-evm-calls/)! 

Prerequisites:
- [Faucet for Moonbase Alpha DEV Funds](https://apps.moonbeam.network/moonbase-alpha/faucet/)
- [Add the Moonbase Alpha Network to MetaMask](https://docs.moonbeam.network/)

Setup Steps:
- [Export the Private Key from MetaMask and Import to Moonbase Relay Testnet Polkadot Js Apps](https://polkadot.js.org/apps/?rpc=wss%3A%2F%2Ffrag-moonbase-relay-rpc-ws.g.moonbase.moonbeam.network#/accounts)
- Import the Account to the Polkadot Js Extension from the Back up File
- [Make a Swap on Moonbeam Swap (Testnet) to get 1-2 xcUNIT](https://moonbeam-swap.netlify.app/#/swap)
- [Withdraw all of the xcUNIT to your address on the relay chain](https://apps.moonbeam.network/moonbase-alpha/)

Identify the Derivative Account
- [Copy your address from Moonbase Relay Polkadot Js Apps](https://polkadot.js.org/apps/?rpc=wss%3A%2F%2Ffrag-moonbase-relay-rpc-ws.g.moonbase.moonbeam.network#/accounts)
- [Convert it from AccountID to Hex using Shawn Tabrizi's Converter](https://www.shawntabrizi.com/substrate-js-utilities/)
- [Clone the XCM Tools Repository](https://github.com/albertov19/xcmTools/) Then run Yarn. 

Run the following command to generate your address:

ts-node calculateMultilocationDerivative.ts \
--w wss://wss.api.moonbase.moonbeam.network \
--a YOUR_HEX_ADDRESS_HERE \
--n 0x57657374656e64

Fund your derived address with 0.5 DEV or so. 

Copy the contents of [SimpleStorage.sol](https://github.com/themacexpert/polkadotSummitSF/blob/main/SimpleStorage.sol) into Remix. Compile and deploy this contract to Moonbase Alpha. 

After deployment, make a note of the contract address and the CallData. 
