---
title: Configurar grupos de ativos fixos
description: Este tópico explica como criar um novo grupo de ativos fixos.
author: saraschi2
manager: AnnBe
ms.date: 08/02/2019
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: AssetGroup, AssetGroupBookSetup
audience: Application User
ms.reviewer: roschlom
ms.search.region: Global
ms.author: saraschi
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 4eead36e1274194b151b230767a4d6385173b12f
ms.sourcegitcommit: 38d40c331c8894acb7b119c5073e3088b54776c1
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/15/2021
ms.locfileid: "4994831"
---
# <a name="set-up-fixed-asset-groups"></a><span data-ttu-id="6cd32-103">Configurar grupos de ativos fixos</span><span class="sxs-lookup"><span data-stu-id="6cd32-103">Set up fixed asset groups</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="6cd32-104">Este tópico explica como criar um novo grupo de ativos fixos.</span><span class="sxs-lookup"><span data-stu-id="6cd32-104">This topic explains how to create a new fixed asset group.</span></span> <span data-ttu-id="6cd32-105">Ela usa a função de contador e os dados de demonstração da entidade legal de USMF.</span><span class="sxs-lookup"><span data-stu-id="6cd32-105">It uses the Accountant role and demo data for the USMF legal entity.</span></span>

1. <span data-ttu-id="6cd32-106">No Painel de navegação, vá para **Módulos > Ativos fixos > Configuração > Grupos de ativos fixos**.</span><span class="sxs-lookup"><span data-stu-id="6cd32-106">In the navigation pane, go to **Modules > Fixed assets > Setup > Fixed asset groups**.</span></span>
2. <span data-ttu-id="6cd32-107">Selecione **Novo**.</span><span class="sxs-lookup"><span data-stu-id="6cd32-107">Select **New**.</span></span>
3. <span data-ttu-id="6cd32-108">No campo **Grupo de ativo fixo**, digite um valor.</span><span class="sxs-lookup"><span data-stu-id="6cd32-108">In the **Fixed asset group** field, type a value.</span></span>
4. <span data-ttu-id="6cd32-109">No campo **Nome**, digite um valor.</span><span class="sxs-lookup"><span data-stu-id="6cd32-109">In the **Name** field, type a value.</span></span> <span data-ttu-id="6cd32-110">Os ativos fixos e o código da sequência numérica de Autonumber no grupo de **Ativos fixos** substituirão as configurações nos parâmetros de ativos fixos.</span><span class="sxs-lookup"><span data-stu-id="6cd32-110">Autonumber fixed assets and Number sequence code on the **Fixed asset** group will override the settings on the Fixed assets parameters.</span></span> <span data-ttu-id="6cd32-111">Você pode alterá-lo aqui se os ativos no grupo de ativos fixos forem diferentes da numeração de outros grupos.</span><span class="sxs-lookup"><span data-stu-id="6cd32-111">You can change it here if the assets in this fixed asset group will have different numbering from other groups.</span></span>  
5. <span data-ttu-id="6cd32-112">Selecione **Registros**.</span><span class="sxs-lookup"><span data-stu-id="6cd32-112">Select **Books**.</span></span>
6. <span data-ttu-id="6cd32-113">No campo **Registro**, insira ou selecione um valor.</span><span class="sxs-lookup"><span data-stu-id="6cd32-113">In the **Book** field, enter or select a value.</span></span> <span data-ttu-id="6cd32-114">Como o campo **Calcular depreciação** é definido como **Sim**, o registro do ativo será incluído nas propostas de depreciação.</span><span class="sxs-lookup"><span data-stu-id="6cd32-114">The **Calculate depreciation** field is set to **Yes**, so the asset book will be included in depreciation proposals.</span></span> <span data-ttu-id="6cd32-115">Se **Calcular a depreciação** for definido como **Não**, o ativo não será depreciado automaticamente.</span><span class="sxs-lookup"><span data-stu-id="6cd32-115">If **Calculate depreciation** is set to **No**, the asset will not be automatically depreciated.</span></span>  
7. <span data-ttu-id="6cd32-116">Defina a vida útil do ativo fixo, em anos.</span><span class="sxs-lookup"><span data-stu-id="6cd32-116">Set the Service life of the asset, in years.</span></span> <span data-ttu-id="6cd32-117">Observe que o valor do campo **Períodos de depreciação** será calculado depois de definir a vida útil.</span><span class="sxs-lookup"><span data-stu-id="6cd32-117">Note that the **Depreciation periods** field value is calculated after setting the Service life.</span></span>  
8. <span data-ttu-id="6cd32-118">No campo **Convenção de depreciação**, selecione uma opção.</span><span class="sxs-lookup"><span data-stu-id="6cd32-118">In the **Depreciation convention** field, select an option.</span></span>
9. <span data-ttu-id="6cd32-119">Feche a página.</span><span class="sxs-lookup"><span data-stu-id="6cd32-119">Close the page.</span></span>

