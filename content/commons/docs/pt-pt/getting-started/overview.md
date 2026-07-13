---
title: Visão Geral
description: Descubra o que é o TransitCore, como funciona e os princípios que orientaram o seu design.
---

# Visão Geral

Bem-vindo ao **TransitCore**.

O TransitCore é um framework modular de simulação ferroviária para Minecraft, concebido para criar redes ferroviárias realistas através de um poderoso sistema de Addons e da linguagem de script **LuaTC**.

Ao contrário dos mods ferroviários tradicionais, o TransitCore não fornece diretamente veículos ou infraestruturas. O framework disponibiliza o motor de simulação, enquanto os comboios, metros, elétricos, vias, sinais e outros conteúdos são distribuídos como Addons independentes.

<Alert severity="info">

O TransitCore separa completamente o **motor** do **conteúdo**. O framework fornece os diferentes sistemas de simulação, enquanto os Addons trazem os veículos, as vias, os sinais, as estações e todos os outros elementos ferroviários.

</Alert>

## Porquê o TransitCore?

O TransitCore foi desenvolvido em torno de quatro princípios fundamentais.

### Realismo

O objetivo do TransitCore é reproduzir o funcionamento de uma rede ferroviária da forma mais fiel possível, mantendo-se perfeitamente integrado no Minecraft.

O framework suporta nomeadamente:

- Uma simulação avançada dos veículos.
- Sistemas de travagem realistas.
- A sinalização ferroviária.
- Os sistemas elétricos.
- A gestão de passageiros.
- A sincronização multijogador.
- As linhas ferroviárias de alta velocidade.

### Modularidade

Tudo no TransitCore é concebido de forma modular.

O próprio framework contém apenas os motores necessários ao seu funcionamento.

Os veículos, infraestruturas, sons, texturas, interfaces de utilizador e extensões de gameplay são distribuídos como Addons que podem ser instalados, atualizados ou removidos independentemente uns dos outros.

### Desempenho

O TransitCore foi concebido para gerir de forma eficiente redes ferroviárias de grande dimensão.

O renderizado, a física, a rede e a simulação são otimizados de forma a limitar os cálculos desnecessários mantendo um comportamento realista.

### Extensibilidade

Todas as funcionalidades oferecidas pelo TransitCore são acessíveis através de **LuaTC**, a linguagem de script oficial do framework.

Os developers podem assim criar Addons completos sem terem de modificar o código Java do TransitCore.

## Arquitetura

O TransitCore é composto por vários sistemas independentes que funcionam em conjunto.

```text title="Arquitetura do TransitCore"
TransitCore
├── Core Engine
├── Physics Engine
├── Rendering Engine
├── Railway Engine
├── Signaling Engine
├── Electrical Engine
├── Audio Engine
├── Animation Engine
├── Networking Engine
├── LuaTC Runtime
└── Addon Loader
```

Cada sistema é responsável por uma parte precisa do framework e comunica com os outros através de APIs públicas e estáveis.

## LuaTC

O LuaTC é a linguagem de script oficial do TransitCore.

Baseado em Lua, estende-o com APIs especialmente concebidas para a simulação ferroviária. Permite aos developers interagir com o framework sem terem de aceder diretamente aos mecanismos internos do Minecraft.

```luatc title="Criar um veículo"
local train = tc.vehicle.create(tc.VehicleType.TRAIN)

train:setName("TGV Duplex")
train:setMaximumSpeed(320)
train:setMass(383000)
```

<Alert severity="success">

A maioria dos Addons pode ser desenvolvida integralmente em LuaTC. O Java só é necessário para estender o funcionamento interno do TransitCore.

</Alert>

## Os Addons

O TransitCore baseia-se numa arquitetura totalmente assente em Addons.

Cada Addon é carregado independentemente e comunica com o framework através de LuaTC.

Um Addon pode adicionar, por exemplo:

- Comboios.
- Metros.
- Elétricos.
- Funiculares.
- Vias ferroviárias.
- Sinais.
- Catenárias.
- Estações.
- Interfaces de utilizador.
- Sons.
- Extensões de gameplay.

Se um Addon encontrar um erro durante o carregamento, o TransitCore desativa-o automaticamente sem impedir o framework ou os outros Addons de arrancar.

```text title="Exemplo de estrutura de um Addon"
MyAddon/
├── addon.yaml
├── scripts/
├── models/
├── textures/
├── sounds/
└── lang/
```

<Alert severity="warning" title="Isolamento dos Addons">

Um Addon defeituoso não pode impedir o TransitCore de arrancar. O framework deteta automaticamente o erro, desativa apenas o Addon concernente e prossegue o carregamento de todos os outros.

</Alert>

## A documentação

A documentação está organizada em várias secções.

| Secção | Descrição |
|---------|-------------|
| Começar | Instalar o TransitCore e criar o seu primeiro Addon. |
| LuaTC | Descobrir a linguagem de script oficial do framework. |
| Guias | Tutoriais detalhados que cobrem os principais sistemas do TransitCore. |
| Referência da API | Documentação completa dos serviços, classes, métodos e eventos. |
| Exemplos | Projetos de exemplo que ilustram as boas práticas e as funcionalidades do framework. |

## Open Source

O TransitCore é um projeto open source desenvolvido pela **Fire Sparks Studio**.

O código fonte, a documentação e o sistema de seguimento de problemas estão acessíveis publicamente de forma a permitir à comunidade propor melhorias, reportar anomalias e contribuir para o desenvolvimento do framework.

## Próximo passo

Se está a descobrir o TransitCore, continue com **Instalação** de forma a preparar o seu ambiente de desenvolvimento e criar o seu primeiro Addon.