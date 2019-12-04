---
title: O usuário pode acessar o Core HR, mas não o Onboard nem o Attract
description: Este tópico explica como resolver o problema onde um usuário pode acessar o Microsoft Dynamics 365 Talent - Core HR, mas não pode acessar o Attract ou o Onboard.
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
ms.openlocfilehash: 1a86936d756d8375761ce50c9d9bf33dc638dfad
ms.sourcegitcommit: fbc106af09bdadb860677f590464fb93223cbf65
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/06/2019
ms.locfileid: "2772910"
---
# <a name="user-can-access-core-hr-but-not-onboard-or-attract"></a><span data-ttu-id="34f8c-103">O usuário pode acessar o Core HR, mas não o Onboard nem o Attract</span><span class="sxs-lookup"><span data-stu-id="34f8c-103">User can access Core HR but not Onboard or Attract</span></span>

[!include [banner](includes/banner.md)]

<span data-ttu-id="34f8c-104">**Detalhes do ambiente**</span><span class="sxs-lookup"><span data-stu-id="34f8c-104">**Environment details**</span></span>

- <span data-ttu-id="34f8c-105">A implantação do Microsoft Dynamics Lifecycle Services (LCS) foi feita pelo usuário A.</span><span class="sxs-lookup"><span data-stu-id="34f8c-105">The Microsoft Dynamics Lifecycle Services (LCS) deployment was done by user A.</span></span>
- <span data-ttu-id="34f8c-106">Usuário A adicionou usuário B como um usuário do Microsoft Dynamics 365 Talent: Core HR.</span><span class="sxs-lookup"><span data-stu-id="34f8c-106">User A added user B as a user to Microsoft Dynamics 365 Talent: Core HR.</span></span>

<span data-ttu-id="34f8c-107">**Emissão**</span><span class="sxs-lookup"><span data-stu-id="34f8c-107">**Issue**</span></span>

<span data-ttu-id="34f8c-108">O usuário B pode acessar Core HR, mas não pode acessar o aplicativo Talent: Attract ou Talent: Onboard.</span><span class="sxs-lookup"><span data-stu-id="34f8c-108">User B can access Core HR, but can't access the Talent: Attract or Talent: Onboard app.</span></span> <span data-ttu-id="34f8c-109">Quando o usuário tenta ir para **Aplicativos de experiência**, ele ou ela é levado para um ambiente de teste, em vez disso.</span><span class="sxs-lookup"><span data-stu-id="34f8c-109">When the user tries to go to **Experience apps**, he or she is taken to a trial environment instead.</span></span>

<span data-ttu-id="34f8c-110">**Solução**</span><span class="sxs-lookup"><span data-stu-id="34f8c-110">**Solution**</span></span>

<span data-ttu-id="34f8c-111">O usuário B deve receber os direitos para visualizar o ambiente do Microsoft Power Apps que o usuário A criou durante o processo de provisionamento.</span><span class="sxs-lookup"><span data-stu-id="34f8c-111">User B must be assigned the rights to view the Microsoft Power Apps environment that user A created during the provisioning process.</span></span>

<span data-ttu-id="34f8c-112">Para obter informações, consulte a seção "Fornecendo acesso ao ambiente" em [Talento de provisão](https://docs.microsoft.com/dynamics365/unified-operations/talent/provisioning-talent).</span><span class="sxs-lookup"><span data-stu-id="34f8c-112">For information, see the "Granting access to the environment" section in [Provision Talent](https://docs.microsoft.com/dynamics365/unified-operations/talent/provisioning-talent).</span></span>

<span data-ttu-id="34f8c-113">**Solução de longo prazo**</span><span class="sxs-lookup"><span data-stu-id="34f8c-113">**Long-term solution**</span></span>

<span data-ttu-id="34f8c-114">Microsoft está considerando atribuir automaticamente os direitos apropriados para Onboard e Attract quando um usuário é adicionado ao Core HR.</span><span class="sxs-lookup"><span data-stu-id="34f8c-114">Microsoft is considering automatically assigning the appropriate rights to Onboard and Attract when a user is added to Core HR.</span></span>
