---
title: Habilitar e configurar encargos automáticos por canal
description: Este tópico explica como habilitar e configurar encargos automáticos por canal no Microsoft Dynamics 365 Commerce.
author: gvrmohanreddy
manager: annbe
ms.date: 03/30/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-commerce
ms.technology: ''
audience: Application User
ms.reviewer: v-chgri
ms.search.region: Global
ms.author: gmohanv
ms.search.validFrom: 2020-03-01
ms.dyn365.ops.version: 10.0.10
ms.openlocfilehash: d37b2b785dd29850dcd02d0905e5872445384990
ms.sourcegitcommit: 38d40c331c8894acb7b119c5073e3088b54776c1
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/15/2021
ms.locfileid: "4993719"
---
# <a name="enable-and-configure-auto-charges-by-channel"></a><span data-ttu-id="32a9c-103">Habilitar e configurar encargos automáticos por canal</span><span class="sxs-lookup"><span data-stu-id="32a9c-103">Enable and configure auto charges by channel</span></span>

<span data-ttu-id="32a9c-104">Este tópico explica como habilitar e configurar encargos automáticos por canal no Microsoft Dynamics 365 Commerce.</span><span class="sxs-lookup"><span data-stu-id="32a9c-104">This topic explains how to enable and configure automatic charges (auto charges) by channel in Microsoft Dynamics 365 Commerce.</span></span>

## <a name="overview"></a><span data-ttu-id="32a9c-105">Visão Geral</span><span class="sxs-lookup"><span data-stu-id="32a9c-105">Overview</span></span>

<span data-ttu-id="32a9c-106">Você pode ter situações nas quais as taxas de reciclagem ou outras taxas devem ser aplicadas a um grupo de produtos vendidos em todas ou em algumas lojas em um estado específico (por exemplo, Califórnia).</span><span class="sxs-lookup"><span data-stu-id="32a9c-106">You might have scenarios where recycling fees or other fees must be applied to a group of products that are sold in all or some stores in a specific state (for example, California).</span></span> <span data-ttu-id="32a9c-107">O recurso **Habilitar os encargos automáticos de filtro por canal** no Commerce permite que você especifique encargos automáticos por canal (por exemplo, um canal físico específico).</span><span class="sxs-lookup"><span data-stu-id="32a9c-107">The **Enable filter auto charges by channel** feature in Commerce lets you specify auto charges by channel (for example, a specific brick-and-mortar channel).</span></span> <span data-ttu-id="32a9c-108">Este recurso está disponível no Dynamics 365 Commerce versões 10.0.10 e posterior.</span><span class="sxs-lookup"><span data-stu-id="32a9c-108">This feature is available in Dynamics 365 Commerce version 10.0.10 and later.</span></span>

<span data-ttu-id="32a9c-109">Para habilitar e configurar encargos automáticos por canal, você deve concluir as seguintes tarefas:</span><span class="sxs-lookup"><span data-stu-id="32a9c-109">To enable and configure auto charges by channel, you must complete the following tasks:</span></span>

- <span data-ttu-id="32a9c-110">Ative o recurso **Habilitar encargos automáticos de filtro por canal**.</span><span class="sxs-lookup"><span data-stu-id="32a9c-110">Turn on the **Enable filter auto charges by channel** feature.</span></span>
- <span data-ttu-id="32a9c-111">Configurar a finalidade da hierarquia da organização.</span><span class="sxs-lookup"><span data-stu-id="32a9c-111">Configure the organization hierarchy purpose.</span></span>
- <span data-ttu-id="32a9c-112">Definir encargos automáticos por canal.</span><span class="sxs-lookup"><span data-stu-id="32a9c-112">Define auto charges by channel.</span></span>

> [!NOTE]
> <span data-ttu-id="32a9c-113">O recurso **Habilitar encargos automáticos de filtro por canal** funciona somente se o recurso de encargos automáticos avançados também estiver ativado.</span><span class="sxs-lookup"><span data-stu-id="32a9c-113">The **Enable filter auto charges by channel** feature works only if the advanced auto charges feature is also turned on.</span></span> <span data-ttu-id="32a9c-114">Para obter informações sobre como ativar o recurso de encargos automáticos avançados, consulte os [Encargos automáticos avançados do Omnicanal](omni-auto-charges.md).</span><span class="sxs-lookup"><span data-stu-id="32a9c-114">For information about how to turn on the advanced auto charges feature, see [Omni-channel advanced auto charges](omni-auto-charges.md).</span></span>

## <a name="turn-on-the-enable-filter-auto-charges-by-channel-feature"></a><span data-ttu-id="32a9c-115">Ative o recurso Habilitar encargos automáticos de filtro por canal</span><span class="sxs-lookup"><span data-stu-id="32a9c-115">Turn on the Enable filter auto charges by channel feature</span></span>

<span data-ttu-id="32a9c-116">Para habilitar os encargos automáticos por canal no Commerce, siga estas etapas.</span><span class="sxs-lookup"><span data-stu-id="32a9c-116">To enable auto charges by channel in Commerce, follow these steps.</span></span>

1. <span data-ttu-id="32a9c-117">Vá para **Administrador do sistema \> Espaços de trabalho \> Gerenciamento de recurso**.</span><span class="sxs-lookup"><span data-stu-id="32a9c-117">Go to **System administrator \> Workspaces \> Feature management**.</span></span>
1. <span data-ttu-id="32a9c-118">Na guia **Não habilitado**, na lista **Nome do recurso**, localize e selecione **Habilitar encargos automáticos do filtro por canal**.</span><span class="sxs-lookup"><span data-stu-id="32a9c-118">On the **Not enabled** tab, in the **Feature name** list, find and select **Enable filter auto charges by channel**.</span></span>
1. <span data-ttu-id="32a9c-119">No canto inferior direito, selecione **Habilitar agora**.</span><span class="sxs-lookup"><span data-stu-id="32a9c-119">In the lower-right corner, select **Enable now**.</span></span> <span data-ttu-id="32a9c-120">Depois que o recurso for ativado, ele será exibido na lista da guia **Tudo**.</span><span class="sxs-lookup"><span data-stu-id="32a9c-120">After the feature has been turned on, it will appear in the list on the **All** tab.</span></span>
1. <span data-ttu-id="32a9c-121">Vá para **Varejo e Comércio \> TI de Varejo e Comércio \> Agenda de distribuição**.</span><span class="sxs-lookup"><span data-stu-id="32a9c-121">Go to **Retail and Commerce \> Retail and Commerce IT \> Distribution schedule**.</span></span>
1. <span data-ttu-id="32a9c-122">No painel esquerdo, localize e selecione o trabalho **1110** (**Configuração global**).</span><span class="sxs-lookup"><span data-stu-id="32a9c-122">In the left pane, find and select the **1110** (**Global configuration**) job.</span></span>
1. <span data-ttu-id="32a9c-123">No painel de ações, selecione **Executar agora** para propagar as alterações de configuração.</span><span class="sxs-lookup"><span data-stu-id="32a9c-123">On the Action Pane, select **Run now** to propagate the configuration changes.</span></span>

> [!WARNING]
> <span data-ttu-id="32a9c-124">Se você desativar o recurso **Habilitar encargos automáticos de filtro por canal** depois de tê-lo usado, o campo **Relação de canal de varejo** em **Encargos automáticos** não será mais exibido e você perderá todas as configurações existentes.</span><span class="sxs-lookup"><span data-stu-id="32a9c-124">If you turn off the **Enable filter auto charges by channel** feature after you've already used it, the **Retail channel relation** field under **Auto charges** will no longer appear, and you will lose all existing configurations.</span></span> <span data-ttu-id="32a9c-125">Se a remoção das configurações de **Relação de canal de varejo** fizer com que as regras de encargos automáticos sejam duplicadas, uma tentativa de desativar o recurso falhará.</span><span class="sxs-lookup"><span data-stu-id="32a9c-125">If removal of the **Retail channel relation** configurations will cause auto charges rules to be duplicated, an attempt to turn off the feature will fail.</span></span> <span data-ttu-id="32a9c-126">Antes de desativar o recurso, verifique se todas as regras de encargos automáticos foram revisadas e faça as alterações necessárias.</span><span class="sxs-lookup"><span data-stu-id="32a9c-126">Before you turn off the feature, be sure to review all auto charges rules and make any required changes.</span></span>

## <a name="configure-the-organization-hierarchy-purpose"></a><span data-ttu-id="32a9c-127">Configurar a finalidade da hierarquia da organização</span><span class="sxs-lookup"><span data-stu-id="32a9c-127">Configure the organization hierarchy purpose</span></span>

<span data-ttu-id="32a9c-128">Uma nova finalidade de hierarquia da organização chamada **Encargo automático de varejo** foi criada para gerenciar a hierarquia de encargos automáticos por canal.</span><span class="sxs-lookup"><span data-stu-id="32a9c-128">A new organization hierarchy purpose that is named **Retail auto charge** has been created to manage the hierarchy for auto charges by channel.</span></span>

<span data-ttu-id="32a9c-129">Para atribuir uma hierarquia padrão a uma finalidade da hierarquia organizacional no Commerce, siga estas etapas.</span><span class="sxs-lookup"><span data-stu-id="32a9c-129">To assign a default hierarchy to an organization hierarchy purpose in Commerce, follow these steps.</span></span>
        
1. <span data-ttu-id="32a9c-130">Vá para **Administração da organização \> Organizações \> Finalidades de hierarquias de organização**.</span><span class="sxs-lookup"><span data-stu-id="32a9c-130">Go to **Organization administration \> Organizations \> Organization hierarchy purposes**.</span></span>
1. <span data-ttu-id="32a9c-131">No painel esquerdo, selecione **Encargo automático de varejo**.</span><span class="sxs-lookup"><span data-stu-id="32a9c-131">In the left pane, select **Retail auto charge**.</span></span>
1. <span data-ttu-id="32a9c-132">Em **Hierarquias atribuídas**, selecione **Adicionar**.</span><span class="sxs-lookup"><span data-stu-id="32a9c-132">Under **Assigned hierarchies**, select **Add**.</span></span>
1. <span data-ttu-id="32a9c-133">Na caixa de diálogo **Hierarquias da organização**, selecione uma hierarquia da organização (por exemple, **Lojas de varejo por região**), e selecione **OK**.</span><span class="sxs-lookup"><span data-stu-id="32a9c-133">In the **Organization hierarchies** dialog box, select an organization hierarchy (for example, **Retail Stores by Region**), and then select **OK**.</span></span>
1. <span data-ttu-id="32a9c-134">Em **Hierarquias atribuídas**, selecione **Definir como padrão**.</span><span class="sxs-lookup"><span data-stu-id="32a9c-134">Under **Assigned hierarchies**, select **Set as default**.</span></span>
1. <span data-ttu-id="32a9c-135">Vá para **Varejo e Comércio \> TI de Varejo e Comércio \> Agenda de distribuição**.</span><span class="sxs-lookup"><span data-stu-id="32a9c-135">Go to **Retail and Commerce \> Retail and Commerce IT \> Distribution schedule**.</span></span>
1. <span data-ttu-id="32a9c-136">No painel esquerdo, localize e selecione o trabalho **1040** (**Produtos**).</span><span class="sxs-lookup"><span data-stu-id="32a9c-136">In the left pane, find and select the **1040** (**Products**) job.</span></span>
1. <span data-ttu-id="32a9c-137">No painel de ação, selecione **Executar Agora**.</span><span class="sxs-lookup"><span data-stu-id="32a9c-137">On the Action Pane, select **Run now**.</span></span>
1. <span data-ttu-id="32a9c-138">Repita as duas etapas anteriores para executar os trabalhos **1070** (**Configuração de canal**) e **1110** (**Configuração global**).</span><span class="sxs-lookup"><span data-stu-id="32a9c-138">Repeat the previous two steps to run the **1070** (**Channel configuration**) and **1110** (**Global configuration**) jobs.</span></span>

![Configuração da organização de encargo automático de varejo finalidade da hierarquia](media/Auto-charges-org-hierarchy-purpose.png)

## <a name="define-auto-charges-by-channel"></a><span data-ttu-id="32a9c-140">Definir encargos automáticos por canal</span><span class="sxs-lookup"><span data-stu-id="32a9c-140">Define auto charges by channel</span></span>

<span data-ttu-id="32a9c-141">Depois que você ativou o recurso **Habilitar o filtro de encargos automáticos por canal** e configurou a finalidade da hierarquia da organização **Encargo automático de varejo**, os encargos automáticos por canal podem ser definidos no nível do cabeçalho da ordem ou no nível da linha da ordem.</span><span class="sxs-lookup"><span data-stu-id="32a9c-141">After you've turned on the **Enable filter auto charges by channel** feature and configured the **Retail auto charge** organization hierarchy purpose, auto charges by channel can be defined at either the order header level or the order line level.</span></span>

<span data-ttu-id="32a9c-142">Para definir os encargos automáticos por canal no Commerce, siga estas etapas.</span><span class="sxs-lookup"><span data-stu-id="32a9c-142">To define auto charges by channel in Commerce, follow these steps.</span></span>

1. <span data-ttu-id="32a9c-143">Vá para **Contas a receber \> Configuração de encargos \> Encargos automáticos**.</span><span class="sxs-lookup"><span data-stu-id="32a9c-143">Go to **Accounts receivable \> Charges setup \> Auto charges**.</span></span>
1. <span data-ttu-id="32a9c-144">No painel à esquerda, no campo **Nível**, selecione **Cabeçalho** ou **Linha**, dependendo de seus requisitos empresariais.</span><span class="sxs-lookup"><span data-stu-id="32a9c-144">In the left pane, in the **Level** field, select either **Header** or **Line**, depending on your business requirements.</span></span>
1. <span data-ttu-id="32a9c-145">No campo **Código de canal de varejo**, selecione o código de canal apropriado (por exemplo **Tabela** ou **Grupo**).</span><span class="sxs-lookup"><span data-stu-id="32a9c-145">In the **Retail channel code** field, select the appropriate channel code (for example, **Table** or **Group**).</span></span> <span data-ttu-id="32a9c-146">Se a configuração padrão, **Tudo** for usada, as regras de encargos serão aplicadas a todos os canais.</span><span class="sxs-lookup"><span data-stu-id="32a9c-146">If the default setting, **All**, is used, charge rules are applied to all channels.</span></span>

    - <span data-ttu-id="32a9c-147">Se você selecionar **Grupo**, certifique-se de que o grupo de encargos de canal de varejo foi criado em **Varejo e Commerce \> Configuração do canal \> Encargos \> Grupos de encargo de canal de varejo**.</span><span class="sxs-lookup"><span data-stu-id="32a9c-147">If you select **Group**, make sure that a retail channel charges group is created at **Retail and Commerce \> Channel setup \> Charges \> Retail channel charge groups**.</span></span>
    - <span data-ttu-id="32a9c-148">Se você selecionar **Tabela** poderá selecionar um canal específico (por exemplo, **San Francisco**) no campo **Relação de canal de varejo**.</span><span class="sxs-lookup"><span data-stu-id="32a9c-148">If you select **Table**, you can select a specific channel (for example, **San Francisco**) in the **Retail channel relation** field.</span></span>

1. <span data-ttu-id="32a9c-149">Vá para **Varejo e Comércio \> TI de Varejo e Comércio \> Agenda de distribuição**.</span><span class="sxs-lookup"><span data-stu-id="32a9c-149">Go to **Retail and Commerce \> Retail and Commerce IT \> Distribution schedule**.</span></span>
1. <span data-ttu-id="32a9c-150">No painel esquerdo, localize e selecione o trabalho **1040** (**Produtos**).</span><span class="sxs-lookup"><span data-stu-id="32a9c-150">In the left pane, find and select the **1040** (**Products**) job.</span></span>
1. <span data-ttu-id="32a9c-151">No painel de ação, selecione **Executar Agora**.</span><span class="sxs-lookup"><span data-stu-id="32a9c-151">On the Action Pane, select **Run now**.</span></span>
1. <span data-ttu-id="32a9c-152">Repita as duas etapas anteriores para executar os trabalhos **1070** (**Configuração de canal**) e **1110** (**Configuração global**).</span><span class="sxs-lookup"><span data-stu-id="32a9c-152">Repeat the previous two steps to run the **1070** (**Channel configuration**) and **1110** (**Global configuration**) jobs.</span></span>
    
![Encargos automáticos definidos por canal](media/Auto-charges-line-charge-by-channel.png)

## <a name="example-scenario"></a><span data-ttu-id="32a9c-154">Cenário de exemplo</span><span class="sxs-lookup"><span data-stu-id="32a9c-154">Example scenario</span></span>

<span data-ttu-id="32a9c-155">O exemplo a seguir destaca as etapas necessárias para configurar um produto, de forma que as taxas de reciclagem sejam cobradas quando o produto é vendido por meio de um canal físico e de San Francisco.</span><span class="sxs-lookup"><span data-stu-id="32a9c-155">The following example outlines the steps that are required to configure a product so that recycling fees are charged when the product is sold through a San Francisco brick-and-mortar channel.</span></span> <span data-ttu-id="32a9c-156">O exemplo também mostra como os encargos automáticos aparecem no aplicativo de ponto de venda (POS) comercial.</span><span class="sxs-lookup"><span data-stu-id="32a9c-156">The example also shows how the auto charges appear in the Commerce point of sale (POS) application.</span></span>

<span data-ttu-id="32a9c-157">A organização define um código de encargos denominado **RECICLAR**, conforme mostrado na ilustração a seguir.</span><span class="sxs-lookup"><span data-stu-id="32a9c-157">The organization defines a charges code that is named **RECYCLE**, as shown in the following illustration.</span></span>

![Código de encargos RECICLAR](media/Auto-charges-charge-code.png)

<span data-ttu-id="32a9c-159">Um encargo automático é criado no nível da linha.</span><span class="sxs-lookup"><span data-stu-id="32a9c-159">An auto charge is created at the line level.</span></span> <span data-ttu-id="32a9c-160">Tem as seguintes configurações:</span><span class="sxs-lookup"><span data-stu-id="32a9c-160">It has the following configuration:</span></span>

- <span data-ttu-id="32a9c-161">O campo **Código de conta** está definido como **Tudo**.</span><span class="sxs-lookup"><span data-stu-id="32a9c-161">The **Account code** field is set to **All**.</span></span>
- <span data-ttu-id="32a9c-162">O campo **Item de conta** está definido como **Tabela**.</span><span class="sxs-lookup"><span data-stu-id="32a9c-162">The **Item code** field is set to **Table**.</span></span>
- <span data-ttu-id="32a9c-163">O campo **Relação de itens** está definido como ID do produto **91001**.</span><span class="sxs-lookup"><span data-stu-id="32a9c-163">The **Item relation** field is set to product ID **91001**.</span></span>
- <span data-ttu-id="32a9c-164">O campo **Modo de código de entrega** está definido como **Tudo**.</span><span class="sxs-lookup"><span data-stu-id="32a9c-164">The **Mode of delivery code** field is set to **All**.</span></span>
- <span data-ttu-id="32a9c-165">O campo **Código de canal de varejo** está definido como **Tabela**.</span><span class="sxs-lookup"><span data-stu-id="32a9c-165">The **Retail channel code** field is set to **Table**.</span></span>
- <span data-ttu-id="32a9c-166">O campo **Relação de canal de varejo** está definido como a loja **San Francisco**.</span><span class="sxs-lookup"><span data-stu-id="32a9c-166">The **Retail channel relation** field is set to the **San Francisco** store.</span></span>

<span data-ttu-id="32a9c-167">Uma linha de encargos automáticos é criada.</span><span class="sxs-lookup"><span data-stu-id="32a9c-167">An auto charges line is created.</span></span> <span data-ttu-id="32a9c-168">Tem as seguintes configurações:</span><span class="sxs-lookup"><span data-stu-id="32a9c-168">It has the following configuration:</span></span>

- <span data-ttu-id="32a9c-169">O campo **Moeda** é definido como **USD**.</span><span class="sxs-lookup"><span data-stu-id="32a9c-169">The **Currency** field is set to **USD**.</span></span>
- <span data-ttu-id="32a9c-170">O campo **Código de encargos** está definido como **RECICLAR**.</span><span class="sxs-lookup"><span data-stu-id="32a9c-170">The **Charges code** field is set to **RECYCLE**.</span></span>
- <span data-ttu-id="32a9c-171">O campo **Categoria** é definido como **Fixo**.</span><span class="sxs-lookup"><span data-stu-id="32a9c-171">The **Category** field is set to **Fixed**.</span></span>
- <span data-ttu-id="32a9c-172">O campo **Encargos** é definido como **$6,25**.</span><span class="sxs-lookup"><span data-stu-id="32a9c-172">The **Charges** field is set to **$6.25**.</span></span>

![Configuração do encargo automático de nível de linha e linha de encargos automáticos](media/Auto-charges-recyclingfee-line-fee.png)

<span data-ttu-id="32a9c-174">No aplicativo POS, uma ordem de venda é criada no canal de armazenamento **San Francisco**.</span><span class="sxs-lookup"><span data-stu-id="32a9c-174">In the POS application, a sales order is created in the **San Francisco** store channel.</span></span> <span data-ttu-id="32a9c-175">A linha **Encargos** mostra a taxa de reciclagem de **$6,25**.</span><span class="sxs-lookup"><span data-stu-id="32a9c-175">The **Charges** line shows the recycling fee of **$6.25**.</span></span>

<span data-ttu-id="32a9c-176">Ao selecionar **Opções de transação \> Encargos \> Gerenciar encargos** no aplicativo PDV, você pode visualizar o código de encargos e descrição da taxa de reciclagem.</span><span class="sxs-lookup"><span data-stu-id="32a9c-176">By selecting **Transaction options \> Charges \> Manage charges** in the POS application, you can view the charges code and description for the recycling fee.</span></span>

![Taxa de reciclagem no aplicativo PDV](media/pos-auto-charges-recyclingfee-line-fee.png)

## <a name="additional-resources"></a><span data-ttu-id="32a9c-178">Recursos adicionais</span><span class="sxs-lookup"><span data-stu-id="32a9c-178">Additional resources</span></span>

[<span data-ttu-id="32a9c-179">Encargos automáticos avançados de omnicanal</span><span class="sxs-lookup"><span data-stu-id="32a9c-179">Omni-channel advanced auto charges</span></span>](omni-auto-charges.md)

[<span data-ttu-id="32a9c-180">Ratear encargos do cabeçalho para as linhas de vendas correspondentes</span><span class="sxs-lookup"><span data-stu-id="32a9c-180">Prorate header charges to matching sales lines</span></span>](pro-rate-charges-matching-lines.md)
