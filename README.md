# Sistema-Controle-Trafego-HCPN
Modelagem de um Sistema de Controle de Tráfego com Prioridade para Transporte Público Usando Redes de Petri Coloridas Hierárquicas (HCPN)

## Index
- [Descrição](#Descrição)
- [Estrutura](#Estrutura)
- [Cenários](#Cenários)
- [Requisitos](#Requisitos)
- [Execução](#Execução)
- [Autores](#Autores)
- [Licença](#Licença)

## Descrição

Este projeto visa proporcionar uma experiência prática na modelagem e análise de sistemas a eventos discretos (SED) utilizando Redes de Petri Coloridas Hierárquicas (HCPN). As HCPN são uma extensão das Redes de Petri tradicionais que incorporam cores (dados associados aos tokens) e hierarquia (módulos reutilizáveis), permitindo modelar sistemas complexos de forma modular e eficiente. A ferramenta a ser utilizada é o CPN Tools, que suporta a criação, simulação e análise de modelos HCPN.

O tema escolhido é a modelagem de um sistema de controle de tráfego em uma interseção urbana com prioridade para veículos de transporte público (como ônibus ou metrôs de superfície). Esse tipo de sistema é um exemplo clássico de SED, em que eventos discretos (como mudanças de semáforo, chegada de veículos ou detecção de ônibus) alteram o estado do sistema. A hierarquia permite decompor o modelo em subsistemas, facilitando a análise de propriedades como ausência de deadlocks, vivacidade e desempenho.

Considere uma interseção em cruzamento com quatro direções (Norte-Sul e Leste-Oeste), incluindo:

- Semáforos para veículos comuns e pedestres.

- Uma faixa dedicada para transporte público (ex.: ônibus) com sensor de detecção que ativa prioridade (prolonga o verde ou interrompe o ciclo normal).

- Filas de veículos em cada direção, com chegada aleatória modelada por distribuições probabilísticas (ex.: Poisson para chegadas).

- Tempos de ciclo: verde padrão de 30 segundos, amarelo de 5 segundos, vermelho ajustável; prioridade estende o verde em 15 segundos para ônibus.

## Estrutura

- Nível superior (página principal): visão geral da interseção, com substituições para módulos como "Controle de Semáforos", "Gerenciamento de Filas" e "Detecção de Prioridade".

- Módulos subordinados:
  - Controle de semáforos: modela as fases (verde, amarelo, vermelho) usando lugares coloridos para estados e transições temporizadas.

  - Gerenciamento de filas: lugares para filas de veículos (tokens coloridos representam tipos: carro comum, ônibus, pedestre), com transições para chegada e partida.

  - Detecção de prioridade: módulo que verifica a presença de ônibus (via token colorido) e ajusta o ciclo de semáforos.

  - Cores (Color Sets): defina conjuntos como `Veiculo = product Int * String` (ID do veículo e tipo: "carro", "onibus", "pedestre"); `EstadoSemaforo = enum with Verde | Amarelo | Vermelho`.

  - Temporização: use transições timed para simular delays reais (ex.: `@+30` para 30 unidades de tempo no verde).

## Cenários

  - Tráfego normal sem prioridade.

  - Tráfego com chegada de ônibus, ativando prioridade.

  - Sobrecarga: Alta taxa de chegada de veículos, analisando congestionamento.

  - Falhas: Simule falha em sensor de detecção e verifique impactos.

## Requisitos

- [Ferramenta: CPN Tools](https://cpntools.org/)

## Execução

Execute o arquivo "Projeto2SED" dentro da pasta source:
```
Projeto2SED.cpn
```

## Autores

- [André Medeiros](https://github.com/andreemedeiros)

- [João Marcelo](https://github.com/marcello-rbr)

- [Vitor Lucas](https://github.com/Vitorluca)

Contribua com o projeto [Supervised-Control-Project](https://github.com/andreemedeiros/Sistema-Controle-Trafego/graphs/contributors)

Video explicativo no [Youtube]()

## Licença

Este projeto é licenciado pela MIT License - veja [LICENSE.md](LICENSE.md) para mais detalhes.
