---
title: "Acesso a endereços privados por função de segurança"
description: "Este tópico explica como resolver o problema onde um cliente não pode acessar endereços particulares."
author: Darinkramer
manager: AnnBe
ms.date: 11/02/2018
ms.topic: article
ms.prod: 
ms.service: dynamics-365-talent
ms.technology: 
audience: Application User
ms.reviewer: josaw
ms.search.scope: Talent
ms.custom: 
ms.assetid: 
ms.search.region: Global
ms.author: dkrame
ms.search.validFrom: 2018-11-02
ms.dyn365.ops.version: Talent
ms.translationtype: HT
ms.sourcegitcommit: d3f974f94b6c327fd70b8098d24f9e1f1e1e8eeb
ms.openlocfilehash: c1c1c3ce1233408e73d177f9e04f1137f3171a49
ms.contentlocale: pt-br
ms.lasthandoff: 12/04/2018

---

# <a name="access-to-private-addresses-by-security-role"></a><span data-ttu-id="8a54c-103">Acesso a endereços privados por função de segurança</span><span class="sxs-lookup"><span data-stu-id="8a54c-103">Access to private addresses by security role</span></span>

[!include [banner](includes/banner.md)]

<span data-ttu-id="8a54c-104">**Saída**</span><span class="sxs-lookup"><span data-stu-id="8a54c-104">**Issue**</span></span>

<span data-ttu-id="8a54c-105">Depois que um cliente duplica uma função de segurança e entra com a nova função, o cliente não pode ver endereços que estavam marcados como particulares.</span><span class="sxs-lookup"><span data-stu-id="8a54c-105">After a customer duplicates a security role and signs in as that new role, the customer can't see addresses that were marked as private.</span></span>

<span data-ttu-id="8a54c-106">**Resolução**</span><span class="sxs-lookup"><span data-stu-id="8a54c-106">**Resolution**</span></span>

<span data-ttu-id="8a54c-107">Para solucionar o problema, o cliente deve rastrear essas etapas para a função de segurança duplicada.</span><span class="sxs-lookup"><span data-stu-id="8a54c-107">To resolve the issue, the customer must follow these steps for the duplicated security role.</span></span>

1. <span data-ttu-id="8a54c-108">Vá para **Administração da organização \> Catálogo de endereços global \> Parâmetros do catálogo de endereços global**.</span><span class="sxs-lookup"><span data-stu-id="8a54c-108">Go to **Organization administration \> Global address book \> Global address book parameters**.</span></span>
2. <span data-ttu-id="8a54c-109">Na guia **Segurança de local privado**, mova a nova opção de segurança da lista **Funções disponíveis** para a lista **Funções selecionadas**.</span><span class="sxs-lookup"><span data-stu-id="8a54c-109">On the **Private location security** tab, move the new security role from the **Available roles** list to the **Selected roles** list.</span></span>
3. <span data-ttu-id="8a54c-110">Selecione **Salvar**.</span><span class="sxs-lookup"><span data-stu-id="8a54c-110">Select **Save**.</span></span>

![Página de parâmetros do catálogo de endereços global](media/GAD-parameters.png)

