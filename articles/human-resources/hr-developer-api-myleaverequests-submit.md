---
title: Enviar uma solicitação de licença para o fluxo de trabalho
description: ''
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
ms.openlocfilehash: 008ee231ca9f0459e332b17cea9f2a3f3e3cc2a5
ms.sourcegitcommit: 40163705a134c9874fd33be80c7ae59ccce22c21
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/03/2020
ms.locfileid: "3008138"
---
# <a name="submit-a-leave-request-to-workflow"></a><span data-ttu-id="3fbd0-102">Enviar uma solicitação de licença para o fluxo de trabalho</span><span class="sxs-lookup"><span data-stu-id="3fbd0-102">Submit a leave request to workflow</span></span>

<span data-ttu-id="3fbd0-103">No Microsoft Dynamics 365 Human Resources, você pode usar a API (interface de programação de aplicativo) MyLeaveRequests submit() para enviar uma solicitação de licença para o fluxo de trabalho.</span><span class="sxs-lookup"><span data-stu-id="3fbd0-103">In Microsoft Dynamics 365 Human Resources, you can use the MyLeaveRequests submit() application programming interface (API) to submit a leave request to workflow.</span></span> <span data-ttu-id="3fbd0-104">Essa API é exposta como uma ação na entidade MyLeaveRequests OData.</span><span class="sxs-lookup"><span data-stu-id="3fbd0-104">This API is exposed as an action on the MyLeaveRequests OData entity.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="3fbd0-105">Pré-requisitos</span><span class="sxs-lookup"><span data-stu-id="3fbd0-105">Prerequisites</span></span>

<span data-ttu-id="3fbd0-106">A solicitação de licença deve ser salva no banco de dados e recuperada por meio da entidade MyLeaveRequests.</span><span class="sxs-lookup"><span data-stu-id="3fbd0-106">The leave request must be saved in the database and must be retrievable through the MyLeaveRequests entity.</span></span>

## <a name="permissions"></a><span data-ttu-id="3fbd0-107">Permissões</span><span class="sxs-lookup"><span data-stu-id="3fbd0-107">Permissions</span></span>

<span data-ttu-id="3fbd0-108">Uma das permissões a seguir é necessária para chamar essa API.</span><span class="sxs-lookup"><span data-stu-id="3fbd0-108">One of the following permissions is required to call this API.</span></span> <span data-ttu-id="3fbd0-109">Para obter mais informações sobre permissões como selecioná-las, consulte [Autenticação](hr-developer-api-authentication.md).</span><span class="sxs-lookup"><span data-stu-id="3fbd0-109">For more information about permissions and how to select them, see [Authentication](hr-developer-api-authentication.md).</span></span>

| <span data-ttu-id="3fbd0-110">Tipo de permissão</span><span class="sxs-lookup"><span data-stu-id="3fbd0-110">Permission type</span></span>                    | <span data-ttu-id="3fbd0-111">Permissões (de menos privilegiado ao mais privilegiado)</span><span class="sxs-lookup"><span data-stu-id="3fbd0-111">Permissions (from least privileged to most privileged)</span></span> |
|------------------------------------|--------------------------------------------------------|
| <span data-ttu-id="3fbd0-112">Delegada (conta corporativa ou de estudante)</span><span class="sxs-lookup"><span data-stu-id="3fbd0-112">Delegated (work or school account)</span></span> | <span data-ttu-id="3fbd0-113">user\_impersonation</span><span class="sxs-lookup"><span data-stu-id="3fbd0-113">user\_impersonation</span></span>                                    |

## <a name="https-request"></a><span data-ttu-id="3fbd0-114">Solicitação HTTPS</span><span class="sxs-lookup"><span data-stu-id="3fbd0-114">HTTPS request</span></span>

<!-- { "blockType": "ignored" } -->
```HTTP
POST https://{cluster}.hr.talent.dynamics.com/namespaces/{namespace_guid}/data/MyLeaveRequests(RequestId='{requestId}', LeaveType='{leaveType}', LeaveDate={leaveDate}, dataAreaId={dataArea})/Microsoft.Dynamics.DataEntities.submit?cross-company=true
```

<span data-ttu-id="3fbd0-115">A solicitação está de acordo com os padrões OData.</span><span class="sxs-lookup"><span data-stu-id="3fbd0-115">The request conforms to OData standards.</span></span> <span data-ttu-id="3fbd0-116">Os parâmetros {requestId}, {leaveType}, {leaveDate} e {dataArea} referem-se aos campos que constituem a chave natural composta da entidade MyLeaveRequests.</span><span class="sxs-lookup"><span data-stu-id="3fbd0-116">The {requestId}, {leaveType}, {leaveDate}, and {dataArea} parameters refer to the fields that make up the composite natural key for the MyLeaveRequests entity.</span></span>

> [!NOTE]
> <span data-ttu-id="3fbd0-117">Embora os campos da entidade MyLeaveRequests se refiram a uma linha individual na solicitação de licença, chamar a API de envio enviará toda a solicitação de licença (todas as linhas) para o fluxo de trabalho.</span><span class="sxs-lookup"><span data-stu-id="3fbd0-117">While the fields for the MyLeaveRequests entity refer to an individual line in the leave request, calling the submit API will submit the entire leave request (all lines) to workflow.</span></span>

### <a name="request-headers"></a><span data-ttu-id="3fbd0-118">Cabeçalhos de solicitação</span><span class="sxs-lookup"><span data-stu-id="3fbd0-118">Request headers</span></span>

| <span data-ttu-id="3fbd0-119">Cabeçalho</span><span class="sxs-lookup"><span data-stu-id="3fbd0-119">Header</span></span>         | <span data-ttu-id="3fbd0-120">Value</span><span class="sxs-lookup"><span data-stu-id="3fbd0-120">Value</span></span>                     |
|----------------|---------------------------|
| <span data-ttu-id="3fbd0-121">Autorização</span><span class="sxs-lookup"><span data-stu-id="3fbd0-121">Authorization</span></span>  | <span data-ttu-id="3fbd0-122">Portador {token} (obrigatório)</span><span class="sxs-lookup"><span data-stu-id="3fbd0-122">Bearer {token} (required)</span></span> |
| <span data-ttu-id="3fbd0-123">Tipo de Conteúdo</span><span class="sxs-lookup"><span data-stu-id="3fbd0-123">Content-Type</span></span>   | <span data-ttu-id="3fbd0-124">application/json</span><span class="sxs-lookup"><span data-stu-id="3fbd0-124">application/json</span></span>          |

### <a name="request-body"></a><span data-ttu-id="3fbd0-125">Corpo da solicitação</span><span class="sxs-lookup"><span data-stu-id="3fbd0-125">Request body</span></span>

<span data-ttu-id="3fbd0-126">Não forneça um corpo de solicitação para este método.</span><span class="sxs-lookup"><span data-stu-id="3fbd0-126">Don't supply a request body for this method.</span></span>

### <a name="response"></a><span data-ttu-id="3fbd0-127">Resposta</span><span class="sxs-lookup"><span data-stu-id="3fbd0-127">Response</span></span>

<span data-ttu-id="3fbd0-128">Uma resposta bem-sucedida é sempre uma resposta **204 sem conteúdo**.</span><span class="sxs-lookup"><span data-stu-id="3fbd0-128">A successful response is always a **204 No Content** response.</span></span>

<span data-ttu-id="3fbd0-129">Os chamadores não autorizados receberão uma resposta **401 não autorizado** ou **403 Proibido**.</span><span class="sxs-lookup"><span data-stu-id="3fbd0-129">Unauthorized callers will receive a **401 Unauthorized** or a **403 Forbidden** response.</span></span>

<span data-ttu-id="3fbd0-130">Se o envio não for bem-sucedido (devido à validação, por exemplo), a resposta será **500 Erro no servidor** e o corpo da resposta incluirá um objeto JSON com mais detalhes.</span><span class="sxs-lookup"><span data-stu-id="3fbd0-130">If submission is unsuccessful (because of validation, for example), the response will be a **500 Server Error**, and the response body will include a JSON object with further details.</span></span>

## <a name="example"></a><span data-ttu-id="3fbd0-131">Exemplo</span><span class="sxs-lookup"><span data-stu-id="3fbd0-131">Example</span></span>

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

## <a name="validation-and-error-messages"></a><span data-ttu-id="3fbd0-132">Validação e mensagens de erro</span><span class="sxs-lookup"><span data-stu-id="3fbd0-132">Validation and error messages</span></span>

<span data-ttu-id="3fbd0-133">Como parte da chamada à API de envio, o Human Resources executa a validação de lógica comercial antes do envio, o que garante o estado válido da solicitação de licença para envio.</span><span class="sxs-lookup"><span data-stu-id="3fbd0-133">As part of the call to the submit API, Human Resources performs business logic validation before submission, which ensures the leave request is in a valid state for submission.</span></span> <span data-ttu-id="3fbd0-134">Possíveis mensagens de erro recebidas na resposta se houver falha nas validações:</span><span class="sxs-lookup"><span data-stu-id="3fbd0-134">The possible error messages you may receive in the response if validations fail are:</span></span>

 - <span data-ttu-id="3fbd0-135">A solicitação deixaria o saldo "{LeaveTypeId}" abaixo do saldo mínimo permitido em {date}.</span><span class="sxs-lookup"><span data-stu-id="3fbd0-135">The request would put the '{LeaveTypeId}' balance below the allowed minimum balance on {date}.</span></span>
 - <span data-ttu-id="3fbd0-136">A solicitação de folga no estado concluído não pode ser enviada.</span><span class="sxs-lookup"><span data-stu-id="3fbd0-136">Time off request in Completed state cannot be submitted.</span></span>
 - <span data-ttu-id="3fbd0-137">Não é possível enviar ou salvar a solicitação, pois não houve alterações.</span><span class="sxs-lookup"><span data-stu-id="3fbd0-137">Unable to submit or save request as no changes have been made.</span></span> <span data-ttu-id="3fbd0-138">Adicione ou atualize o valor ou o tipo de licença e tente novamente.</span><span class="sxs-lookup"><span data-stu-id="3fbd0-138">Add or update the amount or the leave type and try again.</span></span>
 - <span data-ttu-id="3fbd0-139">A solicitação de folga inserida contém um ou mais dias com a mesma data e tipo de licença que uma solicitação pendente existente.</span><span class="sxs-lookup"><span data-stu-id="3fbd0-139">The time off request entered contains one or more days with the same date and leave type as an existing pending request.</span></span> <span data-ttu-id="3fbd0-140">Cancele a solicitação existente para fazer alterações.</span><span class="sxs-lookup"><span data-stu-id="3fbd0-140">Please recall the existing request to make changes.</span></span>
 - <span data-ttu-id="3fbd0-141">O código de motivo '{ReasonCodeId}' não se aplica a nenhum tipo de licença na solicitação.</span><span class="sxs-lookup"><span data-stu-id="3fbd0-141">Reason code '{ReasonCodeId}' doesn't apply to any of the leave types in the request.</span></span>
 - <span data-ttu-id="3fbd0-142">O tipo de licença '{LeaveTypeId}' requer um código de motivo.</span><span class="sxs-lookup"><span data-stu-id="3fbd0-142">Leave type '{LeaveTypeId}' requires a reason code.</span></span> <span data-ttu-id="3fbd0-143">Selecione o tipo e o código de motivo apropriados.</span><span class="sxs-lookup"><span data-stu-id="3fbd0-143">Select the appropriate type and reason code.</span></span>
 - <span data-ttu-id="3fbd0-144">A folga não foi enviada com êxito.</span><span class="sxs-lookup"><span data-stu-id="3fbd0-144">The time off was not submitted successfully.</span></span> <span data-ttu-id="3fbd0-145">A folga foi salva como uma solicitação de rascunho.</span><span class="sxs-lookup"><span data-stu-id="3fbd0-145">The time off has been saved as a draft request.</span></span>

## <a name="see-also"></a><span data-ttu-id="3fbd0-146">Consulte também</span><span class="sxs-lookup"><span data-stu-id="3fbd0-146">See also</span></span>

- [<span data-ttu-id="3fbd0-147">Visão geral de MyLeaveRequests</span><span class="sxs-lookup"><span data-stu-id="3fbd0-147">MyLeaveRequests overview</span></span>](hr-developer-api-myleaverequests-overview.md)
- [<span data-ttu-id="3fbd0-148">Autenticação</span><span class="sxs-lookup"><span data-stu-id="3fbd0-148">Authentication</span></span>](hr-developer-api-authentication.md)