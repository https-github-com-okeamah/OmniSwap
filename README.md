# SoOmnichain

The original intention of SoOmnichain is to achieve the purpose of full chain interoperability by aggregating the liquidity of various bridges. With the help of SoOmnichain:
1. Rapid circulation of user assets in different chains
2. Aggregate different bridges, such as stargate, cbridge, anyswap, etc. Users have the best cross-chain withdrawal, mainly including security, speed and handling fees
3. Aggregate the swap of different chains, users can swap different assets of the two chains with one click, such as eth of Ethereum and bnb of bsc

# Install

~~~shell
pip install -r requirements.txt
~~~

# Environment

You can add your environment variables to a `.env` file. You can use the [.env.exmple](./.env.example) as a template, just fill in the values and rename it to '.env'. 

Here is what your `.env` should look like:
```shell
export WEB3_INFURA_PROJECT_ID=<PROJECT_ID>
export PRIVATE_KEY=<PRIVATE_KEY>
```

# Deploy

After deployment, all deployed contract addresses can be found in `build/deployments/map.json`

~~~shell
brownie run --network {network} scripts/deploy.py
~~~

# Initialize

~~~shell
brownie run --network {network} scripts/initialize.py
~~~

# Swap

Note that you need to Deploy and Initialize src-network and dst-network respectively before calling swap.py.

~~~shell
python -m scripts.swap
~~~

# Network

## set polygon-test host
~~~shell
# modify polygon-test
brownie networks modify polygon-test host=https://matic-mumbai.chainstacklabs.com chainid=80001
~~~

## add arbitrum-test network
~~~shell
brownie networks add Arbitrum arbitrum-test host=https://rinkeby.arbitrum.io/rpc name=Testnet chainid=421611
~~~


