# How to Create an NFT Collection through API
 
NFT API to mint/create collection

NFT API's can be used to build marketplaces, researches, wallets, analytics sites, trading tools etc. This case describes, how to make NFT Collections and mint through simple API call

![image](https://user-images.githubusercontent.com/9072132/209811041-3015bb2f-85b1-4117-8b2a-234b2c60bb65.png)


# Content

* Need to create new NFT collections?
* Need to mint and list an NFT?
* Need to get collection data and images?
* Need to see which NFTs are related to spefic wallet?
* Need to get transactions and listing related to NFT?
* Need to see trade volumes and top collections?

# Start

Get an API key from one of the providers (this example is built on top of leading NFT data provider NFTPort)

1. [Get an API key](https://www.nftport.xyz/?utm_source=GitHub&utm_medium=API+NFT&utm_campaign=Github) - API key is free and can be used for most interactions
2. Test API calls for free here - https://docs.nftport.xyz/reference/retrieve-contract-nfts

If you need any help, please check [NFTPort Discord](https://discord.gg/nftport) , they are quite active


# Create NFT Collection and Mint

Launching your NFT can be done in two main ways:
* Mint your NFT on existing collection provider - easy and fast
* Build your own collection - define your own collection parameters and take ownership of it

## Mint an NFT (Easy minting)
Turn anything into an NFT in less than 5 minutes using one simple API call, you can either upload an image or give a link for it

[Easy minting w/URL](https://docs.nftport.xyz/reference/easy-minting-urls) or [Easy minting w/file upload](https://docs.nftport.xyz/reference/easy-minting-file-upload)

### Supported chain(s): ###
* Polygon

### Body params: ###
* `name` - Name of the NFT
* `description` - Text description of the NFT which will be seen on NFT marketplaces, etc.
* `file_url`- URL that points to the image/video or any other file format as long as it returns a Content-Length and Content-Type header or contains the file extension. HTML files are not supported.
* `mint_to_address`- Account address where the NFT will be sent. For example, your Metamask wallet address if you wish to send it to yourself.

### Request CURL ###
```
curl --request POST \
     --url https://api.nftport.xyz/v0/mints/easy/urls \
     --header 'Authorization: API KEY' \
     --header 'accept: application/json' \
     --header 'content-type: application/json' \
     --data '
{
     "name": "sample_nft",
     "description": "sample_description",
     "file_url": "url_for_the_file",
     "mint_to_address": "your_wallet"
}
```
### Example response ###
```
{
  "response": "OK",
  "chain": "polygon",
  "contract_address": "0x47c7ff137d7a6644a9a96f1d44f5a6f857d9023f",
  "transaction_hash": "0x6eb71286f4875bf48be7834c1ff285910583705714f5a5acff67489f94e14954",
  "transaction_external_url": "https://polygonscan.com/tx/0x6eb71286f4875bf48be7834c1ff285910583705714f5a5acff67489f94e14954",
  "mint_to_address": "0x5FDd0881Ef284D6fBB2Ed97b01cb13d707f91e42",
  "name": "collection name",
  "description": "Example collection"
}
```
