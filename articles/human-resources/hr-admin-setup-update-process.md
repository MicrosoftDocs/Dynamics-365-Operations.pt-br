---
title: Atualizar processo
description: ''
author: andreabichsel
manager: AnnBe
ms.date: 02/03/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-human-resources
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: anbichse
ms.search.scope: Human Resources
ms.custom: 7521
ms.assetid: ''
ms.search.region: Global
ms.author: anbichse
ms.search.validFrom: 2020-02-03
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: 1817e072805bafbf0d5a9eb2698ef75abc75ad68
ms.sourcegitcommit: 4e62c22b53693c201baa646a8f047edb5a0a2747
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/07/2020
ms.locfileid: "3031081"
---
# <a name="update-process"></a>Atualizar processo

O Microsoft Dynamics 365 Human Resources é um software como serviço (SaaS) que disponibiliza atualizações de serviço contínuas e touchless. Essas atualizações contêm alterações no aplicativo e na plataforma, que geralmente oferecem melhorias cruciais para o serviço, incluindo atualizações regulatórias.

## <a name="update-policy"></a>Política de atualização

As atualizações são lançadas regularmente para todos os ambientes. O Human Resources oferecem suporte de acordo com a [política de Ciclo de Vida da Microsoft](https://support.microsoft.com/hub/4095338/microsoft-lifecycle-policy), que oferece diretrizes consistentes e previsíveis para a disponibilidade de suporte.

## <a name="release-cadence"></a>Cadência da versão

As atualizações do Human Resources são aplicadas a todos os ambientes automaticamente. O Human Resources oferece dois tipos de versão:

- **Atualizações de serviço**: atualizações semanais que incluem correções de bugs e novos recursos. As atualizações de serviço também incluem atualizações de Plataforma aplicáveis quando são lançadas. Para ter uma ideia de quando as atualizações de Plataforma serão lançadas, consulte [Tabela 3: versões da plataforma](https://docs.microsoft.com/dynamics365/fin-ops-core/dev-itpro/migration-upgrade/versions-update-policy#table-3-platform-releases). As atualizações semanais geralmente são lançadas às quartas-feiras. Para obter mais informações sobre atualizações semanais, consulte [Novidades ou alterações do Dynamics 365 Human Resources](https://docs.microsoft.com/dynamics365/talent/whats-new).

    Todos os data centers compatíveis são atualizados semanalmente, salvo indicação em contrário. As atualizações semanais geralmente começam na quarta-feira e terminam no domingo. As regiões EUA, Austrália, Europa, Reino Unido, Ásia e Canadá estão inclusas nas atualizações semanais. 

- **Atualizações de soluções do Common Data Service**: essas atualizações ocorrem aproximadamente a cada seis semanas, conforme a necessidade. Elas incluem novas entidades e alterações às entidades existentes no Common Data Service. Essas atualizações são lançadas nas mesmas regiões como as atualizações semanais, e levam até seis semanas para serem replicadas em todos os data centers. As atualizações da solução podem ou não estar alinhadas às atualizações de serviço.

A tabela a seguir exibe uma agenda de amostra:

| Semana | Atualizar tipo |
| --- | --- |
| 1 | Atualização de serviço (todas as regiões) |
| 2 | Atualização de serviço (todas as regiões) + Atualização de solução (Regiões da semana 1) |
| 3 | Atualização de serviço (todas as regiões) + Atualização de solução (Regiões da semana 2) |
| 4 | Atualização de serviço (todas as regiões) + Atualização de solução (Regiões da semana 3) |
| 5 | Atualização de serviço (todas as regiões) + Atualização de solução (Regiões da semana 4) |
| 6 | Atualização de serviço (todas as regiões) + Atualização de solução (Regiões da semana 5) |
| 7 | Atualização de serviço (todas as regiões) + Atualização de solução (Regiões da semana 6) |
| 8 | Atualização de serviço (todas as regiões) |

> [!NOTE]
> As atualizações de solução ficam disponíveis em todos os data centers após serem lançadas. Caso não queira esperar as atualizações serem replicadas automaticamente, você pode aplicá-las manualmente em qualquer ambiente ou data center.

Quando necessário, o Human Resources também oferece os seguintes tipos de correções:

- **Revisão (hotfix)**: correções de bugs que podem ocorrer com ou sem o lançamento da atualização de serviço semanal

- **Correção de emergência**: hotfixes proativos e reativos que são independentes por natureza, podem incluir alterações de código ou somente para configuração para solucionar problemas de sites ativos e podem ocorrer sem um lançamento de atualização de serviço semanal

As versões são analisadas, testadas e validadas em um ambiente interno. Após as compilações serem aprovadas, elas são implementadas na produção.

## <a name="exceptions-in-2019"></a>Exceções em 2019

As datas a seguir são exceções à agenda de lançamentos regular:

| Data  | Descrição |
| --- | --- |
| Semana do dia 25 de novembro | Nenhuma atualização |
| Semana do dia 16 de dezembro | Somente atualizações secundárias |
| Semana do dia 23 de dezembro | Nenhuma atualização |
| Semana do dia 30 de dezembro | Nenhuma atualização |

## <a name="communications"></a>Comunicações

Descubra as novidades do Human Resources e o que já foi lançado em:

- [Dynamics 365 Human Resources roteiro](https://dynamics.microsoft.com/roadmap/talent/)

- [Planos de Versão do Dynamics 365](https://docs.microsoft.com/dynamics365/release-plans/)

- [Novidades ou alterações no Dynamics 365 Human Resources](hr-admin-whats-new.md)

- [Pesquisa de problemas no Lifecycle Services (LCS)](https://docs.microsoft.com/dynamics365/fin-ops-core/dev-itpro/lifecycle-services/issue-search-lcs) (somente para bugs relacionados à Plataforma)

- [Blog do Human Resources](https://community.dynamics.com/365/talent/b/dynamics365fortalent)

- [Comunidade do Human Resources no Yammer](https://www.yammer.com/dynamicsaxfeedbackprograms/#/threads/inGroup?type=in_group&feedId=10542230)

## <a name="preview-features-in-a-sandbox-environment"></a>Versões prévias do recurso em um ambiente de área restrita

Você pode validar as versões prévias do recurso em um ambiente de área restrita antes de habilitá-las no ambiente de produção. Para obter mais informações sobre como habilitar os recursos, consulte [Visão geral do gerenciamento de recursos](https://docs.microsoft.com/dynamics365/fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview).

Todos os novos recursos permanecerão em versão prévia por pelo menos 30 dias e, em geral, por 30 a 60 dias. Os recursos principais estão disponíveis geralmente em outubro e abril de cada ano a partir do período de versão prévia. Assim que vir novos recursos no espaço de trabalho Gerenciamento de recursos, você poderá ativá-los. Alguns recursos podem ser ativados por padrão.

Às vezes, um recurso integral estará ativado por padrão e não poderá ser desativado (por exemplo, o espaço de trabalho Gerenciamento de recursos).

Assim que um recurso estiver disponível de forma geral, ele poderá ser ativado ou desativado em ambientes de produção. O espaço de trabalho Gerenciamento de recursos indica quando a versão prévia do recurso se tornará obrigatória. Geralmente, essa data fica entre 1º de outubro ou 1º de abril, para se alinhar com os planos de lançamento semestrais. Você não pode desativar recursos obrigatórios. Até que ele se torne obrigatório, você poderá ativar e desativar um recurso em todos os ambientes.

É altamente recomendado visualizar os recursos em uma área restrita ou um ambiente de avaliação. É melhor criar uma cópia do ambiente de produção atual ou do banco de dados em um ambiente de área restrita para obter a experiência completa dos novos recursos com seus dados.

Para obter mais informações sobre como provisionar um ambiente de área restrita, consulte [Provisionar um projeto do Human Resources](hr-admin-setup-provision.md). Para remover um ambiente de teste, consulte [Remover uma instância](hr-admin-setup-remove-instance.md#remove-a-test-drive-environment). 

## <a name="report-bugs"></a>Relatar bugs

Enquanto estiver testando as versões prévias do recurso ou experimentando novas funcionalidades, poderá encontrar itens que não funcionam como deveriam. Relate os bugs no [suporte do Microsoft Dynamics 365](https://dynamics.microsoft.com/support/).

## <a name="see-also"></a>Consulte também

- [Planos de Versão do Dynamics 365 e Power Platform](https://docs.microsoft.com/dynamics365/release-plans)
- [Novidades ou alterações no Dynamics 365 Human Resources](hr-admin-whats-new.md)
- [Política de ciclo de vida do software - Nuvem](https://docs.microsoft.com/dynamics365/fin-ops-core/dev-itpro/migration-upgrade/versions-update-policy)

