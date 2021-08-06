---
title: Solucionar problemas de sincronização ao vivo
description: Este tópico fornece informações sobre como solucionar problemas que podem ajudá-lo a corrigir problemas com a sincronização dinâmica.
author: RamaKrishnamoorthy
ms.date: 03/16/2020
ms.topic: article
ms.prod: ''
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
ms.openlocfilehash: a0a14c87af7f0d2372d752233f21d9accbca58a8
ms.sourcegitcommit: f65bde9ab0bf4c12a3250e7c9b2abb1555cd7931
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/13/2021
ms.locfileid: "6542506"
---
# <a name="troubleshoot-live-synchronization-issues"></a>Solucionar problemas de sincronização ao vivo

[!include [banner](../../includes/banner.md)]

[!include [rename-banner](~/includes/cc-data-platform-banner.md)]

Este tópico fornece informações de solução de problemas para integração de gravação dupla entre aplicativos do Finance and Operations e o Dataverse. Especificamente, ele fornece informações que podem ajudá-lo a corrigir problemas com a sincronização dinâmica.

> [!IMPORTANT]
> Alguns dos problemas que este tópico aborda podem exigir a função de administrador do sistema ou as credenciais de administrador do locatário Microsoft Azure Active Directory (Azure AD). A seção para cada problema explica se uma função ou credenciais específicas são necessárias.

## <a name="live-synchronization-throws-a-403-forbidden-error-when-you-create-a-row-in-a-finance-and-operations-app"></a>A sincronização dinâmica lança um erro 403 Proibido ao criar uma linha em um aplicativo Finance and Operations

Você pode receber a seguinte mensagem de erro ao criar uma linha em um aplicativo Finance and Operations:

*\[{\\"error\\":{\\"code\\":\\"0x80072560\\",\\"message\\":\\"O usuário não é um membro da organização.\\"}}\], O servidor remoto retornou um erro: (403) Proibido."}}".*

Para corrigir o problema, siga as etapas dos [pré-requisitos e requisitos do sistema](requirements-and-prerequisites.md). Para concluir essas etapas, os usuários do aplicativo de gravação dupla que são criados em Dataverse devem ter a função de administrador do sistema. A equipe de propriedade padrão também deve ter a função de administrador do sistema.

## <a name="live-synchronization-for-any-table-consistently-throws-a-similar-error-when-you-create-a-row-in-a-finance-and-operations-app"></a>A sincronização ao vivo de uma tabela lança, de forma consistente, um erro semelhante ao criar uma linha em um aplicativo do Finance and Operations

**Função necessária para corrigir o problema:** administrador do sistema

Você pode receber uma mensagem de erro como a seguinte toda vez que tentar salvar dados da tabela em um aplicativo do Finance and Operations:

*Não é possível salvar as alterações no banco de dados. A unidade de trabalho não pode confirmar a transação. Não é possível gravar dados no uoms da entidade. As gravações no UnitOfMeasureEntity falharam com a mensagem de erro. Não é possível sincronizar com a entidade uoms.*

Para corrigir o problema, você deve verificar se os dados de referência de pré-requisito existem no aplicativo Finance and Operations e Dataverse. Por exemplo, se o cliente que você está no aplicativo Finance and Operations pertencer a um grupo de clientes específico, verifique se o grupo de clientes existe em Dataverse.

Se houver dados em ambos os lados e você tiver confirmado que o problema não é relacionado a dados, siga estas etapas.

1. Interrompa a tabela relacionada.
2. Faça login no aplicativo do Finance and Operations e verifique se as linhas da tabela com falha existem nas tabelas DualWriteProjectConfiguration e DualWriteProjectFieldConfiguration. Por exemplo, está será a aparência da consulta se a tabela **Clientes** estiver falhando.

    ```sql
    Select projectname, externalenvironmentURL ,\* 
    from DUALWRITEPROJECTCONFIGURATION 
    where INTERNALENTITYNAME = 'Customers V3' and
        EXTERNALENTITYNAME = 'accounts' 
    ```

3. Se houver linhas para a tabela com falha mesmo depois que você interromper o mapeamento de tabela, exclua as linhas relacionados à tabela com falha. Anote a coluna **projectname** na tabela DualWriteProjectConfiguration e busque o registro na linha DualWriteProjectFieldConfiguration usando o nome do projeto para excluir a linha.
4. Inicie o mapeamento de tabela. Validar se os dados são sincronizados sem problemas.

## <a name="handle-read-or-write-privilege-errors-when-you-create-data-in-a-finance-and-operations-app"></a>Manipular erros de privilégio de leitura ou gravação ao criar dados em um aplicativo Finance and Operations

Você pode receber uma mensagem de erro de "solicitação incorreta" que se assemelha ao exemplo a seguir ao criar dados em um aplicativo Finance and Operations.

![Exemplo da mensagem inválida de erro de solicitação.](media/error_record_id_source.png)

Para corrigir o problema, você deve atribuir o direito de acesso correto à equipe da unidade de negócios do Dynamics 365 Sales ou do Dynamics 365 Customer Service mapeada para habilitar o privilégio ausente.

1. No aplicativo Finance and Operations, localize a unidade de negócios mapeada no conjunto de conexões de integração de dados.

    ![Mapeamento da organização.](media/mapped_business_unit.png)

2. Faça login no ambiente no aplicativo de interação com o cliente, navegue até **Configurações \> Segurança** e encontre a equipe da unidade de negócios mapeada.

    ![Equipe da unidade de negócios mapeada.](media/setting_security_page.png)

3. Abra a página da equipe para edição, e depois selecione **Gerenciar funções** para abrir a caixa de diálogo **Gerenciar funções de equipe**.

    ![Gerenciar botão de funções.](media/manage_team_roles.png)

4. Atribua a função que tem o privilégio de leitura/gravação para as tabelas relevantes e selecione **OK**.

## <a name="fix-synchronization-issues-in-an-environment-that-has-a-recently-changed-dataverse-environment"></a>Corrigir problemas de sincronização em um ambiente que tem um ambiente Dataverse alterado recentemente

**Função necessária para corrigir o problema:** administrador do sistema

Você pode receber a seguinte mensagem de erro ao criar dados em um aplicativo Finance and Operations:

*{"entityName":"CustCustomerV3Entity","executionStatus":2,"fieldResponses":\[\],"recordResponses":\[{"errorMessage":"**Unable para gerar carga de trabalho para a entidade CustCustomerV3Entity**","logDateTime":"2019-08-27T18:51:52.5843124Z","verboseError":"Criação de carga de trabalho falhada com erro de URI inválido: O URI está vazio."}\],"isErrorCountUpdated":true}*

Veja como é uma mensagem de erro no aplicativo de interação com o cliente:

*Ocorreu um erro inesperado no código do ISV. (ErrorType = ClientError) Exceção inesperada do plug-in (Executar): Microsoft.Dynamics.Integrator.DualWriteRuntime.Plugins.PostCommitPlugin: System.Exception: falha ao processar conta da entidade — (Houve falha em uma tentativa de conexão porque a parte conectada não respondeu adequadamente após um período de tempo ou houve falha na conexão estabelecida porque o host não respondeu*

Este erro ocorre quando o ambiente Dataverse é redefinido incorretamente ao mesmo tempo que você tenta criar dados no aplicativo Finance and Operations.

Para corrigir o problema, siga estas etapas.

1. Entre na máquina virtual Finance and Operations (VM), abra SQL Server Management Studio (SSMS), e procure por linhas na tabela DUALWRITEPROJECTCONFIGURATIONENTITY onde **internalentityname** é igual a **Clientes V3** e **externalentityname** é igual a **contas**. Esta é a aparência da consulta.

    ```sql
    select projectname, externalenvironmentURL ,\* 
    from DUALWRITEPROJECTCONFIGURATION 
    where INTERNALENTITYNAME = 'Customers V3' and EXTERNALENTITYNAME = 'accounts'
    ```

2. Use o nome do projeto dos resultados da consulta anterior para executar a consulta a seguir.

    ```sql
    select \* 
    from DUALWRITEPROJECTFIELDCONFIGURATION 
    where projectname = <project name from previous query>
    ```

3. Verifique se a coluna **externalenvironmentURL** tem o Dataverse correto ou URL de aplicativo. Exclua as linhas duplicadas que apontam para a URL de Dataverse errada. Exclua as linhas correspondentes nas tabelas DUALWRITEPROJECTFIELDCONFIGURATION e DUALWRITEPROJECTCONFIGURATION.
4. Interrompa o mapeamento de tabela e reinicie-o

[!INCLUDE[footer-include](../../../../includes/footer-banner.md)]
