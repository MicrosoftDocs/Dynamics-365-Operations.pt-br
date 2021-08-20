---
title: Novidades ou alterações na versão do Dynamics 365 Human Resources de 3 de maio de 2021
description: Este tópico descreve os recursos novos ou alterados no Microsoft Dynamics 365 Human Resources para 3 de maio de 2021.
author: marcelbf
ms.date: 05/03/2021
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
ms.search.validFrom: 2021-05-03
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: 1bfbfabc8ba9c41dfd02c205755042f82387f5e09c88722e2503316bc1cf5feb
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/05/2021
ms.locfileid: "6770351"
---
# <a name="whats-new-or-changed-in-dynamics-365-human-resources-may-3-2021"></a>Novidades ou alterações na versão do Dynamics 365 Human Resources de 3 de maio de 2021

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

Este tópico descreve recursos que são novos, alterados ou que em breve serão lançados no Dynamics 365 Human Resources.

Para obter mais informações sobre nosso processo de atualização e agenda, consulte [Processo de atualização](hr-admin-setup-update-process.md).

Para obter mais informações sobre novos recursos e suas datas de disponibilidade geral esperadas, consulte [Visão geral do Dynamics 365 Human Resources 2021 ciclo de lançamentos 1](/dynamics365-release-plan/2021wave1/human-resources/dynamics365-human-resources/).

## <a name="in-this-release"></a>Nesta versão

Esta versão inclui os novos recursos e correções de bugs a seguir. As alterações se aplicam ao número da compilação 8.1.4140.

### <a name="new-features"></a>Novos recursos

Os seguintes recursos estão geralmente disponíveis nesta versão.

| Recurso | Liberar planos | Documentação |
| --- | --- | --- |
| Adicione a barra de informações quando os eventos de vida forem criados. | - | Quando você cria um evento de vida, a barra de informações exibe uma mensagem indicando o tipo de evento de vida criado.

### <a name="bug-fixes"></a>Correções de bug

As seguintes correções de bug estão incluídas nessa versão.

> [!NOTE]
> Nosso objetivo é obter essas informações o mais rápido possível. Podemos atualizar este tópico para incluir correções de bugs feitas no build após a publicação inicial deste tópico.

| Número do problema | Problema |  descrição |
| --- | --- | --- |
| 559312 |  O nível não é mostrado ao criar um plano de compensação fixo para um funcionário. |  Quando havia discrepância de fuso horário entre o fuso do usuário e o da empresa, o nível de compensação no trabalho não era lido. Uma consulta foi atualizada para obter dados com base no fuso UTC. |
| 573676  | Não é possível adicionar novo período no formulário **Plano de benefícios**. | O formulário foi atualizado para que o botão **Novo** seja habilitado na guia rápida **Período** em **Plano de benefícios**. |

## <a name="in-preview"></a>Em versão preliminar

Os novos recursos a seguir estão em versão preliminar. Para obter mais informações sobre a ativação e a desativação de recursos, consulte [Gerenciar recursos](hr-admin-manage-features.md).

| Recurso | Liberar planos | Documentação |
| --- | --- | --- |
| Espaço de trabalho de gerenciamento de benefícios | [Espaço de trabalho de gerenciamento de benefícios (versão preliminar)](/dynamics365-release-plan/2020wave2/human-resources/dynamics365-human-resources/benefits-management-workspace) | [Espaço de trabalho de gerenciamento de benefícios](hr-benefits-management-workspace.md) |
| Aprimoramentos de experiência de fluxo de trabalho de licença e ausência | [Aprimoramentos de experiência de fluxo de trabalho de licença e ausência](https://go.microsoft.com/fwlink/?linkid=2147528) | [Solicitar folga](hr-employee-self-service-request-time-off.md)|
| Habilitar integração simplificada da folha de pagamento (APIs de integração de folha de pagamento) | [Habilitar integração simplificada com provedores de folha de pagamento](/dynamics365-release-plan/2021wave1/human-resources/dynamics365-human-resources/enable-simplified-integration-payroll-providers) | [API de integração da folha de pagamento](hr-admin-integration-payroll-api-introduction.md)|
| Auditoria de transações de acúmulo de licenças | - | [Auditoria de transações de acúmulo de licenças](hr-leave-and-absence-accrue.md)|

## <a name="coming-soon"></a>Em breve

| Recurso | Detalhes |
| --- | --- |
| Atualização da plataforma 10.0.18 (42) | A atualização da plataforma 10.0.18 está agendada para começar a ser implementada na versão de serviço, em 17 de maio de 2021. Para obter mais informações, consulte [Atualizações de plataforma para a versão 10.0.18 dos aplicativos do Finance and Operations (maio de 2021)](/dynamics365/fin-ops-core/dev-itpro/get-started/whats-new-platform-updates-10-0-18). |
| Suporte a campo personalizado em Regras de qualificação de gerenciamento de benefícios  | [Suporte a campos personalizados para processamento de qualificação](/dynamics365-release-plan/2021wave1/human-resources/dynamics365-human-resources/custom-field-support-eligibility-processing) |

Para obter uma lista completa de recursos planejados e suas versões agendadas, consulte [Visão geral do Dynamics 365 Human Resources 2021 ciclo de lançamentos 1](/dynamics365-release-plan/2021wave1/human-resources/dynamics365-human-resources/).

## <a name="see-also"></a>Consulte também

[Novidades ou alterações no Human Resources](hr-admin-whats-new.md)</br>
[Visão geral do ciclo de lançamentos 1 de 2021 do Dynamics 365 Human Resources](/dynamics365-release-plan/2021wave1/human-resources/dynamics365-human-resources/)</br>
[Atualizar processo](hr-admin-setup-update-process.md)</br>
[Gerenciar recursos](hr-admin-manage-features.md)

[!INCLUDE[footer-include](../includes/footer-banner.md)]
