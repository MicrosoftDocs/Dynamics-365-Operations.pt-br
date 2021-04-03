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
ms.openlocfilehash: 49f9f50b774df8e215c084bbb493a6be9de6b234
ms.sourcegitcommit: 6affb3316be757c99e1fe9c7c7b312b93c483408
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/17/2021
ms.locfileid: "5463927"
---
# <a name="access-to-private-addresses-by-security-role"></a><span data-ttu-id="cf4a8-103">Acesso a endereços privados por função de segurança</span><span class="sxs-lookup"><span data-stu-id="cf4a8-103">Access to private addresses by security role</span></span>

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

<span data-ttu-id="cf4a8-104">**Saída**</span><span class="sxs-lookup"><span data-stu-id="cf4a8-104">**Issue**</span></span>

<span data-ttu-id="cf4a8-105">Depois que um cliente duplica uma função de segurança e entra com a nova função, o cliente não pode ver endereços que estavam marcados como particulares.</span><span class="sxs-lookup"><span data-stu-id="cf4a8-105">After a customer duplicates a security role and signs in as that new role, the customer can't see addresses that were marked as private.</span></span>

<span data-ttu-id="cf4a8-106">**Resolução**</span><span class="sxs-lookup"><span data-stu-id="cf4a8-106">**Resolution**</span></span>

<span data-ttu-id="cf4a8-107">Para solucionar o problema, o cliente deve rastrear essas etapas para a função de segurança duplicada.</span><span class="sxs-lookup"><span data-stu-id="cf4a8-107">To resolve the issue, the customer must follow these steps for the duplicated security role.</span></span>

1. <span data-ttu-id="cf4a8-108">Vá para **Administração da organização \> Catálogo de endereços global \> Parâmetros do catálogo de endereços global**.</span><span class="sxs-lookup"><span data-stu-id="cf4a8-108">Go to **Organization administration \> Global address book \> Global address book parameters**.</span></span>
2. <span data-ttu-id="cf4a8-109">Na guia **Segurança de local privado**, mova a nova opção de segurança da lista **Funções disponíveis** para a lista **Funções selecionadas**.</span><span class="sxs-lookup"><span data-stu-id="cf4a8-109">On the **Private location security** tab, move the new security role from the **Available roles** list to the **Selected roles** list.</span></span>
3. <span data-ttu-id="cf4a8-110">Selecione **Salvar**.</span><span class="sxs-lookup"><span data-stu-id="cf4a8-110">Select **Save**.</span></span>

![Página de parâmetros do catálogo de endereços global](media/GAD-parameters.png)


[!INCLUDE[footer-include](../includes/footer-banner.md)]