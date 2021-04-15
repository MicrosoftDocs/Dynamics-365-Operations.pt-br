---
title: Criar entidades legais
description: Este tópico descreve como criar entidades legais no Microsoft Dynamics 365 Commerce, que devem ser criadas e configuradas antes da criação de canais.
author: samjarawan
ms.date: 01/27/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: v-chgri
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: samjar
ms.search.validFrom: 2020-01-20
ms.dyn365.ops.version: Release 10.0.8
ms.openlocfilehash: 225fd6a07fee29414ac30a4602b4dfccdc4d742b
ms.sourcegitcommit: 3cdc42346bb653c13ab33a7142dbb7969f1f6dda
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/31/2021
ms.locfileid: "5800605"
---
# <a name="create-legal-entities"></a><span data-ttu-id="4c7b4-103">Criar entidades legais</span><span class="sxs-lookup"><span data-stu-id="4c7b4-103">Create legal entities</span></span>

[!include [banner](includes/banner.md)]

<span data-ttu-id="4c7b4-104">Este tópico descreve como criar entidades legais no Microsoft Dynamics 365 Commerce, que devem ser criadas e configuradas antes da criação de canais.</span><span class="sxs-lookup"><span data-stu-id="4c7b4-104">This topic describes how to create legal entities in Microsoft Dynamics 365 Commerce, which must be created and configured before creating channels.</span></span>

<span data-ttu-id="4c7b4-105">Uma entidade legal é uma organização que tem uma estrutura legal registrada ou legislada.</span><span class="sxs-lookup"><span data-stu-id="4c7b4-105">A legal entity is an organization that has a registered or legislated legal structure.</span></span> <span data-ttu-id="4c7b4-106">As entidades legais podem participar de contratos legais e são obrigadas a preparar demonstrativos que registram seu desempenho.</span><span class="sxs-lookup"><span data-stu-id="4c7b4-106">Legal entities can enter into legal contracts and are required to prepare statements that report on their performance.</span></span>

<span data-ttu-id="4c7b4-107">Uma empresa é um tipo de entidade legal.</span><span class="sxs-lookup"><span data-stu-id="4c7b4-107">A company is a type of legal entity.</span></span> <span data-ttu-id="4c7b4-108">Atualmente, empresas são o único tipo de entidade legal que você pode criar, e cada entidade legal está associada a uma ID de empresa.</span><span class="sxs-lookup"><span data-stu-id="4c7b4-108">Currently, companies are the only kind of legal entity that you can create, and every legal entity is associated with a company ID.</span></span> <span data-ttu-id="4c7b4-109">Essa associação existe porque algumas áreas funcionais do programa usam uma ID de empresa, ou *DataAreaID*, nos modelos de dados.</span><span class="sxs-lookup"><span data-stu-id="4c7b4-109">This association exists because some functional areas in the program use a company ID, or *DataAreaId*, in their data models.</span></span> <span data-ttu-id="4c7b4-110">Nessas áreas funcionais, as empresas são usadas como um limite para a segurança dos dados.</span><span class="sxs-lookup"><span data-stu-id="4c7b4-110">In these functional areas, companies are used as a boundary for data security.</span></span> <span data-ttu-id="4c7b4-111">Os usuários podem acessar somente os dados da empresa que estão conectados no momento.</span><span class="sxs-lookup"><span data-stu-id="4c7b4-111">Users can access data only for the company that they are currently logged on to.</span></span> 

<span data-ttu-id="4c7b4-112">Ao criar um canal, você deve especificar a qual entidade legal ele pertence.</span><span class="sxs-lookup"><span data-stu-id="4c7b4-112">When creating a channel, you must specify which legal entity that channel belongs to.</span></span>

## <a name="create-a-new-legal-entity"></a><span data-ttu-id="4c7b4-113">Criar uma nova entidade legal</span><span class="sxs-lookup"><span data-stu-id="4c7b4-113">Create a new legal entity</span></span>

<span data-ttu-id="4c7b4-114">Para criar uma nova entidade legal no Dynamics 365 Commerce, siga estas etapas.</span><span class="sxs-lookup"><span data-stu-id="4c7b4-114">To create a new legal entity in Dynamics 365 Commerce, follow these steps.</span></span>

1. <span data-ttu-id="4c7b4-115">No painel de navegação, vá para **Módulos \> Configuração da sede \> Entidades legais**.</span><span class="sxs-lookup"><span data-stu-id="4c7b4-115">In the navigation pane, go to  **Modules \> Headquarters setup \> Legal entities**.</span></span>
1. <span data-ttu-id="4c7b4-116">No painel de ação, selecione **Novo**.</span><span class="sxs-lookup"><span data-stu-id="4c7b4-116">On the action pane, select **New**.</span></span> <span data-ttu-id="4c7b4-117">O painel **Nova entidade legal** é exibido à direita.</span><span class="sxs-lookup"><span data-stu-id="4c7b4-117">The **New legal entity** pane appears on the right.</span></span>
1. <span data-ttu-id="4c7b4-118">No campo **Nome**, insira um valor.</span><span class="sxs-lookup"><span data-stu-id="4c7b4-118">In the **Name** field, enter a value.</span></span>
1. <span data-ttu-id="4c7b4-119">No campo **Empresa**, insira um valor.</span><span class="sxs-lookup"><span data-stu-id="4c7b4-119">In the **Company** field, enter a value.</span></span>
1. <span data-ttu-id="4c7b4-120">No campo **País/região**, insira ou selecione um valor.</span><span class="sxs-lookup"><span data-stu-id="4c7b4-120">In the **Country/region** field, enter or select a value.</span></span>
1. <span data-ttu-id="4c7b4-121">Selecione **OK**.</span><span class="sxs-lookup"><span data-stu-id="4c7b4-121">Select **OK**.</span></span> 

   ![Criação de uma entidade legal](media/legal-entities.png)

1. <span data-ttu-id="4c7b4-123">Na seção **Geral**, forneça as seguintes informações gerais sobre a entidade legal::</span><span class="sxs-lookup"><span data-stu-id="4c7b4-123">In the **General** section, provide the following general information about the legal entity:</span></span> 
   1. <span data-ttu-id="4c7b4-124">Insira um nome de pesquisa, se um nome de pesquisa for necessário.</span><span class="sxs-lookup"><span data-stu-id="4c7b4-124">Enter a search name, if a search name is required.</span></span> <span data-ttu-id="4c7b4-125">Um nome de pesquisa é um nome alternativo que pode ser usado para procurar essa entidade legal.</span><span class="sxs-lookup"><span data-stu-id="4c7b4-125">A search name is an alternate name that can be used to search for this legal entity.</span></span> 
   1. <span data-ttu-id="4c7b4-126">Selecione se a entidade legal está sendo usada como uma empresa de consolidação.</span><span class="sxs-lookup"><span data-stu-id="4c7b4-126">Select whether this legal entity is being used as a consolidation company.</span></span>
   1. <span data-ttu-id="4c7b4-127">Selecione se essa entidade legal está sendo usada como uma empresa de eliminação.</span><span class="sxs-lookup"><span data-stu-id="4c7b4-127">Select whether this legal entity is being used as an elimination company.</span></span> 
   1. <span data-ttu-id="4c7b4-128">Selecione o **idioma padrão** para a entidade.</span><span class="sxs-lookup"><span data-stu-id="4c7b4-128">Select the **default language** for the entity.</span></span> 
   1. <span data-ttu-id="4c7b4-129">Selecione o **fuso horário** para a entidade.</span><span class="sxs-lookup"><span data-stu-id="4c7b4-129">Select the **time zone** for the entity.</span></span>
1. <span data-ttu-id="4c7b4-130">Na seção **Endereços**, selecione **Editar** para inserir informações de endereço, como nome da rua e número, CEP e cidade.</span><span class="sxs-lookup"><span data-stu-id="4c7b4-130">In the **Addresses** section, select **Edit** to enter address information, such as the street name and number, postal code, and city.</span></span>
1. <span data-ttu-id="4c7b4-131">Na seção **Informações de contato**, insira informações sobre os métodos de comunicação, como endereço de email, URLs e números de telefone.</span><span class="sxs-lookup"><span data-stu-id="4c7b4-131">In the **Contact information** section, enter information about methods of communication, such as email addresses, URLs, and telephone numbers.</span></span>
1. <span data-ttu-id="4c7b4-132">Na seção **Relatório estatutário**, insira os números de registro usados para os relatórios estatutários.</span><span class="sxs-lookup"><span data-stu-id="4c7b4-132">In the **Statutory reporting** section, enter the registration numbers that are used for statutory reporting.</span></span>
1. <span data-ttu-id="4c7b4-133">Na seção **Números de registro**, insira todas as informações exigidas pela entidade legal.</span><span class="sxs-lookup"><span data-stu-id="4c7b4-133">In the **Registration numbers** section, enter any information required by the legal entity.</span></span>
1. <span data-ttu-id="4c7b4-134">Na seção **Informações de conta bancária**, insira as contas bancárias e os números do banco da entidade legal.</span><span class="sxs-lookup"><span data-stu-id="4c7b4-134">In the **Bank account information** section, enter bank accounts and routing numbers for the legal entity.</span></span>
1. <span data-ttu-id="4c7b4-135">Na seção **Comércio exterior e logística**, insira as informações de remessa da entidade legal.</span><span class="sxs-lookup"><span data-stu-id="4c7b4-135">In the **Foreign trade and logistics** section, enter shipping information for the legal entity.</span></span>
1. <span data-ttu-id="4c7b4-136">Na seção **Sequências numéricas**, é possível exibir as sequências numéricas associadas à entidade legal.</span><span class="sxs-lookup"><span data-stu-id="4c7b4-136">In the **Number sequences** section, you can view the number sequences that are associated with the legal entity.</span></span> <span data-ttu-id="4c7b4-137">Ela estará vazia para começar.</span><span class="sxs-lookup"><span data-stu-id="4c7b4-137">This will be empty to start with.</span></span>
1. <span data-ttu-id="4c7b4-138">Na seção **Imagem no painel**, exiba ou altere a imagem do logotipo e do painel associada à entidade legal.</span><span class="sxs-lookup"><span data-stu-id="4c7b4-138">In the **Dashboard image** section, view or change the logo and dashboard image associated with the legal entity.</span></span>
1. <span data-ttu-id="4c7b4-139">Na seção **Registro de imposto**, insira os números de registro usados nos relatórios para as autoridades fiscais.</span><span class="sxs-lookup"><span data-stu-id="4c7b4-139">In the **Tax registration** section, enter the registration numbers that are used to report to tax authorities.</span></span>
1. <span data-ttu-id="4c7b4-140">Na seção **Imposto 1099**, insira a informação 1099 da entidade legal.</span><span class="sxs-lookup"><span data-stu-id="4c7b4-140">In the **Tax 1099** section, enter 1099 information for the legal entity.</span></span>
1. <span data-ttu-id="4c7b4-141">Na seção **Informações sobre impostos**, insira as informações fiscais da entidade legal.</span><span class="sxs-lookup"><span data-stu-id="4c7b4-141">In the **Tax invormation** section, enter tax information for the legal entity.</span></span>
1. <span data-ttu-id="4c7b4-142">Selecione **Salvar**.</span><span class="sxs-lookup"><span data-stu-id="4c7b4-142">Select **Save**.</span></span>

<span data-ttu-id="4c7b4-143">A imagem a seguir mostra detalhes de um exemplo de entidade legal.</span><span class="sxs-lookup"><span data-stu-id="4c7b4-143">The following image shows details of an example legal entity.</span></span>

![Seção Geral da entidade legal](media/legal-entities-general.png)
   
## <a name="additional-resources"></a><span data-ttu-id="4c7b4-145">Recursos adicionais</span><span class="sxs-lookup"><span data-stu-id="4c7b4-145">Additional resources</span></span>

[<span data-ttu-id="4c7b4-146">Visão geral de organizações e hierarquias organizacionais</span><span class="sxs-lookup"><span data-stu-id="4c7b4-146">Organizations and organizational hierarchies overview</span></span>](../fin-ops-core/fin-ops/organization-administration/organizations-organizational-hierarchies.md?toc=/dynamics365/commerce/toc.json)

[<span data-ttu-id="4c7b4-147">Planejar sua hierarquia da organização</span><span class="sxs-lookup"><span data-stu-id="4c7b4-147">Plan your organizational hierarchy</span></span>](../fin-ops-core/fin-ops/organization-administration/plan-organizational-hierarchy.md?toc=/dynamics365/commerce/toc.json)

[<span data-ttu-id="4c7b4-148">Hierarquias da organização</span><span class="sxs-lookup"><span data-stu-id="4c7b4-148">Organization hierarchies</span></span>](channels-org-hierarchies.md)

[<span data-ttu-id="4c7b4-149">Visão geral de canais</span><span class="sxs-lookup"><span data-stu-id="4c7b4-149">Channels overview</span></span>](channels-overview.md)

[<span data-ttu-id="4c7b4-150">Pré-requisitos de configuração de canal</span><span class="sxs-lookup"><span data-stu-id="4c7b4-150">Channel setup prerequisites</span></span>](channels-prerequisites.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]
