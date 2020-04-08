---
title: Criar perfis visuais de ponto de venda (PDV)
description: Este procedimento orienta na criação de um novo perfil visual de ponto de venda (PDV).
author: jashanno
manager: AnnBe
ms.date: 12/05/2015
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-365-retail
ms.technology: ''
audience: Application User
ms.reviewer: josaw
ms.search.scope: Operations, Retail
ms.search.region: Global
ms.search.industry: Retail
ms.author: jashanno
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: b265a94c6d8f9e2534e1509e4f33c6f8a05eded0
ms.sourcegitcommit: 57e1dafa186fec77ddd8ba9425d238e36e0f0998
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/18/2020
ms.locfileid: "3140914"
---
# <a name="create-point-of-sale-pos-visual-profiles"></a><span data-ttu-id="f7f7d-103">Criar perfis visuais de ponto de venda (PDV)</span><span class="sxs-lookup"><span data-stu-id="f7f7d-103">Create point of sale (POS) visual profiles</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="f7f7d-104">Este procedimento orienta na criação de um novo perfil visual de ponto de venda (PDV).</span><span class="sxs-lookup"><span data-stu-id="f7f7d-104">This procedure walks through creating a new point of sale (POS) visual profile.</span></span> <span data-ttu-id="f7f7d-105">Um perfil visual contém informações básicas que determinam a aparência dos terminais de PDV.</span><span class="sxs-lookup"><span data-stu-id="f7f7d-105">A visual profile contains basic information that determines the appearance of POS registers.</span></span> <span data-ttu-id="f7f7d-106">Você pode criar vários perfis visuais e atribuir perfis específicos para executar em registradoras específicas.</span><span class="sxs-lookup"><span data-stu-id="f7f7d-106">You can create several visual profiles and assign specific profiles to run on specific registers.</span></span> <span data-ttu-id="f7f7d-107">Este procedimento usa a empresa de dados de demonstração USRT.</span><span class="sxs-lookup"><span data-stu-id="f7f7d-107">This procedure uses the USRT demo data company.</span></span>

1. <span data-ttu-id="f7f7d-108">Vá para Varejo e Comércio > Configuração de canal > Configuração do PDV > Perfis de PDV > Perfis visuais.</span><span class="sxs-lookup"><span data-stu-id="f7f7d-108">Go to Retail and Commerce > Channel setup > POS setup > POS profiles > Visual profiles.</span></span>
2. <span data-ttu-id="f7f7d-109">Clique em Novo.</span><span class="sxs-lookup"><span data-stu-id="f7f7d-109">Click New.</span></span>
3. <span data-ttu-id="f7f7d-110">No campo número do perfil, digite um valor.</span><span class="sxs-lookup"><span data-stu-id="f7f7d-110">In the Profile number field, type a value.</span></span>
4. <span data-ttu-id="f7f7d-111">No campo Descrição, digite um valor.</span><span class="sxs-lookup"><span data-stu-id="f7f7d-111">In the Description field, type a value.</span></span>
5. <span data-ttu-id="f7f7d-112">No campo Tipo de aplicativo, clique no botão suspenso para abrir a pesquisa.</span><span class="sxs-lookup"><span data-stu-id="f7f7d-112">In the Application type field, click the drop-down button to open the lookup.</span></span>
6. <span data-ttu-id="f7f7d-113">Na lista, clique no link na linha selecionada.</span><span class="sxs-lookup"><span data-stu-id="f7f7d-113">In the list, click the link in the selected row.</span></span>
7. <span data-ttu-id="f7f7d-114">No campo Tema, clique no botão suspenso para abrir a pesquisa.</span><span class="sxs-lookup"><span data-stu-id="f7f7d-114">In the Theme field, click the drop-down button to open the lookup.</span></span>
8. <span data-ttu-id="f7f7d-115">Na lista, clique no link na linha selecionada.</span><span class="sxs-lookup"><span data-stu-id="f7f7d-115">In the list, click the link in the selected row.</span></span>
9. <span data-ttu-id="f7f7d-116">No campo Cor de destaque, clique no botão suspenso para abrir a pesquisa.</span><span class="sxs-lookup"><span data-stu-id="f7f7d-116">In the Accent color field, click the drop-down button to open the lookup.</span></span>
10. <span data-ttu-id="f7f7d-117">Na lista, localize e selecione o registro desejado.</span><span class="sxs-lookup"><span data-stu-id="f7f7d-117">In the list, find and select the desired record.</span></span>
11. <span data-ttu-id="f7f7d-118">Na lista, clique no link na linha selecionada.</span><span class="sxs-lookup"><span data-stu-id="f7f7d-118">In the list, click the link in the selected row.</span></span>
12. <span data-ttu-id="f7f7d-119">Ative/desative a expansão da seção Segundo plano de logon.</span><span class="sxs-lookup"><span data-stu-id="f7f7d-119">Toggle the expansion of the Login background section.</span></span>
13. <span data-ttu-id="f7f7d-120">No campo ID da imagem em paisagem, selecione ou insira uma ID de imagem.</span><span class="sxs-lookup"><span data-stu-id="f7f7d-120">In the Landscape image ID field, select or enter an image ID.</span></span>
14. <span data-ttu-id="f7f7d-121">No campo ID da imagem em retrato, selecione ou insira uma ID de imagem.</span><span class="sxs-lookup"><span data-stu-id="f7f7d-121">In the Portrait image ID field, select or enter an image ID.</span></span>
15. <span data-ttu-id="f7f7d-122">Ative/desative a expansão da seção Segundo plano.</span><span class="sxs-lookup"><span data-stu-id="f7f7d-122">Toggle the expansion of the Background section.</span></span>
16. <span data-ttu-id="f7f7d-123">Solicite o pop-up da ID da imagem.</span><span class="sxs-lookup"><span data-stu-id="f7f7d-123">RequestPopup the Image ID.</span></span>
17. <span data-ttu-id="f7f7d-124">Na lista, clique no link na linha selecionada.</span><span class="sxs-lookup"><span data-stu-id="f7f7d-124">In the list, click the link in the selected row.</span></span>
18. <span data-ttu-id="f7f7d-125">Clique em Salvar.</span><span class="sxs-lookup"><span data-stu-id="f7f7d-125">Click Save.</span></span>

