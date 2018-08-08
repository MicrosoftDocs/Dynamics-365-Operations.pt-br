---
title: "Integração com o Microsoft Dynamics 365 for Field Service"
description: "Este tópico fornece uma visão geral da integração com o Microsoft Dynamics 365 for Field Service."
author: ChristianRytt
manager: AnnBe
ms.date: 04/25/2018
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: 
audience: Application User, IT Pro
ms.reviewer: josaw
ms.search.scope: Core, Operations
ms.custom: 
ms.assetid: 
ms.search.region: global
ms.search.industry: 
ms.author: crytt
ms.dyn365.ops.version: July 2017 update
ms.search.validFrom: 2017-07-8
ms.translationtype: HT
ms.sourcegitcommit: 1d98cbff30620256c9d13e7b4a90314db150e33e
ms.openlocfilehash: 2ef7f71dc6d58108b498ed89e9175ff2ce900cda
ms.contentlocale: pt-br
ms.lasthandoff: 08/07/2018

---


# <a name="integration-with-microsoft-dynamics-365-for-field-service"></a><span data-ttu-id="b013f-103">Integração com o Microsoft Dynamics 365 for Field Service</span><span class="sxs-lookup"><span data-stu-id="b013f-103">Integration with Microsoft Dynamics 365 for Field Service</span></span>

[!include[banner](../includes/banner.md)]

<span data-ttu-id="b013f-104">O Microsoft Dynamics 365 for Finance and Operations permite a sincronização dos processos comerciais entre o Finance and Operations e o Microsoft Dynamics 365 for Field Service.</span><span class="sxs-lookup"><span data-stu-id="b013f-104">Microsoft Dynamics 365 for Finance and Operations enables synchronization of business processes between Finance and Operations and Microsoft Dynamics 365 for Field Service.</span></span> <span data-ttu-id="b013f-105">Os cenários de integração são configurados usando modelos extensíveis do Integrador de dados e o CDS (Common Data Service) para habilitar a sincronização dos processos comerciais.</span><span class="sxs-lookup"><span data-stu-id="b013f-105">The integration scenarios are configured by using extensible Data integrator templates and the Common Data Service (CDS) to enable the synchronization of business processes.</span></span>

<span data-ttu-id="b013f-106">[![Sincronização de processos empresariais entre o Finance and Operations e o Field Service](./media/field-service-integration.png)](./media/field-service-integration.png)</span><span class="sxs-lookup"><span data-stu-id="b013f-106">[![Synchronization of business processes between Finance and Operations and Field Service](./media/field-service-integration.png)](./media/field-service-integration.png)</span></span>

<span data-ttu-id="b013f-107">A primeira fase da integração entre o Field Service e o Finance and Operations é centrada em habilitar ordens de trabalho e contratos no Field Service para serem faturados no Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="b013f-107">The first phase  of the integration between Field Service and Finance and Operations is focused on enabling work orders and agreements in Field Service to be invoiced in Finance and Operations.</span></span> <span data-ttu-id="b013f-108">O fluxo com suporte começa no Field Service, onde as informações das ordens de trabalho são sincronizadas com o Finance and Operations como ordens de venda.</span><span class="sxs-lookup"><span data-stu-id="b013f-108">The supported flow starts in Field Service, where information from work orders is synchronized to Finance and Operations as sales orders.</span></span> <span data-ttu-id="b013f-109">No Finance and Operations, as ordens de venda são faturadas para gerar os documentos de fatura.</span><span class="sxs-lookup"><span data-stu-id="b013f-109">In Finance and Operations, the sales orders are invoiced to generate invoice documents.</span></span> <span data-ttu-id="b013f-110">Além disso, as informações das faturas de contrato do Field Service são sincronizadas com o Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="b013f-110">In addition, the information from Field Service agreement invoices is synchronized to Finance and Operations.</span></span> <span data-ttu-id="b013f-111">O Integrador de dados do Microsoft Dynamics 365 sincroniza os dados usando projetos personalizáveis.</span><span class="sxs-lookup"><span data-stu-id="b013f-111">The Microsoft Dynamics 365 Data integrator synchronizes data by using customizable projects.</span></span> <span data-ttu-id="b013f-112">Modelos padrão podem ser usados para criar projetos de integração personalizados em que o padrão adicional e os campos personalizadas, além das entidades, podem ser mapeados para ajustar a integração e para atender a requisitos específicos.</span><span class="sxs-lookup"><span data-stu-id="b013f-112">Standard templates can be used to create custom integration projects where additional standard and custom fields, and also entities, can be mapped to adjust the integration and meet specific requirements.</span></span>

<span data-ttu-id="b013f-113">O primeira fase da integração entre o Field Service e o Finance and Operations permite a sincronização dos seguintes itens:</span><span class="sxs-lookup"><span data-stu-id="b013f-113">The first phase of the integration between Field Service and Finance and Operations enables synchronization of the following items:</span></span>

- [<span data-ttu-id="b013f-114">Produto no Finance and Operations com produtos no Field Service que incluam informações de Tipo de Produto</span><span class="sxs-lookup"><span data-stu-id="b013f-114">Products in Finance and Operations to products in Field Service that include Product Type information</span></span>](field-service-product.md)
- [<span data-ttu-id="b013f-115">Ordens de trabalho no Field Service com ordens de venda no Finance and Operations</span><span class="sxs-lookup"><span data-stu-id="b013f-115">Work orders in Field Service to sales orders in Finance and Operations</span></span>](field-service-work-order.md)
- [<span data-ttu-id="b013f-116">Faturas no Field Service com faturas de texto livre no Finance and Operations</span><span class="sxs-lookup"><span data-stu-id="b013f-116">Invoices in Field Service to free text invoices in Finance and Operations</span></span>](field-service-invoice.md)

<span data-ttu-id="b013f-117">Para ver um exemplo de como você pode sincronizar uma ordem de trabalho entre o Field Service e Finance and Operations , assista a um vídeo do YouTube [Sincronizar uma ordem de trabalho entre o Dynamics 365 for Field Service e Finance and Operations](https://www.youtube.com/watch?v=hAB4TDVMjxU).</span><span class="sxs-lookup"><span data-stu-id="b013f-117">To see an example of how you can synchronize a work order between Field Service and Finance and Operations, watch the short YouTube video [Synchronize a work order between Dynamics 365 for Field Service and Finance and Operations](https://www.youtube.com/watch?v=hAB4TDVMjxU).</span></span>

[![](https://img.youtube.com/vi/hAB4TDVMjxU/0.jpg)](https://www.youtube.com/watch?v=hAB4TDVMjxU)

## <a name="system-requirements-for-finance-and-operations"></a><span data-ttu-id="b013f-118">Requisitos de sistema para Finance and Operations</span><span class="sxs-lookup"><span data-stu-id="b013f-118">System requirements for Finance and Operations</span></span>
<span data-ttu-id="b013f-119">A integração do Field Service é compatível com as seguintes versões:</span><span class="sxs-lookup"><span data-stu-id="b013f-119">Field Service integration supports the following versions:</span></span>

### <a name="dynamics-365-for-finance-and-operations-version-80-april-2018-or-later"></a><span data-ttu-id="b013f-120">Versão 8.0 do Dynamics 365 for Finance and Operations (abril de 2018) ou posterior</span><span class="sxs-lookup"><span data-stu-id="b013f-120">Dynamics 365 for Finance and Operations version 8.0 (April 2018) or later</span></span>

- <span data-ttu-id="b013f-121">A versão 8.0 do Dynamics 365 for Finance and Operations (abril de 2018) foi liberada em abril de 2018 e tem o número de compilação do aplicativo 8.0.30.8020 com a atualização 15 da plataforma (7.0.4841.35234).</span><span class="sxs-lookup"><span data-stu-id="b013f-121">Dynamics 365 for Finance and Operations version 8.0 (April 2018) was released in April 2018 and has an application build number 8.0.30.8020 with Platform Update 15 (7.0.4841.35234).</span></span> 

## <a name="system-requirements-for-field-service"></a><span data-ttu-id="b013f-122">Requisitos do sistema para o Field Service</span><span class="sxs-lookup"><span data-stu-id="b013f-122">System requirements for Field Service</span></span>
<span data-ttu-id="b013f-123">Para usar a solução de integração do Field Service, você deve instalar os seguintes componentes:</span><span class="sxs-lookup"><span data-stu-id="b013f-123">To use the Field Service integration solution, you must install the following components:</span></span>

### <a name="microsoft-dynamics-365-for-field-service-90-or-later"></a><span data-ttu-id="b013f-124">Microsoft Dynamics 365 for Field Service 9.0 ou posterior</span><span class="sxs-lookup"><span data-stu-id="b013f-124">Microsoft Dynamics 365 for Field Service 9.0 or later</span></span>

- <span data-ttu-id="b013f-125">Dynamics 365 for Field Service, versão 1612 (9.0.1.733) (DB 9.0.1.733) online ou uma versão posterior.</span><span class="sxs-lookup"><span data-stu-id="b013f-125">Dynamics 365 for Field Service version 1612 (9.0.1.733) (DB 9.0.1.733) online or a later version.</span></span>
- <span data-ttu-id="b013f-126">Solução P2C (Prospect to Cash) para Dynamics 365, versão 1.15.0.1 ou uma versão posterior.</span><span class="sxs-lookup"><span data-stu-id="b013f-126">Prospect to Cash (P2C) solution for Dynamics 365, version 1.15.0.1 or a later version.</span></span> <span data-ttu-id="b013f-127">A solução está disponível para download no [AppSource](https://appsource.microsoft.com/en-us/product/dynamics-365/mscrm.c7a48b40-eed3-4d67-93ba-f2364281feb3).</span><span class="sxs-lookup"><span data-stu-id="b013f-127">The solution is available for download from [AppSource](https://appsource.microsoft.com/en-us/product/dynamics-365/mscrm.c7a48b40-eed3-4d67-93ba-f2364281feb3).</span></span>
- <span data-ttu-id="b013f-128">Integração do Field Service para Dynamics 365, versão 1.0.0.0 ou uma versão posterior.</span><span class="sxs-lookup"><span data-stu-id="b013f-128">Field Service integration solution for Dynamics 365, version 1.0.0.0 or a later version.</span></span> <span data-ttu-id="b013f-129">A solução está disponível para download no [AppSource](https://appsource.microsoft.com/en-us/product/dynamics-365/mscrm.p2cfieldserviceintegration).</span><span class="sxs-lookup"><span data-stu-id="b013f-129">The solution is available for download from [AppSource](https://appsource.microsoft.com/en-us/product/dynamics-365/mscrm.p2cfieldserviceintegration).</span></span>

