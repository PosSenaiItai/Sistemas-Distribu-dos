
# Sistemas-Distribuidos
Vamos implementar uma chamada de procedimento remoto (RPC) usando Docker e Python. RPC é um mecanismo de comunicação entre processos em sistemas distribuídos que permite que um processo invoque um procedimento em outro processo sem saber sua localização física.

Arquitetura do sistema

Nosso sistema RPC terá dois componentes: um servidor e um cliente. O servidor será responsável por implementar o procedimento a ser chamado remotamente. O cliente será responsável por enviar uma requisição ao servidor e receber a resposta.

Implementação do servidor

O servidor será implementado em um container Docker. O código do servidor é o seguinte:

