---
title: Copiar uma instância
description: É possível usar o Microsoft Dynamics Lifecycle Services (LCS) para copiar um banco de dados do Microsoft Dynamics 365 Human Resources para um ambiente de área restrita.
author: andreabichsel
manager: AnnBe
ms.date: 02/03/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-human-resources
ms.technology: ''
ms.search.form: SystemAdministrationWorkspaceForm
audience: Application User
ms.reviewer: anbichse
ms.search.scope: Human Resources
ms.custom: 7521
ms.assetid: ''
ms.search.region: Global
ms.author: anbichse
ms.search.validFrom: 2020-02-03
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: e8385b7dfcd1d7294542c7f54f609b26b7988ac4
ms.sourcegitcommit: ba340f836e472f13f263dec46a49847c788fca44
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/04/2020
ms.locfileid: "3431236"
---
# <a name="copy-an-instance"></a>Copiar uma instância

É possível usar o Microsoft Dynamics Lifecycle Services (LCS) para copiar um banco de dados do Microsoft Dynamics 365 Human Resources para um ambiente de área restrita. Se houver outro ambiente de área restrita, você também poderá copiar o banco de dados daquele ambiente para um ambiente de área restrita direcionado.

Para copiar uma instância, é necessário garantir o seguinte:

- A instância de Human Resources que deseja substituir deve ser um ambiente de área restrita.

- Os ambientes dos quais você está copiando e devem estar na mesma região. Não é possível copiar entre regiões.

- Você deve ser um administrador no ambiente de destino para que possa fazer login nele depois de copiar a instância.

- Ao copiar o banco de dados de Human Resources, você não copia os elementos (aplicativos ou dados) contidos em um ambiente do Microsoft PowerApps. Para obter informações sobre como copiar elementos em um ambiente do PowerApps, consulte [Copiar um ambiente](https://docs.microsoft.com/power-platform/admin/copy-environment). A ambiente do PowerApps que deseja substituir deve ser um ambiente de área restrita. Você deve ser um administrador de locatário global para alterar um ambiente de produção do PowerApps para um ambiente de área restrita. Para obter mais informações sobre como alterar um ambiente do PowerApps, consulte [Alternar uma instância](https://docs.microsoft.com/dynamics365/admin/switch-instance).

## <a name="effects-of-copying-a-human-resources-database"></a>Efeitos da cópia de um banco de dados do Human Resources

Os seguintes eventos ocorrem ao copiar um banco de dados do Human Resources:

- O processo de cópia apaga o banco de dados existente no ambiente de destino. Depois que o processo de cópia for concluído, não será possível recuperar o banco de dados existente.

- O ambiente de destino não estará disponível até que o processo de cópia seja concluído.

- Os documentos do armazenamento em Microsoft Azure Blob não são copiados de um ambiente para outro. Portanto, quaisquer documentos e modelos anexados não serão copiados e permanecerão no ambiente de origem.

- Todos usuários, exceto o usuário Administrador e outras contas de usuário de serviço internas estarão indisponíveis. Portanto, o usuário administrador pode excluir ou ofuscar dados antes que outros usuários tenham permissão de volta para o sistema.

- O usuário administrador deve fazer as alterações de configuração necessárias, como reconectar empresas de integração a serviços ou URLs específicos.

## <a name="copy-the-human-resources-database"></a>Copiar o banco de dados do Human Resources

Para concluir essa tarefa, primeiro copie uma instância e efetue login na central de administração do Microsoft Power Platform para copiar seu ambiente do PowerApps.

> [!WARNING]
> Quando você copia uma instância, o banco de dados é apagado na instância de destino. A instância de destino não está disponível durante esse processo.

1. Faça login nas LCS e selecione o projeto LCS que contém a instância que você deseja copiar.

2. Em seu projeto LCS, selecione o bloco **Gerenciamento do Aplicativo de Human Resources**.

3. Selecione a instância a ser copiada e selecione **Copiar**.

4. No painel de tarefas **Copiar uma instância**, selecione a instância a ser substituída e, em seguida, selecione **Copiar**. Aguarde o valor do campo **Copiar status** ser atualizado para **Concluído**.

   ![[Selecione a instância a ser substituída](./media/copy-instance-select-target-instance.png)](./media/copy-instance-select-target-instance.png)

5. Selecione **Power Platform**, e entre na central de administração do Microsoft Power Platform.

   ![[Selecione Power Platform](./media/copy-instance-select-power-platform.png)](./media/copy-instance-select-power-platform.png)

6. Selecione o ambiente do PowerApps a ser copiada e selecione **Copiar**.

7. Quando o processo de cópia for concluído, efetue login na instância de destino e habilite a integração do Common Data Service. Para saber mais informações e instruções, consulte [Configurar a integração do Common Data Service](https://docs.microsoft.com/dynamics365/talent/hr-common-data-service-integration).

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

Alguns desses elementos não são copiados porque são específicos do ambiente. Exemplos incluem registros **BatchServerConfig** e **SysCorpNetPrinters**. Outros elementos não são copiados devido ao volume de tíquetes de suporte. Por exemplo, os emails duplicados podem ser enviados porque o SMTP ainda está habilitado no ambiente de teste de aceitação do usuário (Sandbox), as mensagens de integração inválidas podem ser enviadas porque os trabalhos em lotes ainda estão habilitados e os usuários podem estar habilitados para que os administradores possam realizar ações de limpeza após a renovação.

Além disso, os seguintes status são alterados ao copiar uma instância:

- Todos os usuários, exceto o administrador, estão definidos como **Desabilitados**.

- Todos os trabalhos em lotes, exceto para alguns trabalhos do sistema, são definidos como **Retenção**.

## <a name="environment-admin"></a>Administrador do ambiente

Todos os usuários no ambiente de área de proteção de destino, incluindo os administradores, são substituídos pelos usuários do ambiente de origem. Antes de copiar uma instância, verifique se você é um administrador no ambiente de destino. Se não estiver, não será possível fazer logon no ambiente de área de proteção de destino após a conclusão da cópia.

Todos os usuários que não são administradores no ambiente de área de proteção de destino são desabilitados para evitar a entrada indesejada no ambiente de área restrita. Os administradores podem habilitar novamente os usuários, se necessário.
