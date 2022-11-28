### Making a Rentable Dapp

Right now we are just dealing with NFT centered Dapps( whitelisting and sale)

but we are eager to see a variety of dapps that the community will bring.

1. NFT Launch Centered Dapps

        Developing such dapp will be easy yet it can be a little tricky. But we believe that you can do it : )

##### Steps to follow
            - At first , make your dapp for just one collection of your choice . 
   (Using any deployed instance of [WhitelistFactory.sol](https://github.com/rentweb3/RentWeb3-code/blob/master/contracts/WhitelistFactory.sol) or [Salefactory.sol](https://github.com/rentweb3/RentWeb3-code/blob/master/contracts/SaleFactory.sol))
   
   
            - Store the smart contract address somewhere in a variable in the app.js or index.js file on top of everything.
            - Check the total supply of the collection via `totalSupply` method of the contract of your choice.
            - Access the NFTs metadata Uri with the `tokenURI` method  by passing `i` as token Id where `i varies from 1 to totalSupply`.
            - Write the logic of sale or whitelisting according to the type of your dapp.
            - Check if everything is working - tokens minted successfully or whitelisting is happening flawlessly.
            - Time to add the magic.
   Access the deployed smart contract Instance of [WebsiteRent.sol](https://github.com/rentweb3/RentWeb3-code/blob/master/contracts/WebsiteRent.sol)
   
   at the addresses mentioned in [here](https://github.com/rentweb3/Rentweb3-docs/blob/main/Dapp-renting.md) via ethers js or tronweb ( according to your blockchain)
   
            - Acccess the current deployment with following code

``` javascript
export async function getCurrentDeployment(
  Blockchain,
  NetworkChain,
  web3ModalRef,
  websiteURL
) {
  
  let contract = await getWebsiteRentContract(
    Blockchain,
    NetworkChain,
    web3ModalRef
  );
  console.log("checking Deployment of _" + websiteURL + "_");
  let _currentDeployment = await contract.websiteToDeployment(websiteURL);
  if (noDeployment(_currentDeployment)) {
    console.log("No deployment");
    return null;
  }

  let rentTime = await contract.rentTime(websiteURL);

  let jsEpochRentTime = parseInt(rentTime * 1000);
  let currentTime = new Date().getTime();
  if (jsEpochRentTime <= currentTime) {
    _currentDeployment = null;
  }
  return { currentDeployment: _currentDeployment, rentTime };
}


```

            - After the deployment access , check if the deployment exists or not using 
``` javascript

function noDeployment(adr) {
  if (
    !adr ||
    adr?.toString().includes("0x0000") ||
    adr?.toString().includes("0X0000") ||
    adr?.toString().includes("41c0000") ||
    adr?.toString().includes("0000000000000000000") 
    
  )
    return true;

  return false;
}
```
            - If the deployment exists , render NFT collection and perform whitelist , sale or any thing that the dapp is developed for.
            - Make sure everything is working smoothly before uploading to the platform.
            - You are all set

#### Sample Dapps to check
Following are some of the dapps that are built by the RentWeb3 Team . Feel free to check out

##### Polygon
Whitelist       : [Get Whitelisted](https://github.com/rentweb3/Get-Whitelisted)
Sale            : [Lets Sale](https://github.com/rentweb3/Lets-Sale)

##### Ethereum
Whitelist       : [Whitelister](https://github.com/rentweb3/whitelister)
Sale            : [Nifter](https://github.com/rentweb3/Nifter)

##### Tron
Whitelist       : [Tron Whitelister](https://github.com/rentweb3/tron-whitelister)
Sale            : Yet to be developed


             
#### Other Dapps are coming !
Bring your ideas and lets have a coffe at rentweb3@gmail.com
    
    
