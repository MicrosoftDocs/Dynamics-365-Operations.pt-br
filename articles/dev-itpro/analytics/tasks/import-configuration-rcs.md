---
title: (ER) Importar configurações de RCS
description: Este tópico fornece informações sobre como um usuário pode importar uma nova versão de configuração de ER de RCS.
author: NickSelin
manager: AnnBe
ms.date: 07/03/2019
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: kfend
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2019-07-28
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: c458cf815837fb7e4688c4c0443b7962cac403a5
ms.sourcegitcommit: 287d78e6afdaf40c499e5db6c4531f2b26dbaca0
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/04/2019
ms.locfileid: "1726997"
---
# <a name="er-import-configurations-from-rcs"></a><span data-ttu-id="c500d-103">(ER) Importar configurações de RCS</span><span class="sxs-lookup"><span data-stu-id="c500d-103">(ER) Import configurations from RCS</span></span>

[!include [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="c500d-104">As etapas a seguir explicam como um usuário na função de Administrador do Sistema ou Desenvolvedor de Relatório Eletrônico pode importar uma nova versão de uma configuração de Relatório eletrônico (ER) do Regulatory Configuration Services (RCS) da Microsoft.</span><span class="sxs-lookup"><span data-stu-id="c500d-104">The following steps explain how a user in the System Administrator or Electronic Reporting Developer role can import a new version of an Electronic reporting (ER) configuration from Microsoft Regulatory Configuration Services (RCS).</span></span> <span data-ttu-id="c500d-105">Neste exemplo, você selecionará a versão da configuração de ER que foi configurada na instância de RCS e importá-la para a instância do Finance and Operations atual para a empresa exemplo, Litware, Inc. Estas etapas podem ser executadas em qualquer empresa porque as configurações de ER são compartilhadas entre empresas.</span><span class="sxs-lookup"><span data-stu-id="c500d-105">In this example, you will select the version of the ER configuration that has been configured in an RCS instance and import it into the current Finance and Operations instance for sample company, Litware, Inc. These steps can be performed in any company because ER configurations are shared among companies.</span></span> <span data-ttu-id="c500d-106">Para concluir estas etapas, primeiro é necessário concluir as etapas do tópico, [Criar um provedor de configuração e marcá-lo como ativo](er-configuration-provider-mark-it-active-2016-11.md).</span><span class="sxs-lookup"><span data-stu-id="c500d-106">To complete these steps, you must first complete the steps in the topic, [Create a configuration provider and mark it as active](er-configuration-provider-mark-it-active-2016-11.md).</span></span> <span data-ttu-id="c500d-107">Para concluir essas etapas, você também deve ter acesso a uma instância de RCS que contenha pelo menos uma configuração de ER no status **Concluído** ou **Compartilhado**.</span><span class="sxs-lookup"><span data-stu-id="c500d-107">To complete these steps, you must also have access to an RCS instance containing at least one ER configuration in either **Completed** or **Shared** status.</span></span>

1. <span data-ttu-id="c500d-108">Vá para **Administração da organização** > **Espaços de trabalho** > **Relatório eletrônico**.</span><span class="sxs-lookup"><span data-stu-id="c500d-108">Go to **Organization administration** > **Workspaces** > **Electronic reporting**.</span></span> 
2. <span data-ttu-id="c500d-109">Verifique se o provedor de configuração da empresa exemplo, Litware, Inc., está disponível e marcado como **Ativo**.</span><span class="sxs-lookup"><span data-stu-id="c500d-109">Make sure that the configuration provider for the sample company, Litware, Inc., is available and marked as **Active**.</span></span> <span data-ttu-id="c500d-110">Caso não veja este provedor de configuração, conclua as etapas do tópico, [Criar um provedor de configuração e marcá-lo como ativo](er-configuration-provider-mark-it-active-2016-11.md).</span><span class="sxs-lookup"><span data-stu-id="c500d-110">If you don’t see this configuration provider, complete the steps in the topic, [Create a configuration provider and mark it as active](er-configuration-provider-mark-it-active-2016-11.md).</span></span> 
3. <span data-ttu-id="c500d-111">Se não tiver o ambiente do RCS provisionado para sua empresa, clique no link externo **Regulatory services – Configuração** e siga as instruções para provisionar um ambiente do RCS.</span><span class="sxs-lookup"><span data-stu-id="c500d-111">If you have no RCS environment provisioned to your company, click **Regulatory services – Configuration** external link and follow the instructions to provision an RCS environment.</span></span> 
4. <span data-ttu-id="c500d-112">Clique em **Parâmetros de relatório eletrônico**.</span><span class="sxs-lookup"><span data-stu-id="c500d-112">Click **Electronic reporting parameters**.</span></span> 
5. <span data-ttu-id="c500d-113">Clique na guia **RCS**.</span><span class="sxs-lookup"><span data-stu-id="c500d-113">Click the **RCS** tab.</span></span> 
6. <span data-ttu-id="c500d-114">Se o ambiente de RCS já tiver sido provisionado para sua empresa, use as URLs apresentadas na página para acessá-lo.</span><span class="sxs-lookup"><span data-stu-id="c500d-114">If RCS environment has been already provisioned to your company, use presented on the page URLs to access it.</span></span> 
7. <span data-ttu-id="c500d-115">Feche a página.</span><span class="sxs-lookup"><span data-stu-id="c500d-115">Close the page.</span></span> 

## <a name="register-a-new-er-repository"></a><span data-ttu-id="c500d-116">Registre um novo repositório de ER.</span><span class="sxs-lookup"><span data-stu-id="c500d-116">Register a new ER repository.</span></span> 
1. <span data-ttu-id="c500d-117">Na lista, marque a linha selecionada.</span><span class="sxs-lookup"><span data-stu-id="c500d-117">In the list, mark the selected row.</span></span> 
2. <span data-ttu-id="c500d-118">Selecione o provedor Litware, Inc.</span><span class="sxs-lookup"><span data-stu-id="c500d-118">Select Litware, Inc. provider.</span></span> 
3. <span data-ttu-id="c500d-119">Clique em Repositórios.</span><span class="sxs-lookup"><span data-stu-id="c500d-119">Click Repositories.</span></span> 
4. <span data-ttu-id="c500d-120">Clique em Adicionar para abrir a caixa de diálogo suspensa.</span><span class="sxs-lookup"><span data-stu-id="c500d-120">Click Add to open the drop dialog.</span></span> 
5. <span data-ttu-id="c500d-121">No campo Tipo de repositório de configuração, insira 'RCS'.</span><span class="sxs-lookup"><span data-stu-id="c500d-121">In the Configuration repository type field, enter 'RCS'.</span></span> 
6. <span data-ttu-id="c500d-122">Clique em Criar repositório.</span><span class="sxs-lookup"><span data-stu-id="c500d-122">Click Create repository.</span></span> 
7. <span data-ttu-id="c500d-123">No campo de nome de exibição do ambiente do RCS, insira ou selecione um valor.</span><span class="sxs-lookup"><span data-stu-id="c500d-123">In the RCS environment display name field, enter or select a value.</span></span> 
8. <span data-ttu-id="c500d-124">Selecione a instância de RCS desejada.</span><span class="sxs-lookup"><span data-stu-id="c500d-124">Select the desired RCS instance.</span></span> <span data-ttu-id="c500d-125">Observe que você pode ter várias delas.</span><span class="sxs-lookup"><span data-stu-id="c500d-125">Note that you can have several of them.</span></span> 
9. <span data-ttu-id="c500d-126">Clique em OK.</span><span class="sxs-lookup"><span data-stu-id="c500d-126">Click OK.</span></span> 

## <a name="import-er-configurations-from-rcs-based-repository"></a><span data-ttu-id="c500d-127">Importe as configurações de ER do repositório com base em RCS</span><span class="sxs-lookup"><span data-stu-id="c500d-127">Import ER configurations from RCS based repository</span></span>
1. <span data-ttu-id="c500d-128">Clique em **Mostrar filtros**.</span><span class="sxs-lookup"><span data-stu-id="c500d-128">Click **Show filters**.</span></span> 
2. <span data-ttu-id="c500d-129">Insira um valor de filtro de "RCS" no campo **Nome** usando o operador de filtro **começa com**.</span><span class="sxs-lookup"><span data-stu-id="c500d-129">Enter a filter value of "RCS" on the **Name** field using the **begins with** filter operator.</span></span> 
3. <span data-ttu-id="c500d-130">Ao abrir o repositório selecionado, na página **Conectar aos Regulatory Configuration Services**, clique no link **Clique aqui para conectar-se aos Regulatory Configuration Services**.</span><span class="sxs-lookup"><span data-stu-id="c500d-130">When you open the selected repository, on the **Connect to Regulatory Configuration Services** page, click **Click here to connect to Regulatory Configuration Services** link.</span></span> 
4. <span data-ttu-id="c500d-131">Clique em **Abrir**.</span><span class="sxs-lookup"><span data-stu-id="c500d-131">Click **Open**.</span></span> 
5. <span data-ttu-id="c500d-132">Clique em **Fechar**.</span><span class="sxs-lookup"><span data-stu-id="c500d-132">Click **Close**.</span></span> 
6. <span data-ttu-id="c500d-133">Selecione a versão desejada da configuração de ER e clique em **Importar** para exibi-la na instância do Finance and Operations atual.</span><span class="sxs-lookup"><span data-stu-id="c500d-133">Select the desired version of ER configuration and click **Import** to bring it in the current Finance and Operations instance.</span></span>

