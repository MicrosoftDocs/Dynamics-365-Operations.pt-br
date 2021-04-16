---
title: Configurar estágios da ordem de serviço
description: Configurar estágios da ordem de serviço.
author: ShylaThompson
ms.date: 05/07/2018
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: SMAServiceOrderTable
audience: Application User
ms.reviewer: kamaybac
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: kamaybac
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 4b6e245b351b66724eedf8e0d1a0ebf0202df857
ms.sourcegitcommit: 0e8db169c3f90bd750826af76709ef5d621fd377
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/01/2021
ms.locfileid: "5824405"
---
# <a name="set-up-service-order-stages"></a><span data-ttu-id="3e960-103">Configurar estágios da ordem de serviço</span><span class="sxs-lookup"><span data-stu-id="3e960-103">Set up service order stages</span></span> 

[!include [banner](../includes/banner.md)]


1.  <span data-ttu-id="3e960-104">Vá para **Gerenciamento de serviços** \> **Configuração** \> **Ordens de serviço** \> **Fases de serviço**.</span><span class="sxs-lookup"><span data-stu-id="3e960-104">Go to **Service management** \> **Setup** \> **Service orders** \> **Service stages**.</span></span>

2.  <span data-ttu-id="3e960-105">Selecione **Novo** para criar um novo registro.</span><span class="sxs-lookup"><span data-stu-id="3e960-105">Select **New** to create a new record.</span></span>

3.  <span data-ttu-id="3e960-106">Nos campos **Etapa de serviço** e **Descrição**, especifique uma ID de etapa de serviço e uma descrição.</span><span class="sxs-lookup"><span data-stu-id="3e960-106">In the **Service stage** and **Description** fields, specify a service stage ID and description.</span></span>

4.  <span data-ttu-id="3e960-107">Selecione os parâmetros apropriados para o estágio.</span><span class="sxs-lookup"><span data-stu-id="3e960-107">Select the appropriate parameters for the stage.</span></span>

5.  <span data-ttu-id="3e960-108">Selecione a fase pai da fase atual ou deixe o campo **Pai** em branco, se a fase for a fase inicial na configuração de fase.</span><span class="sxs-lookup"><span data-stu-id="3e960-108">Select the parent stage for the current stage or leave the **Parent** field blank if the stage is the initial stage in the stage setup.</span></span>


> [!NOTE]
> <P><span data-ttu-id="3e960-109">Depois que você salvar o estágio, não poderá modificar o campo <STRONG>Pai</STRONG>.</span><span class="sxs-lookup"><span data-stu-id="3e960-109">You cannot modify the <STRONG>Parent</STRONG> field after you save the stage.</span></span> <span data-ttu-id="3e960-110">Em vez disso, você pode excluir o registro e criá-lo novamente com uma seleção diferente no campo <STRONG>Pai</STRONG>.</span><span class="sxs-lookup"><span data-stu-id="3e960-110">Instead, you can delete the record and create the record again with a different selection in the <STRONG>Parent</STRONG> field.</span></span></P>
> <P><span data-ttu-id="3e960-111">Além disso, você pode criar apenas um estágio com um campo <STRONG>Pai</STRONG> em branco.</span><span class="sxs-lookup"><span data-stu-id="3e960-111">Also, you can only create one stage with a blank <STRONG>Parent</STRONG> field.</span></span> <span data-ttu-id="3e960-112">Ou seja, apenas um estágio inicial é permitido.</span><span class="sxs-lookup"><span data-stu-id="3e960-112">That is, only one initial stage is permitted.</span></span></P>


  




[!INCLUDE[footer-include](../../includes/footer-banner.md)]