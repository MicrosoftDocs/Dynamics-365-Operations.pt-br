---
title: Criar orçamentos de manutenção
description: Este tópico explica como criar um orçamento de manutenção em Gerenciamento de Ativos.
author: josaw1
manager: tfehr
ms.date: 08/13/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: EntAssetBudgetLineAdjust, EntAssetBudget, EntAssetBudgetRecalc, EntAssetBudgetCopy, EntAssetBudgetLine, EntAssetBudgetCreate, EntAssetBudgetApprove, EntAssetBudgetCalculateActualCost
audience: Application User
ms.reviewer: kamaybac
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: riluan
ms.search.validFrom: 2019-08-30
ms.dyn365.ops.version: 10.0.5
ms.openlocfilehash: 602a00060c1e56285d9954981d019bececaf90fd
ms.sourcegitcommit: deac22ba5377a912d93fe408c5ae875706378c2d
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/16/2021
ms.locfileid: "5020980"
---
# <a name="create-maintenance-budgets"></a>Criar orçamentos de manutenção

[!include [banner](../../includes/banner.md)]

 



Os orçamentos de manutenção são usados para fornecer uma visão geral dos custos esperados para manutenção preventiva. As linhas de orçamento são calculadas com base nas linhas de agendamento de manutenção que têm uma data de início prevista durante o período do orçamento.

Os orçamentos de manutenção são baseados nos tipos de custo usados no Gerenciamento de Ativos: **Preventivo**, **Corretivo** e **Investimento**. Os custos do orçamento para manutenção do investimento são incluídos para ativos que têm uma data de substituição durante o período do orçamento e um valor de substituição relacionado. Os custos do orçamento para manutenção corretiva serão incluídos se uma data corretiva anterior for incluída no cálculo do orçamento. Nesse caso, os custos corretivos de um período anterior são calculados para o mesmo período futuro para o qual você calcula o orçamento de manutenção.

## <a name="create-a-maintenance-budget"></a>Criar um orçamento de manutenção

1. Selecione **Gerenciamento de ativos** \> **Consultas** \> **Orçamentos de manutenção** \> **Orçamento**.
2. Selecione **Criar orçamento**.
3. No campo **Orçamento de manutenção**, insira uma ID de orçamento.
4. No campo **Descrição**, insira uma descrição.
4. Na Guia Rápida **Período**, nos campos **Data inicial** e **Data final**, insira as datas de início e término do período do orçamento.
5. Para incluir custos orçamentários corretivos que são calculados com base nos custos reais de um período anterior, no campo **Data inicial corretiva**, insira a data de início do período em que esses custos devem ser incluídos.
6. Dependendo do nível de detalhes necessário no orçamento, defina as opções relevantes nas cinco Guias Rápidas **Agrupar por**.
7. Selecione **OK**.
8. Selecione **Linhas de orçamento** para abrir a página **Linhas de orçamento de manutenção**, onde você pode exibir todas as linhas de orçamento que foram criadas para o período.
9. Para aprovar o orçamento, selecione-o na página **Orçamentos de manutenção** e selecione **Aprovar**. Em seguida, na caixa de diálogo **Aprovar orçamento**, selecione **OK**. Seu nome é inserido no campo **Aprovado por** na página **Orçamentos de manutenção**.

    > [!NOTE]
    > Depois de aprovar um orçamento de manutenção, você não poderá recalcular ou ajustar as linhas relacionadas na página **Linhas de orçamento de manutenção**, a menos que primeiro remova a aprovação. Para remover a aprovação de um orçamento de manutenção, selecione-o na página **Orçamentos de manutenção** e selecione **Aprovar**. Em seguida, na caixa de diálogo **Aprovar orçamento**, selecione **OK**.

![Orçamentos de Manutenção](media/01-maintenance-budgets.png)

Também é possível criar um orçamento de manutenção, copiando um orçamento existente. Na página **Orçamentos de manutenção**, selecione o orçamento a ser copiado e selecione **Copiar**. Essa abordagem é útil se, por exemplo, você criou um orçamento para um mês e deseja copiá-lo para outros meses.

> [!NOTE]
> O orçamento de manutenção calcula apenas os custos com base nas linhas de agendamento de manutenção. Para calcular custos reais para o mesmo período, você pode fazer esse cálculo na página **Controle de custos de ativos**. 


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]