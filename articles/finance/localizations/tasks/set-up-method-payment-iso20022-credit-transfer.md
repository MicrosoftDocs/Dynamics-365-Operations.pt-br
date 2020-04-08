---
title: Configurar método de pagamento para transferência de crédito de ISO20022
description: Este procedimento mostra como configurar o método de pagamento de fornecedor da transferência de crédito ISO20022 ou de qualquer outro tipo de pagamento usando o relatório eletrônico para gerar um arquivo.
author: mrolecki
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: VendPaymMode
audience: Application User
ms.reviewer: kfend
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: mrolecki
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: d6d60502cd7f749b71cf39cc38d8a39dcbb7b108
ms.sourcegitcommit: 57e1dafa186fec77ddd8ba9425d238e36e0f0998
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/18/2020
ms.locfileid: "3140108"
---
# <a name="set-up-method-of-payment-for-iso20022-credit-transfer"></a><span data-ttu-id="46a14-103">Configurar método de pagamento para transferência de crédito de ISO20022</span><span class="sxs-lookup"><span data-stu-id="46a14-103">Set up method of payment for ISO20022 credit transfer</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="46a14-104">Este procedimento mostra como configurar o método de pagamento de fornecedor da transferência de crédito ISO20022 ou de qualquer outro tipo de pagamento usando o relatório eletrônico para gerar um arquivo.</span><span class="sxs-lookup"><span data-stu-id="46a14-104">This procedure shows how to set up the vendor method of payment for ISO20022 credit transfer or any other payment type using electronic reporting to generate a file.</span></span> 

<span data-ttu-id="46a14-105">Antes de concluir esta tarefa, você deve exportar as configurações de formato e definir as contas de pagamento.</span><span class="sxs-lookup"><span data-stu-id="46a14-105">Before you complete this task, you must export format configurations and set up payment accounts.</span></span>

<span data-ttu-id="46a14-106">Essa tarefa foi criada usando a empresa de dados demonstrativos DEMF.</span><span class="sxs-lookup"><span data-stu-id="46a14-106">This task was created using the DEMF demo data company.</span></span>

<span data-ttu-id="46a14-107">Este é o terceiro dos cinco procedimentos que ilustram o processo de pagamento de fornecedores usando as configurações de relatório eletrônico.</span><span class="sxs-lookup"><span data-stu-id="46a14-107">This is the third procedure, out of five, that illustrates the vendor payment process using electronic reporting configurations.</span></span> <span data-ttu-id="46a14-108">Este procedimento é para um recurso que foi adicionado na versão 1611 do Dynamics 365 for Operations.</span><span class="sxs-lookup"><span data-stu-id="46a14-108">This procedure is for a feature that was added in Dynamics 365 for Operations version 1611.</span></span>

1. <span data-ttu-id="46a14-109">Vá para Contas a pagar > Configurar pagamento > Métodos de pagamento.</span><span class="sxs-lookup"><span data-stu-id="46a14-109">Go to Accounts payable > Payment setup > Methods of payment.</span></span>
2. <span data-ttu-id="46a14-110">Use o Filtro Rápido para localizar registros.</span><span class="sxs-lookup"><span data-stu-id="46a14-110">Use the Quick Filter to find records.</span></span> <span data-ttu-id="46a14-111">Por exemplo, filtre o campo Método de pagamento com um valor de 'SEPA CT'.</span><span class="sxs-lookup"><span data-stu-id="46a14-111">For example, filter on the Method of payment field with a value of 'SEPA CT'.</span></span>
3. <span data-ttu-id="46a14-112">Clique em Editar.</span><span class="sxs-lookup"><span data-stu-id="46a14-112">Click Edit.</span></span>
4. <span data-ttu-id="46a14-113">No campo Período, selecione 'Total'.</span><span class="sxs-lookup"><span data-stu-id="46a14-113">In the Period field, select 'Total'.</span></span>
5. <span data-ttu-id="46a14-114">No campo Tipo de liquidação, selecione 'Pagamento eletrônico'.</span><span class="sxs-lookup"><span data-stu-id="46a14-114">In the Payment type field, select 'Electronic payment'.</span></span>
6. <span data-ttu-id="46a14-115">Expanda a seção Formatos de arquivo.</span><span class="sxs-lookup"><span data-stu-id="46a14-115">Expand the File formats section.</span></span>
7. <span data-ttu-id="46a14-116">Selecione Sim no campo eletrônico Genérico do relatório.</span><span class="sxs-lookup"><span data-stu-id="46a14-116">Select Yes in the Generic electronic reporting field.</span></span>
8. <span data-ttu-id="46a14-117">No campo Exportar configuração de formato, insira ou selecione um valor.</span><span class="sxs-lookup"><span data-stu-id="46a14-117">In the Export format configuration field, enter or select a value.</span></span>
    * <span data-ttu-id="46a14-118">Na lista, selecione a transferência de crédito do valor ISO20022 (DE).</span><span class="sxs-lookup"><span data-stu-id="46a14-118">In the list, select the value ISO20022 Credit transfer (DE).</span></span> <span data-ttu-id="46a14-119">Se a lista estiver vazia, a configuração de formato de exportação do pagamento do fornecedor não foi importada e não está ativa.</span><span class="sxs-lookup"><span data-stu-id="46a14-119">If the list is empty, the vendor payment export format configuration is not imported and active.</span></span>  
9. <span data-ttu-id="46a14-120">No campo Tipo de conta, selecione 'Banco'.</span><span class="sxs-lookup"><span data-stu-id="46a14-120">In the Account type field, select 'Bank'.</span></span>
10. <span data-ttu-id="46a14-121">No campo Conta de pagamento, especifique os valores 'DEMF OPER'.</span><span class="sxs-lookup"><span data-stu-id="46a14-121">In the Payment account field, specify the values 'DEMF OPER'.</span></span>
11. <span data-ttu-id="46a14-122">Clique em Salvar.</span><span class="sxs-lookup"><span data-stu-id="46a14-122">Click Save.</span></span>

