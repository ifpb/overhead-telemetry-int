# overhead-telemetry-int
Repositório de código do projeto de pesquisa do laboratório LARIM

## Funcionamentos dos códigos
Este repositório contém os scripts necessários para realizar experimentos com telemetria em banda (In-band Network Telemetry - INT). Abaixo está uma explicação sobre os principais scripts e como utilizá-los.

### run.sh
O script run.sh automatiza a execução dos scripts send.py e receive.py, garantindo a sincronização entre as tarefas. Ele é executado no host local e dispara os comandos necessários em cada máquina virtual.

1. Inicia o receive.py no Host-2 para capturar pacotes INT.
2. Executa o send.py no Host-1 para enviar pacotes ao Host-2.
3. Reproduz o vídeo DASH no Host-2 com o VLC.
4. Gera tráfego adicional no Host-3 com o sinusoid.py.

### send.py
O script send.py é responsável por enviar pacotes INT do Host-1 para o Host-2, simulando tráfego de rede com metadados telemétricos gerados pelos switches programáveis.
Inicialmente, gera pacotes com metadados INT, configurados no código P4 dos switches. Os pacotes são enviados para o Host-2 em intervalos que podem ser ajustados diretamente no código.

### receive.py
O script receive.py captura, processa e armazena os pacotes INT recebidos no Host-2, extraindo informações importantes para análise.
Após o recebimento dos pacotes INT enviados pelo Host-1, os pacotes são processados para obter o cabeçalho do pacote juntamente com seus respectivos valores. Esses dados são salvos para posterior análise.

