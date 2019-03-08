---
title: O Talent não aparece entre os aplicativos do Microsoft Dynamics 365 (CDS1.0)
description: Este tópico explica o que fazer se o cliente não vir o aplicativo Microsoft Dynamics 365 for Talent entre os aplicativos do Microsoft Dynamics 365.
author: Darinkramer
manager: AnnBe
ms.date: 11/02/2018
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-talent
ms.technology: ''
audience: Application User
ms.reviewer: josaw
ms.search.scope: Talent
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: dkrame
ms.search.validFrom: 2018-11-02
ms.dyn365.ops.version: Talent
ms.openlocfilehash: 32ae0ab807e953bd811a557e6878b9bee79d293c
ms.sourcegitcommit: 0f530e5f72a40f383868957a6b5cb0e446e4c795
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/29/2019
ms.locfileid: "303295"
---
# <a name="talent-doesnt-appear-among-the-microsoft-dynamics-365-apps-cds10"></a><span data-ttu-id="1e465-103">O Talent não aparece entre os aplicativos do Microsoft Dynamics 365 (CDS1.0)</span><span class="sxs-lookup"><span data-stu-id="1e465-103">Talent doesn't appear among the Microsoft Dynamics 365 apps (CDS1.0)</span></span>

[!include [banner](includes/banner.md)]

<span data-ttu-id="1e465-104">**Saída**</span><span class="sxs-lookup"><span data-stu-id="1e465-104">**Issue**</span></span>

<span data-ttu-id="1e465-105">O cliente não encontrar o aplicativo Microsoft Dynamics 365 for Talent entre os aplicativos do Microsoft Dynamics 365.</span><span class="sxs-lookup"><span data-stu-id="1e465-105">The customer doesn't see the Microsoft Dynamics 365 for Talent app among the Microsoft Dynamics 365 apps.</span></span>

<span data-ttu-id="1e465-106">**Resolução**</span><span class="sxs-lookup"><span data-stu-id="1e465-106">**Resolution**</span></span>

<span data-ttu-id="1e465-107">O usuário deve ser adicionado à função de criador de ambiente do ambiente no Microsoft PowerApps.</span><span class="sxs-lookup"><span data-stu-id="1e465-107">The user must be added to the Environment Maker role for the environment in Microsoft PowerApps.</span></span>

1. <span data-ttu-id="1e465-108">O usuário admin com uma licença de plano de PowerApps 2 deverá abrir [Portal de admin do PowerApps](https://preview.admin.powerapps.com/).</span><span class="sxs-lookup"><span data-stu-id="1e465-108">The admin user who has a PowerApps Plan 2 license must open the [PowerApps Admin portal](https://preview.admin.powerapps.com/).</span></span>
2. <span data-ttu-id="1e465-109">Selecione **Ambientes**, e selecione o ambiente atual de Talent.</span><span class="sxs-lookup"><span data-stu-id="1e465-109">Select **Environments**, and select the correct environment for Talent.</span></span>
3. <span data-ttu-id="1e465-110">Na guia **Segurança**, na guia **Funções de ambiente**, selecione **Criador de ambiente**.</span><span class="sxs-lookup"><span data-stu-id="1e465-110">On the **Security** tab, on the **Environment roles** tab, select **Environment Maker**.</span></span>

    ![Funções da guia de ambiente](media/environment-roles.png)

4. <span data-ttu-id="1e465-112">Na guia **Usuários**, adicione o usuário ou a organização.</span><span class="sxs-lookup"><span data-stu-id="1e465-112">On the **Users** tab, add the user or your organization.</span></span>

    ![Tabela de usuários](media/environment-maker.png)

5. <span data-ttu-id="1e465-114">Selecione **Salvar**.</span><span class="sxs-lookup"><span data-stu-id="1e465-114">Select **Save**.</span></span>
6. <span data-ttu-id="1e465-115">O usuário agora deve entrar no [Microsoft Dynamics 365](https://home.dynamics.com/).</span><span class="sxs-lookup"><span data-stu-id="1e465-115">The user must now sign in to [Microsoft Dynamics 365](https://home.dynamics.com/).</span></span>
7. <span data-ttu-id="1e465-116">Selecione **Sincronizar** para atualizar os aplicativos do usuário.</span><span class="sxs-lookup"><span data-stu-id="1e465-116">Select **Sync** to update the user apps.</span></span>

    ![Botão de sincronização](media/get-more.png)

    <span data-ttu-id="1e465-118">Após a sincronização ser concluída, Talent aparecerá na página inicial.</span><span class="sxs-lookup"><span data-stu-id="1e465-118">After synchronization is completed, Talent will appear on the home page.</span></span>
