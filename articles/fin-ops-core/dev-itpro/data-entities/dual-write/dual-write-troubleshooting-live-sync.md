---
title: Solucionar problemas de sincronização ao vivo
description: Este tópico fornece informações sobre como solucionar problemas que podem ajudá-lo a corrigir problemas com a sincronização dinâmica.
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
ms.search.scope: Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: global
ms.search.industry: ''
ms.author: ramasri
ms.dyn365.ops.version: ''
ms.search.validFrom: 2020-03-16
ms.openlocfilehash: d45b19c1e88e6a27bde4335d4a356f2173bdfcd3
ms.sourcegitcommit: e06da171b9cba8163893e30244c52a9ce0901146
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/21/2020
ms.locfileid: "3275408"
---
# <a name="troubleshoot-live-synchronization-issues"></a>Solucionar problemas de sincronização ao vivo

[!include [banner](../../includes/banner.md)]



Este tópico fornece informações de solução de problemas para integração de gravação dupla entre aplicativos do Finance and Operations e o Common Data Service. Especificamente, ele fornece informações que podem ajudá-lo a corrigir problemas com a sincronização dinâmica.

> [!IMPORTANT]
> Alguns dos problemas que este tópico aborda podem exigir a função de administrador do sistema ou as credenciais de administrador do locatário Microsoft Azure Active Directory (Azure AD). A seção para cada problema explica se uma função ou credenciais específicas são necessárias.

## <a name="live-synchronization-throws-a-403-forbidden-error-when-you-create-a-record-in-a-finance-and-operations-app"></a>A sincronização dinâmica lança um erro 403 Proibido ao criar um registro em um aplicativo Finance and Operations

Você pode receber a seguinte mensagem de erro ao criar um registro em um aplicativo Finance and Operations:

*\[{\\"error\\":{\\"code\\":\\"0x80072560\\",\\"message\\":\\"O usuário não é um membro da organização.\\"}}\], O servidor remoto retornou um erro: (403) Proibido."}}".*

Para corrigir o problema, siga as etapas dos [pré-requisitos e requisitos do sistema](requirements-and-prerequisites.md). Para concluir essas etapas, os usuários do aplicativo de gravação dupla que são criados em Common Data Service devem ter a função de administrador do sistema. A equipe de propriedade padrão também deve ter a função de administrador do sistema.

## <a name="live-synchronization-for-any-entity-consistently-throws-a-similar-error-when-you-create-a-record-in-a-finance-and-operations-app"></a>A sincronização ao vivo de uma entidade lança, de forma consistente, um erro semelhando ao criar um registro em um aplicativo Finance and Operations

**Função necessária para corrigir o problema:** administrador do sistema

Você pode receber uma mensagem de erro como a seguinte toda vez que tentar salvar dados da entidade em um aplicativo Finance and Operations:

*Não é possível salvar as alterações no banco de dados. A unidade de trabalho não pode confirmar a transação. Não é possível gravar dados no uoms da entidade. As gravações no UnitOfMeasureEntity falharam com a mensagem de erro. Não é possível sincronizar com a entidade uoms.*

Para corrigir o problema, você deve verificar se os dados de referência de pré-requisito existem no aplicativo Finance and Operations e Common Data Service. Por exemplo, se o cliente que você está no aplicativo Finance and Operations pertencer a um grupo de clientes específico, verifique se o grupo de clientes existe em Common Data Service.

Se houver dados em ambos os lados e você tiver confirmado que o problema não é relacionado a dados, siga estas etapas.

1. Interrompa a entidade relacionada.
2. Faça login no aplicativo Finance and Operations e verifique se os registros da entidade com falha existem nas tabelas DualWriteProjectConfiguration e DualWriteProjectFieldConfiguration. Por exemplo, aqui está a aparência da consulta se a entidade **Clientes** está falhando.

    ```sql
    Select projectname, externalenvironmentURL ,\* 
    from DUALWRITEPROJECTCONFIGURATION 
    where INTERNALENTITYNAME = 'Customers V3' and
        EXTERNALENTITYNAME = 'accounts' 
    ```

3. Se houver registros para a entidade com falha mesmo depois que você interromper o mapeamento de entidade, exclua os registros relacionados à entidade com falha. Anote a coluna **projectname** na tabela DualWriteProjectConfiguration, e busque o registro na tabela DualWriteProjectFieldConfiguration usando o nome do projeto para excluir o registro.
4. Inicie o mapeamento de entidade. Validar se os dados são sincronizados sem problemas.

## <a name="handle-read-or-write-privilege-errors-when-you-create-data-in-a-finance-and-operations-app"></a>Manipular erros de privilégio de leitura ou gravação ao criar dados em um aplicativo Finance and Operations

Você pode receber uma mensagem de erro de "solicitação incorreta" que se assemelha ao exemplo a seguir ao criar dados em um aplicativo Finance and Operations.

![Exemplo da mensagem inválida de erro de solicitação](media/error_record_id_source.png)

Para corrigir o problema, você deve atribuir o direito de acesso correto à equipe da unidade de negócios do Dynamics 365 Sales ou do Dynamics 365 Customer Service mapeada para habilitar o privilégio ausente.

1. No aplicativo Finance and Operations, localize a unidade de negócios mapeada no conjunto de conexões de integração de dados.

    ![Mapeamento da organização](media/mapped_business_unit.png)

2. Faça login no ambiente no aplicativo controlado por modelo no Dynamics 365, navegue até **Definir segurança do \>**, e encontre a equipe da unidade de negócios mapeada.

    ![Equipe da unidade de negócios mapeada](media/setting_security_page.png)

3. Abra a página da equipe para edição, e depois selecione **Gerenciar funções** para abrir a caixa de diálogo **Gerenciar funções de equipe**.

    ![Gerenciar botão de funções](media/manage_team_roles.png)

4. Atribua a função que tem o privilégio de leitura/gravação para as entidades relevantes e selecione **OK**.

## <a name="fix-synchronization-issues-in-an-environment-that-has-a-recently-changed-common-data-service-environment"></a>Corrigir problemas de sincronização em um ambiente que tem um ambiente Common Data Service alterado recentemente

**Função necessária para corrigir o problema:** administrador do sistema

Você pode receber a seguinte mensagem de erro ao criar dados em um aplicativo Finance and Operations:

*{"entityName":"CustCustomerV3Entity","executionStatus":2,"fieldResponses":\[\],"recordResponses":\[{"errorMessage":"**Unable para gerar carga de trabalho para a entidade CustCustomerV3Entity**","logDateTime":"2019-08-27T18:51:52.5843124Z","verboseError":"Criação de carga de trabalho falhada com erro de URI inválido: O URI está vazio."}\],"isErrorCountUpdated":true}*

Esta é a aparência do erro no aplicativo baseado em modelo no Dynamics 365:

*Ocorreu um erro inesperado no código do ISV. (ErrorType = ClientError) Exceção inesperada do plug-in (Executar): Microsoft.Dynamics.Integrator.DualWriteRuntime.Plugins.PostCommitPlugin: System.Exception: falha ao processar conta da entidade — (Houve falha em uma tentativa de conexão porque a parte conectada não respondeu adequadamente após um período de tempo ou houve falha na conexão estabelecida porque o host não respondeu*

Este erro ocorre quando o ambiente Common Data Service é redefinido incorretamente ao mesmo tempo que você tenta criar dados no aplicativo Finance and Operations.

Para corrigir o problema, siga estas etapas.

1. Entre na máquina virtual Finance and Operations (VM), abra SQL Server Management Studio (SSMS), e procure por registros na tabela DUALWRITEPROJECTCONFIGURATIONENTITY onde **internalentityname** é igual a **Clientes V3** e **externalentityname** é igual a **contas**. Esta é a aparência da consulta.

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

3. Verifique se a coluna **externalenvironmentURL** tem o Common Data Service correto ou URL de aplicativo. Exclua os registros duplicados que apontam para a URL de Common Data Service errada. Exclua os registros correspondentes nas tabelas DUALWRITEPROJECTFIELDCONFIGURATION e DUALWRITEPROJECTCONFIGURATION.
4. Interrompa o mapeamento da entidade e reinicie-o
