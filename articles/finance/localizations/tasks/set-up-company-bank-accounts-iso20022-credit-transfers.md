---
title: Configurar contas bancárias de empresa para transferências de crédito de ISO20022
description: Este procedimento mostra como configurar as informações da conta bancária específica da empresa que são necessárias para a geração do arquivo de pagamento.
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
ms.openlocfilehash: 5ad1ebbea9bca41f43f3f4098114116e32f8517b
ms.sourcegitcommit: eaf330dbee1db96c20d5ac479f007747bea079eb
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/15/2021
ms.locfileid: "5205461"
---
# <a name="set-up-company-bank-accounts-for-iso20022-credit-transfers"></a><span data-ttu-id="c61a5-103">Configurar contas bancárias de empresa para transferências de crédito de ISO20022</span><span class="sxs-lookup"><span data-stu-id="c61a5-103">Set up company bank accounts for ISO20022 credit transfers</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="c61a5-104">Este procedimento mostra como configurar as informações da conta bancária específica da empresa que são necessárias para a geração do arquivo de pagamento.</span><span class="sxs-lookup"><span data-stu-id="c61a5-104">This procedure shows how to set up company-specific bank account information that is required for payment file generation.</span></span> <span data-ttu-id="c61a5-105">Você configura as informações necessárias para gerar o formato de transferência de crédito ISO 20022 mas, dependendo do formato, outras informações podem ser necessárias, como a ID da empresa ou o código de classificação.</span><span class="sxs-lookup"><span data-stu-id="c61a5-105">You set up information required to generate ISO 20022 credit transfer format but depending on the format there might be other information required, such as the Company ID or the Sort code.</span></span> 

<span data-ttu-id="c61a5-106">A empresa de dados demonstrativos utilizada para criar esse procedimento é a DEMF.</span><span class="sxs-lookup"><span data-stu-id="c61a5-106">The demo data company used to create this procedure is DEMF.</span></span>

<span data-ttu-id="c61a5-107">Este é o segundo dos cinco procedimentos que ilustram o processo de pagamento de fornecedores usando as configurações de relatório eletrônico.</span><span class="sxs-lookup"><span data-stu-id="c61a5-107">This is the second procedure, out of five, that illustrates the vendor payment process using electronic reporting configurations.</span></span> <span data-ttu-id="c61a5-108">Este procedimento é para um recurso que foi adicionado na versão 1611 do Dynamics 365 for Operations.</span><span class="sxs-lookup"><span data-stu-id="c61a5-108">This procedure is for a feature that was added in Dynamics 365 for Operations version 1611.</span></span>


## <a name="set-up-iban-and-swift-code"></a><span data-ttu-id="c61a5-109">Configurar IBAN e código SWIFT</span><span class="sxs-lookup"><span data-stu-id="c61a5-109">Set up IBAN and SWIFT code</span></span>
1. <span data-ttu-id="c61a5-110">Vá para Gerenciamento de caixa e bancos > Contas bancárias.</span><span class="sxs-lookup"><span data-stu-id="c61a5-110">Go to Cash and bank management > Bank accounts.</span></span>
2. <span data-ttu-id="c61a5-111">Use o Filtro Rápido para filtrar o campo Conta bancária com o valor 'DEMF OPER'.</span><span class="sxs-lookup"><span data-stu-id="c61a5-111">Use the Quick Filter to filter on the Bank account field with a value of 'DEMF OPER'.</span></span>
3. <span data-ttu-id="c61a5-112">Clique em DEMF OPER para abrir os detalhes da conta bancária.</span><span class="sxs-lookup"><span data-stu-id="c61a5-112">Click DEMF OPER to open bank account details.</span></span>
4. <span data-ttu-id="c61a5-113">Clique em Editar.</span><span class="sxs-lookup"><span data-stu-id="c61a5-113">Click Edit.</span></span>
5. <span data-ttu-id="c61a5-114">Expanda a seção Identificação adicional.</span><span class="sxs-lookup"><span data-stu-id="c61a5-114">Expand the Additional identification section.</span></span>
6. <span data-ttu-id="c61a5-115">No campo IBAN, digite ''DE89370400440532013000'.</span><span class="sxs-lookup"><span data-stu-id="c61a5-115">In the IBAN field, type 'DE89370400440532013000'.</span></span>
7. <span data-ttu-id="c61a5-116">No campo Código SWIFT, digite 'DEUTDEFF'.</span><span class="sxs-lookup"><span data-stu-id="c61a5-116">In the SWIFT code field, type 'DEUTDEFF'.</span></span>
    * <span data-ttu-id="c61a5-117">Observe que o SWIFT\BIC não é necessário para vários formatos de pagamento, no entanto, é recomendável registrá-lo em uma conta bancária.</span><span class="sxs-lookup"><span data-stu-id="c61a5-117">Note that SWIFT\BIC is not required for many payment formats, however it is recommended to have it registered for a bank account.</span></span>  
8. <span data-ttu-id="c61a5-118">Clique em Salvar.</span><span class="sxs-lookup"><span data-stu-id="c61a5-118">Click Save.</span></span>

## <a name="set-up-bank-account-for-the-legal-entity"></a><span data-ttu-id="c61a5-119">Configurar conta bancária da entidade legal</span><span class="sxs-lookup"><span data-stu-id="c61a5-119">Set up bank account for the legal entity</span></span>
1. <span data-ttu-id="c61a5-120">Vá para Administração da organização > Organizações > Entidades legais.</span><span class="sxs-lookup"><span data-stu-id="c61a5-120">Go to Organization administration > Organizations > Legal entities.</span></span>
2. <span data-ttu-id="c61a5-121">Clique em Editar.</span><span class="sxs-lookup"><span data-stu-id="c61a5-121">Click Edit.</span></span>
3. <span data-ttu-id="c61a5-122">Expanda a seção Informações de conta bancária.</span><span class="sxs-lookup"><span data-stu-id="c61a5-122">Expand the Bank account information section.</span></span>
4. <span data-ttu-id="c61a5-123">No campo Conta bancária, insira ou selecione um valor.</span><span class="sxs-lookup"><span data-stu-id="c61a5-123">In the Bank account field, enter or select a value.</span></span>
5. <span data-ttu-id="c61a5-124">Clique em Salvar.</span><span class="sxs-lookup"><span data-stu-id="c61a5-124">Click Save.</span></span>



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]