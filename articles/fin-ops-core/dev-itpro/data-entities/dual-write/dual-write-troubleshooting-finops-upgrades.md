---
title: Solucionar problemas relacionados a atualizações de aplicativos do Finance and Operations
description: Este tópico fornece informações sobre como solucionar problemas que são relacionados às atualizações dos aplicativos Finance and Operations.
author: RamaKrishnamoorthy
manager: AnnBe
ms.date: 03/16/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ''
audience: Application User, IT Pro
ms.reviewer: rhaertle
ms.custom: ''
ms.assetid: ''
ms.search.region: global
ms.search.industry: ''
ms.author: ramasri
ms.dyn365.ops.version: ''
ms.search.validFrom: 2020-03-16
ms.openlocfilehash: c76b35ed3af766f42484a118a4a0407d969b5240
ms.sourcegitcommit: 659375c4cc7f5524cbf91cf6160f6a410960ac16
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/05/2020
ms.locfileid: "4683590"
---
# <a name="troubleshoot-issues-related-to-upgrades-of-finance-and-operations-apps"></a>Solucionar problemas relacionados a atualizações de aplicativos do Finance and Operations

[!include [banner](../../includes/banner.md)]

[!include [rename-banner](~/includes/cc-data-platform-banner.md)]



Este tópico fornece informações de solução de problemas para integração de gravação dupla entre aplicativos do Finance and Operations e o Dataverse. Especificamente, ele fornece informações sobre como solucionar problemas que são relacionados às atualizações dos aplicativos Finance and Operations.

> [!IMPORTANT]
> Alguns dos problemas que este tópico aborda podem exigir a função de administrador do sistema ou as credenciais de administrador do locatário Microsoft Azure Active Directory (Azure AD). A seção para cada problema explica se uma função ou credenciais específicas são necessárias.

## <a name="database-synchronization-errors"></a>Sincronização de erros de banco de dados

**Função necessária para corrigir o problema:** administrador do sistema

Você pode receber uma mensagem de erro semelhante à seguinte ao tentar usar a entidade **DualWriteProjectConfiguration** para atualizar um aplicativo Finance and Operations para atualização de plataforma 30.

```console
Infolog diagnostic message: 'Cannot select a row in Dual write project sync (DualWriteProjectConfiguration). The SQL database has issued an error.' on category 'Error'. 10/28/2019 15:18:20: Infolog diagnostic message: 'Object Server Database Synchronizer: ' on category 'Error'. 10/28/2019 15:18:20: Infolog diagnostic message: '[Microsoft][ODBC Driver 17 for SQL Server][SQL Server]Invalid column name 'ISDELETE'.' on category 'Error'. 10/28/2019 15:18:20: Infolog diagnostic message: 'SELECT T1.PROJECTNAME,T1.EXTERNALENTITYNAME,T1.INTERNALENTITYNAME,T1.EXTERNALENVIRONMENTURL,T1.STATUS,T1.ENABLEBATCHLOOKUP,T1.PARTITIONMAP,T1.QUERYFILTEREXPRESSION,T1.INTEGRATIONKEY,T1.ISDELETE,T1.ISDEBUGMODE,T1.RECVERSION,T1.PARTITION,T1.RECID FROM DUALWRITEPROJECTCONFIGURATION T1 WHERE (PARTITION=5637144576)' on category 'Error'. 10/28/2019 15:18:20: Infolog diagnostic message: 'session 1043 (Admin)' on category 'Error'. 10/28/2019 15:18:20: Infolog diagnostic message: 'Stack trace: Call to TTSCOMMIT without first calling TTSBEGIN.' on category 'Error'.
10/28/2019 15:18:20: Application configuration sync failed.
Microsoft.Dynamics.AX.Framework.Database.TableSyncException: Custom action threw exception(s), please investigate before synchronizing again: 'InfoException:Stack trace: Call to TTSCOMMIT without first calling TTSBEGIN."
```

Para corrigir o problema, siga estas etapas.

1. Faça login na máquina virtual (VM) para o aplicativo Finance and Operations.
2. Abra Visual Studio como um administrador e abra a AOT (árvore de objetos de aplicativo).
3. Procure **DualWriteProjectConfiguration**.
4. No AOT, clique com o botão direito em **DualWriteProjectConfiguration** e selecione **Adicionar ao novo projeto**. Selecione **OK** para criar o novo projeto que usa opções padrão.
5. No Gerenciador de Soluções, clique com o botão direito em **Propriedades de projeto** e defina **Sincronizar banco de dados no Build** como **Verdadeiro**.
6. Compile o projeto e confirme se a compilação foi bem-sucedida.
7. No menu **Dynamics 365**, selecione **Sincronizar banco de dados**.
8. Selecione **Sincronizar** para fazer uma sincronização de banco de dados completa.
9. Depois que a sincronização completa do banco de dados for bem-sucedida, execute novamente a etapa de sincronização do banco de dados em Microsoft Dynamics Lifecycle Services (LCS) e use os scripts de atualização manual conforme aplicável, para que você possa continuar com a atualização.

## <a name="missing-entity-fields-issue-on-maps"></a>Ausência de campos de entidade na edição de mapas

**Função necessária para corrigir o problema:** administrador do sistema

Na página **Gravação dupla**, você pode receber uma mensagem de erro parecida com o seguinte exemplo:

*Nome do campo de origem \<field name\> ausente no esquema.*

![Exemplo da mensagem de erro de campo de origem ausente](media/error_missing_field.png)

Para corrigir o problema, primeiro siga estas etapas para verificar se os campos estão na entidade.

1. Faça login na VM para o aplicativo Finance and Operations.
2. Acesse **Espaços de trabalho \> Gerenciamento de dados**, selecione o bloco **Parâmetros de estrutura** e, em seguida, na guia **Configurações da tabela**, selecione **Atualizar lista de entidade** para atualizar as tabelas.
3. Vá para **Espaços de trabalho \> Gerenciamento de dados**, selecione a guia **Tabelas de dados** e certifique-se de que a entidade está listada. Se a entidade não estiver listada, faça login na VM para o aplicativo Finance and Operations e certifique-se de que a entidade está disponível.
4. Abra a página **Mapeamento da tabela** na página **Gravação dupla** no aplicativo Finance and Operations.
5. Selecione **Atualizar lista de entidades** para preencher automaticamente os campos nos mapeamentos de tabela.

Se o problema ainda não for solucionado, siga estas etapas.

> [!IMPORTANT]
> Essas etapas o orientam no processo de exclusão de uma entidade e, em seguida, a adiciona novamente. Para evitar problemas, certifique-se de seguir as etapas exatamente.

1. No aplicativo Finance and Operations, vá para **Espaços de trabalho \> Gerenciamento de dados** e selecione o bloco **Tabelas de dados**.
2. Encontre a entidade que está sem o atributo. Clique em **Modificar mapeamento de destino** na barra de ferramentas.
3. No painel **Mapear preparo para destino**, clique em **gerar mapeamento**.
4. Abra a página **Mapeamento da tabela** na página **Gravação dupla** no aplicativo Finance and Operations.
5. Se o atributo não estiver preenchido automaticamente no mapa, adicione-o manualmente, clicando no botão **Adicionar atributo** e clicando em **Salvar**. 
6. Selecione o mapa e clique em **Executar**.


[!INCLUDE[footer-include](../../../../includes/footer-banner.md)]