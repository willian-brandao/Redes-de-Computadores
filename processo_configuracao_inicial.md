
## Configuração Inicial do Switch

### Etapas Iniciais

1 - O switch carrega um post (power-on self-test) que fica armazenado na ROM. O POST verifica o subsistema da CPU. Ele testa a CPU, DRAM e a parte do dispositivo flash que compõeo sistema de arquivos flash. 

2 - Depois, o switch carrega o software carregador de inicialização. O carregador de inicialização (boot loader) é um programa pequeno armazenado na ROM que é executada imediatamente após a conclusão do POST. 

3 - O carregador de inícialização executa inicialização de baixo nível da CPU. Ele inicializa os registros da CPU, que controlam onde a memória física é mapeada, a quantidade de memória e sua velocidade. 

4 - O carregador de inicializaçao inicializa o sistema de arquivos da memória flash na placa de sistema.

5 - O carregador inicializa e carrega uma imagem do software de sistema operacional IOS padrão na memória e passa o controle do switch para o IOS.

## Sistema de Boot

O switch tenta inicializar automaticamente usando informações na variável de ambiente BOOT. Se esta variável nçao estiver definida, o switch tentará carregar e executar o primeiro executável que encontrar. Nos switches 2960, o arquivo de imagem normalmente está contido em um diretório que tem o nome do arquivo de imagem.

O sistema operacional IOS inicializa as interfaces usando os comandos do Cisco IOS encontrados nos arquivo startup-config. O arquivo startup-config é chamado config.text e está localizado em flash.

A variável de ambiente BOOT é definida usando o comando modo de configuração boot system global.
```
S1(config)# boot system flash:/c2960-lanbasek9-mz.150-2.SE/c2960-lanbasek9-mz.150-2.SE.bin
```
### Estrutura do Comando 

O comando principal
```
boot system
```
O dispositivo de armazenamento
```
flash:
```
O caminho para o sistema de arquivos
```
c2960-lanbasek9-mz.150-2.SE/
```
O nome do arquivo IOS
```
c2960-lanbasek9-mz.150-2.SE.bin
```

## Indicadores de LED
Os LED do switch servem para monitorar rapidamente o desempenho e a atividade do switch. Os interruptores de diferentes modelos e conjuntos de recursos terão LEDs diferentes e sua colocação no painel frontal do interruptor também pode variar. 

<img width="837" height="313" alt="image" src="https://github.com/user-attachments/assets/48b53386-46e5-46ab-912c-41413094c51a" />

### 1 SYST

**LED de Sistema**

Mostra se o sistema está recebedno energia e está funcionando corretamente. Se o LED estiver desligado, significa que o sistema não está ligado. Se o LED estiver verde, o sistema está funcionando normalmente. Se o LED estiver âmbar, o sistema está recebendo energia, mas não está funcionando corretamente. 

### 2 RPS 
**LED do Sistema Redundante de fonte(RPS)**

Mostra o status do RPS. Se o LED estiver apagado, o RPS está desativado ou não foi conectado corretamente. Se o LED estiver verde, o  RPS está conectado e pronto para fornecer energia reserva. Se o LED estiver piscando em verde, o RPS está conectado mas não está disponível porque está fornecendo energia para outro dispositivo. Se o LED estiver amarelo, o RPS está no modo de espera ou em uma condição de falha. Se o LED estiver piscando na cor âmbar, a fonte de alimentação interna do comutador falhou e o RPS está fornecendo energia. 

### 3 STAT 

**LED de Status da porta**

Indica que o modo de status da porta está selecionado quando o LED está verde. Este é o modo padrão. Quando selecionado, os LEDs de porta exibirão cores com significados diferentes:

* LED Desligado - Não há link ou a porta foi desligada administrativamente.
* LED Verde - Há um link presente. Quando a porta estiver piscando em VERDE, significa que há atividade e a porta está recebendo ou enviando dados.
* LED Verde-Âmbar - Falha de Link.
* LED Amarelo - 

