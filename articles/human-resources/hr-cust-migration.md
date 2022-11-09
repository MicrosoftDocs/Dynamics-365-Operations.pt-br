---
title: Migração do cliente do Dynamics 365 Human Resources para a infraestrutura de finanças e operações
description: Este artigo descreve a migração do cliente do Microsoft Dynamics 365 Human Resources para a infraestrutura de finanças e operações.
author: twheeloc
ms.date: 10/25/2022
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.custom: 7521
ms.assetid: ''
ms.search.region: Global
ms.author: twheeloc
ms.search.validFrom: 2020-10-13
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: 63b08a8493702cf319aa078ef6aa787e2094be87
ms.sourcegitcommit: 088a7b5eb9a3b68710dfe012abf4c24776978750
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/01/2022
ms.locfileid: "9733430"
---
# <a name="dynamics-365-human-resources-customer-migration"></a>Migração do cliente do Dynamics 365 Human Resources

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]
[!include [preview banner](../includes/preview-banner.md)]

A migração do cliente é uma "migração lift-and-shift" (movimento) de um banco de dados de cliente para a infraestrutura de finanças e operações. A ferramenta de migração automatizada é usada para isso. O resultado é um novo ambiente de finanças e operações que usa o banco de dados do Human Resources do cliente.

## <a name="prerequisites"></a>Pré-requisitos

### <a name="user-access-and-permissions"></a>Acesso e permissões do usuário

- O usuário do Lifecycle Services do Microsoft Dynamics deve ter a função de **Administrador da organização**.
- O usuário deve ser capaz de [criar projetos do Azure DevOps](/azure/devops/organizations/projects/create-project) ou usar um projeto do Azure DevOps existente.
- O usuário deve ter acesso para [criar um Token de Segurança de Acesso Pessoal do Azure DevOps](/azure/devops/organizations/accounts/use-personal-access-tokens-to-authenticate), ou deve ter um token disponível para uso.

### <a name="dataverse-environment-backup-sandbox"></a>Backup do ambiente do Dataverse (Área restrita)

1. Opcional, mas recomendado: Atualize o ambiente de área restrita do Human Resources existente usando uma cópia do ambiente de produção do Human Resources.
2. [Criar um novo ambiente do Dataverse](/power-platform/admin/create-environment#create-an-environment-with-a-database) usando o centro de administração do Power Platform.

    > [!NOTE]
    > Ao adicionar um banco de dados, verifique se a opção **Habilitar aplicativos do Dynamics 365** está definida como **Sim**.

3. [Copie o ambiente do Dataverse existente](/power-platform/admin/copy-environment), que é vinculado ao aplicativo autônomo do Human Resources, para o ambiente que você criou na etapa anterior.

### <a name="dataverse-capacity"></a>Capacidade do Dataverse

1. Use a página **Resumo** no centro de administração do Power Platform para verificar se o [armazenamento do Dataverse](/power-platform/admin/finance-operations-storage-capacity) tem capacidade disponível suficiente para a cópia do ambiente.
2. Se não houver capacidade disponível suficiente, use a [orientação para liberar espaço de armazenamento](/power-platform/admin/free-storage-space) para reduzir o consumo geral. Os clientes também podem [adicionar capacidade de armazenamento adicional](/power-platform/admin/add-storage).

## <a name="customer-migration-process"></a>Processo de migração de clientes

### <a name="create-a-lifecycle-services-project-for-human-resources-migration"></a>Criar um projeto do Lifecycle Services para migração do Human Resources

A primeira etapa é criar um novo projeto de Implementação de finanças e operações nos Lifecycle Services. O cliente terá um projeto do Lifecycle Services do Human Resources. Os ambientes do Human Resources existentes serão migrados para o novo projeto de Implementação de finanças e operações.

Para criar um novo projeto, siga estas etapas.

1. Entre no Lifecycle Services como administrador global ou usuário de conta de serviço designado.
2. Na home page do Lifecycle Services, selecione **Criar/novo (+)**.
3. Selecione os aplicativos de finanças e operações como o produto.
4. No campo **Finalidade do projeto**, selecione **Implementação**.
5. Inserir um nome e uma descrição do projeto.
6. No campo **Tipo de personalização do projeto**, selecione **migração do Microsoft Dynamics 365 Human Resources**.
7. Marque a caixa de seleção para concordar com os termos e condições.
8. Selecione **Criar**.

Depois de criar um novo projeto do Lifecycle Services, siga estas etapas para configurá-lo.

1. Selecione **Integração do projeto** para concluir a integração do projeto. Para obter mais informações, consulte [Integração do projeto](../fin-ops-core/dev-itpro/lifecycle-services/project-onboarding.md).

    - Selecione a mesma região que os ambientes atuais. Esta seleção não afetará a migração.
    - Para sistemas herdados, selecione **Outro**.

2. Concluir as configurações do projeto. Como parte dessa etapa, você deve configurar a biblioteca Online do SharePoint, conexões do Azure DevOps e do Azure, se forem necessárias. Para obter mais informações, consulte [Guia do usuário do Lifecycle Services (LCS)](../dev-itpro/lifecycle-services/lcs-user-guide.md).

> [!NOTE]
> Os clientes podem usar um projeto existente do Azure DevOps e o Token de Segurança de Acesso Pessoal associado. Se um projeto existente for usado, as configurações relacionadas ao projeto estarão disponíveis automaticamente e podem ser revisadas para obter precisão.

### <a name="migrate-a-human-resources-sandbox-environment"></a>Migrar um ambiente de área restrita do Human Resources

#### <a name="prepare-to-migrate-the-sandbox-environment"></a>Preparar-se para migrar o ambiente de área restrita

Depois que um novo projeto do Lifecycle Services for criado, e o processo de integração do projeto tiver sido concluído, você estará pronto para migrar seu primeiro ambiente. Antes de iniciar esse processo, recomendamos que você atualize o ambiente de área restrita que deseja migrar do ambiente de produção na infraestrutura autônoma.

#### <a name="prepare-a-power-platform-environment"></a>Preparar um ambiente do Power Platform

> [!NOTE]
> Esta etapa só se aplica a migração de ambiente de área restrita. Quando você migra o ambiente de produção, o ambiente do centro de administração existente do Power Platform anexado ao ambiente de produção será postergado.

- No Centro de administração do Power Platform, [crie um ambiente do Power platform](/power-platform/admin/create-environment#create-an-environment-in-the-power-platform-admin-center) para usar na migração de área restrita ou selecione um ambiente existente.
- [Copie um ambiente](/power-platform/admin/copy-environment) para atualizar o ambiente do Power Platform usado para mapeamento.

#### <a name="migrate-the-sandbox-environment"></a>Migrar o ambiente de área restrita

1. Entre no Lifecycle Services como administrador global ou usuário de conta de serviço designado.

    > [!NOTE]
    > Recomendamos usar uma conta de usuário nomeada. O usuário conectado deve ter a função de segurança **Proprietário do projeto** ou **Gerente de ambiente** no projeto autônomo do Lifecycle Services do Human Resources.

2. Abra o projeto de migração de Human Resources recém-criado.
3. Analise e complete as fases apropriadas da metodologia de migração e o integração de projetos.
4. No painel de projeto, no painel **Padrão: teste de aceitação padrão**, selecione **Migrar HR**.
5. No painel **Selecione o ambiente para fazer a migração**, selecione o projeto Lifecycle Services apropriado e o ambiente Human Resources de origem (do aplicativo autônomo de origem Human Resources).
6. Habilite **Mapear para novo ambiente do Power Platform** e selecione o ambiente do Power Platform apropriado. Selecione **Avançar**.
7. Conclua o assistente de **Configurações de implantação (finanças e operações - área restrita)** para confirmar os detalhes e aprovação do cliente, e em seguida, selecione **Implantar**.

O estado do ambiente mostrará o andamento. O estado será alterado de **Carregamento** para **Implantação** para **Implantado**.

> [!NOTE]
> O painel de produção não estará disponível até a lista de verificação de preparação do projeto ao vivo ser concluída. Para obter mais informações, consulte [Preparar para ativação](../fin-ops-core/fin-ops/imp-lifecycle/prepare-go-live.md).

#### <a name="considerations-and-assumptions"></a>Considerações e suposições

Existe um ambiente de área restrita de Human Resources em um projeto do Lifecycle Services no locatário que possui as seguintes características:

- O ambiente de área restrita do Human Resources não está vinculado a um ambiente mesclado existente. Somente uma migração de cada vez pode estar em andamento para um determinado ambiente do Human Resources.
- O número de ambientes de área restrita permitido por vez é baseado no licenciamento do Human Resources. Se o licenciamento suficiente tiver sido adquirido para o locatário, ambientes de área restrita adicionais serão listados no painel **Ambientes** do projeto.
- As migrações devem ser feitas para ambientes do mesmo tipo. Em outras palavras, podem ser feitas migrações de área restrita a área restrita ou de produção para produção.

    > [!NOTE]
    > Somente os tipos de ambiente do Human Resources são considerados quando o status de produção ou de área restrita é determinado. Se os ambientes forem categorizados incorretamente (ou seja, um ambiente de produção for marcado como um ambiente de área restrita ou um ambiente de área restrita for marcado como um ambiente de produção), contate o Suporte.

- Se a migração não for bem-sucedida, uma mensagem de erro de falha será mostrada e um botão **Excluir** ficará disponível. Use este botão para excluir a migração que falhou. Em seguida, você poderá migrar novamente o ambiente.

#### <a name="validate-the-sandbox-migration"></a>Validar a migração de área restrita

Depois que o processo de migração de área restrita for concluído com êxito, crie um plano de testes detalhado para verificar e aprovar todos os processos de negócios.

Antes de começar a testar, valide os seguintes detalhes:

- Confirme se o ambiente migrado está acessível na URL gerada.
- Confirme se os usuários podem acessar a área restrita migrada.
- Confirme se o ambiente do Dataverse associado ao ambiente de área restrita migrado está acessível.
- Verifique dados diferentes para confirmar se os dados mais atualizados estão disponíveis.
- Conclua os processos comerciais críticos para validação.
- Confirme se as políticas de segurança são aplicáveis.
- Confirme se os trabalhos em lotes foram disparados como esperado.

Você não terá acesso da Área de Trabalho Remota à área restrita da migração. Você pode usar recursos e ferramentas de autoatendimento para executar as seguintes ações para os ambientes de nível 2 + área restrita:

- Acesse o [banco de dados SQL do Azure](../fin-ops-core/dev-itpro/deployment/deploymentfaq.md#access-the-azure-sql-database).
- Acesse [arquivos de log](../fin-ops-core/dev-itpro/deployment/deploymentfaq.md#access-log-files).
- Use [ferramentas perfmon](../fin-ops-core/dev-itpro/deployment/deploymentfaq.md#use-perfmon-tools).
- [Ative/desative o modo de manutenção](../fin-ops-core/dev-itpro/deployment/deploymentfaq.md#access-self-service-logs).
- Reiniciar [serviços](../fin-ops-core/dev-itpro/deployment/deploymentfaq.md#restart-services).
- Configure a [Regression suite automation tool](../fin-ops-core/dev-itpro/deployment/deploymentfaq.md#configure-the-regression-suite-automation-tool).

Para obter mais informações, consulte [Pergunta frequente para implantação do autoatendimento](../fin-ops-core/dev-itpro/deployment/deploymentfaq.md).

### <a name="migrate-a-human-resources-production-environment"></a>Migrar um ambiente de produção do Human Resources

Depois de concluir a migração e a validação de um ambiente de área restrita, siga estas etapas para migrar o ambiente de produção.

#### <a name="prerequisites"></a>Pré-requisitos

- O avaliador de Assinatura deve ser concluído.
- A [avaliação de preparação](../fin-ops-core/fin-ops/imp-lifecycle/prepare-go-live.md) de Ativação deve ser concluída.

#### <a name="migrate-the-production-environment"></a>Migração o ambiente de produção

1. Entre no Lifecycle Services como administrador global ou usuário de conta de serviço designado.

    > [!NOTE]
    > Recomendamos usar uma conta de usuário nomeada. O usuário conectado deve ter a função de segurança **Proprietário do projeto** ou **Gerente de ambiente** no projeto do Lifecycle Services.

2. Abra o novo projeto de migração de Human Resources.
3. Analise e complete as fases apropriadas da metodologia de migração e o integração de projetos.
4. No painel de projeto, no painel **Produção**, selecione **Migrar HR**.
5. No painel **Selecione o ambiente para fazer a migração**, selecione o projeto Lifecycle Services apropriado e o ambiente Human Resources de origem (do aplicativo autônomo de origem Human Resources). Selecione **Avançar**.
6. Conclua o assistente de **Configurações de implantação (finanças e operações - área restrita)** para confirmar os detalhes e aprovação do cliente, e em seguida, selecione **Implantar**.

O estado do ambiente mostrará o andamento da implantação. O estado será alterado de **Carregamento** para **Implantação** para **Implantado**.

#### <a name="post-migration-considerations"></a>Considerações pós-migração

- Aplique as [atualizações de qualidade](/fin-ops-core/fin-ops/get-started/quality-updates) mais recentes para seus ambientes.
- Se você estiver usando [tabelas virtuais](hr-admin-integration-common-data-service-virtual-entities.md), reconfigure os pontos de extremidade.
- Reconfigure a integração de gravação dupla. Avalie quais entidades devem ser habilitadas.
- Considere o uso de tabelas virtuais para substituir a gravação dupla para integração.

#### <a name="dual-write-integration"></a>Integração da gravação dupla

##### <a name="set-up-microsoft-power-platform-dual-write-integration"></a>Configure a integração de gravação dupla do Microsoft Power Platform

1. Vá para o centro de administração do Power Platform e selecione **Ambientes** na navegação esquerda.
2. Selecione o ambiente copiado/atualizado anteriormente e confirme se o estado é **Pronto**.
3. Vá para Lifecycle Services e confirme se o status do projeto de migração é **Implantado**.
4. No ambiente migrado, selecione **Detalhes completo** para rever detalhes adicionais e [configurar um aplicativo de gravação dupla](../fin-ops-core/dev-itpro/data-entities/dual-write/lcs-setup.md#set-up-dual-write-for-new-or-existing-dataverse-environments).
5. No painel **Configuração do aplicativo de gravação dupla**, marque a caixa de seleção para concordar em mapear e sincronizar dados entre bancos de dados e selecione **Configurar**.
6. Quando uma caixa de mensagem notifica sobre a configuração de gravação dupla bem-sucedida, selecione **OK**.
7. Você pode monitorar o andamento da configuração nos detalhes.
8. Quando a configuração estiver concluída, selecione **Vincular ao ambiente do Power Platform** para sincronizar as entidades de dados disponíveis.
9. Quando o status indicar que os ambientes foram vinculados com êxito, vá para o centro de administração do Power Platform para revisar e selecionar as entidades de dados apropriadas.
10. No painel esquerdo, selecione **Aplicativos do Dynamics 365 \> Recursos**.
11. Confirme se o status do aplicativo Human Resources de gravação dupla está **Habilitado**.
12. Selecione o aplicativo Human Resources de gravação dupla e, em seguida, selecione **Instalar**.
13. No painel **Instalar aplicativo Dynamics 365 Human Resources de gravação dupla**, selecione o ambiente apropriado no qual será instalado o pacote.
14. Marque a caixa de seleção para concordar com os termos de serviço e selecione **Instalar**.
15. No ambiente do aplicativo Dynamics 365, o status será **Em instalação**, enquanto a instalação estiver em andamento. Ele será atualizado para **Instalado** quando a instalação for concluída.

##### <a name="review-and-apply-a-dual-write-solution"></a>Revisar e aplicar uma solução de gravação dupla

1. No novo ambiente de finanças e operações, vá para **Gerenciamento de dados \> Gravação dupla**.
2. Selecione **Aplicar solução**.
3. No painel, selecione **Soluções instaladas do Dynamics**, **Mapas de entidade de núcleo de aplicativos com gravação dupla** e **Mapas do Dynamics 365 Human Resources**. Em seguida, selecione **Aplicar**. Uma mensagem confirma que a solução está sendo aplicada. Depois que a solução for aplicada com êxito, todos os mapas de tabela disponíveis serão exibidos.
4. Revise os mapas de tabela disponíveis para selecionar e executar a integração usando a gravação dupla.
5. Ao executar a integração de gravação dupla pela primeira vez para mapas de tabela, marque a caixa de seleção **Sincronização inicial**. Se houver uma integração existente do ambiente do Human Resources de origem, você não precisará marcar a caixa de seleção **Sincronização inicial** ao executar a integração para mapas de tabela.

#### <a name="recommended-practices"></a>Práticas recomendadas

Esta seção descreve as recomendações para a migração da infraestrutura autônoma para a infraestrutura de finanças e operações.

- É altamente recomendável que você trabalhe com seu parceiro da Microsoft Dynamics para obter ajuda na migração do seu ambiente do Human Resources.
- Planeje o tempo apropriado para fazer UAT (teste de aceitação total do usuário) no ambiente de migração de área restrita.
- Planeje e documente as etapas detalhadas para migrar as integrações para o ambiente migrado.
- Crie uma lista de verificação detalhada para descrever o processo de transferência para a migração.
- Planeje uma quantidade de tempo de inatividade adequada para seu negócio enquanto executa a migração.
- É altamente recomendável que os clientes do FastTrack trabalhem com seu arquiteto de soluções FastTrack para obter ajuda na supervisão do processo de migração.
- É altamente recomendável que você atualize seu ambiente de área restrita na infraestrutura autônoma antes de fazer a primeira migração. Essa atualização deve incluir seu ambiente do Dataverse conectado ao ambiente de área restrita ao qual você você pretende migrar.
- É altamente recomendável usar uma conta de serviço ao implantar, migrar e criar seu projeto do Lifecycle Services.
- Planeje a atualização do ambiente de área restrita para a validação do UAT na versão de disponibilidade geral mais recente (GA). Para obter mais informações, consulte [considerações](hr-infrastructure-merge.md#considerations).
