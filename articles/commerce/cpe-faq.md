---
title: Perguntas frequentes sobre o ambiente de avaliação do Dynamics 365 Commerce
description: Este tópico fornece respostas às perguntas frequentes sobre o ambiente de avaliação do Microsoft Dynamics 365 Commerce.
author: v-chgri
manager: annbe
ms.date: 07/16/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-commerce
ms.technology: ''
audience: Application user
ms.reviewer: v-chgri
ms.search.scope: Operations, Retail, Core
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: v-chgri
ms.search.validFrom: 2019-12-10
ms.dyn365.ops.version: Release 10.0.5
ms.openlocfilehash: 637714e28b9f8f4aa66e251e709d8f78bff2739d
ms.sourcegitcommit: 5175e3fae432016246244cf70fe05465f43de88c
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/17/2020
ms.locfileid: "3599741"
---
# <a name="dynamics-365-commerce-evaluation-environment-faq"></a><span data-ttu-id="5627c-103">Perguntas frequentes sobre o ambiente de avaliação do Dynamics 365 Commerce</span><span class="sxs-lookup"><span data-stu-id="5627c-103">Dynamics 365 Commerce evaluation environment FAQ</span></span>

[!include [banner](includes/banner.md)]

<span data-ttu-id="5627c-104">Este tópico fornece respostas às perguntas frequentes sobre o ambiente de avaliação do Microsoft Dynamics 365 Commerce.</span><span class="sxs-lookup"><span data-stu-id="5627c-104">This topic provides answers to frequently asked questions about the Microsoft Dynamics 365 Commerce evaluation environment.</span></span>

<span data-ttu-id="5627c-105">**É possível usar o ambiente de avaliação do Commerce como uma vitrine do e-Commerce para clientes que atualmente implementam o Retail?**</span><span class="sxs-lookup"><span data-stu-id="5627c-105">**Can we use the Commerce evaluation environment as an e-Commerce storefront for customers that currently implement Retail?**</span></span>

<span data-ttu-id="5627c-106">Não.</span><span class="sxs-lookup"><span data-stu-id="5627c-106">No.</span></span> <span data-ttu-id="5627c-107">O ambiente de avaliação do Commerce é somente para avaliação.</span><span class="sxs-lookup"><span data-stu-id="5627c-107">The Commerce evaluation environment is only for evaluation.</span></span> <span data-ttu-id="5627c-108">Se você precisar de um ambiente para um cliente que implemente Varejo, contate a Microsoft.</span><span class="sxs-lookup"><span data-stu-id="5627c-108">If you require an environment for a customer that implements Retail, contact Microsoft.</span></span>

<span data-ttu-id="5627c-109">**O ambiente de avaliação do Commerce pode ser usado para provisionar os recursos do e-Commerce sobre um aplicativo/ambiente existente que implementa o Retail?**</span><span class="sxs-lookup"><span data-stu-id="5627c-109">**Can the Commerce evaluation environment be used to provision the e-Commerce features on top of an existing application/environment that implements Retail?**</span></span>

<span data-ttu-id="5627c-110">Não (normalmente).</span><span class="sxs-lookup"><span data-stu-id="5627c-110">No (mostly).</span></span> <span data-ttu-id="5627c-111">Os componentes de avaliação do Commerce estão disponíveis somente para ambientes que correspondam às configurações especificadas no guia de pré-requisitos e provisionamento.</span><span class="sxs-lookup"><span data-stu-id="5627c-111">The Commerce evaluation components are available only to environments that match the configurations that are specified in the prerequisites and provisioning guide.</span></span> <span data-ttu-id="5627c-112">Além disso, os dados de demonstração base necessários não estarão disponíveis em ambientes implantados com uma versão inicial anterior à 10.0.8.</span><span class="sxs-lookup"><span data-stu-id="5627c-112">Additionally, the required base demo data won't be available in environments that were deployed with an initial release that is earlier than 10.0.8.</span></span> 

<span data-ttu-id="5627c-113">**Quais são os custos envolvidos na implantação do ambiente de avaliação do Commerce no Microsoft Azure via Microsoft Dynamics Lifecycle Services (LCS)?**</span><span class="sxs-lookup"><span data-stu-id="5627c-113">**What costs are involved in deploying the Commerce evaluation environment on Microsoft Azure via Microsoft Dynamics Lifecycle Services (LCS)?**</span></span>

<span data-ttu-id="5627c-114">Um ambiente de demonstração de sede tradicional (máquina virtual \[VM\]) do Dynamics 365 Finance/Dynamics 365 Supply Chain Management/Dynamics 365 Commerce será hospedado na sua assinatura do Azure.</span><span class="sxs-lookup"><span data-stu-id="5627c-114">A traditional Dynamics 365 Finance/Dynamics 365 Supply Chain Management/Dynamics 365 Commerce headquarters demo environment (virtual machine \[VM\]) will be hosted in your Azure subscription.</span></span> <span data-ttu-id="5627c-115">Você pode usar a [Calculadora de preços do Azure](https://azure.microsoft.com/pricing/calculator/) para estimar esse custo.</span><span class="sxs-lookup"><span data-stu-id="5627c-115">You can use the [Azure pricing calculator](https://azure.microsoft.com/pricing/calculator/) to estimate this cost.</span></span>

<span data-ttu-id="5627c-116">Outros componentes, como o Commerce Scale Unit, o construtor de sites do Commerce e seu site do e-Commerce, estarão disponíveis como software como serviço (SaaS) e serão hospedados pela Microsoft.</span><span class="sxs-lookup"><span data-stu-id="5627c-116">Other components such as Commerce Scale Unit, Commerce site builder, and your e-Commerce site will be available as software as a service (SaaS) and hosted by Microsoft.</span></span>

<span data-ttu-id="5627c-117">**Quais regiões do Azure são atualmente compatíveis com o ambiente de avaliação do Commerce?**</span><span class="sxs-lookup"><span data-stu-id="5627c-117">**Which Azure geographies are currently supported for the Commerce evaluation environment?**</span></span>

<span data-ttu-id="5627c-118">O ambiente de avaliação do Commerce só pode ser implantado na América do Norte.</span><span class="sxs-lookup"><span data-stu-id="5627c-118">The Commerce evaluation environment can be deployed only in the North America geography.</span></span>

<span data-ttu-id="5627c-119">**Há um disco rígido virtual (VHD) baixado que tem a opção de máquina virtual (VM) OneBox completa?**</span><span class="sxs-lookup"><span data-stu-id="5627c-119">**Is there a downloadable virtual hard disk (VHD) that has the complete OneBox virtual machine (VM) option?**</span></span>

<span data-ttu-id="5627c-120">O Dynamics 365 Commerce e o Commerce Scale Unit são totalmente software como serviço (SaaS) e devem ser hospedados na nuvem.</span><span class="sxs-lookup"><span data-stu-id="5627c-120">Dynamics 365 Commerce and Commerce Scale Unit are completely software as a service (SaaS) and must be cloud-hosted.</span></span>

<span data-ttu-id="5627c-121">**Por quanto tempo o ambiente de avaliação do Commerce pode ser usado?**</span><span class="sxs-lookup"><span data-stu-id="5627c-121">**How long can the Commerce evaluation environment be used?**</span></span>

<span data-ttu-id="5627c-122">O ambiente de avaliação do Commerce tem um limite de tempo de 30 dias a partir da data em que componentes SaaS, como o Commerce Scale Unit, o construtor de sites do Commerce e seu site do e-Commerce, são provisionados.</span><span class="sxs-lookup"><span data-stu-id="5627c-122">The Commerce evaluation environment has a 30-day time limit from the date when SaaS components such as Commerce Scale Unit, Commerce site builder, and your e-Commerce site are provisioned.</span></span>

<span data-ttu-id="5627c-123">**É possível estender o limite de tempo para meu ambiente de avaliação do Commerce?**</span><span class="sxs-lookup"><span data-stu-id="5627c-123">**Can I extend the time limit for my Commerce evaluation environment?**</span></span>

<span data-ttu-id="5627c-124">A extensão do limite de tempo é uma exceção à norma e é considerada caso a caso.</span><span class="sxs-lookup"><span data-stu-id="5627c-124">Extension of the time limit is an exception to the norm and is considered on a case-by-case basis.</span></span> <span data-ttu-id="5627c-125">Fale com o contato do seu parceiro Microsoft para obter ajuda.</span><span class="sxs-lookup"><span data-stu-id="5627c-125">You should reach out to your Microsoft partner contact for assistance.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="5627c-126">Recursos adicionais</span><span class="sxs-lookup"><span data-stu-id="5627c-126">Additional resources</span></span>

[<span data-ttu-id="5627c-127">Visão geral do ambiente de avaliação do Dynamics 365 Commerce</span><span class="sxs-lookup"><span data-stu-id="5627c-127">Dynamics 365 Commerce evaluation environment overview</span></span>](cpe-overview.md)

[<span data-ttu-id="5627c-128">Provisionar um ambiente de avaliação do Dynamics 365 Commerce</span><span class="sxs-lookup"><span data-stu-id="5627c-128">Provision a Dynamics 365 Commerce evaluation environment</span></span>](provisioning-guide.md)

[<span data-ttu-id="5627c-129">Configurar um ambiente de avaliação do Dynamics 365 Commerce</span><span class="sxs-lookup"><span data-stu-id="5627c-129">Configure a Dynamics 365 Commerce evaluation environment</span></span>](cpe-post-provisioning.md)

[<span data-ttu-id="5627c-130">Configurar BOPIS em um ambiente de avaliação do Dynamics 365 Commerce</span><span class="sxs-lookup"><span data-stu-id="5627c-130">Configure BOPIS in a Dynamics 365 Commerce evaluation environment</span></span>](cpe-bopis.md)

[<span data-ttu-id="5627c-131">Configurar recursos opcionais para um ambiente de avaliação do Dynamics 365 Commerce</span><span class="sxs-lookup"><span data-stu-id="5627c-131">Configure optional features for a Dynamics 365 Commerce evaluation environment</span></span>](cpe-optional-features.md)
