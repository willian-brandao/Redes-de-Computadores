# Configuração do Switch Cisco

Modificar o hostname do dispositivo.

```
Switch> enable
Switch #configure terminal
Switch (config)# hostname S1
S1 (config)#exit 
```

Habilitar o acesso seguro ao console do dispositivo. A partir dessa configuração ao acessar o dispositivo sempre será requisitado a senha para autenticação.

```
S1> enable
S1# configure terminal
S1(config)# line console 0
S1(config-line)# password [senha]
S1(config-line)# login
S1(config-line)# exit
S1(config)# exit
S1# exit
```
O parâmetro *login* é usado para tornar obrigatório que ao acessar o console seja obrigatório.

Após a configuração, ao acessar o console o prompt exibirá:
```
-------------------------------------------

User Access Verification

Password: 
```


