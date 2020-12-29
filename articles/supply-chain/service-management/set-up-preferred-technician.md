---
title: Configurar um técnico preferido
description: Você pode selecionar qualquer trabalhador como um técnico preferido para um contrato ou uma ordem de serviço.
author: ShylaThompson
manager: tfehr
ms.date: 05/01/2018
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: SMAAgreementTable, SMADispatchBoard
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: kamaybac
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 850d91372fb1a918840ebc316a4479f4a70bdc24
ms.sourcegitcommit: 199848e78df5cb7c439b001bdbe1ece963593cdb
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/13/2020
ms.locfileid: "4421861"
---
# <a name="set-up-a-preferred-technician"></a><span data-ttu-id="8c846-103">Configurar um técnico preferido</span><span class="sxs-lookup"><span data-stu-id="8c846-103">Set up a preferred technician</span></span> 

[!include [banner](../includes/banner.md)]


<span data-ttu-id="8c846-104">Você pode selecionar qualquer trabalhador como um técnico preferido para um contrato ou uma ordem de serviço.</span><span class="sxs-lookup"><span data-stu-id="8c846-104">You can select any worker as a preferred technician for a service agreement or service order.</span></span> <span data-ttu-id="8c846-105">Entretanto, é recomendável adicionar o trabalhador à equipe de expedição apropriada de forma que ele seja incluído em **Quadro de expedição**.</span><span class="sxs-lookup"><span data-stu-id="8c846-105">However, it is a good idea to add the worker to the appropriate dispatch team so that the worker is included on the **Dispatch board**.</span></span>

## <a name="assign-employee-to-a-dispatch-team"></a><span data-ttu-id="8c846-106">Atribuir funcionário a uma equipe de expedição</span><span class="sxs-lookup"><span data-stu-id="8c846-106">Assign employee to a dispatch team</span></span>

1.  <span data-ttu-id="8c846-107">Clique em **Recursos humanos** \> **Comum** \> **Trabalhadores** \> **Trabalhadores**.</span><span class="sxs-lookup"><span data-stu-id="8c846-107">Click **Human resources** \> **Common** \> **Workers** \> **Workers**.</span></span> <span data-ttu-id="8c846-108">Clique duas vezes em um trabalhador para abrir a página de detalhes sobre ele.</span><span class="sxs-lookup"><span data-stu-id="8c846-108">Double-click a worker to open the worker details page.</span></span> <span data-ttu-id="8c846-109">No **Painel de Ação**, clique em **Configuração** \>**Equipe de expedição** para abrir o formulário **Trabalhadores de expedição**.</span><span class="sxs-lookup"><span data-stu-id="8c846-109">On the **Action Pane**, click **Setup** \>**Dispatch team** to open the **Dispatch workers** form.</span></span>

2.  <span data-ttu-id="8c846-110">No formulário **Equipe de expedição**, selecione a equipe para a qual o trabalhador será atribuído.</span><span class="sxs-lookup"><span data-stu-id="8c846-110">In the **Dispatch team** field, select the team to assign the worker to.</span></span>

## <a name="assign-a-preferred-technician-to-a-service-agreement"></a><span data-ttu-id="8c846-111">Atribuir um técnico preferido a um contrato de serviço</span><span class="sxs-lookup"><span data-stu-id="8c846-111">Assign a preferred technician to a service agreement</span></span>

1.  <span data-ttu-id="8c846-112">Clique em **Gerenciamento de serviços** \> **Comum** \> **Contratos de serviço** \> **Contratos de serviço**.</span><span class="sxs-lookup"><span data-stu-id="8c846-112">Click **Service management** \> **Common** \> **Service agreements** \> **Service agreements**.</span></span> <span data-ttu-id="8c846-113">Clique duas vezes em um contrato de serviço para abrir o formulário de detalhes.</span><span class="sxs-lookup"><span data-stu-id="8c846-113">Double-click a service agreement to open the details form.</span></span>

2.  <span data-ttu-id="8c846-114">Na guia **Geral**, selecione o campo **Técnico preferido** e então selecione um membro da equipe de expedição apropriada como o técnico preferido para o contrato de serviço.</span><span class="sxs-lookup"><span data-stu-id="8c846-114">On the **General** tab, select the **Preferred technician** field, and then select a member of the appropriate dispatch team as the preferred technician for the service agreement.</span></span>

## <a name="assign-a-preferred-technician-to-a-service-order"></a><span data-ttu-id="8c846-115">Atribuir um técnico preferido a uma ordem de serviço</span><span class="sxs-lookup"><span data-stu-id="8c846-115">Assign a preferred technician to a service order</span></span>

1.  <span data-ttu-id="8c846-116">Clique em **Gerenciamento de serviço** \> **Periódico** \> **Quadro de expedição**.</span><span class="sxs-lookup"><span data-stu-id="8c846-116">Click **Service management** \> **Periodic** \> **Dispatch board**.</span></span>
    

    > [!NOTE]
    > <P><span data-ttu-id="8c846-117">No formulário <STRONG>Quadro de expedição</STRONG>, especifique um intervalo de datas para as atividades de expedição que deseja exibir.</span><span class="sxs-lookup"><span data-stu-id="8c846-117">In the <STRONG>Dispatch board</STRONG> form, specify a date range for dispatch activities to view.</span></span> <span data-ttu-id="8c846-118">Também especifique se deseja exibir as atividades fechadas e limitar a lista de atividades de expedição a equipes às quais você pertence ou está autorizado a monitorar.</span><span class="sxs-lookup"><span data-stu-id="8c846-118">Also, specify whether to display closed activities and whether to limit the dispatch activity list to teams that you belong to or are authorized to monitor.</span></span> <span data-ttu-id="8c846-119">Clique em <STRONG>OK</STRONG> para abrir a caixa de diálogo <STRONG>Quadro de expedição</STRONG>.</span><span class="sxs-lookup"><span data-stu-id="8c846-119">Click <STRONG>OK</STRONG> to open the <STRONG>Dispatch board</STRONG>.</span></span></P>



2.  <span data-ttu-id="8c846-120">Selecione a linha da atividade de serviço a ser modificada.</span><span class="sxs-lookup"><span data-stu-id="8c846-120">Select the line of the service activity to modify.</span></span>

3.  <span data-ttu-id="8c846-121">Na guia **Relacionado**, use a lista **Trabalhador** para atribuir um membro da equipe de expedição apropriada como o técnico preferido para a chamada de serviço.</span><span class="sxs-lookup"><span data-stu-id="8c846-121">On the **Related** tab, use the **Worker** list to assign a member of the appropriate dispatch team as the preferred technician for the service call.</span></span>

## <a name="see-also"></a><span data-ttu-id="8c846-122">Consulte também</span><span class="sxs-lookup"><span data-stu-id="8c846-122">See also</span></span>

[<span data-ttu-id="8c846-123">Visão geral de desenvolvimento e estabelecimento de contratos de serviço</span><span class="sxs-lookup"><span data-stu-id="8c846-123">Develop and establish service agreements overview</span></span>](service-agreements.md)

[<span data-ttu-id="8c846-124">Criar ordens de serviço manualmente</span><span class="sxs-lookup"><span data-stu-id="8c846-124">Create service orders manually</span></span>](create-service-orders-manually.md)

<span data-ttu-id="8c846-125">[Contratos de serviço (formulário)](https://technet.microsoft.com/library/aa617823\(v=ax.60\))</span><span class="sxs-lookup"><span data-stu-id="8c846-125">[Service agreements (form)](https://technet.microsoft.com/library/aa617823\(v=ax.60\))</span></span>
  


