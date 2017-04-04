---
title: "Método de alocação de custo total"
description: "Este artigo oferece diretrizes para usar a alocação de custo total (TCA). A TCA é um método de cálculo de custos entre o item de fórmula principal para uma ordem de lote e os coprodutos definidos para a fórmula."
author: YuyuScheller
manager: AnnBe
ms.date: 04/04/2017
ms.topic: article
ms.prod: 
ms.service: Dynamics365Operations
ms.technology: 
ms.search.form: BOMConsistOf, PmfFormulaCoBy
audience: Application User
ms.search.scope: AX 7.0.0, Operations, Core
ms.custom: 83852
ms.assetid: 7c14c3e5-9476-4a79-a210-e77fc91cc7fc
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: mguada
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
translationtype: Human Translation
ms.sourcegitcommit: 9ccbe5815ebb54e00265e130be9c82491aebabce
ms.openlocfilehash: c26dcc5a8caa461bce90f931bb5c584f1816526b
ms.lasthandoff: 03/31/2017


---

# <a name="total-cost-allocation-method"></a>Método de alocação de custo total

Este artigo oferece diretrizes para usar a alocação de custo total (TCA). A TCA é um método de cálculo de custos entre o item de fórmula principal para uma ordem de lote e os coprodutos definidos para a fórmula.

A alocação de custo total (TCA) é um método de cálculo de custos entre o item de fórmula principal para uma ordem de lote e os coprodutos definidos para a fórmula. Esse método é dinâmico. Ele calcula os custos como uma média ponderada entre as quantidades relatadas como concluídas para o item de fórmula e os coprodutos. Quando a TCA é usada, não é necessário examinar as alocações de custo para cada ordem de lotes. Se a TCA não for usada, o cálculo da fórmula usa a funcionalidade existente.

## <a name="using-tca-for-coproducts"></a>Usando o TCA para coproducts
Veja algumas das diretrizes para usar TCA para coprodutos:

-   Se você definir o controle deslizante **Alocação de custo total** como **Sim** para uma versão da fórmula, os coprodutos deverão ter um preço de custo maior do que 0 (zero). O valor pode ser obtido da versão de custo ativa para ao mesmo site, ou para o primeiro site para uma fórmula não específica de site. Essa condição é validada quando a fórmula é aprovada.
-   Se você definir o controle deslizante **Alocação de Custo Total** como **Sim** para a versão da fórmula e as condições a seguir forem verdadeiras, o método de alocação de custo será **TCA** e a porcentagem de alocação de custo prevista permanecerá inalterada:
    -   Você adicionou coprodutos.
    -   Você usou um método diferente de alocação de custos para os coprodutos.
-   Se você definir o controle deslizante **Alocação de Custo Total** como **não** para a versão da fórmula e as condições a seguir forem verdadeiras, o método de alocação de custo será alterado para **Manual** e a porcentagem de alocação de custo prevista permanecerá inalterada:
    -   Você adicionou coprodutos.
    -   A porcentagem de alocação de custos é maior do que 0 (zero)
-   Antes que você possa realizar com êxito o cálculo da fórmula, você deverá estimar as porcentagens de alocação de custos. Você pode concluir esta etapa manualmente ou usando a opção **Estimar custo** na página **Coprodutos**. **Observação:** a opção **Estimar custo** só estará disponível quando a caixa de seleção **Alocação de Custo Total** for definida como **Sim** na versão da fórmula. Você pode exibir a alocação prevista se as quantidades da ordem de lote relatadas como concluídas corresponderem às quantidades que aparecem na fórmula.
-   Quando uma ordem de lotes é criada manualmente ou uma ordem de lote planejada é confirmada, o valor do controle deslizante **Alocação de Custo Total** para a versão da fórmula é copiada para a ordem de lotes. No entanto, você pode alterar essa configuração na ordem de lotes. Se o controle deslizante **Alocação Total de Custo** for definido como **Não** para a versão da fórmula e então alterado para **Sim** para a ordem de lotes, o método de alocação de custo para cada linha definido como **Manual** será alterado para **TCA**. Uma alocação de custo **Nenhuma** permanecerá inalterada. Se o controle deslizante **Alocação Total de Custo** for definido como **Sim** para a versão da fórmula e então alterado para **Não** para a ordem de lotes, o método de alocação de custo para cada coproduto do tipo **Produção** será alterado para **Manual**. Qualquer porcentagem prevista de alocação de custos permanece inalterada.
-   A página **Alocação de custo de coproduto** mostra a porcentagem calculada de alocação de custo. Você pode abrir essa página da página **Ordem de lotes**. Essas informações são úteis quando os produtos e as quantidades relatados são diferentes das quantidades agendadas ou iniciadas na ordem de lotes. Quando o custo for concluído, essas novas alocações de porcentagem de TCA serão mostradas na página **Alocação de custo de coproduto**.

## <a name="calculating-the-burden-for-byproducts"></a>Calculando a carga para byproducts
O campo **Alocação de custo de subproduto** na página **Coprodutos** é um campo enumerador usado apenas para subprodutos. Para coprodutos, o valor deste campo é sempre **Nenhum**. Para linhas de subproduto, esse campo determina como o valor de custo para a linha de subprodutos será adicionado aos custos totais de produção. As opções a seguir estão disponíveis:

-   **Nenhum**: nenhum valor é adicionado aos custos totais de produção para essa linha de subproduto.
-   **Percentual**: o valor de custo é calculado como uma porcentagem do custo total de matérias-primas que são consumidas na produção. A porcentagem usada para o cálculo é inserida no campo.
-   **Por série**: o valor de custo é calculado como um valor pelo tamanho de lote padrão da ordem de produção. Esse valor é independente da quantidade relatada na produção. O valor usado para o cálculo é inserido no campo.
-   **Por quantidade** ─ o valor de custo é calculado como um valor por quantidade relatada do item de fórmula na produção. O valor usado para o cálculo é inserido no campo.



