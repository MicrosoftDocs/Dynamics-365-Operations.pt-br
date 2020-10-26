---
title: Aprovar um modelo da configuração do produto
description: Executar este procedimento exige que pelo menos um modelo de configuração do produto esteja disponível.
author: ShylaThompson
manager: tfehr
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: DefaultDashboard, EcoResProductVariantMaintainWorkspace, PCProductConfigurationModelListPage, PCProductModelVersion, PCApproveProductModelVersion, HcmWorkerLookUp
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: kamaybac
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 440ffbdf1db22ac25971922d80a5569a340ba81c
ms.sourcegitcommit: 708ca25687a4e48271cdcd6d2d22d99fb94cf140
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/10/2020
ms.locfileid: "3986374"
---
# <a name="approve-a-product-configuration-model"></a><span data-ttu-id="a2f98-103">Aprovar um modelo da configuração do produto</span><span class="sxs-lookup"><span data-stu-id="a2f98-103">Approve a product configuration model</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="a2f98-104">Executar este procedimento exige que pelo menos um modelo de configuração do produto esteja disponível.</span><span class="sxs-lookup"><span data-stu-id="a2f98-104">Running this procedure requires that at least one product configuration model is available.</span></span> <span data-ttu-id="a2f98-105">Este procedimento usa o modelo de alto-falante avançado na empresa de dados de demonstração USMF.</span><span class="sxs-lookup"><span data-stu-id="a2f98-105">This procedure uses the High end speaker model in the demo data company USMF.</span></span> <span data-ttu-id="a2f98-106">Observe que esse modelo já foi aprovado, mas o procedimento o conduz por todo o processo.</span><span class="sxs-lookup"><span data-stu-id="a2f98-106">Note that this model has already been approved, but the procedure walks you through the entire process.</span></span>

1. <span data-ttu-id="a2f98-107">Clique em Definição de modelo de variante de produto.</span><span class="sxs-lookup"><span data-stu-id="a2f98-107">Click Product variant model definition.</span></span>
2. <span data-ttu-id="a2f98-108">Clique em Modelos de configuração do produto.</span><span class="sxs-lookup"><span data-stu-id="a2f98-108">Click Product configuration models.</span></span>
3. <span data-ttu-id="a2f98-109">Na lista, localize e selecione o PDV desejado.</span><span class="sxs-lookup"><span data-stu-id="a2f98-109">In the list, find and select the desired record.</span></span>
    * <span data-ttu-id="a2f98-110">Selecione o modelo alto-falante avançado para este procedimento.</span><span class="sxs-lookup"><span data-stu-id="a2f98-110">Select the High end speaker model for this procedure.</span></span>  
4. <span data-ttu-id="a2f98-111">Clique em Versões.</span><span class="sxs-lookup"><span data-stu-id="a2f98-111">Click Versions.</span></span>
5. <span data-ttu-id="a2f98-112">Clique em Novo.</span><span class="sxs-lookup"><span data-stu-id="a2f98-112">Click New.</span></span>
6. <span data-ttu-id="a2f98-113">No campo Número do produto, insira ou selecione um valor.</span><span class="sxs-lookup"><span data-stu-id="a2f98-113">In the Product number field, enter or select a value.</span></span>
    * <span data-ttu-id="a2f98-114">A referência a um produto representa uma versão do modelo de configuração do produto.</span><span class="sxs-lookup"><span data-stu-id="a2f98-114">The reference to a product represents a version of a product configuration model.</span></span> <span data-ttu-id="a2f98-115">Somente os produtos mestre que têm a tecnologia de configuração com base restrição aparecerão na lista.</span><span class="sxs-lookup"><span data-stu-id="a2f98-115">Only product masters which have the constraint-based configuration technology will appear in this list.</span></span>  
7. <span data-ttu-id="a2f98-116">No campo De data, insira uma data.</span><span class="sxs-lookup"><span data-stu-id="a2f98-116">In the From date field, enter a date.</span></span>
    * <span data-ttu-id="a2f98-117">Selecione quando a versão do modelo de produto estará disponível.</span><span class="sxs-lookup"><span data-stu-id="a2f98-117">Select when the product model version will be available.</span></span>  
8. <span data-ttu-id="a2f98-118">No campo Para data, insira uma data.</span><span class="sxs-lookup"><span data-stu-id="a2f98-118">In the To date field, enter a date.</span></span>
    * <span data-ttu-id="a2f98-119">Selecione uma data final na qual essa versão do modelo de produto irá expirar ou selecione Nunca.</span><span class="sxs-lookup"><span data-stu-id="a2f98-119">Select an end date when this product model version will expire, or select Never.</span></span>  
9. <span data-ttu-id="a2f98-120">Clique em Aprovar para abrir a caixa de diálogo suspensa.</span><span class="sxs-lookup"><span data-stu-id="a2f98-120">Click Approve to open the drop dialog.</span></span>
10. <span data-ttu-id="a2f98-121">No campo Aprovado por, insira ou selecione um valor.</span><span class="sxs-lookup"><span data-stu-id="a2f98-121">In the Approved by field, enter or select a value.</span></span>
    * <span data-ttu-id="a2f98-122">Selecione a pessoa é responsável pela aprovação de modelos de produto para uso nas operações.</span><span class="sxs-lookup"><span data-stu-id="a2f98-122">Select the person who is responsible for approving product models for use in operations.</span></span>  
11. <span data-ttu-id="a2f98-123">Clique em OK.</span><span class="sxs-lookup"><span data-stu-id="a2f98-123">Click OK.</span></span>
12. <span data-ttu-id="a2f98-124">No campo Método de precificação, selecione uma opção.</span><span class="sxs-lookup"><span data-stu-id="a2f98-124">In the Pricing method field, select an option.</span></span>
    * <span data-ttu-id="a2f98-125">Ative a versão do modelo de produto.</span><span class="sxs-lookup"><span data-stu-id="a2f98-125">Activate the product model version.</span></span> <span data-ttu-id="a2f98-126">Só é possível ter um produto ativo para um modelo de produto por vez.</span><span class="sxs-lookup"><span data-stu-id="a2f98-126">It is only possible to have one product active for one product model at a time.</span></span>  
13. <span data-ttu-id="a2f98-127">Feche a página.</span><span class="sxs-lookup"><span data-stu-id="a2f98-127">Close the page.</span></span>

