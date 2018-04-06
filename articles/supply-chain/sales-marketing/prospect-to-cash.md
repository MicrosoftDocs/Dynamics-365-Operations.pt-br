---
title: Prospect to cash
description: "Este tópico fornece uma visão geral da solução Prospect to cash entre o Microsoft Dynamics 365 for Finance and Operations e o Microsoft Dynamics 365 for Sales."
author: ChristianRytt
manager: AnnBe
ms.date: 02/08/2018
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: CustTable, SalesTable, EcoResProductListPage
audience: Application User, IT Pro
ms.reviewer: yuyus
ms.search.scope: Core, Operations
ms.custom: 
ms.assetid: 
ms.search.region: global
ms.search.industry: 
ms.author: crytt
ms.dyn365.ops.version: July 2017 update
ms.search.validFrom: 2017-07-8
ms.translationtype: HT
ms.sourcegitcommit: a0739304723d19b910388893d08e8c36a1f49d13
ms.openlocfilehash: 025be8b44726194e6fc219816c40d2a15a7349df
ms.contentlocale: pt-br
ms.lasthandoff: 03/26/2018

---

# <a name="prospect-to-cash"></a><span data-ttu-id="8afc0-103">Prospect to cash</span><span class="sxs-lookup"><span data-stu-id="8afc0-103">Prospect to cash</span></span>

[!include[banner](../includes/banner.md)]

<span data-ttu-id="8afc0-104">A solução Prospect to cash fornece sincronização direta entre o Dynamics 365 for Finance and Operations e o Dynamics 365 for Sales.</span><span class="sxs-lookup"><span data-stu-id="8afc0-104">The Prospect to cash solution provides direct synchronization across Dynamics 365 for Finance and Operations, and Dynamics 365 for Sales.</span></span> <span data-ttu-id="8afc0-105">Os modelos Prospect to cash que estão disponíveis com o recurso Integração de Dados permitem o fluxo de dados para contas, contatos, produtos, cotações de vendas, ordens de venda e faturas de vendas entre o Finance and Operations e o Sales.</span><span class="sxs-lookup"><span data-stu-id="8afc0-105">The Prospect to cash templates that are available with the Data Integration feature enable the flow of data for accounts, contacts, products, sales quotations, sales orders, and sales invoices between Finance and Operations and Sales.</span></span> <span data-ttu-id="8afc0-106">Apesar de os dados estarem fluindo entre o Finance and Operations e o Sales, você pode executar atividades de vendas e de marketing no Sales e pode tratar o atendimento da ordem usando o gerenciamento de estoque no Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="8afc0-106">While data is flowing between Finance and Operations and Sales, you can perform sales and marketing activities in Sales, and you can handle order fulfillment by using inventory management in Finance and Operations.</span></span> 

<span data-ttu-id="8afc0-107">Para obter mais informações sobre a integração Prospect to cash, assista ao vídeo curto no YouTube:</span><span class="sxs-lookup"><span data-stu-id="8afc0-107">For more information about the Prospect to cash integration, watch the short YouTube video:</span></span>

> [!Video https://www.youtube.com/embed/AVV9x5x-XCg]

<span data-ttu-id="8afc0-108">Na versão atual, a solução Prospect to cash fornece os seguintes tipos de sincronização direta:</span><span class="sxs-lookup"><span data-stu-id="8afc0-108">In the current version, the Prospect to cash solution provides the following types of direct synchronization:</span></span>

- [<span data-ttu-id="8afc0-109">Manter contas no Sales e sincronizá-las diretamente do Sales para o Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="8afc0-109">Maintain accounts in Sales and sync them directly from Sales to Finance and Operations</span></span>](accounts-template-mapping-direct.md)
- [<span data-ttu-id="8afc0-110">Manter produtos no Finance and Operations e sincronizá-los diretamente para o Sales</span><span class="sxs-lookup"><span data-stu-id="8afc0-110">Maintain products in Finance and Operations and sync them directly to Sales</span></span>](products-template-mapping-direct.md)
- [<span data-ttu-id="8afc0-111">Manter contatos no Sales e sincronizá-los diretamente para contatos ou clientes do Finance and Operations</span><span class="sxs-lookup"><span data-stu-id="8afc0-111">Maintain contacts in Sales and sync them directly to contacts or customers in Finance and Operations</span></span>](contacts-template-mapping-direct.md)
- [<span data-ttu-id="8afc0-112">Sincronizar cotação de venda diretamente do Sales para o Finance and Operations</span><span class="sxs-lookup"><span data-stu-id="8afc0-112">Synchronize sales quotation directly from Sales to Finance and Operations</span></span>](sales-quotation-template-mapping-sales-fin.md)
- [<span data-ttu-id="8afc0-113">Sincronizar ordens de venda diretamente entre o Sales e o Finance and Operations</span><span class="sxs-lookup"><span data-stu-id="8afc0-113">Synchronize sales orders directly between Sales and Finance and Operations</span></span>](sales-order-template-mapping-direct-two-ways.md)
- [<span data-ttu-id="8afc0-114">Sincronizar fatura de venda diretamente do Finance and Operations para o Sales</span><span class="sxs-lookup"><span data-stu-id="8afc0-114">Synchronize sales invoice directly from Finance and Operations to Sales</span></span>](sales-invoice-template-mapping-direct.md)

## <a name="system-requirements-for-finance-and-operations"></a><span data-ttu-id="8afc0-115">Requisitos de sistema para Finance and Operations</span><span class="sxs-lookup"><span data-stu-id="8afc0-115">System requirements for Finance and Operations</span></span>

<span data-ttu-id="8afc0-116">A integração Prospect to cash tem suporte nas seguintes versões:</span><span class="sxs-lookup"><span data-stu-id="8afc0-116">Prospect to cash integration is supported on the following versions:</span></span>

### <a name="microsoft-dynamics-365-for-finance-and-operations-enterprise-edition-73-december-2017"></a><span data-ttu-id="8afc0-117">Microsoft Dynamics 365 for Finance and Operations, Enterprise Edition 7.3 (dezembro de 2017)</span><span class="sxs-lookup"><span data-stu-id="8afc0-117">Microsoft Dynamics 365 for Finance and Operations, Enterprise edition 7.3 (December 2017)</span></span>

- <span data-ttu-id="8afc0-118">Dynamics 365 for Finance and Operations, Enterprise Edition (dezembro de 2017) - compilação do aplicativo 7.3.11971.56116 com atualização de plataforma 12 (7.0.4709.41129)</span><span class="sxs-lookup"><span data-stu-id="8afc0-118">Dynamics 365 for Finance and Operations, Enterprise edition (December 2017) - Application build 7.3.11971.56116 with Platform Update 12 (7.0.4709.41129)</span></span>

### <a name="dynamics-365-for-finance-and-operations-enterprise-edition-july-2017"></a><span data-ttu-id="8afc0-119">Dynamics 365 for Finance and Operations, Enterprise Edition (Julho de 2017)</span><span class="sxs-lookup"><span data-stu-id="8afc0-119">Dynamics 365 for Finance and Operations, Enterprise edition (July 2017)</span></span>

- <span data-ttu-id="8afc0-120">Dynamics 365 for Finance and Operations, Enterprise Edition (julho de 2017) - com atualização de plataforma 8 (compilação do aplicativo 7.2.11792.56024 com compilação de plataforma 7.0.4565.16212).</span><span class="sxs-lookup"><span data-stu-id="8afc0-120">Dynamics 365 for Finance and Operations, Enterprise edition (July 2017) - with platform update 8 (application build 7.2.11792.56024 with platform build 7.0.4565.16212).</span></span>
- <span data-ttu-id="8afc0-121">Os seguintes hotfixes são necessários:</span><span class="sxs-lookup"><span data-stu-id="8afc0-121">The following hotfixes are required:</span></span>

    - <span data-ttu-id="8afc0-122">**[KB4045570](https://fix.lcs.dynamics.com/Issue/Resolved?kb=4045570&bugId=3851320&qc=ac1145034fd04ab71ccc4d14aa012f245176712c9af7c36bb77a118726d46160)** – Este hotfix permite a sincronização da ordem de venda do Sales para o Finance and Operations através do recurso de Integração de dados.</span><span class="sxs-lookup"><span data-stu-id="8afc0-122">**[KB4045570](https://fix.lcs.dynamics.com/Issue/Resolved?kb=4045570&bugId=3851320&qc=ac1145034fd04ab71ccc4d14aa012f245176712c9af7c36bb77a118726d46160)** – This hotfix enables sales order synchronization from Sales to Finance and Operations via the Data Integration feature.</span></span> <span data-ttu-id="8afc0-123">Também fornece diversos outros aprimoramentos.</span><span class="sxs-lookup"><span data-stu-id="8afc0-123">It also provides several other enhancements.</span></span>
    - <span data-ttu-id="8afc0-124">**[KB4036524](https://fix.lcs.dynamics.com/Issue/Resolved?kb=4036524&bugId=3847504&qc=e2fcfae08b1a5d5ce9f53f330e8c212b0636c375368ff7d8d9b5ec6701523ad2)** – Este hotfix permite a sincronização da linha da ordem de venda do Finance and Operations para o Sales através do recurso de Integração de dados.</span><span class="sxs-lookup"><span data-stu-id="8afc0-124">**[KB4036524](https://fix.lcs.dynamics.com/Issue/Resolved?kb=4036524&bugId=3847504&qc=e2fcfae08b1a5d5ce9f53f330e8c212b0636c375368ff7d8d9b5ec6701523ad2)** – This hotfix enables sales order line synchronization from Finance and Operations to Sales via the Data Integration feature.</span></span>
    - <span data-ttu-id="8afc0-125">**[KB4036461](https://fix.lcs.dynamics.com/Issue/Resolved?kb=4036461&bugId=3847029&qc=e2fcfae08b1a5d5ce9f53f330e8c212b0636c375368ff7d8d9b5ec6701523ad2)** – Este hotfix permite a sincronização da ordem de venda do Finance and Operations para o Sales através do recurso de Integração de dados.</span><span class="sxs-lookup"><span data-stu-id="8afc0-125">**[KB4036461](https://fix.lcs.dynamics.com/Issue/Resolved?kb=4036461&bugId=3847029&qc=e2fcfae08b1a5d5ce9f53f330e8c212b0636c375368ff7d8d9b5ec6701523ad2)** – This hotfix enables sales order synchronization from Finance and Operations to Sales via the Data Integration feature.</span></span>

    > [!NOTE]
    > <span data-ttu-id="8afc0-126">Basta instalar o KB4045570, pois a instalação inclui as alterações dos outros hotfixes.</span><span class="sxs-lookup"><span data-stu-id="8afc0-126">You only have to install KB4045570 because the installation includes the changes from other hotfixes.</span></span> 

### <a name="dynamics-365-for-finance-and-operations-version-1611-november-2016"></a><span data-ttu-id="8afc0-127">Versão 1611 do Dynamics 365 for Finance and Operations (Novembro de 2016)</span><span class="sxs-lookup"><span data-stu-id="8afc0-127">Dynamics 365 for Finance and Operations version 1611 (November 2016)</span></span>

- <span data-ttu-id="8afc0-128">Versão 1611 (Novembro de 2016) do Dynamics 365 for Finance and Operations com atualização da plataforma 8 ou superior</span><span class="sxs-lookup"><span data-stu-id="8afc0-128">Dynamics 365 for Finance and Operations version 1611 (November 2016)  with platform update 8 or higher</span></span>

- <span data-ttu-id="8afc0-129">Os seguintes hotfixes são necessários:</span><span class="sxs-lookup"><span data-stu-id="8afc0-129">The following hotfixes are required:</span></span>

    - <span data-ttu-id="8afc0-130">**[KB4051266](https://fix.lcs.dynamics.com/Issue/Resolved?kb=4051266&bugId=3863566&qc=ee80faaa7bc6c77b368d5eaf456c9c08e0b9fba5903a7b6fd8c13756c3a4b757)** - Permite a sincronização da ordem de venda com o Integrador de dados do Finance and Operations para o Sales.</span><span class="sxs-lookup"><span data-stu-id="8afc0-130">**[KB4051266](https://fix.lcs.dynamics.com/Issue/Resolved?kb=4051266&bugId=3863566&qc=ee80faaa7bc6c77b368d5eaf456c9c08e0b9fba5903a7b6fd8c13756c3a4b757)** - Enable sales order synchronization with Data integrator from Finance and Operations to Sales.</span></span> 
    - <span data-ttu-id="8afc0-131">**[KB4037542](https://fix.lcs.dynamics.com/Issue/Resolved?kb=4037542&bugId=3848253&qc=8323b93c15280172c5ab4159e0256e37104ced1729462c91ab2f7d00cb8d419c)** - Permite a sincronização da linha e do cabeçalho da ordem de venda com o Integrador de dados do Finance and Operations para o Sales.</span><span class="sxs-lookup"><span data-stu-id="8afc0-131">**[KB4037542](https://fix.lcs.dynamics.com/Issue/Resolved?kb=4037542&bugId=3848253&qc=8323b93c15280172c5ab4159e0256e37104ced1729462c91ab2f7d00cb8d419c)** - Enable sales order header and line synchronization with Data integrator from Finance and Operations to Sales.</span></span>
    - <span data-ttu-id="8afc0-132">**[KB4033093](https://fix.lcs.dynamics.com/Issue/Resolved?kb=4033093&bugId=3824604&qc=bd7e15e1fb56066b3a82ce48b691cf1ffbc934a7473fa888545b2211a8d416c5)** - É necessário o suporte para integração de prospect to cash através de entidades de dados.</span><span class="sxs-lookup"><span data-stu-id="8afc0-132">**[KB4033093](https://fix.lcs.dynamics.com/Issue/Resolved?kb=4033093&bugId=3824604&qc=bd7e15e1fb56066b3a82ce48b691cf1ffbc934a7473fa888545b2211a8d416c5)** - Support for prospect to cash integration through data entities is required.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="8afc0-133">Após a instalação dos hotfixes, você deve disparar o seguinte trabalho em lotes do formulário **SalesPopulateProspectToCash**.</span><span class="sxs-lookup"><span data-stu-id="8afc0-133">After you install the hotfixes, you must trigger the following batch job from the **SalesPopulateProspectToCash** form.</span></span> <span data-ttu-id="8afc0-134">Este formulário fica oculto, pois você só precisa dele uma vez.</span><span class="sxs-lookup"><span data-stu-id="8afc0-134">This form is hidden because you only need it once.</span></span> <span data-ttu-id="8afc0-135">Para acessar o formulário, faça logon no ambiente e adicione o seguinte ao URL no endereço do navegador: &mi=action:SalesPopulateProspectToCash, por exemplo, `https://ax123456.cloud.test.dynamics.com/?cmp=USMF&mi=action:SalesPopulateProspectToCash`.</span><span class="sxs-lookup"><span data-stu-id="8afc0-135">To access the form, log in to the environment and add the following to the URL in your browser address: &mi=action:SalesPopulateProspectToCash, for example, `https://ax123456.cloud.test.dynamics.com/?cmp=USMF&mi=action:SalesPopulateProspectToCash`.</span></span> <span data-ttu-id="8afc0-136">Ao abrir o formulário, clique em OK.</span><span class="sxs-lookup"><span data-stu-id="8afc0-136">When the form opens, click OK.</span></span> <span data-ttu-id="8afc0-137">Será preenchido um novo campo **LineCreationSequnceNumber** nas tabelas **SalesLine**, **SalesQuotationLine** e **CustInvoiceTrans** com valores exclusivos e a lista de produtos será atualizada.</span><span class="sxs-lookup"><span data-stu-id="8afc0-137">This will populate a new **LineCreationSequnceNumber** field in the **SalesLine**, **SalesQuotationLine**, and **CustInvoiceTrans** tables with unique values, and the product list will be refreshed.</span></span> <span data-ttu-id="8afc0-138">Isso é necessário para que a integração do Prospect to cash funcione.</span><span class="sxs-lookup"><span data-stu-id="8afc0-138">This is required for the Prospect to cash integration to work.</span></span>


## <a name="system-requirements-for-sales"></a><span data-ttu-id="8afc0-139">Requisitos do sistema para Sales</span><span class="sxs-lookup"><span data-stu-id="8afc0-139">System requirements for Sales</span></span>

<span data-ttu-id="8afc0-140">Para usar a solução Prospect to cash, instale os seguintes componentes:</span><span class="sxs-lookup"><span data-stu-id="8afc0-140">To use the Prospect to cash solution, you must install the following components:</span></span>

- <span data-ttu-id="8afc0-141">Dynamics 365 for Sales versão 1612 (8.2.1.207) (DB 8.2.1.207) online ou uma versão posterior</span><span class="sxs-lookup"><span data-stu-id="8afc0-141">Dynamics 365 for Sales version 1612 (8.2.1.207) (DB 8.2.1.207) online or a later version</span></span>
- <span data-ttu-id="8afc0-142">Solução Prospect to cash para Dynamics 365 for Sales, versão 1.15.0.0 (v15)</span><span class="sxs-lookup"><span data-stu-id="8afc0-142">Prospect to cash solution for Dynamics 365 for Sales, version 1.15.0.0 (v15)</span></span> 

### <a name="install-the-prospect-to-cash-solution-for-sales"></a><span data-ttu-id="8afc0-143">Instale a solução Prospect to cash para Sales</span><span class="sxs-lookup"><span data-stu-id="8afc0-143">Install the Prospect to cash solution for Sales</span></span>

1. <span data-ttu-id="8afc0-144">Baixe o [arquivo zip do pacote da solução Prospect to cash para Dynamics 365 for Sales](https://mbs.microsoft.com/customersource/Global/365Enterprise/downloads/product-releases/MD365FNOPENTProspectToCash) no CustomerSource.</span><span class="sxs-lookup"><span data-stu-id="8afc0-144">Download the [Prospect to cash for Dynamics 365 for Sales solution package zip file](https://mbs.microsoft.com/customersource/Global/365Enterprise/downloads/product-releases/MD365FNOPENTProspectToCash) from CustomerSource.</span></span>
2. <span data-ttu-id="8afc0-145">Verifique se o arquivo zip está desbloqueado.</span><span class="sxs-lookup"><span data-stu-id="8afc0-145">Make sure that the zip file is unblocked.</span></span> <span data-ttu-id="8afc0-146">Se não tiver, ao tentar instalar o pacote de solução, talvez você receba a seguinte mensagem de erro: “Nenhum pacote de importação encontrado."</span><span class="sxs-lookup"><span data-stu-id="8afc0-146">Otherwise, when you try to install the solution package, you may receive the following error message, "No import packages were found."</span></span> <span data-ttu-id="8afc0-147">Para desbloquear o arquivo zip, clique com o botão direito do mouse nele e selecione **Propriedades**.</span><span class="sxs-lookup"><span data-stu-id="8afc0-147">To unblock the zip file, right-click it, and select **Properties**.</span></span> <span data-ttu-id="8afc0-148">Selecione **Desbloquear**.</span><span class="sxs-lookup"><span data-stu-id="8afc0-148">Select **Unblock**.</span></span>
3. <span data-ttu-id="8afc0-149">Descompacte e execute o arquivo **PackageDeployer.exe**.</span><span class="sxs-lookup"><span data-stu-id="8afc0-149">Unzip and run **PackageDeployer.exe**.</span></span>
4. <span data-ttu-id="8afc0-150">Instale a solução Prospect to cash em sua instância do Sales:</span><span class="sxs-lookup"><span data-stu-id="8afc0-150">Install the Prospect to cash solution on your Sales instance:</span></span>

    1. <span data-ttu-id="8afc0-151">Selecione **Office 365** como o tipo de implantação.</span><span class="sxs-lookup"><span data-stu-id="8afc0-151">Select **Office 365** as the deployment type.</span></span>
    2. <span data-ttu-id="8afc0-152">Selecione **Mostrar avançada**.</span><span class="sxs-lookup"><span data-stu-id="8afc0-152">Select **Show advanced**.</span></span>
    3. <span data-ttu-id="8afc0-153">Para uma instalação rápida, selecione uma região.</span><span class="sxs-lookup"><span data-stu-id="8afc0-153">For a quick installation, select a region.</span></span> <span data-ttu-id="8afc0-154">Se você selecionar **Não sei**, o sistema pesquisará todas as regiões e a instalação demorará mais.</span><span class="sxs-lookup"><span data-stu-id="8afc0-154">If you select **Don't know**, the system searches for all regions, and the installation will take more time.</span></span>
    4. <span data-ttu-id="8afc0-155">Informe o nome do usuário e a senha de um usuário administrativo que tem os direitos de instalação.</span><span class="sxs-lookup"><span data-stu-id="8afc0-155">Enter the user name and password of an admin user who has installation rights.</span></span>



