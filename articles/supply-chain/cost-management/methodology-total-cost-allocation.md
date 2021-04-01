---
title: Método de alocação de custo total
description: Este tópico oferece diretrizes para usar a alocação de custo total (TCA). A TCA é um método de cálculo de custos entre o item de fórmula principal para uma ordem de lote e os coprodutos definidos para a fórmula.
author: AndersGirke
manager: tfehr
ms.date: 04/15/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: BOMConsistOf, PmfFormulaCoBy
audience: Application User
ms.reviewer: kamaybac
ms.custom: 83852
ms.assetid: 7c14c3e5-9476-4a79-a210-e77fc91cc7fc
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: mguada
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: c37463bf2f31a900e6f5a8e106b9d58b1fdedcaa
ms.sourcegitcommit: eaf330dbee1db96c20d5ac479f007747bea079eb
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/15/2021
ms.locfileid: "5235523"
---
# <a name="total-cost-allocation-method"></a>​Método de alocação de custo total​

[!include [banner](../includes/banner.md)]

A alocação de custo total (TCA) é um método de cálculo de custos entre o item de fórmula principal para uma ordem de lote e os coprodutos definidos para a fórmula. Esse método é dinâmico. Ele calcula os custos como uma média ponderada entre as quantidades relatadas como concluídas para o item de fórmula e os coprodutos. Quando a TCA é usada, não é necessário examinar as alocações de custo para cada ordem de lotes. Se a TCA não for usada, o cálculo da fórmula usa a funcionalidade existente.

## <a name="using-tca-for-coproducts"></a>Usando TCA para coprodutos
Veja algumas das diretrizes para usar TCA para coprodutos:

-   Se você definir o controle deslizante **Alocação de custo total** como **Sim** para uma versão da fórmula, os coprodutos deverão ter um preço de custo maior do que 0 (zero). O valor pode ser obtido da versão de custo ativa para ao mesmo site, ou para o primeiro site para uma fórmula não específica de site. Essa condição é validada quando a fórmula é aprovada.

    -   Não será necessário digitar manualmente porcentagens de alocação de custos para coprodutos. Em vez disso, o sistema cria automaticamente a porcentagem de alocação de custo previsto como média de preços de custo ativos de coprodutos. 
    -   Você não precisa inserir custos padrão para itens de custo não padrão que são coprodutos. Há dois tipos de versões de avaliação de custo no sistema: custo padrão e custo planejado 
    -   Se um item não estiver avaliado pelo método de avaliação de custo padrão, recomendamos usar um preço de custo ativo na versão de custo planejado. Esse preço é usado para estimativa de custo, por exemplo, cálculo de BOM, estimativa de custo de produção e preço de fallback no processo de avaliação de estoque. 

-   Se você definir o controle deslizante **Alocação de Custo Total** como **Sim** para a versão da fórmula e as condições a seguir forem verdadeiras, o método de alocação de custo será **TCA** e a porcentagem de alocação de custo prevista permanecerá inalterada:
    -   Você adicionou coprodutos.
    -   Você usou um método diferente de alocação de custos para os coprodutos.
-   Se você definir o controle deslizante **Alocação de Custo Total** como **não** para a versão da fórmula e as condições a seguir forem verdadeiras, o método de alocação de custo será alterado para **Manual** e a porcentagem de alocação de custo prevista permanecerá inalterada:
    -   Você adicionou coprodutos.
    -   A porcentagem de alocação de custos é maior do que 0 (zero)
-   Antes que você possa realizar com êxito o cálculo da fórmula, você deverá estimar as porcentagens de alocação de custos. Você pode concluir esta etapa manualmente ou usando a opção **Estimar custo** na página **Coprodutos**. **Observação:** a opção **Estimar custo** só estará disponível quando a caixa de seleção **Alocação de Custo Total** for definida como **Sim** na versão da fórmula. Você pode exibir a alocação prevista se as quantidades da ordem de lote relatadas como concluídas corresponderem às quantidades que aparecem na fórmula.
-   Quando uma ordem de lotes é criada manualmente ou uma ordem de lote planejada é confirmada, o valor do controle deslizante **Alocação de Custo Total** para a versão da fórmula é copiada para a ordem de lotes. No entanto, você pode alterar essa configuração na ordem de lotes. Se o controle deslizante **Alocação Total de Custo** for definido como **Não** para a versão da fórmula e então alterado para **Sim** para a ordem de lotes, o método de alocação de custo para cada linha definido como **Manual** será alterado para **TCA**. Uma alocação de custo **Nenhuma** permanecerá inalterada. Se o controle deslizante **Alocação Total de Custo** for definido como **Sim** para a versão da fórmula e então alterado para **Não** para a ordem de lotes, o método de alocação de custo para cada coproduto do tipo **Produção** será alterado para **Manual**. Qualquer porcentagem prevista de alocação de custos permanece inalterada.
-   A página **Alocação de custo de coproduto** mostra a porcentagem calculada de alocação de custo. Você pode abrir essa página da página **Ordem de lotes**. Essas informações são úteis quando os produtos e as quantidades relatados são diferentes das quantidades agendadas ou iniciadas na ordem de lotes. Quando o custo for concluído, essas novas alocações de porcentagem de TCA serão mostradas na página **Alocação de custo de coproduto**.

## <a name="calculating-the-burden-for-byproducts"></a>Como calcular o custo indireto de subprodutos
O campo **Alocação de custo de subproduto** na página **Coprodutos** é um campo enumerador usado apenas para subprodutos. Para coprodutos, o valor deste campo é sempre **Nenhum**. Para linhas de subproduto, esse campo determina como o valor de custo para a linha de subprodutos será adicionado aos custos totais de produção. As opções a seguir estão disponíveis:

-   **Nenhum**: nenhum valor é adicionado aos custos totais de produção para essa linha de subproduto.
-   **Percentual**: o valor de custo é calculado como uma porcentagem do custo total de matérias-primas que são consumidas na produção. A porcentagem usada para o cálculo é inserida no campo.
-   **Por série**: o valor de custo é calculado como um valor pelo tamanho de lote padrão da ordem de produção. Esse valor é independente da quantidade relatada na produção. O valor usado para o cálculo é inserido no campo.
-   **Por quantidade** ─ o valor de custo é calculado como um valor por quantidade relatada do item de fórmula na produção. O valor usado para o cálculo é inserido no campo.






[!INCLUDE[footer-include](../../includes/footer-banner.md)]