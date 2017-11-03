---
title: Inicialize dados semente em um novo ambiente de varejo
description: "Este artigo descreve os dados que são criados como parte do processo de inicialização para o Microsoft Dynamics 365 for Retail."
author: josaw1
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-365-retail
ms.technology: 
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations, Retail
ms.custom: 49621
ms.assetid: 4dc762eb-190e-4485-8f55-b0cafc81bc37
ms.search.region: global
ms.search.industry: Retail
ms.author: josaw
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0, Retail July 2017 update
ms.translationtype: HT
ms.sourcegitcommit: 2771a31b5a4d418a27de0ebe1945d1fed2d8d6d6
ms.openlocfilehash: 7388324fe8a9abc8fc3d723b7c8df2c73d76a2ae
ms.contentlocale: pt-br
ms.lasthandoff: 11/03/2017

---

# <a name="initialize-seed-data-in-a-new-retail-environment"></a><span data-ttu-id="ba2cc-103">Inicialize dados semente em um novo ambiente de varejo</span><span class="sxs-lookup"><span data-stu-id="ba2cc-103">Initialize seed data in a new Retail environment</span></span>

[!include[banner](includes/banner.md)]


<span data-ttu-id="ba2cc-104">Este artigo descreve os dados que são criados como parte do processo de inicialização para o Microsoft Dynamics 365 for Retail.</span><span class="sxs-lookup"><span data-stu-id="ba2cc-104">This article describes the data that's created as part of the initialization process for Microsoft Dynamics 365 for Retail.</span></span>

<span data-ttu-id="ba2cc-105">Depois que a solução Retail for implantada no Microsoft Dynamics Lifecycle Services (LCS), você deverá inicializar a configuração de varejo para criar os dados básicos de configuração.</span><span class="sxs-lookup"><span data-stu-id="ba2cc-105">After the Retail solution has been deployed through Microsoft Dynamics Lifecycle Services (LCS), you must initialize the retail configuration to create the basic configuration data.</span></span> <span data-ttu-id="ba2cc-106">**Importante:** antes que você inicialize a configuração de varejo, verifique se especificou um idioma e um endereço postal para cada entidade legal em que configurará as lojas de varejo.</span><span class="sxs-lookup"><span data-stu-id="ba2cc-106">**Important:** Before you initialize the retail configuration, make sure that you've specified a language and a postal address for each legal entity where you will set up retail stores.</span></span> <span data-ttu-id="ba2cc-107">Essa etapa deve ser concluída para cada entidade legal usada no varejo.</span><span class="sxs-lookup"><span data-stu-id="ba2cc-107">This step must be completed for each legal entity that you use for retail.</span></span> <span data-ttu-id="ba2cc-108">Para inicializar a configuração de varejo, execute estas etapas:</span><span class="sxs-lookup"><span data-stu-id="ba2cc-108">To initialize the retail configuration, follow these steps.</span></span>

1.  <span data-ttu-id="ba2cc-109">Inicie o cliente do Dynamics 365 for Retail.</span><span class="sxs-lookup"><span data-stu-id="ba2cc-109">Start the Dynamics 365 for Retail client.</span></span>
2.  <span data-ttu-id="ba2cc-110">Clique em **Varejo** &gt; **Configuração da sede** &gt; **Parâmetros** &gt; **Parâmetros de varejo**.</span><span class="sxs-lookup"><span data-stu-id="ba2cc-110">Click **Retail** &gt; **Headquarters setup** &gt; **Parameters** &gt; **Retail parameters**.</span></span>
3.  <span data-ttu-id="ba2cc-111">Clique em **Inicializar**.</span><span class="sxs-lookup"><span data-stu-id="ba2cc-111">Click **Initialize**.</span></span>

<span data-ttu-id="ba2cc-112">A inicialização cria os seguintes dados de configuração padrão:</span><span class="sxs-lookup"><span data-stu-id="ba2cc-112">Initialization creates the following default configuration data:</span></span>

-   <span data-ttu-id="ba2cc-113">Trabalhos e subtrabalhos do agendador de varejo</span><span class="sxs-lookup"><span data-stu-id="ba2cc-113">Retail scheduler jobs and subjobs</span></span>
-   <span data-ttu-id="ba2cc-114">Esquema do canal de varejo</span><span class="sxs-lookup"><span data-stu-id="ba2cc-114">Retail channel schema</span></span>
-   <span data-ttu-id="ba2cc-115">Agendas de distribuição do varejo</span><span class="sxs-lookup"><span data-stu-id="ba2cc-115">Retail distribution schedules</span></span>
-   <span data-ttu-id="ba2cc-116">Layouts de tela padrão, que inclui grades de botões, imagens e temas</span><span class="sxs-lookup"><span data-stu-id="ba2cc-116">Default screen layouts, which include button grids, images, and themes</span></span>
-   <span data-ttu-id="ba2cc-117">Informações sobre fuso horário</span><span class="sxs-lookup"><span data-stu-id="ba2cc-117">Time zone information</span></span>
-   <span data-ttu-id="ba2cc-118">Operações de PDV (ponto de venda)</span><span class="sxs-lookup"><span data-stu-id="ba2cc-118">Point-of-sale (POS) operations</span></span>
-   <span data-ttu-id="ba2cc-119">Permissões do PDV</span><span class="sxs-lookup"><span data-stu-id="ba2cc-119">POS permissions</span></span>
-   <span data-ttu-id="ba2cc-120">Relatórios do canal</span><span class="sxs-lookup"><span data-stu-id="ba2cc-120">Channel reports</span></span>
-   <span data-ttu-id="ba2cc-121">Metadados de atributo</span><span class="sxs-lookup"><span data-stu-id="ba2cc-121">Attribute metadata</span></span>
-   <span data-ttu-id="ba2cc-122">Modelos de validação de entidade</span><span class="sxs-lookup"><span data-stu-id="ba2cc-122">Entity validation templates</span></span>
-   <span data-ttu-id="ba2cc-123">Trabalhos em lotes para limpar o histórico da sessão do Commerce Data Exchange</span><span class="sxs-lookup"><span data-stu-id="ba2cc-123">Batch job to purge Commerce Data Exchange session history</span></span>

<span data-ttu-id="ba2cc-124">Além disso, os registros relacionados à PCI (indústria de pagamento por cartão) estão habilitados para o banco de dados do Dynamics 365 for Retail.</span><span class="sxs-lookup"><span data-stu-id="ba2cc-124">Additionally, logging that is related to the payment card industry (PCI) is enabled for the Dynamics 365 for Retail database.</span></span> <span data-ttu-id="ba2cc-125">**Observação:** há uma opção para configurar separadamente o agendador do Retail.</span><span class="sxs-lookup"><span data-stu-id="ba2cc-125">**Note:** There is an option to separately configure the Retail scheduler.</span></span> <span data-ttu-id="ba2cc-126">Esta opção permite redefinir a configuração do agendador do Retail para suas configurações padrão.</span><span class="sxs-lookup"><span data-stu-id="ba2cc-126">This option lets you reset the Retail scheduler configuration to its default settings.</span></span> <span data-ttu-id="ba2cc-127">Depois que a inicialização for concluída, você deve configurar os dados adicionais de varejo.</span><span class="sxs-lookup"><span data-stu-id="ba2cc-127">After initialization is completed, you must configure additional retail data.</span></span> <span data-ttu-id="ba2cc-128">Eis alguns exemplos:</span><span class="sxs-lookup"><span data-stu-id="ba2cc-128">Here are some examples:</span></span>

-   <span data-ttu-id="ba2cc-129">Parâmetros de varejo</span><span class="sxs-lookup"><span data-stu-id="ba2cc-129">Retail parameters</span></span>
-   <span data-ttu-id="ba2cc-130">Parâmetros do agendador do Retail</span><span class="sxs-lookup"><span data-stu-id="ba2cc-130">Retail scheduler parameters</span></span>
-   <span data-ttu-id="ba2cc-131">Canais de varejo</span><span class="sxs-lookup"><span data-stu-id="ba2cc-131">Retail channels</span></span>
-   <span data-ttu-id="ba2cc-132">Registros e dispositivos</span><span class="sxs-lookup"><span data-stu-id="ba2cc-132">Registers and devices</span></span>
-   <span data-ttu-id="ba2cc-133">Sortimentos</span><span class="sxs-lookup"><span data-stu-id="ba2cc-133">Assortments</span></span>





