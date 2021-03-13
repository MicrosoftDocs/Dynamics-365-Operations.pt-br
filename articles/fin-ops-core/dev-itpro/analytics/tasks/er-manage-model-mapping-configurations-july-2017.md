---
title: Gerenciar o mapeamento do modelo ER em configurações ER separadas
description: Este tópico descreve como gerenciar mapeamentos de modelo de relatório eletrônico (ER) em configurações de ER separadas.
author: NickSelin
manager: AnnBe
ms.date: 06/19/2017
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
audience: Application User
ms.reviewer: kfend
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 2f1013cfc9f421525fb0661cd5ace5eeaa157f9a
ms.sourcegitcommit: 5192cfaedfd861faea63d8954d7bcc500608a225
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/30/2021
ms.locfileid: "5093789"
---
# <a name="manage-er-model-mapping-in-separate-er-configurations"></a><span data-ttu-id="f102a-103">Gerenciar o mapeamento do modelo de ER em configurações de ER separadas</span><span class="sxs-lookup"><span data-stu-id="f102a-103">Manage ER model mapping in separate ER configurations</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="f102a-104">As etapas a seguir explicam como um usuário atribuído ao Administrador do sistema ou Desenvolvedor de relatório eletrônico pode gerenciar mapeamentos de modelo de Relatório eletrônico (RE) em configurações de ER separadas.</span><span class="sxs-lookup"><span data-stu-id="f102a-104">The following steps explain how a user assigned to the System administrator or Electronic reporting developer role can manage Electronic reporting (ER) model mappings in separate ER configurations.</span></span> <span data-ttu-id="f102a-105">Nesta guia de tarefas, você criará as configurações de ER necessárias para a empresa exemplo, Litware, Inc. Para concluir este guia de tarefas, você deverá primeiramente concluir as etapas no guia de tarefas, "ER Criar um provedor configuração" e marcá-lo como ativo.</span><span class="sxs-lookup"><span data-stu-id="f102a-105">In this task guide, you will create required ER configurations for the sample company, Litware, Inc. To complete this task guide, you must first complete the steps in the task guide, "ER Create a configuration provider" and mark it as active.</span></span> 

<span data-ttu-id="f102a-106">Como as configurações de ER são compartilhadas entre empresas, você pode concluir este guia de tarefas usando o conjunto de dados da empresa de sua escolha.</span><span class="sxs-lookup"><span data-stu-id="f102a-106">Because ER configurations are shared among companies, you can complete this task guide using the company data set of your choice.</span></span> <span data-ttu-id="f102a-107">A funcionalidade deste guia de tarefas estará disponível se você tiver instalado um dos seguintes hotfixes: https://fix.lcs.dynamics.com/Issue/Resolved?kb=4012872 para a versão 7.0 do Dynamics AX ou https://fix.lcs.dynamics.com/Issue/Resolved?kb=4012871 para a versão Dynamics 365 for Operations.</span><span class="sxs-lookup"><span data-stu-id="f102a-107">The functionality for this task guide is available if you have installed one of the following hotfixes: https://fix.lcs.dynamics.com/Issue/Resolved?kb=4012872 for the Dynamics AX 7.0 version or https://fix.lcs.dynamics.com/Issue/Resolved?kb=4012871 for the Dynamics 365 for Operations version.</span></span>

1. <span data-ttu-id="f102a-108">Ir para Administração da organização > Espaços de trabalho > Relatório eletrônico.</span><span class="sxs-lookup"><span data-stu-id="f102a-108">Go to Organization administration > Workspaces > Electronic reporting.</span></span>
    * <span data-ttu-id="f102a-109">Verifique se o provedor de configuração para a empresa exemplo Litware, Inc. está disponível e marcado como ativo.</span><span class="sxs-lookup"><span data-stu-id="f102a-109">Verify that the configuration provider for the sample company Litware, Inc. is available and marked as active.</span></span> <span data-ttu-id="f102a-110">Se você não vir este provedor de configuração, deverá concluir primeiro as etapas na guia de tarefas, Criar um provedor de configuração e marcá-lo como ativo.</span><span class="sxs-lookup"><span data-stu-id="f102a-110">If you don't see this configuration provider, you must first complete the steps in the task guide, Create a configuration provider, and mark it as active.</span></span>   

## <a name="add-a-new-er-model-configuration"></a><span data-ttu-id="f102a-111">Adicionar uma nova configuração de modelo de ER</span><span class="sxs-lookup"><span data-stu-id="f102a-111">Add a new ER model configuration</span></span>
1. <span data-ttu-id="f102a-112">Clique em Configurações de relatórios.</span><span class="sxs-lookup"><span data-stu-id="f102a-112">Click Reporting configurations.</span></span>
    * <span data-ttu-id="f102a-113">Adicionar uma nova configuração de modelo.</span><span class="sxs-lookup"><span data-stu-id="f102a-113">Add a new model configuration.</span></span> <span data-ttu-id="f102a-114">O nome deve ser exclusivo na árvore de configurações.</span><span class="sxs-lookup"><span data-stu-id="f102a-114">The name must be unique in the configurations tree.</span></span>  
2. <span data-ttu-id="f102a-115">Clique em Criar configuração para abrir a caixa de diálogo suspensa.</span><span class="sxs-lookup"><span data-stu-id="f102a-115">Click Create configuration to open the drop dialog.</span></span>
3. <span data-ttu-id="f102a-116">No campo Nome, digite "Modelo de dados de amostra".</span><span class="sxs-lookup"><span data-stu-id="f102a-116">In the Name field, type 'Sample data model'.</span></span>
    * <span data-ttu-id="f102a-117">Modelo de dados de exemplo</span><span class="sxs-lookup"><span data-stu-id="f102a-117">Sample data model</span></span>  
4. <span data-ttu-id="f102a-118">Clique em Criar configuração.</span><span class="sxs-lookup"><span data-stu-id="f102a-118">Click Create configuration.</span></span>
5. <span data-ttu-id="f102a-119">Clique em Designer.</span><span class="sxs-lookup"><span data-stu-id="f102a-119">Click Designer.</span></span>
6. <span data-ttu-id="f102a-120">Clique em Novo para abrir a caixa de diálogo suspensa.</span><span class="sxs-lookup"><span data-stu-id="f102a-120">Click New to open the drop dialog.</span></span>
7. <span data-ttu-id="f102a-121">No campo Nome, digite "Raiz".</span><span class="sxs-lookup"><span data-stu-id="f102a-121">In the Name field, type 'Root'.</span></span>
    * <span data-ttu-id="f102a-122">Raiz</span><span class="sxs-lookup"><span data-stu-id="f102a-122">Root</span></span>  
8. <span data-ttu-id="f102a-123">Clique em Adicionar.</span><span class="sxs-lookup"><span data-stu-id="f102a-123">Click Add.</span></span>
9. <span data-ttu-id="f102a-124">Clique em Novo para abrir a caixa de diálogo suspensa.</span><span class="sxs-lookup"><span data-stu-id="f102a-124">Click New to open the drop dialog.</span></span>
10. <span data-ttu-id="f102a-125">No campo Nome, digite 'Empresa'.</span><span class="sxs-lookup"><span data-stu-id="f102a-125">In the Name field, type 'Company'.</span></span>
    * <span data-ttu-id="f102a-126">Empresa</span><span class="sxs-lookup"><span data-stu-id="f102a-126">Company</span></span>  
11. <span data-ttu-id="f102a-127">Clique em Adicionar.</span><span class="sxs-lookup"><span data-stu-id="f102a-127">Click Add.</span></span>
12. <span data-ttu-id="f102a-128">No campo Descrição, insira o texto, a descrição da entidade legal ou da empresa em que o usuário fez logon no tempo de execução.</span><span class="sxs-lookup"><span data-stu-id="f102a-128">In the Description field, enter the text, Description of the legal entity or company in which a user logged at run-time.</span></span> 
    * <span data-ttu-id="f102a-129">Descrição da entidade legal ou da empresa em que o usuário fez logon no tempo de execução.</span><span class="sxs-lookup"><span data-stu-id="f102a-129">Description of the legal entity or company in which a user logged at run-time.</span></span>  
13. <span data-ttu-id="f102a-130">Clique em Referência raiz.</span><span class="sxs-lookup"><span data-stu-id="f102a-130">Click Root reference.</span></span>
14. <span data-ttu-id="f102a-131">Clique em OK.</span><span class="sxs-lookup"><span data-stu-id="f102a-131">Click OK.</span></span>
15. <span data-ttu-id="f102a-132">Clique em Salvar.</span><span class="sxs-lookup"><span data-stu-id="f102a-132">Click Save.</span></span>
16. <span data-ttu-id="f102a-133">Feche a página.</span><span class="sxs-lookup"><span data-stu-id="f102a-133">Close the page.</span></span>
17. <span data-ttu-id="f102a-134">Clique em Alterar status.</span><span class="sxs-lookup"><span data-stu-id="f102a-134">Click Change status.</span></span>
18. <span data-ttu-id="f102a-135">Clique em Concluir.</span><span class="sxs-lookup"><span data-stu-id="f102a-135">Click Complete.</span></span>
19. <span data-ttu-id="f102a-136">Clique em OK.</span><span class="sxs-lookup"><span data-stu-id="f102a-136">Click OK.</span></span>

## <a name="add-a-new-er-model-mapping-configuration"></a><span data-ttu-id="f102a-137">Adicionar uma nova configuração de mapeamento do modelo de ER</span><span class="sxs-lookup"><span data-stu-id="f102a-137">Add a new ER model-mapping configuration</span></span>
1. <span data-ttu-id="f102a-138">Clique em Criar configuração para abrir a caixa de diálogo suspensa.</span><span class="sxs-lookup"><span data-stu-id="f102a-138">Click Create configuration to open the drop dialog.</span></span>
2. <span data-ttu-id="f102a-139">No campo Novo, insira 'Mapeamento de modelo baseado no modelo de dados Modelo de dados de amostra'.</span><span class="sxs-lookup"><span data-stu-id="f102a-139">In the New field, enter 'Model Mapping based on data model Sample data model'.</span></span>
3. <span data-ttu-id="f102a-140">No campo Nome, digite 'Mapeamento de amostra'.</span><span class="sxs-lookup"><span data-stu-id="f102a-140">In the Name field, type 'Sample mapping'.</span></span>
    * <span data-ttu-id="f102a-141">Mapeamento de amostra</span><span class="sxs-lookup"><span data-stu-id="f102a-141">Sample mapping</span></span>  
4. <span data-ttu-id="f102a-142">Clique em Criar configuração.</span><span class="sxs-lookup"><span data-stu-id="f102a-142">Click Create configuration.</span></span>
5. <span data-ttu-id="f102a-143">Expanda a seção Pré-requisitos.</span><span class="sxs-lookup"><span data-stu-id="f102a-143">Expand the Prerequisites section.</span></span>
    * <span data-ttu-id="f102a-144">O grupo de pré-requisitos Implementações foi adicionado automaticamente.</span><span class="sxs-lookup"><span data-stu-id="f102a-144">The Implementations prerequisites group has been added automatically.</span></span> <span data-ttu-id="f102a-145">O grupo contém o componente de pré-requisito que se refere à configuração do modelo de dados pai e é marcado como Implementação.</span><span class="sxs-lookup"><span data-stu-id="f102a-145">The group contains the prerequisite component that refers to the parent data model configuration and is marked as Implementation.</span></span> <span data-ttu-id="f102a-146">Isso significa que esta Configuração de mapeamento do modelo de mapeamento de amostra é considerada a implementação do modelo de dados Modelo de dados de amostra.</span><span class="sxs-lookup"><span data-stu-id="f102a-146">This means that this Sample-mapping model-mapping configuration is considered the implementation of the data model, Sample data model.</span></span> <span data-ttu-id="f102a-147">Portanto, este componente forçará o ER para baixar a configuração de mapeamento do modelo Mapeamento de amostra de um repositório de ER sempre que a configuração do modelo Modelo de dados de amostra for baixada.</span><span class="sxs-lookup"><span data-stu-id="f102a-147">Therefore, this component will force ER to download the model-mapping configuration, Sample mapping from an ER repository when the model configuration, Sample data model, is downloaded.</span></span>   
6. <span data-ttu-id="f102a-148">Clique em Designer.</span><span class="sxs-lookup"><span data-stu-id="f102a-148">Click Designer.</span></span>
    * <span data-ttu-id="f102a-149">A configuração de mapeamento modelo criada contém um novo mapeamento em branco com o mesmo nome da configuração criada.</span><span class="sxs-lookup"><span data-stu-id="f102a-149">The created model-mapping configuration contains a new blank mapping with the same name as the created configuration.</span></span> <span data-ttu-id="f102a-150">Quando uma configuração de modelo pai selecionada contiver mapeamentos de modelo, eles serão copiados para uma configuração de mapeamento do novo modelo.</span><span class="sxs-lookup"><span data-stu-id="f102a-150">When a selected parent model configuration contains model mappings, they will be copied to a new model-mapping configuration.</span></span>   
7. <span data-ttu-id="f102a-151">Clique em Designer.</span><span class="sxs-lookup"><span data-stu-id="f102a-151">Click Designer.</span></span>
8. <span data-ttu-id="f102a-152">Na árvore, selecione 'Dynamics 365 for Operations\Tabela'.</span><span class="sxs-lookup"><span data-stu-id="f102a-152">In the tree, select 'Dynamics 365 for Operations\Table'.</span></span>
9. <span data-ttu-id="f102a-153">Clique em Adicionar raiz.</span><span class="sxs-lookup"><span data-stu-id="f102a-153">Click Add root.</span></span>
10. <span data-ttu-id="f102a-154">No campo Nome, digite 'Empresa'.</span><span class="sxs-lookup"><span data-stu-id="f102a-154">In the Name field, type 'Company'.</span></span>
    * <span data-ttu-id="f102a-155">Empresa</span><span class="sxs-lookup"><span data-stu-id="f102a-155">Company</span></span>  
11. <span data-ttu-id="f102a-156">No campo Tabela, digite 'CompanyInfo'.</span><span class="sxs-lookup"><span data-stu-id="f102a-156">In the Table field, type 'CompanyInfo'.</span></span>
    * <span data-ttu-id="f102a-157">CompanyInfo</span><span class="sxs-lookup"><span data-stu-id="f102a-157">CompanyInfo</span></span>  
12. <span data-ttu-id="f102a-158">Clique em OK.</span><span class="sxs-lookup"><span data-stu-id="f102a-158">Click OK.</span></span>
13. <span data-ttu-id="f102a-159">Na árvore, expanda 'Empresa'.</span><span class="sxs-lookup"><span data-stu-id="f102a-159">In the tree, expand 'Company'.</span></span>
14. <span data-ttu-id="f102a-160">Na árvore, expanda 'Empresa\find()'.</span><span class="sxs-lookup"><span data-stu-id="f102a-160">In the tree, expand 'Company\find()'.</span></span>
15. <span data-ttu-id="f102a-161">Na árvore, selecione 'Empresa\find()\Nome'.</span><span class="sxs-lookup"><span data-stu-id="f102a-161">In the tree, select 'Company\find()\Name'.</span></span>
16. <span data-ttu-id="f102a-162">Clique em Associar.</span><span class="sxs-lookup"><span data-stu-id="f102a-162">Click Bind.</span></span>
17. <span data-ttu-id="f102a-163">Clique em Salvar.</span><span class="sxs-lookup"><span data-stu-id="f102a-163">Click Save.</span></span>
18. <span data-ttu-id="f102a-164">Feche a página.</span><span class="sxs-lookup"><span data-stu-id="f102a-164">Close the page.</span></span>
19. <span data-ttu-id="f102a-165">Feche a página.</span><span class="sxs-lookup"><span data-stu-id="f102a-165">Close the page.</span></span>
20. <span data-ttu-id="f102a-166">No Painel de Ação, clique em Configurações.</span><span class="sxs-lookup"><span data-stu-id="f102a-166">On the Action Pane, click Configurations.</span></span>
21. <span data-ttu-id="f102a-167">Clique em Parâmetros de usuário.</span><span class="sxs-lookup"><span data-stu-id="f102a-167">Click User parameters.</span></span>
22. <span data-ttu-id="f102a-168">Selecione Sim no campo Executar configurações.</span><span class="sxs-lookup"><span data-stu-id="f102a-168">Select Yes in the Run settings field.</span></span>
23. <span data-ttu-id="f102a-169">Clique em OK.</span><span class="sxs-lookup"><span data-stu-id="f102a-169">Click OK.</span></span>
24. <span data-ttu-id="f102a-170">Clique em Editar.</span><span class="sxs-lookup"><span data-stu-id="f102a-170">Click Edit.</span></span>
25. <span data-ttu-id="f102a-171">Selecione Sim no campo Executar Rascunho.</span><span class="sxs-lookup"><span data-stu-id="f102a-171">Select Yes in the Run Draft field.</span></span>

## <a name="add-a-new-er-format-configuration"></a><span data-ttu-id="f102a-172">Adicionar uma nova configuração de formato de ER</span><span class="sxs-lookup"><span data-stu-id="f102a-172">Add a new ER format configuration</span></span>
1. <span data-ttu-id="f102a-173">Na árvore, selecione 'Modelo de dados de amostra'.</span><span class="sxs-lookup"><span data-stu-id="f102a-173">In the tree, select 'Sample data model'.</span></span>
2. <span data-ttu-id="f102a-174">Clique em Criar configuração para abrir a caixa de diálogo suspensa.</span><span class="sxs-lookup"><span data-stu-id="f102a-174">Click Create configuration to open the drop dialog.</span></span>
3. <span data-ttu-id="f102a-175">No campo Novo, insira 'Formato baseado no modelo de dados Modelo de dados de amostra'.</span><span class="sxs-lookup"><span data-stu-id="f102a-175">In the New field, enter 'Format based on data model Sample data model'.</span></span>
4. <span data-ttu-id="f102a-176">No campo, digite 'Formato de amostra'.</span><span class="sxs-lookup"><span data-stu-id="f102a-176">In the Name field, type 'Sample format'.</span></span>
    * <span data-ttu-id="f102a-177">Formato de amostra</span><span class="sxs-lookup"><span data-stu-id="f102a-177">Sample format</span></span>  
5. <span data-ttu-id="f102a-178">Clique em Criar configuração.</span><span class="sxs-lookup"><span data-stu-id="f102a-178">Click Create configuration.</span></span>
6. <span data-ttu-id="f102a-179">Clique em Designer.</span><span class="sxs-lookup"><span data-stu-id="f102a-179">Click Designer.</span></span>
7. <span data-ttu-id="f102a-180">Clique em Adicionar raiz para abrir a caixa de diálogo suspensa.</span><span class="sxs-lookup"><span data-stu-id="f102a-180">Click Add root to open the drop dialog.</span></span>
8. <span data-ttu-id="f102a-181">Na árvore, selecione 'Texto\Cadeia de caracteres'.</span><span class="sxs-lookup"><span data-stu-id="f102a-181">In the tree, select 'Text\String'.</span></span>
9. <span data-ttu-id="f102a-182">Clique em OK.</span><span class="sxs-lookup"><span data-stu-id="f102a-182">Click OK.</span></span>
10. <span data-ttu-id="f102a-183">Clique na aba Mapeamento.</span><span class="sxs-lookup"><span data-stu-id="f102a-183">Click the Mapping tab.</span></span>
11. <span data-ttu-id="f102a-184">Na árvore, expanda 'modelo'.</span><span class="sxs-lookup"><span data-stu-id="f102a-184">In the tree, expand 'model'.</span></span>
12. <span data-ttu-id="f102a-185">Na árvore, selecione 'modelo\Empresa'.</span><span class="sxs-lookup"><span data-stu-id="f102a-185">In the tree, select 'model\Company'.</span></span>
13. <span data-ttu-id="f102a-186">Clique em Associar.</span><span class="sxs-lookup"><span data-stu-id="f102a-186">Click Bind.</span></span>
14. <span data-ttu-id="f102a-187">Clique em Salvar.</span><span class="sxs-lookup"><span data-stu-id="f102a-187">Click Save.</span></span>
15. <span data-ttu-id="f102a-188">Feche a página.</span><span class="sxs-lookup"><span data-stu-id="f102a-188">Close the page.</span></span>
    * <span data-ttu-id="f102a-189">Executar a versão de rascunho de formato criado para fins de teste.</span><span class="sxs-lookup"><span data-stu-id="f102a-189">Run the draft version of the created format for testing purposes.</span></span>  
16. <span data-ttu-id="f102a-190">Clique em Executar.</span><span class="sxs-lookup"><span data-stu-id="f102a-190">Click Run.</span></span>
    * <span data-ttu-id="f102a-191">Em versões FastTab, clique em Executar.</span><span class="sxs-lookup"><span data-stu-id="f102a-191">On the Versions FastTab, click Run.</span></span>  
17. <span data-ttu-id="f102a-192">Clique em OK.</span><span class="sxs-lookup"><span data-stu-id="f102a-192">Click OK.</span></span>
    * <span data-ttu-id="f102a-193">Reveja a saída que contêm o nome da empresa na qual o usuário que está executando essa configuração de formato está registrado.</span><span class="sxs-lookup"><span data-stu-id="f102a-193">Review the output that contains the name of the company in which the user who is running this format configuration is logged into.</span></span> <span data-ttu-id="f102a-194">A configuração de mapeamento modelo criada será usada por essa configuração de formato porque só há uma configuração disponível que contém mapeamentos de modelo necessários.</span><span class="sxs-lookup"><span data-stu-id="f102a-194">The created model-mapping configuration is used by this format configuration because there is only one configuration available that contains required model mappings.</span></span>   

## <a name="add-alternative-er-model-mapping-configuration"></a><span data-ttu-id="f102a-195">Adicionar a configuração de mapeamento do modelo de ER alternativo</span><span class="sxs-lookup"><span data-stu-id="f102a-195">Add alternative ER model-mapping configuration</span></span>
1. <span data-ttu-id="f102a-196">Na árvore, selecione 'Modelo de dados de amostra'.</span><span class="sxs-lookup"><span data-stu-id="f102a-196">In the tree, select 'Sample data model'.</span></span>
2. <span data-ttu-id="f102a-197">Clique em Criar configuração para abrir a caixa de diálogo suspensa.</span><span class="sxs-lookup"><span data-stu-id="f102a-197">Click Create configuration to open the drop dialog.</span></span>
3. <span data-ttu-id="f102a-198">No campo Novo, insira 'Mapeamento de modelo baseado no modelo de dados Modelo de dados de amostra'.</span><span class="sxs-lookup"><span data-stu-id="f102a-198">In the New field, enter 'Model Mapping based on data model Sample data model'.</span></span>
4. <span data-ttu-id="f102a-199">No campo Nome, digite "Mapeamento de amostra (alternativo)'.</span><span class="sxs-lookup"><span data-stu-id="f102a-199">In the Name field, type 'Sample mapping (alternative)'.</span></span>
    * <span data-ttu-id="f102a-200">Mapeamento de amostra (alternativo)</span><span class="sxs-lookup"><span data-stu-id="f102a-200">Sample mapping (alternative)</span></span>  
5. <span data-ttu-id="f102a-201">Clique em Criar configuração.</span><span class="sxs-lookup"><span data-stu-id="f102a-201">Click Create configuration.</span></span>
6. <span data-ttu-id="f102a-202">Clique em Designer.</span><span class="sxs-lookup"><span data-stu-id="f102a-202">Click Designer.</span></span>
7. <span data-ttu-id="f102a-203">Clique em Designer.</span><span class="sxs-lookup"><span data-stu-id="f102a-203">Click Designer.</span></span>
8. <span data-ttu-id="f102a-204">Na árvore, selecione 'Dynamics 365 for Operations\Tabela'.</span><span class="sxs-lookup"><span data-stu-id="f102a-204">In the tree, select 'Dynamics 365 for Operations\Table'.</span></span>
9. <span data-ttu-id="f102a-205">Clique em Adicionar raiz.</span><span class="sxs-lookup"><span data-stu-id="f102a-205">Click Add root.</span></span>
10. <span data-ttu-id="f102a-206">No campo Nome, digite 'Empresa'.</span><span class="sxs-lookup"><span data-stu-id="f102a-206">In the Name field, type 'Company'.</span></span>
    * <span data-ttu-id="f102a-207">Empresa</span><span class="sxs-lookup"><span data-stu-id="f102a-207">Company</span></span>  
11. <span data-ttu-id="f102a-208">No campo Tabela, digite 'CompanyInfo'.</span><span class="sxs-lookup"><span data-stu-id="f102a-208">In the Table field, type 'CompanyInfo'.</span></span>
    * <span data-ttu-id="f102a-209">CompanyInfo</span><span class="sxs-lookup"><span data-stu-id="f102a-209">CompanyInfo</span></span>  
12. <span data-ttu-id="f102a-210">Clique em OK.</span><span class="sxs-lookup"><span data-stu-id="f102a-210">Click OK.</span></span>
13. <span data-ttu-id="f102a-211">Clique em Editar.</span><span class="sxs-lookup"><span data-stu-id="f102a-211">Click Edit.</span></span>
14. <span data-ttu-id="f102a-212">Na árvore, selecione 'Cadeia de caracteres\CONCATENATE'.</span><span class="sxs-lookup"><span data-stu-id="f102a-212">In the tree, select 'String\CONCATENATE'.</span></span>
15. <span data-ttu-id="f102a-213">Clique em Adicionar função.</span><span class="sxs-lookup"><span data-stu-id="f102a-213">Click Add function.</span></span>
16. <span data-ttu-id="f102a-214">Na árvore, expanda 'Empresa'.</span><span class="sxs-lookup"><span data-stu-id="f102a-214">In the tree, expand 'Company'.</span></span>
17. <span data-ttu-id="f102a-215">Na árvore, expanda 'Empresa\find()'.</span><span class="sxs-lookup"><span data-stu-id="f102a-215">In the tree, expand 'Company\find()'.</span></span>
18. <span data-ttu-id="f102a-216">Na árvore, selecione 'Empresa\find()\Nome'.</span><span class="sxs-lookup"><span data-stu-id="f102a-216">In the tree, select 'Company\find()\Name'.</span></span>
19. <span data-ttu-id="f102a-217">Clique em Adicionar fonte de dados.</span><span class="sxs-lookup"><span data-stu-id="f102a-217">Click Add data source.</span></span>
20. <span data-ttu-id="f102a-218">No campo Fórmula, digite um valor.</span><span class="sxs-lookup"><span data-stu-id="f102a-218">In the Formula field, type a value.</span></span>
    * <span data-ttu-id="f102a-219">CONCATENATE(Company.'find()'.Name, ";",</span><span class="sxs-lookup"><span data-stu-id="f102a-219">CONCATENATE(Company.'find()'.Name, ";",</span></span>  
21. <span data-ttu-id="f102a-220">Na árvore, selecione 'Company\find()\Company(DataArea)'.</span><span class="sxs-lookup"><span data-stu-id="f102a-220">In the tree, select 'Company\find()\Company(DataArea)'.</span></span>
22. <span data-ttu-id="f102a-221">Clique em Adicionar fonte de dados.</span><span class="sxs-lookup"><span data-stu-id="f102a-221">Click Add data source.</span></span>
23. <span data-ttu-id="f102a-222">No campo Fórmula, digite um valor.</span><span class="sxs-lookup"><span data-stu-id="f102a-222">In the Formula field, type a value.</span></span>
    * <span data-ttu-id="f102a-223">CONCATENATE(Company.'find()'.Name, ";", Company.'find()'.DataArea)</span><span class="sxs-lookup"><span data-stu-id="f102a-223">CONCATENATE(Company.'find()'.Name, ";", Company.'find()'.DataArea)</span></span>  
24. <span data-ttu-id="f102a-224">Clique em Salvar.</span><span class="sxs-lookup"><span data-stu-id="f102a-224">Click Save.</span></span>
25. <span data-ttu-id="f102a-225">Feche a página.</span><span class="sxs-lookup"><span data-stu-id="f102a-225">Close the page.</span></span>
26. <span data-ttu-id="f102a-226">Clique em Salvar.</span><span class="sxs-lookup"><span data-stu-id="f102a-226">Click Save.</span></span>
27. <span data-ttu-id="f102a-227">Feche a página.</span><span class="sxs-lookup"><span data-stu-id="f102a-227">Close the page.</span></span>
28. <span data-ttu-id="f102a-228">Feche a página.</span><span class="sxs-lookup"><span data-stu-id="f102a-228">Close the page.</span></span>
29. <span data-ttu-id="f102a-229">Selecione Sim no campo Executar Rascunho.</span><span class="sxs-lookup"><span data-stu-id="f102a-229">Select Yes in the Run Draft field.</span></span>

## <a name="use-an-existing-er-model-mapping-configuration"></a><span data-ttu-id="f102a-230">Usar uma configuração existente de mapeamento do ER</span><span class="sxs-lookup"><span data-stu-id="f102a-230">Use an existing ER model-mapping configuration</span></span>
1. <span data-ttu-id="f102a-231">Na árvore, selecione "Modelo de dados de amostra\Formato de amostra".</span><span class="sxs-lookup"><span data-stu-id="f102a-231">In the tree, select 'Sample data model\Sample format'.</span></span>
2. <span data-ttu-id="f102a-232">Clique em Executar.</span><span class="sxs-lookup"><span data-stu-id="f102a-232">Click Run.</span></span>
    * <span data-ttu-id="f102a-233">A versão de rascunho selecionada da configuração de formato de ER não pode ser realizada porque há mais de uma configuração de mapeamento de modelo disponível para o modelo de dados indefinido que foi selecionada como a fonte de dados do formato de ER de execução.</span><span class="sxs-lookup"><span data-stu-id="f102a-233">The selected draft version of the ER format configuration can't be executed because there is more than one model-mapping configuration available for the undefined data model that has been selected as the data source of the running ER format.</span></span>   
    * <span data-ttu-id="f102a-234">Em seguida, você definirá a configuração de mapeamento de modelo alternativo como aquela da qual os mapeamentos modelo serão usados como fontes de dados do formato de ER de execução.</span><span class="sxs-lookup"><span data-stu-id="f102a-234">Next, you will define the alternative model-mapping configuration as the one from which model mappings will be used as data sources for running ER format.</span></span>   
3. <span data-ttu-id="f102a-235">Na árvore, selecione "Modelo de dados de amostra\Mapeamento de amostra (alternativo)".</span><span class="sxs-lookup"><span data-stu-id="f102a-235">In the tree, select 'Sample data model\Sample mapping (alternative)'.</span></span>
4. <span data-ttu-id="f102a-236">Selecione Sim no campo Padrão do mapeamento de modelo.</span><span class="sxs-lookup"><span data-stu-id="f102a-236">Select Yes in the Default for model-mapping field.</span></span>
5. <span data-ttu-id="f102a-237">Na árvore, selecione "Modelo de dados de amostra\Formato de amostra".</span><span class="sxs-lookup"><span data-stu-id="f102a-237">In the tree, select 'Sample data model\Sample format'.</span></span>
6. <span data-ttu-id="f102a-238">Clique em Executar.</span><span class="sxs-lookup"><span data-stu-id="f102a-238">Click Run.</span></span>
7. <span data-ttu-id="f102a-239">Clique em OK.</span><span class="sxs-lookup"><span data-stu-id="f102a-239">Click OK.</span></span>
    * <span data-ttu-id="f102a-240">A configuração de mapeamento de modelo padrão será usada por essa configuração de formato para gerar o documento eletrônico (a saída criada contêm o código da empresa).</span><span class="sxs-lookup"><span data-stu-id="f102a-240">The default model-mapping configuration is used by this format configuration for generating the electronic document (the created output contains the company code).</span></span>  

