---
title: Editar e auditar transações da ordem online e assíncronas da ordem do cliente
description: Este tópico descreve como editar e auditar transações da ordem online e assíncronas da ordem do cliente no Microsoft Dynamics 365 Commerce.
author: josaw1
manager: AnnBe
ms.date: 11/04/2020
ms.topic: index-page
ms.prod: ''
ms.service: dynamics-365-retail
ms.technology: ''
audience: Application User
ms.reviewer: v-chgri
ms.custom: ''
ms.assetid: ed0f77f7-3609-4330-bebd-ca3134575216
ms.search.region: global
ms.search.industry: Retail
ms.author: josaw
ms.search.validFrom: 2018-11-15
ms.dyn365.ops.version: ''
ms.openlocfilehash: 8fa6f7a71bae759e2b8feb3c5778200bb7bdbfe9
ms.sourcegitcommit: 38d40c331c8894acb7b119c5073e3088b54776c1
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/15/2021
ms.locfileid: "5114716"
---
# <a name="edit-and-audit-online-order-and-asynchronous-customer-order-transactions"></a><span data-ttu-id="a9ba1-103">Editar e auditar transações da ordem online e assíncronas da ordem do cliente</span><span class="sxs-lookup"><span data-stu-id="a9ba1-103">Edit and audit online order and asynchronous customer order transactions</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="a9ba1-104">Este tópico descreve como editar e auditar transações da ordem online e assíncronas da ordem do cliente no Microsoft Dynamics 365 Commerce.</span><span class="sxs-lookup"><span data-stu-id="a9ba1-104">This topic describes how to edit and audit online order and asynchronous customer order transactions in Microsoft Dynamics 365 Commerce.</span></span>

## <a name="overview"></a><span data-ttu-id="a9ba1-105">Visão Geral</span><span class="sxs-lookup"><span data-stu-id="a9ba1-105">Overview</span></span>

<span data-ttu-id="a9ba1-106">Entre o Commerce versões 10.0.5 e 10.0.6, o suporte foi adicionado para editar transações de cash and carry (como vendas e devoluções) e transações de gerenciamento de caixa (como entrada de flutuação e remoção de meio de pagamento).</span><span class="sxs-lookup"><span data-stu-id="a9ba1-106">Between Commerce versions 10.0.5 and 10.0.6, support was added for editing cash and carry transactions (such as sales and returns) and cash management transactions (such as float entry and tender removal).</span></span> <span data-ttu-id="a9ba1-107">No Commerce versão 10.0.7, o suporte foi adicionado para editar transações da ordem online e transações assíncronas da ordem do cliente.</span><span class="sxs-lookup"><span data-stu-id="a9ba1-107">In Commerce version 10.0.7, support was added for editing online order transactions and asynchronous customer order transactions.</span></span>

## <a name="edit-and-audit-order-transactions"></a><span data-ttu-id="a9ba1-108">Editar e auditar transações da ordem</span><span class="sxs-lookup"><span data-stu-id="a9ba1-108">Edit and audit order transactions</span></span>

<span data-ttu-id="a9ba1-109">Para editar e auditar transações na matriz do Commerce, siga estas etapas:</span><span class="sxs-lookup"><span data-stu-id="a9ba1-109">To edit and audit order transactions in Commerce headquarters, follow these steps.</span></span>

1. <span data-ttu-id="a9ba1-110">Instalar o [Microsoft Dynamics Office Add-in](https://appsource.microsoft.com/product/office/WA104379629?tab=Overview).</span><span class="sxs-lookup"><span data-stu-id="a9ba1-110">Install the [Microsoft Dynamics Office Add-in](https://appsource.microsoft.com/product/office/WA104379629?tab=Overview).</span></span>
1. <span data-ttu-id="a9ba1-111">Na página **Parâmetros reais**, na guia **Ordens do cliente**, na FastTab **Ordem**, especifique um código de bloqueio para **Código de bloqueio para erros de sincronização da ordem**.</span><span class="sxs-lookup"><span data-stu-id="a9ba1-111">On the **Retail parameters** page, on the **Customer orders** tab, on the **Order** FastTab, specify a hold code for **Hold code for order synchronization errors**.</span></span>
1. <span data-ttu-id="a9ba1-112">Abra o espaço de trabalho **Finanças da loja**.</span><span class="sxs-lookup"><span data-stu-id="a9ba1-112">Open the **Store financials** workspace.</span></span> <span data-ttu-id="a9ba1-113">Os blocos **Erros de sincronização da ordem online** e **Erros de sincronização da ordem do cliente** fornecem uma exibição pré-filtrada da página de transação de varejo.</span><span class="sxs-lookup"><span data-stu-id="a9ba1-113">The **Online order synchronization errors** and **Customer order synchronization errors** tiles provide a prefiltered view of the retail transaction page.</span></span> <span data-ttu-id="a9ba1-114">Cada um deles mostra os registros de transação que falharam na sincronização do tipo de ordem correspondente.</span><span class="sxs-lookup"><span data-stu-id="a9ba1-114">Each shows the transaction records that have failed synchronization for the corresponding order type.</span></span>
1. <span data-ttu-id="a9ba1-115">Abra a página **Erros de sincronização da ordem online** ou a página **Erros de sincronização da ordem do cliente**.</span><span class="sxs-lookup"><span data-stu-id="a9ba1-115">Open either the **Online order synchronization errors** page or the **Customer order synchronization errors** page.</span></span> <span data-ttu-id="a9ba1-116">Selecione um registro para exibir os detalhes de erro de sincronização.</span><span class="sxs-lookup"><span data-stu-id="a9ba1-116">Select a record to view the synchronization error details.</span></span> <span data-ttu-id="a9ba1-117">A FastTab **Status de sincronização** fornece os seguintes detalhes de erro:</span><span class="sxs-lookup"><span data-stu-id="a9ba1-117">The **Synchronization status** FastTab provides the following error details:</span></span>

    - <span data-ttu-id="a9ba1-118">Status da ordem pendente</span><span class="sxs-lookup"><span data-stu-id="a9ba1-118">Pending order status</span></span>
    - <span data-ttu-id="a9ba1-119">Detalhes do erro da ordem</span><span class="sxs-lookup"><span data-stu-id="a9ba1-119">Order error details</span></span>
    - <span data-ttu-id="a9ba1-120">Data e hora da modificação</span><span class="sxs-lookup"><span data-stu-id="a9ba1-120">Modified date and time</span></span>
    - <span data-ttu-id="a9ba1-121">Número de tentativas</span><span class="sxs-lookup"><span data-stu-id="a9ba1-121">Retry count</span></span>

1. <span data-ttu-id="a9ba1-122">Se os detalhes do erro indicarem que o registro deve ser corrigido, selecione **Office Add in** e selecione **Editar transação selecionada**.</span><span class="sxs-lookup"><span data-stu-id="a9ba1-122">If the error details indicate that the record must be fixed, select **Office Add in**, and then select **Edit selected transaction**.</span></span> <span data-ttu-id="a9ba1-123">Um arquivo Excel que mostra os detalhes da transação selecionada é aberto.</span><span class="sxs-lookup"><span data-stu-id="a9ba1-123">An Excel file that shows the details of the selected transaction is opened.</span></span>

    - <span data-ttu-id="a9ba1-124">Se a transação que está sendo editada for uma transação da ordem online, o arquivo Excel conterá as seguintes planilhas:</span><span class="sxs-lookup"><span data-stu-id="a9ba1-124">If the transaction that is being edited is an online order transaction, the Excel file contains the following worksheets:</span></span>

        - <span data-ttu-id="a9ba1-125">**Transação** – essa planilha tem os detalhes do cabeçalho da transação.</span><span class="sxs-lookup"><span data-stu-id="a9ba1-125">**Transaction** – This worksheet has the header details for the transaction.</span></span>
        - <span data-ttu-id="a9ba1-126">**Transação de vendas** – essa planilha tem os detalhes da linha da transação.</span><span class="sxs-lookup"><span data-stu-id="a9ba1-126">**Sales transaction** – This worksheet has the line details for the transaction.</span></span>
        - <span data-ttu-id="a9ba1-127">**Transações de pagamento** – essa planilha tem os detalhes das linhas de pagamento da transação.</span><span class="sxs-lookup"><span data-stu-id="a9ba1-127">**Payment transactions** – This worksheet has the details of the payment lines for the transaction.</span></span>
        - <span data-ttu-id="a9ba1-128">**Transações de desconto** – essa planilha tem os detalhes relacionados ao desconto da transação.</span><span class="sxs-lookup"><span data-stu-id="a9ba1-128">**Discount transactions** – This worksheet has the discount-related details for the transaction.</span></span>
        - <span data-ttu-id="a9ba1-129">**Transações de imposto** – essa planilha tem os detalhes relacionados ao imposto da transação.</span><span class="sxs-lookup"><span data-stu-id="a9ba1-129">**Tax transactions** – This worksheet has the tax-related details for the transaction.</span></span>
        - <span data-ttu-id="a9ba1-130">**Transações de cobrança** – essa planilha tem os dados relacionados aos encargos da transação.</span><span class="sxs-lookup"><span data-stu-id="a9ba1-130">**Charges transactions** – This worksheet has the charges-related data for the transaction.</span></span>

    - <span data-ttu-id="a9ba1-131">Se a transação que está sendo editada for uma transação assíncrona da ordem do cliente, o arquivo Excel conterá as seguintes planilhas:</span><span class="sxs-lookup"><span data-stu-id="a9ba1-131">If the transaction that is being edited is an asynchronous customer order transaction, the Excel file contains the following worksheets:</span></span>

        - <span data-ttu-id="a9ba1-132">**Linhas** – essa planilha tem os detalhes do cabeçalho e da linha da transação.</span><span class="sxs-lookup"><span data-stu-id="a9ba1-132">**Lines** – This worksheet has the header and line details for the transaction.</span></span>
        - <span data-ttu-id="a9ba1-133">**Pagamentos** – essa planilha tem os detalhes das linhas de pagamento da transação.</span><span class="sxs-lookup"><span data-stu-id="a9ba1-133">**Payments** – This worksheet has the details of the payment lines for the transaction.</span></span>
        - <span data-ttu-id="a9ba1-134">**Descontos** – essa planilha tem os detalhes relacionados ao desconto da transação.</span><span class="sxs-lookup"><span data-stu-id="a9ba1-134">**Discounts** – This worksheet has the discount-related details for the transaction.</span></span>
        - <span data-ttu-id="a9ba1-135">**Impostos** – essa planilha tem os detalhes relacionados ao imposto da transação.</span><span class="sxs-lookup"><span data-stu-id="a9ba1-135">**Taxes** – This worksheet has the tax-related details for the transaction.</span></span>
        - <span data-ttu-id="a9ba1-136">**Encargos** – essa planilha tem os dados relacionados aos encargos da transação.</span><span class="sxs-lookup"><span data-stu-id="a9ba1-136">**Charges** – This worksheet has the charges-related data for the transaction.</span></span>

1. <span data-ttu-id="a9ba1-137">No arquivo Excel, no campo **Status da ordem pendente**, insira **Edição** e publique a alteração.</span><span class="sxs-lookup"><span data-stu-id="a9ba1-137">In the Excel file, in the **Pending order status** field, enter **Editing**, and then publish the change.</span></span> <span data-ttu-id="a9ba1-138">Dessa forma, você impede que o trabalho **Sincronizar ordem** sendo executado no modo de lote ignore esse registro durante o processamento.</span><span class="sxs-lookup"><span data-stu-id="a9ba1-138">In this way, you prevent the **Synchronize order** job that is running in batch mode from skipping this record during processing.</span></span>
1. <span data-ttu-id="a9ba1-139">No arquivo do Excel, você modifica os campos apropriados e carrega os dados de volta na matriz do Commerce usando a funcionalidade de publicação do Dynamics Excel Add-in.</span><span class="sxs-lookup"><span data-stu-id="a9ba1-139">In the Excel file, modify the appropriate fields, and then upload the data back into Commerce headquarters by using the publishing functionality of the Dynamics Excel Add-in.</span></span> <span data-ttu-id="a9ba1-140">Depois que os dados forem publicados, as alterações serão refletidas no sistema.</span><span class="sxs-lookup"><span data-stu-id="a9ba1-140">After the data is published, the changes will be reflected in the system.</span></span> <span data-ttu-id="a9ba1-141">Durante a publicação, nenhuma validação é feita nas alterações feitas pelos usuários.</span><span class="sxs-lookup"><span data-stu-id="a9ba1-141">During publication, no validation is done for changes that users make.</span></span>
1. <span data-ttu-id="a9ba1-142">É possível exibir uma trilha de auditoria completa das alterações pode ser exibida ao selecionar **Exibir trilha de auditoria** no cabeçalho **Transação de varejo** para as alterações no nível do cabeçalho e na seção e no registro relevantes na página de transação apropriada.</span><span class="sxs-lookup"><span data-stu-id="a9ba1-142">You can view a complete audit trail of the changes by selecting **View audit trail** in the **Retail transaction** header for the header-level changes, and in the relevant section and record on the appropriate transaction page.</span></span> <span data-ttu-id="a9ba1-143">Por exemplo, todas as alterações relacionadas às linhas de vendas serão mostradas na página **Transações de vendas** e todas as alterações relacionadas a pagamentos serão mostradas na página **Transações de pagamento**.</span><span class="sxs-lookup"><span data-stu-id="a9ba1-143">For example, all changes that are related to sales lines will be shown on the **Sales transactions** page, and all changes that are related to payments will be shown on the **Payment transactions** page.</span></span> <span data-ttu-id="a9ba1-144">Os seguintes detalhes de auditoria serão mantidos para as alterações:</span><span class="sxs-lookup"><span data-stu-id="a9ba1-144">The following audit details are maintained for the changes:</span></span>

    - <span data-ttu-id="a9ba1-145">Data e hora da modificação</span><span class="sxs-lookup"><span data-stu-id="a9ba1-145">Modified date and time</span></span>
    - <span data-ttu-id="a9ba1-146">Campo</span><span class="sxs-lookup"><span data-stu-id="a9ba1-146">Field</span></span>
    - <span data-ttu-id="a9ba1-147">Valor antigo</span><span class="sxs-lookup"><span data-stu-id="a9ba1-147">Old value</span></span>
    - <span data-ttu-id="a9ba1-148">Novo valor</span><span class="sxs-lookup"><span data-stu-id="a9ba1-148">New value</span></span>
    - <span data-ttu-id="a9ba1-149">Modificação de</span><span class="sxs-lookup"><span data-stu-id="a9ba1-149">Modified by</span></span>

1. <span data-ttu-id="a9ba1-150">Depois de fazer e publicar as alterações, selecione **Sincronizar ordem** para iniciar o processo de sincronização imediatamente.</span><span class="sxs-lookup"><span data-stu-id="a9ba1-150">After you've made and published your changes, select **Synchronize order** to immediately start the synchronization process.</span></span> <span data-ttu-id="a9ba1-151">Como alternativa, você pode aguardar o processo de sincronização em execução no modo de lote para processar a transação.</span><span class="sxs-lookup"><span data-stu-id="a9ba1-151">Alternatively, you can wait for the synchronization process that is running in batch mode to process the transaction.</span></span>

<span data-ttu-id="a9ba1-152">Por padrão, após as ordens serem sincronizadas com sucesso, elas são colocadas no status de suspensão, com base no código de bloqueio definido nos parâmetros do Commerce.</span><span class="sxs-lookup"><span data-stu-id="a9ba1-152">By default, after the orders are successfully synced, they are put in a hold status, based on the hold code that is defined in the Commerce parameters.</span></span> <span data-ttu-id="a9ba1-153">O bloqueio das ordens deve ser removido antes que elas possam ser processadas posteriormente para cumprimento ou outras operações.</span><span class="sxs-lookup"><span data-stu-id="a9ba1-153">The hold on the orders must be removed before the orders can be processed further for fulfillment or other operations.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="a9ba1-154">Recursos adicionais</span><span class="sxs-lookup"><span data-stu-id="a9ba1-154">Additional resources</span></span>

[<span data-ttu-id="a9ba1-155">Editar e auditar transações cash and carry e de gerenciamento de caixa</span><span class="sxs-lookup"><span data-stu-id="a9ba1-155">Edit and audit cash and carry and cash management transactions</span></span>](edit-cash-trans.md)

[<span data-ttu-id="a9ba1-156">Editar dimensões financeiras para transações de varejo</span><span class="sxs-lookup"><span data-stu-id="a9ba1-156">Edit financial dimensions for retail transactions</span></span>](edit-financial-dim.md)

[<span data-ttu-id="a9ba1-157">Criar uma pasta de trabalho do Excel para editar transações de varejo</span><span class="sxs-lookup"><span data-stu-id="a9ba1-157">Create an Excel workbook to edit retail transactions</span></span>](create-excel-edit.md)

[<span data-ttu-id="a9ba1-158">Adicionar campos a uma pasta de trabalho do Excel para editar transações de varejo</span><span class="sxs-lookup"><span data-stu-id="a9ba1-158">Add fields to an Excel workbook to edit retail transactions</span></span>](add-fields-excel.md)
