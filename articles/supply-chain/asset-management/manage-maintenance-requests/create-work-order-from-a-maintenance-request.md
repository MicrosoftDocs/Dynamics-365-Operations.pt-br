---
title: Crie ordens de serviço a partir de solicitações de manutenção
description: Este tópico explica como criar uma ordem de serviço a partir de uma solicitação de manutenção em Gerenciamento de Ativos.
author: johanhoffmann
ms.date: 10/01/2019
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: kamaybac
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: johanho
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: 10.0.5
ms.openlocfilehash: c360985509f8f1379ed4a9bd17b95f2d8c85340e
ms.sourcegitcommit: 0e8db169c3f90bd750826af76709ef5d621fd377
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/01/2021
ms.locfileid: "5808583"
---
# <a name="create-work-orders-from-maintenance-requests"></a><span data-ttu-id="63892-103">Crie ordens de serviço a partir de solicitações de manutenção</span><span class="sxs-lookup"><span data-stu-id="63892-103">Create work orders from maintenance requests</span></span>

[!include [banner](../../includes/banner.md)]

 


<span data-ttu-id="63892-104">Depois de criar solicitações de manutenção, você poderá facilmente convertê-las em ordens de trabalho.</span><span class="sxs-lookup"><span data-stu-id="63892-104">After you've created maintenance requests, you can easily convert them to work orders.</span></span> <span data-ttu-id="63892-105">Este tópico descreve a maneira mais rápida de trabalhar com solicitações de manutenção, atualizar várias solicitações de manutenção ao mesmo tempo e criar uma ordem de serviço para várias solicitações de manutenção simultaneamente.</span><span class="sxs-lookup"><span data-stu-id="63892-105">This topic describes the quickest way to work with maintenance requests, update several maintenance requests at the same time, and then create a work order for several maintenance requests at the same time.</span></span> <span data-ttu-id="63892-106">Na página **Solicitações de manutenção ativas** ou **Minhas solicitações de manutenção local funcional**, é possível trabalhar com uma solicitação de serviço por vez e converter uma solicitação de manutenção em uma ordem de serviço.</span><span class="sxs-lookup"><span data-stu-id="63892-106">On the **Active maintenance requests** or **My functional location maintenance requests** page, you can also work with one maintenance request at a time and convert one maintenance request to a work order.</span></span>

> [!NOTE]
> <span data-ttu-id="63892-107">Toda solicitação de manutenção pode estar relacionado a apenas uma ordem de serviço.</span><span class="sxs-lookup"><span data-stu-id="63892-107">Every maintenance request can be related to only one work order.</span></span> <span data-ttu-id="63892-108">Porém, várias solicitações de manutenção podem ser incluídas em uma ordem de serviço, mesmo que as solicitações de manutenção tenham diferentes ativos.</span><span class="sxs-lookup"><span data-stu-id="63892-108">However, multiple maintenance requests can be included in one work order, even if the maintenance requests have different assets.</span></span>

1. <span data-ttu-id="63892-109">Selecione **Gerenciamento de ativos** \> **Comum** \> **Solicitações de manutenção** \> **Todas as solicitações de manutenção**.</span><span class="sxs-lookup"><span data-stu-id="63892-109">Select **Asset management** \> **Common** \> **maintenance requests** \> **All maintenance requests**.</span></span>
2. <span data-ttu-id="63892-110">Antes de criar uma ordem de serviço a partir de solicitações de manutenção, selecione, pelo menos, um tipo de trabalho de manutenção para as solicitações de manutenção. Selecione também a grade e o comércio de um tipo de trabalho de manutenção, caso essas informações sejam relevantes.</span><span class="sxs-lookup"><span data-stu-id="63892-110">Before you can create a work order from maintenance requests, you must select, at a minimum, a maintenance job type for the maintenance requests, and also a maintenance job type variant and trade, if this information is relevant.</span></span> <span data-ttu-id="63892-111">Na exibição de grade, você pode facilmente atualizar informações para uma solicitação de manutenção.</span><span class="sxs-lookup"><span data-stu-id="63892-111">In the grid view, you can easily update information for a maintenance request.</span></span>
3. <span data-ttu-id="63892-112">Quando estiver pronto para criar uma ordem de serviço, selecione as solicitações de manutenção a serem incluídas nela.</span><span class="sxs-lookup"><span data-stu-id="63892-112">When you're ready to create a work order, select the maintenance requests to include in it.</span></span>

    - <span data-ttu-id="63892-113">Se você selecionar várias solicitações de manutenção para converter em uma ordem de serviço, defina os campos **Ativo** e **Tipo de trabalho de manutenção** antes de criar a ordem de serviço.</span><span class="sxs-lookup"><span data-stu-id="63892-113">If you select several maintenance requests to convert to a work order, both the **Asset** field and the **Maintenance job type** field must be set before you create the work order.</span></span>
    - <span data-ttu-id="63892-114">Se você selecionar uma solicitação de manutenção para converter em uma ordem de serviço, defina apenas o campo **Ativo** antes de criar a ordem de serviço.</span><span class="sxs-lookup"><span data-stu-id="63892-114">If you select one maintenance request to convert to a work order, only the **Asset** field must be set before you create the work order.</span></span> <span data-ttu-id="63892-115">Porém, quando você criar a ordem de serviço, selecione um tipo de trabalho de manutenção (e uma grade e um comércio relacionados ao tipo de trabalho de manutenção, se essas informações forem relevantes) na caixa de diálogo **Criar ordem de serviço**.</span><span class="sxs-lookup"><span data-stu-id="63892-115">However, when you create the work order, you can select a maintenance job type (and a related maintenance job type variant and trade, if this information is relevant) in the **Create work order** dialog box.</span></span>

4. <span data-ttu-id="63892-116">Selecione **Ordem de serviço**.</span><span class="sxs-lookup"><span data-stu-id="63892-116">Select **Work order**.</span></span>
5. <span data-ttu-id="63892-117">Na caixa de diálogo **Criar ordem de serviço**, defina os campos e selecione **OK**.</span><span class="sxs-lookup"><span data-stu-id="63892-117">In the **Create work order** dialog box, set the fields, and then select **OK**.</span></span>

    <span data-ttu-id="63892-118">Uma barra de mensagem pode notificá-lo de que uma nova ordem de serviço foi criada.</span><span class="sxs-lookup"><span data-stu-id="63892-118">A message bar might notify you that a new work order has been created.</span></span>

    <span data-ttu-id="63892-119">Além disso, quando você criar uma ordem de serviço com base em uma solicitação de manutenção, se o ativo relacionado à solicitação de manutenção estiver incluído em um contrato de garantia, uma barra de mensagem o notificará sobre o contrato de garantia.</span><span class="sxs-lookup"><span data-stu-id="63892-119">Additionally, when you create a work order that is based on a maintenance request, if the asset that is related to the maintenance request is included in a warranty agreement, a message bar notifies you about the warranty agreement.</span></span>

6. <span data-ttu-id="63892-120">Selecione **Gerenciamento de ativos** \> **Comum** \> **Ordens de serviço** \> **Todas as ordens de serviço** e abra a nova ordem de serviço.</span><span class="sxs-lookup"><span data-stu-id="63892-120">Select **Asset management** \> **Common** \> **Work orders** \> **All work orders**, and open the new work order.</span></span>

    ![Abrir nova ordem de serviço](media/05-manage-maintenance-requests.png)



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]