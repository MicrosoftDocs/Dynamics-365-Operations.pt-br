---
title: Novidades ou alterações no Dynamics 365 Human Resources (9 de agosto 2021)
description: Este tópico descreve os recursos novos ou alterados no Microsoft Dynamics 365 Human Resources para 9 de agosto de 2021.
author: marcelbf
ms.date: 08/09/2021
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
ms.search.validFrom: 2021-08-09
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: 0f515b614aedce3d58994bf21104ada25702a71e
ms.sourcegitcommit: fc19ee0aba2a6174fef305d151f1eb23ca6c0346
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/13/2021
ms.locfileid: "7385691"
---
# <a name="whats-new-or-changed-in-dynamics-365-human-resources-august-9-2021"></a>Novidades ou alterações no Dynamics 365 Human Resources (9 de agosto 2021)

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

Este tópico descreve recursos que são novos, alterados ou que em breve serão lançados no Microsoft Dynamics 365 Human Resources.

Para obter mais informações sobre nosso processo de atualização e agenda, consulte [Processo de atualização](hr-admin-setup-update-process.md).

Para obter mais informações sobre novos recursos e suas datas de disponibilidade geral esperadas, consulte [Visão geral do Dynamics 365 Human Resources 2021 ciclo de lançamentos 2](/dynamics365-release-plan/2021wave2/human-resources/dynamics365-human-resources/).

## <a name="in-this-release"></a>Nesta versão

Esta versão inclui os novos recursos e correções de bugs a seguir. As alterações se aplicam ao número da compilação 8.1.4393.

### <a name="bug-fixes"></a>Correções de bug

As seguintes correções de bug estão incluídas nessa versão.

> [!NOTE]
> Nosso objetivo é obter essas informações o mais rápido possível. Podemos atualizar este tópico para incluir correções de bugs feitas no build após a publicação inicial deste tópico.

| Número do problema | Problema | descrição |
| --- | --- | --- |
| 558385 | O design padrão não é selecionado quando a opção **Selecionar os representantes de seleção automática** está ativada para os representantes padrão. | Esse problema está corrigido agora. Vários representantes padrão são automaticamente selecionados em planos elegíveis quando a opção **Seleção automática de representantes** na página **Parâmetros compartilhados de recursos humanos** está ativada. |
| 589617 | Na página **Folga**, os saldos **Disponível para compra** e **Disponível para venda** estão em branco quando o acesso é restrito a uma empresa específica. | Esse problema está corrigido agora. A página **Folga**, mostra os saldos **Disponível para compra** e **Disponível para venda** corretos quando o usuário é restrito a uma empresa específica. |

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
