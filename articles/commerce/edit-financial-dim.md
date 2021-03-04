---
title: Editar dimensões financeiras para transações de varejo
description: Este tópico descreve como editar dimensões financeiras para transações de varejo no Microsoft Dynamics 365 Commerce.
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
ms.openlocfilehash: 5a5a82adbad16d8fea2ccf60ae0dbfbd2fd9f3c1
ms.sourcegitcommit: 38d40c331c8894acb7b119c5073e3088b54776c1
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/15/2021
ms.locfileid: "5114717"
---
# <a name="edit-financial-dimensions-for-retail-transactions"></a><span data-ttu-id="9768b-103">Editar dimensões financeiras para transações de varejo</span><span class="sxs-lookup"><span data-stu-id="9768b-103">Edit financial dimensions for retail transactions</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="9768b-104">Este tópico descreve como editar dimensões financeiras para transações de varejo no Microsoft Dynamics 365 Commerce.</span><span class="sxs-lookup"><span data-stu-id="9768b-104">This topic describes how to edit financial dimensions for retail transactions in Microsoft Dynamics 365 Commerce.</span></span>

## <a name="edit-financial-dimensions"></a><span data-ttu-id="9768b-105">Editar dimensões financeiras</span><span class="sxs-lookup"><span data-stu-id="9768b-105">Edit financial dimensions</span></span>

<span data-ttu-id="9768b-106">Para editar dimensões financeiras para transações de varejo na matriz do Commerce, siga estas etapas:</span><span class="sxs-lookup"><span data-stu-id="9768b-106">To edit financial dimensions for retail transactions in Commerce headquarters, follow these steps.</span></span>

1. <span data-ttu-id="9768b-107">Abra a página **Configuração de dimensões financeiras para integração de aplicativos**.</span><span class="sxs-lookup"><span data-stu-id="9768b-107">Open the **Financial dimensions configuration for integrating applications** page.</span></span>
1. <span data-ttu-id="9768b-108">Selecione o registro **Integração de dimensões padrão** ativo.</span><span class="sxs-lookup"><span data-stu-id="9768b-108">Select the active **Default dimensions integration** record.</span></span>
1. <span data-ttu-id="9768b-109">Na FastTab **Dimensões financeiras**, certifique-se de que todas as dimensões que você deseja editar na planilha do Excel estejam presentes na lista **Selecionado**.</span><span class="sxs-lookup"><span data-stu-id="9768b-109">On the **Financial dimensions** FastTab, make sure that all the dimensions that you want to edit in the Excel worksheet are present in the **Selected** list.</span></span> <span data-ttu-id="9768b-110">Para obter mais informações, consulte [Entidades de dados](https://docs.microsoft.com/dynamics365/fin-ops-core/dev-itpro/financial/financial-dimension-configuration-integration#data-entities).</span><span class="sxs-lookup"><span data-stu-id="9768b-110">For more information, see [Data entities](https://docs.microsoft.com/dynamics365/fin-ops-core/dev-itpro/financial/financial-dimension-configuration-integration#data-entities).</span></span>
1. <span data-ttu-id="9768b-111">Baixe e abra o arquivo Excel na página **Demonstrativos**, na página **Transações de varejo** ou no bloco **Falhas na validação de transações** no espaço de trabalho **Finanças da loja**.</span><span class="sxs-lookup"><span data-stu-id="9768b-111">Download and open the Excel file from the **Statements** page, the **Retail transactions** page, or the **Transaction validation failures** tile in the **Store financials** workspace.</span></span>
1. <span data-ttu-id="9768b-112">Para alterar a dimensão financeira da transação, selecione **Design** e selecione o símbolo de lápis ao lado da linha **Transação (auditável)**.</span><span class="sxs-lookup"><span data-stu-id="9768b-112">To change the transaction financial dimension, select **Design**, and then select the pencil symbol next to the **Transaction (auditable)** row.</span></span>
1. <span data-ttu-id="9768b-113">Encontre e selecione o campo **FinancialDimensionDisplayValue**, selecione uma célula na parte do cabeçalho da planilha do Excel e selecione **Adicionar rótulo**.</span><span class="sxs-lookup"><span data-stu-id="9768b-113">Find and select the **FinancialDimensionDisplayValue** field, select a cell in the header part of the Excel worksheet, and then select **Add label**.</span></span>
1. <span data-ttu-id="9768b-114">Selecione uma célula abaixo da célula selecionada na etapa anterior, selecione **Adicionar valor** e, sem seguida, selecione **Atualizar**.</span><span class="sxs-lookup"><span data-stu-id="9768b-114">Select a cell below the cell that you selected in the previous step, select **Add Value**, and then select **Refresh**.</span></span> <span data-ttu-id="9768b-115">As dimensões financeiras serão adicionadas à planilha do Excel e poderão ser editadas e publicadas.</span><span class="sxs-lookup"><span data-stu-id="9768b-115">The financial dimensions are added to the Excel worksheet, and they can then be edited and published.</span></span>
1. <span data-ttu-id="9768b-116">Para alterar as dimensões nas linhas de transação, selecione a linha **Transações de vendas (auditável)**, selecione o símbolo de lápis e repita as etapas 6 e 7.</span><span class="sxs-lookup"><span data-stu-id="9768b-116">To change the dimensions on the transaction lines, select the **Sales transactions (auditable)** row, select the pencil symbol, and then repeat steps 6 and 7.</span></span>
1. <span data-ttu-id="9768b-117">Para alterar as dimensões nas linhas de pagamento, selecione a linha **Transações de pagamento (auditável)**, selecione o símbolo de lápis e repita as etapas 6 e 7.</span><span class="sxs-lookup"><span data-stu-id="9768b-117">To change the dimensions on the payment lines, select the **Payment transactions (auditable)** row, select the pencil symbol, and then repeat steps 6 and 7.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="9768b-118">Recursos adicionais</span><span class="sxs-lookup"><span data-stu-id="9768b-118">Additional resources</span></span>

[<span data-ttu-id="9768b-119">Editar e auditar transações cash and carry e de gerenciamento de caixa</span><span class="sxs-lookup"><span data-stu-id="9768b-119">Edit and audit cash and carry and cash management transactions</span></span>](edit-cash-trans.md)

[<span data-ttu-id="9768b-120">Editar e auditar transações da ordem online e assíncronas da ordem do cliente</span><span class="sxs-lookup"><span data-stu-id="9768b-120">Edit and audit online order and asynchronous customer order transactions</span></span>](edit-order-trans.md)

[<span data-ttu-id="9768b-121">Criar uma pasta de trabalho do Excel para editar transações de varejo</span><span class="sxs-lookup"><span data-stu-id="9768b-121">Create an Excel workbook to edit retail transactions</span></span>](create-excel-edit.md)

[<span data-ttu-id="9768b-122">Adicionar campos a uma pasta de trabalho do Excel para editar transações de varejo</span><span class="sxs-lookup"><span data-stu-id="9768b-122">Add fields to an Excel workbook to edit retail transactions</span></span>](add-fields-excel.md)
