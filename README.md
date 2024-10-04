# Sequence Transactions Manager
Leveraging our transaction API in an express backend to mint NFTs, you can leverage this Dockerfile in order to deploy your backend.

## Prerequisites
- Docker Installed


## How to Run
1. Copy `.env.example` to `.env` with `cp .env.example .env` and complete fields.
2. Run `docker build -t transaction-manager . && docker run -p 3001:3001 transaction-manager` to build the image and start the container.


Then mint an ERC721 collectible to your wallet by swapping out the `walletAddress` with your address in the following command:
```shell
curl -X POST http://localhost:3001/mint \
-H "Content-Type: application/json" \
-d '{"walletAddress": "0x0365e0BcAd6D799b732ADB9673cB4C43688Bb450"}'
```

Once you confirmed the docker image is working correctly, you can terminate the process and run it in detached mode:

`docker run -d -p 3001:3001 transaction-manager`

