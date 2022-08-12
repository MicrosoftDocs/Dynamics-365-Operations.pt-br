---
title: Atualizar processo
description: O Microsoft Dynamics 365 Human Resources é um software como serviço (SaaS) que disponibiliza atualizações de serviço contínuas e touchless para alterações de aplicação e plataforma.
author: twheeloc
ms.date: 09/01/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: SystemAdministrationWorkspaceForm
audience: Application User
ms.custom: 7521
ms.assetid: ''
ms.search.region: Global
ms.author: twheeloc
ms.search.validFrom: 2020-02-27
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: 25889f9d4a7ffb4f155b7b7c12ec3b21a44a4710
ms.sourcegitcommit: 1401d66b6b64c590ca1f8f339d622e922920cf15
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/20/2022
ms.locfileid: "9178432"
---
# <a name="update-process"></a>Atualizar processo

_**Aplica-se a:** Human Resources na infraestrutura autônoma_ 

> [!NOTE]
> A partir de 2022 de julho, novos ambientes do Human Resources não podem ser provisionados na infraestrutura autônoma do Human Resources, e novos projetos do Lifecycle Services (LCS) do Microsoft Dynamics não podem ser criados nele. Os clientes podem implantar ambientes de Recursos Humanos na infraestrutura de aplicativos de finanças e operações. Para obter mais informações, consulte [Provisionar Recursos Humanos na infraestrutura de finanças e operações](/hr-admin-setup-provision-fo.md).

> [!IMPORTANT]
> O processo de atualização e hotfix na infraestrutura de aplicativos de finanças e operações é diferente do processo de atualização e hotfix autônomo do Human Resources. Para obter mais informações sobre processo de atualização, consulte [Processo para migrar para a última atualização do aplicativo de finanças e operações](../fin-ops-core/dev-itpro/migration-upgrade/upgrade-latest-update.md). Para obter mais informações sobre hotfixes, consulte [Baixar atualizações do Lifecycle Services (LCS)](/fin-ops-core/dev-itpro/migration-upgrade/download-hotfix-lcs.md). 

O Microsoft Dynamics 365 Human Resources é um software como serviço (SaaS) que disponibiliza atualizações de serviço contínuas e touchless. Essas atualizações contêm alterações no aplicativo e na plataforma, que geralmente oferecem melhorias cruciais para o serviço, incluindo atualizações regulatórias.

## <a name="update-policy"></a>Política de atualização

As atualizações são lançadas regularmente para todos os ambientes. O Human Resources oferecem suporte de acordo com a [política de Ciclo de Vida da Microsoft](https://support.microsoft.com/hub/4095338/microsoft-lifecycle-policy), que oferece diretrizes consistentes e previsíveis para a disponibilidade de suporte.

## <a name="release-cadence"></a>Cadência da versão 

As atualizações do Human Resources são aplicadas a todos os ambientes automaticamente. O Human Resources oferece dois tipos de versão:

- **Atualizações de serviço**: atualizações ocorrem a cada duas semanas e incluem correções de bugs e novos recursos. As atualizações de serviço também incluem atualizações de plataforma aplicáveis quando são lançadas. Para obter mais informações sobre versões da plataforma, consulte [Novidades ou alterações em Atualizações de plataforma](../fin-ops-core/dev-itpro/get-started/whats-new-home-page.md). As atualizações têm uma distribuição global em etapas entre regiões. Para obter mais informações sobre atualizações, consulte [Novidades ou alterações no Dynamics 365 Human Resources](hr-admin-whats-new.md).

- **Atualizações de soluções do Dataverse**: essas atualizações ocorrem aproximadamente a cada seis semanas, conforme a necessidade. Elas incluem novas entidades e alterações às entidades existentes no Dataverse. Essas atualizações serão lançadas nas mesmas regiões como as atualizações quinzenais, e levam até seis semanas para serem replicadas em todos os data centers. As atualizações da solução podem ou não estar alinhadas às atualizações de serviço quinzenais.

> [!NOTE]
> As atualizações de solução ficam disponíveis em todos os data centers após serem lançadas. Caso não queira esperar as atualizações serem replicadas automaticamente, você pode aplicá-las manualmente em qualquer ambiente ou data center.

Quando necessário, o Human Resources também oferece os seguintes tipos de correções:

- **Revisão (hotfix)**: correções de bugs que podem ocorrer com ou sem o lançamento da atualização de serviço quinzenal

- **Correção de emergência**: hotfixes proativos e reativos que são independentes por natureza, podem incluir alterações de código ou somente para configuração para solucionar problemas de sites ativos e podem ocorrer sem um lançamento de atualização de serviço quinzenal

As versões são analisadas, testadas e validadas em um ambiente interno. Após as compilações serem aprovadas, elas são implementadas na produção.

## <a name="release-cadence-exceptions-in-2021"></a>Exceções de cadência da versão em 2021

Para contabilizar feriados, a agenda de lançamentos para novembro e dezembro de 2021 é a seguinte:

- Lançamento de novembro: 1 de novembro - 14 de novembro
- Lançamento de dezembro: 29 de novembro - 12 de dezembro
 
A cadência de lançamentos de duas semanas será retomada normalmente em 10 de janeiro de 2022.

## <a name="communications"></a>Comunicações

Descubra as novidades do Human Resources e o que já foi lançado em:

- [Dynamics 365 Human Resources roteiro](https://dynamics.microsoft.com/roadmap/human-resources/)

- [Planos de Versão do Dynamics 365](/dynamics365/release-plans/)

- [Novidades ou alterações no Dynamics 365 Human Resources](hr-admin-whats-new.md)

- [Pesquisa de problemas no Lifecycle Services (LCS)](../fin-ops-core/dev-itpro/lifecycle-services/issue-search-lcs.md) (somente para bugs relacionados à Plataforma)

- [Blog do Human Resources](https://community.dynamics.com/365/talent/b/dynamics365fortalent)

- [Comunidade do Human Resources no Yammer](https://www.yammer.com/dynamicsaxfeedbackprograms/#/threads/inGroup?type=in_group&feedId=10542230)

## <a name="preview-features-in-a-sandbox-environment"></a>Versões prévias do recurso em um ambiente de área restrita

Você pode validar as versões prévias do recurso em um ambiente de área restrita antes de habilitá-las no ambiente de produção. Para obter mais informações sobre como habilitar os recursos, consulte [Visão geral do gerenciamento de recursos](../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md).

Todos os novos recursos permanecerão em versão prévia por pelo menos 30 dias e, em geral, por 30 a 60 dias. Os recursos principais estão disponíveis geralmente em outubro e abril de cada ano a partir do período de versão prévia. Assim que vir novos recursos no espaço de trabalho **Gerenciamento de recursos**, você poderá ativá-los. Alguns recursos podem ser ativados por padrão.

Às vezes, um recurso integral estará ativado por padrão e não poderá ser desativado (por exemplo, o espaço de trabalho Gerenciamento de recursos).

Assim que um recurso estiver disponível de forma geral, ele poderá ser ativado ou desativado em ambientes de produção. O espaço de trabalho **Gerenciamento de recursos** indica quando a versão prévia do recurso se tornará obrigatória. Geralmente, essa data fica entre 1º de outubro ou 1º de abril, para se alinhar com os planos de lançamento semestrais. Você não pode desativar recursos obrigatórios. Até que ele se torne obrigatório, você poderá ativar e desativar um recurso em todos os ambientes.

É altamente recomendado visualizar os recursos em uma área restrita ou um ambiente de avaliação. É melhor criar uma cópia do ambiente de produção atual ou do banco de dados em um ambiente de área restrita para obter a experiência completa dos novos recursos com seus dados.

Para obter mais informações sobre como provisionar um ambiente de área restrita, consulte [Provisionar um projeto do Human Resources](hr-admin-setup-provision.md). Para remover um ambiente de teste, consulte [Remover uma instância](hr-admin-setup-remove-instance.md#remove-a-test-drive-environment). 

## <a name="report-bugs"></a>Relatar bugs

Enquanto estiver testando as versões prévias do recurso ou experimentando novas funcionalidades, poderá encontrar itens que não funcionam como deveriam. Relate os bugs no [suporte do Microsoft Dynamics 365](https://dynamics.microsoft.com/support/).

## <a name="see-also"></a>Consulte também

[Planos de Versão do Dynamics 365 e Power Platform](/dynamics365/release-plans)</br>
[Novidades ou alterações no Dynamics 365 Human Resources](hr-admin-whats-new.md)</br>
[Política de ciclo de vida do software - Nuvem](../fin-ops-core/dev-itpro/migration-upgrade/versions-update-policy.md)



[!INCLUDE[footer-include](../includes/footer-banner.md)]
