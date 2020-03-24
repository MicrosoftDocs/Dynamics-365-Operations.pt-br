---
title: Enviar uma solicitação de licença para o fluxo de trabalho
description: No Microsoft Dynamics 365 Human Resources, você pode usar a API (interface de programação de aplicativo) MyLeaveRequests submit() para enviar uma solicitação de licença para o fluxo de trabalho.
author: andreabichsel
manager: AnnBe
ms.date: 02/03/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-human-resources
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: anbichse
ms.search.scope: Human Resources
ms.custom: 7521
ms.assetid: ''
ms.search.region: Global
ms.author: anbichse
ms.search.validFrom: 2020-02-03
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: 7552a4c921dc4a88034b5d2c87d5a9b47d699ae3
ms.sourcegitcommit: f38302b9430f2ab3efe91d0a7beff946bc610e8f
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/28/2020
ms.locfileid: "3092005"
---
# <a name="submit-a-leave-request-to-workflow"></a><span data-ttu-id="81313-103">Enviar uma solicitação de licença para o fluxo de trabalho</span><span class="sxs-lookup"><span data-stu-id="81313-103">Submit a leave request to workflow</span></span>

<span data-ttu-id="81313-104">No Microsoft Dynamics 365 Human Resources, você pode usar a API (interface de programação de aplicativo) MyLeaveRequests submit() para enviar uma solicitação de licença para o fluxo de trabalho.</span><span class="sxs-lookup"><span data-stu-id="81313-104">In Microsoft Dynamics 365 Human Resources, you can use the MyLeaveRequests submit() application programming interface (API) to submit a leave request to workflow.</span></span> <span data-ttu-id="81313-105">Essa API é exposta como uma ação na entidade MyLeaveRequests OData.</span><span class="sxs-lookup"><span data-stu-id="81313-105">This API is exposed as an action on the MyLeaveRequests OData entity.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="81313-106">Pré-requisitos</span><span class="sxs-lookup"><span data-stu-id="81313-106">Prerequisites</span></span>

<span data-ttu-id="81313-107">A solicitação de licença deve ser salva no banco de dados e recuperada por meio da entidade MyLeaveRequests.</span><span class="sxs-lookup"><span data-stu-id="81313-107">The leave request must be saved in the database and must be retrievable through the MyLeaveRequests entity.</span></span>

## <a name="permissions"></a><span data-ttu-id="81313-108">Permissões</span><span class="sxs-lookup"><span data-stu-id="81313-108">Permissions</span></span>

<span data-ttu-id="81313-109">Uma das permissões a seguir é necessária para chamar essa API.</span><span class="sxs-lookup"><span data-stu-id="81313-109">One of the following permissions is required to call this API.</span></span> <span data-ttu-id="81313-110">Para obter mais informações sobre permissões como selecioná-las, consulte [Autenticação](hr-developer-api-authentication.md).</span><span class="sxs-lookup"><span data-stu-id="81313-110">For more information about permissions and how to select them, see [Authentication](hr-developer-api-authentication.md).</span></span>

| <span data-ttu-id="81313-111">Tipo de permissão</span><span class="sxs-lookup"><span data-stu-id="81313-111">Permission type</span></span>                    | <span data-ttu-id="81313-112">Permissões (de menos privilegiado ao mais privilegiado)</span><span class="sxs-lookup"><span data-stu-id="81313-112">Permissions (from least privileged to most privileged)</span></span> |
|------------------------------------|--------------------------------------------------------|
| <span data-ttu-id="81313-113">Delegada (conta corporativa ou de estudante)</span><span class="sxs-lookup"><span data-stu-id="81313-113">Delegated (work or school account)</span></span> | <span data-ttu-id="81313-114">user\_impersonation</span><span class="sxs-lookup"><span data-stu-id="81313-114">user\_impersonation</span></span>                                    |

## <a name="https-request"></a><span data-ttu-id="81313-115">Solicitação HTTPS</span><span class="sxs-lookup"><span data-stu-id="81313-115">HTTPS request</span></span>

<!-- { "blockType": "ignored" } -->
```HTTP
POST https://{cluster}.hr.talent.dynamics.com/namespaces/{namespace_guid}/data/MyLeaveRequests(RequestId='{requestId}', LeaveType='{leaveType}', LeaveDate={leaveDate}, dataAreaId={dataArea})/Microsoft.Dynamics.DataEntities.submit?cross-company=true
```

<span data-ttu-id="81313-116">A solicitação está de acordo com os padrões OData.</span><span class="sxs-lookup"><span data-stu-id="81313-116">The request conforms to OData standards.</span></span> <span data-ttu-id="81313-117">Os parâmetros {requestId}, {leaveType}, {leaveDate} e {dataArea} referem-se aos campos que constituem a chave natural composta da entidade MyLeaveRequests.</span><span class="sxs-lookup"><span data-stu-id="81313-117">The {requestId}, {leaveType}, {leaveDate}, and {dataArea} parameters refer to the fields that make up the composite natural key for the MyLeaveRequests entity.</span></span>

> [!NOTE]
> <span data-ttu-id="81313-118">Embora os campos da entidade MyLeaveRequests se refiram a uma linha individual na solicitação de licença, chamar a API de envio enviará toda a solicitação de licença (todas as linhas) para o fluxo de trabalho.</span><span class="sxs-lookup"><span data-stu-id="81313-118">While the fields for the MyLeaveRequests entity refer to an individual line in the leave request, calling the submit API will submit the entire leave request (all lines) to workflow.</span></span>

### <a name="request-headers"></a><span data-ttu-id="81313-119">Cabeçalhos de solicitação</span><span class="sxs-lookup"><span data-stu-id="81313-119">Request headers</span></span>

| <span data-ttu-id="81313-120">Cabeçalho</span><span class="sxs-lookup"><span data-stu-id="81313-120">Header</span></span>         | <span data-ttu-id="81313-121">Value</span><span class="sxs-lookup"><span data-stu-id="81313-121">Value</span></span>                     |
|----------------|---------------------------|
| <span data-ttu-id="81313-122">Autorização</span><span class="sxs-lookup"><span data-stu-id="81313-122">Authorization</span></span>  | <span data-ttu-id="81313-123">Portador {token} (obrigatório)</span><span class="sxs-lookup"><span data-stu-id="81313-123">Bearer {token} (required)</span></span> |
| <span data-ttu-id="81313-124">Tipo de Conteúdo</span><span class="sxs-lookup"><span data-stu-id="81313-124">Content-Type</span></span>   | <span data-ttu-id="81313-125">application/json</span><span class="sxs-lookup"><span data-stu-id="81313-125">application/json</span></span>          |

### <a name="request-body"></a><span data-ttu-id="81313-126">Corpo da solicitação</span><span class="sxs-lookup"><span data-stu-id="81313-126">Request body</span></span>

<span data-ttu-id="81313-127">Não forneça um corpo de solicitação para este método.</span><span class="sxs-lookup"><span data-stu-id="81313-127">Don't supply a request body for this method.</span></span>

### <a name="response"></a><span data-ttu-id="81313-128">Resposta</span><span class="sxs-lookup"><span data-stu-id="81313-128">Response</span></span>

<span data-ttu-id="81313-129">Uma resposta bem-sucedida é sempre uma resposta **204 sem conteúdo**.</span><span class="sxs-lookup"><span data-stu-id="81313-129">A successful response is always a **204 No Content** response.</span></span>

<span data-ttu-id="81313-130">Os chamadores não autorizados receberão uma resposta **401 não autorizado** ou **403 Proibido**.</span><span class="sxs-lookup"><span data-stu-id="81313-130">Unauthorized callers will receive a **401 Unauthorized** or a **403 Forbidden** response.</span></span>

<span data-ttu-id="81313-131">Se o envio não for bem-sucedido (devido à validação, por exemplo), a resposta será **500 Erro no servidor** e o corpo da resposta incluirá um objeto JSON com mais detalhes.</span><span class="sxs-lookup"><span data-stu-id="81313-131">If submission is unsuccessful (because of validation, for example), the response will be a **500 Server Error**, and the response body will include a JSON object with further details.</span></span>

## <a name="example"></a><span data-ttu-id="81313-132">Exemplo</span><span class="sxs-lookup"><span data-stu-id="81313-132">Example</span></span>

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

## <a name="validation-and-error-messages"></a><span data-ttu-id="81313-133">Validação e mensagens de erro</span><span class="sxs-lookup"><span data-stu-id="81313-133">Validation and error messages</span></span>

<span data-ttu-id="81313-134">Como parte da chamada à API de envio, o Human Resources executa a validação de lógica comercial antes do envio, o que garante o estado válido da solicitação de licença para envio.</span><span class="sxs-lookup"><span data-stu-id="81313-134">As part of the call to the submit API, Human Resources performs business logic validation before submission, which ensures the leave request is in a valid state for submission.</span></span> <span data-ttu-id="81313-135">Possíveis mensagens de erro recebidas na resposta se houver falha nas validações:</span><span class="sxs-lookup"><span data-stu-id="81313-135">The possible error messages you may receive in the response if validations fail are:</span></span>

 - <span data-ttu-id="81313-136">A solicitação deixaria o saldo "{LeaveTypeId}" abaixo do saldo mínimo permitido em {date}.</span><span class="sxs-lookup"><span data-stu-id="81313-136">The request would put the '{LeaveTypeId}' balance below the allowed minimum balance on {date}.</span></span>
 - <span data-ttu-id="81313-137">A solicitação de folga no estado concluído não pode ser enviada.</span><span class="sxs-lookup"><span data-stu-id="81313-137">Time off request in Completed state cannot be submitted.</span></span>
 - <span data-ttu-id="81313-138">Não é possível enviar ou salvar a solicitação, pois não houve alterações.</span><span class="sxs-lookup"><span data-stu-id="81313-138">Unable to submit or save request as no changes have been made.</span></span> <span data-ttu-id="81313-139">Adicione ou atualize o valor ou o tipo de licença e tente novamente.</span><span class="sxs-lookup"><span data-stu-id="81313-139">Add or update the amount or the leave type and try again.</span></span>
 - <span data-ttu-id="81313-140">A solicitação de folga inserida contém um ou mais dias com a mesma data e tipo de licença que uma solicitação pendente existente.</span><span class="sxs-lookup"><span data-stu-id="81313-140">The time off request entered contains one or more days with the same date and leave type as an existing pending request.</span></span> <span data-ttu-id="81313-141">Cancele a solicitação existente para fazer alterações.</span><span class="sxs-lookup"><span data-stu-id="81313-141">Please recall the existing request to make changes.</span></span>
 - <span data-ttu-id="81313-142">O código de motivo '{ReasonCodeId}' não se aplica a nenhum tipo de licença na solicitação.</span><span class="sxs-lookup"><span data-stu-id="81313-142">Reason code '{ReasonCodeId}' doesn't apply to any of the leave types in the request.</span></span>
 - <span data-ttu-id="81313-143">O tipo de licença '{LeaveTypeId}' requer um código de motivo.</span><span class="sxs-lookup"><span data-stu-id="81313-143">Leave type '{LeaveTypeId}' requires a reason code.</span></span> <span data-ttu-id="81313-144">Selecione o tipo e o código de motivo apropriados.</span><span class="sxs-lookup"><span data-stu-id="81313-144">Select the appropriate type and reason code.</span></span>
 - <span data-ttu-id="81313-145">A folga não foi enviada com êxito.</span><span class="sxs-lookup"><span data-stu-id="81313-145">The time off was not submitted successfully.</span></span> <span data-ttu-id="81313-146">A folga foi salva como uma solicitação de rascunho.</span><span class="sxs-lookup"><span data-stu-id="81313-146">The time off has been saved as a draft request.</span></span>

## <a name="see-also"></a><span data-ttu-id="81313-147">Consulte também</span><span class="sxs-lookup"><span data-stu-id="81313-147">See also</span></span>

- [<span data-ttu-id="81313-148">Visão geral de MyLeaveRequests</span><span class="sxs-lookup"><span data-stu-id="81313-148">MyLeaveRequests overview</span></span>](hr-developer-api-myleaverequests-overview.md)
- [<span data-ttu-id="81313-149">Autenticação</span><span class="sxs-lookup"><span data-stu-id="81313-149">Authentication</span></span>](hr-developer-api-authentication.md)