---
title: "Redefinir data mart de relatório financeiro após restaurar um banco de dados"
description: "Este tópico descreve como redefinir o data mart de relatório financeiro após restaurar um banco de dados do Microsoft Dynamics 365 for Finance and Operations."
author: ShylaThompson
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-platform
ms.technology: 
audience: Application User, IT Pro
ms.reviewer: shylaw
ms.search.scope: Core, Operations, UnifiedOperations
ms.custom: 261824
ms.assetid: d0784b2c-fe10-428d-8d07-fd474ca50fcc
ms.search.region: Global
ms.author: kweekley
ms.search.validFrom: 2016-11-30
ms.dyn365.ops.version: Version 1611
ms.translationtype: HT
ms.sourcegitcommit: 9953d2f29a67b35f4bb43f577df1c4d910e379a1
ms.openlocfilehash: 08a420a776f47119a5dc47f9119545aa448ffdbd
ms.contentlocale: pt-br
ms.lasthandoff: 08/03/2017

---

# <a name="reset-the-financial-reporting-data-mart-after-restoring-a-database"></a><span data-ttu-id="de6c6-103">Redefinir data mart de relatório financeiro após restaurar um banco de dados</span><span class="sxs-lookup"><span data-stu-id="de6c6-103">Reset the financial reporting data mart after restoring a database</span></span>

[!include[banner](../includes/banner.md)]


<span data-ttu-id="de6c6-104">Este tópico descreve como redefinir o data mart de relatório financeiro após restaurar um banco de dados do Microsoft Dynamics 365 for Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="de6c6-104">This topic describes how to reset the financial reporting data mart after restoring a Microsoft Dynamics 365 for Finance and Operations database.</span></span>

<span data-ttu-id="de6c6-105">Se restaurar a banco de dados do Finance and Operations a partir de um backup ou copiar o banco de dados de outro ambiente, você deve seguir as etapas deste tópico para garantir que o data mart de relatório financeiro está usando corretamente o banco de dados restaurado do Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="de6c6-105">If you ever restore your Finance and Operations database from a backup or copy the database from another environment, you must follow the steps in this topic to ensure that the financial reporting data mart is correctly using the restored Finance and Operations database.</span></span> 
<!--If you have questions about resetting the financial reporting data mart for a reason outside of restoring a Finance and Operations database, refer to the [Resetting the Management Reporter data mart](https://blogs.msdn.microsoft.com/dynamics_financial_reporting/2016/06/28/resetting-the-management-reporter-data-mart/) for more information. -->
> [!Note] 
> <span data-ttu-id="de6c6-106">As etapas deste processo têm suporte na versão de maio de 2016 do Dynamics 365 for Operations (compilação de aplicativo 7.0.1265.23014 e compilação de geração de relatórios financeiros 7.0.10000.4) e versões mais recentes.</span><span class="sxs-lookup"><span data-stu-id="de6c6-106">The steps in this process are supported for Dynamics 365 for Operation May 2016 release (App build 7.0.1265.23014 and financial reporting build 7.0.10000.4) and newer releases.</span></span> <span data-ttu-id="de6c6-107">Se você tiver uma versão anterior do Finance and Operations, contate nossa Equipe de suporte para obter assistência.</span><span class="sxs-lookup"><span data-stu-id="de6c6-107">If you have an earlier release of Finance and Operations, contact our Support team for assistance.</span></span>

## <a name="export-report-definitions"></a><span data-ttu-id="de6c6-108">Exportar definições de relatório</span><span class="sxs-lookup"><span data-stu-id="de6c6-108">Export report definitions</span></span>
<span data-ttu-id="de6c6-109">Primeiro, exporte os projetos de relatório localizados no Report Designer, usando as seguintes etapas:</span><span class="sxs-lookup"><span data-stu-id="de6c6-109">First, export the report designs located in the Report Designer, using the following steps:</span></span>

1.  <span data-ttu-id="de6c6-110">No Report Designer, vá para **Empresa** &gt; **Grupos do bloco de construção**.</span><span class="sxs-lookup"><span data-stu-id="de6c6-110">In the Report Designer, go to **Company** &gt; **Building Block Groups**.</span></span>
2.  <span data-ttu-id="de6c6-111">Selecione o grupo do bloco de construção para exportar, clique em **Exportar**.</span><span class="sxs-lookup"><span data-stu-id="de6c6-111">Select the building block group to export, and click **Export**.</span></span> 
    > [!Note] 
    > <span data-ttu-id="de6c6-112">Para o Finanças e Operações, apenas um grupo de blocos de construção é suportado, **Padrão**.</span><span class="sxs-lookup"><span data-stu-id="de6c6-112">For Finance and Operations, only one building block group is supported, **Default**.</span></span>
3.  <span data-ttu-id="de6c6-113">Selecione as definições de relatório a serem exportadas:</span><span class="sxs-lookup"><span data-stu-id="de6c6-113">Select the report definitions to export:</span></span>
    -   <span data-ttu-id="de6c6-114">Para exportar todas as definições de relatório e os blocos de construção associados, clique em **Selecionar Tudo**.</span><span class="sxs-lookup"><span data-stu-id="de6c6-114">To export all your report definitions and the associated building blocks, click **Select All**.</span></span>
    -   <span data-ttu-id="de6c6-115">Para exportar relatórios, linhas, colunas, árvores ou conjuntos de dimensões específicos, clique na guia apropriada e selecione os itens a serem exportados.</span><span class="sxs-lookup"><span data-stu-id="de6c6-115">To export specific reports, rows, columns, trees, or dimension sets, click the appropriate tab, and then select the items to export.</span></span> <span data-ttu-id="de6c6-116">Pressione e mantenha pressionada a tecla Ctrl para selecionar vários itens em uma guia.</span><span class="sxs-lookup"><span data-stu-id="de6c6-116">Press and hold the Ctrl key to select multiple items in a tab.</span></span> <span data-ttu-id="de6c6-117">Quando você seleciona relatórios para exportação, as linhas, colunas, árvores e conjuntos de dimensões associados são selecionados.</span><span class="sxs-lookup"><span data-stu-id="de6c6-117">When you select reports to export, the associated rows, columns, trees, and dimension sets are selected.</span></span>

4.  <span data-ttu-id="de6c6-118">Clique em **Exportar**.</span><span class="sxs-lookup"><span data-stu-id="de6c6-118">Click **Export**.</span></span>
5.  <span data-ttu-id="de6c6-119">Insira um nome de arquivo e selecione um local seguro onde deseja salvar as definições de relatório exportadas.</span><span class="sxs-lookup"><span data-stu-id="de6c6-119">Enter a file name and select a secure location where you want to save the exported report definitions.</span></span>
6.  <span data-ttu-id="de6c6-120">Clique em **Salvar**.</span><span class="sxs-lookup"><span data-stu-id="de6c6-120">Click **Save**.</span></span>

<span data-ttu-id="de6c6-121">O arquivo pode ser copiado ou carregado em um local seguro, permitindo que seja importado em um ambiente em outro momento.</span><span class="sxs-lookup"><span data-stu-id="de6c6-121">The file can be copied or uploaded to a secure location, allowing it to be imported into a different environment at another time.</span></span> <span data-ttu-id="de6c6-122">Informações sobre como usar uma conta de armazenamento do Microsoft Azure podem ser encontradas em [Transferir dados com o utilitário de linha de comando AzCopy](https://docs.microsoft.com/en-gb/azure/storage/storage-use-azcopy).</span><span class="sxs-lookup"><span data-stu-id="de6c6-122">Information about using a Microsoft Azure storage account can be found in [Transfer data with the AzCopy Command-Line Utility](https://docs.microsoft.com/en-gb/azure/storage/storage-use-azcopy).</span></span> 
> [!NOTE]
> <span data-ttu-id="de6c6-123">A Microsoft não fornece uma conta de armazenamento como parte do seu contrato do Finanças e Operações.</span><span class="sxs-lookup"><span data-stu-id="de6c6-123">Microsoft doesn’t provide a storage account as part of your Finance and Operations agreement.</span></span> <span data-ttu-id="de6c6-124">Você deve comprar uma conta de armazenamento ou usar uma conta de armazenamento de uma subscrição separada do Azure.</span><span class="sxs-lookup"><span data-stu-id="de6c6-124">You must either purchase a storage account or use a storage account from a separate Azure subscription.</span></span> 
> [!WARNING]
> <span data-ttu-id="de6c6-125">Esteja ciente do comportamento da unidade D no Azure Virtual Machines.</span><span class="sxs-lookup"><span data-stu-id="de6c6-125">Be aware of the behavior of the D drive on Azure Virtual Machines.</span></span> <span data-ttu-id="de6c6-126">Não mantenha seus grupos de blocos de construção exportados aqui permanentemente.</span><span class="sxs-lookup"><span data-stu-id="de6c6-126">Do not keep your exported building block groups here permanently.</span></span> <span data-ttu-id="de6c6-127">Para obter mais informações sobre unidades temporárias, consulte [Entendendo a unidade temporária nas máquinas virtuais do Windows Azure](https://blogs.msdn.microsoft.com/mast/2013/12/06/understanding-the-temporary-drive-on-windows-azure-virtual-machines/).</span><span class="sxs-lookup"><span data-stu-id="de6c6-127">For more information about temporary drives, see [Understanding the temporary drive on Windows Azure Virtual Machines](https://blogs.msdn.microsoft.com/mast/2013/12/06/understanding-the-temporary-drive-on-windows-azure-virtual-machines/).</span></span>

## <a name="stop-services"></a><span data-ttu-id="de6c6-128">Interromper serviços</span><span class="sxs-lookup"><span data-stu-id="de6c6-128">Stop services</span></span>
<span data-ttu-id="de6c6-129">Use a Área de Trabalho Remota para se conectar a todos os computadores no ambiente e parar os seguintes serviços do Windows usando services.msc:</span><span class="sxs-lookup"><span data-stu-id="de6c6-129">Use Remote Desktop to connect to all the computers in the environment and stop the following Windows services by using services.msc:</span></span>

-   <span data-ttu-id="de6c6-130">Serviço de publicação na Web (em todos os computadores AOS)</span><span class="sxs-lookup"><span data-stu-id="de6c6-130">World wide web publishing service (on all AOS computers)</span></span>
-   <span data-ttu-id="de6c6-131">Gerenciamento de Lotes do Microsoft Dynamics 365 for Finance and Operations (somente em computadores AOS não particulares)</span><span class="sxs-lookup"><span data-stu-id="de6c6-131">Microsoft Dynamics 365 for Finance and Operations Batch Management Service (on non-private AOS computers only)</span></span>
-   <span data-ttu-id="de6c6-132">Serviço de Processamento do Management Reporter 2012 (somente computadores BI)</span><span class="sxs-lookup"><span data-stu-id="de6c6-132">Management Reporter 2012 Process Service (on BI computers only)</span></span>

<span data-ttu-id="de6c6-133">Esses serviços terão conexões abertas com o banco de dados do Finanças e Operações.</span><span class="sxs-lookup"><span data-stu-id="de6c6-133">These services will have open connections to the Finance and Operations database.</span></span>

## <a name="reset"></a><span data-ttu-id="de6c6-134">Redefinir</span><span class="sxs-lookup"><span data-stu-id="de6c6-134">Reset</span></span>
#### <a name="locate-and-download-the-latest-minorversiondataupgradezip-package"></a><span data-ttu-id="de6c6-135">Localizar e baixar o pacote MinorVersionDataUpgrade.zip mais recente</span><span class="sxs-lookup"><span data-stu-id="de6c6-135">Locate and download the latest MinorVersionDataUpgrade.zip package</span></span>

<span data-ttu-id="de6c6-136">Localize o pacote MinorVersionDataUpgrade.zip mais recente usando as instruções encontradas em [Baixar o pacote implantável de atualização de dados mais recente](..\migration-upgrade\upgrade-data-to-latest-update.md#download-the-latest-data-upgrade-deployable-package).</span><span class="sxs-lookup"><span data-stu-id="de6c6-136">Locate the latest MinorVersionDataUpgrade.zip package using the directions found in [Download the latest data upgrade deployable package](..\migration-upgrade\upgrade-data-to-latest-update.md#download-the-latest-data-upgrade-deployable-package).</span></span> <span data-ttu-id="de6c6-137">As instruções explicam como localizar e baixar a versão correta do pacote de atualização de dados.</span><span class="sxs-lookup"><span data-stu-id="de6c6-137">The directions explain how to locate and download the correct version of the data upgrade package.</span></span> <span data-ttu-id="de6c6-138">Não é necessária uma atualização para baixar o pacote MinorVersionDataUpgrade.zip.</span><span class="sxs-lookup"><span data-stu-id="de6c6-138">An upgrade is not required to download the MinorVersionDataUpgrade.zip package.</span></span> <span data-ttu-id="de6c6-139">Basta concluir as etapas na seção "Baixar o pacote implantável de atualização de dados mais recente" sem executar nenhuma das outras etapas no artigo para recuperar uma cópia do pacote MinorVersionDataUpgrade.zip.</span><span class="sxs-lookup"><span data-stu-id="de6c6-139">You only need to complete the steps in the “Download the latest data upgrade deployable package” section without performing any of the other steps in the article to retrieve a copy of the MinorVersionDataUpgrade.zip package.</span></span>

#### <a name="execute-scripts-against-finance-and-operations-database"></a><span data-ttu-id="de6c6-140">Executar scripts no banco de dados do Finanças e Operações</span><span class="sxs-lookup"><span data-stu-id="de6c6-140">Execute scripts against Finance and Operations database</span></span>

<span data-ttu-id="de6c6-141">Execute os seguintes scripts no banco de dados do Finanças e Operações (não no banco de dados de relatórios financeiros).</span><span class="sxs-lookup"><span data-stu-id="de6c6-141">Run the following scripts against the Finance and Operations database (not against the financial reporting database).</span></span>

-   <span data-ttu-id="de6c6-142">DataUpgrade.zip\\AosService\\Scripts\\ConfigureAxReportingIntegration.sql</span><span class="sxs-lookup"><span data-stu-id="de6c6-142">DataUpgrade.zip\\AosService\\Scripts\\ConfigureAxReportingIntegration.sql</span></span>
-   <span data-ttu-id="de6c6-143">DataUpgrade.zip\\AosService\\Scripts\\GrantAzViewChangeTracking.sql</span><span class="sxs-lookup"><span data-stu-id="de6c6-143">DataUpgrade.zip\\AosService\\Scripts\\GrantAzViewChangeTracking.sql</span></span>

<span data-ttu-id="de6c6-144">Esses scripts garantem que os usuários, as funções e as configurações de controle de alterações estejam corretas.</span><span class="sxs-lookup"><span data-stu-id="de6c6-144">These scripts ensure that the users, roles, and change tracking settings are correct.</span></span>

#### <a name="execute-powershell-command-to-reset-database"></a><span data-ttu-id="de6c6-145">Execute o comando PowerShell para redefinir o banco de dados.</span><span class="sxs-lookup"><span data-stu-id="de6c6-145">Execute PowerShell command to reset database</span></span>

<span data-ttu-id="de6c6-146">Execute o seguinte comando, diretamente no computador AOS, para redefinir a integração entre o Finanças e Operações e os relatórios financeiros:</span><span class="sxs-lookup"><span data-stu-id="de6c6-146">Execute the following command, directly on the AOS computer, to reset the integration between Finance and Operations and financial reporting:</span></span>

1.  <span data-ttu-id="de6c6-147">Abra o Windows PowerShell como administrador.</span><span class="sxs-lookup"><span data-stu-id="de6c6-147">Open Windows PowerShell as Administrator.</span></span>
2.  <span data-ttu-id="de6c6-148">Execute: F:</span><span class="sxs-lookup"><span data-stu-id="de6c6-148">Execute: F:</span></span>
3.  <span data-ttu-id="de6c6-149">Execute: cd F:\\MRApplicationService\\MRInstallDirectory</span><span class="sxs-lookup"><span data-stu-id="de6c6-149">Execute: cd F:\\MRApplicationService\\MRInstallDirectory</span></span>
4.  <span data-ttu-id="de6c6-150">Execute: Import-Module .\\Server\\MRDeploy\\MRDeploy.psd1</span><span class="sxs-lookup"><span data-stu-id="de6c6-150">Execute: Import-Module .\\Server\\MRDeploy\\MRDeploy.psd1</span></span>
5.  <span data-ttu-id="de6c6-151">Execute: Reset-DatamartIntegration -Reason OTHER -ReasonDetail “&lt;motivo para redefinir&gt;”</span><span class="sxs-lookup"><span data-stu-id="de6c6-151">Execute: Reset-DatamartIntegration -Reason OTHER -ReasonDetail “&lt;my reason for resetting&gt;”</span></span>
    -   <span data-ttu-id="de6c6-152">Será solicitado que você pressione “Y” para confirmar.</span><span class="sxs-lookup"><span data-stu-id="de6c6-152">You will be asked to enter “Y” to confirm.</span></span>

<span data-ttu-id="de6c6-153">Explicação dos parâmetros:</span><span class="sxs-lookup"><span data-stu-id="de6c6-153">Explanation of parameters:</span></span>

-   <span data-ttu-id="de6c6-154">Os valores válidos para -Reason são: SERVICING, BADDATA, OTHER.</span><span class="sxs-lookup"><span data-stu-id="de6c6-154">The valid values for -Reason are: SERVICING, BADDATA, OTHER.</span></span>
-   <span data-ttu-id="de6c6-155">O parâmetro -ReasonDetail é texto livre.</span><span class="sxs-lookup"><span data-stu-id="de6c6-155">The -ReasonDetail parameter is free text.</span></span>
-   <span data-ttu-id="de6c6-156">A razão e o reasonDetail serão registrados em telemetria/monitoramento de ambiente.</span><span class="sxs-lookup"><span data-stu-id="de6c6-156">The reason and reasonDetail will be recorded in telemetry/environment monitoring.</span></span>

## <a name="start-services"></a><span data-ttu-id="de6c6-157">Iniciar serviços</span><span class="sxs-lookup"><span data-stu-id="de6c6-157">Start services</span></span>
<span data-ttu-id="de6c6-158">Use o services.msc para reiniciar os serviços que você interrompeu anteriormente:</span><span class="sxs-lookup"><span data-stu-id="de6c6-158">Use services.msc to restart the services that you stopped earlier:</span></span>

-   <span data-ttu-id="de6c6-159">Serviço de publicação na Web (em todos os computadores AOS)</span><span class="sxs-lookup"><span data-stu-id="de6c6-159">World wide web publishing service (on all AOS computers)</span></span>
-   <span data-ttu-id="de6c6-160">Gerenciamento de Lotes do Microsoft Dynamics 365 for Finance and Operations (somente em computadores AOS não particulares)</span><span class="sxs-lookup"><span data-stu-id="de6c6-160">Microsoft Dynamics 365 for Finance and Operations Batch Management Service (on non-private AOS computers only)</span></span>
-   <span data-ttu-id="de6c6-161">Serviço de Processamento do Management Reporter 2012 (somente computadores BI)</span><span class="sxs-lookup"><span data-stu-id="de6c6-161">Management Reporter 2012 Process Service (on BI computers only)</span></span>

## <a name="import-report-definitions"></a><span data-ttu-id="de6c6-162">Importar definições de relatório</span><span class="sxs-lookup"><span data-stu-id="de6c6-162">Import report definitions</span></span>
<span data-ttu-id="de6c6-163">Importe seus designs de relatório do Report Designer, usando o arquivo criado durante a exportação:</span><span class="sxs-lookup"><span data-stu-id="de6c6-163">Import your report designs from the Report Designer, using the file created during the export:</span></span>

1.  <span data-ttu-id="de6c6-164">No Report Designer, vá para **Empresa** &gt; **Grupos do bloco de construção**.</span><span class="sxs-lookup"><span data-stu-id="de6c6-164">In the Report Designer, go to **Company** &gt; **Building Block Groups**.</span></span>
2.  <span data-ttu-id="de6c6-165">Selecione o grupo do bloco de construção para exportar, clique em **Exportar**.</span><span class="sxs-lookup"><span data-stu-id="de6c6-165">Select the building block group to export, and click **Export**.</span></span> 

    > [!NOTE]
    > <span data-ttu-id="de6c6-166">Para o Finanças e Operações, apenas um grupo de blocos de construção é suportado, **Padrão**.</span><span class="sxs-lookup"><span data-stu-id="de6c6-166">For Finance and Operations, only one building block group is supported, **Default**.</span></span>
    
3.  <span data-ttu-id="de6c6-167">Selecione o bloco de construção **Padrão** e clique em **Importar**.</span><span class="sxs-lookup"><span data-stu-id="de6c6-167">Select the **Default** building block and click **Import**.</span></span>
4.  <span data-ttu-id="de6c6-168">Selecione o arquivo que contém as definições de relatório exportadas e clique em **Abrir**.</span><span class="sxs-lookup"><span data-stu-id="de6c6-168">Select the file containing the exported report definitions and click **Open**.</span></span>
5.  <span data-ttu-id="de6c6-169">Na caixa de diálogo Importar, selecione as definições de relatório para importação:</span><span class="sxs-lookup"><span data-stu-id="de6c6-169">In the Import dialog box, select the report definitions to import:</span></span>
    -   <span data-ttu-id="de6c6-170">Para importar todas as definições de relatório e os blocos de construção de suporte, clique em **Selecionar Tudo**.</span><span class="sxs-lookup"><span data-stu-id="de6c6-170">To import all the report definitions and the supporting building blocks, click **Select All**.</span></span>
    -   <span data-ttu-id="de6c6-171">Para importar relatórios, linhas, colunas, árvores ou conjuntos de dimensões específicos, selecione os relatórios, as linhas, as colunas, as árvores ou os conjuntos de dimensões a serem importados.</span><span class="sxs-lookup"><span data-stu-id="de6c6-171">To import specific reports, rows, columns, trees, or dimension sets, select the reports, rows, columns, trees, or dimension sets to import.</span></span>

6.  <span data-ttu-id="de6c6-172">Clique em **Importar**.</span><span class="sxs-lookup"><span data-stu-id="de6c6-172">Click **Import**.</span></span>





