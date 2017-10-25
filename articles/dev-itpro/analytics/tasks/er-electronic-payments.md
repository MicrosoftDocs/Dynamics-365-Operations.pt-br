--- 
title: "Gerar documentos eletrônicos para pagamentos usando uma configuração de formato para relatório eletrônico (ER)"
description: "As etapas a seguir explicam como um usuário no papel de Administrador do Sistema ou Desenvolvedor de Relatório Eletrônico pode usar uma nova configuração de formato de Relatório Eletrônico (RE) para gerar documentos eletrônicos para processamento de pagamentos."
author: NickSelin
manager: AnnBe
ms.date: 11/10/2016
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: kfend
ms.search.scope: Operations
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: f827b4787506cfdec8b9a91c4a68f3293190158a
ms.openlocfilehash: a5d958d3b55bfa76f3cfbb3c1a289e4e89c49146
ms.contentlocale: pt-br
ms.lasthandoff: 09/29/2017

---
# <a name="generate-electronic-documents-for-payments-using-a-format-configuration-for-electronic-reporting-er"></a><span data-ttu-id="21899-103">Gerar documentos eletrônicos para pagamentos usando uma configuração de formato para relatório eletrônico (ER)</span><span class="sxs-lookup"><span data-stu-id="21899-103">Generate electronic documents for payments using a format configuration for electronic reporting (ER)</span></span>

[!include[task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="21899-104">As etapas a seguir explicam como um usuário no papel de Administrador do Sistema ou Desenvolvedor de Relatório Eletrônico pode usar uma nova configuração de formato de Relatório Eletrônico (RE) para gerar documentos eletrônicos para processamento de pagamentos.</span><span class="sxs-lookup"><span data-stu-id="21899-104">The following steps explain how a user in the System Administrator or Electronic Reporting Developer role can use a new Electronic reporting (ER) format configuration to generate electronic documents for processing payments.</span></span> <span data-ttu-id="21899-105">Essas etapas podem ser executadas na empresa de amostra GBSI.</span><span class="sxs-lookup"><span data-stu-id="21899-105">These steps can be performed in the GBSI sample company.</span></span>

<span data-ttu-id="21899-106">Para completar essas etapas, você deve primeiro completar as etapas do procedimento “Criar uma configuração de documento de pagamento“.</span><span class="sxs-lookup"><span data-stu-id="21899-106">To complete these steps, you must first complete the steps in the “Create a configuration with format of payment document” procedure.</span></span>


## <a name="change-the-configuration-of-the-electronic-payment-method"></a><span data-ttu-id="21899-107">Alterar a configuração do método do pagamento eletrônico</span><span class="sxs-lookup"><span data-stu-id="21899-107">Change the configuration of the electronic payment method</span></span>
1. <span data-ttu-id="21899-108">Vá para Contas a pagar > Configurar pagamento > Métodos de pagamento.</span><span class="sxs-lookup"><span data-stu-id="21899-108">Go to Accounts payable > Payment setup > Methods of payment.</span></span>
2. <span data-ttu-id="21899-109">Ativar/desativar a seção Formato de arquivo para expandi-la, se necessário.</span><span class="sxs-lookup"><span data-stu-id="21899-109">Toggle the File format section to expand it, if needed.</span></span>
3. <span data-ttu-id="21899-110">Use o Filtro Rápido para localizar registros.</span><span class="sxs-lookup"><span data-stu-id="21899-110">Use the Quick Filter to find records.</span></span> <span data-ttu-id="21899-111">Por exemplo, filtre o campo Método de pagamento com um valor de "Electronic".</span><span class="sxs-lookup"><span data-stu-id="21899-111">For example, filter on the Method of payment field with a value of 'Electronic'.</span></span>
4. <span data-ttu-id="21899-112">Clique em Editar.</span><span class="sxs-lookup"><span data-stu-id="21899-112">Click Edit.</span></span>
5. <span data-ttu-id="21899-113">Definir o campo Relatório eletrônico geral para Sim.</span><span class="sxs-lookup"><span data-stu-id="21899-113">Set the General electronic reporting field to Yes.</span></span>
    * <span data-ttu-id="21899-114">Selecione Sim para usar o Padrão eletrônico geral de relatório para a geração dos arquivos de pagamento.</span><span class="sxs-lookup"><span data-stu-id="21899-114">Select Yes to use the General electronic reporting pattern for payment files generation.</span></span>  
6. <span data-ttu-id="21899-115">No campo Nome, clique no botão suspenso para abrir a pesquisa.</span><span class="sxs-lookup"><span data-stu-id="21899-115">In the Name field, click the drop-down button to open the lookup.</span></span>
7. <span data-ttu-id="21899-116">Selecionar configuração de formato BACS (fictício do Reino Unido).</span><span class="sxs-lookup"><span data-stu-id="21899-116">Select BACS (UK fictitious) format configuration.</span></span>
8. <span data-ttu-id="21899-117">Clique em Salvar.</span><span class="sxs-lookup"><span data-stu-id="21899-117">Click Save.</span></span>
9. <span data-ttu-id="21899-118">Feche a página.</span><span class="sxs-lookup"><span data-stu-id="21899-118">Close the page.</span></span>

## <a name="test-the-format-of-generated-payment-files"></a><span data-ttu-id="21899-119">Testar o formato de arquivo de pagamento gerado</span><span class="sxs-lookup"><span data-stu-id="21899-119">Test the format of generated payment files</span></span>
1. <span data-ttu-id="21899-120">Vá para Contas a pagar > Pagamentos > Diário de pagamentos.</span><span class="sxs-lookup"><span data-stu-id="21899-120">Go to Accounts payable > Payments > Payment journal.</span></span>
2. <span data-ttu-id="21899-121">Clique em Novo.</span><span class="sxs-lookup"><span data-stu-id="21899-121">Click New.</span></span>
3. <span data-ttu-id="21899-122">Na lista, marque a linha selecionada.</span><span class="sxs-lookup"><span data-stu-id="21899-122">In the list, mark the selected row.</span></span>
4. <span data-ttu-id="21899-123">No campo Nome, clique no botão suspenso para abrir a pesquisa.</span><span class="sxs-lookup"><span data-stu-id="21899-123">In the Name field, click the drop-down button to open the lookup.</span></span>
5. <span data-ttu-id="21899-124">Na lista, clique no link na linha selecionada.</span><span class="sxs-lookup"><span data-stu-id="21899-124">In the list, click the link in the selected row.</span></span>
    * <span data-ttu-id="21899-125">Selecionar VendPay.</span><span class="sxs-lookup"><span data-stu-id="21899-125">Select VendPay.</span></span>  
6. <span data-ttu-id="21899-126">Clique em Salvar.</span><span class="sxs-lookup"><span data-stu-id="21899-126">Click Save.</span></span>
7. <span data-ttu-id="21899-127">Clique em Linhas.</span><span class="sxs-lookup"><span data-stu-id="21899-127">Click Lines.</span></span>
8. <span data-ttu-id="21899-128">No campo Empresa, digite "DEMF".</span><span class="sxs-lookup"><span data-stu-id="21899-128">In the Company field, type 'DEMF'.</span></span>
    * <span data-ttu-id="21899-129">DEMF</span><span class="sxs-lookup"><span data-stu-id="21899-129">DEMF</span></span>  
9. <span data-ttu-id="21899-130">No campo Conta, especifique os valores "DE-01001".</span><span class="sxs-lookup"><span data-stu-id="21899-130">In the Account field, specify the values 'DE-01001'.</span></span>
    * <span data-ttu-id="21899-131">DE - 01001</span><span class="sxs-lookup"><span data-stu-id="21899-131">DE-01001</span></span>  
10. <span data-ttu-id="21899-132">No campo Descrição, digite "Pagamento".</span><span class="sxs-lookup"><span data-stu-id="21899-132">In the Description field, type 'Payment'.</span></span>
    * <span data-ttu-id="21899-133">Pagamento</span><span class="sxs-lookup"><span data-stu-id="21899-133">Payment</span></span>  
11. <span data-ttu-id="21899-134">No campo Débito, insira um número.</span><span class="sxs-lookup"><span data-stu-id="21899-134">In the Debit field, enter a number.</span></span>
    * <span data-ttu-id="21899-135">1000</span><span class="sxs-lookup"><span data-stu-id="21899-135">1000</span></span>  
12. <span data-ttu-id="21899-136">Clique na aba Pagamento.</span><span class="sxs-lookup"><span data-stu-id="21899-136">Click the Payment tab.</span></span>
13. <span data-ttu-id="21899-137">No campo Método de pagamento, clique no botão suspenso para abrir a pesquisa.</span><span class="sxs-lookup"><span data-stu-id="21899-137">In the Method of payment field, click the drop-down button to open the lookup.</span></span>
14. <span data-ttu-id="21899-138">Na lista, localize e selecione o PDV desejado.</span><span class="sxs-lookup"><span data-stu-id="21899-138">In the list, find and select the desired record.</span></span>
    * <span data-ttu-id="21899-139">Selecione o Valor eletrônico.</span><span class="sxs-lookup"><span data-stu-id="21899-139">Select the Electronic value.</span></span>  
15. <span data-ttu-id="21899-140">Na lista, clique no link na linha selecionada.</span><span class="sxs-lookup"><span data-stu-id="21899-140">In the list, click the link in the selected row.</span></span>
16. <span data-ttu-id="21899-141">Clique em Salvar.</span><span class="sxs-lookup"><span data-stu-id="21899-141">Click Save.</span></span>
17. <span data-ttu-id="21899-142">Clique em Gerar pagamentos.</span><span class="sxs-lookup"><span data-stu-id="21899-142">Click Generate payments.</span></span>
18. <span data-ttu-id="21899-143">No campo Método de pagamento, clique no botão suspenso para abrir a pesquisa.</span><span class="sxs-lookup"><span data-stu-id="21899-143">In the Method of payment field, click the drop-down button to open the lookup.</span></span>
19. <span data-ttu-id="21899-144">Na lista, localize e selecione o PDV desejado.</span><span class="sxs-lookup"><span data-stu-id="21899-144">In the list, find and select the desired record.</span></span>
    * <span data-ttu-id="21899-145">Selecione o Valor eletrônico.</span><span class="sxs-lookup"><span data-stu-id="21899-145">Select the Electronic value.</span></span>  
20. <span data-ttu-id="21899-146">Na lista, clique no link na linha selecionada.</span><span class="sxs-lookup"><span data-stu-id="21899-146">In the list, click the link in the selected row.</span></span>
    * <span data-ttu-id="21899-147">Selecione o Valor eletrônico.</span><span class="sxs-lookup"><span data-stu-id="21899-147">Select the Electronic value.</span></span>  
21. <span data-ttu-id="21899-148">No campo Nome do arquivo, digite um valor.</span><span class="sxs-lookup"><span data-stu-id="21899-148">In the File name field, type a value.</span></span>
    * <span data-ttu-id="21899-149">Por exemplo, digite "Pagamentos".</span><span class="sxs-lookup"><span data-stu-id="21899-149">For example, type 'payments'.</span></span>  
22. <span data-ttu-id="21899-150">No campo Conta bancária, clique no botão suspenso para abrir a pesquisa.</span><span class="sxs-lookup"><span data-stu-id="21899-150">In the Bank account field, click the drop-down button to open the lookup.</span></span>
23. <span data-ttu-id="21899-151">Na lista, clique no link na linha selecionada.</span><span class="sxs-lookup"><span data-stu-id="21899-151">In the list, click the link in the selected row.</span></span>
    * <span data-ttu-id="21899-152">Selecione o valor GBSI OPER.</span><span class="sxs-lookup"><span data-stu-id="21899-152">Select the value GBSI OPER.</span></span>  
24. <span data-ttu-id="21899-153">Clique em OK.</span><span class="sxs-lookup"><span data-stu-id="21899-153">Click OK.</span></span>
25. <span data-ttu-id="21899-154">Clique em OK.</span><span class="sxs-lookup"><span data-stu-id="21899-154">Click OK.</span></span>
    * <span data-ttu-id="21899-155">Analisar o arquivo de pagamento criada no formato XML.</span><span class="sxs-lookup"><span data-stu-id="21899-155">Analyze the created payment file in XML format.</span></span> <span data-ttu-id="21899-156">Compare-o com o layout de documento criado e defina atributos da transação de pagamento.</span><span class="sxs-lookup"><span data-stu-id="21899-156">Compare it with the designed document layout and defined payment transaction attributes.</span></span>  

