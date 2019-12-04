---
title: Criar configurações de ER para importar dados de arquivos CSV externos
description: Use este procedimento para criar configurações de ER (relatório eletrônico) para importar dados para o aplicativo do Finance and Operations de um arquivo externo em formato CSV.
author: NickSelin
manager: AnnBe
ms.date: 12/12/2017
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
audience: Application User
ms.reviewer: kfend
ms.search.scope: Operations
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: cf27590d80bbaf7749a0b6e69adc63ddcf4f9380
ms.sourcegitcommit: 3ba95d50b8262fa0f43d4faad76adac4d05eb3ea
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/27/2019
ms.locfileid: "2185143"
---
# <a name="design-er-configurations-to-import-data-from-external-csv-files"></a><span data-ttu-id="fc102-103">Criar configurações de ER para importar dados de arquivos CSV externos</span><span class="sxs-lookup"><span data-stu-id="fc102-103">Design ER configurations to import data from external CSV files</span></span>

[!include [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="fc102-104">Use este procedimento para criar configurações de ER (relatório eletrônico) para importar dados para o aplicativo de um arquivo externo em formato CSV.</span><span class="sxs-lookup"><span data-stu-id="fc102-104">Use this procedure to design Electronic reporting (ER) configurations to import data in to the application from an external file in CSV format.</span></span> <span data-ttu-id="fc102-105">Neste procedimento, você criará as configurações de ER necessárias para a empresa exemplo, Litware, Inc. Para concluir estas etapas, você deverá primeiramente concluir as etapas no procedimento, "ER Criar um provedor configuração e marcá-lo como ativo".</span><span class="sxs-lookup"><span data-stu-id="fc102-105">In this procedure, you will create the required ER configurations for the sample company, Litware, Inc. To complete these steps, you must first complete the steps in the procedure, “ER Create a configuration provider and mark it as active.”</span></span> 

<span data-ttu-id="fc102-106">Este procedimento é criado para usuários com a função atribuída de Administrador do sistema ou Desenvolvedor de relatório eletrônico.</span><span class="sxs-lookup"><span data-stu-id="fc102-106">This procedure is created for users with the assigned role of System administrator or Electronic reporting developer.</span></span> <span data-ttu-id="fc102-107">Estas etapas podem ser concluídas usando o conjunto de dados de USMF.</span><span class="sxs-lookup"><span data-stu-id="fc102-107">These steps can be completed using the USMF data set.</span></span> 

<span data-ttu-id="fc102-108">Você também deve baixar e salvar localmente os seguintes arquivos: (https://go.microsoft.com/fwlink/?linkid=862266): 1099model.xml, 1099formatcsv.xml, 1099entriescsv.csv.</span><span class="sxs-lookup"><span data-stu-id="fc102-108">You must also download and save the following files locally: (https://go.microsoft.com/fwlink/?linkid=862266): 1099model.xml, 1099formatcsv.xml, 1099entriescsv.csv.</span></span>

1. <span data-ttu-id="fc102-109">Ir para Administração da organização > Espaços de trabalho > Relatório eletrônico.</span><span class="sxs-lookup"><span data-stu-id="fc102-109">Go to Organization administration > Workspaces > Electronic reporting.</span></span>
    * <span data-ttu-id="fc102-110">Você pode configurar um processo para importar arquivos externos em formato XML, TXT ou CSV para as tabelas no aplicativo.</span><span class="sxs-lookup"><span data-stu-id="fc102-110">You can configure a process to import external files in XML, TXT, or CSV format to tables in the application.</span></span> <span data-ttu-id="fc102-111">Primeiro, você deve criar um modelo de dados abstrato para representar os dados importados, de um ponto de vista comercial, uma configuração do modelo de dados de ER é criada para isso.</span><span class="sxs-lookup"><span data-stu-id="fc102-111">First, you must create an abstract data model to represent the imported data, from a business standpoint – an ER data model configuration is created for that.</span></span> <span data-ttu-id="fc102-112">Em seguida, defina uma estrutura do arquivo importado que mapeie ao modelo de dados criado como forma de portar dados do arquivo ao modelo de dados abstrato, uma configuração de formato de ER é criada para isso.</span><span class="sxs-lookup"><span data-stu-id="fc102-112">Next, define a structure of the imported file that maps to the designed data model as the way to port data from the file to the abstract data model – an ER format configuration is created for that.</span></span> <span data-ttu-id="fc102-113">Depois, a configuração de modelo de dados de ER deve ser estendida com um novo mapeamento de modelo que descreva como os dados do arquivo importado e os dados persistentes do modelo de dados abstrato são usados para atualizar as tabelas do aplicativo ou entidades de dados.</span><span class="sxs-lookup"><span data-stu-id="fc102-113">Then, the ER data model configuration must be extended with a new model mapping that describes how the data from the imported file and the persisted data from the abstract data model is used to update the application tables or data entities.</span></span>  
    * <span data-ttu-id="fc102-114">As etapas a seguir mostram como as transações de fornecedores externamente acompanhadas são importadas do arquivo CSV externo para uso posterior na liquidação de fornecedores para os formulários de 1099.</span><span class="sxs-lookup"><span data-stu-id="fc102-114">The following steps show how externally tracked vendors’ transactions are imported from the external CSV file for later use in the vendor’s settlement for 1099’s forms.</span></span>   
    * <span data-ttu-id="fc102-115">Verifique se o provedor de configuração da empresa exemplo, Litware, Inc., está disponível e marcado como ativo.</span><span class="sxs-lookup"><span data-stu-id="fc102-115">Verify that the configuration provider for sample company, Litware, Inc. is available and marked as active.</span></span> <span data-ttu-id="fc102-116">Se não visualizar esse provedor de configuração, você deve primeiro concluir as etapas do procedimento "Criar um provedor de configuração e marcá-lo como ativo".</span><span class="sxs-lookup"><span data-stu-id="fc102-116">If you don’t see this configuration provider, you must first complete the steps in the procedure, “Create a configuration provider and mark it as active”.</span></span>  
2. <span data-ttu-id="fc102-117">Clique em Configurações de relatórios.</span><span class="sxs-lookup"><span data-stu-id="fc102-117">Click Reporting configurations.</span></span>
3. <span data-ttu-id="fc102-118">Aplicar o filtro 'Modelo de pagamentos 1099'.</span><span class="sxs-lookup"><span data-stu-id="fc102-118">Apply the '1099 Payments model' filter.</span></span> <span data-ttu-id="fc102-119">Se já tiver concluído o procedimento “ER Criar as configurações necessárias para importar dados de um arquivo externo para relatório eletrônico” e a configuração 'Modelo de pagamentos 1099' estiver disponível na árvore de configuração, ignore todas as etapas da subtarefa a seguir.</span><span class="sxs-lookup"><span data-stu-id="fc102-119">If you already completed the procedure,” ER Create required configurations to import data from an external file for electronic reporting”, and the ‘1099 Payments model’ configuration is available in the configuration tree, skip all of the steps in the next sub-task.</span></span>   

## <a name="add-a-new-er-model-configuration"></a><span data-ttu-id="fc102-120">Adicionar uma nova configuração de modelo de ER</span><span class="sxs-lookup"><span data-stu-id="fc102-120">Add a new ER model configuration</span></span>
1. <span data-ttu-id="fc102-121">Em vez de criar um novo modelo para oferecer suporte à importação de dados, carregue o arquivo 1099model.xml, que foi baixado anteriormente.</span><span class="sxs-lookup"><span data-stu-id="fc102-121">Instead of creating a new model to support data import, load the 1099model.xml file that you previously downloaded.</span></span> <span data-ttu-id="fc102-122">Este arquivo contém o modelo de dados personalizado das transações de fornecedores.</span><span class="sxs-lookup"><span data-stu-id="fc102-122">This file contains the custom data model of vendors’ transactions.</span></span> <span data-ttu-id="fc102-123">Esse modelo de dados já está mapeado para os componentes de dados necessários.</span><span class="sxs-lookup"><span data-stu-id="fc102-123">This data model is already mapped to the necessary data components.</span></span>  
2. <span data-ttu-id="fc102-124">Clique em Trocar.</span><span class="sxs-lookup"><span data-stu-id="fc102-124">Click Exchange.</span></span>
3. <span data-ttu-id="fc102-125">Clique em Carregar de um arquivo XML.</span><span class="sxs-lookup"><span data-stu-id="fc102-125">Click Load from XML file.</span></span>
4. <span data-ttu-id="fc102-126">Clique em Procurar e navegue até o arquivo 1099model.xml que foi baixado anteriormente.</span><span class="sxs-lookup"><span data-stu-id="fc102-126">Click Browse and navigate to the 1099model.xml file that you previously downloaded.</span></span>  
5. <span data-ttu-id="fc102-127">Clique em OK.</span><span class="sxs-lookup"><span data-stu-id="fc102-127">Click OK.</span></span>

## <a name="add-a-new-er-format-configuration-that-supports-data-import"></a><span data-ttu-id="fc102-128">Adicione uma nova configuração de formato de ER que suporte importação de dados</span><span class="sxs-lookup"><span data-stu-id="fc102-128">Add a new ER format configuration that supports data import</span></span>
1. <span data-ttu-id="fc102-129">Na árvore, selecione "Modelo de pagamento 1099".</span><span class="sxs-lookup"><span data-stu-id="fc102-129">In the tree, select '1099 Payments model'.</span></span>
2. <span data-ttu-id="fc102-130">Clique em Criar configuração para abrir a caixa de diálogo suspensa.</span><span class="sxs-lookup"><span data-stu-id="fc102-130">Click Create configuration to open the drop dialog.</span></span>
3. <span data-ttu-id="fc102-131">No campo Novo, insira "Formato baseado no modelo de dados do modelo de Pagamentos 1099".</span><span class="sxs-lookup"><span data-stu-id="fc102-131">In the New field, enter 'Format based on data model 1099 Payments model'.</span></span>
4. <span data-ttu-id="fc102-132">Selecione Sim no campo Dá suporte à importação de dados.</span><span class="sxs-lookup"><span data-stu-id="fc102-132">Select Yes in the Supports data import field.</span></span>
5. <span data-ttu-id="fc102-133">Pressione a tecla ESC para fechar esta página.</span><span class="sxs-lookup"><span data-stu-id="fc102-133">Press ESC key to close this page.</span></span>
    * <span data-ttu-id="fc102-134">Em vez de criar um novo formato de ER para oferecer suporte à importação de dados, carregue o arquivo 1099formatcsv.xml, que foi baixado anteriormente.</span><span class="sxs-lookup"><span data-stu-id="fc102-134">Instead of creating a new ER format to support data import, load the 1099formatcsv.xml file that you previously downloaded.</span></span> <span data-ttu-id="fc102-135">Esse arquivo contém o formato de ER necessário que define a estrutura do arquivo CSV de entrada e o mapeamento dessa estrutura ao modelo de dados das transações de fornecedores.</span><span class="sxs-lookup"><span data-stu-id="fc102-135">This file contains the required ER format that defines the structure of the incoming CSV file and the mapping of this structure to the data model of the vendors’ transactions.</span></span>   
6. <span data-ttu-id="fc102-136">Clique em Trocar.</span><span class="sxs-lookup"><span data-stu-id="fc102-136">Click Exchange.</span></span>
7. <span data-ttu-id="fc102-137">Clique em Carregar de um arquivo XML.</span><span class="sxs-lookup"><span data-stu-id="fc102-137">Click Load from XML file.</span></span>
    * <span data-ttu-id="fc102-138">Clique em Procurar e navegue até o arquivo 1099formatcsv.xml, que foi baixado anteriormente.</span><span class="sxs-lookup"><span data-stu-id="fc102-138">Click Browse and navigate to the 1099formatcsv.xml file that you previously downloaded.</span></span>  
8. <span data-ttu-id="fc102-139">Clique em OK.</span><span class="sxs-lookup"><span data-stu-id="fc102-139">Click OK.</span></span>
9. <span data-ttu-id="fc102-140">Na árvore, expanda "Modelo de pagamentos 1099".</span><span class="sxs-lookup"><span data-stu-id="fc102-140">In the tree, expand '1099 Payments model'.</span></span>
10. <span data-ttu-id="fc102-141">Na árvore, selecione 'Modelo de pagamentos 1099\Para importar as transações de fornecedores (CSV)'.</span><span class="sxs-lookup"><span data-stu-id="fc102-141">In the tree, select '1099 Payments model\For importing vendors' transactions (CSV)'.</span></span>

## <a name="review-format-settings"></a><span data-ttu-id="fc102-142">Examine as configurações de formato</span><span class="sxs-lookup"><span data-stu-id="fc102-142">Review format settings</span></span>
1. <span data-ttu-id="fc102-143">Clique em Designer.</span><span class="sxs-lookup"><span data-stu-id="fc102-143">Click Designer.</span></span>
2. <span data-ttu-id="fc102-144">Clique em Expandir/recolher.</span><span class="sxs-lookup"><span data-stu-id="fc102-144">Click Expand/collapse.</span></span>
3. <span data-ttu-id="fc102-145">Ative 'Mostrar detalhes'.</span><span class="sxs-lookup"><span data-stu-id="fc102-145">Toggle ‘Show details’ on.</span></span>
    * <span data-ttu-id="fc102-146">O formato criado representa a estrutura prevista do arquivo externo no formato CSV.</span><span class="sxs-lookup"><span data-stu-id="fc102-146">The designed format represents the expected structure of the external file in CSV format.</span></span>  
4. <span data-ttu-id="fc102-147">Na árvore, selecione 'Entrada: Arquivo\Raiz: Sequência'.</span><span class="sxs-lookup"><span data-stu-id="fc102-147">In the tree, select 'Incoming: File\Root: Sequence'.</span></span>
    * <span data-ttu-id="fc102-148">Para o elemento Raiz do tipo SEQUENCE, a opção 'Nova linha - Windows (CR LF)' foi selecionada no campo 'Caracteres especiais'.</span><span class="sxs-lookup"><span data-stu-id="fc102-148">For the Root element of the type SEQUENCE, the option ‘New line - Windows (CR LF)’ has been selected in the ‘Special characters’ field.</span></span> <span data-ttu-id="fc102-149">Com base nessa configuração, cada linha no arquivo de análise deve ser considerada como um registro separado.</span><span class="sxs-lookup"><span data-stu-id="fc102-149">Based on this setting, each line in the parsing file must be considered as a separate record.</span></span>   
5. <span data-ttu-id="fc102-150">Na árvore, selecione 'Entrada: Arquivo\Raiz: Sequência\Linha: Sequência 1..\* '.</span><span class="sxs-lookup"><span data-stu-id="fc102-150">In the tree, select 'Incoming: File\Root: Sequence\Line: Sequence 1..\* '.</span></span>
    * <span data-ttu-id="fc102-151">Para o elemento Raiz\Linha do tipo SEQUENCE, a opção 'Um muitos' foi selecionada no campo 'Multiplicidade'.</span><span class="sxs-lookup"><span data-stu-id="fc102-151">For the Root\Line element of the type SEQUENCE, the option ‘One many’ has been selected in the ‘Multiplicity’ field.</span></span> <span data-ttu-id="fc102-152">Com base nessa configuração, pelo menos uma linha será apresentada no arquivo de análise.</span><span class="sxs-lookup"><span data-stu-id="fc102-152">Based on this setting, at least one line will be presented in the parsing file.</span></span>   
6. <span data-ttu-id="fc102-153">Na árvore, selecione 'Entrada: Arquivo\Raiz: Sequência\Linha: Sequência 1..\* Tipos: Caso'.</span><span class="sxs-lookup"><span data-stu-id="fc102-153">In the tree, select 'Incoming: File\Root: Sequence\Line: Sequence 1..\* \Types: Case'.</span></span>
    * <span data-ttu-id="fc102-154">Observe que o elemento Raiz\Linha\Tipos do tipo CASE foi adicionado como o elemento aninhado da sequência Raiz\Linha.</span><span class="sxs-lookup"><span data-stu-id="fc102-154">Note that the Root\Line\Types element of the type CASE has been added as the nested element of the Root\Line sequence.</span></span> <span data-ttu-id="fc102-155">Como esse elemento CASE contém 3 elementos de sequência aninhados, essa configuração presume que esperamos atender a 3 tipos de linha diferentes no arquivo de análise.</span><span class="sxs-lookup"><span data-stu-id="fc102-155">Because this CASE element contains 3 nested sequence elements, this setting assumes that we expect to meet 3 different types of line in the parsing file.</span></span>   
7. <span data-ttu-id="fc102-156">Na árvore, selecione 'Entrada: Arquivo\Raiz: Sequência\Linha: Sequência 1..\* \Tipos: Caso\Cabeçalho: Sequência 1..1 '.</span><span class="sxs-lookup"><span data-stu-id="fc102-156">In the tree, select 'Incoming: File\Root: Sequence\Line: Sequence 1..\* \Types: Case\Header: Sequence 1..1 '.</span></span>
    * <span data-ttu-id="fc102-157">O elemento Raiz\Linha\Tipos\Cabeçalho do tipo SEQUENCE contém o elemento STRING aninhado cujo valor foi definido como o valor da cadeia de caracteres fixo.</span><span class="sxs-lookup"><span data-stu-id="fc102-157">The Root\Line\Types\Header element of the type SEQUENCE contains the nested STRING element the value of which has been defined as the fixed string value.</span></span> <span data-ttu-id="fc102-158">Esta sequência analisará a linha de cabeçalho do arquivo de análise.</span><span class="sxs-lookup"><span data-stu-id="fc102-158">This sequence will parse the header line of the parsing file.</span></span>   
8. <span data-ttu-id="fc102-159">Na árvore, selecione 'Entrada: Arquivo\Raiz: Sequência\Linha: Sequência 1..\* \Tipos: Caso\Registro: Sequência 1..1 (,)'.</span><span class="sxs-lookup"><span data-stu-id="fc102-159">In the tree, select 'Incoming: File\Root: Sequence\Line: Sequence 1..\* \Types: Case\Record: Sequence 1..1 (,)'.</span></span>
    * <span data-ttu-id="fc102-160">O elemento Raiz\Linha\Tipos\Registro do tipo SEQUENCE foi configurado para analisar as linhas de transação.</span><span class="sxs-lookup"><span data-stu-id="fc102-160">The Root\Line\Types\Record element of the type SEQUENCE, has been configured to parse the transaction lines.</span></span> <span data-ttu-id="fc102-161">Observe que a opção de caracteres 'Delimitador personalizado' foi configurada como uma vírgula.</span><span class="sxs-lookup"><span data-stu-id="fc102-161">Note that the ‘Custom delimiter’ character option has been configured as a comma.</span></span> <span data-ttu-id="fc102-162">Isso significa que a vírgula será usada como separador de campos para esse tipo de linha no arquivo de análise.</span><span class="sxs-lookup"><span data-stu-id="fc102-162">This means that the comma will be used as a fields’ separator for this type of line in the parsing file.</span></span>   
    * <span data-ttu-id="fc102-163">Observe que vários elementos aninhados de diferentes tipos de dados foram adicionados ao elemento Raiz\Linha\Tipos\Registro para analisar as linhas de transação como campos separados.</span><span class="sxs-lookup"><span data-stu-id="fc102-163">Note that several nested elements of different data types have been added for the Root\Line\Types\Record element for parsing the transaction’s lines as separated fields.</span></span> <span data-ttu-id="fc102-164">Observe que a opção 'Aplicativo de cotação' foi configurada como 'Nenhum'.</span><span class="sxs-lookup"><span data-stu-id="fc102-164">Note that the ‘Quotation application’ option has been configured as ‘None’.</span></span> <span data-ttu-id="fc102-165">Isso significa que no arquivo de análise, todos os campos desse tipo serão considerados como desprovidos de caracteres inseridos.</span><span class="sxs-lookup"><span data-stu-id="fc102-165">This means that in the parsing file, all fields of this type will be considered as having no enclosed characters.</span></span>   
9. <span data-ttu-id="fc102-166">Na árvore, selecione 'Entrada: Arquivo\Raiz: Sequência\Linha: Sequência 1..\* \Tipos: Caso\Registro: Sequência 1..1 (,)\TransactionDate: DateTime'.</span><span class="sxs-lookup"><span data-stu-id="fc102-166">In the tree, select 'Incoming: File\Root: Sequence\Line: Sequence 1..\* \Types: Case\Record: Sequence 1..1 (,)\TransactionDate: DateTime'.</span></span>
    * <span data-ttu-id="fc102-167">Por exemplo, o elemento Raiz\Linha\Tipos\Registro\TransactionDate do tipo DATETIME foi configurado para obter o valor de data e hora da transação a partir do arquivo de análise no formato 'M/d/aaaa'.</span><span class="sxs-lookup"><span data-stu-id="fc102-167">For example, the Root\Line\Types\Record\TransactionDate element of the type DATETIME has been configured to get the transaction’s date and time value from the parsing file in the ‘M/d/yyyy’ format.</span></span>   
10. <span data-ttu-id="fc102-168">Na árvore, selecione 'Entrada: Arquivo\Raiz: Sequência\Linha: Sequência 1..\* \Tipos: Caso\Registro: Sequência 1..1 (,)\CountryCode: String 0..1 '.</span><span class="sxs-lookup"><span data-stu-id="fc102-168">In the tree, select 'Incoming: File\Root: Sequence\Line: Sequence 1..\* \Types: Case\Record: Sequence 1..1 (,)\CountryCode: String 0..1 '.</span></span>
    * <span data-ttu-id="fc102-169">Observe que o elemento Raiz\Linha\Tipos\Registro\CountryCode do tipo STRING foi configurado com a opção 'Zero um' no campo 'Multiplicidade'.</span><span class="sxs-lookup"><span data-stu-id="fc102-169">Note that Root\Line\Types\Record\CountryCode element of the type STRING has been configured as having the option ‘Zero one’ in the ‘Multiplicity’ field.</span></span> <span data-ttu-id="fc102-170">Essa configuração considera o valor do campo CountryCode na linha de análise como opcional.</span><span class="sxs-lookup"><span data-stu-id="fc102-170">This setting considers the value of the CountryCode field in the parsing line as optional.</span></span>   
11. <span data-ttu-id="fc102-171">Na árvore, selecione 'Entrada: Arquivo\Raiz: Sequência\Linha: Sequência 1..\* \Tipos: Caso\Registro: Sequência 1..1 (,)\Comentário: Sequência 1..1 (,)'.</span><span class="sxs-lookup"><span data-stu-id="fc102-171">In the tree, select 'Incoming: File\Root: Sequence\Line: Sequence 1..\* \Types: Case\Record: Sequence 1..1 (,)\Remark: Sequence 1..1 (,)'.</span></span>
    * <span data-ttu-id="fc102-172">Observe que o elemento Raiz\Linha\Tipos\Registro\Comentário do tipo SEQUENCE foi configurado com a opção 'Tudo' no campo 'Aplicativo de cotação' e aspas duplas no campo 'Aspas'.</span><span class="sxs-lookup"><span data-stu-id="fc102-172">Note that Root\Line\Types\Record\Remark element of the type SEQUENCE has been configured as having the option ‘All’ in the ‘Quotation application’ field and double quotes character in the ‘Quotation mark’ field.</span></span> <span data-ttu-id="fc102-173">Isso significa que todos os campos desse tipo de linhas no arquivo de análise (descrito pelos elementos aninhados: texto do tipo STRING) serão considerados como inseridos entre aspas duplas.</span><span class="sxs-lookup"><span data-stu-id="fc102-173">It means that all fields of this type of lines in the parsing file (described by the nested elements: Text of the STRING type) will be considered as enclosed in double quotes characters.</span></span>  
12. <span data-ttu-id="fc102-174">Na árvore, selecione 'Entrada: Arquivo\Raiz: Sequência\Linha: Sequência 1..\* \Tipos: Caso\Não analisado: Sequência 1..1 '.</span><span class="sxs-lookup"><span data-stu-id="fc102-174">In the tree, select 'Incoming: File\Root: Sequence\Line: Sequence 1..\* \Types: Case\Unparsed: Sequence 1..1 '.</span></span>
    * <span data-ttu-id="fc102-175">O elemento Raiz\Linha\Tipos\Não analisado do tipo SEQUENCE foi configurado para analisar as linhas de transação da estrutura que não corresponde à estrutura descrita acima no elemento CASE pai.</span><span class="sxs-lookup"><span data-stu-id="fc102-175">The Root\Line\Types\Unparsed element of the type SEQUENCE has been configured to parse the transaction lines for the structure which does not match the structure described above in the parent CASE element.</span></span>   

## <a name="review-the-setting-of-the-format-mapping-to-the-data-model"></a><span data-ttu-id="fc102-176">Examine a configuração do mapeamento de formato para o modelo de dados</span><span class="sxs-lookup"><span data-stu-id="fc102-176">Review the setting of the format mapping to the data model</span></span>
1. <span data-ttu-id="fc102-177">Clique em Mapear formato para modelo.</span><span class="sxs-lookup"><span data-stu-id="fc102-177">Click Map format to model.</span></span>
    * <span data-ttu-id="fc102-178">O mapeamento de modelo 'Mapeamento para modelo de formato CSV' descreve o fluxo de dados da transferência de dados do arquivo CSV de entrada ao modelo de dados.</span><span class="sxs-lookup"><span data-stu-id="fc102-178">The model mapping ‘Mapping to model from CSV format’ describes the data flow of the data transfer from the incoming CSV file to the data model.</span></span>   
2. <span data-ttu-id="fc102-179">Clique em Designer.</span><span class="sxs-lookup"><span data-stu-id="fc102-179">Click Designer.</span></span>
3. <span data-ttu-id="fc102-180">Na árvore, expanda 'format'.</span><span class="sxs-lookup"><span data-stu-id="fc102-180">In the tree, expand 'format'.</span></span>
    * <span data-ttu-id="fc102-181">Observe que o formato criado será apresentado aqui como um componente de fonte de dados.</span><span class="sxs-lookup"><span data-stu-id="fc102-181">Note that the designed format is presented here as a data source component.</span></span>  
4. <span data-ttu-id="fc102-182">Na árvore, expanda 'formato\Entrada: Arquivo(Incoming)'.</span><span class="sxs-lookup"><span data-stu-id="fc102-182">In the tree, expand 'format\Incoming: File(Incoming)'.</span></span>
5. <span data-ttu-id="fc102-183">Na árvore, expanda 'formato\Entrada: Arquivo(Incoming)\Raiz: Sequência(Root)'.</span><span class="sxs-lookup"><span data-stu-id="fc102-183">In the tree, expand 'format\Incoming: File(Incoming)\Root: Sequence(Root)'.</span></span>
6. <span data-ttu-id="fc102-184">Na árvore, expanda 'formato\Entrada: Arquivo(Incoming)\Raiz: Sequência(Root)\Linha: Sequência 1..\* (Line)'.</span><span class="sxs-lookup"><span data-stu-id="fc102-184">In the tree, expand 'format\Incoming: File(Incoming)\Root: Sequence(Root)\Line: Sequence 1..\* (Line)'.</span></span>
7. <span data-ttu-id="fc102-185">Na árvore, expanda 'formato\Entrada: Arquivo(Incoming)\Raiz: Sequência(Root)\Linha: Sequência 1..\* (Line)\Tipos: Caso(Types)'.</span><span class="sxs-lookup"><span data-stu-id="fc102-185">In the tree, expand 'format\Incoming: File(Incoming)\Root: Sequence(Root)\Line: Sequence 1..\* (Line)\Types: Case(Types)'.</span></span>
8. <span data-ttu-id="fc102-186">Na árvore, expanda 'formato\Entrada: Arquivo(Incoming)\Raiz: Sequência(Root)\Linha: Sequência 1..\* (Line)\Tipos: Caso(Types)\Registro: Sequência 1..1 (,)(Record)'.</span><span class="sxs-lookup"><span data-stu-id="fc102-186">In the tree, expand 'format\Incoming: File(Incoming)\Root: Sequence(Root)\Line: Sequence 1..\* (Line)\Types: Case(Types)\Record: Sequence 1..1 (,)(Record)'.</span></span>
9. <span data-ttu-id="fc102-187">Na árvore, expanda 'formato\Entrada: Arquivo(Incoming)\Raiz: Sequência(Root)\Linha: Sequência 1..\* (Line)\Tipos: Caso(Types)\Registro: Sequência 1..1 (,)(Record)\Dados'.</span><span class="sxs-lookup"><span data-stu-id="fc102-187">In the tree, expand 'format\Incoming: File(Incoming)\Root: Sequence(Root)\Line: Sequence 1..\* (Line)\Types: Case(Types)\Record: Sequence 1..1 (,)(Record)\Data'.</span></span>
10. <span data-ttu-id="fc102-188">Na árvore, expanda 'formato\Entrada: Arquivo(Incoming)\Raiz: Sequência(Root)\Linha: Sequência 1..\* (Line)\Tipos: Caso(Types)\Registro: Sequência 1..1 (,)(Record)\Dados\CountryCode: String 0..1 (CountryCode)'.</span><span class="sxs-lookup"><span data-stu-id="fc102-188">In the tree, expand 'format\Incoming: File(Incoming)\Root: Sequence(Root)\Line: Sequence 1..\* (Line)\Types: Case(Types)\Record: Sequence 1..1 (,)(Record)\Data\CountryCode: String 0..1 (CountryCode)'.</span></span>
11. <span data-ttu-id="fc102-189">Na árvore, selecione 'formato\Entrada: Arquivo(Incoming)\Raiz: Sequência(Root)\Linha: Sequência 1..\* (Line)\Tipos: Caso(Types)\Registro: Sequência 1..1 (,)(Record)\Dados\TransactionDate: DateTime(TransactionDate)'.</span><span class="sxs-lookup"><span data-stu-id="fc102-189">In the tree, select 'format\Incoming: File(Incoming)\Root: Sequence(Root)\Line: Sequence 1..\* (Line)\Types: Case(Types)\Record: Sequence 1..1 (,)(Record)\Data\TransactionDate: DateTime(TransactionDate)'.</span></span>
    * <span data-ttu-id="fc102-190">Observe que os elementos de formato obrigatórios e opcionais, como TransactionDate e CountryCode, têm um aspecto diferente no componente de fonte de dados de 'formato' predefinido.</span><span class="sxs-lookup"><span data-stu-id="fc102-190">Note that the required and optional format elements, such as TransactionDate and CountryCode, look different in the predefined ‘format’ data source component.</span></span>   
12. <span data-ttu-id="fc102-191">Na árvore, expanda 'Transações = '$both''.</span><span class="sxs-lookup"><span data-stu-id="fc102-191">In the tree, expand 'Transactions = '$both''.</span></span>
    * <span data-ttu-id="fc102-192">Observe que os elementos do formato que define a estrutura do arquivo importado estão associados aos elementos do modelo de dados.</span><span class="sxs-lookup"><span data-stu-id="fc102-192">Note that the elements of the format that defines the structure of the imported file are bound to the elements of the data model.</span></span> <span data-ttu-id="fc102-193">Com base nessas associações, o conteúdo do arquivo CSV importado será armazenado no tempo de execução no modelo de dados existente.</span><span class="sxs-lookup"><span data-stu-id="fc102-193">Based on these bindings, the content of the imported CSV file will be stored at run-time in the existing data model.</span></span> <span data-ttu-id="fc102-194">Preste atenção na associação do elemento CountryRegion.</span><span class="sxs-lookup"><span data-stu-id="fc102-194">Pay attention to the binding of the CountryRegion element.</span></span> <span data-ttu-id="fc102-195">Para qualquer elemento de transação no arquivo de entrada que não tiver um valor de código de país especificado, o código de país padrão 'EUA' será preenchido no modelo de dados.</span><span class="sxs-lookup"><span data-stu-id="fc102-195">For any transaction element in the incoming file that does not have a country code value specified, the default country code ‘USA’ will be populated in the data model.</span></span>   
13. <span data-ttu-id="fc102-196">Ative 'Mostrar detalhes'.</span><span class="sxs-lookup"><span data-stu-id="fc102-196">Toggle on ‘Show details’.</span></span>
14. <span data-ttu-id="fc102-197">Clique na guia Validações.</span><span class="sxs-lookup"><span data-stu-id="fc102-197">Click the Validations tab.</span></span>
15. <span data-ttu-id="fc102-198">Clique em Pesquisar.</span><span class="sxs-lookup"><span data-stu-id="fc102-198">Click Search.</span></span>
16. <span data-ttu-id="fc102-199">No campo Encontrar, digite "forn.".</span><span class="sxs-lookup"><span data-stu-id="fc102-199">In the Find field, type 'vend'.</span></span>
17. <span data-ttu-id="fc102-200">Clique em Localizar próximo.</span><span class="sxs-lookup"><span data-stu-id="fc102-200">Click Find next.</span></span>
    * <span data-ttu-id="fc102-201">Este mapeamento de formato pode conter a lógica definida pelo usuário para validar a precisão dos dados importados de um ponto de vista comercial.</span><span class="sxs-lookup"><span data-stu-id="fc102-201">This format mapping may contain user-defined logic to validate the accuracy of the imported data from a business standpoint.</span></span> <span data-ttu-id="fc102-202">Por exemplo, com base na configuração, para qualquer linha no arquivo de importação cuja estrutura não corresponda nem à estrutura da linha de cabeçalho nem a da linha de transação, uma mensagem de aviso será gerada no Log de Informações comunicando o usuário sobre esse caso, indicando o número de sequência da transação no arquivo.</span><span class="sxs-lookup"><span data-stu-id="fc102-202">For example, based on the setting, for any line in the importing file the structure of which does not match neither the structure of the header line nor transaction line, a warning message will be generated in the Infolog informing the user about this case, indicating the transaction’s sequence number in the file.</span></span>   
18. <span data-ttu-id="fc102-203">Feche a página.</span><span class="sxs-lookup"><span data-stu-id="fc102-203">Close the page.</span></span>

## <a name="run-the-format-mapping"></a><span data-ttu-id="fc102-204">Executar o mapeamento de formato</span><span class="sxs-lookup"><span data-stu-id="fc102-204">Run the format mapping</span></span>
<span data-ttu-id="fc102-205">Para fins de teste, execute o mapeamento de formato usando o arquivo 1099entriescsv.csv, que foi baixado anteriormente.</span><span class="sxs-lookup"><span data-stu-id="fc102-205">For testing purposes, execute the format mapping using the 1099entriescsv.csv file that you previously downloaded.</span></span> <span data-ttu-id="fc102-206">A saída gerada apresentará os dados que serão importados do arquivo CSV selecionado e preenchidos no modelo de dados personalizado na importação real.</span><span class="sxs-lookup"><span data-stu-id="fc102-206">The generated output will present data that will be imported from the selected CSV file and populated to the custom data model at real import.</span></span>   
1. <span data-ttu-id="fc102-207">Clique em Executar.</span><span class="sxs-lookup"><span data-stu-id="fc102-207">Click Run.</span></span>
    * <span data-ttu-id="fc102-208">Clique em Procurar e navegue até o arquivo 1099entriescsv.csv, que foi baixado anteriormente.</span><span class="sxs-lookup"><span data-stu-id="fc102-208">Click Browse and navigate to the 1099entriescsv.csv file that you previously downloaded.</span></span>  
2. <span data-ttu-id="fc102-209">Clique em OK.</span><span class="sxs-lookup"><span data-stu-id="fc102-209">Click OK.</span></span>
    * <span data-ttu-id="fc102-210">Observe as mensagens de aviso sobre as linhas que não são aceitas.</span><span class="sxs-lookup"><span data-stu-id="fc102-210">Note the warning messages about lines that are not accepted.</span></span> <span data-ttu-id="fc102-211">A linha 4 contém o valor da renda que é apresentado no formato não aceitável enquanto a linha 7 não contém o texto do comentário de transação em aspas duplas.</span><span class="sxs-lookup"><span data-stu-id="fc102-211">Line 4 contains the income value that is presented in the non-acceptable format while line 7 does not contain the transaction remark text in double quotes.</span></span>   
    * <span data-ttu-id="fc102-212">Examine a saída no formato XML, que representa os dados que foram importados do arquivo selecionado e transferidos para o modelo de dados.</span><span class="sxs-lookup"><span data-stu-id="fc102-212">Review the output in XML format that represents the data that has been imported from the selected file and ported to the data model.</span></span> <span data-ttu-id="fc102-213">Observe que todas as 7 linhas do arquivo CSV importado foram processadas.</span><span class="sxs-lookup"><span data-stu-id="fc102-213">Note that all 7 lines of the imported CSV file were processed.</span></span> <span data-ttu-id="fc102-214">A linha 1 dos títulos de campos foi ignorada, 4 transações foram devidamente analisadas e 2 transações foram reconhecidas como inválidas.</span><span class="sxs-lookup"><span data-stu-id="fc102-214">The containing fields’ titles line 1 were skipped, 4 transactions were properly parsed, and 2 transactions were recognized as not valid.</span></span>   
3. <span data-ttu-id="fc102-215">Feche a página.</span><span class="sxs-lookup"><span data-stu-id="fc102-215">Close the page.</span></span>
4. <span data-ttu-id="fc102-216">Feche a página.</span><span class="sxs-lookup"><span data-stu-id="fc102-216">Close the page.</span></span>
