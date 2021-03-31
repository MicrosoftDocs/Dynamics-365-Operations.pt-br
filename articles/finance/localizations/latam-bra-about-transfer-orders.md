---
title: Ordens de transferência (Brasil)
description: Este tópico fornece informações sobre as ordens de transferência do Brasil.
author: ShylaThompson
manager: AnnBe
ms.date: 09/13/2018
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
audience: Application User
ms.reviewer: kfend
ms.search.region: Brazil
ms.author: roschlom
ms.search.validFrom: 2017-12-31
ms.dyn365.ops.version: 7.2999999999999998
ms.openlocfilehash: a6bdd6b3ed73d065ce0e39d02165f81fd93660c1
ms.sourcegitcommit: eaf330dbee1db96c20d5ac479f007747bea079eb
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/15/2021
ms.locfileid: "5226188"
---
# <a name="transfer-orders-brazil"></a><span data-ttu-id="fce97-103">Ordens de transferência (Brasil)</span><span class="sxs-lookup"><span data-stu-id="fce97-103">Transfer orders (Brazil)</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="fce97-104">Você pode usar ordens de transferência para transferir itens de estoque entre os depósitos que estão localizados em estabelecimentos fiscais diferentes.</span><span class="sxs-lookup"><span data-stu-id="fce97-104">You can use transfer orders to transfer inventory items between warehouses that are located at different fiscal establishments.</span></span> <span data-ttu-id="fce97-105">Você também pode transferir itens de estoque para outro estabelecimento fiscal.</span><span class="sxs-lookup"><span data-stu-id="fce97-105">You can also transfer inventory items to another fiscal establishment.</span></span>

<span data-ttu-id="fce97-106">Quando você transfere os itens entre estabelecimentos fiscais diferentes, as notas fiscais de transferência são emitidas ou recebidas:</span><span class="sxs-lookup"><span data-stu-id="fce97-106">When you transfer the items between different fiscal establishments, the following transfer fiscal documents are issued or received:</span></span>

  - <span data-ttu-id="fce97-107">Nota fiscal de saída – emitido quando você envia itens a um depósito que está localizado em um estabelecimento fiscal diferente.</span><span class="sxs-lookup"><span data-stu-id="fce97-107">Outbound fiscal document – Issued when you ship items to a warehouse that is located at a different fiscal establishment.</span></span>
  
  - <span data-ttu-id="fce97-108">Nota fiscal de entrada – recebido quando você recebe itens de um depósito que está localizado em um estabelecimento fiscal diferente.</span><span class="sxs-lookup"><span data-stu-id="fce97-108">Inbound fiscal document – Received when you receive items from a warehouse that is located at a different fiscal establishment.</span></span>

<span data-ttu-id="fce97-109">Você pode fazer o seguinte para transferir itens entre estabelecimentos fiscais usando ordens de transferência:</span><span class="sxs-lookup"><span data-stu-id="fce97-109">You can do the following to transfer items between fiscal establishments by using transfer orders:</span></span>

  - <span data-ttu-id="fce97-110">Configurar uma matriz de Código Fiscal de Operações e Prestações (CFOP) para a transferência de estabelecimento fiscal ou tipos de transação de transferência de terceiros.</span><span class="sxs-lookup"><span data-stu-id="fce97-110">Set up a Código Fiscal de Operações e Prestações (CFOP) matrix for fiscal establishment transfer or third-party transfer transaction types.</span></span> <span data-ttu-id="fce97-111">Para obter mais informações, consulte [Configurar a matriz CFOP](https://review.docs.microsoft.com/dynamicsax-2012/appuser-itpro/bra-set-up-the-cfop-matrix?branch=master).</span><span class="sxs-lookup"><span data-stu-id="fce97-111">For more information, see [Set up the CFOP matrix](https://review.docs.microsoft.com/dynamicsax-2012/appuser-itpro/bra-set-up-the-cfop-matrix?branch=master).</span></span>

  - <span data-ttu-id="fce97-112">Configurar uma matriz de imposto para um grupo de estabelecimento fiscal usando o tipo de transação de estabelecimento fiscal.</span><span class="sxs-lookup"><span data-stu-id="fce97-112">Set up a tax matrix for a fiscal establishment group by using the fiscal establishment transaction type.</span></span> <span data-ttu-id="fce97-113">Para obter mais informações, consulte [Configurar uma matriz de imposto](https://review.docs.microsoft.com/dynamicsax-2012/appuser-itpro/bra-set-up-a-tax-matrix?branch=master).</span><span class="sxs-lookup"><span data-stu-id="fce97-113">For more information, see [Set up a tax matrix](https://review.docs.microsoft.com/dynamicsax-2012/appuser-itpro/bra-set-up-a-tax-matrix?branch=master).</span></span>

  - <span data-ttu-id="fce97-114">Criar e enviar uma ordem de transferência para criar uma nota fiscal de saída.</span><span class="sxs-lookup"><span data-stu-id="fce97-114">Create and ship a transfer order to create an outbound fiscal document.</span></span> <span data-ttu-id="fce97-115">Para obter mais informações, consulte [Criar um documento fiscal para transferência de saída](https://review.docs.microsoft.com/dynamicsax-2012/appuser-itpro/bra-create-an-outbound-transfer-fiscal-document?branch=master).</span><span class="sxs-lookup"><span data-stu-id="fce97-115">For more information, see [Create an outbound transfer fiscal document](https://review.docs.microsoft.com/dynamicsax-2012/appuser-itpro/bra-create-an-outbound-transfer-fiscal-document?branch=master).</span></span>

  - <span data-ttu-id="fce97-116">Receber uma ordem de transferência para criar uma nota fiscal de entrada.</span><span class="sxs-lookup"><span data-stu-id="fce97-116">Receive a transfer order to create an inbound fiscal document.</span></span> <span data-ttu-id="fce97-117">Para obter mais informações, consulte [Receber nota fiscal para transferência de entrada](https://review.docs.microsoft.com/dynamicsax-2012/appuser-itpro/bra-receive-an-inbound-transfer-fiscal-document?branch=master).</span><span class="sxs-lookup"><span data-stu-id="fce97-117">For more information, see [Receive an inbound transfer fiscal document](https://review.docs.microsoft.com/dynamicsax-2012/appuser-itpro/bra-receive-an-inbound-transfer-fiscal-document?branch=master).</span></span>

  - <span data-ttu-id="fce97-118">Retornar uma nota fiscal de transferência.</span><span class="sxs-lookup"><span data-stu-id="fce97-118">Return a transfer fiscal document.</span></span> <span data-ttu-id="fce97-119">Para obter mais informações, consulte [Retornar uma nota fiscal de transferência](https://review.docs.microsoft.com/dynamicsax-2012/appuser-itpro/bra-return-a-transfer-fiscal-document?branch=master).</span><span class="sxs-lookup"><span data-stu-id="fce97-119">For more information, see [Return a transfer fiscal document](https://review.docs.microsoft.com/dynamicsax-2012/appuser-itpro/bra-return-a-transfer-fiscal-document?branch=master).</span></span>

  - <span data-ttu-id="fce97-120">Cancelar uma ordem de transferência incorreta.</span><span class="sxs-lookup"><span data-stu-id="fce97-120">Cancel an incorrect transfer order.</span></span> <span data-ttu-id="fce97-121">Para obter mais informações, consulte [Cancelar uma nota fiscal de transferência](https://review.docs.microsoft.com/dynamicsax-2012/appuser-itpro/bra-cancel-a-transfer-fiscal-document?branch=master).</span><span class="sxs-lookup"><span data-stu-id="fce97-121">For more information, see [Cancel a transfer fiscal document](https://review.docs.microsoft.com/dynamicsax-2012/appuser-itpro/bra-cancel-a-transfer-fiscal-document?branch=master).</span></span>


[!INCLUDE[footer-include](../../includes/footer-banner.md)]