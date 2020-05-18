---
title: Solucionar problemas durante a configuração inicial
description: Este tópico fornece informações sobre como solucionar problemas que podem ajudá-lo a corrigir problemas que podem ocorrer durante a configuração inicial da integração entre aplicativos Finance and Operations e Common Data Service.
author: RamaKrishnamoorthy
manager: AnnBe
ms.date: 03/16/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ''
audience: Application User, IT Pro
ms.reviewer: rhaertle
ms.search.scope: Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: global
ms.search.industry: ''
ms.author: ramasri
ms.dyn365.ops.version: ''
ms.search.validFrom: 2020-03-16
ms.openlocfilehash: 76e104c9ebd7db7ebcbaf214e84be6c4353e8a73
ms.sourcegitcommit: e06da171b9cba8163893e30244c52a9ce0901146
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/21/2020
ms.locfileid: "3275432"
---
# <a name="troubleshoot-issues-during-initial-setup"></a><span data-ttu-id="aefa6-103">Solucionar problemas durante a configuração inicial</span><span class="sxs-lookup"><span data-stu-id="aefa6-103">Troubleshoot issues during initial setup</span></span>

[!include [banner](../../includes/banner.md)]



<span data-ttu-id="aefa6-104">Este tópico fornece informações de solução de problemas para integração de gravação dupla entre aplicativos do Finance and Operations e o Common Data Service.</span><span class="sxs-lookup"><span data-stu-id="aefa6-104">This topic provides troubleshooting information for dual-write integration between Finance and Operations apps and Common Data Service.</span></span> <span data-ttu-id="aefa6-105">Especificamente, ele fornece informações sobre como solucionar problemas que podem ajudá-lo a corrigir problemas que podem ocorrer durante a configuração inicial da integração de gravação dupla.</span><span class="sxs-lookup"><span data-stu-id="aefa6-105">Specifically, it provides information that can help you fix issues that might occur during the initial setup of dual-write integration.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="aefa6-106">Alguns dos problemas que este tópico aborda podem exigir a função de administrador do sistema ou as credenciais de administrador do locatário Microsoft Azure Active Directory (Azure AD).</span><span class="sxs-lookup"><span data-stu-id="aefa6-106">Some of the issues that this topic addresses might require either the system admin role or Microsoft Azure Active Directory (Azure AD) tenant admin credentials.</span></span> <span data-ttu-id="aefa6-107">A seção para cada problema explica se uma função ou credenciais específicas são necessárias.</span><span class="sxs-lookup"><span data-stu-id="aefa6-107">The section for each issue explains whether a specific role or credentials are required.</span></span>

## <a name="you-cant-link-a-finance-and-operations-app-to-common-data-service"></a><span data-ttu-id="aefa6-108">Não é possível vincular um aplicativo Finance and Operations ao Common Data Service</span><span class="sxs-lookup"><span data-stu-id="aefa6-108">You can't link a Finance and Operations app to Common Data Service</span></span>

<span data-ttu-id="aefa6-109">**Função necessária para configurar a gravação dupla:** administrador do sistema nos aplicativos Finance and Operations e Common Data Service.</span><span class="sxs-lookup"><span data-stu-id="aefa6-109">**Required role to set up dual-write:** System administrator in Finance and Operations apps and Common Data Service.</span></span>

<span data-ttu-id="aefa6-110">Erros na página **Configurar link para Common Data Service** geralmente são causados por configuração incompleta ou problemas de permissão.</span><span class="sxs-lookup"><span data-stu-id="aefa6-110">Errors on the **Setup link to Common Data Service** page are usually caused by incomplete setup or permissions issues.</span></span> <span data-ttu-id="aefa6-111">Verifique se toda a verificação de integridade foi aprovada na página **Configurar link para Common Data Service**, conforme mostrado na ilustração a seguir.</span><span class="sxs-lookup"><span data-stu-id="aefa6-111">Make sure that the whole health check passes on the **Setup link to Common Data Service** page, as shown in the following illustration.</span></span> <span data-ttu-id="aefa6-112">Não é possível vincular a dupla gravação, a menos que toda a verificação de integridade seja aprovada.</span><span class="sxs-lookup"><span data-stu-id="aefa6-112">You can't link dual-write unless the whole health check passes.</span></span>

![Verificação bem-sucedida de integridade](media/health_check.png)

<span data-ttu-id="aefa6-114">Você deve ter credenciais de administração de locatário do Azure AD para vincular os ambientes Finance and Operations e Common Data Service.</span><span class="sxs-lookup"><span data-stu-id="aefa6-114">You must have Azure AD tenant admin credentials to link the Finance and Operations and Common Data Service environments.</span></span> <span data-ttu-id="aefa6-115">Depois de vincular os ambientes, os usuários podem fazer login usando suas credenciais de conta e atualizar um mapa de entidade existente.</span><span class="sxs-lookup"><span data-stu-id="aefa6-115">After you link the environments, users can sign in by using their account credentials and update an existing entity map.</span></span>

## <a name="error-when-you-open-the-link-to-common-data-service-page"></a><span data-ttu-id="aefa6-116">Erro ao abrir o link para a página do Common Data Service</span><span class="sxs-lookup"><span data-stu-id="aefa6-116">Error when you open the Link to Common Data Service page</span></span>

<span data-ttu-id="aefa6-117">**Credenciais necessárias para corrigir o problema:** administrador de locatário do Azure AD</span><span class="sxs-lookup"><span data-stu-id="aefa6-117">**Required credentials to fix the issue:** Azure AD tenant admin</span></span>

<span data-ttu-id="aefa6-118">Você pode receber a seguinte mensagem de erro ao abrir a página **Link para Common Data Service** em um aplicativo Finance and Operations:</span><span class="sxs-lookup"><span data-stu-id="aefa6-118">You might receive the following error message when you open the **Link to Common Data Service** page in a Finance and Operations app:</span></span>

<span data-ttu-id="aefa6-119">*O código de status de resposta não indica êxito: 404 (Não encontrado).*</span><span class="sxs-lookup"><span data-stu-id="aefa6-119">*Response status code does not indicate success: 404 (Not Found).*</span></span>

<span data-ttu-id="aefa6-120">Este erro ocorre quando a etapa de consentimento não foi concluída.</span><span class="sxs-lookup"><span data-stu-id="aefa6-120">This error occurs when the consent step hasn't been completed.</span></span> <span data-ttu-id="aefa6-121">Para validar se a etapa de consentimento foi concluída, efetue login no portal do Azure.com usando a conta de administrador de locatário do Azure AD e verifique se o aplicativo de terceiros que tem a ID **33976c19-1db5-4c02-810e-c243db79efde** aparece na lista de **aplicativos corporativos do Azure AD**.</span><span class="sxs-lookup"><span data-stu-id="aefa6-121">To validate whether the consent step has been completed, sign in to portal.Azure.com by using the Azure AD tenant admin account, and see whether the third-party app that has the ID **33976c19-1db5-4c02-810e-c243db79efde** appears in the Azure AD **Enterprise applications** list.</span></span> <span data-ttu-id="aefa6-122">Se não tiver, você deverá fornecer consentimento ao aplicativo.</span><span class="sxs-lookup"><span data-stu-id="aefa6-122">If it doesn't, you must provide app consent.</span></span>

<span data-ttu-id="aefa6-123">Para fornecer consentimento ao aplicativo, siga estas etapas.</span><span class="sxs-lookup"><span data-stu-id="aefa6-123">To provide app consent, follow these steps.</span></span>

1. <span data-ttu-id="aefa6-124">Abra a seguinte URL usando suas credenciais administrativas.</span><span class="sxs-lookup"><span data-stu-id="aefa6-124">Open the following URL by using your admin credentials.</span></span> <span data-ttu-id="aefa6-125">Você deve receber um aviso de consentimento.</span><span class="sxs-lookup"><span data-stu-id="aefa6-125">You should be prompted for consent.</span></span>

    <https://login.microsoftonline.com/common/oauth2/authorize?client_id=33976c19-1db5-4c02-810e-c243db79efde&response_type=code&prompt=admin_consent>

2. <span data-ttu-id="aefa6-126">Selecione **Aceitar** para indicar que você está dando seu consentimento a instalação do aplicativo que tem a ID no seu locatário do **33976c19-1db5-4c02-810e-c243db79efde**.</span><span class="sxs-lookup"><span data-stu-id="aefa6-126">Select **Accept** to indicate that you're giving your consent to install the app that has the ID **33976c19-1db5-4c02-810e-c243db79efde** in your tenant.</span></span>

    > [!TIP]
    > <span data-ttu-id="aefa6-127">Este aplicativo é necessário para vincular aplicativos Common Data Service e Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="aefa6-127">This app is required to link Common Data Service and Finance and Operations apps.</span></span> <span data-ttu-id="aefa6-128">Se você tiver problemas com essa etapa, abra seu navegador no modo Incognito (no Google Chrome) ou no modo InPrivate (em Microsoft Edge).</span><span class="sxs-lookup"><span data-stu-id="aefa6-128">If you have trouble with this step, open your browser in incognito mode (in Google Chrome) or InPrivate mode (in Microsoft Edge).</span></span>

## <a name="verify-that-company-data-and-dual-write-teams-are-set-up-correctly-during-linking"></a><span data-ttu-id="aefa6-129">Verificar se os dados da empresa e as equipes de gravação dupla estão configurados corretamente durante a vinculação</span><span class="sxs-lookup"><span data-stu-id="aefa6-129">Verify that company data and dual-write teams are set up correctly during linking</span></span>

<span data-ttu-id="aefa6-130">Para garantir que a gravação dupla funcione corretamente, as empresas selecionadas durante a configuração são criadas no ambiente do Common Data Service.</span><span class="sxs-lookup"><span data-stu-id="aefa6-130">To ensure that dual-write works correctly, the companies that you select during configuration are created in the Common Data Service environment.</span></span> <span data-ttu-id="aefa6-131">Por padrão, essas empresas são apenas leitura e a propriedade **IsDualWriteEnable** está definida como **Verdadeira**.</span><span class="sxs-lookup"><span data-stu-id="aefa6-131">By default, these companies are read-only, and the **IsDualWriteEnable** property is set to **True**.</span></span> <span data-ttu-id="aefa6-132">Além disso, o proprietário e a equipe padrão da unidade de negócios são criados e incluem o nome da empresa.</span><span class="sxs-lookup"><span data-stu-id="aefa6-132">In addition, the default owning business unit owner and team are created and include the company name.</span></span> <span data-ttu-id="aefa6-133">Antes de habilitar os mapas, verifique se o proprietário padrão da equipe foi especificado.</span><span class="sxs-lookup"><span data-stu-id="aefa6-133">Before you enable the maps, verify that the default team owner is specified.</span></span> <span data-ttu-id="aefa6-134">Para encontrar a entidade **Empresas (Empresa\_CDM)**, siga estas etapas.</span><span class="sxs-lookup"><span data-stu-id="aefa6-134">To find the **Companies (CDM\_Company)** entity, follow these steps.</span></span>

1. <span data-ttu-id="aefa6-135">No aplicativo baseado em modelo no Dynamics 365, selecione o filtro no canto superior direito.</span><span class="sxs-lookup"><span data-stu-id="aefa6-135">In the model-driven app in Dynamics 365, select the filter in the upper-right corner.</span></span>
2. <span data-ttu-id="aefa6-136">Na lista suspensa, selecione **Empresa**.</span><span class="sxs-lookup"><span data-stu-id="aefa6-136">In the drop-down list, select **Company**.</span></span>
3. <span data-ttu-id="aefa6-137">Selecione **Executar** para ver os resultados.</span><span class="sxs-lookup"><span data-stu-id="aefa6-137">Select **Run** to see the results.</span></span>
4. <span data-ttu-id="aefa6-138">Selecione a empresa que estava vinculada quando você configurou a gravação dupla.</span><span class="sxs-lookup"><span data-stu-id="aefa6-138">Select the company that was linked when you configured dual-write.</span></span>
5. <span data-ttu-id="aefa6-139">Verifique se o campo **Equipe proprietária padrão** tem um valor.</span><span class="sxs-lookup"><span data-stu-id="aefa6-139">Verify that the **Default owning team** field has a value.</span></span> <span data-ttu-id="aefa6-140">Na ilustração a seguir, o campo **Padrão de propriedade da equipe** é definido como **Gravação dupla USMF**.</span><span class="sxs-lookup"><span data-stu-id="aefa6-140">In the following illustration, the **Default owning team** field is set to **USMF Dual Write**.</span></span>

    ![Verificando a equipe proprietária padrão](media/default_owning_team.png)

## <a name="find-the-limit-on-the-number-of-legal-entities-or-companies-that-can-be-linked-for-dual-write"></a><span data-ttu-id="aefa6-142">Encontre o limite para o número de entidades legais ou empresas que podem ser vinculadas para gravação dupla</span><span class="sxs-lookup"><span data-stu-id="aefa6-142">Find the limit on the number of legal entities or companies that can be linked for dual-write</span></span>

<span data-ttu-id="aefa6-143">A seguinte mensagem de erro pode ser exibida ao tentar habilitar os mapas:</span><span class="sxs-lookup"><span data-stu-id="aefa6-143">You might receive the following error message when you try to enable maps:</span></span>

<span data-ttu-id="aefa6-144">*Falha na gravação dupla - Falha no registro de plug-in: \[(Não foi possível obter mapa de partição para o projeto DWM-1ae35e60-4bc2-4905-88ea-69efd3b29260-7f12cb89-1550-42e2-858e-4761fc1443ea. Erro excede as partições máximas permitidas para mapeamento de DWM-1ae35e60-4bc2-4905-88ea-69efd3b29260-7f12cb89-1550-42e2-858e-4761fc1443ea)\], Um ou mais erros ocorreram.*</span><span class="sxs-lookup"><span data-stu-id="aefa6-144">*Dual write failure - Plugin registration failed: \[(Unable to get partition map for project DWM-1ae35e60-4bc2-4905-88ea-69efd3b29260-7f12cb89-1550-42e2-858e-4761fc1443ea. Error Exceeds the maximum partitions allowed for mapping DWM-1ae35e60-4bc2-4905-88ea-69efd3b29260-7f12cb89-1550-42e2-858e-4761fc1443ea)\], One or more errors occurred.*</span></span>

<span data-ttu-id="aefa6-145">O limite atual ao vincular os ambientes é de aproximadamente 40 entidades legais.</span><span class="sxs-lookup"><span data-stu-id="aefa6-145">The current limit when you link the environments is approximately 40 legal entities.</span></span> <span data-ttu-id="aefa6-146">Este erro ocorre se você tentar habilitar mapas, e mais de 40 entidades legais serão vinculadas entre os ambientes.</span><span class="sxs-lookup"><span data-stu-id="aefa6-146">This error occurs if you try to enable maps, and more than 40 legal entities are linked between the environments.</span></span>