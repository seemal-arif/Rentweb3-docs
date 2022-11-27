
#### Dapp Renting - Technical process

  What happens is anyone who created a whitelist or sale contract on RentWeb3  can rent a dapp for sale of whitelisting of their collection.
  The Dapps Information ( Image , name , address and price etc. ) is stored in smart contract and IPFS 
  ( Right now we only store url and price of NFT in smart for acheiving good speed and reducing gas fees )
  
  Now the smart contract has the record that which dapp is rented for which deployment ( Sale or whitelist contract ).
  We store this information in two mappings 
  `websiteToDeployment` takes a dapp url and gives a smart contract address it is rented for
  `deploymentToWebsite` takes a smart contract address and gives a dapp address it is hosted on

##### Detecting if Dapp is Not Rented

  If website is not rented for any deployment , it contains by default the address `0x0000000000000000000000000000000000000000` (for ETH and POLYGON)
  and `410000000000000000000000000000000000000000` (for TRON )
  (denoting NULL contract address) .
  If the deployment has no website rented , it contains the Blank space string.

##### So How Does it finally work ?
  
  1.  Each dapp on it's start checks for any deployment against it's URL address in the `WebsiteRent.sol` contract address
  which has different deployment addresses due to different blockchains.
  Here are the deployment addresses for each Blockchain ( with testnets caption)
    
    - Polygon Mumbai `0xf8FdF1234F85ca66e8a142BE77DC02a472971b25`
    - Ethereum Goerli `0x641033186ea3Abb91C0b8EB5b55026457DA804Bd`
    - Tron Nile `TGS4a7AhSiKejVgAEXzMiXg87uXvkQ7kEd`
  
  2. Based upon the `NULL deployement` , it either renders the collection and perform it's purpose or it says website is not rented by anyone .
  ( See Detecting if Dapp is not rented to get a hint on how to check for no deployment ).
  
  
###### Benefits

  This Re-usability will transform the way we see NFT Collections Launch.
  It will breed `low-cost` and `speed` for `creators` who want to `launch` their `NFT collection` 
  and `more money generation` for `developers` who made the dapp Rentable.
  
  
