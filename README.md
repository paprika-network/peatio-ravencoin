clone peatio

go into the folder /lib/peatio

create a folder named ravencoin

upload the files blockchain.rb / client.rb / wallet.rb

go in the folder /peatio/config/initializers

open the file blockchain_api.rb

and paste this

Peatio::Blockchain.registry[:ravencoin] = Ravencoin::Blockchain

save and exit

open the file wallet_api.rb in the same folder and paste this

Peatio::Wallet.registry[:ravencoind] = Ravencoin::Wallet

save and exit

now you have ravencoin ready to be added to tower

clone your new image of peatio

docker build -t peatio:custom image

change peatio image in /opendax/config/app.yml

rake render:config && rake service:app
