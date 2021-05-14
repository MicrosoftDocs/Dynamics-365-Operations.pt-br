---
title: Aprovar um modelo da configuração do produto
description: Executar este procedimento exige que pelo menos um modelo de configuração do produto esteja disponível.
author: ShylaThompson
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: DefaultDashboard, EcoResProductVariantMaintainWorkspace, PCProductConfigurationModelListPage, PCProductModelVersion, PCApproveProductModelVersion, HcmWorkerLookUp
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: kamaybac
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 2c945756997b0580ac7ffb19261f9184e53a1c10
ms.sourcegitcommit: fa99a36c3d30d0c0577fd3f63ed6bf2f71599e40
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/20/2021
ms.locfileid: "5920498"
---
# <a name="approve-a-product-configuration-model"></a><span data-ttu-id="a16a9-103">Aprovar um modelo da configuração do produto</span><span class="sxs-lookup"><span data-stu-id="a16a9-103">Approve a product configuration model</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="a16a9-104">Executar este procedimento exige que pelo menos um modelo de configuração do produto esteja disponível.</span><span class="sxs-lookup"><span data-stu-id="a16a9-104">Running this procedure requires that at least one product configuration model is available.</span></span> <span data-ttu-id="a16a9-105">Este procedimento usa o modelo de alto-falante avançado na empresa de dados de demonstração USMF.</span><span class="sxs-lookup"><span data-stu-id="a16a9-105">This procedure uses the High end speaker model in the demo data company USMF.</span></span> <span data-ttu-id="a16a9-106">Observe que esse modelo já foi aprovado, mas o procedimento o conduz por todo o processo.</span><span class="sxs-lookup"><span data-stu-id="a16a9-106">Note that this model has already been approved, but the procedure walks you through the entire process.</span></span>

1. <span data-ttu-id="a16a9-107">Vá para **Gerenciamento de informações do produto \> Produtos \> Modelos de configuração do produto**.</span><span class="sxs-lookup"><span data-stu-id="a16a9-107">Go to **Product information management \> Products \> Product configuration models**.</span></span>
1. <span data-ttu-id="a16a9-108">Na lista, localize e selecione o registro desejado.</span><span class="sxs-lookup"><span data-stu-id="a16a9-108">In the list, find and select the desired record.</span></span>
    * <span data-ttu-id="a16a9-109">Selecione o modelo alto-falante avançado para este procedimento.</span><span class="sxs-lookup"><span data-stu-id="a16a9-109">Select the High end speaker model for this procedure.</span></span>  
1. <span data-ttu-id="a16a9-110">Selecione **Versões**.</span><span class="sxs-lookup"><span data-stu-id="a16a9-110">Select **Versions**.</span></span>
1. <span data-ttu-id="a16a9-111">Selecione **Novo**.</span><span class="sxs-lookup"><span data-stu-id="a16a9-111">Select **New**.</span></span>
1. <span data-ttu-id="a16a9-112">No campo **Número do produto**, insira ou selecione um valor.</span><span class="sxs-lookup"><span data-stu-id="a16a9-112">In the **Product number** field, enter or select a value.</span></span>
    * <span data-ttu-id="a16a9-113">A referência a um produto representa uma versão do modelo de configuração do produto.</span><span class="sxs-lookup"><span data-stu-id="a16a9-113">The reference to a product represents a version of a product configuration model.</span></span> <span data-ttu-id="a16a9-114">Somente os produtos mestre que têm a tecnologia de configuração com base restrição aparecerão na lista.</span><span class="sxs-lookup"><span data-stu-id="a16a9-114">Only product masters which have the constraint-based configuration technology will appear in this list.</span></span>  
1. <span data-ttu-id="a16a9-115">No campo **Data inicial**, insira uma data.</span><span class="sxs-lookup"><span data-stu-id="a16a9-115">In the **From date** field, enter a date.</span></span>
    * <span data-ttu-id="a16a9-116">Selecione quando a versão do modelo de produto estará disponível.</span><span class="sxs-lookup"><span data-stu-id="a16a9-116">Select when the product model version will be available.</span></span>  
1. <span data-ttu-id="a16a9-117">No campo **Data final**, insira uma data.</span><span class="sxs-lookup"><span data-stu-id="a16a9-117">In the **To date** field, enter a date.</span></span>
    * <span data-ttu-id="a16a9-118">Selecione uma data final na qual essa versão do modelo de produto irá expirar ou selecione Nunca.</span><span class="sxs-lookup"><span data-stu-id="a16a9-118">Select an end date when this product model version will expire, or select Never.</span></span>  
1. <span data-ttu-id="a16a9-119">Selecione **Aprovar** para abrir a caixa de diálogo suspensa.</span><span class="sxs-lookup"><span data-stu-id="a16a9-119">Select **Approve** to open the drop dialog.</span></span>
1. <span data-ttu-id="a16a9-120">No campo **Aprovado por** insira ou selecione um valor.</span><span class="sxs-lookup"><span data-stu-id="a16a9-120">In the **Approved by** field, enter or select a value.</span></span>
    * <span data-ttu-id="a16a9-121">Selecione a pessoa é responsável pela aprovação de modelos de produto para uso nas operações.</span><span class="sxs-lookup"><span data-stu-id="a16a9-121">Select the person who is responsible for approving product models for use in operations.</span></span>  
1. <span data-ttu-id="a16a9-122">Selecione **OK**.</span><span class="sxs-lookup"><span data-stu-id="a16a9-122">Select **OK**.</span></span>
1. <span data-ttu-id="a16a9-123">No campo **Método de precificação**, selecione uma opção.</span><span class="sxs-lookup"><span data-stu-id="a16a9-123">In the **Pricing method** field, select an option.</span></span>
    * <span data-ttu-id="a16a9-124">Ative a versão do modelo de produto.</span><span class="sxs-lookup"><span data-stu-id="a16a9-124">Activate the product model version.</span></span> <span data-ttu-id="a16a9-125">Só é possível ter um produto ativo para um modelo de produto por vez.</span><span class="sxs-lookup"><span data-stu-id="a16a9-125">It is only possible to have one product active for one product model at a time.</span></span>  
1. <span data-ttu-id="a16a9-126">Feche a página.</span><span class="sxs-lookup"><span data-stu-id="a16a9-126">Close the page.</span></span>



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]