---
title: Configurar fornecedores e contas bancárias de fornecedor para transferências de crédito de ISO20022
description: Este procedimento demonstra como configurar o fornecedor e as informações da conta bancária específica do fornecedor necessárias para a Transferência de Crédito ISO20022 ou para a geração do arquivo de pagamento de qualquer fornecedor.
author: mrolecki
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: VendTable, VendBankAccounts
audience: Application User
ms.reviewer: kfend
ms.search.region: Global
ms.author: mrolecki
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 47735d41fde4c5f71ec1c3209446a593e1f4180c
ms.sourcegitcommit: 0e8db169c3f90bd750826af76709ef5d621fd377
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/01/2021
ms.locfileid: "5813410"
---
# <a name="set-up-vendors-and-vendor-bank-accounts-for-iso20022-credit-transfers"></a><span data-ttu-id="8702c-103">Configurar fornecedores e contas bancárias de fornecedor para transferências de crédito de ISO20022</span><span class="sxs-lookup"><span data-stu-id="8702c-103">Set up vendors and vendor bank accounts for ISO20022 credit transfers</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="8702c-104">Este procedimento demonstra como configurar o fornecedor e as informações da conta bancária específica do fornecedor necessárias para a Transferência de Crédito ISO20022 ou para a geração do arquivo de pagamento de qualquer fornecedor.</span><span class="sxs-lookup"><span data-stu-id="8702c-104">This procedure demonstrates how to set up the vendor and vendor specific bank account information required for ISO20022 Credit transfer or any other vendor payment file generation.</span></span> 

<span data-ttu-id="8702c-105">A empresa de dados demonstrativos utilizada para criar esse procedimento é a DEMF.</span><span class="sxs-lookup"><span data-stu-id="8702c-105">The demo data company used to create this procedure is DEMF.</span></span>
<span data-ttu-id="8702c-106">Este é o quarto dos cinco procedimentos que ilustram o processo de pagamento de fornecedores usando as configurações de relatório eletrônico.</span><span class="sxs-lookup"><span data-stu-id="8702c-106">This is the fourth procedure, out of five, that illustrates the vendor payment process using electronic reporting configurations.</span></span> <span data-ttu-id="8702c-107">Este procedimento é para um recurso que foi adicionado na versão 1611 do Dynamics 365 for Operations.</span><span class="sxs-lookup"><span data-stu-id="8702c-107">This procedure is for a feature that was added in Dynamics 365 for Operations version 1611.</span></span>


## <a name="set-up-bank-details"></a><span data-ttu-id="8702c-108">Configurar detalhes do banco</span><span class="sxs-lookup"><span data-stu-id="8702c-108">Set up bank details</span></span>
1. <span data-ttu-id="8702c-109">Vá para Contas a pagar > Fornecedores > Todos os fornecedores.</span><span class="sxs-lookup"><span data-stu-id="8702c-109">Go to Accounts payable > Vendors > All vendors.</span></span>
2. <span data-ttu-id="8702c-110">Use o Filtro Rápido para localizar registros.</span><span class="sxs-lookup"><span data-stu-id="8702c-110">Use the Quick Filter to find records.</span></span> <span data-ttu-id="8702c-111">Por exemplo, no campo Conta de fornecedor, filtre com um valor de 'DE-001'.</span><span class="sxs-lookup"><span data-stu-id="8702c-111">For example, filter on the Vendor account field with a value of 'DE-001'.</span></span>
3. <span data-ttu-id="8702c-112">Clique em DE-001 para abrir detalhes de fornecedor.</span><span class="sxs-lookup"><span data-stu-id="8702c-112">Click DE-001 to open vendor details.</span></span>
4. <span data-ttu-id="8702c-113">No Painel de Ação, clique em Fornecedor.</span><span class="sxs-lookup"><span data-stu-id="8702c-113">On the Action Pane, click Vendor.</span></span>
5. <span data-ttu-id="8702c-114">Clique em Contas bancárias.</span><span class="sxs-lookup"><span data-stu-id="8702c-114">Click Bank accounts.</span></span>
6. <span data-ttu-id="8702c-115">Clique em Editar.</span><span class="sxs-lookup"><span data-stu-id="8702c-115">Click Edit.</span></span>
    * <span data-ttu-id="8702c-116">Se não houver nenhuma conta bancária disponível, você precisa criar uma nova.</span><span class="sxs-lookup"><span data-stu-id="8702c-116">If there is no bank account available, you need to create a new one.</span></span>  
7. <span data-ttu-id="8702c-117">No campo Código SWIFT, digite 'COBADEFFXXX'.</span><span class="sxs-lookup"><span data-stu-id="8702c-117">In the SWIFT code field, type 'COBADEFFXXX'.</span></span>
8. <span data-ttu-id="8702c-118">No campo IBAN, digite ''DE36200400000628808808'.</span><span class="sxs-lookup"><span data-stu-id="8702c-118">In the IBAN field, type 'DE36200400000628808808'.</span></span>
9. <span data-ttu-id="8702c-119">Feche a página.</span><span class="sxs-lookup"><span data-stu-id="8702c-119">Close the page.</span></span>

## <a name="set-up-a-method-of-payment-for-the-vendor"></a><span data-ttu-id="8702c-120">Configurar um método de pagamento para o fornecedor</span><span class="sxs-lookup"><span data-stu-id="8702c-120">Set up a method of payment for the vendor</span></span>
1. <span data-ttu-id="8702c-121">Clique em Editar.</span><span class="sxs-lookup"><span data-stu-id="8702c-121">Click Edit.</span></span>
2. <span data-ttu-id="8702c-122">Expandir ou recolher a seção Pagamento.</span><span class="sxs-lookup"><span data-stu-id="8702c-122">Expand or collapse the Payment section.</span></span>
3. <span data-ttu-id="8702c-123">No campo Método de pagamento, clique no botão suspenso para abrir a pesquisa.</span><span class="sxs-lookup"><span data-stu-id="8702c-123">In the Method of payment field, click the drop-down button to open the lookup.</span></span>
4. <span data-ttu-id="8702c-124">Na lista, clique no link na linha SEPA CT.</span><span class="sxs-lookup"><span data-stu-id="8702c-124">In the list, click the link in the SEPA CT row.</span></span>
5. <span data-ttu-id="8702c-125">Clique em Salvar.</span><span class="sxs-lookup"><span data-stu-id="8702c-125">Click Save.</span></span>



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]