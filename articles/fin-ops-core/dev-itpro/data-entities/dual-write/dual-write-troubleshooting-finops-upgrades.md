---
title: Solucionar problemas de atualizações de aplicativos do Finance and Operations
description: Este tópico fornece informações sobre como solucionar problemas relativos a atualizações de aplicativos de Finanças e Operações.
author: RamaKrishnamoorthy
ms.date: 03/16/2020
ms.topic: article
audience: Application User, IT Pro
ms.reviewer: tfehr
ms.search.region: global
ms.author: ramasri
ms.search.validFrom: 2020-01-06
ms.openlocfilehash: c7c036ef44b0470c9b3f8087e7b5b1e16dde1b34
ms.sourcegitcommit: 4be1473b0a4ddfc0ba82c07591f391e89538f1c3
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/31/2022
ms.locfileid: "8062816"
---
# <a name="troubleshoot-issues-from-upgrades-of-finance-and-operations-apps"></a>Solucionar problemas de atualizações de aplicativos do Finance and Operations

[!include [banner](../../includes/banner.md)]





Este tópico fornece informações de solução de problemas para a integração de gravação dupla entre aplicativos de Finanças e Operações e o Dataverse. Especificamente, ele fornece informações sobre como solucionar problemas relativos a atualizações de aplicativos de Finanças e Operações.

> [!IMPORTANT]
> Alguns dos problemas que este tópico aborda podem exigir a função de administrador do sistema ou as credenciais de administrador do locatário Microsoft Azure Active Directory (Azure AD). A seção para cada problema explica se uma função ou credenciais específicas são necessárias.

## <a name="database-synchronization-errors"></a>Sincronização de erros de banco de dados

**Função necessária para corrigir o problema:** administrador do sistema

Você pode receber uma mensagem de erro semelhante à seguinte ao tentar usar a tabela **DualWriteProjectConfiguration** para atualizar um aplicativo de Finanças e Operações para atualização de plataforma 30.

```console
Infolog diagnostic message: 'Cannot select a row in Dual write project sync (DualWriteProjectConfiguration). The SQL database has issued an error.' on category 'Error'. 10/28/2019 15:18:20: Infolog diagnostic message: 'Object Server Database Synchronizer: ' on category 'Error'. 10/28/2019 15:18:20: Infolog diagnostic message: '[Microsoft][ODBC Driver 17 for SQL Server][SQL Server]Invalid column name 'ISDELETE'.' on category 'Error'. 10/28/2019 15:18:20: Infolog diagnostic message: 'SELECT T1.PROJECTNAME,T1.EXTERNALENTITYNAME,T1.INTERNALENTITYNAME,T1.EXTERNALENVIRONMENTURL,T1.STATUS,T1.ENABLEBATCHLOOKUP,T1.PARTITIONMAP,T1.QUERYFILTEREXPRESSION,T1.INTEGRATIONKEY,T1.ISDELETE,T1.ISDEBUGMODE,T1.RECVERSION,T1.PARTITION,T1.RECID FROM DUALWRITEPROJECTCONFIGURATION T1 WHERE (PARTITION=5637144576)' on category 'Error'. 10/28/2019 15:18:20: Infolog diagnostic message: 'session 1043 (Admin)' on category 'Error'. 10/28/2019 15:18:20: Infolog diagnostic message: 'Stack trace: Call to TTSCOMMIT without first calling TTSBEGIN.' on category 'Error'.
10/28/2019 15:18:20: Application configuration sync failed.
Microsoft.Dynamics.AX.Framework.Database.TableSyncException: Custom action threw exception(s), please investigate before synchronizing again: 'InfoException:Stack trace: Call to TTSCOMMIT without first calling TTSBEGIN."
```

Para corrigir o problema, siga estas etapas.

1. Entre na máquina virtual (VM) para o aplicativo de Finanças e Operações.
2. Abra Visual Studio como um administrador e abra a AOT (árvore de objetos de aplicativo).
3. Procure **DualWriteProjectConfiguration**.
4. No AOT, clique com o botão direito em **DualWriteProjectConfiguration** e selecione **Adicionar ao novo projeto**. Selecione **OK** para criar o novo projeto que usa opções padrão.
5. No Gerenciador de Soluções, clique com o botão direito em **Propriedades de projeto** e defina **Sincronizar banco de dados no Build** como **Verdadeiro**.
6. Compile o projeto e confirme se a compilação foi bem-sucedida.
7. No menu **Dynamics 365**, selecione **Sincronizar banco de dados**.
8. Selecione **Sincronizar** para fazer uma sincronização de banco de dados completa.
9. Depois que a sincronização completa do banco de dados for bem-sucedida, execute novamente a etapa de sincronização do banco de dados em Microsoft Dynamics Lifecycle Services (LCS) e use os scripts de atualização manual conforme aplicável, para que você possa continuar com a atualização.

## <a name="missing-table-columns-issue-on-maps"></a>Problema de colunas de tabela ausentes nos mapas

**Função necessária para corrigir o problema:** administrador do sistema

Na página **Gravação dupla**, você pode receber uma mensagem de erro parecida com o seguinte exemplo:

*Nome do campo de origem \<field name\> ausente no esquema.*

![Exemplo da mensagem de erro de coluna de origem ausente.](media/error_missing_field.png)

Para corrigir o problema, primeiro siga estas etapas para verificar se as colunas estão na tabela.

1. Entre na VM para o aplicativo de Finanças e Operações.
2. Acesse **Espaços de trabalho \> Gerenciamento de dados**, selecione o bloco **Parâmetros de estrutura** e, em seguida, na guia **Configurações da tabela**, selecione **Atualizar lista de tabelas** para atualizar as tabelas.
3. Acesse **Espaços de trabalho \> Gerenciamento de dados**, selecione a guia **Tabelas de dados** e certifique-se de que a tabela esteja listada. Se a tabela não estiver listada, entre na VM para o aplicativo de Finanças e Operações e certifique-se de que a tabela esteja disponível.
4. Abra a página **Mapeamento da tabela** na página **Gravação dupla** no aplicativo de Finanças e Operações.
5. Selecione **Atualizar lista de tabelas** para preencher automaticamente as colunas nos mapeamentos de tabela.

Se o problema ainda não for solucionado, siga estas etapas.

> [!IMPORTANT]
> Essas etapas o orientam no processo de exclusão de uma tabela e, em seguida, a adiciona novamente. Para evitar problemas, certifique-se de seguir as etapas exatamente.

1. No aplicativo de Finanças e Operações, acesse **Espaços de trabalho \> Gerenciamento de dados** e selecione o bloco **Tabelas de dados**.
2. Encontre a tabela que está sem o atributo. Clique em **Modificar mapeamento de destino** na barra de ferramentas.
3. No painel **Mapear preparo para destino**, clique em **gerar mapeamento**.
4. Abra a página **Mapeamento da tabela** na página **Gravação dupla** no aplicativo de Finanças e Operações.
5. Se o atributo não estiver preenchido automaticamente no mapa, adicione-o manualmente, clicando no botão **Adicionar atributo** e clicando em **Salvar**. 
6. Selecione o mapa e clique em **Executar**.


[!INCLUDE[footer-include](../../../../includes/footer-banner.md)]