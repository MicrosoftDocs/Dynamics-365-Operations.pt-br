---
title: "Redefinir data mart de relatório financeiro após restaurar um banco de dados"
description: "Este tópico descreve como redefinir o data mart de relatório financeiro após restaurar um banco de dados do Microsoft Dynamics 365 for Finance and Operations."
author: ShylaThompson
manager: AnnBe
ms.date: 08/15/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-platform
ms.technology: 
audience: Application User, IT Pro
ms.reviewer: shylaw
ms.search.scope: Core, Operations, UnifiedOperations
ms.custom: 261824
ms.search.region: Global
ms.author: kweekley
ms.search.validFrom: 2016-11-30
ms.dyn365.ops.version: Version 1611
ms.translationtype: HT
ms.sourcegitcommit: 47e70cb1291e390b42b7feff844b2aca141f09b7
ms.openlocfilehash: 200b1a03a0ea95ec2d75850f9a8aebda966e38d6
ms.contentlocale: pt-br
ms.lasthandoff: 09/29/2017

---

# <a name="reset-the-financial-reporting-data-mart-after-restoring-a-database"></a><span data-ttu-id="9b492-103">Redefinir data mart de relatório financeiro após restaurar um banco de dados</span><span class="sxs-lookup"><span data-stu-id="9b492-103">Reset the financial reporting data mart after restoring a database</span></span>

[!include[banner](../includes/banner.md)]


<span data-ttu-id="9b492-104">Este tópico descreve como redefinir o data mart de relatório financeiro após restaurar um banco de dados do Microsoft Dynamics 365 for Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="9b492-104">This topic describes how to reset the financial reporting data mart after restoring a Microsoft Dynamics 365 for Finance and Operations database.</span></span>

<span data-ttu-id="9b492-105">Se restaurar a banco de dados do Finance and Operations a partir de um backup ou copiar o banco de dados de outro ambiente, você deve seguir as etapas deste tópico para garantir que o data mart de relatório financeiro está usando corretamente o banco de dados restaurado do Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="9b492-105">If you ever restore your Finance and Operations database from a backup or copy the database from another environment, you must follow the steps in this topic to ensure that the financial reporting data mart is correctly using the restored Finance and Operations database.</span></span> 
> [!Note] 
> <span data-ttu-id="9b492-106">As etapas deste processo têm suporte na versão de maio de 2016 do Dynamics 365 for Operations (compilação de aplicativo 7.0.1265.23014 e compilação de geração de relatórios financeiros 7.0.10000.4) e versões mais recentes.</span><span class="sxs-lookup"><span data-stu-id="9b492-106">The steps in this process are supported for Dynamics 365 for Operation May 2016 release (App build 7.0.1265.23014 and financial reporting build 7.0.10000.4) and newer releases.</span></span> <span data-ttu-id="9b492-107">Se você tiver uma versão anterior do Finance and Operations, contate nossa Equipe de suporte para obter assistência.</span><span class="sxs-lookup"><span data-stu-id="9b492-107">If you have an earlier release of Finance and Operations, contact our Support team for assistance.</span></span>

## <a name="export-report-definitions"></a><span data-ttu-id="9b492-108">Exportar definições de relatório</span><span class="sxs-lookup"><span data-stu-id="9b492-108">Export report definitions</span></span>
<span data-ttu-id="9b492-109">Primeiro, exporte os projetos de relatório localizados no Report Designer, usando as seguintes etapas:</span><span class="sxs-lookup"><span data-stu-id="9b492-109">First, export the report designs located in the Report Designer, using the following steps:</span></span>

1.  <span data-ttu-id="9b492-110">No Report Designer, vá para **Empresa** &gt; **Grupos do bloco de construção**.</span><span class="sxs-lookup"><span data-stu-id="9b492-110">In the Report Designer, go to **Company** &gt; **Building Block Groups**.</span></span>
2.  <span data-ttu-id="9b492-111">Selecione o grupo do bloco de construção para exportar, clique em **Exportar**.</span><span class="sxs-lookup"><span data-stu-id="9b492-111">Select the building block group to export, and click **Export**.</span></span> 

    > [!Note] 
    > <span data-ttu-id="9b492-112">Para o Finanças e Operações, apenas um grupo de blocos de construção é suportado, **Padrão**.</span><span class="sxs-lookup"><span data-stu-id="9b492-112">For Finance and Operations, only one building block group is supported, **Default**.</span></span>
    
3.  <span data-ttu-id="9b492-113">Selecione as definições de relatório a serem exportadas:</span><span class="sxs-lookup"><span data-stu-id="9b492-113">Select the report definitions to export:</span></span>
    -   <span data-ttu-id="9b492-114">Para exportar todas as definições de relatório e os blocos de construção associados, clique em **Selecionar Tudo**.</span><span class="sxs-lookup"><span data-stu-id="9b492-114">To export all your report definitions and the associated building blocks, click **Select All**.</span></span>
    -   <span data-ttu-id="9b492-115">Para exportar relatórios, linhas, colunas, árvores ou conjuntos de dimensões específicos, clique na guia apropriada e selecione os itens a serem exportados.</span><span class="sxs-lookup"><span data-stu-id="9b492-115">To export specific reports, rows, columns, trees, or dimension sets, click the appropriate tab, and then select the items to export.</span></span> <span data-ttu-id="9b492-116">Pressione e mantenha pressionada a tecla Ctrl para selecionar vários itens em uma guia. Quando você seleciona relatórios para exportar, as linhas, as colunas, as hierarquias e os conjuntos de dimensões associados são selecionados.</span><span class="sxs-lookup"><span data-stu-id="9b492-116">Press and hold the Ctrl key to select multiple items in a tab. When you select reports to export, the associated rows, columns, trees, and dimension sets are selected.</span></span>

4.  <span data-ttu-id="9b492-117">Clique em **Exportar**.</span><span class="sxs-lookup"><span data-stu-id="9b492-117">Click **Export**.</span></span>
5.  <span data-ttu-id="9b492-118">Insira um nome de arquivo e selecione um local seguro onde deseja salvar as definições de relatório exportadas.</span><span class="sxs-lookup"><span data-stu-id="9b492-118">Enter a file name and select a secure location where you want to save the exported report definitions.</span></span>
6.  <span data-ttu-id="9b492-119">Clique em **Salvar**.</span><span class="sxs-lookup"><span data-stu-id="9b492-119">Click **Save**.</span></span>

<span data-ttu-id="9b492-120">O arquivo pode ser copiado ou carregado em um local seguro, permitindo que seja importado em um ambiente em outro momento.</span><span class="sxs-lookup"><span data-stu-id="9b492-120">The file can be copied or uploaded to a secure location, allowing it to be imported into a different environment at another time.</span></span> <span data-ttu-id="9b492-121">Informações sobre como usar uma conta de armazenamento do Microsoft Azure podem ser encontradas em [Transferir dados com o utilitário de linha de comando AzCopy](/azure/storage/storage-use-azcopy).</span><span class="sxs-lookup"><span data-stu-id="9b492-121">Information about using a Microsoft Azure storage account can be found in [Transfer data with the AzCopy Command-Line Utility](/azure/storage/storage-use-azcopy).</span></span> 
> [!NOTE]
> <span data-ttu-id="9b492-122">A Microsoft não fornece uma conta de armazenamento como parte do seu contrato do Finanças e Operações.</span><span class="sxs-lookup"><span data-stu-id="9b492-122">Microsoft doesn’t provide a storage account as part of your Finance and Operations agreement.</span></span> <span data-ttu-id="9b492-123">Você deve comprar uma conta de armazenamento ou usar uma conta de armazenamento de uma subscrição separada do Azure.</span><span class="sxs-lookup"><span data-stu-id="9b492-123">You must either purchase a storage account or use a storage account from a separate Azure subscription.</span></span> 
> [!WARNING]
> <span data-ttu-id="9b492-124">Esteja ciente do comportamento da unidade D no Azure Virtual Machines.</span><span class="sxs-lookup"><span data-stu-id="9b492-124">Be aware of the behavior of the D drive on Azure Virtual Machines.</span></span> <span data-ttu-id="9b492-125">Não mantenha seus grupos de blocos de construção exportados aqui permanentemente.</span><span class="sxs-lookup"><span data-stu-id="9b492-125">Do not keep your exported building block groups here permanently.</span></span> <span data-ttu-id="9b492-126">Para obter mais informações sobre unidades temporárias, consulte [Entendendo a unidade temporária nas máquinas virtuais do Windows Azure](https://blogs.msdn.microsoft.com/mast/2013/12/06/understanding-the-temporary-drive-on-windows-azure-virtual-machines/).</span><span class="sxs-lookup"><span data-stu-id="9b492-126">For more information about temporary drives, see [Understanding the temporary drive on Windows Azure Virtual Machines](https://blogs.msdn.microsoft.com/mast/2013/12/06/understanding-the-temporary-drive-on-windows-azure-virtual-machines/).</span></span>

## <a name="stop-services"></a><span data-ttu-id="9b492-127">Interromper serviços</span><span class="sxs-lookup"><span data-stu-id="9b492-127">Stop services</span></span>
<span data-ttu-id="9b492-128">Use a Área de Trabalho Remota para se conectar a todos os computadores no ambiente e parar os seguintes serviços do Windows usando services.msc:</span><span class="sxs-lookup"><span data-stu-id="9b492-128">Use Remote Desktop to connect to all the computers in the environment and stop the following Windows services by using services.msc:</span></span>

-   <span data-ttu-id="9b492-129">Serviço de publicação na Web (em todos os computadores AOS)</span><span class="sxs-lookup"><span data-stu-id="9b492-129">World wide web publishing service (on all AOS computers)</span></span>
-   <span data-ttu-id="9b492-130">Gerenciamento de Lotes do Microsoft Dynamics 365 for Finance and Operations (somente em computadores AOS não particulares)</span><span class="sxs-lookup"><span data-stu-id="9b492-130">Microsoft Dynamics 365 for Finance and Operations Batch Management Service (on non-private AOS computers only)</span></span>
-   <span data-ttu-id="9b492-131">Serviço de Processamento do Management Reporter 2012 (somente computadores BI)</span><span class="sxs-lookup"><span data-stu-id="9b492-131">Management Reporter 2012 Process Service (on BI computers only)</span></span>

<span data-ttu-id="9b492-132">Esses serviços terão conexões abertas com o banco de dados do Finanças e Operações.</span><span class="sxs-lookup"><span data-stu-id="9b492-132">These services will have open connections to the Finance and Operations database.</span></span>

## <a name="reset"></a><span data-ttu-id="9b492-133">Redefinir</span><span class="sxs-lookup"><span data-stu-id="9b492-133">Reset</span></span>
### <a name="locate-and-download-the-latest-minorversiondataupgradezip-package"></a><span data-ttu-id="9b492-134">Localizar e baixar o pacote MinorVersionDataUpgrade.zip mais recente</span><span class="sxs-lookup"><span data-stu-id="9b492-134">Locate and download the latest MinorVersionDataUpgrade.zip package</span></span>

<span data-ttu-id="9b492-135">Localize o pacote MinorVersionDataUpgrade.zip mais recente usando as instruções encontradas em [Baixar o pacote implantável de atualização de dados mais recente](..\migration-upgrade\upgrade-data-to-latest-update.md#download-the-latest-data-upgrade-deployable-packages).</span><span class="sxs-lookup"><span data-stu-id="9b492-135">Locate the latest MinorVersionDataUpgrade.zip package using the directions found in [Download the latest data upgrade deployable package](..\migration-upgrade\upgrade-data-to-latest-update.md#download-the-latest-data-upgrade-deployable-packages).</span></span> <span data-ttu-id="9b492-136">As instruções explicam como localizar e baixar a versão correta do pacote de atualização de dados.</span><span class="sxs-lookup"><span data-stu-id="9b492-136">The directions explain how to locate and download the correct version of the data upgrade package.</span></span> <span data-ttu-id="9b492-137">Não é necessária uma atualização para baixar o pacote MinorVersionDataUpgrade.zip.</span><span class="sxs-lookup"><span data-stu-id="9b492-137">An upgrade is not required to download the MinorVersionDataUpgrade.zip package.</span></span> <span data-ttu-id="9b492-138">Basta concluir as etapas na seção "Baixar o pacote implantável de atualização de dados mais recente" sem executar nenhuma das outras etapas no artigo para recuperar uma cópia do pacote MinorVersionDataUpgrade.zip.</span><span class="sxs-lookup"><span data-stu-id="9b492-138">You only need to complete the steps in the “Download the latest data upgrade deployable package” section without performing any of the other steps in the article to retrieve a copy of the MinorVersionDataUpgrade.zip package.</span></span>

### <a name="execute-scripts-against-finance-and-operations-database"></a><span data-ttu-id="9b492-139">Executar scripts no banco de dados do Finanças e Operações</span><span class="sxs-lookup"><span data-stu-id="9b492-139">Execute scripts against Finance and Operations database</span></span>

<span data-ttu-id="9b492-140">Execute os seguintes scripts no banco de dados do Finanças e Operações (não no banco de dados de relatórios financeiros).</span><span class="sxs-lookup"><span data-stu-id="9b492-140">Run the following scripts against the Finance and Operations database (not against the financial reporting database).</span></span>

-   <span data-ttu-id="9b492-141">DataUpgrade.zip\\AosService\\Scripts\\ConfigureAxReportingIntegration.sql</span><span class="sxs-lookup"><span data-stu-id="9b492-141">DataUpgrade.zip\\AosService\\Scripts\\ConfigureAxReportingIntegration.sql</span></span>
-   <span data-ttu-id="9b492-142">DataUpgrade.zip\\AosService\\Scripts\\GrantAzViewChangeTracking.sql</span><span class="sxs-lookup"><span data-stu-id="9b492-142">DataUpgrade.zip\\AosService\\Scripts\\GrantAzViewChangeTracking.sql</span></span>

<span data-ttu-id="9b492-143">Esses scripts garantem que os usuários, as funções e as configurações de controle de alterações estejam corretas.</span><span class="sxs-lookup"><span data-stu-id="9b492-143">These scripts ensure that the users, roles, and change tracking settings are correct.</span></span>

### <a name="execute-powershell-command-to-reset-database"></a><span data-ttu-id="9b492-144">Execute o comando PowerShell para redefinir o banco de dados.</span><span class="sxs-lookup"><span data-stu-id="9b492-144">Execute PowerShell command to reset database</span></span>

<span data-ttu-id="9b492-145">No computador AOS, execute os seguintes comandos no PowerShell como Administrador para redefinir a integração entre o Finance and Operations e os relatórios financeiros:</span><span class="sxs-lookup"><span data-stu-id="9b492-145">On the AOS computer, execute the following commands in PowerShell as an Administrator to reset the integration between Finance and Operations and financial reporting:</span></span>

```
F:
cd F:\MRApplicationService\MRInstallDirectory
Import-Module .\Server\MRDeploy\MRDeploy.psd1
Reset-DatamartIntegration -Reason OTHER -ReasonDetail “<my reason for resetting>”

```
> [!NOTE]
> <span data-ttu-id="9b492-146">Depois de executar os comandos, será solicitado que você pressione “Y” para confirmar.</span><span class="sxs-lookup"><span data-stu-id="9b492-146">After executing the commands, you will be asked to enter “Y” to confirm.</span></span>

<span data-ttu-id="9b492-147">Explicação dos parâmetros:</span><span class="sxs-lookup"><span data-stu-id="9b492-147">Explanation of parameters:</span></span>

-   <span data-ttu-id="9b492-148">Os valores válidos para -Reason são: SERVICING, BADDATA, OTHER.</span><span class="sxs-lookup"><span data-stu-id="9b492-148">The valid values for -Reason are: SERVICING, BADDATA, OTHER.</span></span>
-   <span data-ttu-id="9b492-149">O parâmetro -ReasonDetail é texto livre.</span><span class="sxs-lookup"><span data-stu-id="9b492-149">The -ReasonDetail parameter is free text.</span></span>
-   <span data-ttu-id="9b492-150">A razão e o reasonDetail serão registrados em telemetria/monitoramento de ambiente.</span><span class="sxs-lookup"><span data-stu-id="9b492-150">The reason and reasonDetail will be recorded in telemetry/environment monitoring.</span></span>

## <a name="start-services"></a><span data-ttu-id="9b492-151">Iniciar serviços</span><span class="sxs-lookup"><span data-stu-id="9b492-151">Start services</span></span>
<span data-ttu-id="9b492-152">Use o services.msc para reiniciar os serviços que você interrompeu anteriormente:</span><span class="sxs-lookup"><span data-stu-id="9b492-152">Use services.msc to restart the services that you stopped earlier:</span></span>

-   <span data-ttu-id="9b492-153">Serviço de publicação na Web (em todos os computadores AOS)</span><span class="sxs-lookup"><span data-stu-id="9b492-153">World wide web publishing service (on all AOS computers)</span></span>
-   <span data-ttu-id="9b492-154">Gerenciamento de Lotes do Microsoft Dynamics 365 for Finance and Operations (somente em computadores AOS não particulares)</span><span class="sxs-lookup"><span data-stu-id="9b492-154">Microsoft Dynamics 365 for Finance and Operations Batch Management Service (on non-private AOS computers only)</span></span>
-   <span data-ttu-id="9b492-155">Serviço de Processamento do Management Reporter 2012 (somente computadores BI)</span><span class="sxs-lookup"><span data-stu-id="9b492-155">Management Reporter 2012 Process Service (on BI computers only)</span></span>

## <a name="import-report-definitions"></a><span data-ttu-id="9b492-156">Importar definições de relatório</span><span class="sxs-lookup"><span data-stu-id="9b492-156">Import report definitions</span></span>
<span data-ttu-id="9b492-157">Importe seus designs de relatório do Report Designer, usando o arquivo criado durante a exportação:</span><span class="sxs-lookup"><span data-stu-id="9b492-157">Import your report designs from the Report Designer, using the file created during the export:</span></span>

1.  <span data-ttu-id="9b492-158">No Report Designer, vá para **Empresa** &gt; **Grupos do bloco de construção**.</span><span class="sxs-lookup"><span data-stu-id="9b492-158">In the Report Designer, go to **Company** &gt; **Building Block Groups**.</span></span>
2.  <span data-ttu-id="9b492-159">Selecione o grupo do bloco de construção para exportar, clique em **Exportar**.</span><span class="sxs-lookup"><span data-stu-id="9b492-159">Select the building block group to export, and click **Export**.</span></span> 

    > [!NOTE]
    > <span data-ttu-id="9b492-160">Para o Finanças e Operações, apenas um grupo de blocos de construção é suportado, **Padrão**.</span><span class="sxs-lookup"><span data-stu-id="9b492-160">For Finance and Operations, only one building block group is supported, **Default**.</span></span>
    
3.  <span data-ttu-id="9b492-161">Selecione o bloco de construção **Padrão** e clique em **Importar**.</span><span class="sxs-lookup"><span data-stu-id="9b492-161">Select the **Default** building block and click **Import**.</span></span>
4.  <span data-ttu-id="9b492-162">Selecione o arquivo que contém as definições de relatório exportadas e clique em **Abrir**.</span><span class="sxs-lookup"><span data-stu-id="9b492-162">Select the file containing the exported report definitions and click **Open**.</span></span>
5.  <span data-ttu-id="9b492-163">Na caixa de diálogo Importar, selecione as definições de relatório para importação:</span><span class="sxs-lookup"><span data-stu-id="9b492-163">In the Import dialog box, select the report definitions to import:</span></span>
    -   <span data-ttu-id="9b492-164">Para importar todas as definições de relatório e os blocos de construção de suporte, clique em **Selecionar Tudo**.</span><span class="sxs-lookup"><span data-stu-id="9b492-164">To import all the report definitions and the supporting building blocks, click **Select All**.</span></span>
    -   <span data-ttu-id="9b492-165">Para importar relatórios, linhas, colunas, árvores ou conjuntos de dimensões específicos, selecione os relatórios, as linhas, as colunas, as árvores ou os conjuntos de dimensões a serem importados.</span><span class="sxs-lookup"><span data-stu-id="9b492-165">To import specific reports, rows, columns, trees, or dimension sets, select the reports, rows, columns, trees, or dimension sets to import.</span></span>

6.  <span data-ttu-id="9b492-166">Clique em **Importar**.</span><span class="sxs-lookup"><span data-stu-id="9b492-166">Click **Import**.</span></span>





