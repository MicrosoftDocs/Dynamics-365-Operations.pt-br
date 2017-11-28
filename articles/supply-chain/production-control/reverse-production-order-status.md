---
title: "Reverter status de ordem de produção"
description: "Este tópico descreve como reverter o status da ordem de produção."
author: johanhoffmann
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: ProdParmStatusDecrease
audience: Application User
ms.reviewer: bis
ms.search.scope: Core, Operations
ms.custom: 70131
ms.assetid: b1e0df43-b388-4326-8fb7-501f30c89776
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: johanho
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 2771a31b5a4d418a27de0ebe1945d1fed2d8d6d6
ms.openlocfilehash: 4761e44b6bbc93ebf4a395948f42c2a73013ecb9
ms.contentlocale: pt-br
ms.lasthandoff: 11/03/2017

---

# <a name="reverse-the-production-order-status"></a>Reverter status de ordem de produção

[!include[banner](../includes/banner.md)]


Este tópico descreve como reverter o status da ordem de produção. 

Reverter o status de uma ordem de produção leva a própria ordem, além de todas as operações associadas aos roteiros, de volta a uma etapa anterior no ciclo de vida da produção. Por exemplo, uma ordem de produção tem um status **Agendado** e você altera o status de volta para **Criado**. Neste caso, o sistema primeiro deve alterar o status para **Estimado**, que é o status que precede imediatamente o status **Agendado**. Em seguida, ele pode alterar o status para o status desejado, **Criado**. **Observação:** Se sua ordem atingiu o status **Relatar como concluído**, você ainda pode revertê-la para um status anterior. No entanto, você deve reexecutar a previsão e o agendamento de operações, o agendamento de trabalho, ou ambos, para atualizar as informações na ordem. Esta etapa é necessária porque todas as reservas do consumo de itens restantes e do consumo de recurso das operações também devem ser redefinidas. O restante deste artigo explica o que ocorre quando você reverte o status de uma ordem de produção das seguintes maneiras:

-   De **Estimado** para **Criado**
-   De **Agendado** para **Estimado**
-   De **Liberado** para **Agendado**
-   De **Iniciado** para **Liberado**

## <a name="from-estimated-to-created"></a>De Estimado para Criado
Quando você reverte o status de uma ordem de produção de **Estimado** para **Criado**, o consumo do item que foi calculado para os itens na lista de materiais (BOM) é removido. As transações do estoque na linha de produção são excluídas e o campo **Status pendente** nas linhas BOM da ordem de produção é redefinido como **Finalizado**. Quando as opções **Compras derivadas** e **Produção derivada** forem selecionadas, quaisquer ordens de compra ou ordens de produção subjacentes serão excluídas. Se você estimou os custos da ordem de produção, ou se reservou manualmente itens, de forma que eles possam ser usados na produção, essas transações são removidas.

## <a name="from-scheduled-to-estimated"></a>De Agendado para Estimado
Quando você reverte o status de uma ordem de produção de **Agendado** para **Estimado**, as datas e horas inicial e final programadas são removidas. As reservas de capacidade feitas durante o agendamento são removidas, e os trabalhos criados durante o agendamento de trabalho são excluídos. Todas as informações que são registradas no planejamento de operações e no planejamento de trabalho na página **Detalhes da ordem de produção** são redefinidas.

## <a name="from-released-to-scheduled"></a>De Liberado para Agendado
Quando você reverte o status de uma ordem de produção de **Liberado** para **Agendado**, a única alteração que ocorre é o valor do campo status.

## <a name="from-started-to-released"></a>De Iniciado para Liberado
Quando você reverte o status de uma ordem de produção de **Iniciado** para **Liberado**, todos os itens que foram reportados como concluídos são revertidos. Caso o material tenha sido separado, ou se as entregas de entrada e de saída tiverem sido feitas para a produção, essas configurações também são revertidas. O campo **Status pendente** nas linhas BOM da ordem de produção é alterado de **Finalizado** para **Consumo de material**. Se a hora foi registrada, ou se as quantidades foram relatadas como concluídas para as operações no roteiro de produção, essas configurações serão revertidas. O campo **Status pendente** é alterado de **Finalizado** para **Consumo de roteiros** na rota de produção. As configurações de todos os itens são lançadas como em andamento ou o trabalho em andamento são revertidas. Na página **Detalhes da ordem de produção**, os campos que mostram uma quantidade que foi iniciada ou reportada como finalizada são redefinidos. As datas dessas transações também são redefinidas.




