---
title: Gerenciar políticas de licença de compra e venda
description: Você pode habilitar funcionários a comprar e vender licenças no Dynamics 365 Human Resources.
author: twheeloc
ms.date: 10/28/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: LeaveBuySellPolicy, LeavePlanFormPart, LeaveAbsenceWorkspace
audience: Application User
ms.search.scope: Human Resources
ms.custom: 7521
ms.assetid: ''
ms.search.region: Global
ms.author: twheeloc
ms.search.validFrom: 2020-06-01
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: 06682a81b09f90de0ef5eb1b656338e634f229db
ms.sourcegitcommit: e91a1797192fd9bc4048b445bb5c1ad5d333d87d
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/01/2021
ms.locfileid: "7728872"
---
# <a name="manage-buy-and-sell-leave-policies"></a>Gerenciar políticas de compra e venda de licenças

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

Você pode permitir que os funcionários comprem e vendam licenças criando uma política de licença de compra e venda. Você pode configurar essas políticas para usar o fluxo de trabalho para aprovações, definir valores e taxas máximos e definir taxas para compras e vendas. 

## <a name="enable-employees-to-buy-and-sell-leave"></a>Habilitar funcionários a comprar e vender licenças

1. Na página **Parâmetros de licença e ausência**, selecione **Sim** para **Permitir que os funcionários comprem licenças** e **Permitir que os funcionários vendam licenças**.

## <a name="create-a-buy-and-sell-leave-policy"></a>Criar uma política de compra e venda de licenças

1. Na página **Licença e ausência**, selecione a guia **Links**. 

2. Selecione a **Política de licença de compra e venda**.

3. Selecione **Novo**.

4. Insira um **Nome** e uma **Descrição** para a política em **Política de licença de compra e venda**. 

5. Selecione um **Tipo de política**. 

   Os tipos de política disponíveis são **Valor** e **Horas por semana**. Selecione **Valor** para inserir um **Valor fixo** para os valores máximos que os funcionários podem comprar e vender. Se você selecionar **Horas por semana**, o período de trabalho definido no calendário de horário de trabalho atribuído do funcionário será usado para determinar o valor máximo da política. 

6. Selecione uma **Data inicial** e uma **Data final** para a política. As solicitações para comprar ou vender licenças só estarão disponíveis para envio durante esse período. 

7. Selecione uma **ID de fluxo de trabalho** para a política. As solicitações de compra e venda usarão este fluxo de trabalho para revisão e aprovação. 

8. Em **Política de compra**, selecione **Equivalência de tempo integral** (FTE) para rateio do valor máximo com base no FTE definido na posição do funcionário. Se o tipo de política for **Valor**, insira um **Valor fixo máximo**. 

9. Selecione **Adicionar** para adicionar os tipos de licença para funcionários comprarem licenças. Você pode adicionar vários tipos de licença à política. 

10. Insira os **Meses de serviço** do tipo de licença para habilitar diferentes meses de serviço para determinar o valor máximo que um funcionário pode comprar. 

11. Insira o **Valor máximo** para o tipo de licença. 

12. Insira a **Taxa** na qual o funcionário comprará a licença. 

13. Opcionalmente, insira o **Código de ganhos** a ser usado para comprar a licença. 

14. Opcionalmente, defina se o FTE deve ser usado para determinar o valor máximo para o tipo de licença. 

15. Para criar uma política de venda, siga as etapas 8 a 14 na **Política de venda**. 

## <a name="add-the-buy-and-sell-leave-policy-to-a-leave-and-absence-plan"></a>Adicionar a política de licença de compra e venda a um plano de licença e ausência

1. Na página **Licença e ausência**, selecione um plano de licença e ausência.

2. Em **Regras**, selecione a **Política de licença de compra e venda**.

## <a name="see-also"></a>Consulte também

[Visão geral de licença e ausência](hr-leave-and-absence-overview.md)</br>
[Configurar tipos de licença e ausência](hr-leave-and-absence-types.md)</br>
[Acumular planos de licença e ausência](hr-leave-and-absence-accrue.md)</br>
[Comprar e vender licenças](hr-employee-self-service-buy-sell-leave.md)



[!INCLUDE[footer-include](../includes/footer-banner.md)]
