
# Sistemas-Distribudos
Vamos implementar uma chamada de procedimento remoto (RPC) usando Docker e Python. RPC é um mecanismo de comunicação entre processos em sistemas distribuídos que permite que um processo invoque um procedimento em outro processo sem saber sua localização física.

Arquitetura do sistema

Nosso sistema RPC terá dois componentes: um servidor e um cliente. O servidor será responsável por implementar o procedimento a ser chamado remotamente. O cliente será responsável por enviar uma requisição ao servidor e receber a resposta.

Implementação do servidor

O servidor será implementado em um container Docker. O código do servidor é o seguinte:

# Python


import socket

def hello(name):
    return f"Olá, {name}!"

with socket.socket(socket.AF_INET, socket.SOCK_STREAM) as s:
    s.bind(("0.0.0.0", 8080))
    s.listen(1)

    conn, addr = s.accept()

    data = conn.recv(1024)
    name = data.decode("utf-8")

    response = hello(name)

    conn.sendall(response.encode("utf-8"))
    conn.close()
