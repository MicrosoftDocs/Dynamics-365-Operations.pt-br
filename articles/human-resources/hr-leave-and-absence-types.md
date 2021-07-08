---
title: Configurar tipos de licença e ausência
description: Configurar tipos de licença que os funcionários podem executar no Dynamics 365 Human Resources.
author: andreabichsel
ms.date: 06/15/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: LeavePlanFormPart, LeaveAbsenceWorkspace
audience: Application User
ms.search.scope: Human Resources
ms.custom: 7521
ms.assetid: ''
ms.search.region: Global
ms.author: anbichse
ms.search.validFrom: 2020-02-03
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: 39e4c4b9c83ca648c21ac20bd20b739af8a6b9ed
ms.sourcegitcommit: dc4898aa32f381620c517bf89c7856e693563ace
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/17/2021
ms.locfileid: "6271118"
---
# <a name="configure-leave-and-absence-types"></a>Configurar tipos de licença e ausência

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

Os tipos de licenças no Dynamics 365 Human Resources definem os tipos de ausências que os funcionários podem relatar. Você pode personalizar os tipos de licença de acordo com as necessidades da sua organização. Exemplos de tipos de licença incluem:

- Folga remunerada (PTO)
- Licença não remunerada
- Férias remuneradas
- Ausência por motivo de doença
- Licença médica
- Licença de família
- Incapacidade temporária
- Licença óbito

## <a name="add-a-leave-type"></a>Adicionar um tipo de licença

1. Na página **Licença e ausência**, selecione a guia **Links**.

2. Em **Configuração**, selecione **Tipos de licença e ausência**.

3. Selecione **Novo**.

4. Digite um nome para o tipo de licença em **Tipo**, selecione um fluxo de trabalho em **ID do fluxo de trabalho** e digite uma descrição em **Descrição**.

5. Em **Geral**, selecione **Nenhum**, **Agendado** ou **Não agendado** no menu suspenso **Categoria**.

6. Selecione um código de ganhos no menu suspenso **Código de ganhos**.

7. Em **Código de motivo obrigatório**, escolha se deseja exigir um código de motivo. Se desejar exigir códigos de motivo, talvez seja necessário adicioná-los. Em **Códigos de motivo**, selecione **Adicionar**, selecione um código de motivo e marque a caixa de seleção **Habilitado** ao lado dele.

8. Em **Restringir acesso a funções selecionadas**, escolha se deseja restringir o acesso. Em seguida, selecione as funções de segurança em **Funções de segurança para este tipo de licença**. As funções de segurança são definidas no fluxo de trabalho selecionado em **ID do fluxo de trabalho**, que vimos antes neste procedimento.

9. Em **Cor do calendário**, escolha a cor a ser exibida nos calendários de licença e ausência desse tipo de licença. 

10. Em **Relações de suspensão**, escolha se você deseja que esse tipo de licença suspenda outro tipo de licença ou seja suspenso por outro tipo de licença. Quando uma solicitação de licença for enviada para o tipo de licença de suspensão, uma suspensão de licença será automaticamente criada para o tipo de licença suspensa. 

10. Selecione **Salvar**.

## <a name="configure-leave-type-rules"></a>Configurar regras de tipo de licença

1. Defina as opções de arredondamento para o tipo de licença. As opções incluem **Nenhum**, **Para cima**, **Para baixo** e **Mais próximo**. Você também pode definir a precisão de arredondamento para o tipo de licença.

2. Defina a **Correção de feriado** para o tipo de licença. Quando você seleciona esta opção, o Human Resources usa o número de feriados que caem em um dia útil para determinar como acumular folgas para o tipo de licença. Por exemplo, se o dia de Natal cair na segunda-feira, o Human Resources subtrairá um dia do tipo de licença ao processar competências.

   Você pode definir feriados no calendário de horário de trabalho. Para obter mais informações, consulte [Criar um calendário de horário de trabalho](hr-leave-and-absence-working-time-calendar.md)
   
 3. Defina **Postergar tipo de licença** para o tipo de licença. Quando você selecionar esta opção, qualquer saldo de postergação será transferido para o tipo de licença especificado. O tipo de licença de postergação também precisa ser incluído no plano de licença e ausência. 
 
4. Defina **Regras de expiração** para o tipo de licença. Ao configurar esta opção, você pode escolher a unidade de dias ou meses e definir a duração do vencimento. A data de efetivação é usada para determinar quando começar a executar o trabalho em lotes que processa a expiração da licença ou a data em que a regra entra em vigor. O vencimento em si sempre ocorrerá na data de início do período de acréscimo. Por exemplo, se a data de início do período de acréscimo for 3 de agosto de 2021, e a regra de vencimento for definida como 6 meses, a regra será processada com base no vencimento compensado a partir da data de início do período de acréscimo, de modo que seria executado em 3 de fevereiro de 2022. Os saldos de licença existentes no momento da expiração serão subtraídos do tipo de licença e serão refletidos no saldo de licença.
 
## <a name="see-also"></a>Consulte também

- [Visão geral de licença e ausência](hr-leave-and-absence-overview.md)
- [Criar um plano de licença e ausência](hr-leave-and-absence-plans.md)
- [Criar um calendário de horas úteis](hr-leave-and-absence-working-time-calendar.md)
- [Suspender licença](hr-leave-and-absence-suspend-leave.md)
- [Criar um fluxo de trabalho de solicitação de compra e venda de licenças](hr-leave-and-absence-buy-sell-workflow.md)



[!INCLUDE[footer-include](../includes/footer-banner.md)]
