##### Integration of Rented NFTs

The Integration is really simple .
You have to interact with our deployed smart contract `NFTRentingTracker.sol` via the deployed address.
The deployed address across different chains are 

    - Polygon Mumbai  `0xA16E0321fbF3F99D84E5E4DCe9a62f7A75cA8B9D`
    - Ethereum goerli `0x65e5bF619B30828EF9dB4747EBD5B02FDE9230fE`
    - Tron Nile       `TYTL59rJM8QARL1zXRKkqGTF6EeieU8mXM`

##### Steps to follow

    - Connect the user wallet with your platform and extract `wallet address`
    - Take input from the user about
        - NFT Collection smart contract address
        - Token Id of the NFT the user wants to use
    - Check if the connected user `wallet address` is the user of that token id by the `userOf` method 
    - Use the NFT if the connect user is the user of that NFT otherwise have a fallback message to the user.
    

##### Technical Steps to follow

    - Install ethers via `npm i ethers`
    - Connect the user wallet with your platform and access the provider of that wallet ( details will be added for how to do it )
    - Access the deployed contract address of `NFtRentingTracker.sol` at the address mentioned in `Integration of Rented NFTs`
( The complete code can be found here [NFTRentingTracker.sol](https://github.com/umaresso/Rent-Web3-Polygon-Included/blob/master/contracts/NftRentingTracker.sol) compile in Remix IDE to get the `ABI` of it )

    - Call the `userOf` method of the contract we accessed in above step with user input `tokenId` and `contractAddress`
    - If the wallet address of the user is same as returned by the user , he / she is the owner . Otherwise they are not.
    - Do favorbale stuff on each case whether wallet address owns that NFT or Not
    

Congratulations, you are set to receive traction from Millions of future NFT game players 🎉
If you face any issues , retry the same proceedure or alternatively reach us at seemalfrl@gmail.com
    
    
    
