Todos los programas estan en bin, se debe parar en esas carpeta
para lanzar los programas desde ahi

Pare crear el material criptografico:
./cryptogen generate --config=../network/crypto-config.yaml
el resultado es una capeta llamada "crypto-config" dentor de /bin

se usa el programa en go "cryptogen" se encuentra en la carperta /bin
el resultado es la creacion de una caperta con el material que se configuro
en el arcchivo "crypto-config.yaml"

==========================================================================================
Para crear el bloque genesis
se usa el programa "configtxgen#
./configtxgen -configPath ../network/ -profile ThreeOrgsOrdererGenesis -channelID system-channel -outputBlock ../network/channel-artifacts/genesis.block


==========================================================================================
Para crear la configuracion del canal
./configtxgen -configPath ../network/ -profile ThreeOrgsChannel -outputCreateChannelTx ../network/channel-artifacts/chanel.tx -channelID marketplace
"marketplace" es el nombre del canal

Para crear la configracion de los anchorpeers para cada organizacion
se debe especificar para que canal y para que organizacion

./configtxgen -configPath ../network/ -profile ThreeOrgsChannel -outputAnchorPeersUpdate ../network/channel-artifacts/Org1MSPanchors.tx -channelID marketplace -asOrg Org1MSP

./configtxgen -configPath ../network/ -profile ThreeOrgsChannel -outputAnchorPeersUpdate ../network/channel-artifacts/Org2MSPanchors.tx -channelID marketplace -asOrg Org2MSP

./configtxgen -configPath ../network/ -profile ThreeOrgsChannel -outputAnchorPeersUpdate ../network/channel-artifacts/Org3MSPanchors.tx -channelID marketplace -asOrg Org3MSP


==========================================================================================
como hacer ajustes ya desplegada la red?
1. contenedor fabric-tools (comandos)
2. sdk (aplicacion cliente)