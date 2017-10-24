---
title: Prospect to cash
description: "O tópico fornece uma visão geral da solução Prospect to cash entre o Dynamics 365 for Finance and Operations, Enterprise Edition e o Dynamics 365 for Sales."
author: ChristianRytt
manager: AnnBe
ms.date: 08/28/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: 
audience: Application User, IT Pro
ms.reviewer: yuyus
ms.search.scope: Core, Operations, UnifiedOperations
ms.custom: 
ms.assetid: 
ms.search.region: global
ms.search.industry: 
ms.author: crytt
ms.dyn365.ops.intro: July 2017 update
ms.search.validFrom: 2017-07-8
ms.translationtype: HT
ms.sourcegitcommit: 47e70cb1291e390b42b7feff844b2aca141f09b7
ms.openlocfilehash: a5f1ecd5f8b46287839439a963e571531ae161a7
ms.contentlocale: pt-br
ms.lasthandoff: 09/29/2017

---

# <a name="prospect-to-cash"></a><span data-ttu-id="55e30-103">Prospect to cash</span><span class="sxs-lookup"><span data-stu-id="55e30-103">Prospect to cash</span></span>  

[!include[banner](../includes/banner.md)]

<span data-ttu-id="55e30-104">A solução Prospect to cash solution usa a [Integração de dados](/common-data-service/entity-reference/dynamics-365-integration) para sincronizar dados entre as instâncias do Microsoft Dynamics 365 for Finance and Operations, Enterprise Edition e do Dynamics 365 for Sales por meio do Common Data Service (CDS).</span><span class="sxs-lookup"><span data-stu-id="55e30-104">The Prospect to cash solution uses [Data Integration](/common-data-service/entity-reference/dynamics-365-integration) to synchronize data across Microsoft Dynamics 365 for Finance and Operations, Enterprise edition and Dynamics 365 for Sales instances via the Common Data Service (CDS).</span></span> <span data-ttu-id="55e30-105">Os modelos do Prospect to cash disponíveis com o recurso Integração de dados permitem o fluxo de contas, contatos, produtos, cotações de vendas, ordens de venda e dados das faturas de vendas entre o Finance and Operations e o Sales.</span><span class="sxs-lookup"><span data-stu-id="55e30-105">The Prospect to cash templates available with the Data Integration feature enable the flow of accounts, contacts, products, sales quotes, sales orders, and sales invoices data between Finance and Operations and Sales.</span></span> <span data-ttu-id="55e30-106">Apesar de os dados estarem fluindo entre o Finance and Operations e o Sales, você pode executar atividades de vendas e de marketing no Sales e tratar o atendimento da ordem com o gerenciamento de estoque no Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="55e30-106">While the data is flowing between Finance and Operations and Sales, you can carry out sales and marketing activities in Sales and handle the order fulfillment with inventory management in Finance and Operations.</span></span> 

<span data-ttu-id="55e30-107">Esta solução oferece integração nas seguintes áreas:</span><span class="sxs-lookup"><span data-stu-id="55e30-107">This solution provides integration in the following areas:</span></span> 

-   [<span data-ttu-id="55e30-108">Manter contas no Sales e sincronizá-las para o Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="55e30-108">Maintain accounts in Sales and sync them to Finance and Operations</span></span>](accounts-template-mapping.md)
-   [<span data-ttu-id="55e30-109">Manter contatos no Sales e sincronizá-los para o Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="55e30-109">Maintain contacts in Sales and sync them to Finance and Operations</span></span>](contacts-template-mapping.md)
-   [<span data-ttu-id="55e30-110">Manter produtos no Finance and Operations e sincronizá-los para o Sales.</span><span class="sxs-lookup"><span data-stu-id="55e30-110">Maintain products in Finance and Operations and sync them to Sales</span></span>](products-template-mapping.md)
-   [<span data-ttu-id="55e30-111">Criar cotações de vendas no Sales e sincronizá-las para o Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="55e30-111">Create sales quotes in Sales and sync them to Finance and Operations</span></span>](sales-quotation-template-mapping.md)
-   [<span data-ttu-id="55e30-112">Criar ordens de venda no Finance and Operations e sincronizá-las para o Sales.</span><span class="sxs-lookup"><span data-stu-id="55e30-112">Create sales orders in Finance and Operations and sync them to Sales</span></span>](sales-order-template-mapping.md)
-   [<span data-ttu-id="55e30-113">Criar faturas de venda no Finance and Operations e sincronizá-las com o Sales.</span><span class="sxs-lookup"><span data-stu-id="55e30-113">Create sales invoices in Finance and Operations and sync them to Sales</span></span>](sales-invoice-template-mapping.md)

## <a name="system-requirements-for-dynamics-365-for-finance-and-operations-enterprise-edition"></a><span data-ttu-id="55e30-114">Requisitos do sistema para o Dynamics 365 for Finance and Operations, Enterprise Edition</span><span class="sxs-lookup"><span data-stu-id="55e30-114">System requirements for Dynamics 365 for Finance and Operations, Enterprise edition</span></span>

<span data-ttu-id="55e30-115">Para usar a solução Prospect to cash, instale o seguinte:</span><span class="sxs-lookup"><span data-stu-id="55e30-115">To use the Prospect to cash solution, you must install the following:</span></span>

- <span data-ttu-id="55e30-116">Microsoft Dynamics 365 for Finance and Operations, Enterprise Edition (julho de 2017) com atualização da Plataforma 8 (App 7.2.11792.56024 com Plataforma 7.0.4565.16212)</span><span class="sxs-lookup"><span data-stu-id="55e30-116">Microsoft Dynamics 365 for Finance and Operations, Enterprise edition (July 2017) with Platform update 8 (App 7.2.11792.56024 w/ Platform 7.0.4565.16212)</span></span>

- <span data-ttu-id="55e30-117">Dois hotfixes para Dynamics 365 for Finance and Operations, Enterprise Edition (julho de 2017).</span><span class="sxs-lookup"><span data-stu-id="55e30-117">Two hotfixes for Dynamics 365 for Finance and Operations, Enterprise edition (July 2017).</span></span>

    -  <span data-ttu-id="55e30-118">[KB4036524](https://fix.lcs.dynamics.com/Issue/Resolved?kb=4036524&bugId=3847504&qc=e2fcfae08b1a5d5ce9f53f330e8c212b0636c375368ff7d8d9b5ec6701523ad2) - Este hotfix permite sincronização da linha da ordem de venda com o recurso de Integração de dados do Finance and Operations com o Sales.</span><span class="sxs-lookup"><span data-stu-id="55e30-118">[KB4036524](https://fix.lcs.dynamics.com/Issue/Resolved?kb=4036524&bugId=3847504&qc=e2fcfae08b1a5d5ce9f53f330e8c212b0636c375368ff7d8d9b5ec6701523ad2) - This hotfix enables sales order line synchronization with the Data Integration feature from Finance and Operations to Sales.</span></span>
        
    -  <span data-ttu-id="55e30-119">[KB4036461](https://fix.lcs.dynamics.com/Issue/Resolved?kb=4036461&bugId=3847029&qc=e2fcfae08b1a5d5ce9f53f330e8c212b0636c375368ff7d8d9b5ec6701523ad2) - Este hotfix permite a sincronização da ordem de venda com o recurso de Integração de dados do Finance and Operations com o Sales.</span><span class="sxs-lookup"><span data-stu-id="55e30-119">[KB4036461](https://fix.lcs.dynamics.com/Issue/Resolved?kb=4036461&bugId=3847029&qc=e2fcfae08b1a5d5ce9f53f330e8c212b0636c375368ff7d8d9b5ec6701523ad2) - This hotfix enables sales order synchronization with the Data Integration feature from Finance and Operations to Sales.</span></span>
    
<span data-ttu-id="55e30-120">**Nota**: Somente é necessário instalar o KB4036524 porque a instalação inclui as alterações do KB4036461.</span><span class="sxs-lookup"><span data-stu-id="55e30-120">**Note**: You only need to install KB4036524 because the installation includes the changes from KB4036461.</span></span>
 
## <a name="system-requirements-for-dynamics-365-for-sales"></a><span data-ttu-id="55e30-121">Requisitos do sistema do Dynamics 365 for Sales</span><span class="sxs-lookup"><span data-stu-id="55e30-121">System requirements for Dynamics 365 for Sales</span></span>

<span data-ttu-id="55e30-122">Para usar a solução Prospect to cash, instale o seguinte:</span><span class="sxs-lookup"><span data-stu-id="55e30-122">To use the Prospect to cash solution, you must install the following:</span></span>

- <span data-ttu-id="55e30-123">Versão 1612 (8.2.1.207) (DB 8.2.1.207) on-line ou posterior do Dynamics 365 for Sales.</span><span class="sxs-lookup"><span data-stu-id="55e30-123">Dynamics 365 for Sales version 1612 (8.2.1.207) (DB 8.2.1.207) online or later.</span></span>
- <span data-ttu-id="55e30-124">Solução Prospect to cash para Dynamics 365 for Sales, versão 1.14.0.0 (v14) ou posterior.</span><span class="sxs-lookup"><span data-stu-id="55e30-124">Prospect to cash solution for Dynamics 365 for Sales, version 1.14.0.0 (v14) or later.</span></span>

### <a name="install-the-prospect-to-cash-solution-for-sales"></a><span data-ttu-id="55e30-125">Instale a solução Prospect to cash para Sales</span><span class="sxs-lookup"><span data-stu-id="55e30-125">Install the Prospect to cash solution for Sales</span></span>

- <span data-ttu-id="55e30-126">Baixe o [arquivo zip do pacote da solução Prospect to cash para Dynamics 365 for Sales](https://mbs.microsoft.com/customersource/Global/365Enterprise/downloads/product-releases/MD365FNOPENTProspectToCash) no CustomerSource.</span><span class="sxs-lookup"><span data-stu-id="55e30-126">Download the [Prospect to cash for Dynamics 365 for Sales solution package zip file](https://mbs.microsoft.com/customersource/Global/365Enterprise/downloads/product-releases/MD365FNOPENTProspectToCash) on CustomerSource.</span></span>

- <span data-ttu-id="55e30-127">Verifique se o arquivo zip está desbloqueado, para não receber a mensagem de erro “Nenhum pacote de importação foi encontrado” ao instalar o pacote da solução.</span><span class="sxs-lookup"><span data-stu-id="55e30-127">Make sure that the zip file is unblocked so that you do not get the error message "No import packages were found" when you install the solution package.</span></span> <span data-ttu-id="55e30-128">Para desbloquear o arquivo, faça o seguinte:</span><span class="sxs-lookup"><span data-stu-id="55e30-128">To unblock the file, do the following:</span></span>

    -  <span data-ttu-id="55e30-129">Clique com o botão direito no arquivo zip.</span><span class="sxs-lookup"><span data-stu-id="55e30-129">Right-click the zip file.</span></span>
    -  <span data-ttu-id="55e30-130">Selecione **Propriedades** e **Desbloquear**.</span><span class="sxs-lookup"><span data-stu-id="55e30-130">Select **Properties** and then select **Unblock**.</span></span> 

- <span data-ttu-id="55e30-131">Descompacte e execute o arquivo PackageDeployer.exe.</span><span class="sxs-lookup"><span data-stu-id="55e30-131">Unzip and run PackageDeployer.exe.</span></span>

- <span data-ttu-id="55e30-132">Instale a solução Prospect to cash em sua instância do Sales.</span><span class="sxs-lookup"><span data-stu-id="55e30-132">Install the Prospect to Cash solution in your Sales instance.</span></span>

    - <span data-ttu-id="55e30-133">Selecione o tipo de implantação **Office 365**.</span><span class="sxs-lookup"><span data-stu-id="55e30-133">Select the **Office 365** Deployment type.</span></span>
    - <span data-ttu-id="55e30-134">Selecione **Mostrar avançada**.</span><span class="sxs-lookup"><span data-stu-id="55e30-134">Select **Show advanced**.</span></span>
    - <span data-ttu-id="55e30-135">Para uma instalação rápida, selecione uma **Região**.</span><span class="sxs-lookup"><span data-stu-id="55e30-135">For a quick installation, select a **Region**.</span></span> <span data-ttu-id="55e30-136">Se você selecionar **Não sei**, o sistema pesquisará todas as regiões e demorará para instalar.</span><span class="sxs-lookup"><span data-stu-id="55e30-136">If you select **Don’t know**, the system searches for all regions and it will take longer to install.</span></span>
    - <span data-ttu-id="55e30-137">Informe **Nome do usuário** e **Senha** de um usuário administrador que tem os direitos de usuário para instalar.</span><span class="sxs-lookup"><span data-stu-id="55e30-137">Enter **User name** and **Password** for an admin user who has the user rights to install.</span></span>

