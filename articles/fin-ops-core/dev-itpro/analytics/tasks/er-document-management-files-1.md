---
title: ER Usar arquivos de gerenciamento de documentos em formato de saída (Parte 1 - Preparar modelo de dados)
description: As etapas a seguir explicam como um usuário atribuído à função de administrador do sistema ou desenvolvedor de relatório eletrônico pode configurar um formato de relatório eletrônico (ER) para usar arquivos de gerenciamento de documentos (anexos) na saída do ER.
author: NickSelin
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ERWorkspace, ERVendorPart, ERSolutionRepositoryTable, ERSolutionRepositoryCreateDropDialog, ERSolutionImport,  ERSolutionTable, ERSolutionCreateDropDialog
audience: Application User
ms.reviewer: kfend
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 29c13e729223a98d7f45244c5a796bca6e3baaf3
ms.sourcegitcommit: 75db3b75d35d27034f9b56e7119c9d0cb7666830
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/03/2019
ms.locfileid: "2550824"
---
# <a name="er-use-document-management-files-in-format-outputs-part-1---prepare-data-model"></a><span data-ttu-id="2a214-103">ER Usar arquivos de gerenciamento de documentos em formato de saída (Parte 1 - Preparar modelo de dados)</span><span class="sxs-lookup"><span data-stu-id="2a214-103">ER Use Document Management files in format outputs (Part 1 - Prepare data model)</span></span>

[!include [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="2a214-104">As etapas a seguir explicam como um usuário atribuído à função de administrador do sistema ou desenvolvedor de relatório eletrônico pode configurar um formato de relatório eletrônico (ER) para usar arquivos de gerenciamento de documentos (anexos) na saída do ER.</span><span class="sxs-lookup"><span data-stu-id="2a214-104">The following steps explain how a user assigned to the system administrator or electronic reporting developer role can configure an Electronic reporting (ER) format to use Document Management files (attachments) in ER output.</span></span> <span data-ttu-id="2a214-105">Essas etapas podem ser executadas em qualquer empresa.</span><span class="sxs-lookup"><span data-stu-id="2a214-105">These steps can be performed in any company.</span></span>

<span data-ttu-id="2a214-106">Para completar essas etapas, você deve primeiro completar as etapas do procedimento “Criar um provedor de configuração e marcá-lo como ativo“.</span><span class="sxs-lookup"><span data-stu-id="2a214-106">To complete these steps, you must first complete the steps in the “Create a configuration provider and mark it as active” procedure.</span></span>

<span data-ttu-id="2a214-107">Este procedimento é para um recurso que foi adicionado na versão 1611 do Dynamics 365 for Operations.</span><span class="sxs-lookup"><span data-stu-id="2a214-107">This procedure is for a feature that was added in Dynamics 365 for Operations version 1611.</span></span>


## <a name="get-access-to-the-list-of-configurations-provided-by-microsoft"></a><span data-ttu-id="2a214-108">Obter acesso à lista de configurações fornecidas pela Microsoft</span><span class="sxs-lookup"><span data-stu-id="2a214-108">Get access to the list of configurations provided by Microsoft</span></span>
1. <span data-ttu-id="2a214-109">Ir para Administração da organização > Espaços de trabalho > Relatório eletrônico.</span><span class="sxs-lookup"><span data-stu-id="2a214-109">Go to Organization administration > Workspaces > Electronic reporting.</span></span>
    * <span data-ttu-id="2a214-110">Verifique se o provedor "Litware, Inc."</span><span class="sxs-lookup"><span data-stu-id="2a214-110">Make sure that the 'Litware, Inc.'</span></span> <span data-ttu-id="2a214-111">está disponível e marcado como ativo.</span><span class="sxs-lookup"><span data-stu-id="2a214-111">provider is available and marked as active.</span></span>  
2. <span data-ttu-id="2a214-112">Selecione o "Litware, Inc."</span><span class="sxs-lookup"><span data-stu-id="2a214-112">Select the 'Litware, Inc.'</span></span> <span data-ttu-id="2a214-113">"Litware, Inc.".</span><span class="sxs-lookup"><span data-stu-id="2a214-113">provider.</span></span>
3. <span data-ttu-id="2a214-114">Clique em Repositórios.</span><span class="sxs-lookup"><span data-stu-id="2a214-114">Click Repositories.</span></span>
    * <span data-ttu-id="2a214-115">Se um repositório do tipo 'Recurso de operações' já existir, ignore as etapas restantes das subtarefa atual.</span><span class="sxs-lookup"><span data-stu-id="2a214-115">If a repository of the 'Operations resources' type already exists, skip the remaining steps of the current sub-task.</span></span>  
4. <span data-ttu-id="2a214-116">Clique em Adicionar para abrir a caixa de diálogo suspensa.</span><span class="sxs-lookup"><span data-stu-id="2a214-116">Click Add to open the drop dialog.</span></span>
5. <span data-ttu-id="2a214-117">No campo Tipo de repositório de configuração, insira 'Recursos de operações'.</span><span class="sxs-lookup"><span data-stu-id="2a214-117">In the Configuration repository type field, enter 'Operations resources'.</span></span>
6. <span data-ttu-id="2a214-118">Clique em Criar repositório.</span><span class="sxs-lookup"><span data-stu-id="2a214-118">Click Create repository.</span></span>
7. <span data-ttu-id="2a214-119">Clique em OK.</span><span class="sxs-lookup"><span data-stu-id="2a214-119">Click OK.</span></span>

## <a name="get-the-customer-invoice-model-configurations-provided-by-microsoft"></a><span data-ttu-id="2a214-120">Obter as configurações do Modelo de fatura de cliente fornecidas pela Microsoft</span><span class="sxs-lookup"><span data-stu-id="2a214-120">Get the Customer invoice model configurations provided by Microsoft</span></span>
1. <span data-ttu-id="2a214-121">Clique em Mostrar filtros.</span><span class="sxs-lookup"><span data-stu-id="2a214-121">Click Show filters.</span></span>
2. <span data-ttu-id="2a214-122">Aplicar os seguintes filtros: inserir um valor de filtro de "Recursos de operações" no campo "Nome" usando o operador de filtro "começa com"; inserir um valor de filtro de "" no campo Descrição usando o operador de filtro "começa com"</span><span class="sxs-lookup"><span data-stu-id="2a214-122">Apply the following filters: Enter a filter value of "Operations resources" on the "Name" field using the "begins with" filter operator; Enter a filter value of "" on the "Description" field using the "begins with" filter operator</span></span>
3. <span data-ttu-id="2a214-123">Clique em Mostrar filtros.</span><span class="sxs-lookup"><span data-stu-id="2a214-123">Click Show filters.</span></span>
4. <span data-ttu-id="2a214-124">Clique em Abrir.</span><span class="sxs-lookup"><span data-stu-id="2a214-124">Click Open.</span></span>
5. <span data-ttu-id="2a214-125">Na árvore, selecione 'Modelo de fatura de cliente'.</span><span class="sxs-lookup"><span data-stu-id="2a214-125">In the tree, select 'Customer invoice model'.</span></span>
    * <span data-ttu-id="2a214-126">Selecione a configuração do modelo 'Modelo de fatura de cliente' para importá-la.</span><span class="sxs-lookup"><span data-stu-id="2a214-126">Select the model configuration 'Customer invoice model' to import it.</span></span>  
6. <span data-ttu-id="2a214-127">Clique em Importar.</span><span class="sxs-lookup"><span data-stu-id="2a214-127">Click Import.</span></span>
    * <span data-ttu-id="2a214-128">Clique em Importar para a versão 1 da configuração selecionada.</span><span class="sxs-lookup"><span data-stu-id="2a214-128">Click Import for version 1 of the selected configuration.</span></span>  
7. <span data-ttu-id="2a214-129">Clique em Sim.</span><span class="sxs-lookup"><span data-stu-id="2a214-129">Click Yes.</span></span>
8. <span data-ttu-id="2a214-130">Feche a página.</span><span class="sxs-lookup"><span data-stu-id="2a214-130">Close the page.</span></span>
9. <span data-ttu-id="2a214-131">Feche a página.</span><span class="sxs-lookup"><span data-stu-id="2a214-131">Close the page.</span></span>
10. <span data-ttu-id="2a214-132">Clique em Configurações de relatórios.</span><span class="sxs-lookup"><span data-stu-id="2a214-132">Click Reporting configurations.</span></span>
11. <span data-ttu-id="2a214-133">Na árvore, selecione 'Modelo de fatura de cliente'.</span><span class="sxs-lookup"><span data-stu-id="2a214-133">In the tree, select 'Customer invoice model'.</span></span>

## <a name="create-the-derived-model-to-support-access-to-the-document-management-files"></a><span data-ttu-id="2a214-134">Crie o modelo derivado para oferecer suporte ao acesso a arquivos de gerenciamento de documentos.</span><span class="sxs-lookup"><span data-stu-id="2a214-134">Create the derived model to support access to the Document Management files.</span></span>
    * <span data-ttu-id="2a214-135">Você criará nossa própria configuração do Modelo de fatura de cliente derivando-o da configuração fornecida pela Microsoft.</span><span class="sxs-lookup"><span data-stu-id="2a214-135">You will create our own configuration of the Customer invoice model deriving it from the configuration provided by Microsoft.</span></span> <span data-ttu-id="2a214-136">Você usará essa configuração para implementar o acesso aos arquivos de gerenciamento de documentos e para disponibilizá-los nos documentos eletrônicos que serão criados com base nesse modelo.</span><span class="sxs-lookup"><span data-stu-id="2a214-136">You will use this configuration to implement access to the Document Management files and make them available for electronic documents that you will create based on this model.</span></span>  
1. <span data-ttu-id="2a214-137">Clique em Criar configuração para abrir a caixa de diálogo suspensa.</span><span class="sxs-lookup"><span data-stu-id="2a214-137">Click Create configuration to open the drop dialog.</span></span>
2. <span data-ttu-id="2a214-138">No campo Novo, digite o nome 'Derivar do Nome: Modelo de fatura de cliente, Microsoft'.</span><span class="sxs-lookup"><span data-stu-id="2a214-138">In the New field, enter 'Derive from Name: Customer invoice model, Microsoft'.</span></span>
3. <span data-ttu-id="2a214-139">No campo Nome, digite 'Modelo de fatura de cliente (personalizada)'.</span><span class="sxs-lookup"><span data-stu-id="2a214-139">In the Name field, type 'Customer invoice model (custom)'.</span></span>
    * <span data-ttu-id="2a214-140">Modelo de fatura de cliente (personalizada)</span><span class="sxs-lookup"><span data-stu-id="2a214-140">Customer invoice model (custom)</span></span>  
4. <span data-ttu-id="2a214-141">Clique em Criar configuração.</span><span class="sxs-lookup"><span data-stu-id="2a214-141">Click Create configuration.</span></span>
