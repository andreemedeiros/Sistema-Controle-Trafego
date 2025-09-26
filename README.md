# Sistema-Controle-Trafego-HCPN
Modelagem de um Sistema de Controle de Tráfego Urbano Usando Redes de Petri Coloridas Hierárquicas (HCPN)

## Index
- [Descrição](#Descrição)
- [Estrutura](#Estrutura)
- [Cenários](#Cenários)
- [Requisitos](#Requisitos)
- [Execução](#Execução)
- [Autores](#Autores)
- [Licença](#Licença)

## Descrição

Este projeto tem como finalidade a aplicação prática de Redes de Petri Coloridas Hierárquicas (HCPN) para a modelagem e o estudo de Sistemas a Eventos Discretos (SED). A abordagem HCPN incorpora o conceito de "cores" — dados anexados aos tokens — e uma estrutura hierárquica de módulos, o que permite representar sistemas complexos de maneira organizada e eficiente. Para desenvolver e analisar os modelos, foi utilizado o software CPN Tools.

O trabalho concentra-se no cenário de um sistema de controle de tráfego em um cruzamento de quatro vias. Sistemas de tráfego são exemplos clássicos de SED, nos quais eventos isolados — a chegada de um veículo, a mudança de um semáforo — provocam mudanças de estado. A estrutura hierárquica das HCPN foi explorada para dividir o sistema em componentes menores, simplificando a análise de aspectos como fluxo contínuo e eficiência.

O modelo representa um cruzamento de quatro vias (Via 1, Via 2, Via 3 e Via 4) com as seguintes características:

- Semáforos individuais para cada via.
- Simulação de filas de veículos em cada direção.
- Definição de ciclos semafóricos: verde por 30 segundos, amarelo por 5 segundos e vermelho por 60 segundos.
- Distinção entre tipos de veículos, como Carro e Ônibus.

## Estrutura

O modelo é organizado de forma hierárquica para simplificar a complexidade do sistema.

- **Nível superior (página "Pagina Principal"):** Oferece uma visão geral do cruzamento. Este nível contém o local central "Cruzamento" e quatro transições de substituição (`Via 1`, `Via 2`, `Via 3`, `Via 4`), onde cada uma representa um semáforo e sua via correspondente.

- **Módulos subordinados (páginas "Semaforo1", "Semaforo2", "Semaforo3", "Semaforo4"):** Cada página modela o comportamento de um semáforo e o fluxo de veículos de sua respectiva via.
    - **Controle de semáforos:** Modela as três fases do semáforo (Verde, Amarelo, Vermelho) usando lugares específicos para cada estado. As transições entre os estados são temporizadas para simular a duração de cada fase.
    - **Gerenciamento de filas:** Um lugar (ex: "Fila de veiculos 1") armazena os veículos que aguardam para cruzar. Os tokens neste lugar são coloridos para representar diferentes tipos de veículos.
    - **Cores (Color Sets):** O projeto utiliza dois conjuntos de cores principais:
        - `EstadoSemaforo`: Define os possíveis estados de um semáforo (`Verde`, `Amarelo`, `Vermelho`).
        - `Veiculo`: Define os tipos de veículos no sistema (`Carro`, `Onibus`).
    - **Temporização:** As transições são temporizadas para simular a duração real dos eventos. Por exemplo, a transição de Verde para Amarelo ocorre após 30 unidades de tempo (`@+30`), de Amarelo para Vermelho após 5 (`@+5`), e de Vermelho para Verde após 60 (`@+60`).

## Cenários

O modelo atual está configurado para simular um cenário de tráfego normal, sem um sistema de prioridade explícito para ônibus. A configuração inicial do modelo inclui:
- **Via 3:** Um token do tipo `Carro` na fila de veículos.
- **Via 4:** Um token do tipo `Onibus` na fila de veículos.

Os semáforos operam em ciclos fixos e independentes, gerenciando o fluxo de veículos com base nos tempos pré-definidos para cada estado (verde, amarelo, vermelho).

## Requisitos

- [Ferramenta: CPN Tools](https://cpntools.org/)

  ## Autores

- [André Medeiros](https://github.com/andreemedeiros)
- [João Marcelo](https://github.com/marcello-rbr)
- [Vitor Lucas](https://github.com/Vitorluca)

Contribua com o projeto [Supervised-Control-Project](https://github.com/andreemedeiros/Sistema-Controle-Trafego/graphs/contributors)

Video explicativo no [Youtube](https://www.youtube.com/watch?v=sKgzRScjHkg)

## Licença

Este projeto é licenciado pela MIT License - veja [LICENSE.md](LICENSE.md) para mais detalhes.

## Execução

Com o CPN Tools instalado, execute o arquivo "ControleTrafego_v4.cpn".
