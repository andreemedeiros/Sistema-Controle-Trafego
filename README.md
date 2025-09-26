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

Este projeto tem como finalidade a aplicação prática de Redes de Petri Coloridas Hierárquicas (HCPN) para a modelagem e o estudo de Sistemas a Eventos Discretos (SED). A abordagem HCPN incorpora o conceito de "cores" - dados anexados aos tokens - e uma estrutura hierárquica de módulos, o que permite representar sistemas complexos de maneira organizada e eficiente. Para desenvolver e analisar os modelos, será utilizado o software CPN Tools.

O trabalho concentrar-se-á no cenário de um sistema de controle de tráfego em um cruzamento, com foco na priorização de veículos de transporte público, como ônibus. Sistemas de tráfego são exemplos clássicos de SED, nos quais eventos isolados - a chegada de um ônibus, a mudança de um semáforo - provocam mudanças de estado. A estrutura hierárquica das HCPN será explorada para dividir o sistema em componentes menores, simplificando a análise de aspectos como fluxo contínuo, ausência de bloqueios e eficiência.

O modelo representará um cruzamento de quatro vias (Norte-Sul e Leste-Oeste) com as seguintes características:

- Semáforos para veículos comuns e para a travessia de pedestres.

- Simulação de filas de veículos em cada direção.

- Definição de ciclos semafóricos: verde por 30 segundos, amarelo por 5 segundos, e tempo de vermelho variável.

## Estrutura

- Nível superior (página principal): visão geral da interseção, com substituições para módulos como "Controle de Semáforos", "Gerenciamento de Filas".

- Módulos subordinados:
  - Controle de semáforos: Modela as fases (verde, amarelo, vermelho) usando lugares coloridos para estados e transições temporizadas.

  - Gerenciamento de filas: Lugares para filas de veículos (tokens coloridos representam tipos: carro comum, ônibus, pedestre), com transições para chegada e partida.

  - Cores (Color Sets): Conjuntos como ID do veículo e tipo: "carro", "onibus", "pedestre".

  - Temporização: Transições timed para simular delays reais (ex.: `@+30` para 30 unidades de tempo no verde).

## Cenários

  - Tráfego normal sem prioridade.

## Requisitos

- [Ferramenta: CPN Tools](https://cpntools.org/)

## Execução

Com o CPN Tools instalado, execute o arquivo "ControleTrafego_v1.cpn" dentro da pasta source:
```
ControleTrafego_v3.cpn
```

## Autores

- [André Medeiros](https://github.com/andreemedeiros)

- [João Marcelo](https://github.com/marcello-rbr)

- [Vitor Lucas](https://github.com/Vitorluca)

Contribua com o projeto [Supervised-Control-Project](https://github.com/andreemedeiros/Sistema-Controle-Trafego/graphs/contributors)

Video explicativo no [Youtube]()

## Licença

Este projeto é licenciado pela MIT License - veja [LICENSE.md](LICENSE.md) para mais detalhes.
