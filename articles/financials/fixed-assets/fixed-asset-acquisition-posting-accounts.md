---
title: Contas de lançamento de aquisição de ativo fixo
description: Este artigo explica como configurar a contabilidade para lançar a aquisição de ativos.
author: ShylaThompson
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: AssetPosting
audience: Application User
ms.reviewer: roschlom
ms.search.scope: Core, Operations
ms.custom: 23021
ms.assetid: d7e86f72-95db-4423-9b04-761e9536a959
ms.search.region: Global
ms.author: saraschi
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 8fea6b1cd79b5536341a7cb50e5592ea38a7392d
ms.sourcegitcommit: 8b4b6a9226d4e5f66498ab2a5b4160e26dd112af
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/01/2019
ms.locfileid: "1840496"
---
# <a name="fixed-asset-acquisition-posting-accounts"></a><span data-ttu-id="4af3d-103">Contas de lançamento de aquisição de ativo fixo</span><span class="sxs-lookup"><span data-stu-id="4af3d-103">Fixed asset acquisition posting accounts</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="4af3d-104">Este artigo explica como configurar a contabilidade para lançar a aquisição de ativos.</span><span class="sxs-lookup"><span data-stu-id="4af3d-104">This article explains how to set up general ledger posting accounts for acquiring assets.</span></span>

<span data-ttu-id="4af3d-105">As contas usadas para lançamento de aquisições de ativo fixo podem variar dependendo do método usado para a aquisição do ativo.</span><span class="sxs-lookup"><span data-stu-id="4af3d-105">Accounts used for posting fixed asset acquisitions may vary depending upon the method used to acquire the asset.</span></span> <span data-ttu-id="4af3d-106">Na página Perfis de lançamentos de ativo fixo, na guia Contas contábeis, selecione Aquisição e Ajuste de aquisição para configurar as contas de ativo fixo para lançamento no razão.</span><span class="sxs-lookup"><span data-stu-id="4af3d-106">On the Fixed asset posting profiles page, on the Ledger accounts tab, select Acquisition and Acquisition adjustment to set up fixed asset accounts to post to the ledger.</span></span> 

<span data-ttu-id="4af3d-107">Em diários e ordens de compra, a conta contábil normalmente é a conta de balanço, onde o valor de aquisição do novo ativo fixo é debitado.</span><span class="sxs-lookup"><span data-stu-id="4af3d-107">In journals and on purchase orders, Ledger account is typically the balance sheet account, where the acquisition value of the new fixed asset is debited.</span></span> <span data-ttu-id="4af3d-108">Essa conta não está exibida no diário e não pode ser substituída em transações.</span><span class="sxs-lookup"><span data-stu-id="4af3d-108">This account is not displayed in the journal and cannot be replaced in transactions.</span></span> 

<span data-ttu-id="4af3d-109">A contrapartida também é uma conta de balanço.</span><span class="sxs-lookup"><span data-stu-id="4af3d-109">Offset account is also a balance sheet account.</span></span> <span data-ttu-id="4af3d-110">No diário geral e no diário de ativos fixos, essa conta geralmente será a conta bancária usada para pagar pela aquisição do ativo.</span><span class="sxs-lookup"><span data-stu-id="4af3d-110">In the general journal and in the fixed assets journal, this account often will be the bank account that is used to pay for the acquisition of the asset.</span></span> <span data-ttu-id="4af3d-111">A contrapartida é uma conta padrão sugerida nos diários.</span><span class="sxs-lookup"><span data-stu-id="4af3d-111">The offset account is a default account, which is suggested in the journals.</span></span> <span data-ttu-id="4af3d-112">Ela pode ser alterada no diário para qualquer outra conta a partir do plano de contas ou para uma conta de fornecedor, se o ativo fixo for comprado de um fornecedor.</span><span class="sxs-lookup"><span data-stu-id="4af3d-112">It can be changed in the journal to any other account from the chart of accounts or to a vendor account, if the fixed asset was purchase from a vendor.</span></span> 

<span data-ttu-id="4af3d-113">Quando Diário de fatura ou Ordens de compra em Contas a pagar são usados para aquisições de ativos fixos, a contrapartida para a transação de ativo fixo é substituída pela conta do fornecedor selecionada para a transação.</span><span class="sxs-lookup"><span data-stu-id="4af3d-113">When Invoice journal or Purchase orders in Accounts payable are used for fixed asset acquisitions, the offset account for the fixed asset transaction is replaced by the vendor account that is selected for the transaction.</span></span>

<span data-ttu-id="4af3d-114">Para aquisições lançadas usando o Diário de estoque para ativos fixos em Contabilidade, o ativo fixo não será trazido de origens externas, mas transferido do estoque da própria empresa.</span><span class="sxs-lookup"><span data-stu-id="4af3d-114">For acquisitions posted using the Inventory to fixed assets journal in General ledger, the fixed asset is not bought from external sources, but transferred from the company's own inventory.</span></span> <span data-ttu-id="4af3d-115">Assim, a contrapartida é uma conta de saída de estoque para o item de estoque em Gerenciamento de estoque.</span><span class="sxs-lookup"><span data-stu-id="4af3d-115">Therefore, the offset account is an inventory issue account for the inventory item in Inventory management.</span></span>

<span data-ttu-id="4af3d-116">Para obter mais informações, consulte [Adquirir ativos por meio de compras](acquire-assets-procurement.md).</span><span class="sxs-lookup"><span data-stu-id="4af3d-116">For more information, see [Acquire assets through procurement](acquire-assets-procurement.md).</span></span>



