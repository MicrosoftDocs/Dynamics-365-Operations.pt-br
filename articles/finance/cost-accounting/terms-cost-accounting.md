---
title: Terminologia de contabilidade de custos
description: Este tópico define os principais termos usados na contabilização de custos.
author: ShylaThompson
manager: AnnBe
ms.date: 08/31/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: CAMCostAccountingLedger
audience: Application User
ms.reviewer: roschlom
ms.search.scope: Core, Operations
ms.custom: 223114
ms.assetid: 1c798592-77d0-4a8f-beaa-9159c75957da
ms.search.region: global
ms.search.industry: Manufacturing
ms.author: roschlom
ms.search.validFrom: 2016-11-30
ms.dyn365.ops.version: Version 1611
ms.openlocfilehash: 948beb7baa19c69530dca52b5d4c119b69f8f011
ms.sourcegitcommit: 708ca25687a4e48271cdcd6d2d22d99fb94cf140
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/10/2020
ms.locfileid: "3977518"
---
# <a name="cost-accounting-terminology"></a>Terminologia de contabilidade de custos

[!include [banner](../includes/banner.md)]

Este tópico define os principais termos usados na contabilização de custos.

**Base de alocação**

A base de alocação é usada para medir e quantificar atividades, como as horas de máquina usadas, os quilowatts-hora consumidos ou a área ocupada. É usada como base para alocar custos para um ou mais objetos de custo.

**Contabilização de custos**

A contabilização de custos permite que você colete dados de várias fontes, como contabilidade, razões auxiliares, orçamentos e informações estatísticas. Com isso, é possível analisar, resumir e avaliar dados de custo a fim de que o gerenciamento possa tomar as melhores decisões possíveis em termos de atualização de preços, orçamentos, controle de custos etc. Os dados de origem usados na análise de custos são tratados de forma independente na contabilização de custos. Portanto, atualizações na contabilização de custos não afetam os dados de origem. No entanto, ao coletar dados de custo de várias origens, e especialmente ao importar as contas principais a partir da contabilidade como elementos de custo, haverá redundância de dados, já que os mesmos dados existem tanto na contabilidade quanto na contabilização de custos. Essa redundância é necessária porque você usa gerenciamento financeiro para relatórios externos e contabilidade de custos para relatórios internos.

**Razão de contabilização de custos**

Definido pelo calendário, moeda e dimensão de elemento de custo, controla processos e políticas para medir custos. 

**Entrada de custo**

As entradas de custo são o resultado de uma transferência por meio de conectores de dados nas entradas de contabilidade, alocações de custo e entradas de custo lançadas nos diários de custo.

**Objeto de custo**

Qualquer tipo de objeto que é selecionado para o controle de custo. Os custos ou as receitas são lançados diretamente ou alocados para os objetos de custo. Alguns objetos de custos comuns são:

-  Produtos
-  Projetos
-  Departamentos
-  Centros de custos

O gerenciamento usa objetos de custo para quantificar custos e realizar análises de lucratividade.

**Elemento de custo**

Usado como uma função para rastrear e categorizar custos. Há dois tipos de elementos de custo: custos primários e custos secundários.

Elementos de custo primários representam o fluxo de custo de conta financeira a contabilização de custo. A estrutura geralmente corresponde à estrutura da conta de lucros e perdas na contabilidade, na qual um elemento de custo pode corresponder a uma conta principal. Nem todas as contas principais precisam ser representadas como elementos de custo, dependendo das necessidades comerciais. 

Os elementos de custo secundário representam o fluxo de custos interno, pois esses custos somente são usados na Contabilização de custos. São usados em regras de acúmulo de custos para agregar custos em classificações significantes usadas por cálculo de custos indiretos. 

**Classificação de custo**

A classificação de custos agrupa custos de acordo com suas características compartilhadas. Por exemplo, custos podem ser agrupados por elementos, rastreabilidade e comportamento.

-   **Por elementos**: materiais, trabalho e despesas.
-   **Por rastreabilidade**: custos diretos e custos indiretos. Os custos diretos são atribuídos diretamente a objetos de custo. Os custos indiretos não são diretamente rastreáveis para objetos de custo. Os custos indiretos são alocados para objetos de custo.
-   **Por comportamento**: fixo, variável e semivariável.

**Comportamento de custo**

O comportamento de custo classifica custos de acordo com seu comportamento em relação a alterações nas principais atividades comerciais. Para controlar custos de forma eficaz, o gerenciamento deve entender o comportamento do custo. Há três tipos de padrão de comportamento de custo: fixo, variável e semivariável.

- **Custo fixo** - Um custo fixo é um custo que não varia no curto prazo, independentemente das alterações no nível de atividade. Por exemplo, um custo fixo pode ser uma despesa operacional básica de uma empresa, como aluguel, que não será afetada caso o nível de atividade aumente ou diminua.

- **Custo variável** -Um custo variável muda de acordo com as alterações no nível de atividade. Por exemplo, um custo direto específico de materiais está associado a cada produto vendido. Quanto mais produtos forem vendidos, mais custos diretos de materiais haverá.

- **Custos semivariáveis** - Custos semivariáveis são custos parcialmente fixos e parcialmente variáveis. Por exemplo, uma taxa de acesso à Internet inclui uma taxa de acesso mensal padrão e uma taxa de uso de banda larga. A taxa de acesso mensal padrão é um custo fixo, enquanto a taxa de uso de banda larga é um custo variável.

**Unidade de controle de custo**

A unidade de controle de custos representa a estrutura de custos. A estrutura determina como os fluxos de custo em uma ordem hierárquica entre dimensões de objeto de custo e seus respectivos objetos de custo. 

**Distribuição de custos**

É usada para redistribuir custo de um objeto de custo a um ou mais outros objetos de custo, aplicando uma base de alocação relevante. A distribuição de custos e a alocação de custo são diferentes na distribuição de custos, sempre que ocorrer em nível de elemento de custo principal do custo original e no processamento recíproco.

**Alocação de custos**

É usado para alocar o saldo de um objeto de custo a outros objetos de custo pela aplicação de uma base de alocação. O Finance oferece suporte ao método de alocação recíproco. No método de alocação recíproco, os serviços mútuos que os objetos de custo auxiliar trocam são totalmente reconhecidos. O sistema determina automaticamente a ordem para executar as alocações e aplicá-la. O saldo de um objeto de custo é alocado por uma base de alocação única. As alocações entre as dimensões de objeto de custo e os respectivos membros são suportadas. A ordem de alocação é controlada pela unidade de controle de custo.

**Política de alocação de custos**

Uma política de alocação de custos define a quantidade que deve ser alocada. Regras de alocação incluem regras de origem de alocação, que determinam os custos que são alocados, e regras de destino de alocação, que determinam onde os custos são alocados. Por exemplo, todos os custos com serviços de instalações são uma origem de alocação que pode ser alocada para vários departamentos em uma organização (ou seja, para destinos de alocação).

**Acúmulo de custo**

A finalidade das regras de acúmulo de custo é agregar custos em classificações significantes. O nível de agregação é definido pelo usuário e envolve a atribuição de um elemento de custo secundário. Se o acúmulo de custo não for usado, cada elemento de um custo é alocado de um objeto de custo para outro.

**Política de taxa de custo**

A taxa de custo é usada para calcular preços por objeto de custo. Para entender os elementos do preço, você define políticas de taxa de custo. Há dois tipos de taxa de custo: taxa de custo histórica e taxa de custo planejada. Uma taxa de custo histórica é uma taxa calculada que é usada como multiplicador para a base de alocação de um objeto de custo. A taxa de custo é calculada com base nas alocações de custo no período anterior. Uma taxa planejada é uma taxa definida pelo usuário.

**Hierarquia de dimensões**

Há duas hierarquias dimensionais: hierarquia de categorização e hierarquia de classificação. O tipo de hierarquia da categorização de dimensão é usado para fins de relatório. Ele oferece suporte somente às dimensões de elemento de custo. O tipo de hierarquia de classificação de dimensão é usado para definir políticas e para fins de relatório. Ele oferece suporte a todas as dimensões, como objetos de custos, elementos de custo, dimensões estatísticas. 

**Conector de dados**

A contabilização de custo suporta integração de dados de sistemas de origem por meio de um conjunto de conectores de dados. Os seguintes conectores de dados estão disponíveis:

-  Transações importadas (anteriormente configuradas)
-  Dynamics 365 Finance (pré-configurado)
-  Dynamics AX (configuração necessária)

**Observação:** As transações importadas do conector de dados são baseadas em entidades de dados.

**Provedor de dados**

A maioria de sistemas de origem pode fornecer os dados que correspondam uma ou mais origens na Contabilização de custo. Para os dados de sistemas de origem com a origem de dados na contabilização de custo, um provedor de dados precisa ser configurado. A tabela a seguir lista a disponibilidade de provedores de dados por connector e origem de dados.

|  **Fontes de dados** |  **Conector de dados das transações importadas** | **Conector de dados do Dynamics 365 Finance**  | **Conector de dados do Dynamics AX**  |
|---|---|---|---|
| Membros de dimensão do elemento de custo  |  Sim | Sim  | Sim  |
|  Membros de dimensão de objeto de custo |  Sim | Sim  | Sim  |
|  Membros de dimensão estatística | Sim  | Não  | Não  |
|  Contabilidade | Sim  | Sim  | Sim  |
|  Entradas de orçamento  | Sim  | Sim  | Sim  |
|  Medidas estatísticas | Sim  | Sim  | Sim  |

**Fórmula**

As bases de alocação da fórmula permitem definir fórmulas avançados para obter a base de alocação correta. Você pode criar manualmente bases de alocação da fórmula. Você pode usar os seguintes operadores para definir sua fórmula.

|  **Símbolos** | **Texto**  |
|---|---|
|  ( ) | Parênteses  |
|  < |  Menor que |
|  > |  Maior que |
|  + |  Adição |
|  – |  Subtração |
| *  | Multiplicação  |

As instruções tradicionais IF não são suportadas. Porém, você pode criar instruções e validar se elas são verdadeiras.

|  **Validação de extrato** | **Resultado**  |
|---|---|
|  a > b| Verdadeiro  |
|  a > b |  Falso |

**Custos gerais indiretos**

Custos gerais referem-se às despesas contínuas de operação de uma empresa. São os custos que não podem ser vinculados diretamente a atividades comerciais específicas. Eis alguns exemplos de custos gerais:

-   Taxas de contabilidade
-   Depreciações
-   Seguro
-   Interesse
-   Taxas legais
-   Impostos
-   Custos com serviços de utilidade pública

**Taxa de custos indiretos**

As taxas são definidas por objeto de custo e elemento de custo. Há dois tipos de taxa: período fiscal e especificado pelo usuário. As taxas do período fiscal são calculadas por cálculo de custos indiretos. Uma taxa específica do usuário é definida pelo usuário e pode ser usada para alocar custo entre objetos de custo em uma taxa predeterminada no cálculo de custos indiretos.

**Publicada**

Se você definir este campo como Sim, um usuário que é atribuído a uma das seguintes funções visualizará o relatório no espaço de trabalho Controle de custos:

-  Gerenciador de contabilização de custos
-  Contador de custos
-  Contador de custos
-  Controlador do objeto de custo

Se você definir este campo como Não, somente os usuários que são atribuídos a uma das seguintes funções visualizarão o relatório no espaço de trabalho Controle de custos:

-  Gerenciador de contabilização de custos
-  Contador de custos
-  Contador de custos

**Dimensão estatística**

Uma dimensão estatística e seus membros são usados ​​para registrar e controlar entradas não monetárias na contabilidade de custos. Os membros da dimensão estatística podem ser utilizados para duas finalidades:

-  Como uma base de alocação nas políticas, como distribuição de custos ou alocação de custos.
-  Para relatar o consumo não monetário.

Uma dimensão estatística é a expressão de uma contagem ou soma de uma atividade que pode ser usada como a base para alocações ou cálculos de taxa. É criada manualmente ou importada de sistemas de origem. Exemplos de dimensões estatísticas incluem o número de funcionários, a contagem de softwares licenciados em cada dispositivo, o consumo de energia de cada máquina ou os metros quadrados de um centro de custo.

**Instrução**

Demonstrativos são exibições para os gerentes responsáveis pelo controle de custos. Demonstrativos são definidos por um controlador de custos e fornecem uma visão geral rápida dos custos reais e orçados e de desvios. O gerente poderá fazer uma busca detalhada, se necessário. Para ajudar a garantir que gerentes vejam apenas os dados pelos quais são responsáveis, os dados que aparecem nos demonstrativos estão sujeitos a regras de acesso.

**Versão**

As versões são usadas para simular, exibir e comparar vários resultados. Por padrão, todos os custos reais são exibidos em uma versão base que é conhecida como *real*. No tocante a orçamentos e cálculos, é possível trabalhar com quantas versões forem necessárias. Por exemplo, você pode importar dados orçamentários para uma versão original e depois revisar o orçamento em uma versão revisada. Para cálculos, você pode criar várias versões. Nessas versões, é possível criar os cálculos usando diferentes regras de cálculo que serão aplicadas na alocação de custos.


