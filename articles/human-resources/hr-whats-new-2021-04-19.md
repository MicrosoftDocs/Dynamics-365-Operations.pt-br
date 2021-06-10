---
title: Novidades ou alterações no Dynamics 365 Human Resources 19 de abril de 2021
description: Este tópico descreve os recursos novos ou alterados no Microsoft Dynamics 365 Human Resources para 19 de abril de 2021.
author: marcelbf
ms.date: 04/19/2021
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
ms.search.validFrom: 2021-04-19
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: b1371e453ae51dafe24b2105b1b9b7c38cdb4db4
ms.sourcegitcommit: 879ee8a10e6158885795dce4b3db5077540eec41
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/18/2021
ms.locfileid: "6052352"
---
# <a name="whats-new-or-changed-in-dynamics-365-human-resources-april-19-2021"></a>Novidades ou alterações no Dynamics 365 Human Resources 19 de abril de 2021

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

Este tópico descreve recursos que são novos, alterados ou que em breve serão lançados no Dynamics 365 Human Resources.

Para obter mais informações sobre nosso processo de atualização e agenda, consulte [Processo de atualização](hr-admin-setup-update-process.md).

Para obter mais informações sobre novos recursos e suas datas de disponibilidade geral esperadas, consulte [Visão geral do Dynamics 365 Human Resources 2021 ciclo de lançamentos 1](/dynamics365-release-plan/2021wave1/human-resources/dynamics365-human-resources/).

## <a name="in-this-release"></a>Nesta versão

Esta versão inclui os novos recursos e correções de bugs a seguir. As alterações se aplicam ao número da compilação 8.1.4113.

### <a name="new-features"></a>Novos recursos

Os seguintes recursos estão geralmente disponíveis nesta versão.

| Recurso | Liberar planos | Documentação |
| --- | --- | --- |
| Atualização da plataforma 10.0.17 (41) | -- | [Atualizações de plataforma para a versão 10.0.17 de aplicativos do Finance and Operations (abril de 2021)](../fin-ops-core/dev-itpro/get-started/whats-new-platform-updates-10-0-17.md) |
| Suporte a campos personalizados em formulários de Gerenciamento de Benefícios | [Suporte a campo personalizado em gerenciamento de benefícios](/dynamics365-release-plan/2021wave1/human-resources/dynamics365-human-resources/custom-field-support-benefits-management)| [Visão geral do gerenciamento de benefícios](hr-benefits-management-overview.md)|

### <a name="bug-fixes"></a>Correções de bug

As seguintes correções de bug estão incluídas nessa versão.

> [!NOTE]
> Nosso objetivo é obter essas informações o mais rápido possível. Podemos atualizar este tópico para incluir correções de bugs feitas no build após a publicação inicial deste tópico.

| Número do problema | Problema |  Descrição |
| --- | --- | --- |
| 552164 | **Exibição salva** em **Autoatendimento para funcionários > Cursos abertos** não funciona para cursos contendo uma agenda | Se uma exibição salva for usada em cursos abertos (ESS) e um dos cursos tiver uma agenda anexada, a exibição não mostrará várias linhas para esse curso |
| 560614 | **Benefícios > Opções de evento de vida** mostra discrepâncias na documentação da dica de ferramenta e no comportamento do código. | Dicas de ferramenta atualizadas em **Opções de evento de vida** para mostrar o comportamento correto. |
| 560616 | **Benefícios > Opções de evento de vida** são editáveis no plano de benefício do trabalhador, mas as alterações não são afetadas. | Comportamento atualizado da opção de evento de vida a ser habilitado ou desabilitado, com base em opções dependentes, por documentação de dica de ferramenta. |
| 565054 | Não é possível exibir o conteúdo de lista **Trabalhadores sem emprego** quando **Acesso avançado** está ativado. | Esta versão corrige o problema em que, quando **Acesso avançado** estava ativado, somente os administradores do sistema podiam exibir o conteúdo da lista **Trabalhadores sem emprego**. Como esta correção é uma alteração de segurança, você precisará optar por ela no gerenciamento de recursos. Depois que o recurso estiver ativado, as funções com acesso ao formulário verão o conteúdo, mesmo que o acesso avançado esteja ativado. Para obter mais informações, consulte [Trabalhadores sem emprego](hr-personnel-workers-without-employment.md). |
| 570586 | A validação da solicitação de licença falha quando o emprego termina antes da última transação para esse trabalhador em todos os planos de licença. | Quando um emprego termina, a validação da solicitação de licença não falha com base em transações de licença do funcionário.|
| 570783 | Ao habilitar e desabilitar a licença intercompanhia em parâmetros compartilhados de Recursos Humanos, você alteram o que os funcionários empregados em uma única empresa veem em solicitações de licença. | Os funcionários empregados em uma única empresa não verão alterações na solicitação de tempo limite se o parâmetro for habilitado ou desabilitado. |
| 572343 | O código de motivo necessário não é exibido quando o recurso de exibição de licença interempresarial está habilitado. | Quando o recurso de licença interempresarial está habilitado, o código de motivo é exibido conforme esperado. |
| 573676 | Não é possível adicionar **Período** a **Gerenciamento de benefícios > Links > Planos de benefícios**. | Bugs corrigidos em que o **Período** não pôde ser adicionado ou atualizado no formulário **Plano de benefícios** existente. |

## <a name="in-preview"></a>Em versão preliminar

Os novos recursos a seguir estão em versão preliminar. Para obter mais informações sobre a ativação e a desativação de recursos, consulte [Gerenciar recursos](hr-admin-manage-features.md).

| Recurso | Liberar planos | Documentação |
| --- | --- | --- |
| Espaço de trabalho de gerenciamento de benefícios | [Espaço de trabalho de gerenciamento de benefícios (versão preliminar)](/dynamics365-release-plan/2020wave2/human-resources/dynamics365-human-resources/benefits-management-workspace) | [Espaço de trabalho de gerenciamento de benefícios](hr-benefits-management-workspace.md) |
| Aprimoramentos de experiência de fluxo de trabalho de licença e ausência | [Aprimoramentos de experiência de fluxo de trabalho de licença e ausência](https://go.microsoft.com/fwlink/?linkid=2147528) | [Solicitar folga](hr-employee-self-service-request-time-off.md)|
| Habilitar integração simplificada da folha de pagamento (APIs de integração de folha de pagamento) | [Habilitar integração simplificada com provedores de folha de pagamento](/dynamics365-release-plan/2021wave1/human-resources/dynamics365-human-resources/enable-simplified-integration-payroll-providers) | [API de integração da folha de pagamento](hr-admin-integration-payroll-api-introduction.md)|

## <a name="coming-soon"></a>Em breve

| Recurso | Detalhes |
| --- | --- |
| As habilidades inseridas por um gerente para os funcionários podem ser aprovadas automaticamente por um fluxo de trabalho | Em breve. |
| Atualização da plataforma 10.0.18 (42) | A atualização da plataforma 10.0.18 está agendada para começar a ser implementada na versão de serviço, em 17 de maio de 2021. Para obter mais informações, consulte [Atualizações de plataforma para a versão 10.0.18 dos aplicativos do Finance and Operations (maio de 2021)](/dynamics365/fin-ops-core/dev-itpro/get-started/whats-new-platform-updates-10-0-18). |
| Suporte a campo personalizado em Regras de qualificação de gerenciamento de benefícios  | [Suporte a campos personalizados para processamento de qualificação](/dynamics365-release-plan/2021wave1/human-resources/dynamics365-human-resources/custom-field-support-eligibility-processing) |

Para obter uma lista completa de recursos planejados e suas versões agendadas, consulte [Visão geral do Dynamics 365 Human Resources 2021 ciclo de lançamentos 1](/dynamics365-release-plan/2021wave1/human-resources/dynamics365-human-resources/).

## <a name="see-also"></a>Consulte também

[Novidades ou alterações no Human Resources](hr-admin-whats-new.md)</br>
[Visão geral do ciclo de lançamentos 1 de 2021 do Dynamics 365 Human Resources](/dynamics365-release-plan/2021wave1/human-resources/dynamics365-human-resources/)</br>
[Atualizar processo](hr-admin-setup-update-process.md)</br>
[Gerenciar recursos](hr-admin-manage-features.md)

[!INCLUDE[footer-include](../includes/footer-banner.md)]
