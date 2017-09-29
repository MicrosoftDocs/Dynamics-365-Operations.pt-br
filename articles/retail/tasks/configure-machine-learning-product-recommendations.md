--- 
title: " Configurar recomendações de produto fornecidas pelo aprendizado de máquina"
description: "Este processo atualiza os dados no Repositório de Entidades que é usado pelo sistema de aprendizado de máquina que fornece recomendações de produto e habilita as recomendações de produto nos PDV clientes."
author: ashishmsft
manager: AnnBe
ms.date: 10/27/2016
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: josaw
ms.search.scope: Operations
ms.search.region: Global
ms.search.industry: Retail
ms.author: asharchw
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 663da58ef01b705c0c984fbfd3fce8bc31be04c6
ms.openlocfilehash: e32c7cf1283487cb7a52f7d8e261b6b587b76364
ms.contentlocale: pt-br
ms.lasthandoff: 08/29/2017

---
# <a name="configure-machine-learning-powered-product-recommendations"></a><span data-ttu-id="939e5-103"> Configurar recomendações de produto fornecidas pelo aprendizado de máquina</span><span class="sxs-lookup"><span data-stu-id="939e5-103">Configure machine learning-powered product recommendations</span></span>

[!include[task guide banner](../includes/task-guide-banner.md)]

<span data-ttu-id="939e5-104">Este processo atualiza os dados no Repositório de Entidades que é usado pelo sistema de aprendizado de máquina que fornece recomendações de produto e habilita as recomendações de produto nos PDV clientes.</span><span class="sxs-lookup"><span data-stu-id="939e5-104">This procedure refreshes the data in the Entity store that is used by the machine learning system that powers product recommendations, and then enables product recommendations on POS clients.</span></span> <span data-ttu-id="939e5-105">Este procedimento usa a empresa USRT nos dados de demonstração.</span><span class="sxs-lookup"><span data-stu-id="939e5-105">This procedure uses the USRT company in demo data.</span></span>

1. <span data-ttu-id="939e5-106">Vá para Administração do sistema > Configuração > Repositório de Entidades.</span><span class="sxs-lookup"><span data-stu-id="939e5-106">Go to System administration > Setup > Entity Store.</span></span>
2. <span data-ttu-id="939e5-107">Na lista, localize e selecione o registro 'RetailSales'.</span><span class="sxs-lookup"><span data-stu-id="939e5-107">In the list, find and select the record 'RetailSales'.</span></span>
3. <span data-ttu-id="939e5-108">Clique em Atualizar.</span><span class="sxs-lookup"><span data-stu-id="939e5-108">Click Refresh.</span></span>
4. <span data-ttu-id="939e5-109">Clique em OK.</span><span class="sxs-lookup"><span data-stu-id="939e5-109">Click OK.</span></span>
5. <span data-ttu-id="939e5-110">Feche a página.</span><span class="sxs-lookup"><span data-stu-id="939e5-110">Close the page.</span></span>
6. <span data-ttu-id="939e5-111">Vá para Varejo e comércio > Configuração da sede > Parâmetros > Parâmetros de varejo.</span><span class="sxs-lookup"><span data-stu-id="939e5-111">Go to Retail and commerce > Headquarters setup > Parameters > Retail parameters.</span></span>
7. <span data-ttu-id="939e5-112">Clique na guia Aprendizado de Máquina.</span><span class="sxs-lookup"><span data-stu-id="939e5-112">Click the Machine learning tab.</span></span>
8. <span data-ttu-id="939e5-113">Selecione 'Sim' no campo Habilitar recomendações de produtos.</span><span class="sxs-lookup"><span data-stu-id="939e5-113">Select 'Yes' in the Enable product recommendations field.</span></span>
    * <span data-ttu-id="939e5-114">Se você receber a mensagem "Não foi possível recuperar os modelos de recomendações", é porque você atualizou o Repositório de Entidades muito recentemente e o sistema pode não ter finalizado a assimilação dos novos dados.</span><span class="sxs-lookup"><span data-stu-id="939e5-114">If you receive the message "The recommendation models couldn't be retrieved", it’s because you refreshed the Entity Store very recently and the system may not have finished assimilating the new data.</span></span> <span data-ttu-id="939e5-115">Aguarde duas a três horas e tente novamente.</span><span class="sxs-lookup"><span data-stu-id="939e5-115">Wait 2-3 hours and try again.</span></span>  
9. <span data-ttu-id="939e5-116">Clique em Salvar.</span><span class="sxs-lookup"><span data-stu-id="939e5-116">Click Save.</span></span>
10. <span data-ttu-id="939e5-117">Feche a página.</span><span class="sxs-lookup"><span data-stu-id="939e5-117">Close the page.</span></span>


