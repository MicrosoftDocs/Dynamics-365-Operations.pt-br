---
title: "Redefinir data mart de relatório financeiro após restaurado um base de dados"
description: "Este tópico descreve como redefinir data mart de relatório financeiro após restaurado Microsoft Dynamics 365 de dados de operações."
author: twheeloc
manager: AnnBe
ms.date: 2016-12-08 16 - 20 - 13
ms.topic: article
ms.prod: 
ms.service: Dynamics365Operations
ms.technology: 
audience: Application User, IT Pro
ms.search.scope: Operations, Core
ms.custom: 261824
ms.assetid: d0784b2c-fe10-428d-8d07-fd474ca50fcc
ms.search.region: Global
ms.author: kweekley
ms.search.validFrom: 2016-11-30
ms.dyn365.ops.version: Version 1611
translationtype: Human Translation
ms.sourcegitcommit: 4d6cf88788dcc5e982e509137aa444a020137a5e
ms.openlocfilehash: 3967cbb869fbb23d5d7716f619e4c22b4a273921
ms.lasthandoff: 03/29/2017


---

# <a name="reset-the-financial-reporting-data-mart-after-restoring-a-database"></a>Redefinir data mart de relatório financeiro após restaurado um base de dados

Este tópico descreve como redefinir data mart de relatório financeiro após restaurado Microsoft Dynamics 365 de dados de operações. 

Há vários cenários onde você possa precisar restaurar sua dynamics 365 de dados de um backup de operações ou de copiar o base de dados de outra ambiente. Quando isso ocorre, também precisará rastrear etapas apropriados para garantir que a data mart de relatório financeiro usando está corretamente o dynamics restaurada 365 de dados de operações. Se você tiver dúvidas sobre redefinir data mart de relatórios financeiros para um razão fora restaurar uma dynamics 365 de dados, consulte operações [redefinindo o data mart] do management reporter https://blogs.msdn.microsoft.com/dynamics_financial_reporting/2016/06/28/resetting-the-management-reporter-data-mart/) (para obter mais informações. Observe que as etapas desse processo são suportadas para dynamics 365 para a operação maio de 2016 (versão de compilação 7.0.1265.23014 e descritivo de compilação 7.0.10000.4 de relatório financeiro) e as versões mais novas. Se você tiver uma versão anterior de condicional dynamics 365 para operações, entre em contato com nosso equipe de suporte da ajuda.

## <a name="export-report-definitions"></a>Exportar definições de relatório
Primeiro, exporte os criar localizados de relatório no Report Designer, usando as seguintes etapas:

1.  No Report Designer, vão ** empresa ** &gt; ** grupos de blocos de construção. **
2.  Selecione o grupo de bloco de construção para exportar, clique ** ** exportação. ** Observação: ** Para dynamics 365 para operações, apenas um grupo de bloco de construção é suportado, ** ** padrão.
3.  Selecione as definições de relatório para exportar:
    -   Para exportar todas as definições de relatório e os blocos de construção associados, clique em **Selecionar Tudo**.
    -   Para exportar relatórios, linhas, colunas, árvores ou conjuntos de dimensões específicos, clique na guia apropriada e selecione os itens a serem exportados. Pressione e mantenha pressionada a tecla Ctrl para selecionar vários itens em uma guia. Quando você seleciona relatórios para exportar, as linhas, as colunas, as hierarquias, e conjuntos de dimensões associados são selecionados.

4.  Clique ** ** exportação.
5.  Insira um nome de arquivo e selecione um local seguro onde deseja salvar as definições de relatório exportadas.
6.  Click **Save**.

O arquivo pode ser copiada ou carregado em um local seguro, permitindo que é importadas em um ambiente em uma diferente outras horas. Informações sobre o uso de uma conta de armazenamento do Microsoft Azure pode ser encontrada em [transferir dados com o utilitário de linha de comando] de AzCopy (https://docs.microsoft.com/en-gb/azure/storage/storage-use-azcopy). ** Observação: ** Microsoft não fornece uma conta de estoque como parte de suas dynamics 365 do contrato de operações. Você deve comprar uma conta de armazenamento ou usar uma conta de armazenamento de uma subscrição separada de Azure. ** Importante: ** Saiba comportamento da unidade de itens em máquinas virtuais de Azure. Não exportados manter os grupos de blocos de construção aqui permanentemente. Para obter mais informações sobre unidades, consulte temporárias [compreendendo a unidade temporária em máquinas virtuais] de Windows Azure (https://blogs.msdn.microsoft.com/mast/2013/12/06/understanding-the-temporary-drive-on-windows-azure-virtual-machines/).

## <a name="stop-services"></a>Parar serviços
Usar área de trabalho remota conectar a todos os computadores no ambiente e interromper os seguintes Serviços usando o Windows services.msc:

-   Serviço de publicação da web (em qualquer computador a OS)
-   Microsoft Dynamics 365 para o serviço de gerenciamento de operações (lote em máquinas particulares não apenas a OS)
-   Serviço de processos do management reporter 2012 (em computadores de BI apenas)

Esses serviços terão conexões abertas o dynamics 365 de dados de operações.

## <a name="reset"></a>Redefinir
#### <a name="locate-the-latest-dataupgradezip-package"></a>Localize o pacote o último de DataUpgrade.zip

Localize o pacote o último de DataUpgrade.zip usando as direções localizadas em [baixe o script de DataUpgrade.zip (]. \ \ upgrade-data-to-latest-update.md atualização). As direções explicam como atender a versão correta de pacote de atualização de dados de seu ambiente.

#### <a name="execute-scripts-against-dynamics-365-for-operations-database"></a>Executar scripts no dynamics 365 de dados de operações

Execute os seguintes scripts no dynamics 365 de dados de operações (não ao base de dados do relatório financeiro.)

-   Scripts\\ConfigureAxReportingIntegration.sql de DataUpgrade.zip\\AosService\\
-   Scripts\\GrantAzViewChangeTracking.sql de DataUpgrade.zip\\AosService\\

Esses scripts asseguram que os usuários, funções, e as configurações de controle de alterações estão corretos.

#### <a name="execute-powershell-command-to-reset-database"></a>Executar um comando de PowerShell redefinir o base de dados

Execute o seguinte comando, diretamente no computador aos, fazer a integração entre o dynamics 365 para operações e o relatório financeiro:

1.  Abra Windows PowerShell como administrador.
2.  Executar: F:
3.  Executar: CD F:\\MRApplicationService\\MRInstallDirectory
4.  Executar: Importação-módulo. o\\MRDeploy\\MRDeploy.psd1\\
5.  Executar: - Raciocina C*1,25 - ReasonDetail redefinido - DatamartIntegration “&lt;motivo para redefinir&gt;a”
    -   Você será solicitado a inserir “Y” ao confirmar.

Explicação parâmetros:

-   Valores válidas para - o motivo é: CONSERVAÇÃO, BADDATA, ELSE.
-   O parâmetro de ReasonDetail é texto livre.
-   A razão e o reasonDetail serão registrados em telemetria/monitoramento de ambiente.

## <a name="start-services"></a>Inicie serviços
Use services.msc reiniciar serviços que você interrompeu anterior:

-   Serviço de publicação da web (em qualquer computador a OS)
-   Microsoft Dynamics 365 para o serviço de gerenciamento de operações (lote em máquinas particulares não apenas a OS)
-   Serviço de processos do management reporter 2012 (em computadores de BI apenas)

## <a name="import-report-definitions"></a>Importar definições de relatório
Importar criar os relatórios do Report Designer, usando o arquivo criada durante a exportação:

1.  No Report Designer, vão ** empresa ** &gt; ** grupos de blocos de construção. **
2.  Selecione o grupo de bloco de construção para exportar, clique ** ** exportação. ** Observação: ** Para dynamics 365 para operações, apenas um grupo de bloco de construção é suportado, ** ** padrão.
3.  ** Selecionar padrão ** o bloco de construção e clique ** ** importação.
4.  Selecione o arquivo que contém as definições de relatório e clique exportados ** ** aberto.
5.  Na caixa de diálogo Importar, selecione as definições de relatório para importação:
    -   Para importar todas as definições de relatório e os blocos de construção de suporte, clique em **Selecionar Tudo**.
    -   Para importar relatórios, linhas, colunas, árvores ou conjuntos de dimensões específicos, selecione os relatórios, as linhas, as colunas, as árvores ou os conjuntos de dimensões a serem importados.

6.  Click **Import**.



