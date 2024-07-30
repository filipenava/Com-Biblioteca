# Filipe Augusto Nava De Almeida Pupo
## Trabalho 1 IPv6 com Biblioteca
### PRESIDENTE PRUDENTE/SP
#### 2024

## Sumário
1. [Visão Geral](#visao-geral)
   - Introdução ao programa de gerenciamento de endereçamento IPv6.
2. [Estrutura do Programa](#estrutura-do-programa)
   - Classes principais: IPv6Manager e IPv6ManagerApp.
3. [Dependências](#dependencias)
   - Requisitos: Python 3.x, bibliotecas ipaddress e tkinter.
4. [Classes e Métodos](#classes-e-metodos)
   - IPv6Manager: Inicialização, alocação (esquerda e direita), liberação e retorno de endereços.
   - IPv6ManagerApp: Inicialização, configuração da interface, ações de alocação, liberação e visualização de endereços.
5. [Função main()](#funcao-main)
   - Inicialização do programa e interface gráfica.
6. [Interface Gráfica](#interface-grafica)
   - Descrição dos elementos e funcionalidades.
7. [Como Usar](#como-usar)
   - Passos para utilizar o programa.
8. [Exemplo de Uso](#exemplo-de-uso)
   - Instruções para alocar, liberar e mostrar endereços.
9. [Como Executar o Programa](#como-executar-o-programa)

## Visão Geral
Este programa gerencia o endereçamento IPv6 utilizando alocação LEFTMOST e RIGHTMOST. Ele oferece uma interface gráfica para facilitar a interação do usuário, permitindo a alocação, liberação e visualização dos endereços IPv6.

## Estrutura do Programa
O programa é dividido em duas principais classes:
1. **IPv6Manager:** Responsável pela lógica de alocação e gerenciamento dos endereços IPv6.
2. **IPv6ManagerApp:** Responsável pela interface gráfica e interação com o usuário.

## Dependências
- Python 3.x
- Bibliotecas padrão: `ipaddress`, `tkinter`

## Classes e Métodos

### Classe IPv6Manager
Responsável pelo gerenciamento dos endereços IPv6.

**Métodos:**
- `__init__(self, base_address)`: Inicializa a rede base e as listas de endereços alocados.
  - `base_address`: Endereço IPv6 base da rede.
- `allocate_leftmost(self)`: Aloca o endereço IPv6 mais à esquerda disponível.
  - Retorna o endereço alocado ou None se não houver endereços disponíveis.
- `allocate_rightmost(self)`: Aloca o endereço IPv6 mais à direita disponível.
  - Retorna o endereço alocado ou None se não houver endereços disponíveis.
- `release_address(self, address)`: Libera um endereço IPv6 especificado.
  - `address`: Endereço IPv6 a ser liberado.
- `get_allocated_addresses(self)`: Retorna as listas de endereços alocados à esquerda e à direita.
  - Retorna uma tupla contendo as listas de endereços alocados à esquerda e à direita.

### Classe IPv6ManagerApp
Responsável pela interface gráfica do programa.

**Métodos:**
- `__init__(self, root, manager)`: Inicializa a interface gráfica do aplicativo.
  - `root`: Janela principal do tkinter.
  - `manager`: Instância da classe IPv6Manager.
- `setup_gui(self)`: Configura os elementos da interface gráfica.
- `allocate_leftmost(self)`: Manipula a ação de alocar o endereço mais à esquerda. Exibe uma mensagem de sucesso ou falha e atualiza a lista de endereços.
- `allocate_rightmost(self)`: Manipula a ação de alocar o endereço mais à direita. Exibe uma mensagem de sucesso ou falha e atualiza a lista de endereços.
- `release_address(self)`: Manipula a ação de liberar um endereço. Solicita ao usuário o endereço a ser liberado e executa a liberação.
- `show_allocated_addresses(self)`: Manipula a ação de mostrar endereços alocados. Atualiza as listas de endereços na interface gráfica.
- `update_address_lists(self)`: Atualiza as listas de endereços alocados na interface gráfica.

## Função main()
Função principal que inicializa o gerenciador de IPv6 e a interface gráfica.
- `base_address = "2001:db8::/32"`: Define o endereço base da rede IPv6.
- Cria uma instância de IPv6Manager com o endereço base.
- Cria a janela principal do tkinter.
- Inicializa a interface gráfica com IPv6ManagerApp.
- Inicia o loop principal do tkinter.

## Interface Gráfica
A interface gráfica utiliza tkinter para facilitar a interação do usuário com as seguintes funcionalidades:
- **Botão "Alocar o endereço mais à esquerda"**: Chama o método `allocate_leftmost`.
- **Botão "Alocar o endereço mais à direita"**: Chama o método `allocate_rightmost`.
- **Botão "Liberar um endereço"**: Chama o método `release_address`.
- **Botão "Mostrar endereços alocados"**: Chama o método `show_allocated_addresses`.
- **Botão "Sair"**: Fecha o programa.
- **Áreas de Texto**: Exibem os endereços alocados à esquerda e à direita, respectivamente.

## Como Usar
1. Execute o programa.
2. A interface gráfica exibirá opções para alocar o endereço mais à esquerda, alocar o endereço mais à direita, liberar um endereço, mostrar endereços alocados e sair.
3. Clique nos botões para executar as ações desejadas.
4. As áreas de texto na interface serão atualizadas automaticamente para mostrar os endereços alocados à esquerda e à direita, com barras de rolagem para facilitar a visualização.

## Exemplo de Uso
1. **Alocar o endereço mais à esquerda:**
   - Clique no botão "Alocar o endereço mais à esquerda".
   - Se um endereço estiver disponível, uma mensagem de sucesso será exibida e o endereço será adicionado à lista de endereços alocados à esquerda.
2. **Alocar o endereço mais à direita:**
   - Clique no botão "Alocar o endereço mais à direita".
   - Se um endereço estiver disponível, uma mensagem de sucesso será exibida e o endereço será adicionado à lista de endereços alocados à direita.
3. **Liberar um endereço:**
   - Clique no botão "Liberar um endereço".
   - Digite o endereço IPv6 a ser liberado.
   - Se o endereço for válido e estiver alocado, uma mensagem de sucesso será exibida e o endereço será removido da lista de endereços alocados.
4. **Mostrar endereços alocados:**
   - Clique no botão "Mostrar endereços alocados".
   - As áreas de texto serão atualizadas para exibir os endereços alocados à esquerda e à direita.

## Como Executar o Programa
**Pré-requisitos**
- Certifique-se de ter o Python 3.x instalado no seu sistema. Você pode fazer o download a partir do site oficial [python.org](https://www.python.org).

**Passo a Passo**
1. Abra o terminal ou prompt de comando.
2. Navegue até o diretório onde você salvou o arquivo `ipv6CB.py`. Você pode usar o comando `cd` para mudar o diretório.
   - Por exemplo: `cd caminho/para/o/diretorio`
3. Execute o programa digitando o comando: `python ipv6CB.py`
4. Instale o módulo `tkinter`, se necessário. Caso você receba um erro relacionado ao módulo `tkinter`, instale-o utilizando o gerenciador de pacotes pip com o comando: `pip install tk`
