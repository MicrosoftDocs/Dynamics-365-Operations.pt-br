---
title: O usuário pode acessar Recursos Humanos, mas não o Onboard ou o Attract
description: Este tópico explica como resolver o problema em que um usuário pode acessar o Microsoft Dynamics 365 Talent - Recursos Humanos, mas não pode acessar o Attract ou o Onboard.
author: andreabichsel
manager: AnnBe
ms.date: 11/02/2018
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-talent
ms.technology: ''
audience: Application User
ms.reviewer: anbichse
ms.search.scope: Talent
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: anbichse
ms.search.validFrom: 2018-11-02
ms.dyn365.ops.version: Talent
ms.openlocfilehash: 6c384d9a7100982eabd201d910e1bea14355dc1f
ms.sourcegitcommit: 199848e78df5cb7c439b001bdbe1ece963593cdb
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/13/2020
ms.locfileid: "4460312"
---
# <a name="user-can-access-human-resources-but-not-onboard-or-attract"></a><span data-ttu-id="3ce61-103">O usuário pode acessar Recursos Humanos, mas não o Onboard ou o Attract</span><span class="sxs-lookup"><span data-stu-id="3ce61-103">User can access Human Resources but not Onboard or Attract</span></span>

[!include [banner](includes/banner.md)]

<span data-ttu-id="3ce61-104">**Detalhes do ambiente**</span><span class="sxs-lookup"><span data-stu-id="3ce61-104">**Environment details**</span></span>

- <span data-ttu-id="3ce61-105">A implantação do Microsoft Dynamics Lifecycle Services (LCS) foi feita pelo usuário A.</span><span class="sxs-lookup"><span data-stu-id="3ce61-105">The Microsoft Dynamics Lifecycle Services (LCS) deployment was done by user A.</span></span>
- <span data-ttu-id="3ce61-106">Usuário A adicionou usuário B como um usuário do Microsoft Dynamics 365 Human Resources.</span><span class="sxs-lookup"><span data-stu-id="3ce61-106">User A added user B as a user to Microsoft Dynamics 365 Human Resources.</span></span>

<span data-ttu-id="3ce61-107">**Emissão**</span><span class="sxs-lookup"><span data-stu-id="3ce61-107">**Issue**</span></span>

<span data-ttu-id="3ce61-108">O usuário B pode acessar Recursos Humanos, mas não pode acessar o aplicativo Talent: Attract ou o Talent: Onboard.</span><span class="sxs-lookup"><span data-stu-id="3ce61-108">User B can access Human Resources, but can't access the Talent: Attract or Talent: Onboard app.</span></span> <span data-ttu-id="3ce61-109">Quando o usuário tenta ir para **Aplicativos de experiência**, ele ou ela é levado para um ambiente de teste, em vez disso.</span><span class="sxs-lookup"><span data-stu-id="3ce61-109">When the user tries to go to **Experience apps**, he or she is taken to a trial environment instead.</span></span>

<span data-ttu-id="3ce61-110">**Solução**</span><span class="sxs-lookup"><span data-stu-id="3ce61-110">**Solution**</span></span>

<span data-ttu-id="3ce61-111">O usuário B deve receber os direitos para visualizar o ambiente do Microsoft Power Apps que o usuário A criou durante o processo de provisionamento.</span><span class="sxs-lookup"><span data-stu-id="3ce61-111">User B must be assigned the rights to view the Microsoft Power Apps environment that user A created during the provisioning process.</span></span>

<span data-ttu-id="3ce61-112">Para obter informações, consulte a seção "Fornecendo acesso ao ambiente" em [Talento de provisão](https://docs.microsoft.com/dynamics365/unified-operations/talent/provisioning-talent).</span><span class="sxs-lookup"><span data-stu-id="3ce61-112">For information, see the "Granting access to the environment" section in [Provision Talent](https://docs.microsoft.com/dynamics365/unified-operations/talent/provisioning-talent).</span></span>

<span data-ttu-id="3ce61-113">**Solução de longo prazo**</span><span class="sxs-lookup"><span data-stu-id="3ce61-113">**Long-term solution**</span></span>

<span data-ttu-id="3ce61-114">A Microsoft está considerando atribuir automaticamente os direitos apropriados para Onboard e Attract quando um usuário é adicionado a Recursos Humanos.</span><span class="sxs-lookup"><span data-stu-id="3ce61-114">Microsoft is considering automatically assigning the appropriate rights to Onboard and Attract when a user is added to Human Resources.</span></span>
