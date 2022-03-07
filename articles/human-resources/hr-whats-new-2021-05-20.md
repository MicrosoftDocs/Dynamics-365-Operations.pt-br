---
title: Novidades ou alterações na versão do Dynamics 365 Human Resources de 20 de maio de 2021
description: Este tópico descreve os recursos novos ou alterados no Microsoft Dynamics 365 Human Resources para 20 de maio de 2021.
author: marcelbf
ms.date: 05/20/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.search.scope: Human Resources
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: marcelbf
ms.search.validFrom: 2021-05-20
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: c7b7f71cf084a05bb0278f5df4ddb022ef3d640f
ms.sourcegitcommit: baad2723291774f610324a8054fc14abf3287fe1
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/14/2021
ms.locfileid: "6560041"
---
# <a name="whats-new-or-changed-in-dynamics-365-human-resources-may-20-2021"></a>Novidades ou alterações na versão do Dynamics 365 Human Resources de 20 de maio de 2021

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

Este tópico descreve recursos que são novos, alterados ou que em breve serão lançados no Dynamics 365 Human Resources.

Para obter mais informações sobre nosso processo de atualização e agenda, consulte [Processo de atualização](hr-admin-setup-update-process.md).

Para obter mais informações sobre novos recursos e suas datas de disponibilidade geral esperadas, consulte [Visão geral do Dynamics 365 Human Resources 2021 ciclo de lançamentos 1](/dynamics365-release-plan/2021wave1/human-resources/dynamics365-human-resources/).

## <a name="in-this-release"></a>Nesta versão

Esta versão inclui os novos recursos e correções de bugs a seguir. As alterações se aplicam ao número da compilação 8.1.4189.

### <a name="new-features"></a>Novos recursos

Os seguintes recursos estão geralmente disponíveis nesta versão.

| Recurso | Liberar planos | Documentação |
| --- | --- | --- |
| Atualização da plataforma 10.0.18 (42) | -- | [Atualizações de plataforma para a versão 10.0.18 de aplicativos do Finance and Operations (maio de 2021)](/dynamics365/fin-ops-core/dev-itpro/get-started/whats-new-platform-updates-10-0-18) |
| O aplicativo de Recursos Humanos para Microsoft Teams agora oferece suporte a definições de meio dia e capacidade dividida no dia | -- | [Gerenciar solicitações de licença no Teams](/dynamics365/human-resources/hr-teams-leave-app#create-a-new-request) |

### <a name="bug-fixes"></a>Correções de bug

As seguintes correções de bug estão incluídas nessa versão.

> [!NOTE]
> Nosso objetivo é obter essas informações o mais rápido possível. Podemos atualizar este tópico para incluir correções de bugs feitas no build após a publicação inicial deste tópico.

| Número do problema | Problema |  descrição |
| --- | --- | --- |
| 583776 | Os registros em massa de funcionários em planos de licença estão causando um erro de registro duplicado | Esse bug foi corrigido com a última versão e os registros de planos de licença em massa devem ser processados com êxito. |
| 582263 | Não é possível executar o processamento de eventos de vida útil para todos os trabalhadores de uma só vez | Quando o campo **Trabalhador** for deixado em branco para processamento de eventos de vida, todos os trabalhadores serão processados. |
| 558383 | Beneficiário principal não marcado como 100% se o design padrão não estiver selecionado | O bug foi corrigido de tal modo que o usuário só precise selecionar a alternância de beneficiário principal.|
| 509404 | Análise do departamento de pessoal não considerando a movimentação de funcionários entre departamentos |As análises foram atualizadas para incluir transferências de funcionários entre departamentos|
| 579420 | O recurso Congelar colunas nas grades ainda não está disponível | O recurso **Congelar colunas nas grades**, que não está disponível em Recursos Humanos, foi listado como disponível no Gerenciamento de Recursos. O recurso foi removido da lista de recursos a ser habilitada. |

## <a name="in-preview"></a>Em versão preliminar

Os novos recursos a seguir estão em versão preliminar. Para obter mais informações sobre a ativação e a desativação de recursos, consulte [Gerenciar recursos](hr-admin-manage-features.md).

| Recurso | Liberar planos | Documentação |
| --- | --- | --- |
| Suporte a campo personalizado em Regras de qualificação de gerenciamento de benefícios | [Suporte a campos personalizados para processamento de qualificação](/dynamics365-release-plan/2021wave1/human-resources/dynamics365-human-resources/custom-field-support-eligibility-processing) |[Configurando regras de qualificação](/dynamics365/human-resources/hr-benefits-setup-eligibility-rules) |
| Espaço de trabalho de gerenciamento de benefícios | [Espaço de trabalho de gerenciamento de benefícios (versão preliminar)](/dynamics365-release-plan/2020wave2/human-resources/dynamics365-human-resources/benefits-management-workspace) | [Espaço de trabalho de gerenciamento de benefícios](hr-benefits-management-workspace.md) |
| Aprimoramentos de experiência de fluxo de trabalho de licença e ausência | [Aprimoramentos de experiência de fluxo de trabalho de licença e ausência](https://go.microsoft.com/fwlink/?linkid=2147528) | [Solicitar folga](hr-employee-self-service-request-time-off.md)|
| Habilitar integração simplificada da folha de pagamento (APIs de integração de folha de pagamento) | [Habilitar integração simplificada com provedores de folha de pagamento](/dynamics365-release-plan/2021wave1/human-resources/dynamics365-human-resources/enable-simplified-integration-payroll-providers) | [API de integração da folha de pagamento](hr-admin-integration-payroll-api-introduction.md)|
| Auditoria de transações de acúmulo de licenças | - | [Auditoria de transações de acúmulo de licenças](hr-leave-and-absence-accrue.md)|

## <a name="coming-soon"></a>Em breve

| Recurso | Detalhes |
| --- | --- |
|  Habilitar um gerente de ausência para gerenciar a licença | [Habilitar um gerente de ausência para gerenciar a licença](/dynamics365-release-plan/2021wave1/human-resources/dynamics365-human-resources/enable-absence-manager-manage-leave) |

Para obter uma lista completa de recursos planejados e suas versões agendadas, consulte [Visão geral do Dynamics 365 Human Resources 2021 ciclo de lançamentos 1](/dynamics365-release-plan/2021wave1/human-resources/dynamics365-human-resources/).

## <a name="see-also"></a>Consulte também

[Novidades ou alterações no Human Resources](hr-admin-whats-new.md)</br>
[Visão geral do ciclo de lançamentos 1 de 2021 do Dynamics 365 Human Resources](/dynamics365-release-plan/2021wave1/human-resources/dynamics365-human-resources/)</br>
[Atualizar processo](hr-admin-setup-update-process.md)</br>
[Gerenciar recursos](hr-admin-manage-features.md)

[!INCLUDE[footer-include](../includes/footer-banner.md)]
