---
title: Manuseio aprimorado de itens de lote rastreados
description: Este tópico descreve os aprimoramentos feitos no manuseio de lotes para itens de lote rastreados durante o processo de lançamento de demonstrativo.
author: josaw1
manager: AnnBe
ms.date: 11/04/2019
ms.topic: index-page
ms.prod: ''
ms.service: dynamics-365-retail
ms.technology: ''
audience: Application User
ms.reviewer: josaw
ms.custom: ''
ms.assetid: ''
ms.search.region: global
ms.search.industry: Retail
ms.author: josaw
ms.search.validFrom: 2019-05-28
ms.dyn365.ops.version: 10
ms.openlocfilehash: 00e1fcb36d685798f3ad7d667805c97bddcceb36
ms.sourcegitcommit: eaf330dbee1db96c20d5ac479f007747bea079eb
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/15/2021
ms.locfileid: "5211144"
---
# <a name="improved-handling-of-batch-tracked-items"></a><span data-ttu-id="dbb74-103">Manuseio aprimorado de itens de lote rastreados</span><span class="sxs-lookup"><span data-stu-id="dbb74-103">Improved handling of batch-tracked items</span></span>


[!include [banner](includes/banner.md)]


<span data-ttu-id="dbb74-104">No ponto de venda (PDV), os números de lote não podem ser capturados para itens de lote rastreados no momento da venda.</span><span class="sxs-lookup"><span data-stu-id="dbb74-104">In Point of Sale (POS), batch numbers can't be captured for batch-tracked items at the time of sale.</span></span> <span data-ttu-id="dbb74-105">No entanto, para configurações específicas, quando as vendas lançadas na matriz por meio de ordens de cliente ou lançamento de demonstrativo, o sistema do Microsoft Dynamics espera que existam números de lote válidos para itens de lote rastreados e que eles sejam usados durante o processo de faturamento.</span><span class="sxs-lookup"><span data-stu-id="dbb74-105">However, for specific configurations, when sales are posted in the headquarters through customer orders or statement posting, the Microsoft Dynamics system expects that valid batch numbers for batch-tracked items exist, and that they will be used during the invoicing process.</span></span>

<span data-ttu-id="dbb74-106">Se os números de lote válidos estiverem disponíveis para os produtos, eles serão usados pelo processo de faturamento da ordem do cliente e pelo processo de faturamento da ordem de venda do lançamento de demonstrativo.</span><span class="sxs-lookup"><span data-stu-id="dbb74-106">If valid batch numbers are available for products, the customer order invoicing process and the sales order invoicing process from statement posting use them.</span></span> <span data-ttu-id="dbb74-107">Caso contrário, processo de faturamento da ordem do cliente não poderá fazer o lançamento e o usuário do PDV receberá uma mensagem de erro.</span><span class="sxs-lookup"><span data-stu-id="dbb74-107">Otherwise, the customer order invoicing process can't post, and the POS user receives an error message.</span></span> <span data-ttu-id="dbb74-108">O lançamento do demonstrativo entrará então em um estado de erro.</span><span class="sxs-lookup"><span data-stu-id="dbb74-108">Statement posting then goes into an error state.</span></span> <span data-ttu-id="dbb74-109">Esse estado de erro ocorrerá mesmo quando o estoque negativo tiver sido ativado para os produtos.</span><span class="sxs-lookup"><span data-stu-id="dbb74-109">This error state occurs even when negative inventory has been turned on for the products.</span></span>

<span data-ttu-id="dbb74-110">Os aprimoramentos feitos no Retail versão 10.0.4 e posterior ajudam a garantir que, quando o estoque negativo for ativado para itens de lote rastreados, o faturamento da ordem do cliente e o faturamento da ordem venda por meio do lançamento de demonstrativo não serão bloqueados para esses itens se o estoque for 0 (zero) ou se um número de lote não estiver disponível.</span><span class="sxs-lookup"><span data-stu-id="dbb74-110">Improvements that have been made in Retail version 10.0.4 and later help guarantee that, when negative inventory is turned on for batch-tracked items, customer order invoicing and sales order invoicing through statement posting aren't blocked for those items if the inventory is 0 (zero) or a batch number isn't available.</span></span> <span data-ttu-id="dbb74-111">A nova funcionalidade usa uma ID de lote padrão para as linhas de venda quando os números de lotes não estão disponíveis.</span><span class="sxs-lookup"><span data-stu-id="dbb74-111">The new functionality uses a default batch ID for the sales lines when batch numbers aren't available.</span></span>

<span data-ttu-id="dbb74-112">Para definir a ID padrão do lote usada para ordens de cliente, na página **Parâmetros do Commerce**, na guia **Ordens do cliente**, na FastTab **Ordem**, defina o campo **ID de lote padrão**.</span><span class="sxs-lookup"><span data-stu-id="dbb74-112">To define the default batch ID that is used for customer orders, on the **Commerce parameters** page, on the **Customer orders** tab, on the **Order** FastTab, set the **Default batch id** field.</span></span>

<span data-ttu-id="dbb74-113">Para definir a ID de lote padrão usada para o faturamento da ordem de venda por meio do lançamento de demonstrativo, na página **Parâmetros do Commerce**, na guia **Lançamento**, na FastTab **Atualização de estoque**, defina o campo **ID de lote padrão**.</span><span class="sxs-lookup"><span data-stu-id="dbb74-113">To define the default batch ID that is used for sales order invoicing through statement posting, on the **Commerce parameters** page, on the **Posting** tab, on the **Inventory update** FastTab, set the **Default batch id** field.</span></span>

> [!NOTE]
> <span data-ttu-id="dbb74-114">Esta funcionalidade ficará disponível somente quando o armazenamento avançado for ativado para os depósitos e o itens de específicos da loja.</span><span class="sxs-lookup"><span data-stu-id="dbb74-114">This functionality is available only when advanced warehousing is turned on for the specific store warehouse and items.</span></span> <span data-ttu-id="dbb74-115">Em uma versão posterior, a funcionalidade também terá suporte para cenários em que o gerenciamento de armazenamento não é usado.</span><span class="sxs-lookup"><span data-stu-id="dbb74-115">In a later release, the functionality will also be supported for scenarios where advanced warehouse management isn't used.</span></span>

> [!NOTE]
> <span data-ttu-id="dbb74-116">O suporte ao manuseio aprimorado de itens de lote rastreados durante o lançamento de demonstrativo a cenários de gerenciamento de depósito não avançado foi apresentado no Retail versão 10.0.5.</span><span class="sxs-lookup"><span data-stu-id="dbb74-116">Support for improved handling of batch-tracked items during statement posting for non-advanced warehouse management scenarios was introduced in Retail version 10.0.5.</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]