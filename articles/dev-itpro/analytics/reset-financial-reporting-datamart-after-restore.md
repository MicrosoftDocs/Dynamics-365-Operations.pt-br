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

# <a name="reset-the-financial-reporting-data-mart"></a>Redefinir o data mart de relatórios Financeiros

[!include[banner](../includes/banner.md)]

Este tópico explica como redefinir data mart de relatórios financeiros para as seguintes versões:

- Microsoft Dynamics 365 for Finance and Operations: versão 7.2.6.0 e posterior de relatórios financeiros
- Microsoft Dynamics 365 for Finance and Operations: versão 7.0.10000.4 e posterior de relatórios financeiros
- Microsoft Dynamics 365 for Finance and Operations, Enterprise edition (local)

Para obter a versão 7.2.6.0 de relatórios financeiros do Finance and Operations, você pode fazer download do KB 4052514 de <https://support.microsoft.com/en-us/help/4052514>.

## <a name="reset-the-financial-reporting-data-mart-for-finance-and-operations-financial-reporting-release-7260-and-later"></a>Redefinir o data mart de relatórios financeiros da versão 7.2.6.0 e posterior de relatórios financeiros do Finance and Operations

### <a name="reset-the-financial-reporting-data-mart-from-report-designer"></a>Redefinir o data mart de relatórios financeiros do designer de relatórios

> [!NOTE]
> As etapas deste processo são suportadas para a versão 7.2.6.0 e posterior de relatórios financeiros do Finance and Operations. Se você tiver uma versão anterior, entre em contato com a equipe de suporte para obter ajuda.

Em cenários específicos, talvez seja necessário redefinir o data mart para relatórios financeiros. Você pode concluir esta tarefa no cliente do designer de relatórios. Veja alguns cenários nos quais pode ser necessário redefinir o data mart:

- O banco de dados do Finance and Operations foi restaurado, mas o banco de dados do data mart não foi.
- Você vê dados incorretos para um período.
- O suporte o instrui para redefinir o data mart como parte de uma etapa de solução de problemas.

A redefinição de data mart deve ser feita somente durante momentos em que o valor de processamento no banco de dados é pequeno. O relatório financeiro ficará indisponível durante o processo de redefinição.

#### <a name="reset-the-data-mart"></a>Redefinir o data mart

Para redefinir o data mart, no designer de Relatório, no menu **Ferramentas**, selecione **Redefinir Data Mart**. A caixa de diálogo que aparece tem duas seções: **Estatística** e **Redefinir**.

[![Caixa de diálogo Redefinir Data Mart](./media/Statistics.png)](./media/Statistics.png)

##### <a name="integration-attempts"></a>Tentativas de integração

A grade **Tentativas de integração** mostra quantas vezes o sistema tentou integrar as transações. O sistema continua tentando integrar os dados durante um período, se as primeiras tentativas falharem. Você saberá se o data mart deve ser redefinido, se o número de tentativas for 8 ou mais, e se houver muitas combinações de Dimensão ou registros da Transação. Nessa situação, os dados não serão reportados.

##### <a name="data-status"></a>Status dos dados

A grade **Status de dados** fornece um instantâneo de transações, taxas de câmbio e valores de dimensão no data mart. Um grande número de registros desatualizados indica que ocorreram várias atualizações nos registros. Essa situação pode causar lentidão na geração do relatório.

##### <a name="misaligned-main-account-categories"></a>Categorias desalinhadas da conta principal

Se estiver usando uma versão que seja anterior à versão 7.2.1 de relatórios financeiros do Microsoft Dynamics 365 for Finance and Operations Financial, pode ser necessário redefinir o data mart, se você renomear as contas e movê-las entre as categorias de conta. Essas ações podem fazer com que as categorias de conta principal fiquem desalinhadas. O campo **Categorias de conta principal desalinhadas** mostra se você está enfrentando esse problema.

### <a name="reset-the-data-mart-in-finance-and-operations-financial-reporting-release-7260"></a>Redefina o data mart na versão 7.2.6.0 de relatórios financeiros do Finance and Operations

Para redefinir o data mart na versão 7.2.6.0 e posterior de relatórios financeiros do Finance and Operations, na caixa de diálogo **Redefinir Data Mart**, marque a caixa de seleção **Redefinir data mart** e selecione **OK**. Você deve redefinir o data mart apenas durante o tempo de inatividade programado.

[![Caixa de diálogo Redefinir data mart](./media/Reset-72.jpg)](./media/Reset-72.jpg)

### <a name="reset-the-data-mart-and-select-a-reason-in-microsoft-dynamics-365-for-finance-and-operations-financial-reporting-release-730"></a>Redefinir o data mart e selecionar um motivo na versão 7.3.0 de relatórios financeiros do Microsoft Dynamics 365 for Finance and Operations

Se você determinar que uma redefinição do data mart é necessária, marque a caixa de seleção **Redefinir data mart** e selecione um motivo no campo **Motivo**. As opções a seguir estão disponíveis:

- **Dados incorretos ou ausentes** baseado nas estatísticas, você determinou que talvez faltem dados. Antes de continuar, recomendamos que trabalhe com o suporte para determinar a causa raiz.
- **Restaurar banco de dados** – O banco de dados do Finance and Operations foi restaurado, mas o banco de dados do data mart não foi.
- **Outro** – Você está redefinindo o data mart por outro motivo. Se você acha que há um problema, entre em contato com o suporte para identificá-lo.

> [!NOTE]
> Verifique se todas as tarefas existentes finalizaram a integração antes de concluir as etapas. Você pode exibir o status da integração selecionando **Ferramentas** &gt; **Status de integração**.

#### <a name="clear-users-and-companies"></a>Limpar usuários e empresas

Marque a caixa de seleção **Limpar usuários e empresas** se você restaurou seu banco de dados, mas depois fez alterações em usuários ou empresas. Raramente você deverá marcar esta caixa de seleção.

Quando estiver pronto para iniciar o processo de redefinição, selecione **OK**. Será solicitado que confirme que está pronto para iniciar o processo. Observe que o relatório financeiro não estará disponível durante a redefinição e a integração de dados inicial que ocorrerá posteriormente.

Se quiser revisar o status de integração, selecione **Ferramentas** &gt; **Status de integração** para ver a última vez que a integração e o status foram executados.

[![Exiba o status da integração](./media/Integration.png)](./media/Integration.png)

## <a name="reset-the-financial-reporting-data-mart-for-finance-and-operations-financial-reporting-release-70100004-and-later"></a>Redefinir o data mart de relatórios financeiros da versão 7.0.10000.4 e posterior de relatórios financeiros do Finance and Operations

Se você já restaurou seu banco de dados do Finance and Operations de um backup ou cópia do banco de dados de outro ambiente, você deve seguir as etapas desta seção para ajudar a garantir que o data mart de relatórios Financeiros usa corretamente o banco de dados do Finance and Operations restaurado.

> [!NOTE]
> As etapas deste processo são suportadas para a versão 7.0.1 do aplicativo do Microsoft Dynamics AX (maio 2016) (compilação 7.0.1265.23014 do aplicativo e compilação 7.0.10000.4 de relatórios financeiros) e posterior. Se você tiver uma versão anterior do Finance and Operations, contate o Suporte para obter ajuda.

### <a name="export-report-definitions"></a>Exportar definições de relatório

Primeiro, siga estas etapas para exporta os designs de relatório do designer de relatório.

1. No Designer de relatórios, selecione **Empresa** &gt; **Grupos de Blocos de Construção**.
2. Selecione o grupo do bloco de construção para exportar, depois selecione **Exportar**.

    > [!NOTE]
    > Para o Finanças e Operações, apenas um grupo de blocos de construção é suportado, **Padrão**.

3. Selecione as definições de relatório a serem exportadas:

    - Para exportar todas as definições de relatório e os blocos de construção associados, clique em **Selecionar Tudo**.
    - Para exportar relatórios, linhas, colunas, árvores ou conjuntos de dimensões específicos, selecione a guia apropriada e selecione os itens a serem exportados. Pressione e mantenha pressionada a tecla Ctrl para selecionar vários itens em uma guia. Quando você selecionar relatórios para exportar, as linhas, as colunas, as hierarquias e os conjuntos de dimensões associados serão selecionados.

4. Selecione **Exportar**.
5. Insira um nome de arquivo e selecione um local seguro onde deseja salvar as definições de relatório exportadas.
6. Selecione **Salvar**.

Você pode copiar ou carregar o arquivo para um local seguro. Assim, o arquivo pode ser importado para um ambiente diferente posteriormente. Para obter informações sobre como usar uma conta de armazenamento do Microsoft Azure, consulte [Transferir dados com o utilitário de linha de comando AzCopy](/azure/storage/storage-use-azcopy).

> [!NOTE]
> A Microsoft não fornece uma conta de armazenamento como parte do seu contrato do Finance and Operations. Você deve comprar uma conta de armazenamento ou usar uma conta de armazenamento de uma subscrição separada do Azure.

> [!WARNING]
> Esteja ciente do comportamento da unidade D nas máquinas virtuais (VMs) do Azure. Não armazene permanentemente seus grupos de bloco de construção exportados na unidade D. Para obter mais informações sobre unidades temporárias, consulte [Noções básicas sobre a unidade temporária nas Máquinas Virtuais do Windows Azure](https://blogs.msdn.microsoft.com/mast/2013/12/06/understanding-the-temporary-drive-on-windows-azure-virtual-machines/).

### <a name="stop-services"></a>Interromper serviços

Os seguintes serviços do Microsoft Windows terão conexões abertas com o banco de dados do Finance and Operations. Portanto, você deve usar a Área de trabalho remota a Microsoft para conectar todos os computadores no ambiente e usar o services.msc para interromper esses serviços.

- Serviço de publicação na Web (em todos os computadores dos Servidores de Objetos de Aplicativo [AOS])
- Gerenciamento de Lotes do Microsoft Dynamics 365 for Finance and Operations (somente em computadores AOS não particulares)
- Serviço de Processo do Management Reporter 2012 (somente nos computadores do Business intelligence [BI])

### <a name="reset"></a>Redefinir

#### <a name="download-the-latest-minorversiondataupgradezip-package"></a>Baixar o pacote MinorVersionDataUpgrade.zip mais recente

Baixar o pacote MinorVersionDataUpgrade.zip mais recente. Para obter instruções sobre como encontrar e baixar a versão correta do pacote de atualização de dados, consulte[Baixar o pacote implantável de atualização de dados mais recente](..\migration-upgrade\upgrade-data-to-latest-update.md#download-the-latest-data-upgrade-deployable-packages). Uma atualização não é necessária para baixar o pacote MinorVersionDataUpgrade.zip. Portanto, você apenas tem que seguir as etapas na seção "Baixar o pacote implantável de atualização de dados mais recente" desse tópico. Você pode ignorar todas as outras etapas do tópico.

#### <a name="run-scripts-against-the-finance-and-operations-database"></a>Executar scripts no banco de dados do Finance and Operations

Execute os seguintes scripts no banco de dados do Finance and Operations (não no banco de dados de relatórios financeiros):

- DataUpgrade.zip\\AosService\\Scripts\\ConfigureAxReportingIntegration.sql
- DataUpgrade.zip\\AosService\\Scripts\\GrantAzViewChangeTracking.sql

Esses scripts ajudam a garantir que os usuários, as funções e as configurações de controle de alterações estejam corretas.

#### <a name="run-a-windows-powershell-command-to-reset-the-database"></a>Execute um comando do Windows PowerShell para redefinir o banco de dados

No computador AOS, inicie o Microsoft Windows PowerShell como Administrador e execute os seguintes comandos para redefinir a integração entre o Finance and Operations e os relatórios financeiros:

```
F:
cd F:\MRApplicationService\MRInstallDirectory
Import-Module .\Server\MRDeploy\MRDeploy.psd1
Reset-DatamartIntegration -Reason OTHER -ReasonDetail "<reason for resetting>"
```

Aqui está uma explicação dos parâmetros no comando **Redefinir-DatamartIntegration**:

- Os valores válidos para **-Motivo** são **SERVICING**, **BADDATA** e **OTHER**.
- O parâmetro **-ReasonDetail** é texto livre.
- O motivo e o detalhe do motivo será registrado no monitoramento de telemetria/ambiente.

> [!NOTE]
> Após executar os comandos, será solicitado que você digite **Y** para confirmar se deseja redefinir o banco de dados.

#### <a name="restart-services"></a>Reiniciar serviços

Use o services.msc para reiniciar os serviços que você interrompeu anteriormente:

- Serviço de publicação na Web (em todos os computadores AOS)
- Gerenciamento de Lotes do Microsoft Dynamics 365 for Finance and Operations (somente em computadores AOS não particulares)
- Serviço de Processamento do Management Reporter 2012 (somente computadores BI)

#### <a name="import-report-definitions"></a>Importar definições de relatório

Importe seus designs de relatório do Report Designer, usando o arquivo criado durante a exportação.

1. No Designer de relatórios, selecione **Empresa** &gt; **Grupos de Blocos de Construção**.
2. Selecione o grupo do bloco de construção para exportar, depois selecione **Exportar**.

    > [!NOTE]
    > Para o Finanças e Operações, apenas um grupo de blocos de construção é suportado, **Padrão**.

3. Selecione o bloco de construção **Padrão** e selecione **Importar**.
4. Selecione o arquivo que contém as definições de relatório exportadas e selecione **Abrir**.
5. Na caixa de diálogo **Importar**, selecione as definições de relatório para importar:

    - Para importar todas as definições de relatório e os blocos de construção associados, clique em **Selecionar Tudo**.
    - Para importar relatórios, linhas, colunas, hierarquias ou conjuntos de dimensões específicos, selecione os relatórios, as linhas, as colunas, as hierarquias ou os conjuntos de dimensões a serem importados.

6. Selecione **Importar**.

## <a name="reset-the-financial-reporting-data-mart-for-finance-and-operations-on-premises"></a>Redefina o data mart de relatórios financeiros para Finance and Operations (local)

1. Instrua todos os usuários para sair do designer de relatórios e da área de relatórios financeiros do Finance and Operations.
2. Execute o seguinte script no base de dados de relatórios financeiros (MRDB).

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

3. Truncar ou excluir todos os registros da tabela FINANCIALREPORTS no banco de dados do Finance and Operations (AXDB).
4. Truncar ou excluir todos os registros da tabela FINANCIALREPORTVERSION, se esta tabela existir no banco de dados do Finance and Operations. Se a tabela não existir no base de dados do Finance and Operations, ignore esta etapa.
5. Execute o script **ResetDatamart.sql** com o banco de dados do relatório financeiro. Este script desabilita a integração de data mart, exclui todos os dados de data mart e habilita novamente a integração de data mart.

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

6. Após a redefinição, você pode verificar a recarga de dados manualmente, executando as seguintes consultas no base de dados de relatórios financeiros.

    ```
    select ReaderObjectName, WriterObjectName, LastRunTime, StateType from Connector.MapsWithDetail with (nolock)
    ```

    Confirme se todas as linhas têm o valor **LastRunTime** e se **StateType** está definido como **5**. Um valor **StateType** de **5** indica que os dados foram recarregados com êxito. Um valor de **7** indica o estado com falha. Ocasionalmente, o mapa de hierarquia organizacional tem este estado na primeira vez que é executado. Entretanto, o estado com falha deve ser resolvido automaticamente.

