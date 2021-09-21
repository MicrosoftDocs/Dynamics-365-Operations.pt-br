---
title: Novidades ou alterações no Dynamics 365 Human Resources (23 de agosto 2021)
description: Este tópico descreve os recursos novos ou alterados no Microsoft Dynamics 365 Human Resources para 23 de agosto de 2021.
author: marcelbf
ms.date: 08/23/2021
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
ms.search.validFrom: 2021-08-23
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: 21c9ee0206bd77a8a2ec42501d64e83077baef09
ms.sourcegitcommit: 696796ca5635863850ae9ef16fc1fb0fc46ce8f0
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/28/2021
ms.locfileid: "7441666"
---
# <a name="whats-new-or-changed-in-dynamics-365-human-resources-august-23-2021"></a>Novidades ou alterações no Dynamics 365 Human Resources (23 de agosto 2021)

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

Este tópico descreve recursos que são novos, alterados ou que em breve serão lançados no Microsoft Dynamics 365 Human Resources.

Para obter mais informações sobre nosso processo de atualização e agenda, consulte [Processo de atualização](hr-admin-setup-update-process.md).

Para obter mais informações sobre novos recursos e suas datas de disponibilidade geral esperadas, consulte [Visão geral do Dynamics 365 Human Resources 2021 ciclo de lançamentos 2](/dynamics365-release-plan/2021wave2/human-resources/dynamics365-human-resources/).

## <a name="in-this-release"></a>Nesta versão

Esta versão inclui os novos recursos e correções de bugs a seguir. As alterações se aplicam ao número da compilação 8.1.4419.

### <a name="bug-fixes"></a>Correções de bug

As seguintes correções de bug estão incluídas nessa versão.

> [!NOTE]
> Nosso objetivo é obter essas informações o mais rápido possível. Podemos atualizar este tópico para incluir correções de bugs feitas no build após a publicação inicial deste tópico.

| Número do problema | Problema | descrição |
| --- | --- | --- |
| 594066 | Não é possível excluir as Informações de Contato | Ao selecionar para excluir um registro de Informações de contato de um funcionário, um registro de informações de contato que não seja o registro selecionado será excluído. |
| 611339 | Adicionar uma personalização faz com que a conta bancária ignore o filtro e busque o primeiro registro | Adicionar uma personalização faz com que a lista de contas bancárias execute uma consulta de personalização após a execução da consulta de fonte de dados. Assim, a consulta busca o primeiro registro, independentemente do trabalhador para quem os detalhes estão sendo exibidos. |
| 591806 | A data de conclusão das tarefas de integração é calculada incorretamente | As datas de conclusão são calculadas incorretamente quando ocorrem as seguintes condições: as listas de verificação criadas estão usando um calendário que usa um intervalo de tempo estendido (por exemplo, de 2005 a 2050) e as preferências do usuário usam um fuso horário diferente de CST. |   
| 592749 | O saldo de licença está incorreto no **Autoatendimento para funcionários** | Se o funcionário estiver empregado em mais de uma entidade legal e a exibição de licença entre empresas estiver habilitada, talvez o saldo de licença esteja incorreto. |
| 603133 | Aviso inesperado ao solicitar folga | Ao solicitar folga, preencher o campo **Meio dia** antes do campo **Valor** gerará um aviso inesperado. |
| 606546 | O campo selecionado não está visível na Folga aprovada | A caixa de seleção para marcar várias solicitações de licença aprovadas não está visível. |
| 597059 | O trabalhador não está visível no **Calendário de licenças e ausências da empresa** | Um trabalhador não estará visível no **Calendário de licenças e ausências da empresa** se o intervalo de datas aplicado incluir qualquer dia em que uma solicitação de licença tenha sido negada. |


## <a name="in-preview"></a>Em versão preliminar

Os novos recursos a seguir estão em versão preliminar. Para obter mais informações sobre como ativar ou desativar os recursos, consulte [Gerenciar recursos](hr-admin-manage-features.md).

| Recurso | Liberar planos | Documentação |
| --- | --- | --- |
| Espaço de trabalho de gerenciamento de benefícios | [Espaço de trabalho de gerenciamento de benefícios (versão preliminar)](/dynamics365-release-plan/2020wave2/human-resources/dynamics365-human-resources/benefits-management-workspace) | [Espaço de trabalho de gerenciamento de benefícios](hr-benefits-management-workspace.md) |
| Habilitar integração simplificada da folha de pagamento (APIs de integração de folha de pagamento) | [Habilitar integração simplificada com provedores de folha de pagamento](/dynamics365-release-plan/2021wave1/human-resources/dynamics365-human-resources/enable-simplified-integration-payroll-providers) | [API de integração da folha de pagamento](hr-admin-integration-payroll-api-introduction.md)|
| Habilitar um gerente de ausência para gerenciar a licença | [Habilitar um gerente de ausência para gerenciar a licença](/dynamics365-release-plan/2021wave1/human-resources/dynamics365-human-resources/enable-absence-manager-manage-leave) | Nesta versão, estamos atualizando a exibição do espaço de trabalho do gerente de ausências. Para obter mais informações, consulte [Configurar a função do gerente de ausências](https://go.microsoft.com/fwlink/?linkid=2168107). |
| Configurar requisito de anexo por tipo de licença | [Configurar requisito de anexo por tipo de licença](/dynamics365-release-plan/2021wave1/human-resources/dynamics365-human-resources/mandate-attachments-specific-leave-types) |[Configurar tipos de licença e ausência](https://go.microsoft.com/fwlink/?linkid=2168108)|
| Configurar unidades de licença por tipo de licença | [Configurar unidades de licença por tipo de licença](/dynamics365-release-plan/2021wave1/human-resources/dynamics365-human-resources/configure-leave-units-per-leave-type) |[Configurar tipos de licença e ausência](https://go.microsoft.com/fwlink/?linkid=2168215)|
| Permitir que os funcionários sejam marcados como prontos para serem pagos | [Permitir que os funcionários sejam marcados como prontos para serem pagos](/dynamics365-release-plan/2021wave1/human-resources/dynamics365-human-resources/enable-employees-be-marked-as-ready-pay) | [Pronto para Pagar](/dynamics365/human-resources/hr-compensation-payroll) |

## <a name="coming-soon"></a>Em breve

Para obter uma lista completa de recursos planejados e suas versões agendadas, consulte [Visão geral do Dynamics 365 Human Resources 2021 ciclo de lançamentos 2](/dynamics365-release-plan/2021wave2/human-resources/dynamics365-human-resources/).

| Recurso | Detalhes |
| --- | --- |
| Atualização da plataforma 10.0.21 (45) | A implementação da atualização da plataforma 10.0.21 está agendada para começar na versão de serviço, em 4 de outubro de 2021. Para obter mais informações, consulte [Atualizações de plataforma para a versão 10.0.21 dos aplicativos do Finance and Operations (Outubro de 2021)](/dynamics365/fin-ops-core/dev-itpro/get-started/whats-new-platform-updates-10-0-21). |

## <a name="see-also"></a>Consulte também

[Novidades ou alterações no Human Resources](hr-admin-whats-new.md)</br>
[Visão geral do ciclo de lançamentos 2 de 2021 do Dynamics 365 Human Resources](/dynamics365-release-plan/2021wave2/human-resources/dynamics365-human-resources/)</br>
[Atualizar processo](hr-admin-setup-update-process.md)</br>
[Gerenciar recursos](hr-admin-manage-features.md)

[!INCLUDE[footer-include](../includes/footer-banner.md)]
