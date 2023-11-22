
# Sistemas-Distribuidos
Vamos implementar uma chamada de procedimento remoto (RPC) usando Docker e Python. RPC é um mecanismo de comunicação entre processos em sistemas distribuídos que permite que um processo invoque um procedimento em outro processo sem saber sua localização física.

Arquitetura do sistema

Nosso sistema RPC terá dois componentes: um servidor e um cliente. O servidor será responsável por implementar o procedimento a ser chamado remotamente. O cliente será responsável por enviar uma requisição ao servidor e receber a resposta.

# Implementação do servidor

O servidor será implementado em um container Docker. O código do servidor é o hello.ipynb:

Esta função hello() recebe o nome de uma pessoa como argumento e retorna uma mensagem de saudação. A função main() do servidor cria um socket TCP e o associa à porta 8080. Em seguida, o servidor fica ouvindo requisições de clientes. Quando um cliente se conecta, o servidor recebe o nome da pessoa a ser saudada e chama a função hello() para retornar a mensagem de saudação. A mensagem de saudação é então enviada de volta ao cliente.

# Implementação do cliente

O cliente também será implementado em um container Docker. O código do cliente é o cliente.ipynb:

