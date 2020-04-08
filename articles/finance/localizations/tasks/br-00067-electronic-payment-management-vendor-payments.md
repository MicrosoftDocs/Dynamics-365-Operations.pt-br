---
title: Gerenciamento de pagamento eletrônico para pagamentos de fornecedores (Brasil)
description: É possível fazer pagamentos eletrônicos pela transferência de arquivos entre uma entidade legal e um banco.
author: sndray
manager: AnnBe
ms.date: 06/27/2017
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
audience: Application User
ms.reviewer: kfend
ms.search.scope: Operations
ms.search.region: Brazil
ms.search.industry: Manufacturing;Distribution;Service industries
ms.author: sndray
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: bd778e8c7ef90fe16664979cf7dc768e95afa27c
ms.sourcegitcommit: c69926b4285cb2ec2d9ce1ad72d1cb852024dd5e
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/18/2020
ms.locfileid: "3138294"
---
# <a name="electronic-payment-management-for-vendor-payments-brazil"></a><span data-ttu-id="7a2fe-103">Gerenciamento de pagamento eletrônico para pagamentos de fornecedores (Brasil)</span><span class="sxs-lookup"><span data-stu-id="7a2fe-103">Electronic payment management for vendor payments (Brazil)</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="7a2fe-104">É possível fazer pagamentos eletrônicos pela transferência de arquivos entre uma entidade legal e um banco.</span><span class="sxs-lookup"><span data-stu-id="7a2fe-104">You can make electronic payments by transferring files between a legal entity and a bank.</span></span> <span data-ttu-id="7a2fe-105">É possível gerar e enviar um arquivo de remessa eletrônica para um banco.</span><span class="sxs-lookup"><span data-stu-id="7a2fe-105">You can generate and send an electronic remittance file to a bank.</span></span> <span data-ttu-id="7a2fe-106">Nesse caso, o arquivo de exportação contém informações sobre as faturas que devem ser recebidas ou pagas, as solicitações de faturas de devolução, ou as alterações nos endereços de cliente ou de fornecedor.</span><span class="sxs-lookup"><span data-stu-id="7a2fe-106">In this case, the export file contains information about invoices that must be received or paid, requests for return invoices, or changes to customer or vendor addresses.</span></span> <span data-ttu-id="7a2fe-107">Como alternativa, é possível importar um arquivo de devolução de um banco.</span><span class="sxs-lookup"><span data-stu-id="7a2fe-107">Alternatively, you can import a return file from a bank.</span></span> <span data-ttu-id="7a2fe-108">Nesse caso, o arquivo de devolução contém informações sobre a aceitação de uma fatura, junto com o número de pagamento fornecido pelo banco, ou informações sobre os pagamentos recebidos de um cliente ou pagos a um fornecedor.</span><span class="sxs-lookup"><span data-stu-id="7a2fe-108">In this case, the return file contains either information about the acceptance of an invoice together with the payment number that is provided by the bank, or information about the payments that are received from a customer or paid to a vendor.</span></span> <span data-ttu-id="7a2fe-109">Esta tarefa usa a empresa de demonstração BRMF.</span><span class="sxs-lookup"><span data-stu-id="7a2fe-109">This task uses the BRMF demo company.</span></span>

1. <span data-ttu-id="7a2fe-110">Vá para Razão de compra > Pagamentos > Transferências de pagamento.</span><span class="sxs-lookup"><span data-stu-id="7a2fe-110">Go to Purchase ledger > Payments > Payment transfers.</span></span>
2. <span data-ttu-id="7a2fe-111">Na lista, marque a linha selecionada.</span><span class="sxs-lookup"><span data-stu-id="7a2fe-111">In the list, mark the selected row.</span></span>
3. <span data-ttu-id="7a2fe-112">Clique em Arquivo retorno - Fornecedor.</span><span class="sxs-lookup"><span data-stu-id="7a2fe-112">Click Return file - vendor.</span></span>
4. <span data-ttu-id="7a2fe-113">No campo Condições de pagamento, insira ou selecione um valor.</span><span class="sxs-lookup"><span data-stu-id="7a2fe-113">In the Method of payment field, enter or select a value.</span></span>
5. <span data-ttu-id="7a2fe-114">Clique em OK.</span><span class="sxs-lookup"><span data-stu-id="7a2fe-114">Click OK.</span></span>
6. <span data-ttu-id="7a2fe-115">Clique em OK.</span><span class="sxs-lookup"><span data-stu-id="7a2fe-115">Click OK.</span></span>
    * <span data-ttu-id="7a2fe-116">O status dos pagamentos é atualizado no campo Status de pagamento na página Transferências de pagamento.</span><span class="sxs-lookup"><span data-stu-id="7a2fe-116">The status of the payments is updated in the Payments status field on the Payment transfers page.</span></span> <span data-ttu-id="7a2fe-117">O novo status se baseia no status do pagamento no arquivo de devolução.</span><span class="sxs-lookup"><span data-stu-id="7a2fe-117">The new status is based on the status of the payment in the return file.</span></span>  
7. <span data-ttu-id="7a2fe-118">Clique em Lançar.</span><span class="sxs-lookup"><span data-stu-id="7a2fe-118">Click Post.</span></span>
8. <span data-ttu-id="7a2fe-119">No campo Nome do novo diário, digite um valor.</span><span class="sxs-lookup"><span data-stu-id="7a2fe-119">In the New journal name field, type a value.</span></span>
9. <span data-ttu-id="7a2fe-120">Clique em OK.</span><span class="sxs-lookup"><span data-stu-id="7a2fe-120">Click OK.</span></span>
10. <span data-ttu-id="7a2fe-121">Feche a página.</span><span class="sxs-lookup"><span data-stu-id="7a2fe-121">Close the page.</span></span>

