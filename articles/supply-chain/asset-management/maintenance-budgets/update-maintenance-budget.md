---
title: Atualizar orçamentos de manutenção
description: Este tópico explica como atualizar um orçamento de manutenção em Gerenciamento de Ativos.
author: josaw1
manager: AnnBe
ms.date: 08/13/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: CatProcureCatalogEdit, CatProcureCatalogListPage
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: mkirknel
ms.search.validFrom: 2019-08-30
ms.dyn365.ops.version: 10.0.5
ms.openlocfilehash: 486782968816cc585d9cf2d753f32e82f85e4f7e
ms.sourcegitcommit: 802dbf0a744d70f9e546632d419415b0993331ab
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/13/2019
ms.locfileid: "1874776"
---
# <a name="update-maintenance-budgets"></a>Atualizar orçamentos de manutenção

[!include [banner](../../includes/banner.md)]

[!include [banner](../../includes/preview-banner.md)]

A página **Linhas de orçamento de manutenção** exibe todas as linhas de orçamento que foram criadas para o orçamento selecionado na página **Orçamentos de manutenção**. (Para obter mais informações, consulte [Criar orçamentos de manutenção](create-maintenance-budget.md).) Você pode calcular novamente e ajudar linhas de orçamento de manutenção até que o orçamento de manutenção seja aprovado. Depois de o período de orçamento ter passado e custos tiverem sido lançados no Gerenciamento de Ativos, você também pode atualizar as linhas de orçamento com custos reais.

## <a name="recalculate-a-maintenance-budget"></a>Calcular novamente um orçamento de manutenção

Você pode recalcular um orçamento de manutenção na página **Linhas de orçamento de manutenção**. Quando você recalcula um orçamento de manutenção, as linhas de orçamento existentes são excluídas e um novo cálculo é realizado.

1. Na página **Linhas de orçamento de manutenção**, selecione **Recalcular**.
2. Na caixa de diálogo **Recalcular orçamento**, faça as alterações necessárias para o novo cálculo e selecione **OK**.

As novas linhas de orçamento são criadas conforme os valores definidos.

## <a name="adjust-budget-lines"></a>Ajustar linhas de orçamento

Em vez de recalcular o orçamento de manutenção completo, você pode ajustar as linhas selecionadas que são relacionadas a custos de orçamento.

1. Na página **Linhas de orçamento de manutenção**, selecione as linhas para atualizar o custo de orçamento.
2. Selecione **Ajustar**.
3. Para adicionar um valor nas linhas selecionadas, marque a caixa de seleção **Adicionar custos**, e insira o valor no campo **Adicionar o valor**.
4. Para multiplicar os custos de orçamento nas linhas de orçamento selecionado por um fator, marque a caixa de seleção **Multiplicar custo**, e insira o fator no campo **Multiplicar valor**.

    Por exemplo, se você insere **1,2** no campo **Multiplicar valor**, você aumenta o custo de orçamento nas linhas selecionadas em 20%. Se inserir **0,7**, você reduz os custos de orçamento nas linhas selecionadas em 30%.

5. Selecione **OK**.

As linhas de orçamento selecionadas são atualizadas de acordo com os valores definidos na etapa 3 ou 4.

## <a name="update-actual-costs"></a>Atualizar custos reais

Depois das datas nas linhas de orçamento terem passado e custos reais tiverem sido lançados no Gerenciamento de ativo, você pode atualizar os custos reais no orçamento de manutenção.

1. Na página **Linhas de orçamento de manutenção**, selecione **Atualizar custo**.
2. Na caixa diálogo **Calcular custos reais**, selecione **OK**.

Os campos **Custos reais** nas linhas de orçamento serão atualizados se os custos reais forem lançados. As novas linhas de orçamento podem ser geradas se novos tipos de ativo forem criados, já que você criou o orçamento, e se esses tipos de ativo foram usados nos ativos para as quais as ordens de serviço foram criadas e custos relacionados para os quais foram postados. As novas linhas de orçamento só mostram custos reais, pois nenhum custo de orçamento é calculado para eles.

> [!NOTE]
> Para ver uma visão geral dos custos reais divididos em preventivo, custos corretivos e de investimento, você pode criar um cálculo para o mesmo período na página **Controle de custo de ativo**. 

## <a name="manually-add-budget-lines"></a>Adicionar linhas de orçamento manualmente

Na página **Linhas de orçamento de serviço**, você poderá adicionar manualmente uma nova linha de orçamento selecionando **Novo** e escolhendo seleções na linha. Veja alguns exemplos das situações onde essa abordagem pode ser útil:

- Você sabe que a restauração de alguns ativos está atualmente na fase de planejamento, mas trabalhos relacionados não foram criados no Gerenciamento de ativos. Entretanto, você deseja que custos de orçamento para esses trabalhos sejam incluídos no orçamento de manutenção.
- Novos ativos ou tipos de ativos foram criados já que você realizou o orçamento de manutenção, mas planos de manutenção não foram configurados para esses ativos ou tipos de ativos. Entretanto, você deseja que custos de orçamento para esses tipos de ativos sejam incluídos no orçamento de manutenção.
