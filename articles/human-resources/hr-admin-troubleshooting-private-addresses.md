---
title: Acesso a endereços privados por função de segurança
description: Este artigo explica como resolver o problema em que um cliente não pode acessar endereços particulares.
author: andreabichsel
manager: tfehr
ms.date: 11/02/2018
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-human-resources
ms.technology: ''
audience: Application User
ms.reviewer: anbichse
ms.search.scope: Human Resources
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: anbichse
ms.search.validFrom: 2018-11-02
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: 6598094e7877a30c35e1b03794f82c8a4ec001a7
ms.sourcegitcommit: ea2d652867b9b83ce6e5e8d6a97d2f9460a84c52
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/03/2021
ms.locfileid: "5111457"
---
# <a name="access-to-private-addresses-by-security-role"></a><span data-ttu-id="21ecf-103">Acesso a endereços privados por função de segurança</span><span class="sxs-lookup"><span data-stu-id="21ecf-103">Access to private addresses by security role</span></span>

<span data-ttu-id="21ecf-104">**Saída**</span><span class="sxs-lookup"><span data-stu-id="21ecf-104">**Issue**</span></span>

<span data-ttu-id="21ecf-105">Depois que um cliente duplica uma função de segurança e entra com a nova função, o cliente não pode ver endereços que estavam marcados como particulares.</span><span class="sxs-lookup"><span data-stu-id="21ecf-105">After a customer duplicates a security role and signs in as that new role, the customer can't see addresses that were marked as private.</span></span>

<span data-ttu-id="21ecf-106">**Resolução**</span><span class="sxs-lookup"><span data-stu-id="21ecf-106">**Resolution**</span></span>

<span data-ttu-id="21ecf-107">Para solucionar o problema, o cliente deve rastrear essas etapas para a função de segurança duplicada.</span><span class="sxs-lookup"><span data-stu-id="21ecf-107">To resolve the issue, the customer must follow these steps for the duplicated security role.</span></span>

1. <span data-ttu-id="21ecf-108">Vá para **Administração da organização \> Catálogo de endereços global \> Parâmetros do catálogo de endereços global**.</span><span class="sxs-lookup"><span data-stu-id="21ecf-108">Go to **Organization administration \> Global address book \> Global address book parameters**.</span></span>
2. <span data-ttu-id="21ecf-109">Na guia **Segurança de local privado**, mova a nova opção de segurança da lista **Funções disponíveis** para a lista **Funções selecionadas**.</span><span class="sxs-lookup"><span data-stu-id="21ecf-109">On the **Private location security** tab, move the new security role from the **Available roles** list to the **Selected roles** list.</span></span>
3. <span data-ttu-id="21ecf-110">Selecione **Salvar**.</span><span class="sxs-lookup"><span data-stu-id="21ecf-110">Select **Save**.</span></span>

![Página de parâmetros do catálogo de endereços global](media/GAD-parameters.png)
