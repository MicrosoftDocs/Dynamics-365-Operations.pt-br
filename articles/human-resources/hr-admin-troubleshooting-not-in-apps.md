---
title: O Human Resources não aparece nos aplicativos do Microsoft Dynamics 365
description: Este artigo explica o que fazer se o cliente não vir o aplicativo Microsoft Dynamics 365 Human Resources entre os aplicativos do Microsoft Dynamics 365.
author: andreabichsel
manager: AnnBe
ms.date: 02/03/2020
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
ms.search.validFrom: 2020-02-03
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: cbf47b4673e1c97965bba7728e5669b7639c4d56
ms.sourcegitcommit: ba340f836e472f13f263dec46a49847c788fca44
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/04/2020
ms.locfileid: "3431075"
---
# <a name="human-resources-doesnt-appear-in-microsoft-dynamics-365-apps"></a><span data-ttu-id="c5fc4-103">O Human Resources não aparece nos aplicativos do Microsoft Dynamics 365</span><span class="sxs-lookup"><span data-stu-id="c5fc4-103">Human Resources doesn't appear in Microsoft Dynamics 365 apps</span></span>

<span data-ttu-id="c5fc4-104">**Emissão**</span><span class="sxs-lookup"><span data-stu-id="c5fc4-104">**Issue**</span></span>

<span data-ttu-id="c5fc4-105">O cliente não verá o Dynamics 365 Human Resources entre os aplicativos do Microsoft Dynamics 365.</span><span class="sxs-lookup"><span data-stu-id="c5fc4-105">The customer doesn't see Dynamics 365 Human Resources among the Microsoft Dynamics 365 apps.</span></span>

<span data-ttu-id="c5fc4-106">**Resolução**</span><span class="sxs-lookup"><span data-stu-id="c5fc4-106">**Resolution**</span></span>

<span data-ttu-id="c5fc4-107">O usuário deve ser adicionado à função de criador de ambiente do ambiente no Microsoft Power Apps.</span><span class="sxs-lookup"><span data-stu-id="c5fc4-107">The user must be added to the Environment Maker role for the environment in Microsoft Power Apps.</span></span>

1. <span data-ttu-id="c5fc4-108">O usuário administrador com uma licença de plano de Power Apps 2 deverá abrir o [Portal de administrador do Power Apps](https://preview.admin.powerapps.com/).</span><span class="sxs-lookup"><span data-stu-id="c5fc4-108">The admin user who has a Power Apps Plan 2 license must open the [Power Apps Admin portal](https://preview.admin.powerapps.com/).</span></span>

2. <span data-ttu-id="c5fc4-109">Selecione **Ambientes** e o ambiente correto para Human Resources.</span><span class="sxs-lookup"><span data-stu-id="c5fc4-109">Select **Environments**, and select the correct environment for Human Resources.</span></span>

3. <span data-ttu-id="c5fc4-110">Na guia **Segurança**, na guia **Funções de ambiente**, selecione **Criador de ambiente**.</span><span class="sxs-lookup"><span data-stu-id="c5fc4-110">On the **Security** tab, on the **Environment roles** tab, select **Environment Maker**.</span></span>

    ![Funções da guia de ambiente](media/environment-roles.png)

4. <span data-ttu-id="c5fc4-112">Na guia **Usuários**, adicione o usuário ou a organização.</span><span class="sxs-lookup"><span data-stu-id="c5fc4-112">On the **Users** tab, add the user or your organization.</span></span>

    ![Tabela de usuários](media/environment-maker.png)

5. <span data-ttu-id="c5fc4-114">Selecione **Salvar**.</span><span class="sxs-lookup"><span data-stu-id="c5fc4-114">Select **Save**.</span></span>

6. <span data-ttu-id="c5fc4-115">O usuário agora deve entrar no [Microsoft Dynamics 365](https://home.dynamics.com/).</span><span class="sxs-lookup"><span data-stu-id="c5fc4-115">The user must now sign in to [Microsoft Dynamics 365](https://home.dynamics.com/).</span></span>

7. <span data-ttu-id="c5fc4-116">Selecione **Sincronizar** para atualizar os aplicativos do usuário.</span><span class="sxs-lookup"><span data-stu-id="c5fc4-116">Select **Sync** to update the user apps.</span></span>

    ![Botão de sincronização](media/get-more.png)

    <span data-ttu-id="c5fc4-118">Após a sincronização ser concluída, Human Resources aparecerá na página inicial.</span><span class="sxs-lookup"><span data-stu-id="c5fc4-118">After synchronization is completed, Human Resources will appear on the home page.</span></span>
