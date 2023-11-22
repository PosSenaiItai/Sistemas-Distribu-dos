
# Sistemas-Distribuidos
Vamos implementar uma chamada de procedimento remoto (RPC) usando Docker e Python. RPC é um mecanismo de comunicação entre processos em sistemas distribuídos que permite que um processo invoque um procedimento em outro processo sem saber sua localização física.

Arquitetura do sistema

Nosso sistema RPC terá dois componentes: um servidor e um cliente. O servidor será responsável por implementar o procedimento a ser chamado remotamente. O cliente será responsável por enviar uma requisição ao servidor e receber a resposta.

# Implementação do servidor

O servidor será implementado em um container Docker. O código do servidor é o hello.ipynb:

Esta função hello() recebe o nome de uma pessoa como argumento e retorna uma mensagem de saudação. A função main() do servidor cria um socket TCP e o associa à porta 8080. Em seguida, o servidor fica ouvindo requisições de clientes. Quando um cliente se conecta, o servidor recebe o nome da pessoa a ser saudada e chama a função hello() para retornar a mensagem de saudação. A mensagem de saudação é então enviada de volta ao cliente.

# Implementação do cliente

O cliente também será implementado em um container Docker. O código do cliente é o cliente.ipynb:

Esta função main() cria um socket TCP e o conecta ao servidor na porta 8080. Em seguida, a função solicita o nome do usuário e envia o nome para o servidor. O servidor então retorna a mensagem de saudação, que é impressa na tela do cliente.

# Execução da demonstração

Para executar a demonstração, precisamos criar dois containers Docker: um para o servidor e outro para o cliente. Podemos fazer isso usando os seguintes comandos:


docker build -t server .
docker build -t client .


Estes comandos criarão dois containers Docker com os nomes server e client.
Para iniciar o servidor, podemos usar o seguinte comando:


docker run -p 8080:8080 server


Este comando iniciará o servidor na porta 8080.
Para iniciar o cliente, podemos usar o seguinte comando:


docker run client


Este comando iniciará o cliente e solicitará o nome do usuário.
Após inserir o nome do usuário, o cliente enviará a requisição ao servidor. O servidor retornará a mensagem de saudação, que será impressa na tela do cliente.
Exemplo de execução
Após executar os comandos acima, podemos ver o seguinte resultado:


Digite seu nome: João

Olá, João!


Neste exemplo, o nome do usuário é "João". O servidor retorna a mensagem "Olá, João!".
