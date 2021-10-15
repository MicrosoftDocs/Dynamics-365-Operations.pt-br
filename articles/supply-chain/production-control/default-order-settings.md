---
title: Configurações de ordem padrão para dimensões e variantes de produto
description: As configurações de ordem padrão definem o local e o depósito de onde os itens serão originários ou armazenados, as quantidades mínima, máxima, múltiplas e padrão que serão usadas para a comercialização ou o gerenciamento de estoque, os prazos de entrega, o sinalizador de parada e o método de promessa de ordens.
author: johanhoffmann
ms.date: 09/23/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: InventItemOrderSetup, InventItemIdLookupByDefaultOrderSetting, EcoResProductReleasedStoppedAllChartPart, UnitTestPartitions
audience: Application User
ms.reviewer: kamaybac
ms.custom: 223084
ms.assetid: fbfbcd7b-dc75-44ab-bffc-8bad576804a4
ms.search.region: global
ms.search.industry: Manufacturing
ms.author: johanho
ms.search.validFrom: 2016-11-30
ms.dyn365.ops.version: 10.0.13
ms.openlocfilehash: 2681a2a13754e240dcc4c99792dc47ae734f6e9e
ms.sourcegitcommit: 3b87f042a7e97f72b5aa73bef186c5426b937fec
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/29/2021
ms.locfileid: "7579415"
---
# <a name="default-order-settings-for-dimensions-and-product-variants"></a>​Configurações de ordem padrão para dimensões e grades de produtos​

[!include [banner](../includes/banner.md)]

As configurações de ordem padrão no Dynamics 365 Supply Chain Management definem o local e o depósito de onde os itens serão originários ou armazenados, as quantidades mínima, máxima, múltipla e padrão que serão usadas para a comercialização ou o gerenciamento de estoque, os prazos de entrega, o sinalizador de parada e o método de promessa de ordens. As configurações de ordem padrão são usadas durante a criação de ordens de compra, ordens de venda, ordens de transferência, diários de estoque e pelo planejamento mestre para a geração de ordens planejadas. As configurações de ordem padrão podem ser específicas por item, local, grade de produto ou dimensão de produto.

Para definir as configurações da ordem padrão de um produto, siga estas etapas.

1. Acesse **Gerenciamento de informações do produto** &gt; **Produtos** &gt; **Produtos liberados**.
1. Selecione o produto relevante na grade.
1. No Painel de Ações, siga uma destas etapas para abrir a página **Configurações Padrão da Ordem** do produto selecionado:

    - Na guia **Plano**, no grupo **Configurações da ordem**, selecione **Configurações padrão da ordem**.
    - Na guia **Gerenciar estoque**, no grupo **Configurações da ordem**, selecione **Configurações padrão da ordem**.

1. Defina as configurações conforme descrito no restante deste tópico.

## <a name="default-order-settings"></a>Configurações Padrão da Ordem

Há três tipos de configurações de ordem padrão para compras, vendas e estoque. As configurações de ordem padrão para compras são usadas ao criar:

- Linhas de ordem de compra
- Linhas do contrato de compra
- Linhas da solicitação de cotação
- Linhas de requisição de compra
- Linhas de reabastecimento de consignação (com suporte parcial, veja a observação)
- Ordens de Compra Planejadas

> [!NOTE]
> Para linhas de ordem de reabastecimento de consignação, as únicas configurações da Guia Rápida **Ordem de compra** da página **Configurações de ordem padrão** que se aplicam são o campo **Site padrão**, o campo **Depósito padrão** e a caixa de seleção **Parado**.

As configurações de ordem padrão para vendas são usadas ao criar:

- Linhas de ordem de venda
- Linhas do contrato de venda
- Linhas de cotação de venda
- Linhas de ordem de devolução e linhas de substituição de item
- LInhas de previsão de demanda

As configurações de ordem padrão para vendas também são aplicáveis ao criar:

- Requisitos de itens de projeto
- Requisições de itens da ordem de serviço

As configurações de ordem padrão para estoque são usadas ao criar:

- Diários de estoque
- Ordens de transferência
- Ordens de transferência planejadas

As configurações de ordem padrão para estoque também são aplicáveis ao criar:

- Ordens de quarentena
- Ordens de qualidade
- Ordens de Produção
- Linhas de BOM
- Ordens de Produção Planejadas

## <a name="full-definition-of-a-released-product"></a>Definição completa de um produto liberado

Ao criar uma transação, é necessário especificar a definição completa de um produto liberado na linha para que o Supply Chain Management possa tentar identificar as configurações de ordem padrão. Na definição completa de um produto liberado, o número de item e todas as dimensões ativas do produto, como configuração, tamanho, estilo, versão e cor estão especificadas na transação. Por exemplo, se você criar manualmente uma linha de ordem de compra para uma grade do produtos liberada, é preciso especificar todas as dimensões do produto necessárias antes que o local, o depósito, a quantidade e o prazo de entrega sejam exibidos por padrão na linha da ordem. 

Nem todos os parâmetros das configurações de ordem padrão são aplicados ao criar linhas de ordem ou de diário. As quantidades e os prazos de entrega somente serão exibidos por padrão quando apropriado. Por exemplo, ao contar uma linha de diário, somente o local e o depósito serão exibidos por padrão quando a linha for criada. Por este motivo, nenhuma quantidade padrão ou verificações de múltiplos e mínimos são executadas ao criar a linha ou ao lançar o diário. 

Os sistema sempre tenta encontrar um local e um depósito padrão quando uma linha de ordem ou de diário é criada. O local nem é sempre exibido por padrão nas configurações da ordem. Por exemplo, ao criar uma ordem de venda ou de compra, o local do cabeçalho da ordem é usado automaticamente nas linhas. Ao criar uma linha de BOM, o local do cabeçalho de BOM é usado. Depois que o local for determinado, ele será usado para localizar quaisquer configurações de ordem específicas do local que possam ser usadas como o padrão para o depósito. 

O tipo de ordem padrão, a compra e os prazos de entrega de estoque podem ser substituídos pelas regras de cobertura do item na página **Cobertura de item**. Embora as configurações de ordem padrão não permitam a distinção entre a produção e o prazo de entrega de transferência, as regras de cobertura de item permitem essa distinção. No entanto, a configuração da cobertura do item será usada somente pelo planejamento mestre (MRP) ao criar a produção planejada e as ordens de transferência planejadas e não será aplicável quando as ordens de produção e de transferência forem criadas manualmente. 

## <a name="default-order-settings-rules"></a>Regras das configurações de ordem padrão

Você pode definir configurações gerais de ordem padrão e qualquer número de regras de configuração de ordem padrão que sejam aplicáveis somente em certas condições, como o local ou uma dimensão de produtos específica ou combinação de dimensões do produto. Não é possível definir configurações específicas da ordem de depósito.

### <a name="rank-in-default-order-settings"></a>Classificar configurações de ordem padrão

As regras de configurações de ordem padrão têm classificações. Quanto mais alta a classificação, mais importante é a regra, o que significa que ela terá mais prioridade e será usada antes das regras com classificações inferiores. As configurações gerais de ordem padrão têm a classificação zero, o que não pode ser alterado. Só pode haver uma regra com classificação zero. As regras podem ter a mesma classificação, desde que as dimensões às quais elas sejam aplicáveis sejam diferentes. Isso é útil para a modelagem de configurações específicas de ordem de local. Quando uma nova regra das configurações de ordem padrão é criada, os valores para os valores da ordem, o sinalizador de parada, etc. são herdados da regra com classificação zero, mas podem ser substituídos.

### <a name="default-order-settings-for-released-products"></a>Configurações de ordem padrão para produtos liberados

Para produtos liberados distintos, você pode definir configurações gerais da ordem ou configurações específicas da ordem. As configurações gerais da ordem terão sempre a classificação zero. Se você definir novas configurações de ordem de venda, de compra e de estoque juntas simultaneamente, é recomendável que você use a **Exibição de detalhes** na página **Configurações de ordem padrão**. Para alternar para a exibição de detalhes, Acesse **Opções** &gt; **Opções da página** &gt; **Alterar exibição** &gt; **Exibição de detalhes**.

### <a name="site-specific-order-settings"></a>Configurações de ordem específica do site

Para criar configurações específicas de ordem do local, selecione **Novo**. Na **Exibição de detalhes**, insira o local no campo **Local** na seção **Configurações aplicáveis a**. Em **Exibição de grade**, insira o local na coluna **Local**. A nova regra é automaticamente atribuída a um novo valor de classificação maior que zero (0). Você pode criar quantas regras específicas do local forem necessárias. Para indicar que são igualmente importantes, é possível atribuir o mesmo valor de classificação a todas as regras específicas do local.

Se estiver em **Exibição de detalhes**, você não poderá obter uma visão geral das regras criadas para o item. Use o botão **Mostrar/Ocultar lista** para ver as informações da visão geral. Quando uma linha da ordem de qualquer tipo é criada e nenhum site é fornecido, o Supply Chain Management procura uma regra sem um site especificado. Isso ajuda a determinar um local padrão na linha da ordem. Esse local será então usado para pesquisar por uma regra específica de local, em que um depósito padrão possa ter sido definido. Esse depósito será aplicado à linha da ordem.

### <a name="specific-order-settings-for-product-dimension"></a>Configurações específicas da ordem para a dimensão do produto

Você poderá definir regras de configuração de ordem para qualquer dimensão de produto ativa ou combinação de dimensões de produto ativas. Se um campo de dimensão de produto for deixado em branco, essa regra será aplicada a todos os valores da dimensão do produto. 

Considere o produto de exemplo a seguir:

| Item                                                 | Alíquota                                   |
|-----------------------------------------------------|-----------------------------------------|
| **Nome do produto**                                    | Sensor fotoelétrico                    |
| **Número do item**                                     | XW56                                    |
| **Configuração** (usado para indicar o tipo de luz) | C1 – Luz vermelha visível, C2 – Luz infravermelha |
| **Versão** | V1, V2, V3                              |

Por exemplo, suponha que o produto seja adquirido e não produzido. Suponha também que a configuração C1 é mais comumente usada, portanto tem prazo de entrega menor. 

Crie as seguintes configurações de ordem padrão para indicar esse cenário.

| Classificação | Site | Configuração | Versão | Compra – substituir configurações padrão | Prazo de entrega da compra | Compra – parada | Vendas – substituir configurações padrão | Vendas – parada |
|------|------|---------------|-------|--------------------------------------|--------------------|--------------------|-----------------------------------|-----------------|
| 10   |      | C1            |       | Sim                                  | 2                  |                    |                                   |                 |
| 0    |      |               |       |                                      | 5                  |                    |                                   |                 |

Quando uma linha de ordem de compra ou de ordem de compra planejada for criada para o item XW56, configuração C1, independentemente da versão ou do local em que for colocada, o prazo de entrega será considerado 2. Suponha que todas as versões além da V3 estejam paradas.

Você pode criar as regras de configurações de ordem padrão a seguir:

| Classificação | Site | Configuração | Versão | Compra – substituir configurações padrão | Prazo de entrega da compra | Compra – parada | Vendas – substituir configurações padrão | Vendas – parada |
|------|------|---------------|-------|--------------------------------------|--------------------|--------------------|-----------------------------------|-----------------|
| 20   |      |               | V2    | Sim                                  |                    | Sim                | Sim                               | Sim             |
| 20   |      |               | V1    | Sim                                  |                    | Sim                | Sim                               | Sim             |
| 10   |      | C1            |       | Sim                                  | 2                  |                    |                                   |                 |
| 0    |      |               |       |                                      | 5                  |                    |                                   |                 |

As duas regras para interromper versões antigas têm a mesma classificação. Portanto, são igualmente importantes. Como ambas as regras têm uma classificação mais alta do que a regra para a configuração C1, elas têm precedência sobre a regra para a configuração C1. 

Este exemplo explica a necessidade para a classificação. Se uma classificação não for usada, quando uma ordem de compra for criada para a configuração C1 e a versão V2, as duas regras definidas para V2 e C1 serão ambíguas. Para resolver a ambiguidade, o Supply Chain Management pesquisará as regras na ordem decrescente de classificação e usará a primeira regra aplicável. No exemplo atual, quando uma linha de ordem de compra for criada para a configuração C1 e a versão V2, o usuário receberá uma mensagem de aviso informando que o item está em espera e que essa espera foi causada pelo valor de versão. Se a regra da configuração tivesse uma classificação maior do que a da versão, uma linha de compra seria criada com êxito para a configuração C1 e para a versão V2 e o usuário não receberia uma mensagem de "item em espera". 

Considere as regras de configuração de ordem padrão a seguir.

| Classificação | Site | Configuração | Versão | Site padrão | Depósito padrão | Compra – substituir dimensões de armazenamento padrão | Depósito de compra |
|------|------|---------------|-------|--------------|-------------------|------------------------------------------------|--------------------|
| 20   | 2    |               |       |              |                   | Sim                                            | 22                 |
| 10   |      | C1            |  V2   |  2           |  21               |                                                |                    |
| 0    |      |               |       | 1            | 11                |                                                |                    |

O sistema percorre o conjunto de regras duas vezes para determinar o local e o depósito. Quando uma linha de ordem de compra for criada para a configuração C1, versão V2, o local será determinado com base na regra com classificação 10. O sistema então procurará por uma regra para o local 2 para determinar um depósito. A regra 20 será encontrada e por ter uma classificação maior, o depósito na linha da ordem de compra será 22, não 21.

Como regra geral, regras específicas e regras para as dimensões que sejam mais importantes do que outras dimensões obtêm classificações mais altas, enquanto regras mais genéricas obtêm classificações mais baixas. 

A regra com classificação zero serve como uma rede de segurança. Se nenhuma outra regra for aplicada, as configurações de ordem padrão da regra zero serão usadas. 

Como o número de classificação é muito importante, no Painel de Ação **Configurações de ordem padrão**, há funções para mover uma regra para cima ou para baixo e para renumerar as regras, de forma que estejam sempre em incrementos de 10. 

O número de regras criadas para um produto liberado pode ser variado. Para compreender melhor o que cada regra substitui e porque ela é necessária, recomendamos usar a **Exibição de grade** na página **Configurações de ordem padrão**. Você pode habilitar a exibição de grade acessando **Opções** &gt; **Opções de página** &gt; **Alterar exibição** &gt; **Exibição de grade**. O número de colunas exibidas na grade pode ser bastante significativo, principalmente para as guias vendas e estoque. Para limitar o número de colunas mostradas na grade, os grupos de colunas podem ser ocultados ou exibidos usando-se os botões no menu **Configurações de ordem padrão** &gt; **Exibição por coluna**.

### <a name="specific-order-settings-for-released-product-variant"></a>Configurações específicas da ordem para grades de produtos liberadas

Se o sistema de regras para as configurações de ordem padrão for muito complicado, há a opção de simplesmente definir as configurações de ordem padrão para cada grade de produto. O exemplo a seguir mostra como o produto será procurado e os casos descritos acima.

| Classificação | Site | Configuração | Versão | Compra – substituir configurações padrão | Prazo de entrega da compra | Compra – parada | Vendas – substituir configurações padrão | Vendas – parada |
|------|------|---------------|-------|--------------------------------------|--------------------|--------------------|-----------------------------------|-----------------|
| 10   |      | C2            | V3    | Sim                                  | 5                  |                    |                                   |                 |
| 10   |      | C2            | V2    | Sim                                  | 5                  | Sim                | Sim                               | Sim             |
| 10   |      | C2            | V1    | Sim                                  | 5                  | Sim                | Sim                               | Sim             |
| 10   |      | C1            | V3    | Sim                                  | 2                  |                    |                                   |                 |
| 10   |      | C1            | V2    | Sim                                  | 2                  | Sim                | Sim                               | Sim             |
| 10   |      | C1            | V1    | Sim                                  | 2                  | Sim                | Sim                               | Sim             |
| 0    |      |               |       |                                      | 5                  |                    |                                   |                 |

A classificação nesse caso não tem importância, portanto você pode optar por ocultá-la. Esta solução apresenta potencialmente um problema de manutenção. No entanto, você pode usar esta configuração se estiver considerando a integração com sistemas PLM (Gerenciamento do Ciclo de Vida do Produto).

## <a name="use-strict-or-standard-validation-of-default-order-quantities"></a>Usar validação estrita ou padrão de quantidades de ordem padrão

Você pode escolher o rigor que o sistema deve ser ao validar as quantidades inseridas nas **Configurações de ordem padrão** para um produto. Quando você usa a nova opção restrita, a **Quantidade de ordem padrão** sempre deve ser um múltiplo do valor **Múltiplo** especificado para ordens de compra, estoque e ordens de venda. Se você estiver usando uma validação restrita, não poderá salvar as configurações de ordem padrão que não atendem a esse requisito (e um erro é exibido na barra de mensagens). 

A validação restrita aplica-se aos valores **Quantidade de ordem padrão** especificados nas guias rápidas **Ordem de compra**, **Estoque** e **Ordem de venda** da página **Configurações da ordem padrão**. Cada guia rápida tem sua própria configuração **Múltipla** para validar o valor **Quantidade de ordem padrão** especificado para essa guia rápida.

### <a name="enable-the-strict-validation-option"></a>Habilitar a opção de validação restrita

Para que você possa usar a opção de validação restrita, ela deve ser habilitada em seu sistema. Os administradores podem usar a página [Gerenciamento de recursos](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md) para verificar o status do recurso e ativá-lo, se necessário. Aqui o recurso está listado como:

- **Módulo** - *Gerenciamento de informações sobre o produto*
- **Nome do recurso** - *Validação restrita nas quantidades da ordem padrão*

### <a name="set-the-validation-option"></a>Definir a opção de validação

Para definir a opção de validação:

1. Acesse **Gerenciamento de informações sobre produtos \> Configuração \> Parâmetros de gerenciamento de informações do produto**.
1. Na guia **Geral**, defina **Validação nas quantidades da ordem padrão** para um dos seguintes valores:
    - **Restrito** -Selecione esta opção para garantir que todos os valores da **Quantidade da ordem padrão** serão um valor **Múltiplo** de cada guia rápida (**Ordem de compra**, **Estoque** e **Ordem de venda**).
    - **Padrão** - Selecione esta opção para usar a validação padrão (que funciona da mesma maneira quando esse recurso não está habilitado).


[!INCLUDE[footer-include](../../includes/footer-banner.md)]