---
title: Contratos de venda
description: "Este artigo fornece informações sobre contratos de venda. Um contrato de venda é um contrato que confirma que o cliente pode comprar produtos em uma determinada quantidade ou valor por um período em troca de preços especiais e descontos."
author: YuyuScheller
manager: AnnBe
ms.date: 04/04/2017
ms.topic: article
ms.prod: 
ms.service: Dynamics365Operations
ms.technology: 
ms.search.form: SalesAgreement, SalesAgreementGenerateReleaseOrder, SalesAgreementListPage
audience: Application User
ms.reviewer: YuyuScheller
ms.search.scope: AX 7.0.0, Operations, Core
ms.custom: 9554
ms.assetid: c5d55c8d-99f2-44f9-a897-5b0dee85fc81
ms.search.region: Global
ms.author: omulvad
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
translationtype: Human Translation
ms.sourcegitcommit: 9ccbe5815ebb54e00265e130be9c82491aebabce
ms.openlocfilehash: 4dd1eae27ae33837fbab16f764083168578d0a29
ms.lasthandoff: 03/31/2017


---

# <a name="sales-agreements"></a>Contratos de venda

Este artigo fornece informações sobre contratos de venda. Um contrato de venda é um contrato que confirma que o cliente pode comprar produtos em uma determinada quantidade ou valor por um período em troca de preços especiais e descontos.

Um contrato de venda é um contrato que confirma que o cliente compra produtos ao longo do tempo em uma quantidade específica ou para um valor específico, em troca de preços promocionais especiais, descontos especiais, e outras condições especiais, como o pagamento e condições de entrega. Os preços e os descontos do contrato de venda substituem os preços e os descontos que declarados em qualquer contrato comercial que possa existir.  

O período de validade de um contrato de venda é definido pelos campos **Data de efetivação** e **Data de vencimento** no contrato. A ordem de venda de um cliente qualifica para as condições do contrato, se a data de remessa solicitada da ordem está dentro do período de validade. Todas as linhas da ordem de venda que estão vinculadas a um contrato de venda contribuem para a realização desse contrato de venda.  

Você pode criar uma ordem de venda diretamente de um contrato de venda usando a ação **Liberar ordem**. Como alternativa, você pode selecionar um contrato de venda efetivo quando estiver fazendo pedidos (consulte a seção “Aplicando contratos de venda no processo de ordem” deste artigo).  

** Observação: ** Em versões anteriores, contratos de venda foram indicados como ordens de venda amplas.

## <a name="commitment-types"></a>Tipos de compromisso
Cada linha de um contrato de venda expressa um compromisso de vender algo. Geralmente, há duas categorias de compromisso:

-   **Compromisso de valor **– O cliente concorda em comprar produtos para um valor específico.
-   **Compromisso de quantidade **– O cliente concorda em comprar uma quantidade específica de produtos.

Além de isso, um contrato pode confirmar que o cliente comprará um produto ou produtos específicos em uma categoria de produto. Combinando esses dois fatores (valor versus quantidade, e produto específico versus categorias de produto), obtivemos quatro tipos de compromisso:

-   **Compromisso de quantidade do produto** – O cliente concorda em comprar uma quantidade específica de produtos. As linhas que usam este tipo do compromisso são definidas por um número de item e, pela quantidade e unidade que acordadas. O campo **Valor** não está disponível.
-   **Compromisso de valor do produto** – O cliente concorda em comprar produtos específicos para um valor específico. As linhas que usam este tipo do compromisso são definidas por um número de item e pelo valor acordados. Os campos **Quantidade** e **Unidade** não estão disponíveis.
-   **Compromisso de valor de categoria do produto** – O cliente concorda em comprar produtos de uma categoria de vendas específica com um valor específico. As linhas que usam este tipo do compromisso são definidos por uma categoria de vendas na hierarquia das categorias de vendas e por um valor. Os campos **Quantidade** e **Unidade** não estão disponíveis.
-   **Compromisso de valor** – O cliente concorda em comprar qualquer produto ou produtos em qualquer categoria de aquisição com um valor específico. Os campos **Quantidade** e **Unidade** não estão disponíveis.

As linhas do mesmo contrato de venda podem ter diferentes tipos de compromissos.

## <a name="pricing-terms-for-sales-agreements"></a>Condições de preço para contratos de venda
As condições de preço podem variar, de acordo com o tipo de compromisso. Em uma ordem de venda que está vinculada a um contrato de venda, os termos de preços do contrato de venda substituem todos os outros termos de preços que se aplicam com base nos contratos comerciais. A tabela a seguir descreve os campos relacionados ao preço que serão afetados por cada tipo de compromisso. "Sim" indica que o campo pode ser atualizado em uma linha de ordem.

| Tipo do compromisso                   | Preço unitário | Unidade de preço | Percentual de desconto | Valor de desconto à vista |
|-----------------------------------|------------|------------|------------------|----------------------|
| Compromisso de quantidade do produto       | Sim        | Sim        | Sim              | Sim                  |
| Compromisso de valor do produto          |            |            | Sim              |                      |
| Compromisso de valor de categoria de produto |            |            | Sim              |                      |
| Compromisso de valor                  |            |            | Sim              |                      |

## <a name="policies-for-sales-agreements"></a>Políticas de contratos de venda
As políticas a seguir afetam o funcionamento do link entre um compromisso de contrato de venda e as linhas da ordem de venda correspondente:

-   **Imposição de valor máx.** – a quantidade ou o valor total de todas as linhas da ordem não pode exceder a quantidade ou o valor que é especificado no compromisso relacionado.
-   **O preço e o desconto são fixos** – O preço em uma linha da ordem e o preço no compromisso relacionado não podem ser diferentes. Se o preço foi alterado na linha da ordem, o link para o compromisso será desfeito. Se o link foi desfeito, a linha da ordem não contribuirá com o atendimento do compromisso.
-   **Valor de liberação mínimo** e **Valor de liberação máximo** – Se um valor for especificado, será exibida uma mensagem se você fizer alguma alteração em uma linha da ordem que faça com que ela seja diferente do compromisso relacionado.

## <a name="fulfillment-calculations-for-sales-agreements"></a>Cálculos de atendimento para contratos de venda
A guia **Atendimento** na Guia Rápida **Detalhes da linha** na página **Contratos de venda** mostra as quantidades e valores de orçamento.  

Na área **Atendimento**, você pode exibir as quantidades e valores totais para todas as linhas de ordem que estão vinculadas ao contrato de venda especificado. Também é possível exibir o valor ou a quantidade restante necessário para preencher o compromisso.  

Na área **Contrato**, você pode exibir as quantidades e valores de um contrato de vendas especificado. Esses valores e quantidades são os totais que foram comprometidos.

## <a name="confirmations-and-version-history-for-sales-agreements"></a>Histórico de versões e confirmações para contratos de venda
Quando você confirma um contrato de venda, a versão atual do contrato é armazenada em uma tabela histórica. Se você alterar o contrato de venda, você o confirma novamente para armazenar outra versão do contrato de venda no histórico.  

Se não confirmar um contrato de venda, você ainda poderá usá-lo para criar ordens de venda. No entanto, as informações do histórico do contrato de venda não são armazenadas.  

É possível visualizar ou imprimir todas as revisões das confirmações. Você pode compartilhar as revisões com seu cliente para obter aprovação.

## <a name="applying-sales-agreements-during-the-ordering-process"></a>Aplicando contratos de venda durante o processo de pedido
Se não liberar ordens de venda diretamente para contratos de venda, você ainda poderá vincular um contrato de venda a uma ordem durante o processo de entrada de ordem. Ao criar uma nova ordem de venda e selecionar um contrato de venda, termos desse contrato, como as condições de pagamento, condições de entrega, e endereço de entrega, são aplicados ao cabeçalho da ordem, e o vínculo entre o contrato e a ordem é criado. Em seguida, nas linhas da ordem quando você selecionar os produtos e as categorias especificados no contrato de venda, os preços e descontos serão copiados desse contrato. A mesma ordem de vendas pode ter linhas que não estão relacionadas a um contrato de venda e linhas que têm um compromisso para um contrato de venda.

## <a name="modifying-sales-orders-that-are-linked-to-sales-agreements"></a>Alternando ordens de venda que estão vinculadas a contratos de venda
Se você criou (liberou) uma ordem de venda com um contrato de venda, determinados campos nas linhas da ordem de venda poderão ser modificados somente se você remover o link para as linhas de contrato de venda associadas. A tabela a seguir lista alguns desses campos.

| Campo                                                             | Descrição                                                                                                                                                                                                                                                                                                                                                                                                                                                  |
|-------------------------------------------------------------------|--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Data de remessa solicitada                                               | Se alterar a data de remessa solicitada para uma data que seja anterior ao valor de **Data efetiva** na linha do contrato de venda, você deverá remover o link da linha do contrato de venda antes de salvar a data de remessa alterada. Se alterar a data de remessa solicitada para uma data que seja posterior ao valor de **Data de vencimento** na linha do contrato de venda, você deverá remover o link da linha do contrato de venda, antes de salvar a data de remessa alterada. |
| Valor CurrencyDiscount, percentDiscountUnit, pricePrice, unitNet | Se você alterar o valor em qualquer um desses campos, e se a caixa de seleção **O preço e o desconto são fixos** estiver marcada em uma linha de contrato de venda associada, uma caixa de mensagem solicitará que a alteração seja salva. Clique em **Sim** para remover o link para a linha de contrato de venda e recalcular o preço. Clique em **Não** para remover o link para a linha de contrato de venda sem recalcular o preço.                                                                   |
| Valor líquido                                                        | Se você especificar um valor que excede o valor especificado em uma linha de contrato de venda onde a caixa de seleção **Imposição de valor máx.** está marcada, uma caixa de mensagem solicitará que você salve o valor alterado. Clique em **Sim** para remover o link para a linha de contrato de venda e recalcular o preço. Clique em **Não** para remover o link para a linha de contrato de venda sem recalcular o preço.                                                                 |
| Quantidade                                                          | Se você especificar uma quantidade que excede a quantidade especificada em uma linha de contrato de venda onde a caixa de seleção **Imposição de valor máx.** está marcada, uma caixa de mensagem solicitará que você salve a quantidade alterada. Clique em **Sim** para remover o link para a linha de contrato de venda e recalcular o preço. Clique em **Não** para remover o link para a linha de contrato de venda sem recalcular o preço.                                                            |

## <a name="returning-an-item-that-was-ordered-from-a-sales-agreement"></a>Devolvendo um item encomendado de um contrato de venda
Quando um cliente devolve um produto que são solicitados a um contrato de venda 365, Microsoft Dynamics para operações pode localizar e atualizar automaticamente o compromisso relacionadas de acordo de venda refletir a alteração na quantidade ou o valor. Ao criar uma ordem de devolução com base na ordem de venda original que é vinculada a um contrato de venda, você estabelece uma relação entre o compromisso do contrato de venda, a linha da ordem de venda e a fatura da ordem de devolução.  

Se não quiser deduzir a quantidade de item devolvido do compromisso do contrato de venda, você poderá usar o controle **Remover link** na **Ordem de devolução** para remover o link entre a ordem de devolução e o compromisso do contrato de venda. Se tiver que restabelecer o link posteriormente, clique **Criar link**.  

**Observação:** Uma ordem de devolução pode ser vinculada somente a um contrato de venda. Se o cliente devolver vários produtos que foram solicitados de vários contratos de venda, você deverá criar uma nova ordem de devolução para cada produto e criar um link para o contrato de venda correspondente.

## <a name="automatic-search-for-sales-agreements"></a>Pesquisa automática por contratos de venda
Em algumas situações nas ordens de venda são criados como indiretamente, quando você cria uma nota ou ordens de venda intercompanhia de crédito, você poderá controlar se o Microsoft Dynamics 365 para pesquisas operações automaticamente de contratos de venda aplicável.

## <a name="financial-dimensions-on-sales-agreements"></a>Dimensões financeiras nos contratos de venda
Você pode copiar as dimensões financeiras para os cabeçalhos de documento ou para as linhas individuais de um contrato de venda. Você pode alterar as dimensões no cabeçalho do contrato ou em uma linha do contrato a qualquer momento. Nesse caso, as dimensões são copiadas automaticamente para o cabeçalho de liberação ou a linha de liberação das ordens de liberação.


