---
title: Importar catálogos do fornecedor
description: Este tópico descreve o processo para importar dados do catálogo do fornecedor.
author: mkirknel
manager: tfehr
ms.date: 03/20/2018
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: VendProspectiveVendorRegistrationRequests
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.custom: ''
ms.search.region: Global
ms.search.industry: ''
ms.author: mkirknel
ms.search.validFrom: 2018-04-20
ms.dyn365.ops.version: 7.2999999999999998
ms.openlocfilehash: 35b8e2a87708c88b12c5c7605a7977712a35a0f4
ms.sourcegitcommit: 4f9912439ff78acf0c754d5bff972c4b85763093
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/02/2020
ms.locfileid: "3207361"
---
# <a name="import-vendor-catalogs"></a><span data-ttu-id="9084d-103">Importar catálogos do fornecedor</span><span class="sxs-lookup"><span data-stu-id="9084d-103">Import vendor catalogs</span></span>
[!include[banner](../includes/banner.md)]

## <a name="vendor-catalogs-import"></a><span data-ttu-id="9084d-104">Importação dos catálogos do fornecedor</span><span class="sxs-lookup"><span data-stu-id="9084d-104">Vendor catalogs import</span></span>

<span data-ttu-id="9084d-105">No Dynamics 365 Supply Chain Management, os profissionais de compra podem criar e manter catálogos para os funcionários da empresa usarem ao solicitar itens e serviços para uso interno.</span><span class="sxs-lookup"><span data-stu-id="9084d-105">In Dynamics 365 Supply Chain Management, purchasing professionals can create and maintain catalogs for company employees to use when they order items and services for internal use.</span></span> <span data-ttu-id="9084d-106">Para criar um catálogo de compras, é possível adicionar itens e serviços que você deseja disponibilizar para os funcionários, importando manualmente os dados do catálogo de produtos ou adicionando manualmente os dados do catálogo de produtos até o produto mestre.</span><span class="sxs-lookup"><span data-stu-id="9084d-106">To create a procurement catalog, you can add the items and services that you want to make available to employees, either by importing the product catalog data or by manually adding the product catalog data to the product master.</span></span> 

<span data-ttu-id="9084d-107">Você pode carregar os dados do catálogo enviados por um fornecedor do cliente do Microsoft Dynamics 365.</span><span class="sxs-lookup"><span data-stu-id="9084d-107">You can upload catalog data submitted by a vendor from the Microsoft Dynamics 365 client.</span></span>

<span data-ttu-id="9084d-108">Os dados do produto que um fornecedor envia para você, na forma de um arquivo de solicitação de manutenção de catálogo (CMR), devem estar no formato de arquivo XML.</span><span class="sxs-lookup"><span data-stu-id="9084d-108">The product data that a vendor submits to you, in the form of a catalog maintenance request (CMR) file, must be in XML file format.</span></span> <span data-ttu-id="9084d-109">O arquivo CMR deve conter todos os detalhes dos produtos que o fornecedor abastece na sua empresa.</span><span class="sxs-lookup"><span data-stu-id="9084d-109">The CMR file should contain the details for the products that the vendor supplies to your company.</span></span>
<span data-ttu-id="9084d-110">''''</span><span class="sxs-lookup"><span data-stu-id="9084d-110">''''</span></span>
## <a name="import-vendor-catalog-data"></a><span data-ttu-id="9084d-111">Importar dados do catálogo do fornecedor</span><span class="sxs-lookup"><span data-stu-id="9084d-111">Import vendor catalog data</span></span>
<span data-ttu-id="9084d-112">"Para importar os dados do catálogo do fornecedor, conclua as seguintes tarefas:</span><span class="sxs-lookup"><span data-stu-id="9084d-112">'' To import vendor catalog data, you must complete the following tasks:</span></span>

1.  <span data-ttu-id="9084d-113">Configure um projeto no espaço de trabalho de Gerenciamento de dados em que você definiu as regras de mapeamento de dados.</span><span class="sxs-lookup"><span data-stu-id="9084d-113">Set up a project in the Data management workspace where you have defined your data mapping rules.</span></span> <span data-ttu-id="9084d-114">Selecione **Gerenciamento de dados** e selecione **Configurar funções para projetos de dados**.</span><span class="sxs-lookup"><span data-stu-id="9084d-114">Select **Data management** and then select **Set up roles for data projects**.</span></span> 
    <span data-ttu-id="9084d-115">''</span><span class="sxs-lookup"><span data-stu-id="9084d-115">''</span></span>
2.  <span data-ttu-id="9084d-116">Configure uma hierarquia de categorias de compras e atribua seus fornecedores às categorias de compras.</span><span class="sxs-lookup"><span data-stu-id="9084d-116">Set up a procurement category hierarchy, and assign your vendors to procurement categories.</span></span> <span data-ttu-id="9084d-117">Se você usar códigos de mercadoria, adicione os códigos de mercadoria às categorias de compras.</span><span class="sxs-lookup"><span data-stu-id="9084d-117">If you use commodity codes, add the commodity codes to the procurement categories.</span></span> <span data-ttu-id="9084d-118">Para obter informações sobre como configurar uma hierarquia de categorias de compras, consulte [Configurar uma hierarquia de categorias de compras](../procurement/tasks/set-up-procurement-category-hierarchy.md).</span><span class="sxs-lookup"><span data-stu-id="9084d-118">For information about setting up a procurement category hierarchy, see [Set up a procurement category hierarchy](../procurement/tasks/set-up-procurement-category-hierarchy.md).</span></span>
    <span data-ttu-id="9084d-119">''</span><span class="sxs-lookup"><span data-stu-id="9084d-119">''</span></span>
3.  <span data-ttu-id="9084d-120">Configurar o fornecedor para importação de catálogo.</span><span class="sxs-lookup"><span data-stu-id="9084d-120">Configure the vendor for catalog import.</span></span> <span data-ttu-id="9084d-121">Selecione um fornecedor e então selecione **Compras** > **Configurar** > **Configurar o fornecedor para importação de catálogo**.</span><span class="sxs-lookup"><span data-stu-id="9084d-121">Select a vendor, and then select **Procurement** > **Set up** > **Configure vendor for catalog import**.</span></span>
<span data-ttu-id="9084d-122">''''</span><span class="sxs-lookup"><span data-stu-id="9084d-122">''''</span></span>
4.  <span data-ttu-id="9084d-123">Configure o fluxo de trabalho para importação de catálogo.</span><span class="sxs-lookup"><span data-stu-id="9084d-123">Configure workflow for catalog import.</span></span> <span data-ttu-id="9084d-124">Crie um modelo do arquivo CMR e compartilhe isso com o fornecedor.</span><span class="sxs-lookup"><span data-stu-id="9084d-124">Create a CMR file template and share this with your vendor.</span></span>

5.  <span data-ttu-id="9084d-125">Selecione **Compras e fornecimento** \> **Comum** \> **Catálogo** \> **Catálogos do fornecedor** para criar um catálogo do fornecedor.</span><span class="sxs-lookup"><span data-stu-id="9084d-125">Select **Procurement and sourcing** \> **Common** \> **Catalogs** \> **Vendor catalogs** to create a vendor catalog.</span></span> <span data-ttu-id="9084d-126">Os arquivos de solicitação de manutenção de catálogo (CMR) recebidos do fornecedor são agrupados nesse catálogo.</span><span class="sxs-lookup"><span data-stu-id="9084d-126">The catalog maintenance request (CMR) files that you receive from your vendor are grouped in this catalog.</span></span> 

6.  <span data-ttu-id="9084d-127">Carregue o arquivo CMR.</span><span class="sxs-lookup"><span data-stu-id="9084d-127">Upload the CMR file.</span></span>

7.  <span data-ttu-id="9084d-128">Revise, aprove ou rejeite os produtos no catálogo do fornecedor.</span><span class="sxs-lookup"><span data-stu-id="9084d-128">Review, approve, or reject the products in the vendor catalog.</span></span> <span data-ttu-id="9084d-129">Os produtos são mapeados automaticamente para as categorias de compras.</span><span class="sxs-lookup"><span data-stu-id="9084d-129">The products are automatically mapped to the procurement categories.</span></span> 
    
<span data-ttu-id="9084d-130">Os produtos aprovados são adicionados ao produto mestre e liberados para as entidades legais selecionadas.</span><span class="sxs-lookup"><span data-stu-id="9084d-130">Approved products are added to the product master and are released to the selected legal entities.</span></span> <span data-ttu-id="9084d-131">Somente os produtos aprovadas podem ser adicionados ao catálogo de compras.</span><span class="sxs-lookup"><span data-stu-id="9084d-131">Only approved products can be added to the procurement catalog.</span></span>

## <a name="generate-a-catalog-import-file-template"></a><span data-ttu-id="9084d-132">Gerar um modelo de arquivo de importação de catálogo</span><span class="sxs-lookup"><span data-stu-id="9084d-132">Generate a catalog import file template</span></span>

<span data-ttu-id="9084d-133">O modelo do arquivo de importação de catálogo é um arquivo XSD usado para criar um arquivo CMR dos produtos de um fornecedor.</span><span class="sxs-lookup"><span data-stu-id="9084d-133">The catalog import file template is an XSD file that you use to create a CMR file for a vendor's products.</span></span> <span data-ttu-id="9084d-134">Você pode usar o arquivo CMR para criar um novo catálogo, substituir um catálogo existente ou modificar um catálogo existente.</span><span class="sxs-lookup"><span data-stu-id="9084d-134">You can use the CMR file to create a new catalog, replace an existing catalog, or modify an existing catalog.</span></span>

1.  <span data-ttu-id="9084d-135">Selecione **Compras e fornecimento** \> **Catálogos** \> **Catálogos do fornecedor** e clique duas vezes no catálogo com que você deseja trabalhar.</span><span class="sxs-lookup"><span data-stu-id="9084d-135">Select **Procurement and sourcing** \> **Catalogs** \> **Vendor catalogs** and double-click the catalog that you want to work with.</span></span>

2.  <span data-ttu-id="9084d-136">Baixe um modelo de importação de catálogo atual (arquivo XSD).</span><span class="sxs-lookup"><span data-stu-id="9084d-136">Download a current catalog import template (XSD file).</span></span> <span data-ttu-id="9084d-137">Na página **Atualizar catálogo**, no **Painel de ações**, na guia **Catálogos** , no grupo **Informações relacionadas** , clique em **Gerar modelo de catálogo** e selecione **Categoria de compras**.</span><span class="sxs-lookup"><span data-stu-id="9084d-137">On the **Update catalog** page, on the **Action Pane**, on the **Catalogs** tab, in the **Related information** group, click **Generate catalog template** and select **Procurement category**.</span></span>

    -   <span data-ttu-id="9084d-138">Com a opção **Categoria de compras**, você pode gerar um modelo de catálogo que inclui as categorias de compras nas quais o fornecedor está autorizado a fornecer produtos.</span><span class="sxs-lookup"><span data-stu-id="9084d-138">With the **Procurement category** option you can generate a catalog template that includes the procurement categories in which the vendor is authorized to provide products.</span></span>

3. <span data-ttu-id="9084d-139">Na caixa de diálogo **Salvar como**, selecione o local onde você deseja armazenar o modelo de arquivo de catálogo e salve o arquivo.</span><span class="sxs-lookup"><span data-stu-id="9084d-139">In the **Save as** dialog box, select the location where you want to store the catalog file template and save the file.</span></span>

<span data-ttu-id="9084d-140">Para obter mais informações e ver exemplos, consulte estas postagem de blog: [Catálogos de fornecedor no Dynamics AX](https://blogs.msdn.microsoft.com/dynamicsaxscm/2016/05/25/vendor-catalogs-in-dynamics-ax/).</span><span class="sxs-lookup"><span data-stu-id="9084d-140">For more information and for examples, refer to this blog post: [Vendor catalogs in Dynamics AX](https://blogs.msdn.microsoft.com/dynamicsaxscm/2016/05/25/vendor-catalogs-in-dynamics-ax/).</span></span>
