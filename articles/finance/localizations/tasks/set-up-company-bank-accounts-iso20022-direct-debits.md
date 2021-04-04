---
title: Configurar contas bancárias de empresa para débitos diretos de ISO20022
description: Esta tarefa orienta como configurar com as informações de conta bancária específicas da empresa que são necessárias para gerar arquivos de pagamento de cliente.
author: mrolecki
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: BankAccountTable, OMLegalEntity, BankAccountTableLookUp
audience: Application User
ms.reviewer: kfend
ms.search.region: Global
ms.author: mrolecki
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 8079dadd09f3e781bcfde21974882cdd59dec809
ms.sourcegitcommit: eaf330dbee1db96c20d5ac479f007747bea079eb
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/15/2021
ms.locfileid: "5256587"
---
# <a name="set-up-company-bank-accounts-for-iso20022-direct-debits"></a><span data-ttu-id="9e321-103">Configurar contas bancárias de empresa para débitos diretos de ISO20022</span><span class="sxs-lookup"><span data-stu-id="9e321-103">Set up company bank accounts for ISO20022 direct debits</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="9e321-104">Esta tarefa orienta como configurar com as informações de conta bancária específicas da empresa que são necessárias para gerar arquivos de pagamento de cliente.</span><span class="sxs-lookup"><span data-stu-id="9e321-104">This task walks you through setting up the company specific bank account information that is required for generating customer payment files.</span></span> <span data-ttu-id="9e321-105">Este procedimento usa o formato de débito direto ISO 20022 como exemplo.</span><span class="sxs-lookup"><span data-stu-id="9e321-105">This procedure uses the ISO 20022 direct debit format as an example.</span></span> <span data-ttu-id="9e321-106">Outros formatos podem exigir informações de configuração adicionais, como a ID da empresa ou o código de classificação.</span><span class="sxs-lookup"><span data-stu-id="9e321-106">Other formats might require additional setup information like the Company ID or the Sort code.</span></span>



<span data-ttu-id="9e321-107">Essa tarefa foi criada usando a empresa de dados demonstrativos DEMF.</span><span class="sxs-lookup"><span data-stu-id="9e321-107">This task was created using the demo data company DEMF.</span></span>



<span data-ttu-id="9e321-108">Este é o segundo dos cinco procedimentos que demonstram o processo de pagamento de clientes usando as configurações de relatório eletrônico.</span><span class="sxs-lookup"><span data-stu-id="9e321-108">This is the second of five procedures that demonstrate the customer payment process using electronic reporting configurations.</span></span>


## <a name="set-up-the-iban-and-swift-codes"></a><span data-ttu-id="9e321-109">Configurar códigos IBAN e SWIFT</span><span class="sxs-lookup"><span data-stu-id="9e321-109">Set up the IBAN and SWIFT codes</span></span>
1. <span data-ttu-id="9e321-110">Vá para Gerenciamento de caixa e bancos > Contas bancárias.</span><span class="sxs-lookup"><span data-stu-id="9e321-110">Go to Cash and bank management > Bank accounts.</span></span>
2. <span data-ttu-id="9e321-111">Use o Filtro Rápido para filtrar o campo Conta bancária com o valor 'DEMF OPER'.</span><span class="sxs-lookup"><span data-stu-id="9e321-111">Use the Quick Filter to filter on the Bank account field with a value of 'DEMF OPER'.</span></span>
3. <span data-ttu-id="9e321-112">Na lista, clique no link na linha selecionada.</span><span class="sxs-lookup"><span data-stu-id="9e321-112">In the list, click the link in the selected row.</span></span>
    * <span data-ttu-id="9e321-113">Por exemplo, clique em 'DEMF OPER' para abrir os detalhes da conta bancária.</span><span class="sxs-lookup"><span data-stu-id="9e321-113">For example, click 'DEMF OPER' to open the bank account details.</span></span>  
4. <span data-ttu-id="9e321-114">Clique em Editar.</span><span class="sxs-lookup"><span data-stu-id="9e321-114">Click Edit.</span></span>
5. <span data-ttu-id="9e321-115">Expanda ou recolha a seção Identificação adicional.</span><span class="sxs-lookup"><span data-stu-id="9e321-115">Expand or collapse the Additional identification section.</span></span>
6. <span data-ttu-id="9e321-116">No campo IBAN, digite um valor.</span><span class="sxs-lookup"><span data-stu-id="9e321-116">In the IBAN field, type a value.</span></span>
    * <span data-ttu-id="9e321-117">Por exemplo, insira "DE89370400440532013000".</span><span class="sxs-lookup"><span data-stu-id="9e321-117">For example, enter 'DE89370400440532013000'.</span></span>  
7. <span data-ttu-id="9e321-118">No campo Código SWIFT, digite um valor.</span><span class="sxs-lookup"><span data-stu-id="9e321-118">In the SWIFT code field, type a value.</span></span>
    * <span data-ttu-id="9e321-119">Por exemplo, insira "DEUTDEFF".</span><span class="sxs-lookup"><span data-stu-id="9e321-119">For example, enter 'DEUTDEFF'.</span></span>    <span data-ttu-id="9e321-120">Observe que o SWIFT\BIC não é obrigatório para vários formatos de pagamento, no entanto, é recomendável registrá-lo em uma conta bancária.</span><span class="sxs-lookup"><span data-stu-id="9e321-120">Please note that SWIFT \ BIC is not mandatory for many payment formats however it is recommended to have it registered for a bank account.</span></span>  
8. <span data-ttu-id="9e321-121">Clique em Salvar.</span><span class="sxs-lookup"><span data-stu-id="9e321-121">Click Save.</span></span>

## <a name="set-up-a-bank-account-for-the-legal-entity"></a><span data-ttu-id="9e321-122">Configurar conta bancária da entidade legal</span><span class="sxs-lookup"><span data-stu-id="9e321-122">Set up a bank account for the legal entity</span></span>
1. <span data-ttu-id="9e321-123">Vá para Administração da organização > Organizações > Entidades legais.</span><span class="sxs-lookup"><span data-stu-id="9e321-123">Go to Organization administration > Organizations > Legal entities.</span></span>
2. <span data-ttu-id="9e321-124">Clique em Editar.</span><span class="sxs-lookup"><span data-stu-id="9e321-124">Click Edit.</span></span>
3. <span data-ttu-id="9e321-125">Expandir ou recolher a seção Informações de conta bancária.</span><span class="sxs-lookup"><span data-stu-id="9e321-125">Expand or collapse the Bank account information section.</span></span>
4. <span data-ttu-id="9e321-126">No campo Conta bancária, clique no botão suspenso para abrir a pesquisa.</span><span class="sxs-lookup"><span data-stu-id="9e321-126">In the Bank account field, click the drop-down button to open the lookup.</span></span>
5. <span data-ttu-id="9e321-127">Na lista, clique no link na linha selecionada.</span><span class="sxs-lookup"><span data-stu-id="9e321-127">In the list, click the link in the selected row.</span></span>
    * <span data-ttu-id="9e321-128">Por exemplo, selecione a conta bancária "DEMF OPER".</span><span class="sxs-lookup"><span data-stu-id="9e321-128">For example, select the "DEMF OPER" bank account.</span></span>  
6. <span data-ttu-id="9e321-129">Clique em Salvar.</span><span class="sxs-lookup"><span data-stu-id="9e321-129">Click Save.</span></span>



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]