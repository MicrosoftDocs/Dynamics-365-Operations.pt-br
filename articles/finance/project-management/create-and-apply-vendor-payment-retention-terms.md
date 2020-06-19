---
title: Criar e aplicar condições de retenção de pagamento de fornecedor
description: Este tópico fornece informações sobre como configurar e manter condições de retenção para pagamentos de fornecedores.
author: kfend
manager: AnnBe
ms.date: 05/26/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
audience: Application User
ms.reviewer: kfend
ms.search.scope: Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.search.industry: Service industries
ms.author: v-radsh
ms.dyn365.ops.version: 7
ms.search.validFrom: 2019-01-15
ms.openlocfilehash: 0e14050a79220b5d02763a025040edb934489d00
ms.sourcegitcommit: cecd97fd74ff7b31f1a677e8fdf3e233aa28ef5a
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/28/2020
ms.locfileid: "3410193"
---
# <a name="create-and-apply-vendor-payment-retention-terms"></a><span data-ttu-id="a2a58-103">Criar e aplicar condições de retenção de pagamento de fornecedor</span><span class="sxs-lookup"><span data-stu-id="a2a58-103">Create and apply vendor payment retention terms</span></span>

[!include [banner](../includes/banner.md)] 

<span data-ttu-id="a2a58-104">A configuração de condições de retenção de pagamento de fornecedor para um projeto é útil quando sua organização deseja reter parte dos pagamentos feitos a um fornecedor.</span><span class="sxs-lookup"><span data-stu-id="a2a58-104">Setting up vendor payment retention terms for a project is useful when your organization wants to retain part of the payments made to a vendor.</span></span> <span data-ttu-id="a2a58-105">Por exemplo, quando você deseja reter o pagamento a um fornecedor até que os produtos entregues atendam às suas expectativas.</span><span class="sxs-lookup"><span data-stu-id="a2a58-105">For example, when you want to hold payment to a vendor until the products delivered meet your expectations.</span></span> <span data-ttu-id="a2a58-106">As condições de retenção de pagamento ao fornecedor podem ser especificadas quando você negocia um contrato com o fornecedor.</span><span class="sxs-lookup"><span data-stu-id="a2a58-106">Vendor payment retention terms can be specified when you negotiate a vendor contract.</span></span>

## <a name="create-vendor-payment-retention-terms"></a><span data-ttu-id="a2a58-107">Criar condições de retenção de pagamento ao fornecedor</span><span class="sxs-lookup"><span data-stu-id="a2a58-107">Create vendor payment retention terms</span></span>

<span data-ttu-id="a2a58-108">Você pode inserir a porcentagem do pagamento do fornecedor para retenção e a porcentagem dos valores retidos anteriormente a serem liberados.</span><span class="sxs-lookup"><span data-stu-id="a2a58-108">You can enter the percentage of vendor payment for retention and the percentage of the previously retained amounts to be released.</span></span> <span data-ttu-id="a2a58-109">Os valores serão retidos automaticamente nas faturas de fornecedor até que o contrato atinja o estado de conclusão específico.</span><span class="sxs-lookup"><span data-stu-id="a2a58-109">Amounts are automatically retained on vendor invoices until the contract reaches the specified state of completion.</span></span> <span data-ttu-id="a2a58-110">Depois de configurar as condições de retenção, você pode aplicá-las a qualquer projeto para esse fornecedor.</span><span class="sxs-lookup"><span data-stu-id="a2a58-110">After you set up the retention terms, you can apply them to any project for that vendor.</span></span>

<span data-ttu-id="a2a58-111">Use as etapas a seguir para configurar e manter condições de retenção para pagamentos de fornecedores.</span><span class="sxs-lookup"><span data-stu-id="a2a58-111">Use the following steps to set up and maintain retention terms for vendor payments.</span></span> 

1. <span data-ttu-id="a2a58-112">Vá para **Gerenciamento e contabilidade do projeto** > **Retenção** > **Condições de retenção de pagamento de fornecedor**.</span><span class="sxs-lookup"><span data-stu-id="a2a58-112">Go to **Project management and accounting** > **Retention** > **Vendor payment retention terms**.</span></span>
2. <span data-ttu-id="a2a58-113">Selecione **Novo** para adicionar uma nova condição de retenção do fornecedor.</span><span class="sxs-lookup"><span data-stu-id="a2a58-113">Select **New** to add a new vendor retention term.</span></span> <span data-ttu-id="a2a58-114">O valor da **ID da regra** da nova condição é inserida automaticamente.</span><span class="sxs-lookup"><span data-stu-id="a2a58-114">The **Rule ID** value for the new term is automatically entered.</span></span> 
3. <span data-ttu-id="a2a58-115">Insira uma breve descrição no campo **Descrição** e, na FastTab **Condições**, selecione **Adicionar linha** para inserir valores de condições para:</span><span class="sxs-lookup"><span data-stu-id="a2a58-115">Enter a brief description in the **Description** field, and on the **Terms** FastTab, select **Add line** to enter term values for the following:</span></span>

   - <span data-ttu-id="a2a58-116">**Porcentagem de unidades entregues**: insira uma porcentagem de conclusão da condição.</span><span class="sxs-lookup"><span data-stu-id="a2a58-116">**Percentage of units delivered**: Enter a percentage of completion for the term.</span></span> <span data-ttu-id="a2a58-117">Os valores serão retidos automaticamente nas faturas do fornecedor até que o estágio de projeto da conclusão seja igual à porcentagem especificada.</span><span class="sxs-lookup"><span data-stu-id="a2a58-117">Amounts are automatically retained on vendor invoices until the project stage of completion is equal to the specified percentage.</span></span> <span data-ttu-id="a2a58-118">Por exemplo, se você inserir 50,00, os valores serão retidos até que o projeto esteja 50% concluído.</span><span class="sxs-lookup"><span data-stu-id="a2a58-118">For example, if you enter 50.00, amounts are retained until the project is 50 percent completed.</span></span>
   - <span data-ttu-id="a2a58-119">**Porcentagem a reter**: insira uma porcentagem do valor da fatura do fornecedor a ser retido.</span><span class="sxs-lookup"><span data-stu-id="a2a58-119">**Percentage to retain**: Enter a percentage of the vendor invoice amount to be retained.</span></span> <span data-ttu-id="a2a58-120">Por exemplo, se você digitar 10,00 nesse campo, 10% do valor em uma fatura de fornecedor serão retidos até que o projeto atinja a porcentagem de conclusão definida no campo **Porcentagem de unidades entregues**.</span><span class="sxs-lookup"><span data-stu-id="a2a58-120">For example, if you enter 10.00, then 10 percent of the amount on a vendor invoice is retained until the project reaches the percentage of completion as set in the **Percentage of units delivered field**.</span></span>
   - <span data-ttu-id="a2a58-121">**Porcentagem a liberar**: selecione **Adicionar linha** para inserir uma porcentagem dos valores retidos anteriormente a serem liberados para o nível de conclusão do projeto selecionado.</span><span class="sxs-lookup"><span data-stu-id="a2a58-121">**Percentage to release**: Select **Add line** to enter a percentage of any previously retained amounts to be released for the selected level of project completion.</span></span>

> [!NOTE]
> <span data-ttu-id="a2a58-122">Se houver mais de uma etapa para diferentes níveis de conclusão de projeto, insira uma linha separada de condição de retenção do fornecedor para cada regra de retenção.</span><span class="sxs-lookup"><span data-stu-id="a2a58-122">If you have more than one milestone for different levels of project completion, enter a separate vendor retention term line for each retention rule.</span></span> <span data-ttu-id="a2a58-123">Cada linha pode especificar uma porcentagem de retenção diferente e uma porcentagem de liberação diferente para cada nível designado de conclusão do projeto.</span><span class="sxs-lookup"><span data-stu-id="a2a58-123">Each line can specify a different retention percentage and a different release percentage for each designated level of project completion.</span></span>

<span data-ttu-id="a2a58-124">Depois de criar condições de retenção de fornecedor para um fornecedor, você poderá as condições a um projeto.</span><span class="sxs-lookup"><span data-stu-id="a2a58-124">After you create vendor retention terms for a vendor, you can apply the terms to a project.</span></span>

## <a name="apply-vendor-retention-terms-to-a-project"></a><span data-ttu-id="a2a58-125">Aplique condições de retenção de fornecedor a um projeto</span><span class="sxs-lookup"><span data-stu-id="a2a58-125">Apply vendor retention terms to a project</span></span>

1. <span data-ttu-id="a2a58-126">Vá para **Gerenciamento e contabilidade do projeto** > **Projetos** > **Todos os projetos** e abra um projeto na página de listagem de projetos.</span><span class="sxs-lookup"><span data-stu-id="a2a58-126">Go to **Project management and accounting** > **Projects** > **All projects** and open a project from the project list page.</span></span>
2. <span data-ttu-id="a2a58-127">Na guia rápida **Contratos de fornecedor**, selecione **Adicionar linha**.</span><span class="sxs-lookup"><span data-stu-id="a2a58-127">On the **Vendor agreements** FastTab, select **Add line**.</span></span>
3. <span data-ttu-id="a2a58-128">No campo **Código da conta**, selecione uma das seguintes opções:</span><span class="sxs-lookup"><span data-stu-id="a2a58-128">In the **Account code field**, select one of the following options:</span></span> 

   - <span data-ttu-id="a2a58-129">**Tabela**: as condições de retenção de fornecedor se aplicam a um único fornecedor.</span><span class="sxs-lookup"><span data-stu-id="a2a58-129">**Table**: The vendor retention terms apply to a single vendor.</span></span>
   - <span data-ttu-id="a2a58-130">**Grupo**: as condições de retenção de fornecedor se aplicam a todos os fornecedores em um grupo de fornecedores.</span><span class="sxs-lookup"><span data-stu-id="a2a58-130">**Group**: The vendor retention terms apply to all vendors in a vendor group.</span></span>
   - <span data-ttu-id="a2a58-131">**Todos**: as condições de retenção de fornecedor se aplicam a todos os fornecedores.</span><span class="sxs-lookup"><span data-stu-id="a2a58-131">**All**: The vendor retention terms apply to all vendors.</span></span>

4. <span data-ttu-id="a2a58-132">No campo **Fornecedor/grupo de fornecedores**, selecione o fornecedor ou grupo de fornecedores aos quais as condições de retenção de fornecedor se aplicam.</span><span class="sxs-lookup"><span data-stu-id="a2a58-132">In the **Vendor/Vendor group field**, select the vendor or vendor group to which the vendor retention terms apply.</span></span> <span data-ttu-id="a2a58-133">Se você selecionar **Todos** na etapa anterior, esse campo não estará disponível.</span><span class="sxs-lookup"><span data-stu-id="a2a58-133">If you selected **All** in the previous step, this field is unavailable.</span></span>
5. <span data-ttu-id="a2a58-134">No campo **Condições de retenção do fornecedor**, selecione as condições de retenção que você criou no no procedimento anterior.</span><span class="sxs-lookup"><span data-stu-id="a2a58-134">In the **Vendor retention terms** field, select the retention terms that you created in the previous procedure.</span></span>
6. <span data-ttu-id="a2a58-135">Se o projeto também tiver as condições de pagamento quando pago (PWP) configuradas para o fornecedor, insira a porcentagem de limite do projeto no campo **Porcentagem de limite PWP**.</span><span class="sxs-lookup"><span data-stu-id="a2a58-135">If the project also has pay-when-paid (PWP) terms set up for the vendor, enter the threshold percentage for the project in the **PWP threshold percentage** field.</span></span>

<span data-ttu-id="a2a58-136">As condições da retenção do fornecedor também são exibidas nas ordens de compra criadas para o fornecedor.</span><span class="sxs-lookup"><span data-stu-id="a2a58-136">The vendor retention terms are also displayed on purchase orders that you create for the vendor.</span></span>
