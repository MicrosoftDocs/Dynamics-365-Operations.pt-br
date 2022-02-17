---
title: Enviar uma solicitação de licença para o fluxo de trabalho
description: No Microsoft Dynamics 365 Human Resources, você pode usar a API (interface de programação de aplicativo) MyLeaveRequests submit() para enviar uma solicitação de licença para o fluxo de trabalho.
author: andreabichsel
ms.date: 02/03/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.search.scope: Human Resources
ms.custom: 7521
ms.assetid: ''
ms.search.region: Global
ms.author: anbichse
ms.search.validFrom: 2020-02-03
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: f9ca716f37b90e22983b2dddc2c426a2b4e251ec
ms.sourcegitcommit: 3a7f1fe72ac08e62dda1045e0fb97f7174b69a25
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/31/2022
ms.locfileid: "8067495"
---
# <a name="submit-a-leave-request-to-workflow"></a>Enviar uma solicitação de licença para o fluxo de trabalho


[!INCLUDE [PEAP](../includes/peap-1.md)]

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

No Microsoft Dynamics 365 Human Resources, você pode usar a API (interface de programação de aplicativo) MyLeaveRequests submit() para enviar uma solicitação de licença para o fluxo de trabalho. Essa API é exposta como uma ação na entidade MyLeaveRequests OData.

## <a name="prerequisites"></a>Pré-requisitos

A solicitação de licença deve ser salva no banco de dados e recuperada por meio da entidade MyLeaveRequests.

## <a name="permissions"></a>Permissões

Uma das permissões a seguir é necessária para chamar essa API. Para obter mais informações sobre permissões como selecioná-las, consulte [Autenticação](hr-developer-api-authentication.md).

| Tipo de permissão                    | Permissões (de menos privilegiado ao mais privilegiado) |
|------------------------------------|--------------------------------------------------------|
| Delegada (conta corporativa ou de estudante) | user\_impersonation                                    |

## <a name="https-request"></a>Solicitação HTTPS

<!-- { "blockType": "ignored" } -->
```HTTP
POST https://{cluster}.hr.talent.dynamics.com/namespaces/{namespace_guid}/data/MyLeaveRequests(RequestId='{requestId}', LeaveType='{leaveType}', LeaveDate={leaveDate}, dataAreaId={dataArea})/Microsoft.Dynamics.DataEntities.submit?cross-company=true
```

A solicitação está de acordo com os padrões OData. Os parâmetros {requestId}, {leaveType}, {leaveDate} e {dataArea} referem-se aos campos que constituem a chave natural composta da entidade MyLeaveRequests.

> [!NOTE]
> Embora os campos da entidade MyLeaveRequests se refiram a uma linha individual na solicitação de licença, chamar a API de envio enviará toda a solicitação de licença (todas as linhas) para o fluxo de trabalho.

### <a name="request-headers"></a>Cabeçalhos de solicitação

| Cabeçalho         | Value                     |
|----------------|---------------------------|
| Autorização  | Portador {token} (obrigatório) |
| Tipo de Conteúdo   | application/json          |

### <a name="request-body"></a>Corpo da solicitação

Não forneça um corpo de solicitação para este método.

### <a name="response"></a>Resposta

Uma resposta bem-sucedida é sempre uma resposta **204 sem conteúdo**.

Os chamadores não autorizados receberão uma resposta **401 não autorizado** ou **403 Proibido**.

Se o envio não for bem-sucedido (devido à validação, por exemplo), a resposta será **500 Erro no servidor** e o corpo da resposta incluirá um objeto JSON com mais detalhes.

## <a name="example"></a>Exemplo

```http
POST https://aos-rts-sf-550e5c091f6-prod-westus2.hr.talent.dynamics.com/namespaces/b2eb8003-334f-4a84-ab63-edbe23569090/data/MyLeaveRequests(RequestId='USMF-000065', LeaveType='Vacation', LeaveDate=2019-10-04T12:00:00Z, dataAreaId='USMF')/Microsoft.Dynamics.DataEntities.submit
```

```json
{
  "error": {
    "code": "",
    "message": "An error has occurred.",
    "innererror": {
      "message": "Exception occurred while executing action submit on Entity MyLeaveRequest: The request would put the 'Vacation' balance below the allowed minimum balance on 9/10/2019.",
      "type": "System.InvalidOperationException",
      "stacktrace": "   at Microsoft.Dynamics.Platform.Integration.Services.OData.Action.ActionInvokable.Invoke()   at Microsoft.Dynamics.Platform.Integration.Services.OData.Update.UpdateProcessor.ActionInvocation(ChangeOperationContext context, ActionInvokable action)   at Microsoft.Dynamics.Platform.Integration.Services.OData.Update.UpdateManager.<>c__DisplayClass13_0.<ScheduleInvokable>b__0(ChangeOperationContext context)   at Microsoft.Dynamics.Platform.Integration.Services.OData.Update.ChangeInfo.ExecuteActionsInCompanyContext(IEnumerable`1 actionList, ChangeOperationContext operationContext)\r\n   at Microsoft.Dynamics.Platform.Integration.Services.OData.Update.ChangeInfo.ExecuteActions(ChangeOperationContext context)   at Microsoft.Dynamics.Platform.Integration.Services.OData.Update.UpdateManager.SaveChanges()   at Microsoft.Dynamics.Platform.Integration.Services.OData.AxODataDelegatingHandler.<SaveChangesAsync>d__3.MoveNext()"
    }
  }
}
```

## <a name="validation-and-error-messages"></a>Validação e mensagens de erro

Como parte da chamada à API de envio, o Human Resources executa a validação de lógica comercial antes do envio, o que garante o estado válido da solicitação de licença para envio. Possíveis mensagens de erro recebidas na resposta se houver falha nas validações:

 - A solicitação deixaria o saldo "{LeaveTypeId}" abaixo do saldo mínimo permitido em {date}.
 - A solicitação de folga no estado concluído não pode ser enviada.
 - Não é possível enviar ou salvar a solicitação, pois não houve alterações. Adicione ou atualize o valor ou o tipo de licença e tente novamente.
 - A solicitação de folga inserida contém um ou mais dias com a mesma data e tipo de licença que uma solicitação pendente existente. Cancele a solicitação existente para fazer alterações.
 - O código de motivo '{ReasonCodeId}' não se aplica a nenhum tipo de licença na solicitação.
 - O tipo de licença '{LeaveTypeId}' requer um código de motivo. Selecione o tipo e o código de motivo apropriados.
 - A folga não foi enviada com êxito. A folga foi salva como uma solicitação de rascunho.

## <a name="see-also"></a>Consulte também

- [Visão geral de MyLeaveRequests](hr-developer-api-myleaverequests-overview.md)
- [Autenticação](hr-developer-api-authentication.md)

[!INCLUDE[footer-include](../includes/footer-banner.md)]
