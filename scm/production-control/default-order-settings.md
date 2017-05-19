---
title: "Configurações de ordem padrão para dimensões e variantes de produto"
description: "As configurações de ordem padrão definem o local e o depósito de onde os itens serão originários ou armazenados, as quantidades mínima, máxima, múltiplas e padrão que serão usadas para a comercialização ou o gerenciamento de estoque, os prazos de entrega, o sinalizador de parada e o método de promessa de ordens. As configurações de ordem padrão são usadas durante a criação de ordens de compra, ordens de venda, ordens de transferência, diários de estoque e pelo planejamento mestre para a geração de ordens planejadas. As configurações de ordem padrão podem ser específicas por item, local, grade de produto ou dimensão de produto."
author: YuyuScheller
manager: AnnBe
ms.date: 04/04/2017
ms.topic: article
ms.prod: 
ms.service: Dynamics365Operations
ms.technology: 
ms.search.form: InventItemOrderSetup
audience: Application User
ms.search.scope: Operations, Core
ms.custom: 223084
ms.assetid: fbfbcd7b-dc75-44ab-bffc-8bad576804a4
ms.search.region: global
ms.search.industry: Manufacturing
ms.author: roxanad
ms.search.validFrom: 2016-11-30
ms.dyn365.ops.version: Version 1611
ms.translationtype: Human Translation
ms.sourcegitcommit: fd3392eba3a394bd4b92112093c1f1f9b894426d
ms.openlocfilehash: 26ad7fb0e9371b8e1d45d61f2348241c6aca16b9
ms.contentlocale: pt-br
ms.lasthandoff: 04/25/2017


---

# <a name="default-order-settings-for-dimensions-and-product-variants"></a>Configurações de ordem padrão para dimensões e variantes de produto

[!include[banner](../includes/banner.md)]


As configurações de ordem padrão definem o local e o depósito de onde os itens serão originários ou armazenados, as quantidades mínima, máxima, múltiplas e padrão que serão usadas para a comercialização ou o gerenciamento de estoque, os prazos de entrega, o sinalizador de parada e o método de promessa de ordens. As configurações de ordem padrão são usadas durante a criação de ordens de compra, ordens de venda, ordens de transferência, diários de estoque e pelo planejamento mestre para a geração de ordens planejadas. As configurações de ordem padrão podem ser específicas por item, local, grade de produto ou dimensão de produto.

Você pode definir as configurações de ordem padrão na página **Configurações de ordem padrão**. Para abrir esta página, vá para **Gerenciamento de informações do produto** &gt; **Produtos** &gt; **Produtos liberados** &gt; selecione um produto liberado &gt; no **Plano** ou no Painel de Ação ****Gerenciar estoque**** &gt; **Configurações da ordem** &gt; **Configurações de ordem padrão**.

## <a name="default-order-settings"></a>Configurações Padrão da Ordem
Há três tipos de configurações de ordem padrão para compras, vendas e estoque. As configurações de ordem padrão para compras são usadas ao criar:

-   Linhas de ordem de compra
-   Linhas do contrato de compra
-   Linhas da solicitação de cotação
-   Linhas de requisição de compra
-   Linhas de reabastecimento de consignação
-   Ordens de Compra Planejadas

As configurações de ordem padrão para vendas são usadas ao criar:

-   Linhas de ordem de venda
-   Linhas do contrato de venda
-   Linhas de cotação de venda
-   Linhas de ordem de devolução e linhas de substituição de item
-   LInhas de previsão de demanda

As configurações de ordem padrão para vendas também são aplicáveis ao criar:

-   Requisitos de itens de projeto
-   Requisições de itens da ordem de serviço

As configurações de ordem padrão para estoque são usadas ao criar:

-   Diários de estoque
-   Ordens de transferência
-   Ordens de transferência planejadas

As configurações de ordem padrão para estoque também são aplicáveis ao criar:

-   Ordens de quarentena
-   Ordens de qualidade
-   Ordens de Produção
-   Linhas de BOM
-   Ordens de produção planejadas

## <a name="full-definition-of-a-released-product"></a>Definição completa de um produto liberado
Ao criar uma transação, é necessário especificar a definição completa de um produto liberado na linha antes que o Dynamics 365 for Operations tente identificar as configurações de ordem padrão. A definição completa de um produto liberado significa que o número de item e todas as dimensões ativas do produto, como configuração, tamanho, estilo e cor estão especificadas na transação. Por exemplo, se você criar manualmente uma linha de ordem de compra para uma grade do produtos liberada, é preciso especificar todas as dimensões do produto necessárias antes que o local, o depósito, a quantidade e o prazo de entrega sejam exibidos por padrão na linha da ordem. 

Nem todos os parâmetros das configurações de ordem padrão são aplicados ao criar linhas de ordem ou de diário. As quantidades e os prazos de entrega somente serão exibidos por padrão quando apropriado. Por exemplo, ao contar uma linha de diário, somente o local e o depósito serão exibidos por padrão quando a linha for criada. Obviamente, nenhuma quantidade padrão ou verificações de múltiplos e mínimos são executadas ao criar a linha ou ao lançar o diário. 

Os sistema sempre tenta encontrar um local e um depósito padrão quando uma linha de ordem ou de diário é criada. O local nem é sempre exibido por padrão nas configurações da ordem. Por exemplo, ao criar uma ordem de venda ou de compra, o local do cabeçalho da ordem é usado automaticamente nas linhas. Ao criar uma linha de BOM, o local do cabeçalho de BOM é usado. Depois que o local for determinado, ele será usado para localizar quaisquer configurações de ordem específicas do local que possam ser usadas como o padrão para o depósito. 

O tipo de ordem padrão, a compra e os prazos de entrega de estoque podem ser substituídos pelas regras de cobertura do item na página **Cobertura de item**. Embora as configurações de ordem padrão não permitam a distinção entre a produção e o prazo de entrega de transferência, as regras de cobertura de item permitem essa distinção. No entanto, a configuração da cobertura do item será usada somente pelo MRP ao criar a produção planejada e as ordens de transferência planejadas e não será aplicável quando as ordens de produção e de transferência forem criadas manualmente. 

## <a name="default-order-settings-rules"></a>Regras das configurações de ordem padrão
Você pode definir configurações gerais de ordem padrão e qualquer número de regras de configuração de ordem padrão que sejam aplicáveis somente em certas condições, como o local ou uma dimensão de produtos específica ou combinação de dimensões do produto. Não é possível definir configurações específicas da ordem de depósito.

### <a name="rank-in-default-order-settings"></a>Classificar configurações de ordem padrão

As regras de configurações de ordem padrão têm classificações. Quanto mais alta a classificação, mais importante é a regra, o que significa que ela terá mais prioridade e será usada antes das regras com classificações inferiores. As configurações gerais de ordem padrão têm a classificação zero, o que não pode ser alterado. Só pode haver uma regra com classificação zero. As regras podem ter a mesma classificação, desde que as dimensões às quais elas sejam aplicáveis sejam diferentes. Isso é útil para a modelagem de configurações específicas de ordem de local. Quando uma nova regra das configurações de ordem padrão é criada, os valores para os valores da ordem, o sinalizador de parada, etc. são herdados da regra com classificação zero, mas podem ser substituídos.

### <a name="default-order-settings-for-released-products"></a>Configurações de ordem padrão para produtos liberados

Para produtos liberados distintos, você pode definir configurações gerais da ordem ou configurações específicas da ordem. As configurações gerais da ordem terão sempre a classificação zero. Se você definir novas configurações de ordem de venda, de compra e de estoque juntas simultaneamente, é recomendável que você use a **Exibição de detalhes** na página **Configurações de ordem padrão**. Para alternar para a exibição de detalhes, vá para o Painel de Ação **Opções** &gt; **Opções de página** &gt; **Alterar exibição** &gt; **Exibição de detalhes**.

### <a name="site-specific-order-settings"></a>Configurações de Ordem Específicas do Local

Para criar configurações específicas de ordem de local, clique em **Novo**. Na **Exibição de detalhes**, preencha o local no campo **Configurações aplicáveis a** &gt; **Local**. Em **Exibição de grade**, preencha o local na coluna **Local**. A nova regra obterá automaticamente um novo valor de classificação, maior que zero. Você pode criar quantas regras específicas de local forem necessárias e pode atribuir a mesma classificação a todas as regras específicas de local, para indicar que elas têm a mesma importância. 

Se estiver em **Exibição de detalhes**, você não poderá obter uma visão geral das regras criadas para o item. Ative o botão **Mostrar/ocultar lista** para consultar as informações da visão geral. Quando uma linha de ordem de qualquer tipo for criada e nenhum local for fornecido, o Dynamics 365 for Operations procurará por uma regra que não tenha nenhum local especificado. Isso pode ajudar a determinar um local padrão na linha da ordem. Esse local será então usado para pesquisar por uma regra específica de local, em que um depósito padrão possa ter sido definido. Esse depósito será aplicado à linha da ordem.

### <a name="specific-order-settings-for-product-dimension"></a>Configurações específicas da ordem para a dimensão do produto

Você poderá definir regras de configuração de ordem para qualquer dimensão de produto ativa ou combinação de dimensões de produto ativas. Se um campo de dimensão de produto for deixado em branco, essa regra será aplicada a todos os valores da dimensão do produto. 

Considere o produto de exemplo a seguir:

|                                                     |                                         |
|-----------------------------------------------------|-----------------------------------------|
| **Nome do produto**                                    | Sensor fotoelétrico                    |
| **Nº de itens**                                     | XW56                                    |
| **Configuração** (usado para indicar o tipo de luz) | C1 – Luz vermelha visível, C2 – Luz infravermelha |
| **Estilo** (usado para indicar a revisão da engenharia)  | R1, R2, R3                              |

Por exemplo, suponha que o produto seja adquirido e não produzido. Suponha também que a configuração C1 é mais comumente usada, portanto tem prazo de entrega menor. 

Crie as seguintes configurações de ordem padrão para indicar esse cenário.

| Classificação | Local | Configuração | Estilo | Compra – substituir configurações padrão | Prazo de entrega da compra | Compra – parada | Vendas – substituir configurações padrão | Vendas – parada |
|------|------|---------------|-------|--------------------------------------|--------------------|--------------------|-----------------------------------|-----------------|
| 10   |      | C1            |       | Sim                                  | 2                  |                    |                                   |                 |
| 0    |      |               |       |                                      | 5                  |                    |                                   |                 |

Quando uma linha de ordem de compra ou de ordem de compra planejada for criada para XW56, Configuração C1, independentemente da revisão ou do local em que for colocada, o prazo de entrega será considerado 2. Suponha que todas as revisões além de R3 estejam paradas.

Você pode criar as regras de configurações de ordem padrão a seguir:

| Classificação | Local | Configuração | Estilo | Compra – substituir configurações padrão | Prazo de entrega da compra | Compra – parada | Vendas – substituir configurações padrão | Vendas – parada |
|------|------|---------------|-------|--------------------------------------|--------------------|--------------------|-----------------------------------|-----------------|
| 20   |      |               | R2    | Sim                                  |                    | Sim                | Sim                               | Sim             |
| 20   |      |               | R1    | Sim                                  |                    | Sim                | Sim                               | Sim             |
| 10   |      | C1            |       | Sim                                  | 2                  |                    |                                   |                 |
| 0    |      |               |       |                                      | 5                  |                    |                                   |                 |

As duas regras para parar as revisões antigas têm a mesma classificação, o que significa que elas têm a mesma importância. Ambas têm uma classificação mais alta do que a regra para a configuração C1, o que significa que elas têm precedência sobre a regra para a configuração C1. 

Este exemplo explica a necessidade para a classificação. Se uma ordem de compra fosse criada para a configuração C1 e a para revisão R2 e se não houvesse classificação, as duas regras definidas para R2 e C1 seriam ambíguas. Para resolver a ambiguidade, o Dynamics 365 for Operations pesquisará regras na ordem decrescente de classificação e usará a primeira regra aplicável. No exemplo atual, quando uma linha de ordem de compra for criada para a configuração C1 e a para revisão R2, o usuário receberá uma mensagem de aviso que o item está em espera e que isso foi causado pelo valor de revisão. Se a regra da configuração tivesse uma classificação maior do que a da revisão, a criação de uma linha de compra para a configuração C1 e para a revisão R2 teria êxito e nenhuma mensagem de "item em espera" seria enviada ao usuário. 

Considere as regras de configuração de ordem padrão a seguir.

| Classificação | Local | Configuração | Estilo | Site padrão | Depósito padrão | Compra – substituir dimensões de armazenamento padrão | Depósito de compra |
|------|------|---------------|-------|--------------|-------------------|------------------------------------------------|--------------------|
| 20   | 2    |               |       |              |                   | Sim                                            | 22                 |
| 10   |      | C1            |  R2   |  2           |  21               |                                                |                    |
| 0    |      |               |       | 1            | 11                |                                                |                    |

O sistema percorre o conjunto de regras duas vezes para determinar o local e o depósito. Quando uma linha de ordem de compra for criada para a configuração C1, estilo R2, o local será determinado com base na regra com classificação 10. O sistema então procurará por uma regra para o local 2 para determinar um depósito. A regra 20 será encontrada e por ter uma classificação maior, o depósito na linha da ordem de compra será 22, e não 21. 

Como regra geral, regras específicas e regras para as dimensões que sejam mais importantes do que outras dimensões obtêm classificações mais altas, enquanto regras mais genéricas obtêm classificações mais baixas. 

A regra com classificação zero serve como uma rede de segurança. Se nenhuma outra regra for aplicada, as configurações de ordem padrão da regra zero serão usadas. 

Como o número de classificação é muito importante, no Painel de Ação **Configurações de ordem padrão**, há funções para mover uma regra para cima ou para baixo e para renumerar as regras, de forma que estejam sempre em incrementos de 10. 

O número de regras criadas para um produto liberado pode ser variado. Para compreender melhor o que cada regra substitui e porque ela é necessária, recomendamos usar a **Exibição de grade** na página**Configurações de ordem padrão**. Você pode habilitar a exibição de grade acessando o Painel de Ação **Opções** &gt; **Opções de página** &gt; **Alterar exibição** &gt; **Exibição de grade**. O número de colunas exibidas na grade pode ser bastante significativo, principalmente para as guias vendas e estoque. Para limitar o número de colunas mostradas na grade, os grupos de colunas podem ser ocultados ou exibidos usando-se os botões no menu **Configurações de ordem padrão** &gt; **Exibição por coluna**.

### <a name="specific-order-settings-for-released-product-variant"></a>Configurações específicas da ordem para grades de produtos liberadas

Se o sistema de regras para as configurações de ordem padrão for muito complicado, há a opção de simplesmente definir as configurações de ordem padrão para cada grade de produto. Os exemplos a seguir mostram como os produtos serão procurados e os casos descritos acima.

| Classificação | Local | Configuração | Estilo | Compra – substituir configurações padrão | Prazo de entrega da compra | Compra – parada | Vendas – substituir configurações padrão | Vendas – parada |
|------|------|---------------|-------|--------------------------------------|--------------------|--------------------|-----------------------------------|-----------------|
| 10   |      | C2            | R3    | Sim                                  | 5                  |                    |                                   |                 |
| 10   |      | C2            | R2    | Sim                                  | 5                  | Sim                | Sim                               | Sim             |
| 10   |      | C2            | R1    | Sim                                  | 5                  | Sim                | Sim                               | Sim             |
| 10   |      | C1            | R3    | Sim                                  | 2                  |                    |                                   |                 |
| 10   |      | C1            | R2    | Sim                                  | 2                  | Sim                | Sim                               | Sim             |
| 10   |      | C1            | R1    | Sim                                  | 2                  | Sim                | Sim                               | Sim             |
| 0    |      |               |       |                                      | 5                  |                    |                                   |                 |

A classificação nesse caso não tem importância, portanto você pode optar por ocultá-la. Esta solução apresenta potencialmente um problema de manutenção. No entanto, você pode querer usar esta configuração se estiver considerando a integração com sistemas PLM (Gerenciamento do Ciclo de Vida do Produto).




