---
title: Suspender licença
description: Você pode suspender uma licença de um funcionário no Dynamics 365 Human Resources.
author: twheeloc
ms.date: 11/21/2022
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: SuspendLeave, LeavePlanFormPart, LeaveAbsenceWorkspace
audience: Application User
ms.custom: 7521
ms.assetid: ''
ms.search.region: Global
ms.author: twheeloc
ms.search.validFrom: 2020-04-01
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: 9c8262fb34175f6f9326d6be82c922b2170fc5a7
ms.sourcegitcommit: e88ecaccd82afa3a915e41df1d4287d99da6a48a
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/29/2022
ms.locfileid: "9805251"
---
# <a name="suspend-leave"></a>Suspender licença

>[!Important]
>A funcionalidade mencionada neste artigo está disponível atualmente para clientes individuais de Dynamics 365 Human Resources. Algumas ou todas as funcionalidades estarão disponíveis como parte de uma versão futura na infraestrutura do Finance após a versão Finance 10.0.26.

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

Você pode suspender uma licença de um funcionário para evitar o acúmulo de licenças processadas para tipos de licença selecionados.

## <a name="suspend-leave-and-absence-for-an-employee"></a>Suspender licenças e ausências de um funcionário

1. No registro do funcionário, selecione **Licença**.

2. Selecione **Suspender licença**.

3. Selecione **Novo**.

4. Na caixa de diálogo **Suspender acúmulo de licença**, selecione o **Tipo de licença** juntamente com a **Data de início** e **Data de término** para a suspensão.

5. Opcionalmente, você pode adicionar um **Comentário** para a suspensão. 

Se as competências forem processadas enquanto a licença do funcionário estiver suspensa, nenhuma competência será feita para os tipos de licença suspenso.

> [!NOTE]
> As solicitações de licença suspenderão solicitações de folga, mas as solicitações de folga não suspenderão as solicitações de ausência.

## <a name="see-also"></a>Consulte também

- [Visão geral de licença e ausência](hr-leave-and-absence-overview.md)
- [Configurar tipos de licença e ausência](hr-leave-and-absence-types.md)
- [Acumular planos de licença e ausência](hr-leave-and-absence-accrue.md)



[!INCLUDE[footer-include](../includes/footer-banner.md)]
