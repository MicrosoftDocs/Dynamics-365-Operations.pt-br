---
title: Habilitar a integração do Dynamics 365 Commerce e do Microsoft Teams
description: Este tópico descreve como habilitar a integração do Microsoft Dynamics 365 Commerce e do Microsoft Teams.
author: gvrmohanreddy
manager: annbe
ms.date: 03/31/2021
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-commerce
ms.technology: ''
audience: Application User
ms.reviewer: v-chgri
ms.search.scope: Retail, Core, Operations
ms.search.region: Global
ms.author: gmohanv
ms.search.validFrom: 2021-01-15
ms.dyn365.ops.version: 10.0.18
ms.openlocfilehash: c0dbf7a3c7fa3532e35cac240c1abb8adbdbe489
ms.sourcegitcommit: 0e8db169c3f90bd750826af76709ef5d621fd377
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/01/2021
ms.locfileid: "5842612"
---
# <a name="enable-dynamics-365-commerce-and-microsoft-teams-integration"></a><span data-ttu-id="32ef2-103">Habilitar a integração do Dynamics 365 Commerce e do Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="32ef2-103">Enable Dynamics 365 Commerce and Microsoft Teams integration</span></span>

[!include [banner](includes/banner.md)]
[!include [banner](includes/preview-banner.md)]

<span data-ttu-id="32ef2-104">Este tópico descreve como habilitar a integração do Microsoft Dynamics 365 Commerce e do Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="32ef2-104">This topic describes how to enable Microsoft Dynamics 365 Commerce and Microsoft Teams integration.</span></span>

<span data-ttu-id="32ef2-105">Para provisionar o Teams com informações do Dynamics 365 Commerce e sincronizar os recursos de gerenciamento de tarefas entre o Teams e o aplicativo PDV (ponto de venda), você deve habilitar os recursos de integração no Commerce Headquarters.</span><span class="sxs-lookup"><span data-stu-id="32ef2-105">To provision Teams with information from Dynamics 365 Commerce and synchronize the task management features between Teams and the point of sale (POS) application, you must enable the integration features in Commerce headquarters.</span></span>

> [!NOTE]
> <span data-ttu-id="32ef2-106">Ao habilitar a integração do Teams, você concorda em compartilhar seus dados com o Teams.</span><span class="sxs-lookup"><span data-stu-id="32ef2-106">When you enable Teams integration, you consent to share your data with Teams.</span></span> <span data-ttu-id="32ef2-107">Os dados compartilhados com o Teams podem residir em um país diferente do que os dados do Commerce e podem estar sujeitos a padrões de conformidade diferentes.</span><span class="sxs-lookup"><span data-stu-id="32ef2-107">Data that is shared with Teams might reside in a different country than your Commerce data, and it might be subject to different compliance standards.</span></span> <span data-ttu-id="32ef2-108">Para obter mais informações, consulte o [Microsoft Trust Center](https://www.microsoft.com/trust-center).</span><span class="sxs-lookup"><span data-stu-id="32ef2-108">For more information, see the [Microsoft Trust Center](https://www.microsoft.com/trust-center).</span></span> <span data-ttu-id="32ef2-109">Para obter informações sobre as diretivas de privacidade da Microsoft, consulte a [Política de Privacidade da Microsoft](https://aka.ms/privacy).</span><span class="sxs-lookup"><span data-stu-id="32ef2-109">For information about Microsoft privacy policies, see the [Microsoft Privacy Statement](https://aka.ms/privacy).</span></span>

## <a name="enable-teams-integration"></a><span data-ttu-id="32ef2-110">Habilitar a integração do Teams</span><span class="sxs-lookup"><span data-stu-id="32ef2-110">Enable Teams integration</span></span>

<span data-ttu-id="32ef2-111">Antes de habilitar a integração do Microsoft Teams com o Commerce, você deve registrar o aplicativo Teams com seu locatário no portal do Azure.</span><span class="sxs-lookup"><span data-stu-id="32ef2-111">Before you can enable Microsoft Teams integration with Commerce, you must register the Teams application with your tenant in the Azure portal.</span></span>

<span data-ttu-id="32ef2-112">Para registrar o aplicativo Teams no seu locatário no portal do Azure, siga estas etapas.</span><span class="sxs-lookup"><span data-stu-id="32ef2-112">To register the Teams application with your tenant in the Azure portal, follow these steps.</span></span>

1. <span data-ttu-id="32ef2-113">Siga as etapas no [Início rápido: registre um aplicativo com a plataforma de identidade da Microsoft](https://docs.microsoft.com/azure/active-directory/develop/quickstart-register-app) para registrar o aplicativo Teams com seu locatário no portal do Azure.</span><span class="sxs-lookup"><span data-stu-id="32ef2-113">Follow the steps in [Quickstart: Register an app in the Microsoft identity platform](https://docs.microsoft.com/azure/active-directory/develop/quickstart-register-app) to register the Teams application with your tenant in the Azure portal.</span></span>
1. <span data-ttu-id="32ef2-114">Copie o valor do **ID do aplicativo (cliente)** da página **Visão Geral** do aplicativo registrado.</span><span class="sxs-lookup"><span data-stu-id="32ef2-114">Copy the **Application (client) ID** value from the **Overview** page for the registered app.</span></span> <span data-ttu-id="32ef2-115">Você usará esse valor para habilitar a integração do Teams no Commerce Headquarters.</span><span class="sxs-lookup"><span data-stu-id="32ef2-115">You will use this value to enable Teams integration in Commerce headquarters.</span></span>
1. <span data-ttu-id="32ef2-116">Copie o valor de certificado que foi inserido quando você [adicionou um certificado](https://docs.microsoft.com/azure/active-directory/develop/quickstart-register-app#add-a-certificate) na etapa 1.</span><span class="sxs-lookup"><span data-stu-id="32ef2-116">Copy the certificate value that was entered when you [added a certificate](https://docs.microsoft.com/azure/active-directory/develop/quickstart-register-app#add-a-certificate) in step 1.</span></span> <span data-ttu-id="32ef2-117">O certificado também é conhecido como chave pública ou chave de aplicativo.</span><span class="sxs-lookup"><span data-stu-id="32ef2-117">The certificate is also known as the public key or application key.</span></span> <span data-ttu-id="32ef2-118">Você usará esse valor para habilitar a integração do Teams no Commerce Headquarters.</span><span class="sxs-lookup"><span data-stu-id="32ef2-118">You will use this value to enable Teams integration in Commerce headquarters.</span></span>

<span data-ttu-id="32ef2-119">Para habilitar a integração do Teams no Commerce headquarters, siga estas etapas.</span><span class="sxs-lookup"><span data-stu-id="32ef2-119">To enable Teams integration in Commerce headquarters, follow these steps.</span></span>

1. <span data-ttu-id="32ef2-120">Vá para **Varejo e Comércio \> Configuração do canal \> Configuração de integração do Microsoft Teams**.</span><span class="sxs-lookup"><span data-stu-id="32ef2-120">Go to **Retail and Commerce \> Channel setup \> Microsoft Teams integration configuration**.</span></span>
1. <span data-ttu-id="32ef2-121">No Painel de Ações, selecione **Editar**.</span><span class="sxs-lookup"><span data-stu-id="32ef2-121">On the Action Pane, select **Edit**.</span></span>
1. <span data-ttu-id="32ef2-122">Defina a opção **Habilitar integração do Microsoft Teams** como **Sim**.</span><span class="sxs-lookup"><span data-stu-id="32ef2-122">Set the **Enable Microsoft Teams integration** option to **Yes**.</span></span>
1. <span data-ttu-id="32ef2-123">Nos campos **ID do aplicativo** e **Chave do aplicativo**, insira os valores obtidos ao registrar o aplicativo Teams no portal do Azure.</span><span class="sxs-lookup"><span data-stu-id="32ef2-123">In the **Application ID** and **Application key** fields, enter the values you obtained when you registered the Teams application in the Azure portal.</span></span>
1. <span data-ttu-id="32ef2-124">No Painel de ações, selecione **Salvar**.</span><span class="sxs-lookup"><span data-stu-id="32ef2-124">On the Action Pane, select **Save**.</span></span>

<span data-ttu-id="32ef2-125">A ilustração a seguir mostra um exemplo da configuração de integração do Teams no Commerce Headquarters.</span><span class="sxs-lookup"><span data-stu-id="32ef2-125">The following illustration shows an example of the configuration of Teams integration in Commerce headquarters.</span></span>

![Configuração de integração do Teams no Commerce Headquarters](media/D365-Commerce-Microsoft-Teams-Configuration_with_disclaimer.png)

## <a name="disable-teams-integration"></a><span data-ttu-id="32ef2-127">Desabilitar a integração do Teams</span><span class="sxs-lookup"><span data-stu-id="32ef2-127">Disable Teams integration</span></span>

<span data-ttu-id="32ef2-128">Para desabilitar a integração do Microsoft Teams no Commerce headquarters, siga estas etapas.</span><span class="sxs-lookup"><span data-stu-id="32ef2-128">To disable Microsoft Teams integration in Commerce headquarters, follow these steps.</span></span>

1. <span data-ttu-id="32ef2-129">Vá para **Varejo e Comércio \> Configuração do canal \> Configuração de integração do Microsoft Teams**.</span><span class="sxs-lookup"><span data-stu-id="32ef2-129">Go to **Retail and Commerce \> Channel setup \> Microsoft Teams Integration Configuration**.</span></span>
1. <span data-ttu-id="32ef2-130">No Painel de Ações, selecione **Editar**.</span><span class="sxs-lookup"><span data-stu-id="32ef2-130">On the Action Pane, select **Edit**.</span></span>
3. <span data-ttu-id="32ef2-131">Defina a opção **Habilitar integração do Microsoft Teams** como **Não**.</span><span class="sxs-lookup"><span data-stu-id="32ef2-131">Set the **Enable Microsoft Teams integration** option to **No**.</span></span>
4. <span data-ttu-id="32ef2-132">Limpe os valores dos campos **ID do Aplicativo** e **Chave do Aplicativo**.</span><span class="sxs-lookup"><span data-stu-id="32ef2-132">Clear the values from the **Application ID** and **Application Key** fields.</span></span>
1. <span data-ttu-id="32ef2-133">No Painel de ações, selecione **Salvar**.</span><span class="sxs-lookup"><span data-stu-id="32ef2-133">On the Action Pane, select **Save**.</span></span>

> [!NOTE]
> <span data-ttu-id="32ef2-134">Depois de desabilitar a integração o Teams com o Commerce, os terminais de POS não mostrarão mais as tarefas publicadas a partir do aplicativo Teams.</span><span class="sxs-lookup"><span data-stu-id="32ef2-134">After you disable Teams integration with Commerce, POS terminals will no longer show tasks that are published from the Teams application.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="32ef2-135">Recursos adicionais</span><span class="sxs-lookup"><span data-stu-id="32ef2-135">Additional resources</span></span>

[<span data-ttu-id="32ef2-136">Visão geral de integração do Dynamics 365 Commerce e do Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="32ef2-136">Dynamics 365 Commerce and Microsoft Teams integration overview</span></span>](commerce-teams-integration.md)

[<span data-ttu-id="32ef2-137">Provisionar o Microsoft Teams a partir do Dynamics 365 Commerce</span><span class="sxs-lookup"><span data-stu-id="32ef2-137">Provision Microsoft Teams from Dynamics 365 Commerce</span></span>](provision-teams-from-commerce.md)

[<span data-ttu-id="32ef2-138">Sincronizar o gerenciamento de tarefas entre o PDV do Microsoft Teams e do Dynamics 365 Commerce</span><span class="sxs-lookup"><span data-stu-id="32ef2-138">Synchronize task management between Microsoft Teams and Dynamics 365 Commerce POS</span></span>](synchronize-tasks-teams-pos.md)

[<span data-ttu-id="32ef2-139">Gerenciar funções do usuário no Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="32ef2-139">Manage user roles in Microsoft Teams</span></span>](manage-user-roles-teams.md)

[<span data-ttu-id="32ef2-140">Mapear lojas e equipes, se houver equipes pré-existentes no Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="32ef2-140">Map stores and teams if there are pre-existing teams in Microsoft Teams</span></span>](map-stores-existing-teams.md)

[<span data-ttu-id="32ef2-141">Perguntas frequentes sobre a integração do Dynamics 365 Commerce e do Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="32ef2-141">Dynamics 365 Commerce and Microsoft Teams integration FAQ</span></span>](teams-integration-faq.md)
