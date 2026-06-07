
## Configuração Inicial do Switch

### Etapas Iniciais

1 - O switch carrega um post (power-on self-test) que fica armazenado na ROM. O POST verifica o subsistema da CPU. Ele testa a CPU, DRAM e a parte do dispositivo flash que compõeo sistema de arquivos flash. 

2 - Depois, o switch carrega o software carregador de inicialização. O carregador de inicialização (boot loader) é um programa pequeno armazenado na ROM que é executada imediatamente após a conclusão do POST. 

3 - O carregador de inícialização executa inicialização de baixo nível da CPU. Ele inicializa os registros da CPU, que controlam onde a memória física é mapeada, a quantidade de memória e sua velocidade. 

4 - O carregador de inicializaçao inicializa o sistema de arquivos da memória flash na placa de sistema.

5 - O carregador inicializa e carrega uma imagem do software de sistema operacional IOS padrão na memória e passa o controle do switch para o IOS.


