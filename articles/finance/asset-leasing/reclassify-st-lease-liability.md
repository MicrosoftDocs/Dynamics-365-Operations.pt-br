---
title: Reclassificar a parte de curto prazo de uma responsabilidade com arrendamento
description: Este tópico explica como criar uma entrada de diário mensal para reclassificar uma parte da responsabilidade com arrendamento como um curto prazo.
author: moaamer
ms.date: 04/12/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: Dialog
audience: Application User
ms.reviewer: kfend
ms.custom: 4464
ms.assetid: 5f89daf1-acc2-4959-b48d-91542fb6bacb
ms.search.region: Global
ms.author: moaamer
ms.search.validFrom: 2020-10-28
ms.dyn365.ops.version: 10.0.14
ms.openlocfilehash: 3a71b809b4bb16c2b918b7acd4fbb8bc49278ff6
ms.sourcegitcommit: 631d2cea52590af15f208e9af584446e85540fcf
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/07/2022
ms.locfileid: "8727724"
---
# <a name="reclassify-the-short-term-portion-of-lease-liability"></a>Reclassificar a parte de curto prazo de uma responsabilidade com arrendamento

[!include [banner](../includes/banner.md)]

Este tópico explica como criar uma entrada de diário mensal para reclassificar uma parte da responsabilidade com arrendamento como um curto prazo. Quando a agenda selecionada no processo em lote é **Reclassificação de responsabilidade com arrendamento de curto prazo**, uma entrada de diário é criada. Essa entrada é usada para lançar a parte atual da responsabilidade com arrendamento no último dia do mês. Ao mesmo tempo, uma entrada de estorno é lançada no primeiro dia do mês seguinte.

A parte de curto prazo da responsabilidade com arrendamento é mostrada no plano de amortização de passivo. Quando a entrada de diário é lançada, a coluna **Diário de reclassificação de passivos** é disponibilizada e a ID do diário também é preenchida na agenda.

Para criar e lançar a entrada do diário de reclassificação de passivos de curto prazo, siga estas etapas.

1. Acesse **Arrendamento de ativos \> Periódico \> Criação de diário em lote**.
2. Na caixa de diálogo **Criação de diário de lotes**, no campo **Selecionar agenda**, selecione **Reclassificação de responsabilidade com arrendamento de curto prazo**.
3. No campo **Grupo de arrendamento**, selecione um grupo de arrendamento. Como alternativa, no campo **ID do Registro**, selecione a ID do registro.
4. Ative o parâmetro **Lançar**. Como alternativa, se a entrada tiver de ser criada mas não lançada, deixe esse parâmetro desativado.
5. Selecione **OK**.


[!INCLUDE[footer-include](../../includes/footer-banner.md)]
