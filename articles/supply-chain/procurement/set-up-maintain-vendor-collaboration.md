---
title: Configurar e manter colaboração de fornecedor
description: Este artigo explica como configurar a colaboração do fornecedor no Dynamics 365 Supply Chain Management. Também explica como provisionar novos usuários de colaboração do fornecedor e gerenciar as funções de segurança para esses usuários.
author: GalynaFedorova
ms.date: 12/03/2018
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: DirExternalRole, SysUserRequestListPage, VendVendorPortalUsers, WorkflowTableListPageRnr
audience: Application User, Developer, IT Pro
ms.reviewer: kamaybac
ms.custom: 220774
ms.assetid: 69d05e8b-7dc2-48ea-bc24-bea9ac963579
ms.search.region: Global
ms.author: gfedorova
ms.search.validFrom: 2016-11-30
ms.dyn365.ops.version: Version 1611
ms.openlocfilehash: 8fe4731f8ff23f4abe25fce57a2325e1fca979c4
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/03/2022
ms.locfileid: "8890818"
---
# <a name="set-up-and-maintain-vendor-collaboration"></a>Configurar e manter colaboração de fornecedor

[!include [banner](../includes/banner.md)]

A interface de colaboração do fornecedor expõe um conjunto limitado de informações sobre ordens de compra, faturas e estoque de consignação para usuários de fornecedores externos. A partir dessa interface, um fornecedor também poderá responder a RFQs (solicitações de cotação) e exibir e editar informações básicas da empresa.

Este artigo explica como configurar a colaboração do fornecedor no Dynamics 365 Supply Chain Management. Também explica como configurar um fluxo de trabalho para provisionar novos usuários de colaboração do fornecedor e como gerenciar as funções de segurança para esses usuários.

> [!NOTE]
> As informações sobre a configuração de funções de segurança para colaboração do fornecedor aplicam-se somente à versão atual do aplicativo de finanças e operações. No Microsoft Dynamics AX 7.0. (fevereiro de 2016) e no aplicativo do Microsoft Dynamics AX versão 7.0.1 (maio de 2016), você colabora com fornecedores usando o módulo **Portal do fornecedor**. Para obter informações sobre permissões de usuário para o portal Fornecedor no Microsoft Dynamics AX, consulte [Segurança de usuário do portal Fornecedor](configure-security-vendor-portal-users.md).

## <a name="set-up-vendor-collaboration-security-roles"></a>Configurar funções de segurança de colaboração do fornecedor

Um profissional de compras ou um fornecedor com permissões suficientes pode solicitar que uma pessoa de contato seja provisionada como um usuário habilitando **Provisionar usuário fornecedor** no registro de pessoa de contato. Durante o processo de provisionamento, as permissões de usuário são selecionadas para o novo usuário externo e a solicitação de novo usuário fornecedor é enviada. É importante configurar corretamente as permissões de usuário que estão disponíveis para seleção na solicitação de usuário fornecedor. Caso contrário, os fornecedores poderão receber acesso a informações para as quais não devem ter acesso no Supply Chain Management.

### <a name="set-up-the-security-roles-that-are-available-for-selection-when-a-new-user-request-is-used-for-a-contact-person"></a>Configurar as funções de segurança disponíveis para seleção quando uma nova solicitação de usuário for usada para uma pessoa de contato

1. Selecione **Administração do sistema** &gt; **Segurança** &gt; **Funções externas**.
2. Selecione **Novo** e, em seguida, selecione uma função de segurança e a função de participante **Fornecedor**.

Talvez você queira adicionar as funções **Administrador do fornecedor (externo)** e **Fornecedor (externo)**, fornecidas no Supply Chain Management. Como alternativa, você poderá usar as funções de segurança criadas por sua empresa.

Você só deverá tornar a função **Administrador do fornecedor (externo)** disponível se os fornecedores puderem criar novos contatos, enviar solicitações de usuário de colaboração do fornecedor para novos usuários e alterações nas informações do usuário e manipular essas solicitações por meio de um fluxo de trabalho.

Se planejar configurar manualmente os contatos e usuários do fornecedor, você poderá tornar somente a função **Fornecedor (externo)** disponível. Essa função será a única função que poderá ser solicitada por meio de uma solicitação de usuário fornecedor.

> [!NOTE]
> A função **SystemUser** é concedida automaticamente quando você cria manualmente uma conta de usuário. Portanto, você deve remover essa função e atribuir a função **SystemExternalUser**. Se novas contas de usuário forem criadas por meio do fluxo de trabalho que é iniciado por uma solicitação de usuário fornecedor para provisionar um novo usuário, uma ou mais funções que você configurou para a colaboração do fornecedor e a função **SystemExternalUser** serão atribuídas.

#### <a name="vendor-admin-external-security-role"></a>Função de segurança Administrador do fornecedor (externo)

A função **Administrador do fornecedor (externo)** pode ser usada para fornecedores externos que mantêm informações de contato do fornecedor e fazer solicitações para provisionar novos usuários de colaboração do fornecedor. Os usuários externos com essa função de segurança podem executar as seguintes tarefas:

- Exiba e modifique informações sobre pessoas de contato, como o cargo da pessoa, o endereço de email e o número de telefone.
- Adicione uma pessoa de contato nova ou existente às contas de fornecedor.
- Exclua qualquer pessoa de contato que tenha sido criada.
- Ative ou desative a associação entre uma pessoa de contato e uma conta de fornecedor. Depois que a associação entre uma pessoa de contato e uma conta de fornecedor for desativada, a pessoa de contato não poderá ser mencionada em novas ordens de compra ou em outros documentos.
- Negue ou permita o acesso de uma pessoa de contato aos documentos na interface de colaboração do fornecedor específico da conta do fornecedor. Depois que a associação entre uma pessoa de contato e uma conta de fornecedor for desativada, o acesso a documentos específicos à conta de fornecedor sempre será negado.
- Solicitar uma nova conta de usuário para uma pessoa de contato usando a ação **Provisionar usuário**.
- Solicite que a conta de usuário da pessoa de contato seja desativada.
- Solicite que a conta de usuário de uma pessoa de contato seja modificada para adicionar ou remover funções de segurança.
- Exiba RFQs.

#### <a name="vendor-external-security-role"></a>Função de segurança Fornecedor (externo)

A função **Fornecedor (externo)** pode ser usada para fornecedores externos que trabalharão com ordens de compra. Os usuários externos com essa função de segurança podem executar as seguintes tarefas:

- Responda e exiba informações sobre ordens de compra.
- Mantenha faturas de colaboração do fornecedor.
- Exiba o estoque em consignação.
- Exiba e responda a RFQs.
- Exiba informações de fornecedor.

## <a name="set-up-security-roles-that-are-used-when-prospective-vendors-are-onboarded"></a>Configurar as funções de segurança usadas quando fornecedores potenciais são integrados

Para fornecedores integrados que são iniciados por meio de uma solicitação de registro de fornecedor potencial, você deve configurar uma função de segurança externa. Essa função será atribuída a novos usuários durante o processo de provisionamento que é controlado pelo fluxo de trabalho do tipo **Fluxo de trabalho de solicitação de usuário (plataforma)**. Para obter mais informações, consulte a seção [Configurar fluxos de trabalho para processar solicitações de usuário de colaboração do fornecedor](#set-up-workflows-to-process-vendor-collaboration-user-requests) posteriormente neste artigo.

Para obter informações sobre como integrar fornecedores potenciais, consulte [Integrar fornecedores](vendor-onboarding.md).

### <a name="set-up-a-security-role-that-is-used-when-a-new-prospective-vendor-user-request-is-submitted"></a>Configurar uma função de segurança que é usada quando uma nova solicitação de usuário fornecedor potencial é enviada

1. Selecione **Administração do sistema** > **Segurança** > **Funções externas**.
2. Selecione **Novo** e, em seguida, selecione uma função de segurança e a função de participante **Fornecedor potencial**.

Você deve adicionar a função **Cliente potencial (externo)** fornecida no Supply Chain Management.

A função de segurança só concederá acesso ao assistente de registro de novo fornecedor.

## <a name="set-up-workflows-to-process-vendor-collaboration-user-requests"></a>Configurar fluxos de trabalho para processar solicitações de usuário de colaboração do fornecedor

Para ajudar a garantir que todas as tarefas relevantes foram concluídas e que as aprovações apropriadas são dadas, você deve configurar os fluxos de trabalho para manipular solicitações de usuário de colaboração do fornecedor.

As solicitações de usuário de colaboração do fornecedor são enviadas por fornecedores externos que têm a função de segurança **Administrador do fornecedor (externo)** ou permissões semelhantes ou por profissionais de compras em sua empresa. Eles também podem ser gerados de solicitações de registro de fornecedor potencial durante o processo de integração do fornecedor.

Existem três tipos de solicitações:

- Solicitações para provisionar um novo usuário
- Solicitações para desativar um usuário existente
- Solicitações para modificar as funções de segurança de um usuário existente

Para obter mais informações sobre solicitações de usuário de colaboração do fornecedor, consulte [Gerenciar usuários de colaboração do fornecedor](manage-vendor-collaboration-users.md).

Você deve criar dois ou mais fluxos de trabalho para processar os três tipos de solicitações de colaboração do fornecedor. Os novos fluxos de trabalho são criados na página **Fluxos de trabalho de usuário**.

### <a name="example-of-a-workflow-for-provisioning-new-users-and-modifying-security-roles"></a>Exemplo de um fluxo de trabalho para provisionamento de novos usuários e modificação de funções de segurança

Para lidar com solicitações de usuário fornecedor para criar novos usuários e modificar funções de segurança, você poderá colocar uma condição de ramificação no início do fluxo de trabalho. Dessa forma, uma ramificação diferente do fluxo de trabalho será usada, dependendo do fato de a solicitação ser criar um novo usuário ou modificar um usuário existente.

Para configurar essa ramificação, crie um novo fluxo de trabalho do tipo **Fluxo de Trabalho de Solicitação de Usuário (Plataforma)**. As ramificações desse fluxo de trabalho podem conter os elementos a seguir.

#### <a name="branch-to-provision-new-users"></a>Ramificação para provisionar novos usuários

1. Atribua uma tarefa de aprovação à pessoa responsável pela aprovação de que novos usuários devem ter acesso a informações de colaboração do fornecedor.
2. Atribua uma tarefa à pessoa responsável por solicitar novas contas de usuário do Microsoft Azure Active Directory (Azure AD) no portal do Azure. Use a tarefa predefinida **Enviar convite de usuário B2B do Azure** para esta etapa. Os usuários B2B podem ser exportados automaticamente para o Azure AD. Use o **Provisionar usuário B2B do Azure AD** predefinido. Para obter mais informações, consulte [Exportar usuários B2B para o Azure AD](../../fin-ops-core/dev-itpro/sysadmin/implement-b2b.md).
3. Atribua uma tarefa de aprovação à pessoa que carrega no Azure. Se uma conta não for criada com êxito, essa pessoa rejeitará a tarefa e terminará o fluxo de trabalho. Essa tarefa de aprovação poderá ser ignorada se você tiver incluído a etapa que exporta automaticamente novas contas de usuário para o Azure por meio da API (interface de programação de aplicativo) B2B.
4. Adicione uma tarefa automatizada que provisione um novo usuário. Use a tarefa predefinida **Usuário de provisão automatizado** para esta etapa.
5. Adicione uma tarefa que notifique o novo usuário. Talvez você queira enviar ao novo usuário um email de boas-vindas que inclua uma URL para o Supply Chain Management. Este email pode usar um modelo que você cria na página **Mensagens de email** e, em seguida, seleciona na página **Parâmetros do fluxo de trabalho do usuário**. O modelo pode incluir a marca **%portalURL%**. Quando o email de boas-vindas for gerado, essa marca que será substituída pela URL do locatário do Supply Chain Management.

    > [!NOTE]
    > Esse fluxo de trabalho pode ser usado em vários cenários que envolvam integração com o usuário. Por exemplo, ele poderá ser usado quando fornecedores potenciais ou pessoas de contato exigirem uma conta de colaboração do fornecedor. Portanto, você deve formular o email como uma instrução geral que possa ser usada para várias finalidades.

#### <a name="branch-to-modify-security-roles"></a>Ramificação para modificar funções de segurança

1. Atribua uma tarefa de aprovação à pessoa responsável por aprovar alterações em funções de segurança.
2. Adicione uma tarefa automatizada que adicione ou remova as funções de segurança relevantes. Use a tarefa **Usuário de provisão automatizado** para esta etapa.

### <a name="example-of-a-workflow-for-inactivating-a-user"></a>Exemplo de fluxo de trabalho para a desativação de um usuário

Crie um fluxo de trabalho do tipo **Desativar plataforma de fluxo de trabalho de solicitação de usuário** e adicione as tarefas a seguir.

1. Atribua uma tarefa de aprovação à pessoa responsável por aceitar solicitações para desativar usuários. Você pode adicionar condições para automatizar essa etapa de aprovação.
2. Adicione uma tarefa automatizada que desative o usuário. Use a tarefa **Desativação de usuário automatizada** para esta etapa.
3. Adicione as tarefas de limpeza necessárias. Por exemplo, você pode adicionar uma tarefa que remova a conta de seu diretório no portal do Azure.

## <a name="enable-vendor-collaboration-for-a-specific-vendor"></a>Habilitar colaboração do fornecedor para um fornecedor específico

Antes de criar uma conta de usuário para alguém que usará a colaboração do fornecedor, você deverá configurar o fornecedor para que ele possa usar a colaboração do fornecedor. Na página **Fornecedores**, na guia **Geral**, defina o campo **Ativação de colaboração**. As opções a seguir estão disponíveis:

- **Ativo (a OC é confirmada automaticamente)** – as ordens de compra são confirmadas automaticamente quando o fornecedor as aceita sem solicitar alterações.
- **Ativo (a OC não é confirmada automaticamente)** – sua organização deve confirmar manualmente as ordens de compra depois que o fornecedor as tiver aceitado.

> [!NOTE]
> Os profissionais de compras da sua empresa também podem concluir essa tarefa.

## <a name="troubleshoot-the-provisioning-of-new-vendor-collaboration-users"></a>Solucionar problemas do provisionamento de novos usuários de colaboração do fornecedor

Os novos usuários de colaboração do fornecedor são provisionados por meio do fluxo de trabalho configurado para processar solicitações de usuário de colaboração do fornecedor do tipo **Provisionar o usuário fornecedor**.

Se o endereço de email de um novo usuário de colaboração do fornecedor pertencer a um domínio registrado no Azure como um locatário (ou seja, se for uma conta de domínio gerenciado), o endereço de email deverá ser uma conta do Azure AD existente. Caso contrário, o processo de provisionamento não poderá ser concluído.

Para obter mais informações sobre o processo usado na tarefa **Enviar convite para usuário B2B do Azure** no fluxo de trabalho para gerenciamento de contas do Azure AD, consulte [Colaboração B2B do Azure Active Directory](/azure/active-directory/external-identities/what-is-b2b).

## <a name="additional-resources"></a>Recursos adicionais

[Colaboração de fornecedores com fornecedores externos](vendor-collaboration-work-external-vendors.md)

Assista a um vídeo curto no processo de integração do fornecedor: [Integrar um novo fornecedor](https://www.youtube.com/watch?v=0KUc3AGaTKk&feature=youtu.be)


[!INCLUDE[footer-include](../../includes/footer-banner.md)]
