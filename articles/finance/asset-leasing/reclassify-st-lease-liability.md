---
title: Reclassificar a parte de curto prazo de uma responsabilidade com arrendamento
description: Este tópico explica como criar uma entrada de diário mensal para reclassificar uma parte da responsabilidade com arrendamento como um curto prazo.
author: moaamer
manager: Ann Beebe
ms.date: 10/28/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: roschlom
ms.custom: 4464
ms.assetid: 5f89daf1-acc2-4959-b48d-91542fb6bacb
ms.search.region: Global
ms.author: moaamer
ms.search.validFrom: 2020-10-28
ms.dyn365.ops.version: 10.0.14
ms.openlocfilehash: 08ca824bb4c4a02a80f2187fb5f8fe4e8b7327c9
ms.sourcegitcommit: 38d40c331c8894acb7b119c5073e3088b54776c1
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/15/2021
ms.locfileid: "4992905"
---
# <a name="reclassify-the-short-term-portion-of-lease-liability"></a>Reclassificar a parte de curto prazo de uma responsabilidade com arrendamento

[!include [banner](../includes/banner.md)]

Este tópico explica como criar uma entrada de diário mensal para reclassificar uma parte da responsabilidade com arrendamento como um curto prazo. Quando a agenda selecionada no processo em lote é **Reclassificação de responsabilidade com arrendamento de curto prazo**, uma entrada de diário é criada. Essa entrada é usada para lançar a parte atual da responsabilidade com arrendamento no último dia do mês. Ao mesmo tempo, uma entrada de estorno é lançada no primeiro dia do mês seguinte.

A parte de curto prazo da responsabilidade com arrendamento é mostrada no plano de amortização de passivo. Quando a entrada de diário é lançada, a coluna **Diário de reclassificação de passivos** é disponibilizada e a ID do diário também é preenchida na agenda.

Para criar e lançar a entrada do diário de reclassificação de passivos de curto prazo, siga estas etapas.

1. Vá para **Arrendamento de ativos \> Periódico \> Criação de diário em lote**.
2. Na caixa de diálogo **Criação de diário de lotes**, no campo **Selecionar agenda**, selecione **Reclassificação de responsabilidade com arrendamento de curto prazo**.
3. No campo **Grupo de arrendamento**, selecione um grupo de arrendamento. Como alternativa, no campo **ID do Registro**, selecione a ID do registro.
4. Ative o parâmetro **Lançar**. Como alternativa, se a entrada tiver de ser criada mas não lançada, deixe esse parâmetro desativado.
5. Ative o parâmetro **Visualizar antes do lançamento** para exibir a entrada antes que ela seja lançada.
6. Selecione **OK**.
