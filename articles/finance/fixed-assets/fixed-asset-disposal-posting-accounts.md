---
title: Contas de lançamento de alienação de ativos fixos
description: Este tópico explica como configurar contas de lançamento de contabilidade para descartar ativos.
author: ShylaThompson
ms.date: 06/20/2017
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: AssetPosting
audience: Application User
ms.reviewer: roschlom
ms.custom: 3461
ms.assetid: dfdc0730-e030-48cc-8d93-15bdc7b23776
ms.search.region: Global
ms.author: saraschi
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 5d1d6a3dc6348e64bcf247544bc7b56c5314db4c
ms.sourcegitcommit: 0e8db169c3f90bd750826af76709ef5d621fd377
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/01/2021
ms.locfileid: "5826849"
---
# <a name="fixed-asset-disposal-posting-accounts"></a><span data-ttu-id="bdee1-103">Contas de lançamento de alienação de ativos fixos</span><span class="sxs-lookup"><span data-stu-id="bdee1-103">Fixed asset disposal posting accounts</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="bdee1-104">Este tópico explica como configurar contas de lançamento de contabilidade para descartar ativos.</span><span class="sxs-lookup"><span data-stu-id="bdee1-104">This topic explains how to set up general ledger posting accounts for disposing of assets.</span></span>

<span data-ttu-id="bdee1-105">Na página Perfis de lançamentos de ativo fixo, na Guia Rápida Contas contábeis, selecione Descarte - Descarte de sucata para configurar lançamentos para o razão.</span><span class="sxs-lookup"><span data-stu-id="bdee1-105">In the Fixed asset posting profiles page, on the Ledger accounts FastTab, select Disposal - sale and Disposal - scrap to set up postings to the ledger.</span></span>

<span data-ttu-id="bdee1-106">Para ambos os tipos de transação, a conta contábil é creditada no valor de alienação do ativo fixo.</span><span class="sxs-lookup"><span data-stu-id="bdee1-106">For both transaction types, the ledger account is credited for the disposal value of the fixed asset.</span></span> <span data-ttu-id="bdee1-107">O débito é lançado em uma conta de baixa, que pode ser, por exemplo, uma conta bancária.</span><span class="sxs-lookup"><span data-stu-id="bdee1-107">The debit is posted to an offset account, which might be, for example, a bank account.</span></span> <span data-ttu-id="bdee1-108">Caso um ativo fixo seja vendido para um cliente, a conta de cliente será usada em lugar da conta de compensação.</span><span class="sxs-lookup"><span data-stu-id="bdee1-108">If a fixed asset is sold to a customer, the customer account is used instead of the offset account.</span></span>

<span data-ttu-id="bdee1-109">Clique em Descarte e em Venda ou sucateamento e configure as contas detalhadas para estornar o valor líquido contábil do ativo fixo.</span><span class="sxs-lookup"><span data-stu-id="bdee1-109">Click Disposal and then click Sale or Scrap, and then set up detailed accounts to reverse the net book value of the fixed asset.</span></span> <span data-ttu-id="bdee1-110">Você também pode inserir informações nos campos Lançar valor e Tipo de valor de venda na página Parâmetros de alienação.</span><span class="sxs-lookup"><span data-stu-id="bdee1-110">You can also enter information in the Post value and Sales value type fields in the Disposal parameters page.</span></span> 

<span data-ttu-id="bdee1-111">A transação de alienação de um ativo em um grupo de valor baixo reduz o valor líquido contábil do grupo de valor baixo somente pelo valor alienado.</span><span class="sxs-lookup"><span data-stu-id="bdee1-111">The disposal transaction for an asset in a low-value pool reduces the net book value of the low-value pool by the disposed amount only.</span></span> <span data-ttu-id="bdee1-112">Porém, quando a venda de um ativo excede o valor líquido contábil do grupo de valor baixo, o valor líquido contábil é reduzido a zero.</span><span class="sxs-lookup"><span data-stu-id="bdee1-112">However, when the sale of an asset exceeds the net book value of the low-value pool, the net book value is reduced to zero.</span></span>







[!INCLUDE[footer-include](../../includes/footer-banner.md)]