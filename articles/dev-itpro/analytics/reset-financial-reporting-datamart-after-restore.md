---
title: "Redefinir o data mart de relatórios Financeiros"
description: "Este tópico descreve como redefinir o data mart de relatórios financeiros."
author: aolson
manager: AnnBe
ms.date: 12/01/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-platform
ms.technology: 
audience: Application User, IT Pro
ms.reviewer: twheeloc
ms.search.scope: Core, Operations
ms.custom: 261824
ms.search.region: Global
ms.author: aloson
ms.search.validFrom: 2016-11-30
ms.dyn365.ops.version: Version 1611
ms.translationtype: HT
ms.sourcegitcommit: 0786d3377b914791106ef30455d676e5ab2ae03d
ms.openlocfilehash: c708fa18b8676d8ff57c26b3176a36d86df29387
ms.contentlocale: pt-br
ms.lasthandoff: 12/07/2017

---

# <a name="reset-the-financial-reporting-data-mart"></a><span data-ttu-id="65ce5-103">Redefinir o data mart de relatórios Financeiros</span><span class="sxs-lookup"><span data-stu-id="65ce5-103">Reset the Financial reporting data mart</span></span>

[!include[banner](../includes/banner.md)]

<span data-ttu-id="65ce5-104">Este tópico explica como redefinir data mart de relatórios financeiros para as seguintes versões:</span><span class="sxs-lookup"><span data-stu-id="65ce5-104">This topic explains how to reset the Financial reporting data mart for the following versions:</span></span>

- <span data-ttu-id="65ce5-105">Microsoft Dynamics 365 for Finance and Operations: versão 7.2.6.0 e posterior de relatórios financeiros</span><span class="sxs-lookup"><span data-stu-id="65ce5-105">Microsoft Dynamics 365 for Finance and Operations Financial reporting release 7.2.6.0 and later</span></span>
- <span data-ttu-id="65ce5-106">Microsoft Dynamics 365 for Finance and Operations: versão 7.0.10000.4 e posterior de relatórios financeiros</span><span class="sxs-lookup"><span data-stu-id="65ce5-106">Microsoft Dynamics 365 for Finance and Operations Financial reporting release 7.0.10000.4 and later</span></span>
- <span data-ttu-id="65ce5-107">Microsoft Dynamics 365 for Finance and Operations, Enterprise edition (local)</span><span class="sxs-lookup"><span data-stu-id="65ce5-107">Microsoft Dynamics 365 for Finance and Operations, Enterprise edition (on-premises)</span></span>

<span data-ttu-id="65ce5-108">Para obter a versão 7.2.6.0 de relatórios financeiros do Finance and Operations, você pode fazer download do KB 4052514 de <https://support.microsoft.com/en-us/help/4052514>.</span><span class="sxs-lookup"><span data-stu-id="65ce5-108">To get Finance and Operations Financial reporting release 7.2.6.0, you can download KB 4052514 from <https://support.microsoft.com/en-us/help/4052514>.</span></span>

## <a name="reset-the-financial-reporting-data-mart-for-finance-and-operations-financial-reporting-release-7260-and-later"></a><span data-ttu-id="65ce5-109">Redefinir o data mart de relatórios financeiros da versão 7.2.6.0 e posterior de relatórios financeiros do Finance and Operations</span><span class="sxs-lookup"><span data-stu-id="65ce5-109">Reset the Financial reporting data mart for Finance and Operations Financial reporting release 7.2.6.0 and later</span></span>

### <a name="reset-the-financial-reporting-data-mart-from-report-designer"></a><span data-ttu-id="65ce5-110">Redefinir o data mart de relatórios financeiros do designer de relatórios</span><span class="sxs-lookup"><span data-stu-id="65ce5-110">Reset the Financial reporting data mart from Report designer</span></span>

> [!NOTE]
> <span data-ttu-id="65ce5-111">As etapas deste processo são suportadas para a versão 7.2.6.0 e posterior de relatórios financeiros do Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="65ce5-111">The steps in this process are supported for Finance and Operations Financial reporting release 7.2.6.0 and later.</span></span> <span data-ttu-id="65ce5-112">Se você tiver uma versão anterior, entre em contato com a equipe de suporte para obter ajuda.</span><span class="sxs-lookup"><span data-stu-id="65ce5-112">If you have an earlier release, contact the Support team for assistance.</span></span>

<span data-ttu-id="65ce5-113">Em cenários específicos, talvez seja necessário redefinir o data mart para relatórios financeiros.</span><span class="sxs-lookup"><span data-stu-id="65ce5-113">In specific scenarios, you might have to reset the data mart for Financial reporting.</span></span> <span data-ttu-id="65ce5-114">Você pode concluir esta tarefa no cliente do designer de relatórios.</span><span class="sxs-lookup"><span data-stu-id="65ce5-114">You can complete this task in the Report designer client.</span></span> <span data-ttu-id="65ce5-115">Veja alguns cenários nos quais pode ser necessário redefinir o data mart:</span><span class="sxs-lookup"><span data-stu-id="65ce5-115">Here are some scenarios where you might have to reset the data mart:</span></span>

- <span data-ttu-id="65ce5-116">O banco de dados do Finance and Operations foi restaurado, mas o banco de dados do data mart não foi.</span><span class="sxs-lookup"><span data-stu-id="65ce5-116">The Finance and Operations database was restored, but the data mart database wasn't restored.</span></span>
- <span data-ttu-id="65ce5-117">Você vê dados incorretos para um período.</span><span class="sxs-lookup"><span data-stu-id="65ce5-117">You see incorrect data for a period.</span></span>
- <span data-ttu-id="65ce5-118">O suporte o instrui para redefinir o data mart como parte de uma etapa de solução de problemas.</span><span class="sxs-lookup"><span data-stu-id="65ce5-118">Support instructs you to reset the data mart as part of a troubleshooting step.</span></span>

<span data-ttu-id="65ce5-119">A redefinição de data mart deve ser feita somente durante momentos em que o valor de processamento no banco de dados é pequeno.</span><span class="sxs-lookup"><span data-stu-id="65ce5-119">The data mart reset should be done only during times when the amount of processing on the database is small.</span></span> <span data-ttu-id="65ce5-120">O relatório financeiro ficará indisponível durante o processo de redefinição.</span><span class="sxs-lookup"><span data-stu-id="65ce5-120">Financial reporting will be unavailable during the reset process.</span></span>

#### <a name="reset-the-data-mart"></a><span data-ttu-id="65ce5-121">Redefinir o data mart</span><span class="sxs-lookup"><span data-stu-id="65ce5-121">Reset the data mart</span></span>

<span data-ttu-id="65ce5-122">Para redefinir o data mart, no designer de Relatório, no menu **Ferramentas**, selecione **Redefinir Data Mart**.</span><span class="sxs-lookup"><span data-stu-id="65ce5-122">To reset the data mart, in Report designer, on the **Tools** menu, select **Reset Data Mart**.</span></span> <span data-ttu-id="65ce5-123">A caixa de diálogo que aparece tem duas seções: **Estatística** e **Redefinir**.</span><span class="sxs-lookup"><span data-stu-id="65ce5-123">The dialog box that appears has two sections: **Statistics** and **Reset**.</span></span>

<span data-ttu-id="65ce5-124">[![Caixa de diálogo Redefinir Data Mart](./media/Statistics.png)](./media/Statistics.png)</span><span class="sxs-lookup"><span data-stu-id="65ce5-124">[![Reset Data Mart dialog box](./media/Statistics.png)](./media/Statistics.png)</span></span>

##### <a name="integration-attempts"></a><span data-ttu-id="65ce5-125">Tentativas de integração</span><span class="sxs-lookup"><span data-stu-id="65ce5-125">Integration attempts</span></span>

<span data-ttu-id="65ce5-126">A grade **Tentativas de integração** mostra quantas vezes o sistema tentou integrar as transações.</span><span class="sxs-lookup"><span data-stu-id="65ce5-126">The **Integration attempts** grid shows how many times the system has tried to integrate transactions.</span></span> <span data-ttu-id="65ce5-127">O sistema continua tentando integrar os dados durante um período, se as primeiras tentativas falharem.</span><span class="sxs-lookup"><span data-stu-id="65ce5-127">The system continues to try to integrate data over a period of days if the first few attempts aren't successful.</span></span> <span data-ttu-id="65ce5-128">Você saberá se o data mart deve ser redefinido, se o número de tentativas for 8 ou mais, e se houver muitas combinações de Dimensão ou registros da Transação.</span><span class="sxs-lookup"><span data-stu-id="65ce5-128">You will know that the data mart must be reset is if the number of attempts is 8 or more, and if there are many Dimension combination or Transaction records.</span></span> <span data-ttu-id="65ce5-129">Nessa situação, os dados não serão reportados.</span><span class="sxs-lookup"><span data-stu-id="65ce5-129">In this situation, the data won't be reported on.</span></span>

##### <a name="data-status"></a><span data-ttu-id="65ce5-130">Status dos dados</span><span class="sxs-lookup"><span data-stu-id="65ce5-130">Data status</span></span>

<span data-ttu-id="65ce5-131">A grade **Status de dados** fornece um instantâneo de transações, taxas de câmbio e valores de dimensão no data mart.</span><span class="sxs-lookup"><span data-stu-id="65ce5-131">The **Data status** grid provides a snapshot of the transactions, exchange rates, and dimension values in the data mart.</span></span> <span data-ttu-id="65ce5-132">Um grande número de registros desatualizados indica que ocorreram várias atualizações nos registros.</span><span class="sxs-lookup"><span data-stu-id="65ce5-132">A large number of stale records indicates that numerous updates to the records have occurred.</span></span> <span data-ttu-id="65ce5-133">Essa situação pode causar lentidão na geração do relatório.</span><span class="sxs-lookup"><span data-stu-id="65ce5-133">This situation might cause slower report generation times.</span></span>

##### <a name="misaligned-main-account-categories"></a><span data-ttu-id="65ce5-134">Categorias desalinhadas da conta principal</span><span class="sxs-lookup"><span data-stu-id="65ce5-134">Misaligned main account categories</span></span>

<span data-ttu-id="65ce5-135">Se estiver usando uma versão que seja anterior à versão 7.2.1 de relatórios financeiros do Microsoft Dynamics 365 for Finance and Operations Financial, pode ser necessário redefinir o data mart, se você renomear as contas e movê-las entre as categorias de conta.</span><span class="sxs-lookup"><span data-stu-id="65ce5-135">If you're using a release that is earlier than Microsoft Dynamics 365 for Finance and Operations Financial reporting release 7.2.1, you might have to reset the data mart if you rename accounts and move accounts between account categories.</span></span> <span data-ttu-id="65ce5-136">Essas ações podem fazer com que as categorias de conta principal fiquem desalinhadas.</span><span class="sxs-lookup"><span data-stu-id="65ce5-136">These actions can cause main account categories to become misaligned.</span></span> <span data-ttu-id="65ce5-137">O campo **Categorias de conta principal desalinhadas** mostra se você está enfrentando esse problema.</span><span class="sxs-lookup"><span data-stu-id="65ce5-137">The **Misaligned main account categories** field shows whether you're experiencing that issue.</span></span>

### <a name="reset-the-data-mart-in-finance-and-operations-financial-reporting-release-7260"></a><span data-ttu-id="65ce5-138">Redefina o data mart na versão 7.2.6.0 de relatórios financeiros do Finance and Operations</span><span class="sxs-lookup"><span data-stu-id="65ce5-138">Reset the data mart in Finance and Operations Financial reporting release 7.2.6.0</span></span>

<span data-ttu-id="65ce5-139">Para redefinir o data mart na versão 7.2.6.0 e posterior de relatórios financeiros do Finance and Operations, na caixa de diálogo **Redefinir Data Mart**, marque a caixa de seleção **Redefinir data mart** e selecione **OK**.</span><span class="sxs-lookup"><span data-stu-id="65ce5-139">To reset the data mart in Finance and Operations Financial reporting release 7.2.6.0 and earlier, in the **Reset Data Mart** dialog box, select the **Reset data mart** check box, and then select **OK**.</span></span> <span data-ttu-id="65ce5-140">Você deve redefinir o data mart apenas durante o tempo de inatividade programado.</span><span class="sxs-lookup"><span data-stu-id="65ce5-140">You should reset the data mart only during scheduled downtime.</span></span>

<span data-ttu-id="65ce5-141">[![Caixa de diálogo Redefinir data mart](./media/Reset-72.jpg)](./media/Reset-72.jpg)</span><span class="sxs-lookup"><span data-stu-id="65ce5-141">[![Reset data mart check box](./media/Reset-72.jpg)](./media/Reset-72.jpg)</span></span>

### <a name="reset-the-data-mart-and-select-a-reason-in-microsoft-dynamics-365-for-finance-and-operations-financial-reporting-release-730"></a><span data-ttu-id="65ce5-142">Redefinir o data mart e selecionar um motivo na versão 7.3.0 de relatórios financeiros do Microsoft Dynamics 365 for Finance and Operations</span><span class="sxs-lookup"><span data-stu-id="65ce5-142">Reset the data mart and select a reason in Microsoft Dynamics 365 for Finance and Operations Financial reporting release 7.3.0</span></span>

<span data-ttu-id="65ce5-143">Se você determinar que uma redefinição do data mart é necessária, marque a caixa de seleção **Redefinir data mart** e selecione um motivo no campo **Motivo**.</span><span class="sxs-lookup"><span data-stu-id="65ce5-143">If you determine that a data mart reset is required, select the **Reset data mart** check box, and then select a reason in the **Reason** field.</span></span> <span data-ttu-id="65ce5-144">As opções a seguir estão disponíveis:</span><span class="sxs-lookup"><span data-stu-id="65ce5-144">The following options are available:</span></span>

- <span data-ttu-id="65ce5-145">**Dados incorretos ou ausentes** baseado nas estatísticas, você determinou que talvez faltem dados.</span><span class="sxs-lookup"><span data-stu-id="65ce5-145">**Missing or incorrect data** – Based on the statistics, you've determined that data might be missing.</span></span> <span data-ttu-id="65ce5-146">Antes de continuar, recomendamos que trabalhe com o suporte para determinar a causa raiz.</span><span class="sxs-lookup"><span data-stu-id="65ce5-146">Before you continue, we recommend that you work with Support to determine the root cause.</span></span>
- <span data-ttu-id="65ce5-147">**Restaurar banco de dados** – O banco de dados do Finance and Operations foi restaurado, mas o banco de dados do data mart não foi.</span><span class="sxs-lookup"><span data-stu-id="65ce5-147">**Restore database** – The Finance and Operations database was restored, but the database for the Financial reporting data mart wasn't restored.</span></span>
- <span data-ttu-id="65ce5-148">**Outro** – Você está redefinindo o data mart por outro motivo.</span><span class="sxs-lookup"><span data-stu-id="65ce5-148">**Other** – You're resetting the data mart for another reason.</span></span> <span data-ttu-id="65ce5-149">Se você acha que há um problema, entre em contato com o suporte para identificá-lo.</span><span class="sxs-lookup"><span data-stu-id="65ce5-149">If you're concerned that there is an issue, contact Support to identify it.</span></span>

> [!NOTE]
> <span data-ttu-id="65ce5-150">Verifique se todas as tarefas existentes finalizaram a integração antes de concluir as etapas.</span><span class="sxs-lookup"><span data-stu-id="65ce5-150">Verify that all existing tasks have finished integrating before you complete the steps.</span></span> <span data-ttu-id="65ce5-151">Você pode exibir o status da integração selecionando **Ferramentas** &gt; **Status de integração**.</span><span class="sxs-lookup"><span data-stu-id="65ce5-151">You can view the status of the integration by selecting **Tools** &gt; **Integration status**.</span></span>

#### <a name="clear-users-and-companies"></a><span data-ttu-id="65ce5-152">Limpar usuários e empresas</span><span class="sxs-lookup"><span data-stu-id="65ce5-152">Clear users and companies</span></span>

<span data-ttu-id="65ce5-153">Marque a caixa de seleção **Limpar usuários e empresas** se você restaurou seu banco de dados, mas depois fez alterações em usuários ou empresas.</span><span class="sxs-lookup"><span data-stu-id="65ce5-153">Select the **Clear users and companies** check box if you restored your database, but you then made changes to users or companies.</span></span> <span data-ttu-id="65ce5-154">Raramente você deverá marcar esta caixa de seleção.</span><span class="sxs-lookup"><span data-stu-id="65ce5-154">You should rarely have to select this check box.</span></span>

<span data-ttu-id="65ce5-155">Quando estiver pronto para iniciar o processo de redefinição, selecione **OK**.</span><span class="sxs-lookup"><span data-stu-id="65ce5-155">When you're ready to start the reset process, select **OK**.</span></span> <span data-ttu-id="65ce5-156">Será solicitado que confirme que está pronto para iniciar o processo.</span><span class="sxs-lookup"><span data-stu-id="65ce5-156">You're prompted to confirm that you're ready to start the process.</span></span> <span data-ttu-id="65ce5-157">Observe que o relatório financeiro não estará disponível durante a redefinição e a integração de dados inicial que ocorrerá posteriormente.</span><span class="sxs-lookup"><span data-stu-id="65ce5-157">Note that Financial reporting won't be available during the reset and the initial data integration that occurs afterward.</span></span>

<span data-ttu-id="65ce5-158">Se quiser revisar o status de integração, selecione **Ferramentas** &gt; **Status de integração** para ver a última vez que a integração e o status foram executados.</span><span class="sxs-lookup"><span data-stu-id="65ce5-158">If you want to review the status of the integration, select **Tools** &gt; **Integration status** to see the last time that the integration was run and the status.</span></span>

<span data-ttu-id="65ce5-159">[![Exiba o status da integração](./media/Integration.png)](./media/Integration.png)</span><span class="sxs-lookup"><span data-stu-id="65ce5-159">[![View the status of the integration](./media/Integration.png)](./media/Integration.png)</span></span>

## <a name="reset-the-financial-reporting-data-mart-for-finance-and-operations-financial-reporting-release-70100004-and-later"></a><span data-ttu-id="65ce5-160">Redefinir o data mart de relatórios financeiros da versão 7.0.10000.4 e posterior de relatórios financeiros do Finance and Operations</span><span class="sxs-lookup"><span data-stu-id="65ce5-160">Reset the Financial reporting data mart for Finance and Operations Financial reporting release 7.0.10000.4 and later</span></span>

<span data-ttu-id="65ce5-161">Se você já restaurou seu banco de dados do Finance and Operations de um backup ou cópia do banco de dados de outro ambiente, você deve seguir as etapas desta seção para ajudar a garantir que o data mart de relatórios Financeiros usa corretamente o banco de dados do Finance and Operations restaurado.</span><span class="sxs-lookup"><span data-stu-id="65ce5-161">If you ever restore your Finance and Operations database from a backup or copy the database from another environment, you must follow the steps in this section to help guarantee that the Financial reporting data mart correctly uses the restored Finance and Operations database.</span></span>

> [!NOTE]
> <span data-ttu-id="65ce5-162">As etapas deste processo são suportadas para a versão 7.0.1 do aplicativo do Microsoft Dynamics AX (maio 2016) (compilação 7.0.1265.23014 do aplicativo e compilação 7.0.10000.4 de relatórios financeiros) e posterior.</span><span class="sxs-lookup"><span data-stu-id="65ce5-162">The steps in this process are supported for Microsoft Dynamics AX application version 7.0.1 (May 2016) (application build 7.0.1265.23014 and Financial reporting build 7.0.10000.4) and later.</span></span> <span data-ttu-id="65ce5-163">Se você tiver uma versão anterior do Finance and Operations, contate o Suporte para obter ajuda.</span><span class="sxs-lookup"><span data-stu-id="65ce5-163">If you have an earlier version of Finance and Operations, contact Support for assistance.</span></span>

### <a name="export-report-definitions"></a><span data-ttu-id="65ce5-164">Exportar definições de relatório</span><span class="sxs-lookup"><span data-stu-id="65ce5-164">Export report definitions</span></span>

<span data-ttu-id="65ce5-165">Primeiro, siga estas etapas para exporta os designs de relatório do designer de relatório.</span><span class="sxs-lookup"><span data-stu-id="65ce5-165">First, follow these steps to export the report designs from Report designer.</span></span>

1. <span data-ttu-id="65ce5-166">No Designer de relatórios, selecione **Empresa** &gt; **Grupos de Blocos de Construção**.</span><span class="sxs-lookup"><span data-stu-id="65ce5-166">In Report designer, select **Company** &gt; **Building Block Groups**.</span></span>
2. <span data-ttu-id="65ce5-167">Selecione o grupo do bloco de construção para exportar, depois selecione **Exportar**.</span><span class="sxs-lookup"><span data-stu-id="65ce5-167">Select the building block group to export, and then select **Export**.</span></span>

    > [!NOTE]
    > <span data-ttu-id="65ce5-168">Para o Finanças e Operações, apenas um grupo de blocos de construção é suportado, **Padrão**.</span><span class="sxs-lookup"><span data-stu-id="65ce5-168">For Finance and Operations, only one building block group is supported, **Default**.</span></span>

3. <span data-ttu-id="65ce5-169">Selecione as definições de relatório a serem exportadas:</span><span class="sxs-lookup"><span data-stu-id="65ce5-169">Select the report definitions to export:</span></span>

    - <span data-ttu-id="65ce5-170">Para exportar todas as definições de relatório e os blocos de construção associados, clique em **Selecionar Tudo**.</span><span class="sxs-lookup"><span data-stu-id="65ce5-170">To export all your report definitions and the associated building blocks, select **Select All**.</span></span>
    - <span data-ttu-id="65ce5-171">Para exportar relatórios, linhas, colunas, árvores ou conjuntos de dimensões específicos, selecione a guia apropriada e selecione os itens a serem exportados.</span><span class="sxs-lookup"><span data-stu-id="65ce5-171">To export specific reports, rows, columns, trees, or dimension sets, select the appropriate tab, and then select the items to export.</span></span> <span data-ttu-id="65ce5-172">Pressione e mantenha pressionada a tecla Ctrl para selecionar vários itens em uma guia. Quando você selecionar relatórios para exportar, as linhas, as colunas, as hierarquias e os conjuntos de dimensões associados serão selecionados.</span><span class="sxs-lookup"><span data-stu-id="65ce5-172">Press and hold the Ctrl key to select multiple items on a tab. When you select reports to export, the associated rows, columns, trees, and dimension sets are selected.</span></span>

4. <span data-ttu-id="65ce5-173">Selecione **Exportar**.</span><span class="sxs-lookup"><span data-stu-id="65ce5-173">Select **Export**.</span></span>
5. <span data-ttu-id="65ce5-174">Insira um nome de arquivo e selecione um local seguro onde deseja salvar as definições de relatório exportadas.</span><span class="sxs-lookup"><span data-stu-id="65ce5-174">Enter a file name, and select a secure location where you want to save the exported report definitions.</span></span>
6. <span data-ttu-id="65ce5-175">Selecione **Salvar**.</span><span class="sxs-lookup"><span data-stu-id="65ce5-175">Select **Save**.</span></span>

<span data-ttu-id="65ce5-176">Você pode copiar ou carregar o arquivo para um local seguro.</span><span class="sxs-lookup"><span data-stu-id="65ce5-176">You can copy or upload the file to a secure location.</span></span> <span data-ttu-id="65ce5-177">Assim, o arquivo pode ser importado para um ambiente diferente posteriormente.</span><span class="sxs-lookup"><span data-stu-id="65ce5-177">In this way, the file can be imported into a different environment later.</span></span> <span data-ttu-id="65ce5-178">Para obter informações sobre como usar uma conta de armazenamento do Microsoft Azure, consulte [Transferir dados com o utilitário de linha de comando AzCopy](/azure/storage/storage-use-azcopy).</span><span class="sxs-lookup"><span data-stu-id="65ce5-178">For information about how to use a Microsoft Azure storage account, see [Transfer data with the AzCopy Command-Line Utility](/azure/storage/storage-use-azcopy).</span></span>

> [!NOTE]
> <span data-ttu-id="65ce5-179">A Microsoft não fornece uma conta de armazenamento como parte do seu contrato do Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="65ce5-179">Microsoft doesn't provide a storage account as part of your Finance and Operations agreement.</span></span> <span data-ttu-id="65ce5-180">Você deve comprar uma conta de armazenamento ou usar uma conta de armazenamento de uma subscrição separada do Azure.</span><span class="sxs-lookup"><span data-stu-id="65ce5-180">You must either purchase a storage account or use a storage account from a separate Azure subscription.</span></span>

> [!WARNING]
> <span data-ttu-id="65ce5-181">Esteja ciente do comportamento da unidade D nas máquinas virtuais (VMs) do Azure.</span><span class="sxs-lookup"><span data-stu-id="65ce5-181">Be aware of the behavior of drive D on Azure virtual machines (VMs).</span></span> <span data-ttu-id="65ce5-182">Não armazene permanentemente seus grupos de bloco de construção exportados na unidade D. Para obter mais informações sobre unidades temporárias, consulte [Noções básicas sobre a unidade temporária nas Máquinas Virtuais do Windows Azure](https://blogs.msdn.microsoft.com/mast/2013/12/06/understanding-the-temporary-drive-on-windows-azure-virtual-machines/).</span><span class="sxs-lookup"><span data-stu-id="65ce5-182">Don't permanently store your exported building block groups on drive D. For more information about temporary drives, see [Understanding the temporary drive on Windows Azure Virtual Machines](https://blogs.msdn.microsoft.com/mast/2013/12/06/understanding-the-temporary-drive-on-windows-azure-virtual-machines/).</span></span>

### <a name="stop-services"></a><span data-ttu-id="65ce5-183">Interromper serviços</span><span class="sxs-lookup"><span data-stu-id="65ce5-183">Stop services</span></span>

<span data-ttu-id="65ce5-184">Os seguintes serviços do Microsoft Windows terão conexões abertas com o banco de dados do Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="65ce5-184">The following Microsoft Windows services will have open connections to the Finance and Operations database.</span></span> <span data-ttu-id="65ce5-185">Portanto, você deve usar a Área de trabalho remota a Microsoft para conectar todos os computadores no ambiente e usar o services.msc para interromper esses serviços.</span><span class="sxs-lookup"><span data-stu-id="65ce5-185">Therefore, you must use Microsoft Remote Desktop to connect to all the computers in the environment and then use services.msc to stop these services.</span></span>

- <span data-ttu-id="65ce5-186">Serviço de publicação na Web (em todos os computadores dos Servidores de Objetos de Aplicativo [AOS])</span><span class="sxs-lookup"><span data-stu-id="65ce5-186">World wide web publishing service (on all Application Object Servers [AOS] computers)</span></span>
- <span data-ttu-id="65ce5-187">Gerenciamento de Lotes do Microsoft Dynamics 365 for Finance and Operations (somente em computadores AOS não particulares)</span><span class="sxs-lookup"><span data-stu-id="65ce5-187">Microsoft Dynamics 365 for Finance and Operations Batch Management Service (on non-private AOS computers only)</span></span>
- <span data-ttu-id="65ce5-188">Serviço de Processo do Management Reporter 2012 (somente nos computadores do Business intelligence [BI])</span><span class="sxs-lookup"><span data-stu-id="65ce5-188">Management Reporter 2012 Process Service (on Business intelligence [BI] computers only)</span></span>

### <a name="reset"></a><span data-ttu-id="65ce5-189">Redefinir</span><span class="sxs-lookup"><span data-stu-id="65ce5-189">Reset</span></span>

#### <a name="download-the-latest-minorversiondataupgradezip-package"></a><span data-ttu-id="65ce5-190">Baixar o pacote MinorVersionDataUpgrade.zip mais recente</span><span class="sxs-lookup"><span data-stu-id="65ce5-190">Download the latest MinorVersionDataUpgrade.zip package</span></span>

<span data-ttu-id="65ce5-191">Baixar o pacote MinorVersionDataUpgrade.zip mais recente.</span><span class="sxs-lookup"><span data-stu-id="65ce5-191">Download the latest MinorVersionDataUpgrade.zip package.</span></span> <span data-ttu-id="65ce5-192">Para obter instruções sobre como encontrar e baixar a versão correta do pacote de atualização de dados, consulte[Baixar o pacote implantável de atualização de dados mais recente](..\migration-upgrade\upgrade-data-to-latest-update.md#download-the-latest-data-upgrade-deployable-packages).</span><span class="sxs-lookup"><span data-stu-id="65ce5-192">For instructions about how to find and download the correct version of the data upgrade package, see the[Download the latest data upgrade deployable package](..\migration-upgrade\upgrade-data-to-latest-update.md#download-the-latest-data-upgrade-deployable-packages).</span></span> <span data-ttu-id="65ce5-193">Uma atualização não é necessária para baixar o pacote MinorVersionDataUpgrade.zip.</span><span class="sxs-lookup"><span data-stu-id="65ce5-193">An upgrade isn't required in order to download the MinorVersionDataUpgrade.zip package.</span></span> <span data-ttu-id="65ce5-194">Portanto, você apenas tem que seguir as etapas na seção "Baixar o pacote implantável de atualização de dados mais recente" desse tópico.</span><span class="sxs-lookup"><span data-stu-id="65ce5-194">Therefore, you just have follow the steps in the "Download the latest data upgrade deployable package" section of that topic.</span></span> <span data-ttu-id="65ce5-195">Você pode ignorar todas as outras etapas do tópico.</span><span class="sxs-lookup"><span data-stu-id="65ce5-195">You can skip all the other steps in the topic.</span></span>

#### <a name="run-scripts-against-the-finance-and-operations-database"></a><span data-ttu-id="65ce5-196">Executar scripts no banco de dados do Finance and Operations</span><span class="sxs-lookup"><span data-stu-id="65ce5-196">Run scripts against the Finance and Operations database</span></span>

<span data-ttu-id="65ce5-197">Execute os seguintes scripts no banco de dados do Finance and Operations (não no banco de dados de relatórios financeiros):</span><span class="sxs-lookup"><span data-stu-id="65ce5-197">Run the following scripts against the Finance and Operations database (not against the Financial reporting database):</span></span>

- <span data-ttu-id="65ce5-198">DataUpgrade.zip\\AosService\\Scripts\\ConfigureAxReportingIntegration.sql</span><span class="sxs-lookup"><span data-stu-id="65ce5-198">DataUpgrade.zip\\AosService\\Scripts\\ConfigureAxReportingIntegration.sql</span></span>
- <span data-ttu-id="65ce5-199">DataUpgrade.zip\\AosService\\Scripts\\GrantAzViewChangeTracking.sql</span><span class="sxs-lookup"><span data-stu-id="65ce5-199">DataUpgrade.zip\\AosService\\Scripts\\GrantAzViewChangeTracking.sql</span></span>

<span data-ttu-id="65ce5-200">Esses scripts ajudam a garantir que os usuários, as funções e as configurações de controle de alterações estejam corretas.</span><span class="sxs-lookup"><span data-stu-id="65ce5-200">These scripts help guarantee that the users, roles, and change tracking settings are correct.</span></span>

#### <a name="run-a-windows-powershell-command-to-reset-the-database"></a><span data-ttu-id="65ce5-201">Execute um comando do Windows PowerShell para redefinir o banco de dados</span><span class="sxs-lookup"><span data-stu-id="65ce5-201">Run a Windows PowerShell command to reset the database</span></span>

<span data-ttu-id="65ce5-202">No computador AOS, inicie o Microsoft Windows PowerShell como Administrador e execute os seguintes comandos para redefinir a integração entre o Finance and Operations e os relatórios financeiros:</span><span class="sxs-lookup"><span data-stu-id="65ce5-202">On the AOS computer, start Microsoft Windows PowerShell as an administrator, and run the following commands to reset the integration between Finance and Operations and Financial reporting.</span></span>

```
F:
cd F:\MRApplicationService\MRInstallDirectory
Import-Module .\Server\MRDeploy\MRDeploy.psd1
Reset-DatamartIntegration -Reason OTHER -ReasonDetail "<reason for resetting>"
```

<span data-ttu-id="65ce5-203">Aqui está uma explicação dos parâmetros no comando **Redefinir-DatamartIntegration**:</span><span class="sxs-lookup"><span data-stu-id="65ce5-203">Here is an explanation of the parameters in the **Reset-DatamartIntegration** command:</span></span>

- <span data-ttu-id="65ce5-204">Os valores válidos para **-Motivo** são **SERVICING**, **BADDATA** e **OTHER**.</span><span class="sxs-lookup"><span data-stu-id="65ce5-204">The valid values for **-Reason** are **SERVICING**, **BADDATA**, and **OTHER**.</span></span>
- <span data-ttu-id="65ce5-205">O parâmetro **-ReasonDetail** é texto livre.</span><span class="sxs-lookup"><span data-stu-id="65ce5-205">The **-ReasonDetail** parameter is free text.</span></span>
- <span data-ttu-id="65ce5-206">O motivo e o detalhe do motivo será registrado no monitoramento de telemetria/ambiente.</span><span class="sxs-lookup"><span data-stu-id="65ce5-206">The reason and reason detail will be recorded in telemetry/environment monitoring.</span></span>

> [!NOTE]
> <span data-ttu-id="65ce5-207">Após executar os comandos, será solicitado que você digite **Y** para confirmar se deseja redefinir o banco de dados.</span><span class="sxs-lookup"><span data-stu-id="65ce5-207">After you run the commands, you will be asked to enter **Y** to confirm that you want to reset the database.</span></span>

#### <a name="restart-services"></a><span data-ttu-id="65ce5-208">Reiniciar serviços</span><span class="sxs-lookup"><span data-stu-id="65ce5-208">Restart services</span></span>

<span data-ttu-id="65ce5-209">Use o services.msc para reiniciar os serviços que você interrompeu anteriormente:</span><span class="sxs-lookup"><span data-stu-id="65ce5-209">Use services.msc to restart the services that you stopped earlier:</span></span>

- <span data-ttu-id="65ce5-210">Serviço de publicação na Web (em todos os computadores AOS)</span><span class="sxs-lookup"><span data-stu-id="65ce5-210">World wide web publishing service (on all AOS computers)</span></span>
- <span data-ttu-id="65ce5-211">Gerenciamento de Lotes do Microsoft Dynamics 365 for Finance and Operations (somente em computadores AOS não particulares)</span><span class="sxs-lookup"><span data-stu-id="65ce5-211">Microsoft Dynamics 365 for Finance and Operations Batch Management Service (on non-private AOS computers only)</span></span>
- <span data-ttu-id="65ce5-212">Serviço de Processamento do Management Reporter 2012 (somente computadores BI)</span><span class="sxs-lookup"><span data-stu-id="65ce5-212">Management Reporter 2012 Process Service (on BI computers only)</span></span>

#### <a name="import-report-definitions"></a><span data-ttu-id="65ce5-213">Importar definições de relatório</span><span class="sxs-lookup"><span data-stu-id="65ce5-213">Import report definitions</span></span>

<span data-ttu-id="65ce5-214">Importe seus designs de relatório do Report Designer, usando o arquivo criado durante a exportação.</span><span class="sxs-lookup"><span data-stu-id="65ce5-214">Import your report designs from Report designer by using the file that was created during the export.</span></span>

1. <span data-ttu-id="65ce5-215">No Designer de relatórios, selecione **Empresa** &gt; **Grupos de Blocos de Construção**.</span><span class="sxs-lookup"><span data-stu-id="65ce5-215">In Report designer, select **Company** &gt; **Building Block Groups**.</span></span>
2. <span data-ttu-id="65ce5-216">Selecione o grupo do bloco de construção para exportar, depois selecione **Exportar**.</span><span class="sxs-lookup"><span data-stu-id="65ce5-216">Select the building block group to export, and then select **Export**.</span></span>

    > [!NOTE]
    > <span data-ttu-id="65ce5-217">Para o Finanças e Operações, apenas um grupo de blocos de construção é suportado, **Padrão**.</span><span class="sxs-lookup"><span data-stu-id="65ce5-217">For Finance and Operations, only one building block group is supported, **Default**.</span></span>

3. <span data-ttu-id="65ce5-218">Selecione o bloco de construção **Padrão** e selecione **Importar**.</span><span class="sxs-lookup"><span data-stu-id="65ce5-218">Select the **Default** building block, and then select **Import**.</span></span>
4. <span data-ttu-id="65ce5-219">Selecione o arquivo que contém as definições de relatório exportadas e selecione **Abrir**.</span><span class="sxs-lookup"><span data-stu-id="65ce5-219">Select the file that contains the exported report definitions, and then select **Open**.</span></span>
5. <span data-ttu-id="65ce5-220">Na caixa de diálogo **Importar**, selecione as definições de relatório para importar:</span><span class="sxs-lookup"><span data-stu-id="65ce5-220">In the **Import** dialog box, select the report definitions to import:</span></span>

    - <span data-ttu-id="65ce5-221">Para importar todas as definições de relatório e os blocos de construção associados, clique em **Selecionar Tudo**.</span><span class="sxs-lookup"><span data-stu-id="65ce5-221">To import all the report definitions and the associated building blocks, select **Select All**.</span></span>
    - <span data-ttu-id="65ce5-222">Para importar relatórios, linhas, colunas, hierarquias ou conjuntos de dimensões específicos, selecione os relatórios, as linhas, as colunas, as hierarquias ou os conjuntos de dimensões a serem importados.</span><span class="sxs-lookup"><span data-stu-id="65ce5-222">To import specific reports, rows, columns, trees, or dimension sets, select the reports, rows, columns, trees, or dimension sets to import.</span></span>

6. <span data-ttu-id="65ce5-223">Selecione **Importar**.</span><span class="sxs-lookup"><span data-stu-id="65ce5-223">Select **Import**.</span></span>

## <a name="reset-the-financial-reporting-data-mart-for-finance-and-operations-on-premises"></a><span data-ttu-id="65ce5-224">Redefina o data mart de relatórios financeiros para Finance and Operations (local)</span><span class="sxs-lookup"><span data-stu-id="65ce5-224">Reset the Financial reporting data mart for Finance and Operations (on-premises)</span></span>

1. <span data-ttu-id="65ce5-225">Instrua todos os usuários para sair do designer de relatórios e da área de relatórios financeiros do Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="65ce5-225">Instruct all users to exit Report designer and the Financial reporting area of Finance and Operations.</span></span>
2. <span data-ttu-id="65ce5-226">Execute o seguinte script no base de dados de relatórios financeiros (MRDB).</span><span class="sxs-lookup"><span data-stu-id="65ce5-226">Run the following script against the Financial reporting database (MRDB).</span></span>

    ```
    DECLARE @triggerIds table(id uniqueidentifier, taskTypeId uniqueidentifier)
    INSERT INTO @triggerIds SELECT tr.[Id], tt.[Id]
    FROM [Scheduling].[Task] t with(nolock)
    JOIN [Scheduling].[Trigger] tr ON t.[TriggerId] = tr.[Id]
    JOIN [Scheduling].[TaskState] ts ON ts.[TaskId] = t.[Id]
    LEFT JOIN [Scheduling].[TaskCategory] tc ON tc.[Id] = t.[CategoryId]
    JOIN [Scheduling].[TaskType] tt ON t.[TypeId] = tt.[Id]
    WHERE tt.[Id] IN ('D81C1197-D486-4FB7-AF8C-078C110893A0', '55D3F71A-2618-4EAE-9AA6-D48767B974D8') -- 'Maintenance Task', 'Map Task'
    PRINT 'Disable integration tasks'
    UPDATE [Scheduling].[Trigger] SET IsEnabled = 0 WHERE [Id] in (SELECT id FROM @triggerIds)
    ```

3. <span data-ttu-id="65ce5-227">Truncar ou excluir todos os registros da tabela FINANCIALREPORTS no banco de dados do Finance and Operations (AXDB).</span><span class="sxs-lookup"><span data-stu-id="65ce5-227">Truncate or delete all records from the FINANCIALREPORTS table in the Finance and Operations database (AXDB).</span></span>
4. <span data-ttu-id="65ce5-228">Truncar ou excluir todos os registros da tabela FINANCIALREPORTVERSION, se esta tabela existir no banco de dados do Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="65ce5-228">Truncate or delete all records from the FINANCIALREPORTVERSION table, if this table exists in the Finance and Operations database.</span></span> <span data-ttu-id="65ce5-229">Se a tabela não existir no base de dados do Finance and Operations, ignore esta etapa.</span><span class="sxs-lookup"><span data-stu-id="65ce5-229">If the table doesn't exist in the Finance and Operations database, skip this step.</span></span>
5. <span data-ttu-id="65ce5-230">Execute o script **ResetDatamart.sql** com o banco de dados do relatório financeiro.</span><span class="sxs-lookup"><span data-stu-id="65ce5-230">Run the **ResetDatamart.sql** script against the Financial reporting database.</span></span> <span data-ttu-id="65ce5-231">Este script desabilita a integração de data mart, exclui todos os dados de data mart e habilita novamente a integração de data mart.</span><span class="sxs-lookup"><span data-stu-id="65ce5-231">This script disables the data mart integration, deletes all the data mart data, and then reenables the data mart integration.</span></span>

    ```
    DECLARE @triggerIds table(id uniqueidentifier, taskTypeId uniqueidentifier)
    INSERT INTO @triggerIds SELECT tr.[Id], tt.[Id]
    FROM [Scheduling].[Task] t with(nolock)
    JOIN [Scheduling].[Trigger] tr ON t.[TriggerId] = tr.[Id]
    JOIN [Scheduling].[TaskState] ts ON ts.[TaskId] = t.[Id]
    LEFT JOIN [Scheduling].[TaskCategory] tc ON tc.[Id] = t.[CategoryId]
    JOIN [Scheduling].[TaskType] tt ON t.[TypeId] = tt.[Id]
    WHERE tt.[Id] IN ('D81C1197-D486-4FB7-AF8C-078C110893A0', '55D3F71A-2618-4EAE-9AA6-D48767B974D8') -- 'Maintenance Task', 'Map Task'
    PRINT 'Disable integration tasks'
    UPDATE [Scheduling].[Trigger] SET IsEnabled = 0 WHERE [Id] in (SELECT id FROM @triggerIds)
    ------------------------------
    PRINT 'Drop archive tables'
    ------------------------------
    DECLARE @tableId nvarchar(max)
    DECLARE dropCursor CURSOR LOCAL FAST_FORWARD FOR
    SELECT Id FROM [Datamart].Archive
    OPEN dropCursor
    FETCH NEXT FROM dropCursor INTO @tableId
    WHILE @@FETCH_STATUS = 0
    BEGIN
        IF EXISTS (SELECT 1 FROM INFORMATION_SCHEMA.TABLES t WHERE t.TABLE_NAME = 'FactStaging' + @tableId and t.TABLE_SCHEMA = 'Datamart')
        EXEC('DROP TABLE [Datamart].FactStaging' + @tableId)
        IF EXISTS (SELECT 1 FROM INFORMATION_SCHEMA.TABLES t WHERE t.TABLE_NAME = 'DimensionCombinationStaging' + @tableId and t.TABLE_SCHEMA = 'Datamart')
        EXEC('DROP TABLE [Datamart].DimensionCombinationStaging' + @tableId)
        FETCH NEXT FROM dropCursor INTO @tableId
    END
    CLOSE dropCursor
    DEALLOCATE dropCursor
    IF EXISTS (SELECT 1 FROM INFORMATION_SCHEMA.TABLES t WHERE t.TABLE_NAME = 'DimensionCombinationProcessing' and t.TABLE_SCHEMA = 'Datamart')
        EXEC('DROP TABLE [Datamart].DimensionCombinationProcessing')
    ------------------------------
    PRINT 'Begin Truncating tables'
    ------------------------------
    DECLARE @tablename nvarchar(200)
    DECLARE @schemaname nvarchar(200)
    DECLARE clear_tables CURSOR
        FOR SELECT TABLE_NAME, TABLE_SCHEMA FROM INFORMATION_SCHEMA.TABLES WHERE TABLE_SCHEMA = 'Datamart' AND TABLE_TYPE='BASE TABLE'
    PRINT 'remove check constraints'
    OPEN clear_tables
    FETCH NEXT FROM clear_tables INTO @tablename, @schemaname
    WHILE @@FETCH_STATUS = 0
    BEGIN
        IF @tablename <> 'VersionHistory'
        BEGIN
        EXEC('ALTER TABLE [' + @schemaname + '].[' + @tablename + '] NOCHECK CONSTRAINT ALL')
        END
        FETCH NEXT FROM clear_tables INTO @tablename, @schemaname
    END
    CLOSE clear_tables
    ------------------------------
    PRINT 'delete data from tables and rebuild indexes'
    ------------------------------
    OPEN clear_tables
    FETCH NEXT FROM clear_tables INTO @tablename, @schemaname
    WHILE @@FETCH_STATUS = 0
    BEGIN
        IF @tablename <> 'VersionHistory'
        BEGIN
            IF(EXISTS (select TOP 1 1 from sys.foreign_keys where referenced_object_id = OBJECT_ID(@schemaname + '.' + @tablename)) OR
            EXISTS(SELECT TOP 1 1 FROM sys.sql_expression_dependencies sed
            INNER JOIN sys.objects o ON sed.referencing_id = o.[object_id]
            WHERE o.[type] = 'V' 
            AND referenced_schema_name = @schemaname
            AND referenced_entity_name = @tablename))
            BEGIN
            PRINT 'deleting from ' + @tablename
            EXEC('DELETE FROM [' + @schemaname + '].[' + @tablename + ']')
            END
            ELSE
            BEGIN
            PRINT 'truncating from ' + @tablename
            EXEC('TRUNCATE TABLE [' + @schemaname + '].[' + @tablename + ']')
            END
        END
        EXEC('ALTER INDEX ALL ON [' + @schemaname + '].[' + @tablename + '] REBUILD')
        FETCH NEXT FROM clear_tables INTO @tablename, @schemaname
    END
    CLOSE clear_tables
    ------------------------------
    PRINT 'reenable check constraints'
    ------------------------------
    OPEN clear_tables
    FETCH NEXT FROM clear_tables INTO @tablename, @schemaname
    WHILE @@FETCH_STATUS = 0
    BEGIN
        IF @tablename <> 'VersionHistory'
        BEGIN
        EXEC('ALTER TABLE [' + @schemaname + '].[' + @tablename +'] WITH CHECK CHECK CONSTRAINT ALL')
        END
        FETCH NEXT FROM clear_tables INTO @tablename, @schemaname
    END
    CLOSE clear_tables
    DEALLOCATE clear_tables
    ------------------------------
    PRINT 'Complete Truncating tables'
    ------------------------------
    ------------------------------
    PRINT 'Remove indexes from DimensionCombination'
    ------------------------------
    DECLARE @indexname nvarchar(200)
    DECLARE drop_indexes CURSOR
    FOR SELECT Name FROM sys.indexes WHERE object_id = OBJECT_ID('[Datamart].[DimensionCombination]') AND is_primary_key = 0
    OPEN drop_indexes
    FETCH NEXT FROM drop_indexes INTO @indexname
    WHILE @@FETCH_STATUS = 0
    BEGIN
        EXEC('DROP INDEX [' + @indexname + '] on [Datamart].[DimensionCombination]')
        FETCH NEXT FROM drop_indexes INTO @indexname
    END
    CLOSE drop_indexes
    DEALLOCATE drop_indexes
    ------------------------------
    PRINT 'Drop Columns on DimensionCombination'
    ------------------------------
    DECLARE @objectname nvarchar(200)
    DECLARE drop_objects CURSOR
    FOR SELECT Name FROM sys.columns WHERE object_id = OBJECT_ID('[Datamart].[DimensionCombination]')
    OPEN drop_objects
    FETCH NEXT FROM drop_objects INTO @objectname
    WHILE @@FETCH_STATUS = 0
    BEGIN
        IF @objectname NOT IN ('Id', 'Description', 'SourceKey', 'OrganizationId', 'InactiveDimensions')
        BEGIN
        EXEC('ALTER TABLE [Datamart].[DimensionCombination] DROP COLUMN ' + @objectname)
        END
        FETCH NEXT FROM drop_objects INTO @objectname
    END
    CLOSE drop_objects
    DEALLOCATE drop_objects
    ------------------------------
    PRINT 'Drop Columns on DimensionCombinationResolving'
    ------------------------------
    DECLARE drop_objects CURSOR
    FOR SELECT Name FROM sys.columns WHERE object_id = OBJECT_ID('[Datamart].[DimensionCombinationResolving]')
    OPEN drop_objects
    FETCH NEXT FROM drop_objects INTO @objectname
    WHILE @@FETCH_STATUS = 0
    BEGIN
        IF @objectname NOT IN ('Id', 'Description', 'SourceKey', 'OrganizationId')
        BEGIN
        EXEC('ALTER TABLE [Datamart].[DimensionCombinationResolving] DROP COLUMN ' + @objectname)
        END
        FETCH NEXT FROM drop_objects INTO @objectname
    END
    CLOSE drop_objects
    DEALLOCATE drop_objects
    ------------------------------
    PRINT 'Drop Columns on DimensionCombinationStaging'
    ------------------------------
    DECLARE drop_objects CURSOR
    FOR SELECT Name FROM sys.columns WHERE object_id = OBJECT_ID('[Datamart].[DimensionCombinationStaging]')
    OPEN drop_objects
    FETCH NEXT FROM drop_objects INTO @objectname
    WHILE @@FETCH_STATUS = 0
    BEGIN
        IF @objectname NOT IN ('Id', 'OrganizationId', 'Description', 'SourceKey', 'OrganizationKey', 'FreshnessDate')
        BEGIN
        EXEC('ALTER TABLE [Datamart].[DimensionCombinationStaging] DROP COLUMN ' + @objectname)
        END
        FETCH NEXT FROM drop_objects INTO @objectname
    END
    CLOSE drop_objects
    DEALLOCATE drop_objects
    ------------------------------
    PRINT 'Drop Columns on DimensionCombinationUnreferenced'
    ------------------------------
    DECLARE drop_objects CURSOR
    FOR SELECT Name FROM sys.columns WHERE object_id = OBJECT_ID('[Datamart].[DimensionCombinationUnreferenced]')
    OPEN drop_objects
    FETCH NEXT FROM drop_objects INTO @objectname
    WHILE @@FETCH_STATUS = 0
    BEGIN
        IF @objectname NOT IN ('Id', 'Description', 'SourceKey', 'OrganizationId')
        BEGIN
        EXEC('ALTER TABLE [Datamart].[DimensionCombinationUnreferenced] DROP COLUMN ' + @objectname)
        END
        FETCH NEXT FROM drop_objects INTO @objectname
    END
    CLOSE drop_objects
    DEALLOCATE drop_objects
    ------------------------------
    PRINT 'Drop Columns on DimensionValueAttributeValue'
    ------------------------------
    DECLARE drop_objects CURSOR
    FOR SELECT Name FROM sys.columns WHERE object_id = OBJECT_ID('[Datamart].[DimensionValueAttributeValue]')
    OPEN drop_objects
    FETCH NEXT FROM drop_objects INTO @objectname
    WHILE @@FETCH_STATUS = 0
    BEGIN
        IF @objectname NOT IN ('DimensionValueId')
        BEGIN
        EXEC('ALTER TABLE [Datamart].[DimensionValueAttributeValue] DROP COLUMN ' + @objectname)
        END
        FETCH NEXT FROM drop_objects INTO @objectname
    END
    CLOSE drop_objects
    DEALLOCATE drop_objects
    ------------------------------
    PRINT 'Drop Columns on FactAttributeValue'
    ------------------------------
    DECLARE drop_objects CURSOR
    FOR SELECT Name FROM sys.columns WHERE object_id = OBJECT_ID('[Datamart].[FactAttributeValue]')
    OPEN drop_objects
    FETCH NEXT FROM drop_objects INTO @objectname
    WHILE @@FETCH_STATUS = 0
    BEGIN
        IF @objectname NOT IN ('FactId')
        BEGIN
        EXEC('ALTER TABLE [Datamart].[FactAttributeValue] DROP COLUMN ' + @objectname)
        END
        FETCH NEXT FROM drop_objects INTO @objectname
    END
    CLOSE drop_objects
    DEALLOCATE drop_objects
    ------------------------------
    PRINT 'Remove constraints from TranslatedPeriodBalance'
    ------------------------------
    DECLARE @name nvarchar(200)
    DECLARE drop_constraints CURSOR
    FOR SELECT Name FROM sys.default_constraints WHERE parent_object_id = OBJECT_ID('[Datamart].[TranslatedPeriodBalance]')
    OPEN drop_constraints
    FETCH NEXT FROM drop_constraints INTO @name
    WHILE @@FETCH_STATUS = 0
    BEGIN
        EXEC('ALTER TABLE [Datamart].[TranslatedPeriodBalance] DROP CONSTRAINT [' + @name + ']')
        FETCH NEXT FROM drop_constraints INTO @name
    END
    CLOSE drop_constraints
    DEALLOCATE drop_constraints
    ------------------------------
    PRINT 'Drop Columns on TranslatedPeriodBalance'
    ------------------------------
    DECLARE drop_objects CURSOR
    FOR SELECT Name FROM sys.columns WHERE object_id = OBJECT_ID('[Datamart].[TranslatedPeriodBalance]')
    OPEN drop_objects
    FETCH NEXT FROM drop_objects INTO @objectname
    WHILE @@FETCH_STATUS = 0
    BEGIN
        IF @objectname NOT IN ('PeriodId', 'DimensionsId', 'ScenarioId', 'FactType', 'PostingLayerId')
        BEGIN
        EXEC('ALTER TABLE [Datamart].[TranslatedPeriodBalance] DROP COLUMN ' + @objectname)
        END
        FETCH NEXT FROM drop_objects INTO @objectname
    END
    CLOSE drop_objects
    DEALLOCATE drop_objects
    ------------------------------
    PRINT 'Remove constraints from TranslatedPeriodBalanceChanges'
    ------------------------------
    DECLARE drop_constraints CURSOR
    FOR SELECT Name FROM sys.default_constraints WHERE parent_object_id = OBJECT_ID('[Datamart].[TranslatedPeriodBalanceChanges]')
    OPEN drop_constraints
    FETCH NEXT FROM drop_constraints INTO @name
    WHILE @@FETCH_STATUS = 0
    BEGIN
        EXEC('ALTER TABLE [Datamart].[TranslatedPeriodBalanceChanges] DROP CONSTRAINT [' + @name + ']')
        FETCH NEXT FROM drop_constraints INTO @name
    END
    CLOSE drop_constraints
    DEALLOCATE drop_constraints
    ------------------------------
    PRINT 'Drop Columns on TranslatedPeriodBalanceChanges'
    ------------------------------
    DECLARE drop_objects CURSOR
    FOR SELECT Name FROM sys.columns WHERE object_id = OBJECT_ID('[Datamart].[TranslatedPeriodBalanceChanges]')
    OPEN drop_objects
    FETCH NEXT FROM drop_objects INTO @objectname
    WHILE @@FETCH_STATUS = 0
    BEGIN
        IF @objectname NOT IN ('PeriodId', 'DimensionsId', 'ScenarioId', 'FactType', 'PostingLayerId')
        BEGIN
        EXEC('ALTER TABLE [Datamart].[TranslatedPeriodBalanceChanges] DROP COLUMN ' + @objectname)
        END
        FETCH NEXT FROM drop_objects INTO @objectname
    END
    CLOSE drop_objects
    DEALLOCATE drop_objects
    -- Rebuild dropped indexes that are dynamic
    EXEC [Datamart].ConfigureIndexesAndConstraints
    ------------------------------------------
    ------------------------------------------
    PRINT 'Reset the map tokens'
    UPDATE [Connector].[Map] SET InitalLoad = 0, ReaderToken=NULL, LastQuerySuccess='1900-01-01' WHERE MapId IN (SELECT t.[Id]
    FROM [Scheduling].[Task] t with(nolock)
    JOIN [Scheduling].[Trigger] tr ON t.[TriggerId] = tr.[Id]
    JOIN [Scheduling].[TaskState] ts ON ts.[TaskId] = t.[Id]
    LEFT JOIN [Scheduling].[TaskCategory] tc ON tc.[Id] = t.[CategoryId]
    JOIN [Scheduling].[TaskType] tt ON t.[TypeId] = tt.[Id]
    WHERE tt.[Id] = '55D3F71A-2618-4EAE-9AA6-D48767B974D8')
    PRINT 'Reset the tasks'
    UPDATE [Scheduling].[TaskState] SET StateType = 0, Progress = 0.0, LastRunTime = NULL, NextRunTime = NULL WHERE TaskId IN (SELECT ts.[TaskId]
    FROM [Scheduling].[Task] t with(nolock)
    JOIN [Scheduling].[Trigger] tr ON t.[TriggerId] = tr.[Id]
    JOIN [Scheduling].[TaskState] ts ON ts.[TaskId] = t.[Id]
    LEFT JOIN [Scheduling].[TaskCategory] tc ON tc.[Id] = t.[CategoryId]
    JOIN [Scheduling].[TaskType] tt ON t.[TypeId] = tt.[Id]
    WHERE tt.[Id] IN ('D81C1197-D486-4FB7-AF8C-078C110893A0', '55D3F71A-2618-4EAE-9AA6-D48767B974D8'))
    PRINT 'Enable integration tasks, RunImmediately'
    UPDATE [Scheduling].[Trigger] SET IsEnabled = 1, RunImmediately = 1, StartBoundary = '1900-01-01' 
    WHERE Id in (SELECT [id] from @triggerIds WHERE taskTypeId = '55D3F71A-2618-4EAE-9AA6-D48767B974D8')
    PRINT 'Enable the Maintenance Task'
    UPDATE [Scheduling].[Trigger] SET IsEnabled = 1, RunImmediately = 0, StartBoundary = GETDATE() WHERE Id in
    (SELECT [id] from @triggerIds WHERE taskTypeId = 'D81C1197-D486-4FB7-AF8C-078C110893A0')
    ------------------------------------------
    ------------------------------------------
    ```

6. <span data-ttu-id="65ce5-232">Após a redefinição, você pode verificar a recarga de dados manualmente, executando as seguintes consultas no base de dados de relatórios financeiros.</span><span class="sxs-lookup"><span data-stu-id="65ce5-232">After the reset, you can manually verify the data reload by running the following query against the Financial reporting database.</span></span>

    ```
    select ReaderObjectName, WriterObjectName, LastRunTime, StateType from Connector.MapsWithDetail with (nolock)
    ```

    <span data-ttu-id="65ce5-233">Confirme se todas as linhas têm o valor **LastRunTime** e se **StateType** está definido como **5**.</span><span class="sxs-lookup"><span data-stu-id="65ce5-233">Confirm that all rows have a **LastRunTime** value, and that **StateType** is set to **5**.</span></span> <span data-ttu-id="65ce5-234">Um valor **StateType** de **5** indica que os dados foram recarregados com êxito.</span><span class="sxs-lookup"><span data-stu-id="65ce5-234">A **StateType** value of **5** indicates that the data was successfully reloaded.</span></span> <span data-ttu-id="65ce5-235">Um valor de **7** indica o estado com falha.</span><span class="sxs-lookup"><span data-stu-id="65ce5-235">A value of **7** indicates a faulted state.</span></span> <span data-ttu-id="65ce5-236">Ocasionalmente, o mapa de hierarquia organizacional tem este estado na primeira vez que é executado.</span><span class="sxs-lookup"><span data-stu-id="65ce5-236">Sometimes, the Organization Hierarchy map has this state the first time that it runs.</span></span> <span data-ttu-id="65ce5-237">Entretanto, o estado com falha deve ser resolvido automaticamente.</span><span class="sxs-lookup"><span data-stu-id="65ce5-237">However, the faulted state but should be automatically resolved.</span></span>

