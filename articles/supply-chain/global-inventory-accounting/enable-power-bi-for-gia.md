---
title: Habilitar o Power BI para Contabilidade de estoque global
description: Este tópico descreve como habilitar o Microsoft Power BI para a Contabilidade de estoque global.
author: AndersGirke
ms.date: 06/18/2021
ms.topic: article
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: aevengir
ms.search.validFrom: 2021-06-18
ms.dyn365.ops.version: 10.0.20
ms.openlocfilehash: d7979ed18b98ee6133774cd91bc866d6fca92d5f
ms.sourcegitcommit: eceae470f4ae58000ec33fea34db34b7a7a1af43
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/18/2021
ms.locfileid: "6273113"
---
# <a name="enable-power-bi-for-global-inventory-accounting"></a><span data-ttu-id="43901-103">Habilitar o Power BI para Contabilidade de estoque global</span><span class="sxs-lookup"><span data-stu-id="43901-103">Enable Power BI for Global Inventory Accounting</span></span>

[!include [banner](../includes/banner.md)]
[!INCLUDE [preview-banner](../includes/preview-banner.md)]

<span data-ttu-id="43901-104">Você pode fixar blocos, painéis e relatórios de sua conta [PowerBI.com](https://powerbi.com/) para o espaço de trabalho do aplicativo Microsoft Dynamics 365.</span><span class="sxs-lookup"><span data-stu-id="43901-104">You can pin tiles, dashboards, and reports from your [PowerBI.com](https://powerbi.com/) account to your Microsoft Dynamics 365 application workspace.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="43901-105">Pré-requisitos</span><span class="sxs-lookup"><span data-stu-id="43901-105">Prerequisites</span></span>

<span data-ttu-id="43901-106">Os seguintes pré-requisitos devem ser atendidos para você habilitar o relatório do Power BI:</span><span class="sxs-lookup"><span data-stu-id="43901-106">The following prerequisites must be in place before you can enable Power BI reporting:</span></span>

- <span data-ttu-id="43901-107">Você deve ser um administrador de sistema no aplicativo Dynamics 365.</span><span class="sxs-lookup"><span data-stu-id="43901-107">You must be a system administrator in the Dynamics 365 application.</span></span>
- <span data-ttu-id="43901-108">Você deve ter uma conta do [PowerBI.com](https://powerbi.com/).</span><span class="sxs-lookup"><span data-stu-id="43901-108">You must have a [PowerBI.com](https://powerbi.com/) account.</span></span>
- <span data-ttu-id="43901-109">Você deve ter pelo menos um painel e um relatório em sua conta do Power BI.</span><span class="sxs-lookup"><span data-stu-id="43901-109">You must have at least one dashboard and one report in your Power BI account.</span></span>
- <span data-ttu-id="43901-110">Você deve ser um administrador da sua conta do Azure Active Directory (Azure AD).</span><span class="sxs-lookup"><span data-stu-id="43901-110">You must be an administrator for your Azure Active Directory (Azure AD) account.</span></span>
- <span data-ttu-id="43901-111">O domínio do Azure AD deve ser o mesmo domínio que você usou para sua conta do [PowerBI.com](https://powerbi.com/).</span><span class="sxs-lookup"><span data-stu-id="43901-111">The Azure AD domain must be the same domain that you used for your [PowerBI.com](https://powerbi.com/) account.</span></span>

## <a name="setup"></a><span data-ttu-id="43901-112">Configurar</span><span class="sxs-lookup"><span data-stu-id="43901-112">Setup</span></span>

<span data-ttu-id="43901-113">Siga estas etapas para configurar a integração do Power BI.</span><span class="sxs-lookup"><span data-stu-id="43901-113">To set up the Power BI integration, follow these steps.</span></span>

1. <span data-ttu-id="43901-114">Entre no [Microsoft Dynamics Lifecycle Services (LCS)](https://lcs.dynamics.com/Logon/Index).</span><span class="sxs-lookup"><span data-stu-id="43901-114">Sign in to [Microsoft Dynamics Lifecycle Services (LCS)](https://lcs.dynamics.com/Logon/Index).</span></span>
1. <span data-ttu-id="43901-115">Vá para a **Biblioteca de ativos compartilhados**, selecione **Modelo de relatório do Power BI** como o tipo de ativo e baixe o pacote **Contabilidade de estoque global**.</span><span class="sxs-lookup"><span data-stu-id="43901-115">Go to **Shared asset library**, select **Power BI report model** as the asset type, and download the **Global Inventory Accounting** package.</span></span> 
1. <span data-ttu-id="43901-116">Entre no [PowerBI.com](https://app.powerbi.com/) e carregue o arquivo de relatório Power BI da **Contabilidade de estoque global** seguindo estas etapas:</span><span class="sxs-lookup"><span data-stu-id="43901-116">Sign in to [PowerBI.com](https://app.powerbi.com/), and upload the **Global Inventory Accounting** Power BI report file by following these steps:</span></span>

    1. <span data-ttu-id="43901-117">Selecione **Novo**.</span><span class="sxs-lookup"><span data-stu-id="43901-117">Select **New**.</span></span>
    1. <span data-ttu-id="43901-118">Selecione **Atualizar um arquivo**.</span><span class="sxs-lookup"><span data-stu-id="43901-118">Select **Upload a file**.</span></span>
    1. <span data-ttu-id="43901-119">Selecione o arquivo de relatório do Power BI da **Contabilidade de estoque global**.</span><span class="sxs-lookup"><span data-stu-id="43901-119">Select the **Global Inventory Accounting** Power BI report file.</span></span>

1. <span data-ttu-id="43901-120">Configure o relatório do Power BI da **Contabilidade de estoque global** seguindo estas etapas:</span><span class="sxs-lookup"><span data-stu-id="43901-120">Configure the **Global Inventory Accounting** Power BI report by following these steps:</span></span>

    1. <span data-ttu-id="43901-121">Vá para **Meu espaço de trabalho**, encontre o conjunto de dados para Contabilidade de estoque global e, em seguida, no menu **Opções**, selecione **Configurações**.</span><span class="sxs-lookup"><span data-stu-id="43901-121">Go to **My workspace**, find the dataset for Global Inventory Accounting, and then, on the **Options** menu, select **Settings**.</span></span>
    1. <span data-ttu-id="43901-122">Em **Configurações da Contabilidade de estoque global**, expanda **Parâmetros** e atualize todos os parâmetros conforme necessário.</span><span class="sxs-lookup"><span data-stu-id="43901-122">In **Settings for Global inventory accounting**, expand **Parameters**, and update all parameters as required.</span></span>

1. <span data-ttu-id="43901-123">Registre o aplicativo conforme descrito em [Configurar integração do PowerBI.com](../../fin-ops-core/dev-itpro/analytics/configure-power-bi-integration.md#registration-process).</span><span class="sxs-lookup"><span data-stu-id="43901-123">Register the application as described in [Configure PowerBI.com integration](../../fin-ops-core/dev-itpro/analytics/configure-power-bi-integration.md#registration-process).</span></span>
1. <span data-ttu-id="43901-124">Para integrar o arquivo de relatório do Power BI da **Contabilidade de estoque global** no Dynamics 365 Supply Chain Management, siga estas etapas:</span><span class="sxs-lookup"><span data-stu-id="43901-124">Integrate the **Global Inventory Accounting** Power BI report file into Dynamics 365 Supply Chain Management by following these steps:</span></span>

    1. <span data-ttu-id="43901-125">Vá para **Administração de sistema \> Configurar \> Configuração do PowerBI.com**.</span><span class="sxs-lookup"><span data-stu-id="43901-125">Go to **System administration \> Setup \> PowerBI.com configuration**.</span></span>
    1. <span data-ttu-id="43901-126">Selecione **Editar**.</span><span class="sxs-lookup"><span data-stu-id="43901-126">Select **Edit**.</span></span>
    1. <span data-ttu-id="43901-127">Selecione **Habilitar integração do PowerBI.Com**.</span><span class="sxs-lookup"><span data-stu-id="43901-127">Select **Enable PowerBI.Com integration**.</span></span>
    1. <span data-ttu-id="43901-128">No campo **ID do aplicativo**, insira o ID do aplicativo.</span><span class="sxs-lookup"><span data-stu-id="43901-128">In the **Application ID** field, enter the application ID.</span></span>
    1. <span data-ttu-id="43901-129">No campo **Chave de aplicativo**, insira a chave do aplicativo.</span><span class="sxs-lookup"><span data-stu-id="43901-129">In the **Application key** field, enter the application key.</span></span>
    1. <span data-ttu-id="43901-130">Selecione **Salvar**.</span><span class="sxs-lookup"><span data-stu-id="43901-130">Select **Save**.</span></span>

1. <span data-ttu-id="43901-131">Atualize a página para que a caixa de diálogo de login no Power BI seja exibida.</span><span class="sxs-lookup"><span data-stu-id="43901-131">Refresh the page so that the Power BI sign-in dialog box appears.</span></span>
1. <span data-ttu-id="43901-132">Na guia **Opções**, selecione **Abrir catálogo de relatórios** e selecione o arquivo de relatório do Power BI da **Contabilidade de estoque global** que você carregou anteriormente.</span><span class="sxs-lookup"><span data-stu-id="43901-132">On the **Options** tab, select **Open report catalog**, and then select the **Global Inventory Accounting** Power BI report file that you uploaded earlier.</span></span>
1. <span data-ttu-id="43901-133">Atualize a página.</span><span class="sxs-lookup"><span data-stu-id="43901-133">Refresh the page.</span></span> <span data-ttu-id="43901-134">Você deverá ver que seu relatório foi adicionado.</span><span class="sxs-lookup"><span data-stu-id="43901-134">You should see that your report has been added.</span></span>
1. <span data-ttu-id="43901-135">Em link **Relatórios do Power BI**, selecione o link **Contabilidade de estoque global**.</span><span class="sxs-lookup"><span data-stu-id="43901-135">Under **Power BI reports**, select the **Global Inventory Accounting** link.</span></span>

<span data-ttu-id="43901-136">Para obter mais informações, consulte [Configurar sua integração do PowerBI.com](../../fin-ops-core/dev-itpro/analytics/configure-power-bi-integration.md).</span><span class="sxs-lookup"><span data-stu-id="43901-136">For more information, see [Configure PowerBI.com integration](../../fin-ops-core/dev-itpro/analytics/configure-power-bi-integration.md).</span></span>
