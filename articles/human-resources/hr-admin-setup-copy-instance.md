---
title: Copiar uma instância
description: É possível usar o Microsoft Dynamics Lifecycle Services (LCS) para copiar um banco de dados do Microsoft Dynamics 365 Human Resources para um ambiente de área restrita.
author: twheeloc
ms.date: 07/22/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: SystemAdministrationWorkspaceForm
audience: Application User
ms.custom: 7521
ms.assetid: ''
ms.search.region: Global
ms.author: twheeloc
ms.search.validFrom: 2020-02-03
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: 20a2ffb44f9b99800146e3365e6f0d6df8e9a75e
ms.sourcegitcommit: 66d129874635d34a8b29c57762ecf1564e4dc233
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/23/2022
ms.locfileid: "9324250"
---
# <a name="copy-an-instance"></a>Copiar uma instância

_**Aplica-se a:** Human Resources na infraestrutura autônoma_ 

> [!NOTE]
> Iniciando em junho de 2022, os ambientes de Recursos Humanos podem ser implantados somente na infraestrutura de aplicativos de finanças e operações. Para obter mais informações, consulte [Provisionar Recursos Humanos na infraestrutura de finanças e operações](hr-admin-setup-provision-fo.md).

> [!IMPORTANT]
> A infraestrutura de finanças e operações não oferece suporte a uma função de cópia de instância. Você pode implantar novos ambientes e usar movimentos de banco de dados para criar cópias. Para obter mais informações sobre implantações de autoatendimento, consulte [Visão geral da Implantação de autoatendimento](../fin-ops-core/dev-itpro/deployment/infrastructure-stack.md). Para obter mais informações sobre os movimentos do banco de dados na infraestrutura de finanças e operações, consulte [Home page de operações de movimentação do banco de dados](../fin-ops-core/dev-itpro/database/dbmovement-operations.md).

É possível usar o Microsoft Dynamics Lifecycle Services (LCS) para copiar um banco de dados do Microsoft Dynamics 365 Human Resources para um ambiente de área restrita. Se houver outro ambiente de área restrita, você também poderá copiar o banco de dados daquele ambiente para um ambiente de área restrita direcionado.

Para copiar uma instância, lembre-se destas dicas:

- A instância de Human Resources que deseja substituir deve ser um ambiente de área restrita.

- Os ambientes dos quais você está copiando e para onde serão copiados devem estar na mesma região. Não é possível copiar entre regiões.

- Você deve ser um administrador no ambiente de destino para que possa fazer login nele depois de copiar a instância.

- Ao copiar o banco de dados de Human Resources, você não copia os elementos (aplicativos ou dados) contidos em um ambiente do Microsoft Power Apps. Para obter informações sobre como copiar elementos em um ambiente do Power Apps, consulte [Copiar um ambiente](/power-platform/admin/copy-environment). A ambiente do Power Apps que deseja substituir deve ser um ambiente de área restrita. Você deve ser um administrador de locatário global para alterar um ambiente de produção do Power Apps para um ambiente de área restrita. Para obter mais informações sobre como alterar um ambiente do Power Apps, consulte [Alternar uma instância](/dynamics365/admin/switch-instance).

- Se você copiar uma instância no ambiente de área restrita e quiser integrar seu ambiente de área restrita com o Dataverse, reaplique campos personalizados a tabelas do Dataverse. Consulte [Aplicar campos personalizados ao Dataverse](hr-admin-setup-copy-instance.md?apply-custom-fields-to-common-data-service).

## <a name="effects-of-copying-a-human-resources-database"></a>Efeitos da cópia de um banco de dados do Human Resources

> [!Note]
> A partir de agosto de 2022, os documentos no Armazenamento de Blobs do Microsoft Azure são incluídos ao copiar de um ambiente de produção para um ambiente de área restrita. Documentos e modelos anexados serão copiados do ambiente de origem no ambiente de destino.

Os seguintes eventos ocorrem ao copiar um banco de dados do Human Resources:

- O processo de cópia apaga o banco de dados existente no ambiente de destino. Depois que o processo de cópia for concluído, não será possível recuperar o banco de dados existente.

- O ambiente de destino não estará disponível até que o processo de cópia seja concluído.

- Todos os usuários, exceto aqueles com a função de segurança "Administrador do Sistema" e outras contas de usuário de serviço interno, não estarão disponíveis. O usuário administrador pode excluir dados antes que outros usuários tenham permissão para voltar ao sistema.

- Qualquer usuário com a função de segurança "Administrador do Sistema" deve fazer as alterações de configuração necessárias, como reconectar pontos de extremidade de integração a serviços ou URLs específicos.

## <a name="copy-the-human-resources-database"></a>Copiar o banco de dados do Human Resources

Para concluir essa tarefa, primeiro copie uma instância e efetue login na central de administração do Microsoft Power Platform para copiar seu ambiente do Power Apps.

> [!WARNING]
> Quando você copia uma instância, o banco de dados é apagado na instância de destino. A instância de destino não está disponível durante esse processo.

1. Faça login nas LCS e selecione o projeto LCS que contém a instância que você deseja copiar.

2. Em seu projeto LCS, selecione o bloco **Gerenciamento do Aplicativo de Human Resources**.

3. Selecione a instância a ser copiada e selecione **Copiar**.

4. No painel de tarefas **Copiar uma instância**, selecione a instância a ser substituída e, em seguida, selecione **Copiar**. Aguarde até o campo **Copiar status** ser atualizado para **Concluído**.

   ![[Selecione a instância a ser substituída.](./media/copy-instance-select-target-instance.png)](./media/copy-instance-select-target-instance.png)

5. Selecione **Power Platform**, e entre na central de administração do Microsoft Power Platform.

   ![[Selecione Power Platform.](./media/copy-instance-select-power-platform.png)](./media/copy-instance-select-power-platform.png)

6. Selecione o ambiente do Power Apps a ser copiada e selecione **Copiar**.

Para obter mais informações sobre cópia de ambientes do Power Apps, consulte [Copiar um ambiente](/power-platform/admin/copy-environment#copy-an-environment-1).

7. Quando o processo de cópia for concluído, efetue login na instância de destino e habilite a integração do Dataverse. Para saber mais informações e instruções, consulte [Configurar a integração do Dataverse](./hr-admin-integration-common-data-service.md).

## <a name="data-elements-and-statuses"></a>Elementos de dados e status

Os seguintes elementos de dados não são copiados quando você copia uma instância de Human Resources:

- Endereços de email na tabela **LogisticsElectronicAddress**

- O histórico do trabalho em lotes nas tabelas **BatchJobHistory**, **BatchHistory** e **BatchConstraintHistory**

- A senha SMTP (Simple Mail Transfer Protocol) na tabela **SysEmailSMTPPassword**

- O servidor de retransmissão SMTP na tabela **SysEmailParameters**

- Configurações de gerenciamento de impressão nas tabelas **PrintMgmtSettings** e **PrintMgmtDocInstance**

- Registros específicos de ambiente nas tabelas **SysServerConfig**, **SysServerSessions**, **SysCorpNetPrinters**, **SysClientSessions**, **BatchServerConfig** e **BatchServerGroup** tables

- Os anexos de documento na tabela DocuValue. Esses anexos incluem todos modelos do Microsoft Office substituídos no ambiente de origem

- A sequência de conexão na tabela **PersonnelIntegrationConfiguration**

Alguns desses elementos não são copiados porque são específicos do ambiente. Exemplos incluem registros **BatchServerConfig** e **SysCorpNetPrinters**. Outros elementos não são copiados devido ao volume de tíquetes de suporte. Por exemplo:

- Os emails duplicados podem ser enviados porque o SMTP ainda está habilitado no ambiente de teste de aceitação do usuário (área restrita).

- Mensagens de integração inválidas podem ser enviadas porque os trabalhos em lotes ainda estão habilitados.

- Os usuários podem ser habilitados para que os administradores possam executar ações de limpeza após a atualização.

Além disso, os seguintes status são alterados ao copiar uma instância:

- Todos os usuários, exceto aqueles com a função de segurança "Administrador do Sistema", são definidos como **Desabilitado**.

- Todos os trabalhos em lotes, exceto para alguns trabalhos do sistema, são definidos como **Retenção**.

## <a name="environment-admin"></a>Administrador do ambiente

Todos os usuários no ambiente de área de proteção de destino, incluindo os administradores, são substituídos pelos usuários do ambiente de origem. Antes de copiar uma instância, verifique se você é um administrador no ambiente de origem. Se não for, não será possível entrar no ambiente de área restrita de destino após a conclusão da cópia.

Todos os usuários que não são administradores no ambiente de área de proteção de destino são desabilitados para evitar a entrada indesejada no ambiente de área restrita. Os administradores podem habilitar novamente os usuários, se necessário.

## <a name="apply-custom-fields-to-dataverse"></a>Aplicar campos personalizados ao Dataverse

Se você copiar uma instância no ambiente de área restrita e quiser integrar seu ambiente de área restrita com o Dataverse, reaplique campos personalizados a tabelas do Dataverse.

Para cada campo personalizado que é exposto em tabelas do Dataverse, siga estas etapas:

1. Acesse o campo personalizado e selecione **Editar**.

2. Desmarque o campo **Habilitado** para cada entidade cdm_* na qual o campo personalizado está habilitado.

3. Selecione **Aplicar Alterações**.

4. Selecione **Editar** novamente.

5. Marque o campo **Habilitado** para cada entidade cdm_* na qual o campo personalizado está habilitado.

6. Selecione **Aplicar Alterações** novamente.

O processo de cancelar a seleção, aplicar alterações, selecionar novamente e reaplicar alterações solicita que o esquema seja atualizado no Dataverse para incluir os campos personalizados.

Para obter mais informações sobre como criar campos personalizados, consulte [Criar e trabalhar com campos personalizados](../fin-ops-core/fin-ops/get-started/user-defined-fields.md).

## <a name="see-also"></a>Consulte também

[Provisionar o Human Resources](hr-admin-setup-provision.md)</br>
[Remover uma instância](hr-admin-setup-remove-instance.md)</br>
[Atualizar processo](hr-admin-setup-update-process.md)



[!INCLUDE[footer-include](../includes/footer-banner.md)]
