# Trajetória de dados

## O que é o Modelo OSI?

- O Modelo OSI (Open Systems Interconnection) é um modelo conceitual que padroniza e divide as funções de comunicação de rede em sete camadas distintas. Ele foi desenvolvido pela ISO (International Organization for Standardization) para facilitar a compreensão e a implementação de redes de computadores. Cada uma das sete camadas do OSI tem responsabilidades específicas, indo desde a interação com os usuários finais até a transmissão física dos dados através do meio de comunicação.

---

## O que é um Modelo TCP/IP?

- O Modelo TCP/IP (Transmission Control Protocol/Internet Protocol) é uma família de protocolos de comunicação amplamente adotada para interconectar dispositivos em redes de computadores, incluindo a internet. Diferentemente do Modelo OSI, o TCP/IP possui uma abordagem mais simplificada, composta por quatro camadas principais. Ele foi desenvolvido originalmente para uso em redes de comutação de pacotes e é o protocolo fundamental da Internet.

---

## Modelo OSI

7. Aplicação
    - Prove serviços (dados das aplicações = dados relevantes para o usuário)

---

6. Apresentação
    - Tonar os dados legíveis para o receptor (recursos com Charset [UTF-8 e outros] e as criptografias são feitas aqui)

---

5. Sessão
    - Gerenciamento de sessão (ponte entre a camada de transporta e a necessidade da aplicação)

---

4. Transporte
    - Determinar a aplicação de origem e destino (endereçamento de portas). Confiabilidade. Segmentação e Reagrupamento ( que permite a multiplexação de conversações)

---

3. Rede
    - Endereçamento logico e (IP). Roteamento

---

2. Enlace de Dados
    - Endereçamento Físico. Controle de acesso ao meio físico. Verificação de erros (checksum)

---

1. Física
    - Transmissão binária no respectivo meio físico ( cabo de par trançado, fibra wireless)

---

## TCP/IP

- **Aplicação**
  
    (7) Aplicação
    
    ---
    
    (6) Apresentação
    
    ---
    
    (5) Sessão

---

- **Transporte**
  
    (4) Transporte

---

- **Internet**
  
    (3) Rede

---

- **Acesso à Rede**
  
    (2) Enlace de dados
    
    ---
    
    (1) Física

---

## Trajetória de dados

### **Aplicação**

- Na camada 7 - Aplicação
    - Aqui é onde o dado é criado e começa a ser guiado para as outras camada
    - Seja por qualquer tipo de aplicação, protocolo ou outros
- **Aplicação** → **Cria** → **Dado**

---

- Na camada 6 - Apresentação
    - Tradução de dados
    - Ou seja, se há diferença entre os dados aqui ela é traduzida, onde os 2 lados se intendam
    
    ---
    
    - Ela é responsável por tarefas como:
        - Criptografia
        - Compressão de dados
        - Conversão de formatos
        - Tradução de Formatos
- **Dado** → **Tradução** → **Dado** (traduzido)

---

- Na camada 5 - Sessão
    - Responsável por estabelecer e encerrar sessões entre os dispositivos
    - Gestão da conexão
    - Controle de diálogo
    - Sincronização entre aplicações em ambos os lados
- Não altera ou manipula o dado

---

### **Transporte**

- Na camada 4 - Transporte [ **TCP** ]
    - **Dado** é encapsulado
    - Ou seja, um cabeçalho (header) é adicionado ao dado
    - Nele é adicionado
        1. Porta de origem
        2. Porta de destino
        3. Mais extras
    - Transformando em um **segmento**
    
    ---
    
    - Tamanho do Header
        - 20 bytes
    - Adições para o Header ( exemplo )
        1. **Porta de Origem (16 bits):** 16 bits / 8 bits por byte = **`2 bytes`**
        2. **Porta de Destino (16 bits):** 16 bits / 8 bits por byte = **`2 bytes`**
        3. **Número de Sequência (32 bits):** 32 bits / 8 bits por byte = **`4 bytes`**
        4. **Número de Acknowledgment (32 bits):** 32 bits / 8 bits por byte = **`4 bytes`**
        5. **Tamanho do Cabeçalho (4 bits):** 4 bits / 8 bits por byte = **`0,5 bytes`** (arredondado para **`1 byte`**)
        6. **Bandeiras (6 bits):** 6 bits / 8 bits por byte = **`0,75 bytes`** (arredondado para **`1 byte`**)
        7. **Janela de Recebimento (16 bits):** 16 bits / 8 bits por byte = **`2 bytes`**
        8. **Checksum (16 bits):** 16 bits / 8 bits por byte = **`2 bytes`**
        9. **Ponteiro de Urgência (16 bits):** 16 bits / 8 bits por byte = **`2 bytes`**
        
        ---
        
        - Resultando em = **`20 bytes`**
- **Dado** → **Encapsulamento** → **Segmento**

---

### **Internet**

- Na camada 3 - Rede [ **IP** ]
    - O **segmento** é encapsulado
    - Ou seja, um cabeçalho (header) onde é adicionado ao dado
    - Nele é adicionado
        1. IP de origem (192.168.x.x)
        2. IP de destino (192.168.x.x)
        3. Mais extras
    - Transformando em um **Pacote**
    
    ---
    
    - Tamanho do Header
        - 20 bytes
    - Adições para o Header
        1. **Versão (4 bits):** 4 bits / 8 bits por byte = **`0,5 bytes`**
        2. **Tamanho do Cabeçalho (4 bits):** 4 bits / 8 bits por byte = **`0,5 bytes`**
        3. **Tipo de Serviço (8 bits):** 8 bits / 8 bits por byte = **`1 byte`**
        4. **Comprimento Total (16 bits):** 16 bits / 8 bits por byte = **`2 bytes`**
        5. **Identificação (16 bits):** 16 bits / 8 bits por byte = **`2 bytes`**
        6. **Flags e Offset de Fragmentação (3 bits + 13 bits):** 16 bits / 8 bits por byte = `**2 bytes**`
        7. **Tempo de Vida (8 bits):** 8 bits / 8 bits por byte = **`1 byte`**
        8. **Protocolo (8 bits):** 8 bits / 8 bits por byte = **`1 byte`**
        9. **Checksum do Cabeçalho (16 bits):** 16 bits / 8 bits por byte = **`2 bytes`**
        10. **Endereço IP de Origem (32 bits):** 32 bits / 8 bits por byte = **`4 bytes`**
        11. **Endereço IP de Destino (32 bits):** 32 bits / 8 bits por byte = **`4 bytes`**
        
        ---
        
        - Resultando em = **`20 bytes`**
    
    ---
    
    - Observação 1:
        - Caso não houver o IP de destino é feita uma requisição DNS para obter o IP
        - Para isso haverá 2 etapas
            - Requisição DNS para resolver o IP
            - Resposta da resolução IP
    - Observação 2:
        - Ao enviar para um rede externa, o IP privado tem q mudar para um IP público
        - Então os dados são alterados, modificando o IP de origem com o NAT
        - Porém o de destino permanece
    
    ---
    
    - É aqui que ocorre a fragmentação
- **Segmento** → **Encapsulamento** → **Pacote**

---

### **Acesso à Rede**

- Na camada 2 - Enlace de Dados [ **Ethernet** ]
    - O **Pacote** é encapsulado
    - Ou seja, um cabeçalho (header) é adicionado ao dado
    - Nele é adicionado
        1. MAC de Destino
        2. MAC de Origem
        3. Mais tipo do protocolo
    - Transformando em um **Quadro** (Frame)
    
    ---
    
    - Tamanho == 1514 do quadro que pode ser transferido
        - Isso pode ser mudado na configuração do comutador
    
    ---
    
    - Tamanho do Header
        - 14 bytes
    - Adições para o Header
        - MAC de Origem [ Placa de rede ] ( **`6 bytes`** )
        - MAC de Destino [ Placa de rede ] ( `**6 bytes**` )
            - ATENÇÃO
            - Se o destino estiver fora da rede, o MAC será do próximo destino, será para o GATEWAY
            - Caso estiver na mesma rede, então ele paga o MAC da própria máquina
            
            ---
            
            - Então se for fora da rede será:
                - MAC Origem
                - MAC Gateway
            - Se for dentro da rede será
                - MAC Origem
                - MAC da Máquina destino
        - Tipo de protocolo ( `**2 bytes**` )
        
        ---
        
        - Resultando em = **`14 bytes`**
    
    ---
    
    - Observação 1:
        - Caso não houver o MAC de destino é feita uma requisição ARP para obter o MAC
        - Para isso haverá 2 etapas
            - Broadcast é usado para enviar informações para todos os dispositivos em uma rede local (LAN)
            - Unicast, por outro lado, é usado para comunicação ponto a ponto, onde um dispositivo envia dados diretamente para outro dispositivo específico
    - Observação 2:
        - Sempre que um pacote é passado para outro router ele abre, pois o destino está para ele, porém o dado não é pra ele, então ele encapsula novamente colocando o próprio MAC como origem e o MAC de destino o próximo router
        - Então o MAC sempre vai mudando até chegar aonde deve
        - Sendo assim, essa camada muda os dados, modificando o MAC de Origem
    - Observação 3:
        - Mesmo se o meio de transporte mudar seja para outros cabos físicos ou por wi-fi ou qualquer outro, o Quadro ( Frame ) NÃO VAI MUDAR
        - Somente vai mudar se entrar em outra rede
- **Pacote** → **Encapsulamento** → **Quadro** (Frame)

---

- Na camada 1 - Física [ **Linguagem de máquina** ]
    - O **Quadro** (Frame) é transformado em 1 e 0
    - Ou seja, transformado em linguagem de máquina
    
    ---
    
- **Quadro** → **Transformado** → **Bits**
