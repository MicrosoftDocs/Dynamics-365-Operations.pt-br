---
title: Visão geral do estado do ciclo de vida do produto
description: O estado do ciclo de vida de um produto documenta o estado do ciclo de vida de um produto ou grade de produto liberado.
author: t-benebo
ms.date: 01/06/2020
ms.topic: overview
ms.prod: ''
ms.technology: ''
ms.search.form: EcoResProductLifecycleState, EcoResReleasedProductLifecycleStateChanges
audience: Application User, IT Pro
ms.reviewer: kamaybac
ms.assetid: ''
ms.search.region: global
ms.search.industry: ''
ms.author: benebotg
ms.dyn365.ops.version: 7.2999999999999998
ms.search.validFrom: 2017-12-31
ms.openlocfilehash: f71ce701adbe60b69b25e41810dda7adeec1d390
ms.sourcegitcommit: 3754d916799595eb611ceabe45a52c6280a98992
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/15/2022
ms.locfileid: "7983785"
---
# <a name="product-lifecycle-state-overview"></a>Visão geral do estado do ciclo de vida do produto

[!include [banner](../includes/banner.md)]

O estado do ciclo de vida de um produto documenta o estado do ciclo de vida de um produto ou grade de produto liberado. Os estados do ciclo de vida de produto são definidos pelo usuário, geralmente um gerente de produto ou um gerente de dados mestre de produto. Os processos de negócios específicos, como planejamento mestre podem ser afetados por um estado específico do ciclo de vida.

Um produto ou grade de produto pode ser associado a um estado do ciclo de vida do produto que documenta em qual estado do ciclo de vida um produto ou grade específica está no momento. É possível definir qualquer número de estados do ciclo de vida do produto atribuindo um nome e uma descrição do estado. Você pode selecionar um estado do ciclo de vida como o status padrão de novos produtos liberados. As grades de produtos liberados herdam o estado do ciclo de vida do produto de seus produtos mestres liberados na criação. Ao alterar o estado do ciclo de vida em um produto mestre liberado, você pode optar por atualizar todas as grades existentes com o mesmo estado original.  

## <a name="create-a-new-product-lifecycle-state"></a>Criar um novo estado do ciclo de vida do produto

- Para criar um novo estado do ciclo de vida do produto, consulte [Criar um novo estado do ciclo de vida do produto](tasks/new-product-lifecycle-state.md).

- Para criar um estado do ciclo de vida do produto padrão, consulte [Criar um estado do ciclo de vida do produto padrão](tasks/default-product-lifecycle-state.md).

## <a name="associate-product-lifecycle-states-to-released-products"></a>Associar estados do ciclo de vida do produto aos produtos liberados  

Há várias formas de associar um estado do ciclo de vida do produto aos produtos ou grades de produtos liberados.

- Na criação de um novo produto liberado, o **Estado do ciclo de vida do produto** padrão é atribuído automaticamente.
- Na liberação de um produto para uma entidade legal, o **O estado do ciclo de vida do produto** padrão é atribuído automaticamente.
- Na liberação de uma grade de produto a uma entidade legal, o **Estado do ciclo de vida do produto** associado a produtos mestre liberados na entidade legal é atribuído automaticamente à nova grade.

Você pode atualizar manualmente o estado do ciclo de vida do produto usando:

- A página de listagem **Produtos liberados** ou **Exibição de detalhes**.
- A página de listagem **Grades de produtos liberadas** ou **Exibição de detalhes**.
- Localize os produtos obsoletos ou grades de produtos com base em demanda e associe um estado do ciclo de vida.  

Para obter mais informações:

- Para associar um estado do ciclo de vida do produto a um produto mestre, consulte [Atribuir um estado do ciclo de vida do produto a um produto mestre liberado](tasks/product-lifecycle-state-released-product-master.md).

- Para associar um estado do ciclo de vida do produto a um produto liberado, consulte [Atribuir um estado do ciclo de vida do produto a um produto liberado](tasks/product-lifecycle-state-released-product.md).

## <a name="impact-on-master-planning"></a>Impacto no planejamento mestre

O estado do ciclo de vida de produto só tem um sinalizador de controle: **Está ativo para planejar**. Por padrão, é definido como **Sim** para todos os estados do ciclo de vida do produto criados, mas pode ser alterado para **Não**. Quando definido como **Não**, os produtos liberados ou grades do produto liberados associados são:

- Excluído do planejamento mestre.
- Excluído do cálculo do nível da BOM.

Para obter informações detalhadas sobre como usar o estado do ciclo de vida do produto para excluir produtos do cálculo de planejamento mestre e do nível da BOM, consulte [Criar um estado do ciclo de vida do produto para excluir produtos do planejamento mestre](tasks/exclude-products-master-planning.md)

> [!NOTE]
> Por motivo de desempenho, é altamente recomendável associar todos os produtos liberados ou grades de produtos obsoletos, especialmente ao trabalhar com grades de configuração de produto não reutilizáveis, com um estado do ciclo de vida do produto que será desativado para o planejamento mestre.  

## <a name="default-migration-import-and-export"></a>Migração, importação e exportação padrão

Os estados do ciclo de vida do produto não são compatíveis com entidades de dados, e o estado do ciclo de vida pode ser definido para um estado variável pelas entidades de dados de produto liberadas ou pela entidade de dados da variante liberada.

## <a name="find-obsolete-products-and-products-variants"></a>Localizar produtos e grades de produto obsoletos

Você poderá executar uma análise de simulação para localizar produtos ou grades de produtos liberados obsoletos e atualizar o status do ciclo de vida do produto. Para localizar, produtos obsoletos, consulte [Localizar grades de produto obsoletos e atribuir um estado do ciclo de vida do produto](tasks/obsolete-product-variants.md). Este tópico mostra como localizar produtos ou grades de produtos liberados obsoletos e como associar um estado do ciclo de vida do produto aos produtos obsoletos. Também mostra como exibir os resultados de simulação e avaliar quantos produtos e grades de produto serão associadas a um novo estado do ciclo de vida de produto ao executar a atualização sem simulação.  

Ao executar a análise em um modo de simulação, os produtos e as grades de produto identificadas como obsoletos são exibidos em um formulário específico, no qual podem ser facilmente revisados. A análise pesquisa transações e dados mestres específicos para identificar produtos que não têm demanda dentro de um período variável e nenhum dado mestre que pode resultar em demanda. Os novos produtos lançados em um período de variáveis podem ser excluídos da análise. Quando a simulação de análise retornar o resultado esperado, o usuário pode executar a análise e definir um novo estado do ciclo de vida do produto a todos os produtos identificados como obsoletos pela análise.  

> [!NOTE]
> Observe que todas as análises e atualizações devem ser feitas dentro da mesma entidade legal.  

## <a name="criteria-to-select-and-update-released-products-or-product-variants"></a>Os critérios para selecionar e atualizar os produtos e grades de produtos liberados

Use os seguintes critérios para selecionar e atualizar os produtos e grades de produtos liberados:

- O estado do ciclo de vida do produto ou grade do produto devem ser diferentes do novo status desejado.
- O produtos ou a grade do produto foram criados alguns dias antes com base no número de dias inserido na caixa de diálogo de seleção.
- Não há nenhuma ordem de produção aberta (= status < concluído) para o produto ou grade de produto.
- Não há transações de estoque abertas (= status de saída ReservPhysical para QuotationIssue ou status de recebimento Registrered para QuotationReceipt) para o produto ou grade do produto.
- Não há transações de estoque dentro do último número de dias para o produto ou grade de produto.
- Não há demanda futura ou previsão de fornecimento para o produto ou grade de produto.  
- Nenhum nível de estoque mínimo foi definido na cobertura do item para o produto ou grade de produto.
- Nenhuma regra kanban de quantidade fixa do produto ou grade de produto.  
- Nenhuma linha de ordem de serviço para produto ou grade de produto.
- Nenhuma linha do contrato de compra ou venda ativa ou futura para o produto ou grade do produto.
- O produto ou grade do produto não é usada em uma BOM associada a uma versão da BOM não aprovada expirada para um produto ou grade que esteja ativo(a) para planejamento.

## <a name="related-topics"></a>Tópicos relacionados

- [Criar um novo estado do ciclo de vida do produto](tasks/new-product-lifecycle-state.md)
- [Criar um estado do ciclo de vida do produto padrão](tasks/default-product-lifecycle-state.md)
- [Atribuir um estado de ciclo de vida do produto a um produto mestre liberado](tasks/product-lifecycle-state-released-product-master.md)
- [Atribuir um estado de ciclo de vida do produto a um produto liberado](tasks/product-lifecycle-state-released-product.md)
- [Localizar grades de produto obsoletos e atribuir um estado do ciclo de vida do produto](tasks/obsolete-product-variants.md)
- [Criar um estado do ciclo de vida do produto para excluir produtos do Planejamento mestre](tasks/exclude-products-master-planning.md)


[!INCLUDE[footer-include](../../includes/footer-banner.md)]