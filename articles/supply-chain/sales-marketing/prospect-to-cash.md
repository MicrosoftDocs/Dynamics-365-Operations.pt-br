---
title: Prospect to cash
description: Este tópico fornece uma visão geral da solução Prospect to cash entre o Dynamics 365 Supply Chain Management e o Dynamics 365 Sales.
author: ChristianRytt
manager: tfehr
ms.date: 04/25/2018
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: CustTable, SalesTable, EcoResProductListPage
audience: Application User, IT Pro
ms.reviewer: kamaybac
ms.custom: ''
ms.assetid: ''
ms.search.region: global
ms.search.industry: ''
ms.author: crytt
ms.dyn365.ops.version: July 2017 update
ms.search.validFrom: 2017-07-8
ms.openlocfilehash: b2f2f7d95d3f0e6bd774c43024836aac1f729abd
ms.sourcegitcommit: 38d40c331c8894acb7b119c5073e3088b54776c1
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/15/2021
ms.locfileid: "4977629"
---
# <a name="prospect-to-cash"></a><span data-ttu-id="00929-103">Cliente potencial ao pagamento à vista</span><span class="sxs-lookup"><span data-stu-id="00929-103">Prospect to cash</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="00929-104">A solução Prospect to cash fornece sincronização direta entre o Dynamics 365 Supply Chain Management e o Dynamics 365 Sales.</span><span class="sxs-lookup"><span data-stu-id="00929-104">The Prospect to cash solution provides direct synchronization across Dynamics 365 Supply Chain Management and Dynamics 365 Sales.</span></span> <span data-ttu-id="00929-105">Os modelos Prospect to cash que estão disponíveis com o recurso Integração de Dados permitem o fluxo de dados para contas, contatos, produtos, cotações de vendas, ordens de venda e faturas de vendas.</span><span class="sxs-lookup"><span data-stu-id="00929-105">The Prospect to cash templates that are available with the Data Integration feature enable the flow of data for accounts, contacts, products, sales quotations, sales orders, and sales invoices.</span></span> <span data-ttu-id="00929-106">Enquanto os dados estiverem fluindo, você poderá executar atividades de vendas e marketing no Sales, bem como poderá tratar do atendimento da ordem usando o gerenciamento de estoque no Supply Chain Management.</span><span class="sxs-lookup"><span data-stu-id="00929-106">While data is flowing, you can perform sales and marketing activities in Sales, and you can handle order fulfillment by using inventory management in Supply Chain Management.</span></span> 

<span data-ttu-id="00929-107">Para obter mais informações sobre a integração Prospect to cash, assista ao vídeo curto no YouTube [Integração do cliente potencial ao pagamento à vista](https://www.youtube.com/watch?v=AVV9x5x-XCg).</span><span class="sxs-lookup"><span data-stu-id="00929-107">For more information about the Prospect to cash integration, watch the short YouTube video [Prospect to cash integration](https://www.youtube.com/watch?v=AVV9x5x-XCg).</span></span>

<span data-ttu-id="00929-108">Na versão atual, a solução Prospect to cash fornece os seguintes tipos de sincronização direta:</span><span class="sxs-lookup"><span data-stu-id="00929-108">In the current version, the Prospect to cash solution provides the following types of direct synchronization:</span></span>

- [<span data-ttu-id="00929-109">Sincronizar contas diretamente do Sales com clientes no Supply Chain Management</span><span class="sxs-lookup"><span data-stu-id="00929-109">Synchronize accounts directly from Sales to customers in Supply Chain Management</span></span>](accounts-template-mapping-direct.md)
- [<span data-ttu-id="00929-110">Sincronizar produtos diretamente do Supply Chain Management com produtos do Sales</span><span class="sxs-lookup"><span data-stu-id="00929-110">Synchronize products directly from Supply Chain Management to products in Sales</span></span>](products-template-mapping-direct.md)
- [<span data-ttu-id="00929-111">Sincronizar contatos diretamente do Sales com contatos ou clientes do Supply Chain Management</span><span class="sxs-lookup"><span data-stu-id="00929-111">Synchronize contacts directly from Sales to contacts or customers in Supply Chain Management</span></span>](contacts-template-mapping-direct.md)
- [<span data-ttu-id="00929-112">Sincronizar cabeçalhos e linhas da cotação de venda diretamente do Sales para o Supply Chain Management</span><span class="sxs-lookup"><span data-stu-id="00929-112">Synchronize sales quotation headers and lines directly from Sales to Supply Chain Management</span></span>](sales-quotation-template-mapping-sales-fin.md)
- [<span data-ttu-id="00929-113">Sincronização de ordens de venda diretamente entre o Sales e o Supply Chain Management</span><span class="sxs-lookup"><span data-stu-id="00929-113">Synchronization of sales orders directly between Sales and Supply Chain Management</span></span>](sales-order-template-mapping-direct-two-ways.md)
- [<span data-ttu-id="00929-114">Sincronizar cabeçalhos e linhas da fatura de venda diretamente do Supply Chain Management com o Sales</span><span class="sxs-lookup"><span data-stu-id="00929-114">Synchronize sales invoice headers and lines directly from Supply Chain Management to Sales</span></span>](sales-invoice-template-mapping-direct.md)

## <a name="system-requirements-for-supply-chain-management"></a><span data-ttu-id="00929-115">Requisitos de sistema do Supply Chain Management</span><span class="sxs-lookup"><span data-stu-id="00929-115">System requirements for Supply Chain Management</span></span>
<span data-ttu-id="00929-116">A integração Prospect to cash tem suporte nas seguintes versões:</span><span class="sxs-lookup"><span data-stu-id="00929-116">Prospect to cash integration is supported on the following versions:</span></span>

### <a name="microsoft-dynamics-365-for-finance-and-operations-enterprise-edition-73-december-2017"></a><span data-ttu-id="00929-117">Microsoft Dynamics 365 for Finance and Operations, Enterprise edition 7.3 (dezembro de 2017).</span><span class="sxs-lookup"><span data-stu-id="00929-117">Microsoft Dynamics 365 for Finance and Operations, Enterprise edition 7.3 (December 2017)</span></span>

- <span data-ttu-id="00929-118">Dynamics 365 for Finance and Operations, Enterprise edition (dezembro de 2017) - compilação do aplicativo 7.3.11971.56116 com atualização de plataforma 12 (7.0.4709.41129)</span><span class="sxs-lookup"><span data-stu-id="00929-118">Dynamics 365 for Finance and Operations, Enterprise edition (December 2017) - Application build 7.3.11971.56116 with Platform Update 12 (7.0.4709.41129)</span></span>

### <a name="dynamics-365-for-finance-and-operations-enterprise-edition-july-2017"></a><span data-ttu-id="00929-119">Dynamics 365 for Finance and Operations, Enterprise edition (julho de 2017)</span><span class="sxs-lookup"><span data-stu-id="00929-119">Dynamics 365 for Finance and Operations, Enterprise edition (July 2017)</span></span>

- <span data-ttu-id="00929-120">Dynamics 365 for Finance and Operations, Enterprise edition (julho de 2017) - com atualização de plataforma 8 (compilação do aplicativo 7.2.11792.56024 com compilação de plataforma 7.0.4565.16212).</span><span class="sxs-lookup"><span data-stu-id="00929-120">Dynamics 365 for Finance and Operations, Enterprise edition (July 2017) - with platform update 8 (application build 7.2.11792.56024 with platform build 7.0.4565.16212).</span></span>
- <span data-ttu-id="00929-121">Os seguintes hotfixes são necessários:</span><span class="sxs-lookup"><span data-stu-id="00929-121">The following hotfixes are required:</span></span>

  - <span data-ttu-id="00929-122">**[KB4045570](https://fix.lcs.dynamics.com/Issue/Resolved?kb=4045570&bugId=3851320&qc=ac1145034fd04ab71ccc4d14aa012f245176712c9af7c36bb77a118726d46160)** – Esse hotfix permite a sincronização da ordem de venda do Sales para o Supply Chain Management por meio do recurso Integração de Dados.</span><span class="sxs-lookup"><span data-stu-id="00929-122">**[KB4045570](https://fix.lcs.dynamics.com/Issue/Resolved?kb=4045570&bugId=3851320&qc=ac1145034fd04ab71ccc4d14aa012f245176712c9af7c36bb77a118726d46160)** – This hotfix enables sales order synchronization from Sales to Supply Chain Management via the Data Integration feature.</span></span> <span data-ttu-id="00929-123">Também fornece diversos outros aprimoramentos.</span><span class="sxs-lookup"><span data-stu-id="00929-123">It also provides several other enhancements.</span></span>
  - <span data-ttu-id="00929-124">**[KB4036524](https://fix.lcs.dynamics.com/Issue/Resolved?kb=4036524&bugId=3847504&qc=e2fcfae08b1a5d5ce9f53f330e8c212b0636c375368ff7d8d9b5ec6701523ad2)** – Esse hotfix permite a sincronização da linha da ordem de venda do Supply Chain Management para o Sales por meio do recurso Integração de Dados.</span><span class="sxs-lookup"><span data-stu-id="00929-124">**[KB4036524](https://fix.lcs.dynamics.com/Issue/Resolved?kb=4036524&bugId=3847504&qc=e2fcfae08b1a5d5ce9f53f330e8c212b0636c375368ff7d8d9b5ec6701523ad2)** – This hotfix enables sales order line synchronization from Supply Chain Management to Sales via the Data Integration feature.</span></span>
  - <span data-ttu-id="00929-125">**[KB4036461](https://fix.lcs.dynamics.com/Issue/Resolved?kb=4036461&bugId=3847029&qc=e2fcfae08b1a5d5ce9f53f330e8c212b0636c375368ff7d8d9b5ec6701523ad2)** – Esse hotfix permite a sincronização da ordem de venda do Supply Chain Management para o Sales por meio do recurso Integração de Dados.</span><span class="sxs-lookup"><span data-stu-id="00929-125">**[KB4036461](https://fix.lcs.dynamics.com/Issue/Resolved?kb=4036461&bugId=3847029&qc=e2fcfae08b1a5d5ce9f53f330e8c212b0636c375368ff7d8d9b5ec6701523ad2)** – This hotfix enables sales order synchronization from Supply Chain Management to Sales via the Data Integration feature.</span></span>

    > [!NOTE]
    > <span data-ttu-id="00929-126">Basta instalar o KB4045570, pois a instalação inclui as alterações dos outros hotfixes.</span><span class="sxs-lookup"><span data-stu-id="00929-126">You only have to install KB4045570 because the installation includes the changes from other hotfixes.</span></span> 

### <a name="dynamics-365-for-finance-and-operations-version-1611-november-2016"></a><span data-ttu-id="00929-127">Dynamics 365 for Finance and Operations versão 1611 (novembro de 2016)</span><span class="sxs-lookup"><span data-stu-id="00929-127">Dynamics 365 for Finance and Operations version 1611 (November 2016)</span></span>

- <span data-ttu-id="00929-128">Dynamics 365 for Finance and Operations versão 1611 (novembro de 2016) com atualização da plataforma 8 ou superior</span><span class="sxs-lookup"><span data-stu-id="00929-128">Dynamics 365 for Finance and Operations version 1611 (November 2016)  with platform update 8 or higher</span></span>

- <span data-ttu-id="00929-129">Os seguintes hotfixes são necessários:</span><span class="sxs-lookup"><span data-stu-id="00929-129">The following hotfixes are required:</span></span>

  - <span data-ttu-id="00929-130">**[KB4051266](https://fix.lcs.dynamics.com/Issue/Resolved?kb=4051266&bugId=3863566&qc=ee80faaa7bc6c77b368d5eaf456c9c08e0b9fba5903a7b6fd8c13756c3a4b757)** – Permite a sincronização da ordem de venda com o Integrador de dados do Supply Chain Management com o Sales.</span><span class="sxs-lookup"><span data-stu-id="00929-130">**[KB4051266](https://fix.lcs.dynamics.com/Issue/Resolved?kb=4051266&bugId=3863566&qc=ee80faaa7bc6c77b368d5eaf456c9c08e0b9fba5903a7b6fd8c13756c3a4b757)** - Enable sales order synchronization with Data integrator from Supply Chain Management to Sales.</span></span> 
  - <span data-ttu-id="00929-131">**[KB4037542](https://fix.lcs.dynamics.com/Issue/Resolved?kb=4037542&bugId=3848253&qc=8323b93c15280172c5ab4159e0256e37104ced1729462c91ab2f7d00cb8d419c)** – Permite a sincronização do cabeçalho e da linha da ordem de venda com o Integrador de dados do Supply Chain Management com o Sales.</span><span class="sxs-lookup"><span data-stu-id="00929-131">**[KB4037542](https://fix.lcs.dynamics.com/Issue/Resolved?kb=4037542&bugId=3848253&qc=8323b93c15280172c5ab4159e0256e37104ced1729462c91ab2f7d00cb8d419c)** - Enable sales order header and line synchronization with Data integrator from Supply Chain Management to Sales.</span></span>
  - <span data-ttu-id="00929-132">**[KB4033093](https://fix.lcs.dynamics.com/Issue/Resolved?kb=4033093&bugId=3824604&qc=bd7e15e1fb56066b3a82ce48b691cf1ffbc934a7473fa888545b2211a8d416c5)** - É necessário o suporte para integração de prospect to cash através de entidades de dados.</span><span class="sxs-lookup"><span data-stu-id="00929-132">**[KB4033093](https://fix.lcs.dynamics.com/Issue/Resolved?kb=4033093&bugId=3824604&qc=bd7e15e1fb56066b3a82ce48b691cf1ffbc934a7473fa888545b2211a8d416c5)** - Support for prospect to cash integration through data entities is required.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="00929-133">Após a instalação dos hotfixes, você deve disparar o seguinte trabalho em lotes do formulário **SalesPopulateProspectToCash**.</span><span class="sxs-lookup"><span data-stu-id="00929-133">After you install the hotfixes, you must trigger the following batch job from the **SalesPopulateProspectToCash** form.</span></span> <span data-ttu-id="00929-134">Este formulário fica oculto, pois você só precisa dele uma vez.</span><span class="sxs-lookup"><span data-stu-id="00929-134">This form is hidden because you only need it once.</span></span> <span data-ttu-id="00929-135">Para acessar o formulário, faça logon no ambiente e adicione o seguinte ao URL no endereço do navegador: *&mi=action:SalesPopulateProspectToCash*, por exemplo, `https://ax123456.cloud.test.dynamics.com/?cmp=USMF&mi=action:SalesPopulateProspectToCash`.</span><span class="sxs-lookup"><span data-stu-id="00929-135">To access the form, log in to the environment and add the following to the URL in your browser address: *&mi=action:SalesPopulateProspectToCash*, for example, `https://ax123456.cloud.test.dynamics.com/?cmp=USMF&mi=action:SalesPopulateProspectToCash`.</span></span> <span data-ttu-id="00929-136">Ao abrir o formulário, clique em OK.</span><span class="sxs-lookup"><span data-stu-id="00929-136">When the form opens, click OK.</span></span> <span data-ttu-id="00929-137">Será preenchido um novo campo **LineCreationSequnceNumber** nas tabelas **SalesLine**, **SalesQuotationLine** e **CustInvoiceTrans** com valores exclusivos e a lista de produtos será atualizada.</span><span class="sxs-lookup"><span data-stu-id="00929-137">This will populate a new **LineCreationSequnceNumber** field in the **SalesLine**, **SalesQuotationLine**, and **CustInvoiceTrans** tables with unique values, and the product list will be refreshed.</span></span> <span data-ttu-id="00929-138">Isso é necessário para que a integração do Prospect to cash funcione.</span><span class="sxs-lookup"><span data-stu-id="00929-138">This is required for the Prospect to cash integration to work.</span></span>


## <a name="system-requirements-for-sales"></a><span data-ttu-id="00929-139">Requisitos do sistema para Sales</span><span class="sxs-lookup"><span data-stu-id="00929-139">System requirements for Sales</span></span>

<span data-ttu-id="00929-140">Para usar a solução Prospect to cash, instale os seguintes componentes:</span><span class="sxs-lookup"><span data-stu-id="00929-140">To use the Prospect to cash solution, you must install the following components:</span></span>

- <span data-ttu-id="00929-141">Dynamics 365 Sales versão 1612 (8.2.1.207) (DB 8.2.1.207) online ou uma versão posterior</span><span class="sxs-lookup"><span data-stu-id="00929-141">Dynamics 365 Sales version 1612 (8.2.1.207) (DB 8.2.1.207) online or a later version</span></span>
- <span data-ttu-id="00929-142">Solução Prospect to cash para Dynamics 365 Sales, versão 1.15.0.0 ou uma versão posterior.</span><span class="sxs-lookup"><span data-stu-id="00929-142">Prospect to cash solution for Dynamics 365 Sales, version 1.15.0.0 or a later version.</span></span> <span data-ttu-id="00929-143">A solução está disponível para download no AppSource.</span><span class="sxs-lookup"><span data-stu-id="00929-143">The solution is available for download from AppSource.</span></span> <span data-ttu-id="00929-144">[Download do Dynamics 365, Prospect to Cash](https://appsource.microsoft.com/product/dynamics-365/mscrm.c7a48b40-eed3-4d67-93ba-f2364281feb3).</span><span class="sxs-lookup"><span data-stu-id="00929-144">[Download Dynamics 365, Prospect to Cash](https://appsource.microsoft.com/product/dynamics-365/mscrm.c7a48b40-eed3-4d67-93ba-f2364281feb3).</span></span>
