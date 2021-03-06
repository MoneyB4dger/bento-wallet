# bento

a lightweight, online Bitcoin wallet

[https://gobento.app](https://gobento.app)

## To start

Set environment variables for:

```
dbUrl=mysql://user:password@host:port/database

baseUrl=https://bento.me

emailAddress=info@bento.me
mailgunDomain=mg.bento.me
mailgunSecret=key-2333322424242424334

network=testnet

nodeInfoMempoolFees=https://api.blockchain.info/mempool/fees
nodeInfoAddressUrl=https://testnet.blockchain.info/address/XXXXX?format=json
nodeInfoTxUrl=https://www.blockchain.com/btc-testnet/tx/XXXXX
nodeInfoUnspentUrl=https://testnet.blockchain.info/unspent?cors=true&active=XXXXX
nodeInfoRawTxUrl=https://testnet.blockchain.info/rawtx/XXXXX?cors=true&format=hex
nodePushTxUrl=https://api.blockcypher.com/v1/btc/test3/txs/push
```

Other requirements:

```
sudo apt-get install redis
sudo apt-get install mysql-server
sudo mysql_secure_installation
sudo mysql -u root -p
CREATE DATABASE bentodb;
ALTER USER 'root'@'localhost' IDENTIFIED WITH mysql_native_password BY 'password';
flush privileges;
```

Then

`npm run start-dev`

or for production:

Update `ecosystem.config.js` with env variables.

Run migration for the database - edit `conf/datastores.js` to run dev with database credentials.

`sh pm2-start.sh`

Then it's `pm2 logs`, `pm2 reload app`, etc.
```
