---
title: Importar catálogos do fornecedor
description: Este tópico descreve o processo para importar dados do catálogo do fornecedor.
author: mkirknel
manager: AnnBe
ms.date: 03/20/2018
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: VendProspectiveVendorRegistrationRequests
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations
ms.custom: ''
ms.search.region: Global
ms.search.industry: ''
ms.author: mkirknel
ms.search.validFrom: 2018-04-20
ms.dyn365.ops.version: 7.2999999999999998
ms.openlocfilehash: cf81823de46da9a834f0214896b9e634989cac0e
ms.sourcegitcommit: 9d4c7edd0ae2053c37c7d81cdd180b16bf3a9d3b
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/15/2019
ms.locfileid: "1569767"
---
# <a name="import-vendor-catalogs"></a><span data-ttu-id="36956-103">Importar catálogos do fornecedor</span><span class="sxs-lookup"><span data-stu-id="36956-103">Import vendor catalogs</span></span>
[!include[banner](../includes/banner.md)]

## <a name="vendor-catalogs-import"></a><span data-ttu-id="36956-104">Importação dos catálogos do fornecedor</span><span class="sxs-lookup"><span data-stu-id="36956-104">Vendor catalogs import</span></span>

<span data-ttu-id="36956-105">No Microsoft Dynamics 365 for Finance and Operations, os profissionais de compra podem criar e manter catálogos para os funcionários da empresa usarem ao solicitar itens e serviços para uso interno.</span><span class="sxs-lookup"><span data-stu-id="36956-105">In Microsoft Dynamics 365 for Finance and Operations, purchasing professionals can create and maintain catalogs for company employees to use when they order items and services for internal use.</span></span> <span data-ttu-id="36956-106">Para criar um catálogo de compras, é possível adicionar itens e serviços que você deseja disponibilizar para os funcionários, importando manualmente os dados do catálogo de produtos ou adicionando manualmente os dados do catálogo de produtos até o produto mestre.</span><span class="sxs-lookup"><span data-stu-id="36956-106">To create a procurement catalog, you can add the items and services that you want to make available to employees, either by importing the product catalog data or by manually adding the product catalog data to the product master.</span></span> 

<span data-ttu-id="36956-107">Você pode carregar os dados do catálogo enviados por um fornecedor do cliente do Microsoft Dynamics 365.</span><span class="sxs-lookup"><span data-stu-id="36956-107">You can upload catalog data submitted by a vendor from the Microsoft Dynamics 365 client.</span></span>

<span data-ttu-id="36956-108">Os dados do produto que um fornecedor envia para você, na forma de um arquivo de solicitação de manutenção de catálogo (CMR), devem estar no formato de arquivo XML.</span><span class="sxs-lookup"><span data-stu-id="36956-108">The product data that a vendor submits to you, in the form of a catalog maintenance request (CMR) file, must be in XML file format.</span></span> <span data-ttu-id="36956-109">O arquivo CMR deve conter todos os detalhes dos produtos que o fornecedor abastece na sua empresa.</span><span class="sxs-lookup"><span data-stu-id="36956-109">The CMR file should contain the details for the products that the vendor supplies to your company.</span></span>

## <a name="import-vendor-catalog-data"></a><span data-ttu-id="36956-110">Importar dados do catálogo do fornecedor</span><span class="sxs-lookup"><span data-stu-id="36956-110">Import vendor catalog data</span></span>

<span data-ttu-id="36956-111">Para importar os dados do catálogo do fornecedor, conclua as seguintes tarefas:</span><span class="sxs-lookup"><span data-stu-id="36956-111">To import vendor catalog data, you must complete the following tasks:</span></span>

1.  <span data-ttu-id="36956-112">Configure um projeto no espaço de trabalho de Gerenciamento de dados em que você definiu as regras de mapeamento de dados.</span><span class="sxs-lookup"><span data-stu-id="36956-112">Set up a project in the Data management workspace where you have defined your data mapping rules.</span></span> <span data-ttu-id="36956-113">Selecione **Gerenciamento de dados** e selecione **Configurar funções para projetos de dados**.</span><span class="sxs-lookup"><span data-stu-id="36956-113">Select **Data management** and then select **Set up roles for data projects**.</span></span> 

2.  <span data-ttu-id="36956-114">Configure uma hierarquia de categorias de compras e atribua seus fornecedores às categorias de compras.</span><span class="sxs-lookup"><span data-stu-id="36956-114">Set up a procurement category hierarchy, and assign your vendors to procurement categories.</span></span> <span data-ttu-id="36956-115">Se você usar códigos de mercadoria, adicione os códigos de mercadoria às categorias de compras.</span><span class="sxs-lookup"><span data-stu-id="36956-115">If you use commodity codes, add the commodity codes to the procurement categories.</span></span> <span data-ttu-id="36956-116">Para obter informações sobre como configurar uma hierarquia de categorias de compras, consulte [Configurar uma hierarquia de categorias de compras](../procurement/tasks/set-up-procurement-category-hierarchy.md).</span><span class="sxs-lookup"><span data-stu-id="36956-116">For information about setting up a procurement category hierarchy, see [Set up a procurement category hierarchy](../procurement/tasks/set-up-procurement-category-hierarchy.md).</span></span>

3.  <span data-ttu-id="36956-117">Configurar o fornecedor para importação de catálogo.</span><span class="sxs-lookup"><span data-stu-id="36956-117">Configure the vendor for catalog import.</span></span> <span data-ttu-id="36956-118">Selecione um fornecedor e então selecione **Compras** > **Configurar** > **Configurar o fornecedor para importação de catálogo**.</span><span class="sxs-lookup"><span data-stu-id="36956-118">Select a vendor, and then select **Procurement** > **Set up** > **Configure vendor for catalog import**.</span></span>

4.  <span data-ttu-id="36956-119">Configure o fluxo de trabalho para importação de catálogo.</span><span class="sxs-lookup"><span data-stu-id="36956-119">Configure workflow for catalog import.</span></span> <span data-ttu-id="36956-120">Crie um modelo do arquivo CMR e compartilhe isso com o fornecedor.</span><span class="sxs-lookup"><span data-stu-id="36956-120">Create a CMR file template and share this with your vendor.</span></span>

5.  <span data-ttu-id="36956-121">Selecione **Compras e fornecimento** \> **Comum** \> **Catálogo** \> **Catálogos do fornecedor** para criar um catálogo do fornecedor.</span><span class="sxs-lookup"><span data-stu-id="36956-121">Select **Procurement and sourcing** \> **Common** \> **Catalogs** \> **Vendor catalogs** to create a vendor catalog.</span></span> <span data-ttu-id="36956-122">Os arquivos de solicitação de manutenção de catálogo (CMR) recebidos do fornecedor são agrupados nesse catálogo.</span><span class="sxs-lookup"><span data-stu-id="36956-122">The catalog maintenance request (CMR) files that you receive from your vendor are grouped in this catalog.</span></span> 

6.  <span data-ttu-id="36956-123">Carregue o arquivo CMR.</span><span class="sxs-lookup"><span data-stu-id="36956-123">Upload the CMR file.</span></span>

7.  <span data-ttu-id="36956-124">Revise, aprove ou rejeite os produtos no catálogo do fornecedor.</span><span class="sxs-lookup"><span data-stu-id="36956-124">Review, approve, or reject the products in the vendor catalog.</span></span> <span data-ttu-id="36956-125">Os produtos são mapeados automaticamente para as categorias de compras no Dynamics 365 for Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="36956-125">The products are automatically mapped to the procurement categories in Dynamics 365 for Finance and Operations.</span></span> 
    
<span data-ttu-id="36956-126">Os produtos aprovados são adicionados ao produto mestre e liberados para as entidades legais selecionadas.</span><span class="sxs-lookup"><span data-stu-id="36956-126">Approved products are added to the product master and are released to the selected legal entities.</span></span> <span data-ttu-id="36956-127">Somente os produtos aprovadas podem ser adicionados ao catálogo de compras.</span><span class="sxs-lookup"><span data-stu-id="36956-127">Only approved products can be added to the procurement catalog.</span></span>

## <a name="generate-a-catalog-import-file-template"></a><span data-ttu-id="36956-128">Gerar um modelo de arquivo de importação de catálogo</span><span class="sxs-lookup"><span data-stu-id="36956-128">Generate a catalog import file template</span></span>

<span data-ttu-id="36956-129">O modelo do arquivo de importação de catálogo é um arquivo XSD usado para criar um arquivo CMR dos produtos de um fornecedor.</span><span class="sxs-lookup"><span data-stu-id="36956-129">The catalog import file template is an XSD file that you use to create a CMR file for a vendor’s products.</span></span> <span data-ttu-id="36956-130">Você pode usar o arquivo CMR para criar um novo catálogo, substituir um catálogo existente ou modificar um catálogo existente.</span><span class="sxs-lookup"><span data-stu-id="36956-130">You can use the CMR file to create a new catalog, replace an existing catalog, or modify an existing catalog.</span></span>

1.  <span data-ttu-id="36956-131">Selecione **Compras e fornecimento** \> **Catálogos** \> **Catálogos do fornecedor** e clique duas vezes no catálogo com que você deseja trabalhar.</span><span class="sxs-lookup"><span data-stu-id="36956-131">Select **Procurement and sourcing** \> **Catalogs** \> **Vendor catalogs** and double-click the catalog that you want to work with.</span></span>

2.  <span data-ttu-id="36956-132">Baixe um modelo de importação de catálogo atual (arquivo XSD).</span><span class="sxs-lookup"><span data-stu-id="36956-132">Download a current catalog import template (XSD file).</span></span> <span data-ttu-id="36956-133">Na página **Atualizar catálogo**, no **Painel de ações**, na guia **Catálogos** , no grupo **Informações relacionadas** , clique em **Gerar modelo de catálogo** e selecione **Categoria de compras**.</span><span class="sxs-lookup"><span data-stu-id="36956-133">On the **Update catalog** page, on the **Action Pane**, on the **Catalogs** tab, in the **Related information** group, click **Generate catalog template** and select **Procurement category**.</span></span>

    -   <span data-ttu-id="36956-134">Com a opção **Categoria de compras**, você pode gerar um modelo de catálogo que inclui as categorias de compras nas quais o fornecedor está autorizado a fornecer produtos.</span><span class="sxs-lookup"><span data-stu-id="36956-134">With the **Procurement category** option you can generate a catalog template that includes the procurement categories in which the vendor is authorized to provide products.</span></span>

3. <span data-ttu-id="36956-135">Na caixa de diálogo **Salvar como**, selecione o local onde você deseja armazenar o modelo de arquivo de catálogo e salve o arquivo.</span><span class="sxs-lookup"><span data-stu-id="36956-135">In the **Save as** dialog box, select the location where you want to store the catalog file template and save the file.</span></span>

<span data-ttu-id="36956-136">Para obter mais informações e ver exemplos, consulte estas postagem de blog: [Catálogos de fornecedor no Dynamics AX](https://blogs.msdn.microsoft.com/dynamicsaxscm/2016/05/25/vendor-catalogs-in-dynamics-ax/).</span><span class="sxs-lookup"><span data-stu-id="36956-136">For more information and for examples, refer to this blog post: [Vendor catalogs in Dynamics AX](https://blogs.msdn.microsoft.com/dynamicsaxscm/2016/05/25/vendor-catalogs-in-dynamics-ax/).</span></span>
