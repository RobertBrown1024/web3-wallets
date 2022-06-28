# web3-wallets

Adapt to web3 wallet, unified interface.

```
                                    wallets          blockchains


                               ╭───[MetaMask]────────[EVM-blockchains]
                               │
                               ├───[WalletConnect]───[EVM-blockchains]
[your dapp]───[web3-wallets]───|
                               ├───[Coinbase]─────────[EVM-blockchains]
                               │
                               ├───[Coin98]─────[EVM-blockchains]
                               |
                               ╰───[Other]----[Other] #Todo

```

## Used `WalletNames`'s

type WalletNames = 'metamask' | 'coinbase' | 'imtoken' | 'math_wallet' | 'token_pocket' | 'wallet_connect' | '
bitkeep' | 'coin98'

```ts
const wallet = new Web3Wallets('metamask')
const accounts = await wallet.enable()
const res = await wallet.request({"method": "eth_blockNumber", "params": []})
```

## Detect Wallets

```ts
const wallets = detectWallets()
const walletList = Object.values(wallets)
```

## Get Provider

```ts
export interface WalletInfo {
    chainId: number
    address: string
    privateKeys?: string[]
    rpcUrl?: RpcInfo
    port?: number
    cacheExpiration?: number
    bridge?: string
    offsetGasLimitRatio?: number
    isSetGasPrice?: boolean
}

const {address, chainId, rpcUrl, walletSigner, walletProvider} = getProvider(walletInfo)

```

## Signature

### signMessage

### signTypeData
```ts

const DOMAIN_DEFAULT = {
    name: 'ZeroEx',
    chainId: 1,
    verifyingContract: '0x0000000000000000000000000000000000000000',
    version: '1.0.0',
};
const zeroHash = getEIP712DomainHash(DOMAIN_DEFAULT)
const zero = "0xc92fa40dbe33b59738624b1b4ec40b30ff52e4da223f68018a7e0667ffc0e798"
console.assert(zeroHash==zero) 
function getEIP712StructHash(typedData.primaryType,EIP_712_ORDER_TYPE,typedData.message)

function getEIP712Hash(typeData: EIP712TypedData): string

```

### ecSignMessage

### ecSignHash

### hexUtils

## Chain Info

```ts
//
function getChainInfo(chinaId: number): ChainConfig

//
async function getChainRpcUrl(chinaId: number, best?: true): Promise<string>

```

### RPC
```ts
    const response = await fetchJson(url, {timeout: 10000, proxyUrl: 'http://127.0.0.1:7890'})
    if (response.ok) {
        console.log(await response.json())
    } else {
        console.log(response)
    }
```