## Descripción
How about we take you on an adventure on exploring certificate signing requests Take a look at this CSR file [here](https://challenge-files.cylabacademy.net/library/adc86ad64fdfdb57ccdc30281c4c93aa2a8a913259426681737dc7e69d257275/readmycert.csr)

## Solución
mkdir -p ~/readmycert-aaron
cd ~/readmycert-aaron
wget -O readmycert.csr 'https://challenge-files.cylabacademy.net/library/adc86ad64fdfdb57ccdc30281c4c93aa2a8a913259426681737dc7e69d257275/readmycert.csr'
openssl req -in readmycert.csr -noout -subject

academy{read_mycert_1767ceb4}

## Notas Adicionales


## Referencias