--- 
title: "Selecionar definição de modelo de dados ao criar o formato para relatório eletrônico (ER)"
description: "Para completar as etapas, neste procedimento você deve primeiro concluir o procedimento, ER Criar um provedor de configuração e marcá-lo como ativo."
author: NickSelin
manager: AnnBe
ms.date: 06/19/2017
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: kfend
ms.search.scope: Operations
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 663da58ef01b705c0c984fbfd3fce8bc31be04c6
ms.openlocfilehash: 79e5c09484f9d33106194c2a8b2c9971d58d0e75
ms.contentlocale: pt-br
ms.lasthandoff: 08/29/2017

---
# <a name="select-data-model-definition-while-creating-format-for-electronic-reporting-er"></a><span data-ttu-id="0e6e4-103">Selecionar definição de modelo de dados ao criar o formato para relatório eletrônico (ER)</span><span class="sxs-lookup"><span data-stu-id="0e6e4-103">Select data model definition while creating format for electronic reporting (ER)</span></span>

[!include[task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="0e6e4-104">Para completar as etapas, neste procedimento você deve primeiro concluir o procedimento, ER Criar um provedor de configuração e marcá-lo como ativo.</span><span class="sxs-lookup"><span data-stu-id="0e6e4-104">To complete the steps in this procedure, you must first complete the procedure, ER Create a configuration provider and mark it as active.</span></span> 

<span data-ttu-id="0e6e4-105">Este procedimento mostra como o item raiz de modelo pode ser selecionado como uma definição do modelo de dados para inserir uma configuração de formato de relatório eletrônico (ER) que é designada para gerar documentos eletrônicos.</span><span class="sxs-lookup"><span data-stu-id="0e6e4-105">This procedure shows how a model’s root item can be selected as a data model definition for inserting an Electronic reporting (ER) format configuration that is designed to generate electronic documents.</span></span> <span data-ttu-id="0e6e4-106">Neste procedimento, você irá adicionar uma nova configuração de formato de ER para a empresa exemplo, Litware, Inc.</span><span class="sxs-lookup"><span data-stu-id="0e6e4-106">In this procedure, you will add a new ER format configuration for the sample company Litware, Inc.</span></span> 

<span data-ttu-id="0e6e4-107">Esse procedimento é destinado a usuários com a função de Administrador do sistema ou Desenvolvedor de relatório eletrônico.</span><span class="sxs-lookup"><span data-stu-id="0e6e4-107">This procedure is intended for users who have the System administrator or Electronic reporting developer role assigned to them.</span></span> <span data-ttu-id="0e6e4-108">As etapas podem ser concluídas usando qualquer conjunto de dados.</span><span class="sxs-lookup"><span data-stu-id="0e6e4-108">The steps can be completed by using any dataset.</span></span>

1. <span data-ttu-id="0e6e4-109">Ir para Administração da organização > Espaços de trabalho > Relatório eletrônico.</span><span class="sxs-lookup"><span data-stu-id="0e6e4-109">Go to Organization administration > Workspaces > Electronic reporting.</span></span>
    * <span data-ttu-id="0e6e4-110">Verifique se o provedor de configuração da empresa exemplo, Litware, Inc., está disponível e marcado como Ativo.</span><span class="sxs-lookup"><span data-stu-id="0e6e4-110">Make sure that the configuration provider for the sample company, Litware, Inc., is available and marked as Active.</span></span> <span data-ttu-id="0e6e4-111">Se não visualizar este provedor de configuração, conclua as etapas no procedimento Criar um provedor de configuração e marcá-lo como ativo.</span><span class="sxs-lookup"><span data-stu-id="0e6e4-111">If you don’t see this configuration provider, complete the steps in the procedure, Create a configuration provider and mark it as active.</span></span>  
2. <span data-ttu-id="0e6e4-112">Clique em Configurações de relatórios.</span><span class="sxs-lookup"><span data-stu-id="0e6e4-112">Click Reporting configurations.</span></span>

## <a name="add-a-new-er-data-model-configuration"></a><span data-ttu-id="0e6e4-113">Adicionar uma nova configuração de modelo de dados do ER</span><span class="sxs-lookup"><span data-stu-id="0e6e4-113">Add a new ER data model configuration</span></span>
1. <span data-ttu-id="0e6e4-114">Clique em Criar configuração para abrir a caixa de diálogo suspensa.</span><span class="sxs-lookup"><span data-stu-id="0e6e4-114">Click Create configuration to open the drop dialog.</span></span>
    * <span data-ttu-id="0e6e4-115">Adicionamos uma nova configuração do modelo de ER que contém o modelo de dados criado para ser usado como a fonte de dados para geração de relatórios de ER.</span><span class="sxs-lookup"><span data-stu-id="0e6e4-115">We add a new ER model configuration containing a data model that is designed to be used as data source for generation ER reports.</span></span>  
2. <span data-ttu-id="0e6e4-116">No campo Nome, digite 'Modelo de pagamento (fictício)'.</span><span class="sxs-lookup"><span data-stu-id="0e6e4-116">In the Name field, type 'Payment model (fictitious)'.</span></span>
    * <span data-ttu-id="0e6e4-117">Modelo de pagamento (fictício)</span><span class="sxs-lookup"><span data-stu-id="0e6e4-117">Payment model (fictitious)</span></span>  
3. <span data-ttu-id="0e6e4-118">Clique em Criar configuração.</span><span class="sxs-lookup"><span data-stu-id="0e6e4-118">Click Create configuration.</span></span>
4. <span data-ttu-id="0e6e4-119">Clique em Designer.</span><span class="sxs-lookup"><span data-stu-id="0e6e4-119">Click Designer.</span></span>
    * <span data-ttu-id="0e6e4-120">Abra o designer de ER para especificar a estrutura do modelo de dados dessa configuração.</span><span class="sxs-lookup"><span data-stu-id="0e6e4-120">Open the ER designer to specify the structure of data model of this configuration.</span></span>  
    * <span data-ttu-id="0e6e4-121">Suponha que criamos o modelo de dados para o domínio comercial de pagamentos para suportar 2 métodos de pagamento – transferência de crédito e débito direto.</span><span class="sxs-lookup"><span data-stu-id="0e6e4-121">Assume that we design the data model for payments business domain to support 2 payment methods – credit transfer and direct debit ones.</span></span>  
5. <span data-ttu-id="0e6e4-122">Clique em Novo para abrir a caixa de diálogo suspensa.</span><span class="sxs-lookup"><span data-stu-id="0e6e4-122">Click New to open the drop dialog.</span></span>
6. <span data-ttu-id="0e6e4-123">No campo Nome, digite 'Pagamentos - transferência de crédito'.</span><span class="sxs-lookup"><span data-stu-id="0e6e4-123">In the Name field, type 'Payments – credit transfer'.</span></span>
    * <span data-ttu-id="0e6e4-124">Pagamentos - transferência de crédito</span><span class="sxs-lookup"><span data-stu-id="0e6e4-124">Payments – credit transfer</span></span>  
7. <span data-ttu-id="0e6e4-125">Clique em Adicionar.</span><span class="sxs-lookup"><span data-stu-id="0e6e4-125">Click Add.</span></span>
8. <span data-ttu-id="0e6e4-126">Clique em Novo para abrir a caixa de diálogo suspensa.</span><span class="sxs-lookup"><span data-stu-id="0e6e4-126">Click New to open the drop dialog.</span></span>
9. <span data-ttu-id="0e6e4-127">No campo Novo nó como um, insira "Raiz do modelo".</span><span class="sxs-lookup"><span data-stu-id="0e6e4-127">In the New node as a field, enter 'Model root'.</span></span>
10. <span data-ttu-id="0e6e4-128">No campo Nome, digite 'Pagamentos - débito direto'.</span><span class="sxs-lookup"><span data-stu-id="0e6e4-128">In the Name field, type 'Payments – direct debit'.</span></span>
    * <span data-ttu-id="0e6e4-129">Pagamentos - débito direto</span><span class="sxs-lookup"><span data-stu-id="0e6e4-129">Payments – direct debit</span></span>  
11. <span data-ttu-id="0e6e4-130">Clique em Adicionar.</span><span class="sxs-lookup"><span data-stu-id="0e6e4-130">Click Add.</span></span>
12. <span data-ttu-id="0e6e4-131">Clique em Salvar.</span><span class="sxs-lookup"><span data-stu-id="0e6e4-131">Click Save.</span></span>
13. <span data-ttu-id="0e6e4-132">Feche a página.</span><span class="sxs-lookup"><span data-stu-id="0e6e4-132">Close the page.</span></span>
14. <span data-ttu-id="0e6e4-133">Clique em Alterar status.</span><span class="sxs-lookup"><span data-stu-id="0e6e4-133">Click Change status.</span></span>
    * <span data-ttu-id="0e6e4-134">Preencha a versão de rascunho do modelo para disponibilizá-lo nos novos mapeamentos e formatos do modelo.</span><span class="sxs-lookup"><span data-stu-id="0e6e4-134">Complete the draft version of the model to make it available in new model mappings and formats.</span></span>  
15. <span data-ttu-id="0e6e4-135">Clique em Concluir.</span><span class="sxs-lookup"><span data-stu-id="0e6e4-135">Click Complete.</span></span>
16. <span data-ttu-id="0e6e4-136">Clique em OK.</span><span class="sxs-lookup"><span data-stu-id="0e6e4-136">Click OK.</span></span>

## <a name="start-to-enter-a-new-er-format-configuration"></a><span data-ttu-id="0e6e4-137">Começar a inserir uma nova configuração de formato de ER</span><span class="sxs-lookup"><span data-stu-id="0e6e4-137">Start to enter a new ER format configuration</span></span>
1. <span data-ttu-id="0e6e4-138">Clique em Criar configuração para abrir a caixa de diálogo suspensa.</span><span class="sxs-lookup"><span data-stu-id="0e6e4-138">Click Create configuration to open the drop dialog.</span></span>
2. <span data-ttu-id="0e6e4-139">No campo Novo, insira 'Formato baseado no modelo de dados Modelo de pagamento (fictício)'.</span><span class="sxs-lookup"><span data-stu-id="0e6e4-139">In the New field, enter 'Format based on data model Payment model (fictitious)'.</span></span>
3. <span data-ttu-id="0e6e4-140">No campo Definição do modelo de dados, insira ou selecione um valor.</span><span class="sxs-lookup"><span data-stu-id="0e6e4-140">In the Data model definition field, enter or select a value.</span></span>
    * <span data-ttu-id="0e6e4-141">Observe que todos os itens raiz do modelo de dados selecionado estão disponíveis atualmente para seleção como uma definição do modelo de dados.</span><span class="sxs-lookup"><span data-stu-id="0e6e4-141">Note that all root items of the selected data model are currently available for selection as a data model definition.</span></span> <span data-ttu-id="0e6e4-142">Você pode continuar a criar seu formato usando alguns itens raiz necessários do modelo de dados.</span><span class="sxs-lookup"><span data-stu-id="0e6e4-142">You can continue to design your format by using any of the required root items of the data model.</span></span> <span data-ttu-id="0e6e4-143">Um mapeamento de modelo ausente para o item raiz selecionado não impede que você prossiga.</span><span class="sxs-lookup"><span data-stu-id="0e6e4-143">A missing model mapping for the selected root item doesn't prevent you from continuing.</span></span>  
4. <span data-ttu-id="0e6e4-144">Feche a página.</span><span class="sxs-lookup"><span data-stu-id="0e6e4-144">Close the page.</span></span>

## <a name="add-a-new-er-model-mapping-configuration"></a><span data-ttu-id="0e6e4-145">Adicionar uma nova configuração de mapeamento do modelo de ER</span><span class="sxs-lookup"><span data-stu-id="0e6e4-145">Add a new ER model mapping configuration</span></span>
1. <span data-ttu-id="0e6e4-146">Clique em Criar configuração para abrir a caixa de diálogo suspensa.</span><span class="sxs-lookup"><span data-stu-id="0e6e4-146">Click Create configuration to open the drop dialog.</span></span>
2. <span data-ttu-id="0e6e4-147">No campo Novo, insira 'Mapeamento de modelo baseado no modelo de dados Modelo de pagamento (fictício)'.</span><span class="sxs-lookup"><span data-stu-id="0e6e4-147">In the New field, enter 'Model Mapping based on data model Payment model (fictitious)'.</span></span>
3. <span data-ttu-id="0e6e4-148">No campo Nome, digite 'Mapeamento de modelo de pagamento (fictício)'.</span><span class="sxs-lookup"><span data-stu-id="0e6e4-148">In the Name field, type 'Payment model mappings (fictitious)'.</span></span>
    * <span data-ttu-id="0e6e4-149">Mapeamentos de modelo de pagamento (fictício)</span><span class="sxs-lookup"><span data-stu-id="0e6e4-149">Payment model mappings (fictitious)</span></span>  
4. <span data-ttu-id="0e6e4-150">No campo Definição do modelo de dados, insira ou selecione um valor.</span><span class="sxs-lookup"><span data-stu-id="0e6e4-150">In the Data model definition field, enter or select a value.</span></span>
5. <span data-ttu-id="0e6e4-151">Clique em Criar configuração.</span><span class="sxs-lookup"><span data-stu-id="0e6e4-151">Click Create configuration.</span></span>

## <a name="design-er-model-mappings"></a><span data-ttu-id="0e6e4-152">Criar mapeamentos de modelo de ER</span><span class="sxs-lookup"><span data-stu-id="0e6e4-152">Design ER model mappings</span></span>
1. <span data-ttu-id="0e6e4-153">Clique em Designer.</span><span class="sxs-lookup"><span data-stu-id="0e6e4-153">Click Designer.</span></span>
    * <span data-ttu-id="0e6e4-154">Use o designer de ER para especificar os mapeamentos de modelo para os itens raiz necessários.</span><span class="sxs-lookup"><span data-stu-id="0e6e4-154">Use the ER designer to specify the model mappings for the required root items.</span></span>  
2. <span data-ttu-id="0e6e4-155">Clique em Designer.</span><span class="sxs-lookup"><span data-stu-id="0e6e4-155">Click Designer.</span></span>
    * <span data-ttu-id="0e6e4-156">Simule a definição de mapeamento de modelo selecionado para o item da raiz do modelo selecionado.</span><span class="sxs-lookup"><span data-stu-id="0e6e4-156">Simulate setting of selected model mapping for the selected model’s root item.</span></span>  
3. <span data-ttu-id="0e6e4-157">Na árvore, selecione "Dynamics 365 for Operations\Registros da tabela".</span><span class="sxs-lookup"><span data-stu-id="0e6e4-157">In the tree, select 'Dynamics 365 for Operations\Table records'.</span></span>
4. <span data-ttu-id="0e6e4-158">Clique em Adicionar raiz.</span><span class="sxs-lookup"><span data-stu-id="0e6e4-158">Click Add root.</span></span>
5. <span data-ttu-id="0e6e4-159">No campo Nome, digite 'Razão'.</span><span class="sxs-lookup"><span data-stu-id="0e6e4-159">In the Name field, type 'Ledger'.</span></span>
6. <span data-ttu-id="0e6e4-160">No campo Tabela, digite 'LedgerJournalTrans'.</span><span class="sxs-lookup"><span data-stu-id="0e6e4-160">In the Table field, type 'LedgerJournalTrans'.</span></span>
    * <span data-ttu-id="0e6e4-161">LedgerJournalTrans</span><span class="sxs-lookup"><span data-stu-id="0e6e4-161">LedgerJournalTrans</span></span>  
7. <span data-ttu-id="0e6e4-162">Clique em OK.</span><span class="sxs-lookup"><span data-stu-id="0e6e4-162">Click OK.</span></span>
8. <span data-ttu-id="0e6e4-163">Clique em Salvar.</span><span class="sxs-lookup"><span data-stu-id="0e6e4-163">Click Save.</span></span>
9. <span data-ttu-id="0e6e4-164">Feche a página.</span><span class="sxs-lookup"><span data-stu-id="0e6e4-164">Close the page.</span></span>
10. <span data-ttu-id="0e6e4-165">Feche a página.</span><span class="sxs-lookup"><span data-stu-id="0e6e4-165">Close the page.</span></span>

## <a name="start-to-enter-another-new-er-format-configuration"></a><span data-ttu-id="0e6e4-166">Começar a inserir outra nova configuração de formato de ER</span><span class="sxs-lookup"><span data-stu-id="0e6e4-166">Start to enter another new ER format configuration</span></span>
1. <span data-ttu-id="0e6e4-167">Na árvore, selecione 'Modelo de pagamento (fictício)'.</span><span class="sxs-lookup"><span data-stu-id="0e6e4-167">In the tree, select 'Payment model (fictitious)'.</span></span>
2. <span data-ttu-id="0e6e4-168">Clique em Criar configuração para abrir a caixa de diálogo suspensa.</span><span class="sxs-lookup"><span data-stu-id="0e6e4-168">Click Create configuration to open the drop dialog.</span></span>
3. <span data-ttu-id="0e6e4-169">No campo Novo, insira 'Formato baseado no modelo de dados Modelo de pagamento (fictício)'.</span><span class="sxs-lookup"><span data-stu-id="0e6e4-169">In the New field, enter 'Format based on data model Payment model (fictitious)'.</span></span>
4. <span data-ttu-id="0e6e4-170">No campo Definição do modelo de dados, insira ou selecione um valor.</span><span class="sxs-lookup"><span data-stu-id="0e6e4-170">In the Data model definition field, enter or select a value.</span></span>
    * <span data-ttu-id="0e6e4-171">Observe que agora um só item raiz está disponível para mapear fontes de dados do aplicativo.</span><span class="sxs-lookup"><span data-stu-id="0e6e4-171">Note that now only one root item is available to map to the application data sources.</span></span> <span data-ttu-id="0e6e4-172">Quando pelo menos um mapeamento de modelo foi introduzido, somente os itens raiz de modelo que são mapeados para fontes de dados do aplicativo poderão ser selecionados como uma definição modelo, quando o formato de ER for adicionado.</span><span class="sxs-lookup"><span data-stu-id="0e6e4-172">When at least one model mapping is introduced, only the model’s root items that are mapped to application data sources can be selected as a model definition while the ER format is added.</span></span>   
5. <span data-ttu-id="0e6e4-173">Feche a página.</span><span class="sxs-lookup"><span data-stu-id="0e6e4-173">Close the page.</span></span>


