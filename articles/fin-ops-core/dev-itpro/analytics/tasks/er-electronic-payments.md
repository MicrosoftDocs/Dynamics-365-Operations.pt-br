---
title: Gerar documentos eletrônicos ER para pagamentos usando uma configuração de formato
description: Este tópico descreve como usar uma nova configuração de formato de relatório eletrônico (ER) para gerar documentos eletrônicos para processar pagamentos.
author: NickSelin
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: VendPaymMode, LedgerJournalTable, LedgerJournalTransVendPaym, BankAccountTableLookUp
audience: Application User
ms.reviewer: kfend
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: f62d7cd690406647886f9d6d1cb1491b691d4159
ms.sourcegitcommit: 074b6e212d19dd5d84881d1cdd096611a18c207f
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/31/2021
ms.locfileid: "5752475"
---
# <a name="er-generate-electronic-documents-for-payments-using-a-format-configuration"></a><span data-ttu-id="d2888-103">Gerar documentos eletrônicos ER para pagamentos usando uma configuração de formato</span><span class="sxs-lookup"><span data-stu-id="d2888-103">ER Generate electronic documents for payments using a format configuration</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="d2888-104">As etapas a seguir explicam como um usuário no papel de Administrador do Sistema ou Desenvolvedor de Relatório Eletrônico pode usar uma nova configuração de formato de Relatório Eletrônico (RE) para gerar documentos eletrônicos para processamento de pagamentos.</span><span class="sxs-lookup"><span data-stu-id="d2888-104">The following steps explain how a user in the System Administrator or Electronic Reporting Developer role can use a new Electronic reporting (ER) format configuration to generate electronic documents for processing payments.</span></span> <span data-ttu-id="d2888-105">Essas etapas podem ser executadas na empresa de amostra GBSI.</span><span class="sxs-lookup"><span data-stu-id="d2888-105">These steps can be performed in the GBSI sample company.</span></span>

<span data-ttu-id="d2888-106">Para concluir estas etapas, primeiramente conclua as etapas no procedimento "Criar uma configuração com formato de documento de pagamento".</span><span class="sxs-lookup"><span data-stu-id="d2888-106">To complete these steps, you must first complete the steps in the "Create a configuration with format of payment document" procedure.</span></span>


## <a name="change-the-configuration-of-the-electronic-payment-method"></a><span data-ttu-id="d2888-107">Alterar a configuração do método do pagamento eletrônico</span><span class="sxs-lookup"><span data-stu-id="d2888-107">Change the configuration of the electronic payment method</span></span>
1. <span data-ttu-id="d2888-108">Vá para Contas a pagar > Configurar pagamento > Métodos de pagamento.</span><span class="sxs-lookup"><span data-stu-id="d2888-108">Go to Accounts payable > Payment setup > Methods of payment.</span></span>
2. <span data-ttu-id="d2888-109">Ativar/desativar a seção Formato de arquivo para expandi-la, se necessário.</span><span class="sxs-lookup"><span data-stu-id="d2888-109">Toggle the File format section to expand it, if needed.</span></span>
3. <span data-ttu-id="d2888-110">Use o Filtro Rápido para localizar registros.</span><span class="sxs-lookup"><span data-stu-id="d2888-110">Use the Quick Filter to find records.</span></span> <span data-ttu-id="d2888-111">Por exemplo, filtre o campo Método de pagamento com um valor de "Electronic".</span><span class="sxs-lookup"><span data-stu-id="d2888-111">For example, filter on the Method of payment field with a value of 'Electronic'.</span></span>
4. <span data-ttu-id="d2888-112">Clique em Editar.</span><span class="sxs-lookup"><span data-stu-id="d2888-112">Click Edit.</span></span>
5. <span data-ttu-id="d2888-113">Definir o campo Relatório eletrônico geral para Sim.</span><span class="sxs-lookup"><span data-stu-id="d2888-113">Set the General electronic reporting field to Yes.</span></span>
    * <span data-ttu-id="d2888-114">Selecione Sim para usar o Padrão eletrônico geral de relatório para a geração dos arquivos de pagamento.</span><span class="sxs-lookup"><span data-stu-id="d2888-114">Select Yes to use the General electronic reporting pattern for payment files generation.</span></span>  
6. <span data-ttu-id="d2888-115">No campo Nome, clique no botão suspenso para abrir a pesquisa.</span><span class="sxs-lookup"><span data-stu-id="d2888-115">In the Name field, click the drop-down button to open the lookup.</span></span>
7. <span data-ttu-id="d2888-116">Selecionar configuração de formato BACS (fictício do Reino Unido).</span><span class="sxs-lookup"><span data-stu-id="d2888-116">Select BACS (UK fictitious) format configuration.</span></span>
8. <span data-ttu-id="d2888-117">Clique em Salvar.</span><span class="sxs-lookup"><span data-stu-id="d2888-117">Click Save.</span></span>
9. <span data-ttu-id="d2888-118">Feche a página.</span><span class="sxs-lookup"><span data-stu-id="d2888-118">Close the page.</span></span>

## <a name="test-the-format-of-generated-payment-files"></a><span data-ttu-id="d2888-119">Testar o formato de arquivo de pagamento gerado</span><span class="sxs-lookup"><span data-stu-id="d2888-119">Test the format of generated payment files</span></span>
1. <span data-ttu-id="d2888-120">Vá para Contas a pagar > Pagamentos > Diário de pagamentos.</span><span class="sxs-lookup"><span data-stu-id="d2888-120">Go to Accounts payable > Payments > Payment journal.</span></span>
2. <span data-ttu-id="d2888-121">Clique em Novo.</span><span class="sxs-lookup"><span data-stu-id="d2888-121">Click New.</span></span>
3. <span data-ttu-id="d2888-122">Na lista, marque a linha selecionada.</span><span class="sxs-lookup"><span data-stu-id="d2888-122">In the list, mark the selected row.</span></span>
4. <span data-ttu-id="d2888-123">No campo Nome, clique no botão suspenso para abrir a pesquisa.</span><span class="sxs-lookup"><span data-stu-id="d2888-123">In the Name field, click the drop-down button to open the lookup.</span></span>
5. <span data-ttu-id="d2888-124">Na lista, clique no link na linha selecionada.</span><span class="sxs-lookup"><span data-stu-id="d2888-124">In the list, click the link in the selected row.</span></span>
    * <span data-ttu-id="d2888-125">Selecionar VendPay.</span><span class="sxs-lookup"><span data-stu-id="d2888-125">Select VendPay.</span></span>  
6. <span data-ttu-id="d2888-126">Clique em Salvar.</span><span class="sxs-lookup"><span data-stu-id="d2888-126">Click Save.</span></span>
7. <span data-ttu-id="d2888-127">Clique em Linhas.</span><span class="sxs-lookup"><span data-stu-id="d2888-127">Click Lines.</span></span>
8. <span data-ttu-id="d2888-128">No campo Empresa, digite "DEMF".</span><span class="sxs-lookup"><span data-stu-id="d2888-128">In the Company field, type 'DEMF'.</span></span>
    * <span data-ttu-id="d2888-129">DEMF</span><span class="sxs-lookup"><span data-stu-id="d2888-129">DEMF</span></span>  
9. <span data-ttu-id="d2888-130">No campo Conta, especifique os valores "DE-01001".</span><span class="sxs-lookup"><span data-stu-id="d2888-130">In the Account field, specify the values 'DE-01001'.</span></span>
    * <span data-ttu-id="d2888-131">DE - 01001</span><span class="sxs-lookup"><span data-stu-id="d2888-131">DE-01001</span></span>  
10. <span data-ttu-id="d2888-132">No campo Descrição, digite "Pagamento".</span><span class="sxs-lookup"><span data-stu-id="d2888-132">In the Description field, type 'Payment'.</span></span>
    * <span data-ttu-id="d2888-133">Pagamento</span><span class="sxs-lookup"><span data-stu-id="d2888-133">Payment</span></span>  
11. <span data-ttu-id="d2888-134">No campo Débito, insira um número.</span><span class="sxs-lookup"><span data-stu-id="d2888-134">In the Debit field, enter a number.</span></span>
    * <span data-ttu-id="d2888-135">1000</span><span class="sxs-lookup"><span data-stu-id="d2888-135">1000</span></span>  
12. <span data-ttu-id="d2888-136">Clique na aba Pagamento.</span><span class="sxs-lookup"><span data-stu-id="d2888-136">Click the Payment tab.</span></span>
13. <span data-ttu-id="d2888-137">No campo Método de pagamento, clique no botão suspenso para abrir a pesquisa.</span><span class="sxs-lookup"><span data-stu-id="d2888-137">In the Method of payment field, click the drop-down button to open the lookup.</span></span>
14. <span data-ttu-id="d2888-138">Na lista, localize e selecione o PDV desejado.</span><span class="sxs-lookup"><span data-stu-id="d2888-138">In the list, find and select the desired record.</span></span>
    * <span data-ttu-id="d2888-139">Selecione o Valor eletrônico.</span><span class="sxs-lookup"><span data-stu-id="d2888-139">Select the Electronic value.</span></span>  
15. <span data-ttu-id="d2888-140">Na lista, clique no link na linha selecionada.</span><span class="sxs-lookup"><span data-stu-id="d2888-140">In the list, click the link in the selected row.</span></span>
16. <span data-ttu-id="d2888-141">Clique em Salvar.</span><span class="sxs-lookup"><span data-stu-id="d2888-141">Click Save.</span></span>
17. <span data-ttu-id="d2888-142">Clique em Gerar pagamentos.</span><span class="sxs-lookup"><span data-stu-id="d2888-142">Click Generate payments.</span></span>
18. <span data-ttu-id="d2888-143">No campo Método de pagamento, clique no botão suspenso para abrir a pesquisa.</span><span class="sxs-lookup"><span data-stu-id="d2888-143">In the Method of payment field, click the drop-down button to open the lookup.</span></span>
19. <span data-ttu-id="d2888-144">Na lista, localize e selecione o PDV desejado.</span><span class="sxs-lookup"><span data-stu-id="d2888-144">In the list, find and select the desired record.</span></span>
    * <span data-ttu-id="d2888-145">Selecione o Valor eletrônico.</span><span class="sxs-lookup"><span data-stu-id="d2888-145">Select the Electronic value.</span></span>  
20. <span data-ttu-id="d2888-146">Na lista, clique no link na linha selecionada.</span><span class="sxs-lookup"><span data-stu-id="d2888-146">In the list, click the link in the selected row.</span></span>
    * <span data-ttu-id="d2888-147">Selecione o Valor eletrônico.</span><span class="sxs-lookup"><span data-stu-id="d2888-147">Select the Electronic value.</span></span>  
21. <span data-ttu-id="d2888-148">No campo Nome do arquivo, digite um valor.</span><span class="sxs-lookup"><span data-stu-id="d2888-148">In the File name field, type a value.</span></span>
    * <span data-ttu-id="d2888-149">Por exemplo, digite "Pagamentos".</span><span class="sxs-lookup"><span data-stu-id="d2888-149">For example, type 'payments'.</span></span>  
22. <span data-ttu-id="d2888-150">No campo Conta bancária, clique no botão suspenso para abrir a pesquisa.</span><span class="sxs-lookup"><span data-stu-id="d2888-150">In the Bank account field, click the drop-down button to open the lookup.</span></span>
23. <span data-ttu-id="d2888-151">Na lista, clique no link na linha selecionada.</span><span class="sxs-lookup"><span data-stu-id="d2888-151">In the list, click the link in the selected row.</span></span>
    * <span data-ttu-id="d2888-152">Selecione o valor GBSI OPER.</span><span class="sxs-lookup"><span data-stu-id="d2888-152">Select the value GBSI OPER.</span></span>  
24. <span data-ttu-id="d2888-153">Clique em OK.</span><span class="sxs-lookup"><span data-stu-id="d2888-153">Click OK.</span></span>
25. <span data-ttu-id="d2888-154">Clique em OK.</span><span class="sxs-lookup"><span data-stu-id="d2888-154">Click OK.</span></span>
    * <span data-ttu-id="d2888-155">Analisar o arquivo de pagamento criada no formato XML.</span><span class="sxs-lookup"><span data-stu-id="d2888-155">Analyze the created payment file in XML format.</span></span> <span data-ttu-id="d2888-156">Compare-o com o layout de documento criado e defina atributos da transação de pagamento.</span><span class="sxs-lookup"><span data-stu-id="d2888-156">Compare it with the designed document layout and defined payment transaction attributes.</span></span>  



[!INCLUDE[footer-include](../../../../includes/footer-banner.md)]