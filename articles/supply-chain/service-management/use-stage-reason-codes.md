---
title: Usar códigos de motivo da fase
description: Os códigos de motivo são usados para indicar por que um contrato de nível de serviço (SLA) foi cancelado ou por que uma ordem de serviço excedeu o limite de tempo definido no SLA.
author: ShylaThompson
manager: tfehr
ms.date: 05/07/2018
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: SMAServiceOrderTable, SMAParameters
audience: Application User
ms.reviewer: kamaybac
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: kamaybac
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 4acba8f723ceb3d629671833db59c97a900c9f01
ms.sourcegitcommit: 38d40c331c8894acb7b119c5073e3088b54776c1
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/15/2021
ms.locfileid: "4965696"
---
# <a name="use-stage-reason-codes"></a><span data-ttu-id="f5600-103">Usar códigos de motivo da fase</span><span class="sxs-lookup"><span data-stu-id="f5600-103">Use stage reason codes</span></span> 

[!include [banner](../includes/banner.md)]


<span data-ttu-id="f5600-104">Os códigos de motivo são usados para indicar por que um contrato de nível de serviço (SLA) foi cancelado ou por que uma ordem de serviço excedeu o limite de tempo definido no SLA.</span><span class="sxs-lookup"><span data-stu-id="f5600-104">You use a reason code to indicate why a service level agreement (SLA) has been canceled, or why a service order has exceeded the time limit that is you define in the SLA.</span></span>

<span data-ttu-id="f5600-105">Você também pode especificar que um código de motivo será necessário quando um SLA for cancelado, ou quando o limite de tempo exceder o tempo especificado no SLA para a ordem de serviço.</span><span class="sxs-lookup"><span data-stu-id="f5600-105">You can also specify that a reason code is required when an SLA is canceled, or when the time limit exceeds the time that is specified in the SLA for the service order.</span></span>

<span data-ttu-id="f5600-106">Se você especificou que um código de motivo será necessário, deverá inserir um código de motivo nas seguintes situações:</span><span class="sxs-lookup"><span data-stu-id="f5600-106">If you have specified that a reason code is required, you must enter a reason code in the following situations:</span></span>

  - <span data-ttu-id="f5600-107">Quando uma ordem de serviço for movida para um estágio no qual o registro de tempo em relação ao SLA da ordem é interrompido.</span><span class="sxs-lookup"><span data-stu-id="f5600-107">When a service order is moved to a stage that stops time recording against the SLA for the service order.</span></span>

  - <span data-ttu-id="f5600-108">Quando a ordem de serviço for aprovada.</span><span class="sxs-lookup"><span data-stu-id="f5600-108">When the service order is signed off.</span></span>

  - <span data-ttu-id="f5600-109">Quando o registro de tempo for interrompido manualmente.</span><span class="sxs-lookup"><span data-stu-id="f5600-109">When time recording is manually stopped.</span></span>

## <a name="set-up-reason-codes"></a><span data-ttu-id="f5600-110">Configurar códigos de motivo</span><span class="sxs-lookup"><span data-stu-id="f5600-110">Set up reason codes</span></span>

1.  <span data-ttu-id="f5600-111">Clique em **Gerenciamento de serviços** \> **Configuração** \> **Ordens de serviço** \> **Códigos de motivo da fase**.</span><span class="sxs-lookup"><span data-stu-id="f5600-111">Click **Service management** \> **Setup** \> **Service orders** \> **Stage reason codes**.</span></span>

2.  <span data-ttu-id="f5600-112">No formulário **Códigos de motivos da fase**, clique em **Novo** para criar um novo código de motivo.</span><span class="sxs-lookup"><span data-stu-id="f5600-112">In the **Stage reason codes** form, click **New** to create a new reason code.</span></span>

3.  <span data-ttu-id="f5600-113">No campo **Código de motivo da fase**, insira um código de motivo de estágio exclusivo.</span><span class="sxs-lookup"><span data-stu-id="f5600-113">In the **Stage reason code** field, enter a unique stage reason code.</span></span>

4.  <span data-ttu-id="f5600-114">No campo **Descrição**, insira uma descrição do código de motivo de estágio.</span><span class="sxs-lookup"><span data-stu-id="f5600-114">In the **Description** field, enter a description of the stage reason code.</span></span>

5.  <span data-ttu-id="f5600-115">Feche o formulário para salvar suas alterações.</span><span class="sxs-lookup"><span data-stu-id="f5600-115">Close the form to save your changes.</span></span>

## <a name="require-reason-codes-when-a-service-level-agreement-is-canceled"></a><span data-ttu-id="f5600-116">Exigir códigos de motivo quando um contrato de nível de serviço é cancelado</span><span class="sxs-lookup"><span data-stu-id="f5600-116">Require reason codes when a service level agreement is canceled</span></span>

1.  <span data-ttu-id="f5600-117">Clique em **Gerenciamento de serviços** \> **Configuração** \> **Parâmetros de gerenciamento de serviços**.</span><span class="sxs-lookup"><span data-stu-id="f5600-117">Click **Service management** \> **Setup** \> **Service management parameters**.</span></span>

2.  <span data-ttu-id="f5600-118">No formulário **Parâmetros de gerenciamento de serviço**, clique no link **Geral**, e marque a caixa de seleção **Código de motivo para cancelamento**.</span><span class="sxs-lookup"><span data-stu-id="f5600-118">In the **Service management parameters** form, click the **General** link, and then select the **Reason code on canceling** check box.</span></span>

## <a name="require-reason-codes-when-the-a-service-order-exceeds-the-time-limit-that-is-set-by-the-service-level-agreement"></a><span data-ttu-id="f5600-119">Exigir códigos de motivo quando a ordem de serviço exceder o limite de tempo definido pelo contrato de nível de serviço</span><span class="sxs-lookup"><span data-stu-id="f5600-119">Require reason codes when the a service order exceeds the time limit that is set by the service level agreement</span></span>

1.  <span data-ttu-id="f5600-120">Clique em **Gerenciamento de serviços** \> **Configuração** \> **Parâmetros de gerenciamento de serviços**.</span><span class="sxs-lookup"><span data-stu-id="f5600-120">Click **Service management** \> **Setup** \> **Service management parameters**.</span></span>

2.  <span data-ttu-id="f5600-121">No formulário **Parâmetros de gerenciamento de serviço**, clique no link **Geral**, e marque a caixa de seleção **Código de motivo sobre tempo excedente**.</span><span class="sxs-lookup"><span data-stu-id="f5600-121">In the **Service management parameters** form, click the **General** link, and then select the **Reason code on exceeding time** check box.</span></span>

## <a name="see-also"></a><span data-ttu-id="f5600-122">Consulte também</span><span class="sxs-lookup"><span data-stu-id="f5600-122">See also</span></span>

[<span data-ttu-id="f5600-123">Iniciar e parar a folha de ponto em uma ordem de serviço</span><span class="sxs-lookup"><span data-stu-id="f5600-123">Start and stop time recording on a service order</span></span>](start-and-stop-time-recording-on-a-service-order.md)

  


