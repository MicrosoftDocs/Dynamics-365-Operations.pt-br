---
title: Inicializar dados de propagação em novos ambientes do Commerce
description: Este artigo descreve os dados que são criados como parte do processo de inicialização do Dynamics 365 Commerce.
author: josaw1
ms.date: 06/20/2017
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: RetailParameters
audience: Application User
ms.reviewer: josaw
ms.custom: 49621
ms.assetid: 4dc762eb-190e-4485-8f55-b0cafc81bc37
ms.search.region: global
ms.search.industry: Retail
ms.author: josaw
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0, Retail July 2017 update
ms.openlocfilehash: 9f534410b21fd97554f4e038bb14eebd5f887130
ms.sourcegitcommit: 3cdc42346bb653c13ab33a7142dbb7969f1f6dda
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/31/2021
ms.locfileid: "5792574"
---
# <a name="initialize-seed-data-in-new-commerce-environments"></a><span data-ttu-id="17478-103">Inicializar dados de propagação em novos ambientes do Commerce</span><span class="sxs-lookup"><span data-stu-id="17478-103">Initialize seed data in new Commerce environments</span></span>

[!include [banner](includes/banner.md)]

<span data-ttu-id="17478-104">Este artigo descreve os dados que são criados como parte do processo de inicialização do Dynamics 365 Commerce.</span><span class="sxs-lookup"><span data-stu-id="17478-104">This article describes the data that's created as part of the initialization process for Dynamics 365 Commerce.</span></span>

<span data-ttu-id="17478-105">Depois que a solução Commerce tiver sido implantada por meio do Microsoft Dynamics Lifecycle Services (LCS), você deverá inicializar a configuração de Commerce para criar os dados básicos de configuração.</span><span class="sxs-lookup"><span data-stu-id="17478-105">After the Commerce solution has been deployed through Microsoft Dynamics Lifecycle Services (LCS), you must initialize the Commerce configuration to create the basic configuration data.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="17478-106">Antes de inicializar a configuração do Commerce, verifique se você especificou um idioma e um endereço postal para cada entidade legal em que vai configurar repositórios.</span><span class="sxs-lookup"><span data-stu-id="17478-106">Before you initialize the commerce configuration, make sure that you've specified a language and a postal address for each legal entity where you will set up stores.</span></span> <span data-ttu-id="17478-107">Essa etapa deve ser concluída para cada entidade legal usada para comércio.</span><span class="sxs-lookup"><span data-stu-id="17478-107">This step must be completed for each legal entity that you use for commerce.</span></span>

<span data-ttu-id="17478-108">Para inicializar a configuração, siga estas etapas.</span><span class="sxs-lookup"><span data-stu-id="17478-108">To initialize the configuration, follow these steps.</span></span>

1. <span data-ttu-id="17478-109">Inicie o cliente do Commerce.</span><span class="sxs-lookup"><span data-stu-id="17478-109">Start the Commerce client.</span></span>
2. <span data-ttu-id="17478-110">Clique em **Retail e Commerce** &gt; **Configuração da sede** &gt; **Parâmetros** &gt; **Parâmetros do Commerce**.</span><span class="sxs-lookup"><span data-stu-id="17478-110">Click **Retail and Commerce** &gt; **Headquarters setup** &gt; **Parameters** &gt; **Commerce parameters**.</span></span>
3. <span data-ttu-id="17478-111">Clique em **Inicializar**.</span><span class="sxs-lookup"><span data-stu-id="17478-111">Click **Initialize**.</span></span>

<span data-ttu-id="17478-112">A inicialização cria os seguintes dados de configuração padrão:</span><span class="sxs-lookup"><span data-stu-id="17478-112">Initialization creates the following default configuration data:</span></span>

- <span data-ttu-id="17478-113">Trabalhos e subtrabalhos do agendador do Commerce</span><span class="sxs-lookup"><span data-stu-id="17478-113">Commerce scheduler jobs and subjobs</span></span>
- <span data-ttu-id="17478-114">Esquema de canal de comércio</span><span class="sxs-lookup"><span data-stu-id="17478-114">Commerce channel schema</span></span>
- <span data-ttu-id="17478-115">Agendas de distribuição do Commerce</span><span class="sxs-lookup"><span data-stu-id="17478-115">Commerce distribution schedules</span></span>
- <span data-ttu-id="17478-116">Layouts de tela padrão, que inclui grades de botões, imagens e temas</span><span class="sxs-lookup"><span data-stu-id="17478-116">Default screen layouts, which include button grids, images, and themes</span></span>
- <span data-ttu-id="17478-117">Informações sobre fuso horário</span><span class="sxs-lookup"><span data-stu-id="17478-117">Time zone information</span></span>
- <span data-ttu-id="17478-118">Operações de PDV (ponto de venda)</span><span class="sxs-lookup"><span data-stu-id="17478-118">Point-of-sale (POS) operations</span></span>
- <span data-ttu-id="17478-119">Permissões do PDV</span><span class="sxs-lookup"><span data-stu-id="17478-119">POS permissions</span></span>
- <span data-ttu-id="17478-120">Relatórios do canal</span><span class="sxs-lookup"><span data-stu-id="17478-120">Channel reports</span></span>
- <span data-ttu-id="17478-121">Metadados de atributo</span><span class="sxs-lookup"><span data-stu-id="17478-121">Attribute metadata</span></span>
- <span data-ttu-id="17478-122">Modelos de validação de entidade</span><span class="sxs-lookup"><span data-stu-id="17478-122">Entity validation templates</span></span>
- <span data-ttu-id="17478-123">Trabalho em lotes para limpar o histórico da sessão do Commerce Data Exchange</span><span class="sxs-lookup"><span data-stu-id="17478-123">Batch job to purge Commerce Data Exchange session history</span></span>

<span data-ttu-id="17478-124">Além disso, os registros relacionados à PCI (indústria de pagamento por cartão) estão habilitados para o banco de dados do Commerce.</span><span class="sxs-lookup"><span data-stu-id="17478-124">Additionally, logging that is related to the payment card industry (PCI) is enabled for the Commerce database.</span></span>

> [!NOTE]
> <span data-ttu-id="17478-125">Há uma opção para configurar separadamente o agendador do Commerce.</span><span class="sxs-lookup"><span data-stu-id="17478-125">There is an option to separately configure the Commerce scheduler.</span></span> <span data-ttu-id="17478-126">Essa opção permite redefinir a configuração do agendador do Commerce para suas configurações padrão.</span><span class="sxs-lookup"><span data-stu-id="17478-126">This option lets you reset the Commerce scheduler configuration to its default settings.</span></span>

<span data-ttu-id="17478-127">Depois que a inicialização for concluída, você deverá configurar os dados adicionais do Commerce.</span><span class="sxs-lookup"><span data-stu-id="17478-127">After initialization is completed, you must configure additional commerce data.</span></span> <span data-ttu-id="17478-128">Eis alguns exemplos:</span><span class="sxs-lookup"><span data-stu-id="17478-128">Here are some examples:</span></span>

- <span data-ttu-id="17478-129">Parâmetros de comércio</span><span class="sxs-lookup"><span data-stu-id="17478-129">Commerce parameters</span></span>
- <span data-ttu-id="17478-130">Parâmetros do agendador do Commerce</span><span class="sxs-lookup"><span data-stu-id="17478-130">Commerce scheduler parameters</span></span>
- <span data-ttu-id="17478-131">Canais do Commerce</span><span class="sxs-lookup"><span data-stu-id="17478-131">Commerce channels</span></span>
- <span data-ttu-id="17478-132">Registros e dispositivos</span><span class="sxs-lookup"><span data-stu-id="17478-132">Registers and devices</span></span>
- <span data-ttu-id="17478-133">Sortimentos</span><span class="sxs-lookup"><span data-stu-id="17478-133">Assortments</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]