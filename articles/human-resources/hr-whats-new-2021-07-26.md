---
title: Novidades ou alterações no Dynamics 365 Human Resources – 26 de julho de 2021
description: Este artigo descreve os recursos novos ou alterados no Microsoft Dynamics 365 Human Resources para 26 de julho de 2021.
author: marcelbf
ms.date: 07/12/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: marcelbf
ms.search.validFrom: 2021-07-26
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: 14041dfc753b508a0d68b90ee99d79510d07e622
ms.sourcegitcommit: 28a726b3b0726ecac7620b5736f5457bc75a5f84
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/29/2022
ms.locfileid: "9070070"
---
# <a name="whats-new-or-changed-in-dynamics-365-human-resources-july-26-2021"></a>Novidades ou alterações no Dynamics 365 Human Resources – 26 de julho de 2021

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

Este artigo descreve os recursos novos, alterados ou que serão lançados em breve no Dynamics 365 Human Resources.

Para obter mais informações sobre nosso processo de atualização e agenda, consulte [Processo de atualização](hr-admin-setup-update-process.md).

Para obter mais informações sobre novos recursos e suas datas de disponibilidade geral esperadas, consulte [Visão geral do Dynamics 365 Human Resources 2021 ciclo de lançamentos 2](/dynamics365-release-plan/2021wave2/human-resources/dynamics365-human-resources/).

## <a name="in-this-release"></a>Nesta versão

Esta versão inclui os novos recursos e correções de bugs a seguir. As alterações se aplicam ao número da compilação 8.1.4384.

### <a name="new-features"></a>Novos recursos

Os seguintes recursos estão geralmente disponíveis nesta versão.

| Recurso | Liberar planos | Documentação |
| --- | --- | --- |
| Update 10.0.20 para plataforma | -- | [Atualizações de plataforma para a versão 10.0.20 dos aplicativos de finanças e operações (agosto de 2021)](/dynamics365/fin-ops-core/dev-itpro/get-started/whats-new-platform-updates-10-0-20) |

### <a name="bug-fixes"></a>Correções de bug

As seguintes correções de bug estão incluídas nessa versão.

> [!NOTE]
> Nosso objetivo é obter essas informações o mais rápido possível. Podemos atualizar este artigo para incluir correções de bugs feitas no build após a publicação inicial deste artigo.

| Número do problema | Problema |  Descrição |
| --- | --- | --- |
| 600422 | A validação do endereço da folha de pagamento falha para Pronto para Pagar. | A validação foi atualizada para exigir somente um endereço do tipo 'Local de residência da folha de pagamento' e apenas um endereço do tipo 'Local de trabalho da folha de pagamento'. |
| 601226 | Problema de integração de dados: o projeto de exportação da integração da folha de pagamento não tem a opção para push completo | A integração da folha de pagamento para a Ceridian DayForce estava realizando um push incremental em vez de um push completo. A Ceridian requer sempre uma atualização completa. Esse problema está corrigido agora, as entidades no projeto de exportação de dados não serão mais invertidas para o push incremental. |
| 602272 | Os blocos que foram adicionados ao espaço de trabalho de Autoatendimento para Funcionários estão ausentes, e os blocos não podem mais ser adicionados a ele | Corrigimos o problema de personalização do Autoatendimento para Funcionários. Novos blocos podem ser adicionados à exibição e qualquer personalização existente ficará visível para os usuários |
| 600711 | Campo de seleção de definição de meio dia habilitado para solicitações de licença de dia inteiro | Esse problema está corrigido agora e o campo de definição de meio dia só será habilitado quando os funcionários selecionarem um tipo de licença com a definição de meio dia habilitada e meio dia como o valor selecionado |
| 602208 | Unidades da taxa de acúmulo exibindo horas em vez de dias | Esse problema está corrigido agora. O formulário **Folga** mostrará a unidade de licença (horas ou dias) correta para a coluna **Taxa de acúmulo**. |

## <a name="in-preview"></a>Em versão preliminar

Os novos recursos a seguir estão em versão preliminar. Para obter mais informações sobre a ativação e a desativação de recursos, consulte [Gerenciar recursos](hr-admin-manage-features.md).

| Recurso | Liberar planos | Documentação |
| --- | --- | --- |
| Espaço de trabalho de gerenciamento de benefícios | [Espaço de trabalho de gerenciamento de benefícios (versão preliminar)](/dynamics365-release-plan/2020wave2/human-resources/dynamics365-human-resources/benefits-management-workspace) | [Espaço de trabalho de gerenciamento de benefícios](hr-benefits-management-workspace.md) |
| Habilitar integração simplificada da folha de pagamento (APIs de integração de folha de pagamento) | [Habilitar integração simplificada com provedores de folha de pagamento](/dynamics365-release-plan/2021wave1/human-resources/dynamics365-human-resources/enable-simplified-integration-payroll-providers) | [API de integração da folha de pagamento](hr-admin-integration-payroll-api-introduction.md)|
|  Habilitar um gerente de ausência para gerenciar a licença | [Habilitar um gerente de ausência para gerenciar a licença](/dynamics365-release-plan/2021wave1/human-resources/dynamics365-human-resources/enable-absence-manager-manage-leave) | Com esta versão, estamos atualizando a exibição do espaço de trabalho do gerente de ausências. Para obter mais informações, consulte [Configurar a função do gerente de ausências](https://go.microsoft.com/fwlink/?linkid=2168107).|
|  Configurar requisito de anexo por tipo de licença | [Configurar requisito de anexo por tipo de licença](/dynamics365-release-plan/2021wave1/human-resources/dynamics365-human-resources/mandate-attachments-specific-leave-types) |[Configurar tipos de licença e ausência](https://go.microsoft.com/fwlink/?linkid=2168108)|
|  Configurar unidades de licença por tipo de licença | [Configurar unidades de licença por tipo de licença](/dynamics365-release-plan/2021wave1/human-resources/dynamics365-human-resources/configure-leave-units-per-leave-type) |[Configurar tipos de licença e ausência](https://go.microsoft.com/fwlink/?linkid=2168215)|
| Permitir que os funcionários sejam marcados como prontos para serem pagos | [Permitir que os funcionários sejam marcados como prontos para serem pagos](/dynamics365-release-plan/2021wave1/human-resources/dynamics365-human-resources/enable-employees-be-marked-as-ready-pay) | [Pronto para Pagar](/dynamics365/human-resources/hr-compensation-payroll) |

## <a name="coming-soon"></a>Em breve

Para obter uma lista completa de recursos planejados e suas versões agendadas, consulte [Visão geral do Dynamics 365 Human Resources 2021 ciclo de lançamentos 2](/dynamics365-release-plan/2021wave2/human-resources/dynamics365-human-resources/).

## <a name="see-also"></a>Consulte também

[Novidades ou alterações no Human Resources](hr-admin-whats-new.md)</br>
[Visão geral do ciclo de lançamentos 2 de 2021 do Dynamics 365 Human Resources](/dynamics365-release-plan/2021wave2/human-resources/dynamics365-human-resources/)</br>
[Atualizar processo](hr-admin-setup-update-process.md)</br>
[Gerenciar recursos](hr-admin-manage-features.md)

[!INCLUDE[footer-include](../includes/footer-banner.md)]

