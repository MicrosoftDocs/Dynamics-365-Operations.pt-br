---
title: "Configurar pré-requisitos para gerenciamento"
description: "Use este procedimento para habilitar processos de gerenciamento de não conformidade."
author: perlynne
manager: AnnBe
ms.date: 06/07/2016
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: YuyuScheller
ms.search.scope: Operations
ms.search.region: Global
ms.search.industry: Distribution
ms.author: perlynne
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 0e7f66cccd76e5326fce75d1a13aff294c16fb9b
ms.openlocfilehash: 842a9441158defca74d1b203a1b2509773ba8919
ms.contentlocale: pt-br
ms.lasthandoff: 09/12/2017

---
# <a name="set-up-prerequisites-for-management"></a><span data-ttu-id="c52e6-103">Configurar pré-requisitos para gerenciamento</span><span class="sxs-lookup"><span data-stu-id="c52e6-103">Set up prerequisites for management</span></span>

[!include[task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="c52e6-104">Use este procedimento para habilitar processos de gerenciamento de não conformidade.</span><span class="sxs-lookup"><span data-stu-id="c52e6-104">Use this procedure to enable nonconformance management processes.</span></span> <span data-ttu-id="c52e6-105">Uma não conformidade descreve um item ou um procedimento com um problema de qualidade, na qual as informações descritivas incluem a origem e o tipo do problema.</span><span class="sxs-lookup"><span data-stu-id="c52e6-105">A nonconformance describes a procedure or item that has a quality problem, where the descriptive information includes the source and type of problem.</span></span> <span data-ttu-id="c52e6-106">Este procedimento usa a empresa de dados de demonstração USMF.</span><span class="sxs-lookup"><span data-stu-id="c52e6-106">This procedure uses the USMF demo data company.</span></span> <span data-ttu-id="c52e6-107">Esse procedimento geralmente é realizado por um gerente de qualidade.</span><span class="sxs-lookup"><span data-stu-id="c52e6-107">This procedure is typically performed by a quality manager.</span></span>


## <a name="enable-quality-management-processes-within-the-company"></a><span data-ttu-id="c52e6-108">Habilitar processos de gerenciamento de qualidade na empresa</span><span class="sxs-lookup"><span data-stu-id="c52e6-108">Enable quality management processes within the company</span></span>
1. <span data-ttu-id="c52e6-109">Vá para Gerenciamento de estoque > Configuração > Parâmetros de gerenciamento de depósito e estoque.</span><span class="sxs-lookup"><span data-stu-id="c52e6-109">Go to Inventory management > Setup > Inventory and warehouse management parameters.</span></span>
2. <span data-ttu-id="c52e6-110">Clique na guia gerenciamento de qualidade.</span><span class="sxs-lookup"><span data-stu-id="c52e6-110">Click the Quality management tab.</span></span>
3. <span data-ttu-id="c52e6-111">Selecione Sim no campo Usar gerenciamento de qualidade.</span><span class="sxs-lookup"><span data-stu-id="c52e6-111">Select Yes in the Use quality management field.</span></span>
    * <span data-ttu-id="c52e6-112">Selecione este parâmetro para habilitar processos de gerenciamento de qualidade para a empresa.</span><span class="sxs-lookup"><span data-stu-id="c52e6-112">Select this parameter to enable quality management processes for the company.</span></span>  
4. <span data-ttu-id="c52e6-113">No campo Preço por hora, digite um número.</span><span class="sxs-lookup"><span data-stu-id="c52e6-113">In the Hourly rate field, enter a number.</span></span>
    * <span data-ttu-id="c52e6-114">Use o campo Preço por hora para inserir um preço de mão de obra por hora na moeda local.</span><span class="sxs-lookup"><span data-stu-id="c52e6-114">Use the Hourly rate field to enter an hourly labor rate in the local currency.</span></span> <span data-ttu-id="c52e6-115">O preço por hora é usado para calcular o custo de operações relacionadas à não conformidade.</span><span class="sxs-lookup"><span data-stu-id="c52e6-115">The hourly rate is used for calculating costs for operations that are related to a nonconformance.</span></span> <span data-ttu-id="c52e6-116">O preço por hora e os custos calculados fornecem informações de referência para uma não conformidade e não interagem com outras funcionalidades.</span><span class="sxs-lookup"><span data-stu-id="c52e6-116">The hourly rate and calculated costs provide reference information for a nonconformance, and they do not interact with other functionality.</span></span>  
5. <span data-ttu-id="c52e6-117">Clique em Configuração de relatório.</span><span class="sxs-lookup"><span data-stu-id="c52e6-117">Click Report setup.</span></span>
    * <span data-ttu-id="c52e6-118">Esta página permite que você defina os tipos de nota de relatório de qualidade que serão usados em diferentes tipos de relatórios de gerenciamento de qualidade.</span><span class="sxs-lookup"><span data-stu-id="c52e6-118">This page allows you define the quality report note types that will be used on different kinds of quality management reports.</span></span>  
6. <span data-ttu-id="c52e6-119">Feche a página.</span><span class="sxs-lookup"><span data-stu-id="c52e6-119">Close the page.</span></span>
7. <span data-ttu-id="c52e6-120">Feche a página.</span><span class="sxs-lookup"><span data-stu-id="c52e6-120">Close the page.</span></span>

## <a name="enable-user-for-nonconformance-processing"></a><span data-ttu-id="c52e6-121">Habilite o usuário para processar não conformidade</span><span class="sxs-lookup"><span data-stu-id="c52e6-121">Enable user for nonconformance processing</span></span>
1. <span data-ttu-id="c52e6-122">Vá para Administração do sistema > Usuários > Usuários.</span><span class="sxs-lookup"><span data-stu-id="c52e6-122">Go to System administration > Users > Users.</span></span>
    * <span data-ttu-id="c52e6-123">Para processar a aprovação de uma não conformidade, o usuário que aprova ou rejeita as não conformidades deve ter um valor de “Nome“ atribuído na página Usuários.</span><span class="sxs-lookup"><span data-stu-id="c52e6-123">To process the approval of a nonconformance the user who  approves or rejects nonconformances must have a “Name” value assigned on the Users page.</span></span> <span data-ttu-id="c52e6-124">Para usar as notas do documento, o usuário também deve ter o Manuseio de documentos ativado nas opções do usuário.</span><span class="sxs-lookup"><span data-stu-id="c52e6-124">To use the document notes, the user must also have Document handling activated in the user options.</span></span>  
2. <span data-ttu-id="c52e6-125">Use o Filtro Rápido para localizar registros.</span><span class="sxs-lookup"><span data-stu-id="c52e6-125">Use the Quick Filter to find records.</span></span> <span data-ttu-id="c52e6-126">Por exemplo, filtre no campo Nome com um valor de "Ricardo".</span><span class="sxs-lookup"><span data-stu-id="c52e6-126">For example, filter on the Name field with a value of 'Ricardo'.</span></span>
    * <span data-ttu-id="c52e6-127">Use o filtro para localizar o usuário que aprovará ou rejeitará os registros de não conformidade.</span><span class="sxs-lookup"><span data-stu-id="c52e6-127">Use the filter to find the user who will be approving or rejecting the nonconformance records.</span></span>  
3. <span data-ttu-id="c52e6-128">Na lista, clique no link na linha selecionada.</span><span class="sxs-lookup"><span data-stu-id="c52e6-128">In the list, click the link in the selected row.</span></span>
    * <span data-ttu-id="c52e6-129">Para processar a aprovação de uma não conformidade, certifique-se de que o usuário que aprova ou rejeita as não conformidades tem um valor de “Nome“ atribuído na página Usuários.</span><span class="sxs-lookup"><span data-stu-id="c52e6-129">To process the approval of a nonconformance, make sure the user who approves or rejects nonconformances has a “Name” value assigned on the Users page.</span></span>  
4. <span data-ttu-id="c52e6-130">Clique em Opções do usuário.</span><span class="sxs-lookup"><span data-stu-id="c52e6-130">Click User options.</span></span>
5. <span data-ttu-id="c52e6-131">Clique na guia Preferências.</span><span class="sxs-lookup"><span data-stu-id="c52e6-131">Click the Preferences tab.</span></span>
6. <span data-ttu-id="c52e6-132">Selecione Sim no campo Habilitar manuseio de documento.</span><span class="sxs-lookup"><span data-stu-id="c52e6-132">Select Yes in the Enable document handling field.</span></span>
    * <span data-ttu-id="c52e6-133">Para usar as notas do documento, o usuário também deve ter o Manuseio de documentos ativado nas opções do usuário.</span><span class="sxs-lookup"><span data-stu-id="c52e6-133">To use the document notes, the user must also have Document handling activated in the user options.</span></span>  
7. <span data-ttu-id="c52e6-134">Feche a página.</span><span class="sxs-lookup"><span data-stu-id="c52e6-134">Close the page.</span></span>
8. <span data-ttu-id="c52e6-135">Feche a página.</span><span class="sxs-lookup"><span data-stu-id="c52e6-135">Close the page.</span></span>
9. <span data-ttu-id="c52e6-136">Feche a página.</span><span class="sxs-lookup"><span data-stu-id="c52e6-136">Close the page.</span></span>

## <a name="define-diagnostic-types-for-nonconformance-processing"></a><span data-ttu-id="c52e6-137">Defina tipos de diagnóstico para o processamento de não conformidade</span><span class="sxs-lookup"><span data-stu-id="c52e6-137">Define diagnostic types for nonconformance processing</span></span>
1. <span data-ttu-id="c52e6-138">Vá para Gerenciamento de estoque > Configuração > Gerenciamento de qualidade > Tipos de diagnósticos.</span><span class="sxs-lookup"><span data-stu-id="c52e6-138">Go to Inventory management > Setup > Quality management > Diagnostic types.</span></span>
    * <span data-ttu-id="c52e6-139">Use a página Tipos de diagnóstico para definir uma classificação de ações de diagnóstico.</span><span class="sxs-lookup"><span data-stu-id="c52e6-139">Use the Diagnostic types page to define a classification of diagnostic actions.</span></span> <span data-ttu-id="c52e6-140">Uma correção identifica o tipo de ação de diagnóstico que deve ser tomada em uma não conformidade aprovada, quem deve realizá-la e a data de solicitação e de conclusão planejada.</span><span class="sxs-lookup"><span data-stu-id="c52e6-140">A correction identifies what type of diagnostic action should be taken on an approved nonconformance, who should perform it, and the requested and planned completion date.</span></span>  
2. <span data-ttu-id="c52e6-141">Clique em Novo.</span><span class="sxs-lookup"><span data-stu-id="c52e6-141">Click New.</span></span>
3. <span data-ttu-id="c52e6-142">No campo Diagnóstico, digite um valor.</span><span class="sxs-lookup"><span data-stu-id="c52e6-142">In the Diagnostic field, type a value.</span></span>
4. <span data-ttu-id="c52e6-143">No campo Descrição, digite um valor.</span><span class="sxs-lookup"><span data-stu-id="c52e6-143">In the Description field, type a value.</span></span>
5. <span data-ttu-id="c52e6-144">Feche a página.</span><span class="sxs-lookup"><span data-stu-id="c52e6-144">Close the page.</span></span>

## <a name="define-quality-charges-for-nonconformance-processing"></a><span data-ttu-id="c52e6-145">Defina encargos de qualidade para o processamento de não conformidade</span><span class="sxs-lookup"><span data-stu-id="c52e6-145">Define quality charges for nonconformance processing</span></span>
1. <span data-ttu-id="c52e6-146">Vá para Gerenciamento de estoque > Configuração > Gerenciamento de qualidade > Encargos de qualidade.</span><span class="sxs-lookup"><span data-stu-id="c52e6-146">Go to Inventory management > Setup > Quality management > Quality charges.</span></span>
    * <span data-ttu-id="c52e6-147">Use a página Encargos de qualidade para definir a classificação de encargos que serão usados em operações relacionadas a não conformidade.</span><span class="sxs-lookup"><span data-stu-id="c52e6-147">Use the Quality charges page to define a classification of charges that will used in operations related to nonconformances.</span></span>  
2. <span data-ttu-id="c52e6-148">Clique em Novo.</span><span class="sxs-lookup"><span data-stu-id="c52e6-148">Click New.</span></span>
3. <span data-ttu-id="c52e6-149">No campo Código de encargo, digite um valor.</span><span class="sxs-lookup"><span data-stu-id="c52e6-149">In the Charges code field, type a value.</span></span>
4. <span data-ttu-id="c52e6-150">No campo Descrição, digite um valor.</span><span class="sxs-lookup"><span data-stu-id="c52e6-150">In the Description field, type a value.</span></span>
5. <span data-ttu-id="c52e6-151">Feche a página.</span><span class="sxs-lookup"><span data-stu-id="c52e6-151">Close the page.</span></span>

## <a name="define-the-operations-for-nonconformance-processing"></a><span data-ttu-id="c52e6-152">Defina as operações para o processamento de não conformidade</span><span class="sxs-lookup"><span data-stu-id="c52e6-152">Define the operations for nonconformance processing</span></span>
1. <span data-ttu-id="c52e6-153">Vá para Gerenciamento de estoque > Configuração > Gerenciamento de qualidade > Operações.</span><span class="sxs-lookup"><span data-stu-id="c52e6-153">Go to Inventory management > Setup > Quality management > Operations.</span></span>
    * <span data-ttu-id="c52e6-154">Use a página Operações para definir uma classificação do trabalho que pode ser realizado para uma não conformidade aprovada.</span><span class="sxs-lookup"><span data-stu-id="c52e6-154">Use the Operations page to define a classification of the work that may be performed for an approved nonconformance.</span></span> <span data-ttu-id="c52e6-155">Quando você relaciona uma operação relacionada a uma não conformidade, você pode definir informações sobre o material associado, as horas de mão-de-obra e os encargos diversos necessários para executar a operação.</span><span class="sxs-lookup"><span data-stu-id="c52e6-155">When you relate an operation to a nonconformance, you can define information about the associated material, labor hours, and miscellaneous charges that are required to perform the operation.</span></span> <span data-ttu-id="c52e6-156">Essas informações fornecem a base para calcular um custo estimado para executar a operação.</span><span class="sxs-lookup"><span data-stu-id="c52e6-156">This information provides the basis for calculating an estimated cost for performing the operation.</span></span>  
2. <span data-ttu-id="c52e6-157">Clique em Novo.</span><span class="sxs-lookup"><span data-stu-id="c52e6-157">Click New.</span></span>
3. <span data-ttu-id="c52e6-158">No campo Operação, digite um valor.</span><span class="sxs-lookup"><span data-stu-id="c52e6-158">In the Operation field, type a value.</span></span>
4. <span data-ttu-id="c52e6-159">No campo Descrição, digite um valor.</span><span class="sxs-lookup"><span data-stu-id="c52e6-159">In the Description field, type a value.</span></span>
5. <span data-ttu-id="c52e6-160">Feche a página.</span><span class="sxs-lookup"><span data-stu-id="c52e6-160">Close the page.</span></span>

## <a name="define-problem-types-for-nonconformance-processing"></a><span data-ttu-id="c52e6-161">Defina tipos de problema para o processamento de não conformidade</span><span class="sxs-lookup"><span data-stu-id="c52e6-161">Define problem types for nonconformance processing</span></span>
1. <span data-ttu-id="c52e6-162">Vá para Gerenciamento de estoque > Configuração > Gerenciamento de qualidade > Tipos de problemas.</span><span class="sxs-lookup"><span data-stu-id="c52e6-162">Go to Inventory management > Setup > Quality management > Problem types.</span></span>
    * <span data-ttu-id="c52e6-163">Use a página Tipos de problema para definir uma classificação dos problemas de qualidade que são encontrados nos vários tipos de não conformidade.</span><span class="sxs-lookup"><span data-stu-id="c52e6-163">Use the Problem types page to define a classification of quality problems that are encountered in the various nonconformance types.</span></span> <span data-ttu-id="c52e6-164">Os tipos de não conformidade incluem: Interno, Cliente, Fornecedor, Solicitação de serviço, Produção e Produção do coproduto.</span><span class="sxs-lookup"><span data-stu-id="c52e6-164">The nonconformance types include Internal, Customer, Vendor, Service request, Production, and Co-product production.</span></span> <span data-ttu-id="c52e6-165">Um único tipo de problema pode ser associado aos vários tipos de não conformidade.</span><span class="sxs-lookup"><span data-stu-id="c52e6-165">A single problem type can be associated with multiple nonconformance types.</span></span>  
2. <span data-ttu-id="c52e6-166">Clique em Novo.</span><span class="sxs-lookup"><span data-stu-id="c52e6-166">Click New.</span></span>
3. <span data-ttu-id="c52e6-167">No campo Tipo de problema, digite um valor.</span><span class="sxs-lookup"><span data-stu-id="c52e6-167">In the Problem type field, type a value.</span></span>
4. <span data-ttu-id="c52e6-168">No campo Descrição, digite um valor.</span><span class="sxs-lookup"><span data-stu-id="c52e6-168">In the Description field, type a value.</span></span>
5. <span data-ttu-id="c52e6-169">Clique em Tipos de não conformidade.</span><span class="sxs-lookup"><span data-stu-id="c52e6-169">Click Non conformance types.</span></span>
    * <span data-ttu-id="c52e6-170">Use a página Tipos de não conformidade para autorizar o uso de um tipo de problema para um ou vários tipos de não conformidade.</span><span class="sxs-lookup"><span data-stu-id="c52e6-170">Use the Non conformance types page to authorize the use of a problem type for one or more of the nonconformance types.</span></span> <span data-ttu-id="c52e6-171">Por exemplo, um tipo de problema relacionado a um código de defeito pode ser aplicado a todos os tipos de não conformidade, enquanto um tipo de problema sobre reclamações do cliente só pode ser aplicado aos tipos de não conformidade de cliente e solicitação de serviço.</span><span class="sxs-lookup"><span data-stu-id="c52e6-171">For example, a problem type regarding a defect code could apply to all nonconformance types, whereas a problem type about customer complaints may only apply to the customer and service request nonconformance types.</span></span>  
6. <span data-ttu-id="c52e6-172">Clique em Novo.</span><span class="sxs-lookup"><span data-stu-id="c52e6-172">Click New.</span></span>
7. <span data-ttu-id="c52e6-173">Na lista, marque a linha selecionada.</span><span class="sxs-lookup"><span data-stu-id="c52e6-173">In the list, mark the selected row.</span></span>
8. <span data-ttu-id="c52e6-174">No campo Tipo de não conformidade, selecione uma opção.</span><span class="sxs-lookup"><span data-stu-id="c52e6-174">In the Non conformance type field, select an option.</span></span>
9. <span data-ttu-id="c52e6-175">Feche a página.</span><span class="sxs-lookup"><span data-stu-id="c52e6-175">Close the page.</span></span>
10. <span data-ttu-id="c52e6-176">Feche a página.</span><span class="sxs-lookup"><span data-stu-id="c52e6-176">Close the page.</span></span>

## <a name="define-quarantine-zones-for-nonconformance-processing"></a><span data-ttu-id="c52e6-177">Defina zonas de quarentena para o processamento de não conformidade</span><span class="sxs-lookup"><span data-stu-id="c52e6-177">Define quarantine zones for nonconformance processing</span></span>
1. <span data-ttu-id="c52e6-178">Vá para Gerenciamento de estoque > Configuração > Gerenciamento de qualidade > Zonas de quarentena.</span><span class="sxs-lookup"><span data-stu-id="c52e6-178">Go to Inventory management > Setup > Quality management > Quarantine zones.</span></span>
2. <span data-ttu-id="c52e6-179">Clique em Novo.</span><span class="sxs-lookup"><span data-stu-id="c52e6-179">Click New.</span></span>
3. <span data-ttu-id="c52e6-180">No campo Zona de quarentena, digite um valor.</span><span class="sxs-lookup"><span data-stu-id="c52e6-180">In the Quarantine zone field, type a value.</span></span>
4. <span data-ttu-id="c52e6-181">No campo Descrição, digite um valor.</span><span class="sxs-lookup"><span data-stu-id="c52e6-181">In the Description field, type a value.</span></span>
5. <span data-ttu-id="c52e6-182">Feche a página.</span><span class="sxs-lookup"><span data-stu-id="c52e6-182">Close the page.</span></span>

