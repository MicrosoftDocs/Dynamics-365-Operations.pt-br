---
title: Terminologia de contabilidade de custos
description: "Este tópico define os principais termos usados na contabilização de custos."
author: YuyuScheller
manager: AnnBe
ms.date: 04/04/2017
ms.topic: article
ms.prod: 
ms.service: Dynamics365Operations
ms.technology: 
ms.search.form: CAMCostControlWorkspace, CAMCostControlWorkspaceConfiguration
audience: Application User
ms.search.scope: Operations, Core
ms.custom: 223114
ms.assetid: 1c798592-77d0-4a8f-beaa-9159c75957da
ms.search.region: global
ms.search.industry: Manufacturing
ms.author: yuyus
ms.search.validFrom: 2016-11-30
ms.dyn365.ops.version: Version 1611
ms.translationtype: Human Translation
ms.sourcegitcommit: fd3392eba3a394bd4b92112093c1f1f9b894426d
ms.openlocfilehash: 76c5d4b3a118747246eeb7ca0db69532af04bf9c
ms.contentlocale: pt-br
ms.lasthandoff: 04/25/2017


---

# <a name="cost-accounting-terminology"></a>Terminologia de contabilidade de custos

[!include[banner](../includes/banner.md)]


Este tópico define os principais termos usados na contabilização de custos.

**Contabilidade de custos**

A contabilização de custos permite que você colete dados de várias fontes, como contabilidade, razões auxiliares, orçamentos e informações estatísticas. Com isso, é possível analisar, resumir e avaliar dados de custo a fim de que o gerenciamento possa tomar as melhores decisões possíveis em termos de atualização de preços, orçamentos, controle de custos etc. Os dados de origem usados na análise de custos são tratados de forma independente na contabilização de custos. Portanto, atualizações na contabilização de custos não afetam os dados de origem. No entanto, ao coletar dados de custo de várias origens, e especialmente ao importar as contas principais a partir da contabilidade no Microsoft Dynamics 365 for Operation como elementos de custo, haverá redundância de dados, já que os mesmos dados existem tanto na contabilidade quanto na contabilização de custos. Essa redundância é necessária porque você usa gerenciamento financeiro para relatórios externos e contabilidade de custos para relatórios internos.

**Razão de contabilidade de custos**

O razão de contabilização de custos é uma estrutura especializada que determina como processos, valores e quantidades são inseridos e apresentados em uma área específica na contabilidade de custos. O razão de contabilização de custos define processos e regras para medição de custos em objetos de custo. Ela controla transações de custo e gerencia documentos que registram as alterações de valores e quantidades que as transações de custo produzem.

**Entrada de custo**

As entradas de custo são o resultado de uma transferência por meio de conectores de dados nas entradas de contabilidade, alocações de custo e entradas de custo lançadas nos diários de custo.

**Objeto de custo**

Objetos de custo são qualquer tipo de objeto para os quais os custos são alocados. Estes são alguns dos objetos de custo típicos:

-   Produtos
-   Projetos
-   Recursos
-   Departamentos
-   Centros de custos
-   Regiões geográficas

O gerenciamento usa objetos de custo para quantificar custos e realizar análises de lucratividade.

**Elemento de custo**

Elementos de custo são usados como uma função para acompanhar e categorizar o local para o qual o fluxo de custo é direcionado. Há dois tipos de elementos de custo: custos primários e custos secundários. **Custos primários** Elementos de custo previsto primários representam o fluxo de custo de conta financeira a contabilização de custo previsto. A estrutura de elemento de custo corresponde à estrutura da conta de lucros e perdas na contabilidade, na qual um elemento de custo pode corresponder a uma conta principal. Nem todas as contas principais precisam ser representadas como elementos de custo, dependendo das necessidades comerciais. Eis alguns exemplos de elementos de custo primários:

-   Custos dos produtos vendidos (COGs)
-   Custos indiretos de material
-   Custo da equipe
-   Custos de energia

**Elemento de custo secundário** 

Os elementos de custo secundário representam o fluxo de custos interno, pois esses custos são criados e usados apenas na contabilização de custos. Elementos de custo secundários ajudam a garantir que a fonte de custos possa ser tratada. Esses elementos de custo são usados em alocações de custo e cálculos de despesas gerais. Eis alguns exemplos de elementos de custo secundários:

-   Custos da produção
-   Despesas gerais com produção, materiais e marketing

**Unidade de controle de custo**

Uma unidade de controle de custos representa a estrutura de custos. Ela deve estar associada a dimensões de objeto de custo em um razão de contabilização de custos.

**Versão**

As versões são usadas para simular, exibir e comparar vários resultados. Por padrão, todos os custos reais são exibidos em uma versão base que é conhecida como *real*. No tocante a orçamentos e cálculos, é possível trabalhar com quantas versões forem necessárias. Por exemplo, você pode importar dados orçamentários para uma versão original e depois revisar o orçamento em uma versão revisada. Para cálculos, você pode criar várias versões. Nessas versões, é possível criar os cálculos usando diferentes regras de cálculo que serão aplicadas na alocação de custos.

**Demonstrativo**

Demonstrativos são exibições para os gerentes responsáveis pelo controle de custos. Demonstrativos são definidos por um controlador de custos e fornecem uma visão geral rápida dos custos reais e orçados e até desvios e versões de cálculo. Para ajudar a garantir que gerentes vejam apenas os dados pelos quais são responsáveis, os dados que aparecem nos demonstrativos estão sujeitos a regras de acesso.

**Conector de dados**

Os dados podem ser importados na contabilização de custos de sistemas externos por meio de conectores de dados. Por exemplo, você pode importar estruturas de contabilidade, dimensões, entradas de contabilidade e entradas de orçamento. É possível usar conectores de dados pré-configurados ou conectores personalizados para importar dados e criar conexões de dados.

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

**Custos gerais indiretos**

Custos gerais referem-se às despesas contínuas de operação de uma empresa. São os custos que não podem ser vinculados diretamente a atividades comerciais específicas. Eis alguns exemplos de custos gerais:

-   Taxas de contabilidade
-   Depreciações
-   Seguro
-   Interesse
-   Taxas legais
-   Impostos
-   Custos com serviços de utilidade pública

**Alocação de custos**

Alocação de custos é o processo de atribuir e alocar custos, com base nas causas principais dos custos comuns. Você aloca as quantidades de custo de um objeto de custo para um ou mais objetos de custo. Por exemplo, todos os custos com serviços de instalações são alocados para os vários departamentos que usam o prédio comercial comum.

**Política de alocação de custos**

Uma política de alocação de custos define a quantidade que deve ser alocada. Regras de alocação incluem regras de origem de alocação, que determinam os custos que são alocados, e regras de destino de alocação, que determinam onde os custos são alocados. Por exemplo, todos os custos com serviços de instalações são uma origem de alocação que pode ser alocada para vários departamentos em uma organização (ou seja, para destinos de alocação).

**Base de alocação**

A base de alocação é a base que pode ser usada para medir e quantificar atividades, como horas de máquina que são usadas, quilowatts-horas que são consumidos, horas de trabalho direto que são gastas ou metragem quadrada que é ocupada. É usada para alocar custos para um ou mais objetos de custo.

**Princípio de alocação**

Um dos princípios de alocação é alocar custo por taxa de custo. Você pode optar por alocar custos usando a taxa do período atual ou uma taxa histórica. A alocação que usa o método recíproco ajuda a garantir que a base de alocação seja determinada por uma série de equações simultâneas antes que a alocação seja realizada pelo uso da taxa de período atual.

**Acúmulo de custo**

A finalidade do acúmulo de custo é incluir todos os custos para um determinado objeto de custo. O nível de agregação é definido pelo usuário. Usando o acúmulo de custo, você pode agregar elementos dos custos que devem ser alocados de um objeto de custo para outro. Quando um acúmulo de custo não é usado, cada elemento dos custos é alocado de um objeto de custo para outro.

**Política de taxa de custo**

A taxa de custo é usada para calcular preços por objeto de custo. Para entender os elementos do preço, você define políticas de taxa de custo. Há dois tipos de taxa de custo: taxa de custo histórica e taxa de custo planejada. Uma taxa de custo histórica é uma taxa calculada que é usada como multiplicador para a base de alocação de um objeto de custo. A taxa de custo é calculada com base nas alocações de custo no período anterior. Uma taxa planejada é uma taxa definida pelo usuário.

**Hierarquia de dimensões**

Hierarquias dimensionais são usadas como estruturas de relatório quando você define regras de alocação, taxa de custo e acúmulo de custos, exibe demonstrativos ou dados no Microsoft Excel e define acesso aos dados agregados. Há duas hierarquias dimensionais: hierarquia de categorização e hierarquia de classificação. Uma hierarquia de categorização é definida de acordo com os elementos de custo, enquanto uma hierarquia de classificação é definida de acordo com os objetos de custo.

**Dimensão estatística**

Uma dimensão estatística é a expressão de uma contagem ou soma de um objeto que pode ser usada como a base para alocações ou cálculos de taxa de custo. É criada manualmente ou importada de sistemas de origem. Exemplos de dimensões estatísticas incluem o número de funcionários, a contagem de softwares licenciados em cada dispositivo, o consumo de energia de cada máquina ou os metros quadrados de um centro de custo.

**Entrada estatística**

Entradas estatísticas mantêm a soma ou valor de contagem registrados para uma determinada dimensão estatística. A soma ou o valor de contagem registrados também é chamado de magnitude.




