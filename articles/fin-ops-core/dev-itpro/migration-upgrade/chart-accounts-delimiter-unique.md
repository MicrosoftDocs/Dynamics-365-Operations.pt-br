---
title: O delimitador do plano de contas deve ser exclusivo
description: Este tópico explica que não é possível ter o mesmo delimitador para o plano de contas e valores de dimensão. Você deve alterar os valores do delimitador após a atualização.
author: panolte
ms.date: 03/30/2018
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: sericks
ms.custom: 265364
ms.assetid: c61391e4-c4bf-4f09-bd18-8107a1bf055e
ms.search.region: Global
ms.author: saraschi
ms.search.validFrom: 2016-11-30
ms.dyn365.ops.version: 8
ms.openlocfilehash: f4f89772dedb5433c3da3f0f7bf02106641f59a8
ms.sourcegitcommit: 074b6e212d19dd5d84881d1cdd096611a18c207f
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/31/2021
ms.locfileid: "5748098"
---
# <a name="make-the-chart-of-accounts-delimiter-unique"></a><span data-ttu-id="05723-104">O delimitador do plano de contas deve ser exclusivo</span><span class="sxs-lookup"><span data-stu-id="05723-104">Make the chart of accounts delimiter unique</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="05723-105">No Microsoft Dynamics AX 2012, era possível usar o mesmo delimitador para o plano de contas e os valores de dimensão.</span><span class="sxs-lookup"><span data-stu-id="05723-105">In Microsoft Dynamics AX 2012, you could use the same delimiter for your chart of accounts and dimension values.</span></span> <span data-ttu-id="05723-106">Nas versões atuais do Finance and Operations, você não pode ter o mesmo delimitador para o plano de contas e para os valores de dimensão.</span><span class="sxs-lookup"><span data-stu-id="05723-106">In current versions of Finance and Operations, you cannot have the same delimiter for the chart of accounts and dimension values.</span></span> <span data-ttu-id="05723-107">Se houver um delimitador duplicado, você poderá alterá-lo após a atualização.</span><span class="sxs-lookup"><span data-stu-id="05723-107">If there is a duplicate delimiter, you can change it after upgrade.</span></span> 

<span data-ttu-id="05723-108">Este recurso está disponível nas seguintes versões:</span><span class="sxs-lookup"><span data-stu-id="05723-108">This feature is available in the following versions:</span></span>
- <span data-ttu-id="05723-109">Finance and Operations versão 8.0</span><span class="sxs-lookup"><span data-stu-id="05723-109">Finance and Operations version 8.0</span></span>
- <span data-ttu-id="05723-110">Finance and Operations versão 7.1, KB 4094701 – não é possível inserir as dimensões financeiras quando os valores de dimensão contêm o delimitador de plano de contas</span><span class="sxs-lookup"><span data-stu-id="05723-110">Finance and Operations version 7.1, KB 4094701 Cannot enter the financial dimensions when the dimension values contain the chart of accounts delimiter</span></span>
- <span data-ttu-id="05723-111">Finance and Operations versão 7.2, KB 4092967 – não é possível escolher subprojeto como dimensão quando o formato do subprojeto contém o delimitador de dimensão</span><span class="sxs-lookup"><span data-stu-id="05723-111">Finance and Operations version 7.2, KB 4092967 Cannot choose sub-project as dimension when sub-project format contains the dimension delimiter</span></span>

## <a name="update-delimiter"></a><span data-ttu-id="05723-112">Atualizar delimitador</span><span class="sxs-lookup"><span data-stu-id="05723-112">Update delimiter</span></span>
<span data-ttu-id="05723-113">Se houver um conflito com o plano de contas, o delimitador do plano de contas e o formato da ID de projeto/subprojeto poderá ser alterado.</span><span class="sxs-lookup"><span data-stu-id="05723-113">If there is a conflict with the chart of accounts, the chart of accounts delimiter and the project/subproject ID format can be changed.</span></span> <span data-ttu-id="05723-114">Nenhum outro delimitador de dimensão pode ser alterado.</span><span class="sxs-lookup"><span data-stu-id="05723-114">No other dimension delimiters can be changed.</span></span> 
- <span data-ttu-id="05723-115">Você pode alterar o delimitador do plano de contas depois da atualização em **Parâmetros de contabilidade** > **Plano de contas e dimensões** > **Alterar delimitador**.</span><span class="sxs-lookup"><span data-stu-id="05723-115">You can change the chart of accounts delimiter after upgrade in **General ledger parameters** > **Chart of accounts and dimensions** > **Change delimiter**.</span></span> 
- <span data-ttu-id="05723-116">Se o único conflito for com o formato da ID do projeto/subprojeto, você poderá alterar esse valor em **Parâmetros de gerenciamento e contabilidade de projetos** > **Geral** > **Modificar o formato do subprojeto**.</span><span class="sxs-lookup"><span data-stu-id="05723-116">If the only conflict is with the project/subproject ID format, you can change that value in **Project management and accounting parameters** > **General** > **Modify subproject format**.</span></span> 

## <a name="how-to-determine-if-your-environment-requires-updated-delimiters"></a><span data-ttu-id="05723-117">Como determinar se o ambiente requer delimitadores atualizados</span><span class="sxs-lookup"><span data-stu-id="05723-117">How to determine if your environment requires updated delimiters</span></span> 
<span data-ttu-id="05723-118">Se os delimitadores em seu ambiente atualizado estiverem em conflito, é possível que haja instabilidade ao inserir valores em um controle de entrada segmentada ou em um controle entrada de dimensão.</span><span class="sxs-lookup"><span data-stu-id="05723-118">If delimiters in your upgraded environment are conflicting, you may experience instability when entering values in a segmented entry control or dimension entry control.</span></span> <span data-ttu-id="05723-119">Isso significa que você sempre precisará usar pesquisas ou um menu suspenso ao inserir combinações de conta e dimensão.</span><span class="sxs-lookup"><span data-stu-id="05723-119">This means that you will need to always use lookups or a flyout menu when entering account and dimension combinations.</span></span>


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]