# IaC-Simples
Esse bash provisiona a criação de usuários e suas devidas permissões. 

#!/bin/bash

echo “iniciando o provisionamento da IaC”

mkdir /publico /adm /ven /sec

groupadd GRP_VEN

groupadd GRP_ADM

groupadd GRP_SEC

echo “Criando usuarios do grupo: GRP_ADM”

useradd carlos -m -c “Carlos Adao” -s /bin/bash -p $(openssl passwd -6 1234)  -G GRP_ADM

passwd carlos -e

useradd maria -m -c “Maria Eva” -s /bin/bash -p $(openssl passwd -6 1234)  -G GRP_ADM

passwd maria -e

useradd joao -m -c “Joao Carlos” -s /bin/bash -p $(openssl passwd -6 1234)  -G GRP_ADM

passwd joao -e

echo “Criando usuarios do grupo: GRP_VEN”

useradd debora -m -c “Debora Almeida” -s /bin/bash -p $(openssl passwd -6 1234)  -G GRP_VEN

passwd debora -e

useradd sebastiana -m -c “Sebastiana Sousa” -s /bin/bash -p $(openssl passwd -6 1234)  -G GRP_VEN

passwd sebastiana -e

useradd roberto -m -c “Roberto Carlos” -s /bin/bash -p $(openssl passwd -6 1234)  -G GRP_VEN

passwd roberto -e

echo “Criando usuarios do grupo: GRP_SEC”
useradd josefina -m -c “Josefina Almeida” -s /bin/bash -p $(openssl passwd -6 1234)  -G GRP_SEC

passwd josefina -e

useradd amanda -m -c “Amanda Lira” -s /bin/bash -p $(openssl passwd -6 1234)  -G GRP_SEC

passwd amanda -e

useradd rogerio -m -c “Rogerio Silva” -s /bin/bash -p $(openssl passwd -6 1234)  -G GRP_SEC

passwd rogerio -e

chmod 777 /publico

chmod 770 /ven

chmod 770 /adm

chmod 770 /sec

chown root:adm /publico

chown root:GRP_ADM /adm

chown root:GRP_VEN /ven

chown root:GRP_SEC /sec

echo “IaC provisionada”
