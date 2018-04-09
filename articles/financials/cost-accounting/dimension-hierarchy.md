---
title: "Hierarquia de dimensões"
description: "Este tópico fornece informações sobre hierarquias de dimensões. As hierarquias de dimensões são usadas para definir a estrutura de relatórios, as políticas de custo e a configuração de segurança na Contabilização de Custos."
author: AndersGirke
manager: AnnBe
ms.date: 06/16/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: CAMDimensionHierarchy,
audience: Application User
ms.reviewer: yuyus
ms.search.scope: Core, Operations
ms.custom: 
ms.assetid: 
ms.search.region: global
ms.search.industry: Manufacturing
ms.author: yuyus
ms.search.validFrom: 2016-11-30
ms.dyn365.ops.version: Version 1611
ms.translationtype: HT
ms.sourcegitcommit: a0739304723d19b910388893d08e8c36a1f49d13
ms.openlocfilehash: 40a4a1d7549876b72186f30a9c0089f0d27cf3b6
ms.contentlocale: pt-br
ms.lasthandoff: 03/26/2018

---

# <a name="dimension-hierarchy"></a>Hierarquia de dimensões

[!include[banner](../includes/banner.md)]

Este tópico fornece informações sobre hierarquias de dimensões. As hierarquias de dimensões são usadas para definir a estrutura de relatórios, as políticas de custo e a configuração de segurança na Contabilização de Custos.  

## <a name="overview"></a>Visão Geral

As hierarquias de dimensões são usadas em vários locais na Contabilização de Custos. Uma hierarquia de dimensões permite que você defina as seguintes informações:

-  A estrutura de relatórios que atende aos requisitos da sua organização
-  Políticas de custo
-  A configuração de segurança

Veja a seguir um exemplo de uma hierarquia de dimensões.

![Exemplo de uma hierarquia de dimensões.](./media/dimension-hierarchy.png)

Uma hierarquia de dimensões pode ser criada para os seguintes tipos de dimensões:

-  Dimensões do elemento de custo
-  Dimensões de objeto de custo
-  Dimensões estatísticas

> [!NOTE]
> - Você pode criar várias hierarquias de dimensões para a mesma dimensão caso sejam necessárias perspectivas diferentes.
> - Uma hierarquia de dimensões pode ser associada a uma única dimensão.
> - Uma hierarquia de dimensões pode ter níveis ilimitados em sua estrutura. Todos os níveis serão disponibilizados no espaço de trabalho **Controle de custos**. Ao usar o Microsoft Excel ou Microsoft Power BI para fins de relatório, somente os primeiros 15 níveis da hierarquia de dimensões são exportados. Essa limitação existe porque ambos, Excel e Power BI, exigem um esquema fixo.
> - Uma hierarquia de dimensões não é efetiva com relação à data. Portanto, qualquer alteração a uma hierarquia de dimensões é salva imediatamente no registro, e você não pode comparar as datas anterior e posterior.

## <a name="dimension-hierarchy-type"></a>Tipo de hierarquia de dimensões

Ao criar uma nova hierarquia de dimensões, você deve selecionar o tipo de hierarquia. Vá para **Contabilização de custos** > **Dimensões** > **Hierarquias de dimensões**. Clique em **Novo** e selecione um tipo de hierarquia de dimensões. Você pode selecionar **Hierarquia de categorização de dimensões** ou **Hierarquia de classificação de dimensões**.

### <a name="dimension-categorization-hierarchy"></a>Hierarquia de categorização de dimensões

O tipo de **Hierarquia de categorização de dimensões** é usado para fins de relatório. Ele oferece suporte somente às dimensões de elemento de custo. Ao selecionar esse tipo, as seguintes regras se aplicam:

-  Um membro da dimensão pode ser associado mais de uma vez na estrutura de hierarquia.
-  Você pode colocar um membro da dimensão de elemento de custo em nós diferentes, atribuindo um comportamento de custo ao nó folha.

### <a name="dimension-classification-hierarchy"></a>Hierarquia de classificação de dimensões

O tipo de **Hierarquia de classificação de dimensões** é usado para definir regras e para fins de relatório. Ele oferece suporte a todas as dimensões, como objetos de custos, elementos de custo, dimensões estatísticas. Ao selecionar esse tipo, um membro da dimensão pode ser associado somente uma vez na estrutura de hierarquia.

## <a name="create-and-maintain-a-dimension-hierarchy"></a>Criar e manter uma hierarquia de dimensões

Uma hierarquia de dimensões é criada em uma estrutura de árvore com relacionamentos de nó e de nó folha.

-  Um nó pode ter 1:_n_ subnós.
-  Um nó não pode ter ambos, subnós e nós folha, atribuídos a ele.
-  Um nó folha pode ser atribuído apenas no nível mais baixo da hierarquia.

### <a name="example"></a>Exemplo

Uma empresa pequena tem a seguinte estrutura de organização, em que os recursos Humanos e Financeiros são departamentos em Administração, e Montagem e Empacotamento são departamentos em Produção.

![Exemplo de uma estrutura organizacional](./media/dimension-hierarchy-org.png)

Uma dimensão de objeto de custo representa todos os centros de custo na organização.

- Dimensão de objeto de custo
    - Centros de custos

A dimensão de objeto de custo que representa todos os centros de custo pode ser configurada como mostrado aqui.

| Centros de custos | descrição |
|--------------|-------------|
| CC001        | RH          |
| CC002        | Finanças     |
| CC003        | Imposto         |
| CC007        | AR/AP       |
| CC005        | Montagem    |
| CC006        | Embalagem   |

Uma dimensão do elemento de custo representa todos os elementos de custo na organização.

- Dimensão do elemento de custo
    - Elementos de custo

A dimensão do elemento de custo que representa todos os elementos de custo pode ser configurada como mostrado aqui.

| Elementos de custo | descrição |
|---------------|-------------|
| 10001         | eletricidade |
| 10010         | Limpeza    |
| 10011         | Aquecimento     |
| 40001         | COGS        |

Uma hierarquia de dimensões que atende aos requisitos de relatórios da organização pode ser configurada como mostrado aqui.

**Detalhes de hierarquia de dimensão**

| Nome de hierarquia de dimensão | Dimensão    | Nome do tipo de hierarquia de dimensões      | Acessar hierarquia de lista |
|--------------------------|--------------|------------------------------------|-----------------------|
| Organização             | Centros de custos | Hierarquia de classificação de dimensões | Não                    |

A hierarquia de dimensões para relatórios pode ser configurada como mostrado aqui.

|                   | Intervalos de membros de dimensão   |                         |
|-------------------|---------------------------|-------------------------|
| **Nós**         | **Membro da dimensão de origem** | **Membro da dimensão de destino** |
| Organização      |                           |                         |
| &nbsp;&nbsp;Administrador         |                           |                         |
|&nbsp;&nbsp;&nbsp;&nbsp;Finanças   | CC002                     | CC003                   |
|                   | CC007                     | CC007                   |
| &nbsp;&nbsp;&nbsp;&nbsp;RH        | CC001                     | CC001                   |
| &nbsp;&nbsp;Produção    |                           |                         |
| &nbsp;&nbsp;&nbsp;&nbsp;Embalagem | CC005                     | CC005                   |
| &nbsp;&nbsp;&nbsp;&nbsp;Montagem  | CC006                     | CC006                   |

Uma hierarquia de dimensões que atende ao requisito de relatório pode ser configurada como mostrado aqui.

**Detalhes de hierarquia de dimensão**

| Nome de hierarquia de dimensão | Dimensão     | Nome do tipo de hierarquia de dimensões      |
|--------------------------|---------------|------------------------------------|
| Comportamento de custo            | Elementos de custo | Hierarquia de classificação de dimensões |

A hierarquia de dimensões para a política pode ser configurada como mostrado aqui.

|                   | Intervalos de membros de dimensão   |                         |
|-------------------|---------------------------|-------------------------|
| **Nós**         | **Membro da dimensão de origem** | **Membro da dimensão de destino** |
| Comportamento de custo     |                           |                         |
| &nbsp;&nbsp;Custo fixo    | 10001                     | 10011                   |
|&nbsp;&nbsp;Custo variável | 40001                     | 40010                   |

> [!NOTE]
> Em **Intervalos de membros de dimensão**, um nó pode conter 1:_n_ intervalos de membros de dimensão. Você pode inserir as IDs de membros de dimensão que ainda não existem como membros de dimensão. Esta abordagem torna a hierarquia resiliente para o futuro.  

### <a name="copy-a-hierarchy"></a>Copiar uma hierarquia

Você pode copiar uma hierarquia de dimensões atual como ponto de partida para uma nova hierarquia de dimensões. Esta abordagem pode ser útil se você deseja comparar a hierarquia de dimensões anterior com a nova hierarquia de dimensões.

### <a name="rearrange-nodes-in-a-hierarchy"></a>Reorganizar os nós em uma hierarquia

Você pode mover um nó para cima e para baixo dentro do seu nível atual na estrutura. Desta forma, você pode reorganizar a ordem dos nós para relatórios no espaço de trabalho **Controle de custos**.

Você move um nó para uma nova localização na hierarquia selecionando o nó de destino. Existem duas maneiras de mover um nó:

- **Mover para baixo** – Mova o nó selecionado da sua posição atual na hierarquia, e insira-o **abaixo** do nó de destino selecionado.
- **Mover após** – Mova o nó selecionado da sua posição atual na hierarquia, e insira-o **após** o nó de destino selecionado, no seu nível hierárquico.

> [!NOTE] 
> A ordem dos nós não é mantida quando você exporta dados para o Excel ou o Power BI, pois essas ferramentas usam uma ordem de classificação alfanumérica por padrão. Você deve reorganizar manualmente a ordem.

## <a name="define-dimension-hierarchies-for-reporting"></a>Definir hierarquias de dimensões para relatórios

As hierarquias de dimensões são importantes para relatórios. Eles permitem definir a estrutura específica que se encaixa na organização individual. As agregações que são feitas no nível de nó da hierarquia de dimensões permitem que as partes interessadas em qualquer nível da organização confiram dados em qualquer nível.

As hierarquias de dimensões estão disponíveis nas seguintes ferramentas de relatório. Essa abordagem ajuda a garantir consistência na estrutura de relatórios.

- Espaço de trabalho de **Controle de custos** (Cliente):

    - Controlado por configuração.

- Espaço de trabalho de **Controle de custos** (Aplicativo móvel):

    - Controlado por configuração.

- Excel

    - Fornece a opção para selecionar hierarquias de dimensões específicas por definição de exportação:

        - Uma hierarquia da dimensão de elemento de custo (obrigatória)
        - Uma hierarquia da dimensão de objeto de custo (opcional)
        - Uma hierarquia da dimensão estatística (opcional)

- Power BI:

    - Todas as hierarquias de dimensões estão disponíveis.
    
Se você criar relatórios usando o Excel ou o Power BI, apenas os 15 primeiros níveis das hierarquias de dimensões serão exportados. Essa limitação existe porque é necessário um esquema fixo no Excel e no Power BI. Se uma hierarquia tiver mais de 15 níveis, os níveis adicionais não serão exportados. A tabela normalizada contém um registro para cada membro de dimensão na hierarquia. Portanto, ocorre uma agregação automatizada. Esse comportamento ajuda a garantir que os saldos em qualquer um dos 15 níveis disponíveis na hierarquia ainda estejam corretos.

O exemplo a seguir mostra qual a aparência que uma hierarquia de dimensões pode ter na estrutura de relatórios.

| Hierarquia da dimensão de objeto de custo – Nível 1 | Hierarquia da dimensão de objeto de custo – Nível 2 | Hierarquia da dimensão de objeto de custo – Nível 3 | Hierarquia da dimensão de objeto de custo – Nível 4 | Hierarquia da dimensão de objeto de custo – Nível 15 |
|-------------------------------------------|-------------------------------------------|-------------------------------------------|-------------------------------------------|--------------------------------------------|
| Organização                              | Administrador                                     | Finanças                                   | CC002                                     |                                            |
| Organização                              | Administrador                                     | Finanças                                   | CC003                                     |                                            |
| Organização                              | Administrador                                     | Finanças                                   | CC007                                     |                                            |
| Organização                              | Administrador                                     | RH                                        | CC001                                     |                                            |
| Organização                              | Produção                                | Embalagem                                 | CC005                                     |                                            |
| Organização                              | Produção                                | Montagem                                  | CC006                                     |                                            |

### <a name="update-the-dimension-hierarchies-that-are-used-for-reporting"></a>Atualizar as hierarquias de dimensões que são usadas para relatórios 

Com o tempo, as hierarquias de dimensões usadas nas ferramentas de relatório mencionadas anteriormente terão que ser atualizadas. É possível atualizar as hierarquias de dimensões atualizando o cliente.

- Espaço de trabalho de **Controle de custos** (Cliente)
- Espaço de trabalho de **Controle de custos** (Aplicativo móvel)

As atualizações para as hierarquias de dimensões são coletadas a cada 24 horas por um trabalho de pré-armazenamento em cache. Após a atualização dos dados exportados, as hierarquias de dimensões atualizadas estão disponíveis nas seguintes ferramentas:

- Excel
- Power BI

> [!NOTE] 
> Para ativar manualmente uma atualização do cache de hierarquia de dimensões, você pode criar uma nova exportação para o Excel referente à(s) hierarquia(s) de dimensões que devem ser atualizadas.

## <a name="define-dimension-hierarchies-for-cost-policies"></a>Definir hierarquias de dimensões para políticas de custo

A contabilização de custos consiste em várias políticas nas quais regras detalhadas são definidas. Você deve definir uma ou mais hierarquias de dimensões para as seguintes políticas:

- Comportamento de custo
- Distribuição de custos
- Alocação de custos
- Acúmulo de custo

As hierarquias de dimensões facilitam a criação de regras. Para evitar ter que criar regras para cada membro da dimensão, você pode aproveitar as agregações de membros da dimensão fornecidas pelos níveis de hierarquia da dimensão. Caso tenha regras sobrepostas, você deve definir regras específicas que o sistema irá considerar ao fazer o cálculo de custos indiretos.

### <a name="example-define-a-cost-behavior-policy"></a>Exemplo: Definir uma política de comportamento de custo

Uma nova política de comportamento de custo é criada, e as hierarquias de dimensões apropriadas são atribuídas à política, como mostrado aqui.

**Política de comportamento de custo**

| Nome da política   | Hierarquia da dimensão de elemento de custo | Hierarquia da dimensão de objeto de custo | Moeda contábil |
|---------------|----------------------------------|---------------------------------|---------------------|
| Comportamento de custo | Comportamento de custo                    | Organização                    | USD                 |

**Regras**

| Nó de hierarquia da dimensão de elemento de custo | Nó de hierarquia da dimensão de objeto de custo | Percentual fixo | Valor fixo | Válido a partir de | Válida até |
|---------------------------------------|--------------------------------------|------------------|--------------|------------|----------|
| Custo fixo                            | Organização                         | 100,00           | 0,00         | 1/1/2017   | Nunca    |
| 10001                                 | Organização                         | 0,00             | 150.00       | 1/1/2017   | Nunca    |
| 10001 (\*)                             | Finanças                              |                  | 50,00        | 1/1/2017   | Nunca    |
| Comportamento de custo ou custo variável (\*\*)   | Organização                         | 0,00             | 0,00         | 1/1/2017   | Nunca    |

\* O nó de custo variável não é necessário. Se um custo não for classificado como custo fixo, ele deve ser um custo variável.

\*\* Uma regra detalhada é criada para a combinação do membro do elemento de custo 10001 e todos os membros do objeto de custo que são agregados ao nível hierárquico Financeiro (CC002, CC003, CC007).

As regras anteriores mostram a flexibilidade que as hierarquias de dimensões fornecem. Ao definir regras de alto nível, você pode ajudar a minimizar a manutenção. Você pode então definir regras detalhadas para adequar a um objetivo comercial específico.

Se as hierarquias de dimensões usadas nas regras estão atualizadas, o sistema disponibiliza as atualizações automaticamente.

Se um nível de granularidade nas regras não for mais necessário, a regra pode expirar.

Por exemplo, uma regra de comportamento de custo específica para o nó da hierarquia de dimensão de objeto de custo financeiro não é mais necessária. Nesse caso, clique em **Regra de expiração** para expirar a regra.

| Nó de hierarquia da dimensão de elemento de custo | Nó de hierarquia da dimensão de objeto de custo | Percentual fixo | Valor fixo | Válido a partir de | Válida até  |
|---------------------------------------|--------------------------------------|------------------|--------------|------------|-----------|
| Custo fixo                            | Organização                         | 100,00           | 0,00         | 1/1/2017   | Nunca     |
| 10001                                 | Organização                         | 0,00             | 150,00       | 1/1/2017   | Nunca     |
| 10001                                 | Finanças                              |                  | 50,00        | 1/1/2017   | 20/1/2017 |
| Comportamento de custo ou custo variável        | Organização                         | 0,00             | 0,00         | 1/1/2017   | Nunca     |

Qualquer cálculo de custos indiretos que seja executado após 20 de janeiro de 2017, já não considera essa regra.

> [!NOTE] 
> Os campos **Válido a partir de** e **Valido até** possuem data e hora de efetivação. Você pode expirar a regra e executar um novo cálculo de custos indiretos no mesmo dia.

## <a name="define-dimension-hierarchies-for-security-setup"></a>Definir hierarquias de dimensões para a configuração de segurança

Os dados de contabilização de custos devem ser disponibilizados a todos os gerentes responsáveis por uma unidade de relatório. Na terminologia de contabilização de custos, uma unidade de relatório é representada como um objeto de custo ou um conjunto de objetos de custo.

Possivelmente, todos os gerentes poderão acessar dados comerciais altamente confidenciais, como receitas e margens. Portanto, é importante configurar a segurança, de modo que os gerentes vejam somente os dados relevantes para eles. Para ajudar a controlar a segurança de dados, você define hierarquias de dimensões.

- O uso de hierarquias de dimensões se aplica somente quando o valor de dimensão selecionado na referência da hierarquia de dimensões é uma dimensão de objeto de custo.
- Apenas uma hierarquia de dimensões pode ser habilitada por dimensão de objeto de custo na hierarquia da lista de acesso.

**Detalhes de hierarquias de dimensão**

| Nome da hierarquia de dimensões | Dimensão    | Nome do tipo de hierarquia de dimensões      | Acessar hierarquia de lista |
|--------------------------|--------------|------------------------------------|-----------------------|
| Organização             | Centros de custos | Hierarquia de classificação de dimensões | **Sim**               |

Uma nova Guia Rápida **Usuários** está disponível no designer de hierarquia. Aqui, você pode inserir uma ou mais IDs de usuário em cada nó na hierarquia.

|                 | Usuários            | Intervalos de membros de dimensão   |                         |
|-----------------|------------------|---------------------------|-------------------------|
| **Nós**       | **ID do Usuário**      | **Membro da dimensão de origem** | **Membro da dimensão de destino** |
| Organização    | Benjamin, Claire |                           |                         |
| &nbsp;&nbsp;Administrador         | Abril            |                           |                         |
| &nbsp;&nbsp;&nbsp;&nbsp;Finanças   | Alicia           | CC002                     | CC003                   |
|                 |                  | CC007                     | CC007                   |
| &nbsp;&nbsp;&nbsp;&nbsp;RH        | Arnie            | CC001                     | CC001                   |
| &nbsp;&nbsp;Produção    | David            |                           |                         |
| &nbsp;&nbsp;&nbsp;&nbsp;Embalagem | Ellen            | CC005                     | CC005                   |
| &nbsp;&nbsp;&nbsp;&nbsp;Montagem  | Chris            | CC006                     | CC006                   |

> [!NOTE] 
> Os contadores devem ser atribuídos ao nível de hierarquia superior para que possam consultar todas as entradas na contabilização de custo.

Para habilitar a hierarquia da lista de acesso e as configurações de segurança, vá para **Contabilização de custos** > **Configuração** > **Parâmetros** > **Geral**. Selecione o parâmetro **Habilitar acesso de visualização para membros de dimensão de objeto de custo**.

As configurações da hierarquia da lista de acesso são usadas para controlar os dados que são mostrados nas seguintes áreas:

- Espaço de trabalho de **Controle de custos** (Cliente):

    - Dados em formulários que são usados para detalhar cenários

- Espaço de trabalho de **Controle de custos** (Aplicativo móvel):

    - Saldos em cartões

- Power BI:

    - Dados mostrados nas visualizações do Power BI
    - Visualizações de Dados do Power BI inseridos no cliente Microsoft Dynamics 365 for Finance and Operations

> [!NOTE] 
> - Antes que a hierarquia da lista de acesso possa afetar os dados no Power BI, a hierarquia da lista de acesso e a segurança em nível de linha no Power BI devem ser emparelhadas. Para obter mais informações, consulte [Configurar segurança para o pacote de conteúdo de contabilização de custo](../../dev-itpro/analytics/setup-security-cost-accounting-content-pack.md).
> - A hierarquia da lista de acesso não ajuda a garantir a exportação de dados para o Excel. Portanto, essa ferramenta de relatório deve ser usada somente por contadores e gerentes que devem ter acesso total aos dados.

