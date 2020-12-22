---
title: Criar uma pasta de trabalho do Excel para editar transações de varejo
description: Este tópico descreve como criar uma pasta de trabalho do Excel para que você possa editar transações de varejo no Microsoft Dynamics 365 Commerce.
author: josaw1
manager: AnnBe
ms.date: 11/04/2020
ms.topic: index-page
ms.prod: ''
ms.service: dynamics-365-retail
ms.technology: ''
audience: Application User
ms.reviewer: v-chgri
ms.search.scope: Core, Operations, Retail
ms.custom: ''
ms.assetid: ed0f77f7-3609-4330-bebd-ca3134575216
ms.search.region: global
ms.search.industry: Retail
ms.author: josaw
ms.search.validFrom: 2018-11-15
ms.dyn365.ops.version: ''
ms.openlocfilehash: b2b6e98db54e7747912aad26f4b8ae24b9ad5a6d
ms.sourcegitcommit: ce51ff2b6099c75dceb99de6dea9d53baf99772d
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/04/2020
ms.locfileid: "4458491"
---
# <a name="create-an-excel-workbook-to-edit-retail-transactions"></a><span data-ttu-id="46cce-103">Criar uma pasta de trabalho do Excel para editar transações de varejo</span><span class="sxs-lookup"><span data-stu-id="46cce-103">Create an Excel workbook to edit retail transactions</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="46cce-104">Este tópico descreve como criar uma pasta de trabalho do Excel para que você possa editar transações de varejo no Microsoft Dynamics 365 Commerce.</span><span class="sxs-lookup"><span data-stu-id="46cce-104">This topic describes how to create an Excel workbook so that you can edit retail transactions in Microsoft Dynamics 365 Commerce.</span></span>

## <a name="overview"></a><span data-ttu-id="46cce-105">Visão geral</span><span class="sxs-lookup"><span data-stu-id="46cce-105">Overview</span></span>

<span data-ttu-id="46cce-106">Há um modelo de Excel predefinido que os clientes podem acessar de diferentes partes do sistema e usar para editar e auditar transações de varejo.</span><span class="sxs-lookup"><span data-stu-id="46cce-106">There is a predefined Excel template that customers can access from different parts of the system and use to edit and audit retail transactions.</span></span> <span data-ttu-id="46cce-107">No entanto, os clientes também podem criar uma pasta de trabalho personalizada do Excel para este fim.</span><span class="sxs-lookup"><span data-stu-id="46cce-107">However, customers can also create a custom Excel workbook for this purpose.</span></span>

## <a name="create-and-configure-an-excel-workbook"></a><span data-ttu-id="46cce-108">Criar e configurar uma pasta de trabalho do Excel</span><span class="sxs-lookup"><span data-stu-id="46cce-108">Create and configure an Excel workbook</span></span>

<span data-ttu-id="46cce-109">Para criar e configurar uma pasta de trabalho do Excel para que você possa editar transações de varejo, siga estas etapas:</span><span class="sxs-lookup"><span data-stu-id="46cce-109">To create and configure an Excel workbook so that you can edit retail transactions, follow these steps.</span></span>

1. <span data-ttu-id="46cce-110">Abra o Excel e crie uma pasta de trabalho em branco.</span><span class="sxs-lookup"><span data-stu-id="46cce-110">Open Excel, and create a blank workbook.</span></span>
1. <span data-ttu-id="46cce-111">Na guia **Inserir**, selecione **Meus suplementos**.</span><span class="sxs-lookup"><span data-stu-id="46cce-111">On the **Insert** tab, select **My add-ins**.</span></span>
1. <span data-ttu-id="46cce-112">No painel direito, selecione o link **Adicionar informações do servidor**.</span><span class="sxs-lookup"><span data-stu-id="46cce-112">In the right pane, select the **Add server information** link.</span></span>
1. <span data-ttu-id="46cce-113">Insira a URL do servidor e selecione **OK**.</span><span class="sxs-lookup"><span data-stu-id="46cce-113">Enter the server URL, and then select **OK**.</span></span>
1. <span data-ttu-id="46cce-114">Se você receber uma mensagem de erro "Nenhum registro applet encontrado", siga estas etapas para resolver o problema:</span><span class="sxs-lookup"><span data-stu-id="46cce-114">If you receive a "No applet registrations found" error message, follow these steps to resolve the issue:</span></span>

    1. <span data-ttu-id="46cce-115">No Commerce, acesse **Administração do sistema \> Configuração \> Parâmetros do aplicativo Office**.</span><span class="sxs-lookup"><span data-stu-id="46cce-115">In Commerce, go to **System administration \> Setup \> Office app parameters**.</span></span>
    1. <span data-ttu-id="46cce-116">Na FastTab **Parâmetros do aplicativo**, selecione **Inicializar parâmetros do aplicativo**.</span><span class="sxs-lookup"><span data-stu-id="46cce-116">On the **App parameters** FastTab, select **Initialize app parameters**.</span></span>
    1. <span data-ttu-id="46cce-117">Na caixa de mensagem de confirmação, selecione **OK**.</span><span class="sxs-lookup"><span data-stu-id="46cce-117">In the confirmation message box, select **OK**.</span></span>
    1. <span data-ttu-id="46cce-118">Na FastTab **Applets registrados**, selecione **Inicializar registro de applet**.</span><span class="sxs-lookup"><span data-stu-id="46cce-118">On the **Registered applets** FastTab, select **Initialize applet registration**.</span></span>
    1. <span data-ttu-id="46cce-119">Repita as três etapas anteriores conforme necessário.</span><span class="sxs-lookup"><span data-stu-id="46cce-119">Repeat the previous three steps as required.</span></span>

1. <span data-ttu-id="46cce-120">Selecione **Design** e, em seguida, selecione **Adicionar tabela**.</span><span class="sxs-lookup"><span data-stu-id="46cce-120">Select **Design**, and then select **Add table**.</span></span>
1. <span data-ttu-id="46cce-121">Com base nos dados que devem ser modificados, selecione as entidades que devem ser adicionadas à pasta de trabalho do Excel para edição.</span><span class="sxs-lookup"><span data-stu-id="46cce-121">Based on the data that has to be modified, select the entities that must be added to the Excel workbook for editing.</span></span> <span data-ttu-id="46cce-122">Use a tabela a seguir como referência.</span><span class="sxs-lookup"><span data-stu-id="46cce-122">Use the following table as a reference.</span></span>

    | <span data-ttu-id="46cce-123">Tipo de transação</span><span class="sxs-lookup"><span data-stu-id="46cce-123">Transaction type</span></span> | <span data-ttu-id="46cce-124">Entidades de dados a serem usadas</span><span class="sxs-lookup"><span data-stu-id="46cce-124">Data entities to use</span></span> |
    |------------------|----------------------|
    | <span data-ttu-id="46cce-125">Transações cash and carry, ordens online, ordens de clientes assíncronas, cotações de clientes assíncronas</span><span class="sxs-lookup"><span data-stu-id="46cce-125">Cash and carry transactions, Online orders, Async customer orders, Async customer quotes</span></span> | <span data-ttu-id="46cce-126">Transações (auditáveis), Transações de vendas (auditáveis), Transações de pagamento (auditáveis), Transações de imposto (auditáveis), Transações de desconto (auditáveis), Transações de encargos (auditáveis)</span><span class="sxs-lookup"><span data-stu-id="46cce-126">Transaction (auditable), Sales transaction (auditable), Payment transactions (auditable), Tax transactions (auditable), Discount transactions (auditable), Charge transactions (auditable)</span></span> |
    | <span data-ttu-id="46cce-127">Depósito bancário</span><span class="sxs-lookup"><span data-stu-id="46cce-127">Bank drop</span></span> | <span data-ttu-id="46cce-128">Transações (auditáveis), Transações de meio de pagamento bancário (auditáveis)</span><span class="sxs-lookup"><span data-stu-id="46cce-128">Transaction (auditable), Banked tender transactions (auditable)</span></span> |
    | <span data-ttu-id="46cce-129">Depósito no cofre</span><span class="sxs-lookup"><span data-stu-id="46cce-129">Safe drop</span></span> | <span data-ttu-id="46cce-130">Transações (auditáveis), Transações de meio de pagamento do cofre (auditáveis)</span><span class="sxs-lookup"><span data-stu-id="46cce-130">Transaction (auditable), Safe tender transactions (auditable)</span></span> |
    | <span data-ttu-id="46cce-131">Declaração de meios de pagamento</span><span class="sxs-lookup"><span data-stu-id="46cce-131">Tender declaration</span></span> | <span data-ttu-id="46cce-132">Transações (auditáveis), Transações de declaração de meios de pagamento (auditáveis)</span><span class="sxs-lookup"><span data-stu-id="46cce-132">Transaction (auditable), Tender declaration transactions (auditable)</span></span> |
    | <span data-ttu-id="46cce-133">Receita, Despesa</span><span class="sxs-lookup"><span data-stu-id="46cce-133">Income, Expense</span></span> | <span data-ttu-id="46cce-134">Transações (auditáveis), Transações de Receitas/Despesas (auditáveis), Transações de pagamento (auditáveis)</span><span class="sxs-lookup"><span data-stu-id="46cce-134">Transaction (auditable), Income/Expense transactions (auditable), Payment transactions (auditable)</span></span> |
    | <span data-ttu-id="46cce-135">Declarar valor inicial, Remoção de meio de pagamento, Entrada de flutuação, Meio de pagamento de troco, Pagamento de fatura, Depósito do cliente</span><span class="sxs-lookup"><span data-stu-id="46cce-135">Declare starting amount, Tender removal, Float entry, Change tender, Invoice payment, Customer deposit</span></span> | <span data-ttu-id="46cce-136">Transações (auditáveis), Transações de pagamento (auditáveis)</span><span class="sxs-lookup"><span data-stu-id="46cce-136">Transaction (auditable), Payment transactions (auditable)</span></span> |

    > [!NOTE]
    > <span data-ttu-id="46cce-137">É importante que você adicione somente uma entidade de dados a cada pasta de trabalho do Excel.</span><span class="sxs-lookup"><span data-stu-id="46cce-137">It's important that you add only one data entity to each Excel workbook.</span></span> <span data-ttu-id="46cce-138">Além disso, todos os campos marcados por um símbolo de chave devem ser adicionados à pasta de trabalho relevante.</span><span class="sxs-lookup"><span data-stu-id="46cce-138">Additionally, all fields that are marked by a key symbol must be added to the relevant workbook.</span></span>

1. <span data-ttu-id="46cce-139">Depois que a pasta de trabalho estiver configurada, aplique os filtros necessários.</span><span class="sxs-lookup"><span data-stu-id="46cce-139">After the workbook is configured, apply the required filters.</span></span> <span data-ttu-id="46cce-140">Certifique-se de aplicar os mesmos filtros a todas as planilhas do arquivo.</span><span class="sxs-lookup"><span data-stu-id="46cce-140">Be sure to apply the same filters to all the worksheets in the file.</span></span> <span data-ttu-id="46cce-141">Evite carregar quantidades muito grandes de dados no arquivo Excel.</span><span class="sxs-lookup"><span data-stu-id="46cce-141">Avoid loading very large amounts of data into the Excel file.</span></span> <span data-ttu-id="46cce-142">Caso contrário, o desempenho pode ser afetado, e o Excel e seu sistema podem ficar lentos.</span><span class="sxs-lookup"><span data-stu-id="46cce-142">Otherwise, performance might be affected, and Excel and your system might slow down.</span></span> <span data-ttu-id="46cce-143">Recomendamos que você use sempre "Empresa" e o "Número do Demonstrativo" ou o "Número da Transação" como filtros para seu arquivo.</span><span class="sxs-lookup"><span data-stu-id="46cce-143">We recommend that you always use "Company" and either "Statement Number" or "Transaction Number" as filters for your file.</span></span>
1. <span data-ttu-id="46cce-144">Depois que os filtros forem configurados, selecione **Atualizar** para carregar os dados.</span><span class="sxs-lookup"><span data-stu-id="46cce-144">After the filters are configured, select **Refresh** to load the data.</span></span>
1. <span data-ttu-id="46cce-145">Edite os dados necessários e publique-os.</span><span class="sxs-lookup"><span data-stu-id="46cce-145">Edit the required data, and then publish it.</span></span> <span data-ttu-id="46cce-146">Se o botão **Publicar** não estiver disponível, alguns campos-chave provavelmente não foram adicionados à pasta de trabalho do Excel.</span><span class="sxs-lookup"><span data-stu-id="46cce-146">If the **Publish** button is unavailable, some key fields probably weren't added to the Excel workbook.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="46cce-147">Recursos adicionais</span><span class="sxs-lookup"><span data-stu-id="46cce-147">Additional resources</span></span>

[<span data-ttu-id="46cce-148">Editar e auditar transações cash and carry e de gerenciamento de caixa</span><span class="sxs-lookup"><span data-stu-id="46cce-148">Edit and audit cash and carry and cash management transactions</span></span>](edit-cash-trans.md)

[<span data-ttu-id="46cce-149">Editar e auditar transações da ordem online e assíncronas da ordem do cliente</span><span class="sxs-lookup"><span data-stu-id="46cce-149">Edit and audit online order and asynchronous customer order transactions</span></span>](edit-order-trans.md)

[<span data-ttu-id="46cce-150">Editar dimensões financeiras para transações de varejo</span><span class="sxs-lookup"><span data-stu-id="46cce-150">Edit financial dimensions for retail transactions</span></span>](edit-financial-dim.md)

[<span data-ttu-id="46cce-151">Adicionar campos a uma pasta de trabalho do Excel para editar transações de varejo</span><span class="sxs-lookup"><span data-stu-id="46cce-151">Add fields to an Excel workbook to edit retail transactions</span></span>](add-fields-excel.md)
