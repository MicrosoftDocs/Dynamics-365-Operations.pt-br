---
title: Provisionar o Human Resources na infraestrutura do aplicativo de finanças e operações
description: Este artigo explica o processo de provisionamento de um novo ambiente de produção para o Microsoft Dynamics 365 Human Resources na infraestrutura do aplicativo de finanças e operações.
author: twheeloc
ms.date: 01/07/2022
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
ms.openlocfilehash: 2fd8176d16178ecc4ba667e5937f2cec2e0af2c3
ms.sourcegitcommit: bd3b55e1af28e592c97b540de1e87cd8ba9c35a8
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/03/2022
ms.locfileid: "9221581"
---
# <a name="provision-human-resources-in-the-finance-and-operations-infrastructure"></a>Provisionar o Human Resources na infraestrutura do aplicativo de finanças e operações

_**Aplica-se a:** Human Resources na infraestrutura do aplicativo de finanças e operações_ 

> [!NOTE]
> A partir de 2022 de julho, novos ambientes do Human Resources não podem ser provisionados na infraestrutura autônoma do Human Resources, e novos projetos do Lifecycle Services (LCS) do Microsoft Dynamics não podem ser criados nele. Os clientes podem implantar ambientes de Recursos Humanos na infraestrutura de aplicativos de finanças e operações.

Este artigo explica o processo de provisionamento de um novo ambiente de produção para o Microsoft Dynamics 365 Human Resources na infraestrutura do aplicativo de finanças e operações.

## <a name="prerequisites"></a>Pré-requisitos

Antes de começar a provisionar um novo ambiente, os seguintes pré-requisitos devem estar disponíveis:

- Você adquiriu o Human Resources por meio de um Provedor de Soluções na Nuvem (CSP) ou de um contrato de arquitetura da empresa (EA). Se você tiver uma licença existente do Dynamics 365 que já inclua o plano do serviço do Human Resources e não puder concluir as etapas deste artigo, entre em contato com o Suporte.
- O administrador global deve ter entrado no [Lifecycle Services (LCS) do Microsoft Dynamics](https://lcs.dynamics.com) e criado um novo projeto do aplicativo de finanças e operações.

## <a name="provision-a-human-resources-trial-environment"></a>Provisionamento de um ambiente de teste de Recursos Humanos

> [!NOTE]
> A partir de 2022 de abril, os ambientes de avaliação do Human Resources não estarão disponíveis no aplicativo autônomo. Os clientes potenciais interessados em avaliar as funcionalidades do Human Resources em aplicativos de finanças e operações podem fazer isso usando a avaliação gratuita de 30 dias, junto com os dados de demonstração. O Dynamics 365 Finance incluirá as funcionalidades do Human Resources trazidas para a infraestrutura de finanças por meio da mesclagem do aplicativo autônomo. Para obter mais informações, consulte [Mesclagem de ofertas de RH reúne funcionalidades para os clientes](https://cloudblogs.microsoft.com/dynamics365/it/2021/09/15/merging-of-hr-offerings-brings-capabilities-together-for-customers). Para obter mais informações sobre as avaliações do Dynamics 365 Finance, consulte o [guia passo a passo](../fin-ops-core/fin-ops/get-started/before-you-buy.md).

## <a name="plan-human-resources-environments"></a>Planejar ambientes do Human Resources

Antes de criar seu primeiro ambiente do Human Resources, você deve planejar cuidadosamente as necessidades ambientais do seu projeto. Uma assinatura básica do Human Resources inclui dois ambientes: um ambiente de produção e um ambiente de teste de aceitação (Área restrita) padrão. Dependendo da complexidade do projeto, você terá a opção de comprar ambientes adicionais para apoiar as atividades do projeto.

Aqui estão algumas considerações para os ambientes opcionais adicionais:

- **Migração de dados**: atividades de migração de dados para permitir que o ambiente de área restrita seja usado para fins de teste durante todo o projeto. Quando você tem um ambiente adicional, as atividades de migração de dados podem continuar enquanto as atividades de teste e configuração ocorrem simultaneamente em um ambiente diferente.
- **Integração** – configura e testa integrações que podem incluir integrações nativas ou personalizadas, como as de folha de pagamento, sistemas de rastreamento de candidatos ou sistemas e provedores de benefícios.
- **Treinamento**: Talvez você precise de um ambiente separado que seja configurado com um conjunto de dados de treinamento, de forma que você possa treinar funcionários sobre o uso do novo sistema. 
- **Projeto multi-fase**: talvez precise de um ambiente adicional para dar suporte a configuração, migração de dados, testes ou outras atividades em uma fase de projeto que é planejada após a ativação inicial do projeto.
- **Desenvolvimento** – na infraestrutura do aplicativo de finanças e operações, você pode estender a solução e desenvolver suas próprias personalizações. Cada desenvolvedor deve usar seu próprio ambiente de desenvolvimento. Para mais informações, consulte [Implantar e acessar ambientes de desenvolvimento](../fin-ops-core/dev-itpro/dev-tools/access-instances.md).
- **OURO** – para novas implantações, uma prática comum é usar um ambiente OURO separado que é mantido intacto para migração de dados e configuração. Esse ambiente pode ser usado em toda a implementação para atualizar outros ambientes. Ele será usado para criar o novo ambiente de produção que tem a configuração básica e a migração de dados. Não é possível implantar um ambiente de produção na infraestrutura de finanças e operações até que você tenha concluído o processo de preparação da ativação. Para obter mais informações, consulte [Preparar para ativação](../fin-ops-core/fin-ops/imp-lifecycle/prepare-go-live.md).

<!--NOTE: Need to come back and verify Tier-1 can be used and if a customer cannot purchase tier 3-5 need specific documentation about this.-->

> [!IMPORTANT]
> Ao considerar seus ambientes, recomendamos a seguinte abordagem:
>
> - Use o ambiente padrão de teste de aceitação padrão (anteriormente Área Restrita) ou outro ambiente para realizar uma simulação de simulação antes da ativação.
> - Mantenha uma lista de verificação detalhada de substituição que inclua cada pacote de dados necessários para migrar os dados finais para o ambiente de produção durante a substituição da ativação. Essa recomendação é especialmente importante se você não tiver um ambiente OURO separado para armazenar suas configurações.
> - Use o ambiente padrão de teste de aceitação padrão (anteriormente Área restrita) ou outro ambiente de nível 2 ou superior como seu ambiente de teste no seu projeto. Se você precisar de ambientes adicionais, sua organização poderá comprá-los por um custo adicional.

## <a name="create-an-lcs-project"></a>Criar um projeto LCS

Para usar o LCS para gerenciar seus ambientes do Human Resources, você deve criar primeiro um projeto LCS. Se você estiver migrando seu ambiente do Human Resources para a infraestrutura do aplicativo de finanças e operações, deverá criar um novo projeto LCS para aplicativos de finanças e operações. Se você já tiver um projeto LCS para outros aplicativos de finanças e operações, poderá habilitar as funcionalidades do Human Resources no espaço de trabalho **Gerenciamento de recursos**. Para obter mais informações, consulte [Visão geral do Gerenciamento de recursos](../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md).

Quando um novo cliente se inscrever no Human Resources, a assinatura inclui um espaço de trabalho de projeto de implementação. Depois que o cliente ativa o serviço, o administrador de locatários deverá entrar em <https://lcs.dynamics.com> usando a conta de locatário. O espaço de trabalho do projeto é criado automaticamente para a organização. Para obter informações, consulte [Lifecycle Services (LCS) para clientes dos aplicativos de Finanças e Operações](../fin-ops-core/dev-itpro/lifecycle-services/lcs-works-lcs.md).

> [!NOTE]
> Para garantir o provisionamento com êxito, a conta usada para provisionar o ambiente do Human Resources deve ser atribuída à função **Administrador do Sistema** ou **Personalizador do Sistema** no ambiente do Power Apps associado ao ambiente do Human Resources. Para obter mais informações sobre como atribuir direitos de acesso no Microsoft Power Platform, consulte [Configurar segurança do usuário para recursos](/power-platform/admin/database-security).

Você deve preencher o processo de integração do projeto LCS antes de começar a implantar ambientes. Para obter mais informações, consulte [Integração do projeto](../fin-ops-core/dev-itpro/lifecycle-services/project-onboarding.md). Para obter mais informações sobre como usar o LCS, consulte [Guia do usuário do Lifecycle Services (LCS)](../fin-ops-core/dev-itpro/lifecycle-services/lcs-user-guide.md).

## <a name="deploy-human-resources-environments"></a>Implantar ambientes do Human Resources

A implantação de aplicativos de finanças e operações, incluindo Human Resources, na nuvem requer que você compreenda o ambiente e a assinatura em que está implantando, que pode executar quais tarefas e quais dados e personalizações você deve gerenciar. É recomendável usar uma conta de serviço em vez de um usuário nomeado ao implantar novos ambientes. Para obter mais informações sobre como implantar ambientes na infraestrutura do aplicativo de finanças e operações, consulte [visão geral da implantação na Nuvem](/fin-ops-core/dev-itpro/deployment/cloud-deployment-overview).

Para implantar um ambiente de produção para Human Resources na infraestrutura de finanças e operações, é necessário concluir o processo de preparação da ativação. Para obter mais informações, consulte [Preparar para ativação](../fin-ops-core/fin-ops/imp-lifecycle/prepare-go-live.md). Esse processo inclui o avaliador de assinatura no LCS. Para obter mais informações, consulte [Avaliador de assinatura](../fin-ops-core/dev-itpro/lifecycle-services/subscription-estimator.md).

## <a name="integrate-microsoft-power-platform-with-human-resources"></a>Integrar o Microsoft Power Platform ao Human Resources

O Microsoft Power Platform fornece um conjunto de recursos para aplicativos Dynamics 365 por meio do centro de administração do Power Platform. Você pode integrar e estender o uso de dados do Human Resources usando as ferramentas do Microsoft Power Platform. Para obter informações sobre como integrar recursos humanos ao Microsoft Power Platform, consulte [Integração do Microsoft Power Platform com os aplicativos de Finanças e Operações](../fin-ops-core/dev-itpro/power-platform/overview.md).

## <a name="supported-geographies"></a>Geografias com suporte

Para obter informações sobre os idiomas e geografias que têm suporte para recursos humanos, consulte [Global por design: conheça os países e idiomas com suporte](https://dynamics.microsoft.com/availability-reports/).

## <a name="grant-access-to-the-environment"></a>Conceder acesso ao ambiente

Por padrão, o administrador global que criou o ambiente tem acesso a ele. Os usuários adicionais do aplicativo devem ter acesso explicitamente. Você deve adicionar usuários e atribuir a eles as funções adequadas no ambiente do Human Resources. Para obter mais informações, consulte [Criar novos usuários](/dynamics365/unified-operations/dev-itpro/sysadmin/tasks/create-new-users) e [Atribuir usuários a funções de segurança](/dynamics365/unified-operations/dev-itpro/sysadmin/tasks/assign-users-security-roles).

## <a name="additional-resources"></a>Recursos adicionais
Você pode aprender mais sobre como usar e gerenciar projetos nas LCS na infraestrutura de aplicativos de finanças e operações usando os seguintes recursos:

- [Recursos do Lifecycle Services](../fin-ops-core/dev-itpro/lifecycle-services/lcs.md)
- [Guia do usuário do Lifecycle Services (LCS)](../fin-ops-core/dev-itpro/lifecycle-services/lcs-user-guide.md)
- [Visão geral da Implantação de autoatendimento](../fin-ops-core/dev-itpro/deployment/infrastructure-stack.md)
- [Home page de operações de movimentação do banco de dados](../fin-ops-core/dev-itpro/database/dbmovement-operations.md)

[!INCLUDE[footer-include](../includes/footer-banner.md)]
