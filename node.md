# Verificação de Conexão com Nós RPC da Binance Smart Chain

Este script Python permite verificar a conexão com nós RPC da Binance Smart Chain (BSC) e obter informações sobre o número do último bloco em cada nó.

## Como Usar

Certifique-se de ter Python instalado em seu ambiente de desenvolvimento.

1. Clone o repositório ou copie o script Python para o seu projeto.
2. Instale a biblioteca `web3` usando o gerenciador de pacotes `pip`:
3. Execute o script Python. Ele irá iterar sobre uma lista de URLs de nós RPC da BSC e tentar conectar-se a cada um deles.

## Descrição do Código

O código realiza as seguintes operações:

1. Define uma lista `node_urls` que contém URLs de nós RPC da Binance Smart Chain (BSC).
2. Itera sobre cada URL na lista `node_urls`.
3. Tenta criar uma conexão com o nó usando o URL atual.
4. Se a conexão for bem-sucedida, obtém o número do último bloco da blockchain associada ao nó.
5. Imprime uma mensagem indicando que a conexão foi bem-sucedida, juntamente com o URL do nó e o número do último bloco.
6. Se ocorrer uma exceção durante a tentativa de conexão, imprime uma mensagem indicando que a conexão falhou, juntamente com o URL do nó e detalhes da exceção.

Espero que este script seja útil para verificar a conectividade com os nós RPC da Binance Smart Chain!

```python
from web3 import Web3

# Lista de nós RPC da Binance Smart Chain (BSC)
node_urls = [
    "https://bsc-dataseed1.binance.org/",
    "https://bsc-dataseed2.binance.org/",
    "https://bsc-dataseed3.binance.org/",
    "https://bsc-dataseed4.binance.org/",
    "https://bsc-dataseed1.defibit.io/",
    "https://bsc-dataseed2.defibit.io/",
    "https://bsc-dataseed3.defibit.io/",
    "https://bsc-dataseed4.defibit.io/",
    "https://bsc-dataseed1.ninicoin.io/",
    "https://bsc-dataseed2.ninicoin.io/",
    "https://bsc-dataseed3.ninicoin.io/",
    "https://bsc-dataseed4.ninicoin.io/"
]

# Iterar sobre todos os URLs da lista de nós
for url in node_urls:
    try:
        # Criar a conexão com o nó
        web3 = Web3(Web3.HTTPProvider(url))
        # Tentar obter o número do último bloco
        latest_block = web3.eth.block_number
        # Se nenhuma exceção for lançada, a conexão foi bem-sucedida
        print("-" * 50)
        print("Connection Successful")
        print("Connected to:", url)
        print("Latest Block Number:", latest_block)
        print("-" * 50)
    except Exception as e:
        # Se ocorrer uma exceção, a conexão falhou
        print(f"Connection failed for {url}: {e}")

```
