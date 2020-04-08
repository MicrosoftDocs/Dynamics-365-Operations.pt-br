---
title: Processamento de recibo de despesas
description: Este tópico fornece informações sobre o processamento de OCR (reconhecimento óptico de caracteres) para recibos. Esse recurso foi desenvolvido para melhorar a experiência do usuário quando os relatórios de despesas são criados no Microsoft Dynamics 365 Finance.
author: stsporen
manager: AnnBe
ms.date: 11/20/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
audience: Application User
ms.reviewer: roschlom
ms.search.scope: Operations, Core
ms.search.region: Global
ms.author: stsporen
ms.search.validFrom: 2019-11-20
ms.dyn365.ops.version: 10.0.8
ms.openlocfilehash: 49cdfeac8cda9f1ddd3aca61f902f00f30f3485b
ms.sourcegitcommit: de5af1912201dd70aa85fdcad0b184c42405802e
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/21/2020
ms.locfileid: "3154031"
---
# <a name="expense-receipt-processing"></a><span data-ttu-id="4b7d9-104">Processamento de recebimento de despesas</span><span class="sxs-lookup"><span data-stu-id="4b7d9-104">Expense receipt processing</span></span>

[!include [banner](../includes/banner.md)]
[!include [preview banner](../includes/preview-banner.md)]


<span data-ttu-id="4b7d9-105">A entrada de despesas foi aprimorada por meio da introdução do processamento de OCR (reconhecimento óptico de caracteres) para recibos.</span><span class="sxs-lookup"><span data-stu-id="4b7d9-105">Expense entry has been enhanced through the introduction of optical character recognition (OCR) processing for receipts.</span></span> <span data-ttu-id="4b7d9-106">Esse recurso foi desenvolvido para melhorar a experiência do usuário quando os relatórios de despesas são criados.</span><span class="sxs-lookup"><span data-stu-id="4b7d9-106">This feature is designed to improve the user experience when expense reports are created.</span></span>

## <a name="key-features"></a><span data-ttu-id="4b7d9-107">Recursos principais</span><span class="sxs-lookup"><span data-stu-id="4b7d9-107">Key features</span></span>

- <span data-ttu-id="4b7d9-108">O nome do comerciante, a data e o valor total são extraídos dos recibos.</span><span class="sxs-lookup"><span data-stu-id="4b7d9-108">The merchant name, date, and total amount are extracted from receipts.</span></span>
- <span data-ttu-id="4b7d9-109">O recurso tenta fazer a correspondência entre os recibos não anexados e as transações de despesa não anexadas.</span><span class="sxs-lookup"><span data-stu-id="4b7d9-109">The feature tries to match unattached receipts to unattached expense transactions.</span></span>
- <span data-ttu-id="4b7d9-110">Os usuários podem criar transações de despesa inseridas manualmente usando os recibos.</span><span class="sxs-lookup"><span data-stu-id="4b7d9-110">Users can create manually entered expense transactions from receipts.</span></span>

## <a name="usage-examples"></a><span data-ttu-id="4b7d9-111">Exemplos de uso</span><span class="sxs-lookup"><span data-stu-id="4b7d9-111">Usage examples</span></span>

- <span data-ttu-id="4b7d9-112">**Anexar automaticamente os recibos que incluem transações de cartão de crédito quando um relatório de despesas é criado.**</span><span class="sxs-lookup"><span data-stu-id="4b7d9-112">**Automatically attach receipts that include credit card transactions when an expense report is created.**</span></span>

    1. <span data-ttu-id="4b7d9-113">Abra o espaço de trabalho **Gerenciamento de despesas**.</span><span class="sxs-lookup"><span data-stu-id="4b7d9-113">Open the **Expense management** workspace.</span></span>
    2. <span data-ttu-id="4b7d9-114">Na guia **Recibos**, verifique se há recibos não anexados.</span><span class="sxs-lookup"><span data-stu-id="4b7d9-114">On the **Receipts** tab, verify that unattached receipts exist.</span></span> <span data-ttu-id="4b7d9-115">Também é possível carregar recibos na guia **Recibos**.</span><span class="sxs-lookup"><span data-stu-id="4b7d9-115">You can also upload receipts on the **Receipts** tab.</span></span>
    3. <span data-ttu-id="4b7d9-116">Na guia **Despesas**, verifique se há despesas não anexadas.</span><span class="sxs-lookup"><span data-stu-id="4b7d9-116">On the **Expenses** tab, verify that unattached expenses exist.</span></span> <span data-ttu-id="4b7d9-117">Normalmente, o administrador de despesas importa essas despesas do emissor do cartão de crédito.</span><span class="sxs-lookup"><span data-stu-id="4b7d9-117">Typically, the expense administrator imports these expenses from the credit card provider.</span></span>
    4. <span data-ttu-id="4b7d9-118">Selecione **Novo relatório de despesa**.</span><span class="sxs-lookup"><span data-stu-id="4b7d9-118">Select **New expense report**.</span></span> <span data-ttu-id="4b7d9-119">Observe que agora você também pode incluir despesas, e recibos, ao criar um relatório de despesas.</span><span class="sxs-lookup"><span data-stu-id="4b7d9-119">Notice that you can include expenses, and receipts, now as well, when you create an expense report.</span></span> <span data-ttu-id="4b7d9-120">Se você adicionar despesas e recibos, será disparada a correspondência automática de recibos em relação às despesas.</span><span class="sxs-lookup"><span data-stu-id="4b7d9-120">If you add both expenses and receipts, automatic matching of the receipts against the expenses is triggered.</span></span>

- <span data-ttu-id="4b7d9-121">**Criar uma despesa ou fazer a correspondência de uma despesa usando um recibo.**</span><span class="sxs-lookup"><span data-stu-id="4b7d9-121">**Create an expense, or match an expense from a receipt.**</span></span>

    1. <span data-ttu-id="4b7d9-122">Em um relatório de despesas, na guia **Recibos**, anexe um recibo selecionando **Adicionar recibos**.</span><span class="sxs-lookup"><span data-stu-id="4b7d9-122">On an expense report, on the **Receipts** tab, attach a receipt by selecting **Add receipts**.</span></span>
    2. <span data-ttu-id="4b7d9-123">Na imagem carregada do recibo, observe as opções **Criar** e **Fazer a Correspondência**.</span><span class="sxs-lookup"><span data-stu-id="4b7d9-123">Under the uploaded image of the receipt, notice the **Create** and **Match** options.</span></span>

        - <span data-ttu-id="4b7d9-124">Selecione **Criar** para criar uma transação de despesa inserida manualmente e preencher os valores que são extraídos do recibo.</span><span class="sxs-lookup"><span data-stu-id="4b7d9-124">Select **Create** to create a manually entered expense transaction and fill in the values that are extracted from the receipt.</span></span>
        - <span data-ttu-id="4b7d9-125">Se você selecionar **Fazer a Correspondência**, o sistema tentará fazer a correspondência de uma despesa existente com o recibo.</span><span class="sxs-lookup"><span data-stu-id="4b7d9-125">If you select **Match**, the system tries to match an existing expense to the receipt.</span></span>

## <a name="installation"></a><span data-ttu-id="4b7d9-126">Instalação</span><span class="sxs-lookup"><span data-stu-id="4b7d9-126">Installation</span></span>

<span data-ttu-id="4b7d9-127">Esse recurso funciona em combinação com o recurso **Relatórios de despesas reformulados** para ajudar a simplificar a experiência de despesas.</span><span class="sxs-lookup"><span data-stu-id="4b7d9-127">This feature works in combination with the **Expense reports re-imagined** feature to help simplify the expense experience.</span></span>

<span data-ttu-id="4b7d9-128">Para usar esses recursos avançados de despesa, instale o suplemento Serviço de Gerenciamento de Despesas para o Microsoft Dynamics 365 Finance e ative os recursos na sua instância.</span><span class="sxs-lookup"><span data-stu-id="4b7d9-128">To use these advanced expense capabilities, install the Expense Management Service add-in for Microsoft Dynamics 365 Finance, and turn on the features in your instance.</span></span> <span data-ttu-id="4b7d9-129">Você pode acessar o suplemento do seu projeto no Microsoft Dynamics Lifecycle Services (LCS).</span><span class="sxs-lookup"><span data-stu-id="4b7d9-129">You can access the add-in from your project in Microsoft Dynamics Lifecycle Services (LCS).</span></span>

1. <span data-ttu-id="4b7d9-130">Entre no LCS e abra o ambiente desejado.</span><span class="sxs-lookup"><span data-stu-id="4b7d9-130">Sign in to LCS, and open the desired environment.</span></span>
2. <span data-ttu-id="4b7d9-131">Vá para **Detalhes completos**.</span><span class="sxs-lookup"><span data-stu-id="4b7d9-131">Go to **Full details**.</span></span>
3. <span data-ttu-id="4b7d9-132">Selecione **Manter** ou role para baixo até a Guia Rápida **Suplementos de ambiente**.</span><span class="sxs-lookup"><span data-stu-id="4b7d9-132">Select **Maintain**, or scroll down to the **Environment add-ins** FastTab.</span></span>
4. <span data-ttu-id="4b7d9-133">Selecione **Instalar um novo suplemento**.</span><span class="sxs-lookup"><span data-stu-id="4b7d9-133">Select **Install a new add-in**.</span></span>
5. <span data-ttu-id="4b7d9-134">Selecione **Serviço de Gerenciamento de Despesas**.</span><span class="sxs-lookup"><span data-stu-id="4b7d9-134">Select **Expense Management Service**.</span></span>
6. <span data-ttu-id="4b7d9-135">Acompanhe o guia de instalação e concorde com os termos e condições.</span><span class="sxs-lookup"><span data-stu-id="4b7d9-135">Follow the installation guide, and agree to the terms and conditions.</span></span>
7. <span data-ttu-id="4b7d9-136">Selecione **Instalar**.</span><span class="sxs-lookup"><span data-stu-id="4b7d9-136">Select **Install**.</span></span>

<span data-ttu-id="4b7d9-137">No espaço de trabalho **Gerenciamento de recursos**, ative os seguintes recursos:</span><span class="sxs-lookup"><span data-stu-id="4b7d9-137">In the **Feature management** workspace, turn on the following features:</span></span>

- <span data-ttu-id="4b7d9-138">Relatórios de despesas reformulados</span><span class="sxs-lookup"><span data-stu-id="4b7d9-138">Expense reports re-imagined</span></span>
- <span data-ttu-id="4b7d9-139">Corresponder automaticamente e criar despesa a partir do recibo</span><span class="sxs-lookup"><span data-stu-id="4b7d9-139">Auto-match and create expense from receipt</span></span>

<span data-ttu-id="4b7d9-140">Quando você ativa esses recursos, as seguintes ações ocorrem:</span><span class="sxs-lookup"><span data-stu-id="4b7d9-140">When you turn on these features the following actions occur:</span></span>

- <span data-ttu-id="4b7d9-141">O espaço de trabalho existente **Gerenciamento de despesas** é substituído pelo novo espaço de trabalho.</span><span class="sxs-lookup"><span data-stu-id="4b7d9-141">The existing **Expense management** workspace is replaced with the new workspace.</span></span>
- <span data-ttu-id="4b7d9-142">Um novo item de menu para visibilidade do campo de despesa é adicionado.</span><span class="sxs-lookup"><span data-stu-id="4b7d9-142">A new menu item for expense field visibility is added.</span></span>
- <span data-ttu-id="4b7d9-143">Você ainda pode abrir a página **Relatórios de despesas** antiga acessando **Gerenciamento de despesas > Minhas despesas > Relatórios de despesas**.</span><span class="sxs-lookup"><span data-stu-id="4b7d9-143">You can still open the former **Expense reports** page by going to **Expense management > My expenses > Expense reports**.</span></span>
- <span data-ttu-id="4b7d9-144">Fluxos de trabalho e quaisquer aprovações ainda o levam para a página de relatórios de despesas existente.</span><span class="sxs-lookup"><span data-stu-id="4b7d9-144">Workflows and any approvals still take you to the existing expense reports page.</span></span>
- <span data-ttu-id="4b7d9-145">Os recibos serão processados pelo Microsoft Azure Cognitive Services, e metadados serão extraídos e adicionados.</span><span class="sxs-lookup"><span data-stu-id="4b7d9-145">Receipts will be processed through Microsoft Azure Cognitive Services, and metadata will be extracted and added.</span></span>
- <span data-ttu-id="4b7d9-146">É adicionada uma opção que permite a você criar um relatório de despesas que inclua recibos não anexados correspondidos.</span><span class="sxs-lookup"><span data-stu-id="4b7d9-146">An option is added that lets you create an expense report that includes matched unattached receipts.</span></span>
- <span data-ttu-id="4b7d9-147">Uma opção que foi adicionada aos relatórios de despesas permite criar uma linha de despesa a partir de um recibo ou tenta fazer a correspondência de um recibo existente com uma linha de despesa existente.</span><span class="sxs-lookup"><span data-stu-id="4b7d9-147">An option that is added to expense reports lets you create an expense line from a receipt, or attempts to match an existing receipt to an existing expense line.</span></span>

<span data-ttu-id="4b7d9-148">Para obter mais informações sobre o recurso Relatórios de despesas reformulados, consulte [Relatórios de despesas reformulados](ExpenseWorkspaceNew.md).</span><span class="sxs-lookup"><span data-stu-id="4b7d9-148">For more information about the Expense reports re-imagined feature, see [Expense reports reimagined](ExpenseWorkspaceNew.md).</span></span>

## <a name="frequently-asked-questions"></a><span data-ttu-id="4b7d9-149">Perguntas frequentes</span><span class="sxs-lookup"><span data-stu-id="4b7d9-149">Frequently asked questions</span></span>

<span data-ttu-id="4b7d9-150">**A Microsoft usa meus dados para seus modelos?**</span><span class="sxs-lookup"><span data-stu-id="4b7d9-150">**Does Microsoft use my data for its models?**</span></span>

<span data-ttu-id="4b7d9-151">Não, a Microsoft criou um modelo geral de aprendizado de máquina para o serviço de processamento de recibos.</span><span class="sxs-lookup"><span data-stu-id="4b7d9-151">No, Microsoft has built a general machine learning model for its receipt processing service.</span></span> <span data-ttu-id="4b7d9-152">Esse modelo não se baseia nos recibos que você carrega.</span><span class="sxs-lookup"><span data-stu-id="4b7d9-152">This model isn't based on the receipts that you upload.</span></span>

<span data-ttu-id="4b7d9-153">**Onde esse recurso está disponível e é processado?**</span><span class="sxs-lookup"><span data-stu-id="4b7d9-153">**Where is this feature available and processed?**</span></span>

<span data-ttu-id="4b7d9-154">Atualmente, nos Estados Unidos.</span><span class="sxs-lookup"><span data-stu-id="4b7d9-154">Currently, the United States is supported.</span></span>

<span data-ttu-id="4b7d9-155">**Para onde vão meus recibos?**</span><span class="sxs-lookup"><span data-stu-id="4b7d9-155">**Where do my receipts go?**</span></span>

<span data-ttu-id="4b7d9-156">O Finance entrará em contato com o Cognitive Services para extrair os dados de campo.</span><span class="sxs-lookup"><span data-stu-id="4b7d9-156">Finance will contact Cognitive Services to extract the field data.</span></span> <span data-ttu-id="4b7d9-157">O Cognitive Services manterá uma cópia do seu recibo por até 24 horas enquanto ocorre o processamento.</span><span class="sxs-lookup"><span data-stu-id="4b7d9-157">Cognitive Services will retain a copy of your receipt for up to 24 hours while processing occurs.</span></span> <span data-ttu-id="4b7d9-158">Depois que o processamento for concluído, o Cognitive Services removerá o recibo.</span><span class="sxs-lookup"><span data-stu-id="4b7d9-158">After processing is completed, Cognitive Services will remove the receipt.</span></span> <span data-ttu-id="4b7d9-159">Os recibos continuam armazenados no Finance.</span><span class="sxs-lookup"><span data-stu-id="4b7d9-159">Receipts are still stored in Finance.</span></span>

<span data-ttu-id="4b7d9-160">Para obter mais informações, consulte [Habilitar o conhecimento de recibo com o novo recurso do Reconhecimento de Formulários](https://azure.microsoft.com/blog/enable-receipt-understanding-with-form-recognizer-s-new-capability/).</span><span class="sxs-lookup"><span data-stu-id="4b7d9-160">For more information, see [Enable receipt understanding with Form Recognizer's new capability](https://azure.microsoft.com/blog/enable-receipt-understanding-with-form-recognizer-s-new-capability/).</span></span>
