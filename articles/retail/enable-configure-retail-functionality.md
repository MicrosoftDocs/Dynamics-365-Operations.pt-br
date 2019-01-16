---
title: Inicialize dados semente em novos ambientes de varejo
description: "Este artigo descreve os dados que são criados como parte do processo de inicialização para o Microsoft Dynamics 365 for Retail."
author: josaw1
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-365-retail
ms.technology: 
ms.search.form: RetailParameters
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
ms.sourcegitcommit: 190d0b59ad2e232b33b3c0d1700cbaf95c45aeca
ms.openlocfilehash: 52f0c52748958f0bebb6c40df01cfac10c0ed427
ms.contentlocale: pt-br
ms.lasthandoff: 01/04/2019

---

# <a name="initialize-seed-data-in-new-retail-environments"></a><span data-ttu-id="a1d6a-103">Inicialize dados semente em novos ambientes de varejo</span><span class="sxs-lookup"><span data-stu-id="a1d6a-103">Initialize seed data in new Retail environments</span></span>

[!include [banner](includes/banner.md)]

<span data-ttu-id="a1d6a-104">Este artigo descreve os dados que são criados como parte do processo de inicialização para o Microsoft Dynamics 365 for Retail.</span><span class="sxs-lookup"><span data-stu-id="a1d6a-104">This article describes the data that's created as part of the initialization process for Microsoft Dynamics 365 for Retail.</span></span>

<span data-ttu-id="a1d6a-105">Depois que a solução Retail for implantada no Microsoft Dynamics Lifecycle Services (LCS), você deverá inicializar a configuração de varejo para criar os dados básicos de configuração.</span><span class="sxs-lookup"><span data-stu-id="a1d6a-105">After the Retail solution has been deployed through Microsoft Dynamics Lifecycle Services (LCS), you must initialize the retail configuration to create the basic configuration data.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="a1d6a-106">Antes de inicializar a configuração de varejo, verifique se você especificou um idioma e um endereço postal para cada entidade legal em que configurará lojas de varejo.</span><span class="sxs-lookup"><span data-stu-id="a1d6a-106">Before you initialize the retail configuration, make sure that you've specified a language and a postal address for each legal entity where you will set up retail stores.</span></span> <span data-ttu-id="a1d6a-107">Essa etapa deve ser concluída para cada entidade legal usada no varejo.</span><span class="sxs-lookup"><span data-stu-id="a1d6a-107">This step must be completed for each legal entity that you use for retail.</span></span>

<span data-ttu-id="a1d6a-108">Para inicializar a configuração de varejo, execute estas etapas:</span><span class="sxs-lookup"><span data-stu-id="a1d6a-108">To initialize the retail configuration, follow these steps.</span></span>

1. <span data-ttu-id="a1d6a-109">Inicie o cliente do Dynamics 365 for Retail.</span><span class="sxs-lookup"><span data-stu-id="a1d6a-109">Start the Dynamics 365 for Retail client.</span></span>
2. <span data-ttu-id="a1d6a-110">Clique em **Varejo** &gt; **Configuração da sede** &gt; **Parâmetros** &gt; **Parâmetros de varejo**.</span><span class="sxs-lookup"><span data-stu-id="a1d6a-110">Click **Retail** &gt; **Headquarters setup** &gt; **Parameters** &gt; **Retail parameters**.</span></span>
3. <span data-ttu-id="a1d6a-111">Clique em **Inicializar**.</span><span class="sxs-lookup"><span data-stu-id="a1d6a-111">Click **Initialize**.</span></span>

<span data-ttu-id="a1d6a-112">A inicialização cria os seguintes dados de configuração padrão:</span><span class="sxs-lookup"><span data-stu-id="a1d6a-112">Initialization creates the following default configuration data:</span></span>

- <span data-ttu-id="a1d6a-113">Trabalhos e subtrabalhos do agendador de varejo</span><span class="sxs-lookup"><span data-stu-id="a1d6a-113">Retail scheduler jobs and subjobs</span></span>
- <span data-ttu-id="a1d6a-114">Esquema do canal de varejo</span><span class="sxs-lookup"><span data-stu-id="a1d6a-114">Retail channel schema</span></span>
- <span data-ttu-id="a1d6a-115">Agendas de distribuição do varejo</span><span class="sxs-lookup"><span data-stu-id="a1d6a-115">Retail distribution schedules</span></span>
- <span data-ttu-id="a1d6a-116">Layouts de tela padrão, que inclui grades de botões, imagens e temas</span><span class="sxs-lookup"><span data-stu-id="a1d6a-116">Default screen layouts, which include button grids, images, and themes</span></span>
- <span data-ttu-id="a1d6a-117">Informações sobre fuso horário</span><span class="sxs-lookup"><span data-stu-id="a1d6a-117">Time zone information</span></span>
- <span data-ttu-id="a1d6a-118">Operações de PDV (ponto de venda)</span><span class="sxs-lookup"><span data-stu-id="a1d6a-118">Point-of-sale (POS) operations</span></span>
- <span data-ttu-id="a1d6a-119">Permissões do PDV</span><span class="sxs-lookup"><span data-stu-id="a1d6a-119">POS permissions</span></span>
- <span data-ttu-id="a1d6a-120">Relatórios do canal</span><span class="sxs-lookup"><span data-stu-id="a1d6a-120">Channel reports</span></span>
- <span data-ttu-id="a1d6a-121">Metadados de atributo</span><span class="sxs-lookup"><span data-stu-id="a1d6a-121">Attribute metadata</span></span>
- <span data-ttu-id="a1d6a-122">Modelos de validação de entidade</span><span class="sxs-lookup"><span data-stu-id="a1d6a-122">Entity validation templates</span></span>
- <span data-ttu-id="a1d6a-123">Trabalhos em lotes para limpar o histórico da sessão do Commerce Data Exchange</span><span class="sxs-lookup"><span data-stu-id="a1d6a-123">Batch job to purge Commerce Data Exchange session history</span></span>

<span data-ttu-id="a1d6a-124">Além disso, os registros relacionados à PCI (indústria de pagamento por cartão) estão habilitados para o banco de dados do Dynamics 365 for Retail.</span><span class="sxs-lookup"><span data-stu-id="a1d6a-124">Additionally, logging that is related to the payment card industry (PCI) is enabled for the Dynamics 365 for Retail database.</span></span>

> [!NOTE]
> <span data-ttu-id="a1d6a-125">Há uma opção para configurar separadamente o Agendador do Retail.</span><span class="sxs-lookup"><span data-stu-id="a1d6a-125">There is an option to separately configure the Retail scheduler.</span></span> <span data-ttu-id="a1d6a-126">Esta opção permite redefinir a configuração do agendador do Retail para suas configurações padrão.</span><span class="sxs-lookup"><span data-stu-id="a1d6a-126">This option lets you reset the Retail scheduler configuration to its default settings.</span></span>

<span data-ttu-id="a1d6a-127">Depois que a inicialização for concluída, você deve configurar os dados adicionais de varejo.</span><span class="sxs-lookup"><span data-stu-id="a1d6a-127">After initialization is completed, you must configure additional retail data.</span></span> <span data-ttu-id="a1d6a-128">Eis alguns exemplos:</span><span class="sxs-lookup"><span data-stu-id="a1d6a-128">Here are some examples:</span></span>

- <span data-ttu-id="a1d6a-129">Parâmetros de varejo</span><span class="sxs-lookup"><span data-stu-id="a1d6a-129">Retail parameters</span></span>
- <span data-ttu-id="a1d6a-130">Parâmetros do agendador do Retail</span><span class="sxs-lookup"><span data-stu-id="a1d6a-130">Retail scheduler parameters</span></span>
- <span data-ttu-id="a1d6a-131">Canais de varejo</span><span class="sxs-lookup"><span data-stu-id="a1d6a-131">Retail channels</span></span>
- <span data-ttu-id="a1d6a-132">Registros e dispositivos</span><span class="sxs-lookup"><span data-stu-id="a1d6a-132">Registers and devices</span></span>
- <span data-ttu-id="a1d6a-133">Sortimentos</span><span class="sxs-lookup"><span data-stu-id="a1d6a-133">Assortments</span></span>

