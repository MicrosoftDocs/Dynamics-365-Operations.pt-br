---
title: Novidades ou alterações no Dynamics 365 Human Resources 6 de setembro de 2021
description: Este artigo descreve os recursos novos ou alterados no Microsoft Dynamics 365 Human Resources para 6 de setembro de 2021.
author: marcelbf
ms.date: 09/06/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: marcelbf
ms.search.validFrom: 2021-09-06
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: 03f832a6a3a099c472b781f7e2258ac575127101
ms.sourcegitcommit: 28a726b3b0726ecac7620b5736f5457bc75a5f84
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/29/2022
ms.locfileid: "9069990"
---
# <a name="whats-new-or-changed-in-dynamics-365-human-resources-september-6-2021"></a>Novidades ou alterações no Dynamics 365 Human Resources 6 de setembro de 2021

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

Este artigo descreve os recursos novos, alterados ou que serão lançados em breve no Microsoft Dynamics 365 Human Resources.

Para obter mais informações sobre nosso processo de atualização e agenda, consulte [Processo de atualização](hr-admin-setup-update-process.md).

Para obter mais informações sobre novos recursos e suas datas de disponibilidade geral esperadas, consulte [Visão geral do Dynamics 365 Human Resources 2021 ciclo de lançamentos 2](/dynamics365-release-plan/2021wave2/human-resources/dynamics365-human-resources/).

## <a name="in-this-release"></a>Nesta versão

Esta versão inclui os novos recursos e correções de bugs a seguir. As alterações se aplicam ao número da compilação 8.1.4443.

### <a name="new-features"></a>Novos recursos

Os seguintes recursos estão geralmente disponíveis nesta versão.

| Recurso | Liberar planos | Documentação |
|---|---|---|
| Habilitar um gerente de ausência para gerenciar a licença | [Habilitar um gerente de ausência para gerenciar a licença](/dynamics365-release-plan/2021wave1/human-resources/dynamics365-human-resources/enable-absence-manager-manage-leave) | Nesta versão, estamos atualizando a exibição do espaço de trabalho do gerente de ausências. Para obter mais informações, consulte [Configurar a função do gerente de ausências](https://go.microsoft.com/fwlink/?linkid=2168107). |
| Configurar requisito de anexo por tipo de licença | [Configurar requisito de anexo por tipo de licença](/dynamics365-release-plan/2021wave1/human-resources/dynamics365-human-resources/mandate-attachments-specific-leave-types) | [Configurar tipos de licença e ausência](https://go.microsoft.com/fwlink/?linkid=2168108) |
| Configurar unidades de licença por tipo de licença | [Configurar unidades de licença por tipo de licença](/dynamics365-release-plan/2021wave1/human-resources/dynamics365-human-resources/configure-leave-units-per-leave-type) | [Configurar tipos de licença e ausência](https://go.microsoft.com/fwlink/?linkid=2168215) |

### <a name="bug-fixes"></a>Correções de bug

As seguintes correções de bug estão incluídas nessa versão.

> [!NOTE]
> Nosso objetivo é obter essas informações o mais rápido possível. Podemos atualizar este artigo para incluir correções de bugs feitas no build após a publicação inicial deste artigo.

| Número do problema | Problema | Descrição |
|---|---|---|
| 610128 | Erro ao publicar dados ao usar o HcmDiscussionOverallCommentEntity | Quando os dados são publicados de uma pasta de trabalho do Excel na entidade HcmDiscussionOverralCommentEntity, ocorre o seguinte erro: "Não é possível localizar o registro da fonte de dados do tipo HcmTopicOverrall". |
| 589073 | O relatório EEO-1 conta valores "Não específicos" e vazios para o campo **Sexo** como valor "Feminino". | Se **Masculino** não for especificado para o campo **Sexo**, o relatório EEO-1 gerará um valor padrão **Feminino**. |
| 589617 | Os saldos de Cartão de folga, Disponível para comprar e Disponível para vender não aparecem quando as funções de usuário estão restritas a uma entidade legal específica. | Se o usuário (função de funcionário) for restrito a uma entidade legal específica, os saldos não aparecerão corretamente no cartão **Saldos de folga** e nos campos **Disponível para comprar** e **Disponível para vender**. |
| 604310 | A guia Gerenciador de ausências deve estar oculta quando o usuário não tem hierarquia de ausências atribuída. | Para determinada entidade legal, a guia **Gerenciador de ausências** deve estar oculta no portal de autoatendimento, a menos que o parâmetro interempresarial esteja habilitado e pelo menos uma hierarquia de ausências esteja associada ao usuário. |

## <a name="in-preview"></a>Em versão preliminar

Os novos recursos a seguir estão em versão preliminar. Para obter mais informações sobre como ativar ou desativar os recursos, consulte [Gerenciar recursos](hr-admin-manage-features.md).

| Recurso | Liberar planos | Documentação |
|---|---|---|
| Habilitar integração simplificada da folha de pagamento (APIs de integração de folha de pagamento) | [Habilitar integração simplificada com provedores de folha de pagamento](/dynamics365-release-plan/2021wave1/human-resources/dynamics365-human-resources/enable-simplified-integration-payroll-providers) | [API de integração da folha de pagamento](hr-admin-integration-payroll-api-introduction.md) |
| Espaço de trabalho de gerenciamento de benefícios | [Espaço de trabalho de gerenciamento de benefícios (versão preliminar)](/dynamics365-release-plan/2020wave2/human-resources/dynamics365-human-resources/benefits-management-workspace) | [Espaço de trabalho de gerenciamento de benefícios](hr-benefits-management-workspace.md) |
| Permitir que os funcionários sejam marcados como prontos para serem pagos | [Permitir que os funcionários sejam marcados como prontos para serem pagos](/dynamics365-release-plan/2021wave1/human-resources/dynamics365-human-resources/enable-employees-be-marked-as-ready-pay) | [Pronto para Pagar](/dynamics365/human-resources/hr-compensation-payroll) |
| Campos personalizados na qualificação |[Suporte a campos personalizados no processamento de qualificação](/dynamics365-release-plan/2021wave1/human-resources/dynamics365-human-resources/custom-field-support-benefits-management) | [Usando campos personalizados no processamento de qualificação](/dynamics365/human-resources/hr-benefits-setup-eligibility-rules#using-custom-fields-in-eligibility-rules) |

## <a name="coming-soon"></a>Em breve

Para obter uma lista completa de recursos planejados e suas versões agendadas, consulte [Visão geral do Dynamics 365 Human Resources 2021 ciclo de lançamentos 2](/dynamics365-release-plan/2021wave2/human-resources/dynamics365-human-resources/).

| Recurso | Detalhes |
|---|---|
| Atualização da plataforma 10.0.21 (45) | A implementação da atualização da plataforma 10.0.21 está agendada para começar na versão de serviço, em 4 de outubro de 2021. Para mais informações, consulte [Atualizações de plataforma para a versão 10.0.21 dos aplicativos de finanças e operações (outubro de 2021)](/dynamics365/fin-ops-core/dev-itpro/get-started/whats-new-platform-updates-10-0-21). |
| Demonstrativo de benefícios | Declaração de benefícios para exibir as eleições de benefícios atuais de um funcionário. Para obter mais informações, consulte [Demonstrativo de benefícios](/dynamics365-release-plan/2021wave1/human-resources/dynamics365-human-resources/benefits-summary-statement) no documento de ciclo de lançamentos. |

## <a name="see-also"></a>Consulte também

[Novidades ou mudanças no Human Resources](hr-admin-whats-new.md)</br>
[Visão geral do ciclo de lançamentos 2 de 2021 do Dynamics 365 Human Resources](/dynamics365-release-plan/2021wave2/human-resources/dynamics365-human-resources/)</br>
[Atualizar processo](hr-admin-setup-update-process.md)</br>
[Gerenciar recursos](hr-admin-manage-features.md)

[!INCLUDE[footer-include](../includes/footer-banner.md)]

