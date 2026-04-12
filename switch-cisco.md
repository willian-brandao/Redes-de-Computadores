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
Configurar a senha do modo privilegiado

```
S1>enable
S1#configure terminal
S1 (config)#enable
S1 (config)#enable password [senha]
S1 (config)# exit
```
Após realizar essa configuração, ao acessar o console e tentar acessar novamennte o modo privilegiado, a senha será requerida. 
```
S1>enable
Password:
```
As senhas usadas dessa forma, são armazenadas em texto simples, o que não é interessante para um dispositivo de acesso à rede. Nesse caso, é necessário usar a configuração de senha de modo criptografado. 
```
S1>enable
S1#configure terminal
S1 (config)#enable
S1 (config)#enable secret [senha]
S1 (config)# exit
```
Para que todas as senhas configuradas estejam criptografadas, usa-se o comando abaixo:
```
S1>enable
S1#configure terminal
S1 (config)#service password-encryption
S1 (config)# exit
```

É importante que os dispositivos da rede tenham um banner para informar sobre o dispositivo ou inibir o uso por pessoas não autorizadas.
```
S1#configure terminal 
S1(config)#banner motd "This is a secure system. Authorized Access Only!"
S1(config)#
S1(config)#exit
```


