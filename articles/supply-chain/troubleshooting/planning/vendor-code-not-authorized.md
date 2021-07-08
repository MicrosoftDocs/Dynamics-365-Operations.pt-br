---
title: O código do fornecedor não está autorizado para um produto e data específicos
description: Quando você tenta firmar uma ordem planejada ou adicionar uma linha a uma ordem de compra, você recebe uma mensagem de erro que afirma que o código do fornecedor não está autorizado para um produto e data.
author: ankubik
ms.date: 06/10/2021
ms.topic: troubleshooting
ms.search.form: ReqTransPO_ReqTransPoMarkFirm
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: ankubik
ms.search.validFrom: 2021-06-10
ms.dyn365.ops.version: 10.0.20
ms.openlocfilehash: e6b1189e4fedfdb029f4b4503f0635133df9d87e
ms.sourcegitcommit: 18ca2df785e9656fdd4e8c0734eca2b2624fda10
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/22/2021
ms.locfileid: "6294014"
---
# <a name="vendor-code-isnt-authorized-for-a-specific-product-and-date"></a><span data-ttu-id="b3615-103">O código do fornecedor não está autorizado para um produto e data específicos</span><span class="sxs-lookup"><span data-stu-id="b3615-103">Vendor code isn't authorized for a specific product and date</span></span>

<span data-ttu-id="b3615-104">Código de erro: SYP4881415</span><span class="sxs-lookup"><span data-stu-id="b3615-104">Error code: SYP4881415</span></span>

## <a name="symptoms"></a><span data-ttu-id="b3615-105">Sintomas</span><span class="sxs-lookup"><span data-stu-id="b3615-105">Symptoms</span></span>

<span data-ttu-id="b3615-106">Quando você tenta firmar uma ordem planejada ou adicionar uma linha a uma ordem de compra, você recebe a seguinte mensagem de erro:</span><span class="sxs-lookup"><span data-stu-id="b3615-106">When you try to firm a planned order or add a line to a purchase order, you receive the following error message:</span></span>

> <span data-ttu-id="b3615-107">O código de fornecedor %1 não está autorizado para %2 em %3.</span><span class="sxs-lookup"><span data-stu-id="b3615-107">Vendor code %1 is not authorized for %2 on %3.</span></span>

## <a name="cause"></a><span data-ttu-id="b3615-108">Causa</span><span class="sxs-lookup"><span data-stu-id="b3615-108">Cause</span></span>

<span data-ttu-id="b3615-109">O erro ocorre porque o campo **Método de verificação do fornecedor aprovado** está definido como *Apenas aviso* ou *Não permitido* para o produto especificado, e o fornecedor não está autorizado a fornecer esse produto.</span><span class="sxs-lookup"><span data-stu-id="b3615-109">The error occurs because the **Approved vendor check method** field is set to *Warning only* or *Not allowed* for the specified product, and the vendor isn't currently authorized to supply that product.</span></span>

## <a name="resolution"></a><span data-ttu-id="b3615-110">Resolução</span><span class="sxs-lookup"><span data-stu-id="b3615-110">Resolution</span></span>

<span data-ttu-id="b3615-111">Para corrigir esse problema, desabilite a verificação de fornecedor para o produto relevante ou aprove o fornecedor.</span><span class="sxs-lookup"><span data-stu-id="b3615-111">To fix this issue, either disable the vendor check for the relevant product or approve the vendor.</span></span>

<span data-ttu-id="b3615-112">Para desativar a verificação do fornecedor para um produto, siga estas etapas.</span><span class="sxs-lookup"><span data-stu-id="b3615-112">To disable the vendor check for a product, follow these steps.</span></span>

1. <span data-ttu-id="b3615-113">Vá para **Gerenciamento de informações do produto \> Produtos \> Produtos liberados**.</span><span class="sxs-lookup"><span data-stu-id="b3615-113">Go to **Product information management \> Products \> Released products**.</span></span>
1. <span data-ttu-id="b3615-114">Abra o produto relevante.</span><span class="sxs-lookup"><span data-stu-id="b3615-114">Open the relevant product.</span></span>
1. <span data-ttu-id="b3615-115">No FastTab **Compra**, defina o campo **Método de verificação do fornecedor aprovado** como um valor diferente de *Apenas aviso* ou *Não Permitido*.</span><span class="sxs-lookup"><span data-stu-id="b3615-115">On the **Purchase** FastTab, set the **Approved vendor check method** field to a value other than *Warning only* or *Not allowed*.</span></span>

<span data-ttu-id="b3615-116">Para aprovar um fornecedor para um produto, siga estas etapas.</span><span class="sxs-lookup"><span data-stu-id="b3615-116">To approve a vendor for a product, follow these steps.</span></span>

1. <span data-ttu-id="b3615-117">Vá para **Gerenciamento de informações do produto \> Produtos \> Produtos liberados**.</span><span class="sxs-lookup"><span data-stu-id="b3615-117">Go to **Product information management \> Products \> Released products**.</span></span>
1. <span data-ttu-id="b3615-118">Abra o item relevante.</span><span class="sxs-lookup"><span data-stu-id="b3615-118">Open the relevant item.</span></span>
1. <span data-ttu-id="b3615-119">No Painel de ação, na guia **Compra**, no grupo **Fornecedor aprovado**, clique em **Configuração**.</span><span class="sxs-lookup"><span data-stu-id="b3615-119">On the Action Pane, on the **Purchase** tab, in the **Approved vendor** group, select **Setup**.</span></span>
1. <span data-ttu-id="b3615-120">Na página de lista **Fornecedor aprovado**, adicione uma linha à grade e defina os seguintes valores:</span><span class="sxs-lookup"><span data-stu-id="b3615-120">On the **Approved vendor** list page, add a row to the grid, and set the following values for it:</span></span>

    - <span data-ttu-id="b3615-121">**Fornecedor** – Selecione o fornecedor para aprovar o produto atual.</span><span class="sxs-lookup"><span data-stu-id="b3615-121">**Vendor** – Select the vendor to approve for the current product.</span></span>
    - <span data-ttu-id="b3615-122">**Data de vigência** – Selecione a primeira data para a aprovação do fornecedor.</span><span class="sxs-lookup"><span data-stu-id="b3615-122">**Effective date** – Select the first date that the vendor is approved for.</span></span>
    - <span data-ttu-id="b3615-123">**Data de vencimento** – Selecione a primeira data para a sua aprovação.</span><span class="sxs-lookup"><span data-stu-id="b3615-123">**Expiration date** – Select the last date that the vendor is approved for.</span></span>

<span data-ttu-id="b3615-124">Para obter mais informações, consulte [Aprovar fornecedores para produtos específicos](/dynamics365/supply-chain/procurement/tasks/approve-vendors-specific-products.md).</span><span class="sxs-lookup"><span data-stu-id="b3615-124">For more information, see [Approve vendors for specific products](/dynamics365/supply-chain/procurement/tasks/approve-vendors-specific-products.md).</span></span>
