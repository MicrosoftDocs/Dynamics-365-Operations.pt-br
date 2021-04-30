---
title: Novidades ou alterações no Dynamics 365 Human Resources em 28 de janeiro de 2021
description: Este tópico descreve os recursos novos ou alterados no Microsoft Dynamics 365 Human Resources para 28 de janeiro de 2021.
author: marcelbf
ms.date: 01/28/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: anbichse
ms.search.scope: Human Resources
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: marcelbf
ms.search.validFrom: 2021-01-28
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: 4fbf3034805146c3900b46f5ccce76e63b0805a4
ms.sourcegitcommit: 951393b05bf409333cb3c7ad977bcaa804aa801b
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/13/2021
ms.locfileid: "5893068"
---
# <a name="whats-new-or-changed-in-dynamics-365-human-resources-january-28-2021"></a>Novidades ou alterações no Dynamics 365 Human Resources em 28 de janeiro de 2021

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

Este tópico descreve recursos que são novos, alterados ou que em breve serão lançados no Dynamics 365 Human Resources.

Para obter mais informações sobre nosso processo de atualização e agenda, consulte [Processo de atualização](hr-admin-setup-update-process.md).

Para obter mais informações sobre novos recursos e suas datas de disponibilidade geral esperadas, consulte [Visão geral do Dynamics 365 Human Resources 2021 ciclo de lançamentos 1](/dynamics365-release-plan/2021wave1/human-resources/dynamics365-human-resources/).

## <a name="in-this-release"></a>Nesta versão

Esta versão inclui os novos recursos e correções de bugs a seguir. As alterações se aplicam ao número da compilação 8.1.3906.

### <a name="new-features"></a>Novos recursos

Os seguintes recursos estão geralmente disponíveis nesta versão.

| Recurso | Liberar planos | Documentação |
| --- | --- | --- |
| Integrar códigos de motivo de benefício no espaço de trabalho **Gerenciamento de pessoal** | -- | [Configurar códigos de motivo](hr-benefits-setup-reason-codes.md) |

### <a name="bug-fixes"></a>Correções de bug

As seguintes correções de bug estão incluídas nessa versão.

> [!NOTE]
> Nosso objetivo é obter essas informações o mais rápido possível. Podemos atualizar este tópico para incluir correções de bugs feitas no build após a publicação inicial deste tópico.


| Número do problema | Problema |  descrição |
| --- | --- | --- |
| 539456 | O calendário mostra o tipo de licença no foco do texto quando **Mostrar somente ausência sem detalhes** está habilitado. | Quando a opção **Mostrar apenas ausências sem detalhes** estiver habilitada, a data da solicitação será exibida ao ser focalizada. |
| 528907 | A concessão de acesso a uma entidade legal em resultados da função de funcionário em gerentes que não podem ver a atividade de saldo de licença para os funcionários na área **Minha equipe** do Autoatendimento para funcionários. |A definição dessa opção agora permite que os gerentes continuem a ver a atividade de saldo de licença. |
| 526280 | Erro de permissões em HcmWorkerEntity, HcmEmployeeEntity e HcmContractorEntity. | Os usuários em uma função de administrador não pertencente ao sistema não puderam exportar as entidades listadas devido a um erro de permissão no campo NationalityCountryRegion. Os usuários continuarão precisando dos seguintes privilégios para exportar essas informações: HcmWorkerEntityMaintain, HcmWorkerEntityView, HcmEmployeeEntityMaintain, HcmEmployeeEntityMaintain, HcmEmployeeEntityView, HcmContractorEntityMaintain e HCMContractorEntityView. |
| 542147 | Os campos **Número da conta bancária** e **Número identificador do banco** são obrigatórios ao adicionar uma conta bancária via Autoatendimento para funcionários. | Corrigimos o erro em que os funcionários eram solicitados a inserir os campos **Número da conta bancária** e **Número identificador do banco** ao adicionar detalhes da conta bancária. Esses campos não são mais obrigatórios ao salvar as novas informações de conta bancária. |
| 543641 | O CEP não é preenchido no relatório eletrônico. | Corrigido um bug no qual o CEP não foi preenchido no relatório de ACA para códigos de cobertura de L a Q. |
| 545402 | Adicione a alteração de roteamento do arquivo UserBranding.js para remover erros 404. | O usuário não deve ver mais erros 404 no console. |

## <a name="in-preview"></a>Em versão preliminar   

Os novos recursos a seguir estão em versão preliminar. Para obter mais informações sobre a ativação e a desativação de recursos, consulte [Gerenciar recursos](hr-admin-manage-features.md).

| Recurso | Plano de versão | Documentação |
| --- | --- | --- |
| Aplicativo Human Resources no Microsoft Teams | [Experiência de licença e ausência de funcionário no Microsoft Teams](/dynamics365-release-plan/2020wave1/dynamics365-human-resources/employee-leave-absence-experience-teams) | [Aplicativo Human Resources no Teams](./hr-admin-teams-leave-app.md)<br>[Gerenciar solicitações de licença no Teams](hr-teams-leave-app.md) |
| Exibição de licenças interempresariais para gerentes | [Exibição de licenças interempresariais de funcionários para gerentes](/dynamics365-release-plan/2020wave2/human-resources/dynamics365-human-resources/cross-company-view-employee-leave-managers) | [Configurar parâmetros de licença e ausência](./hr-leave-and-absence-parameters.md) |

## <a name="coming-soon"></a>Em breve

| Recurso | Detalhes |
| --- | --- |
| Confirmação de email para registros de benefícios | Este recurso fornecerá uma opção para enviar um email de confirmação aos funcionários quando eles verificarem as experiências de registro de benefícios no Autoatendimento para funcionários. Este recurso estará disponível em 1º de fevereiro. Para obter mais informações, consulte [Configurar parâmetros de gerenciamento de benefícios por empresa](hr-benefits-setup-parameters-per-company.md). |
| As habilidades inseridas por um gerente para os funcionários podem ser aprovadas automaticamente por um fluxo de trabalho | Em breve. |

Para obter uma lista completa de recursos planejados e suas versões agendadas, consulte [Visão geral do Dynamics 365 Human Resources 2021 ciclo de lançamentos 1](/dynamics365-release-plan/2021wave1/human-resources/dynamics365-human-resources/).

## <a name="terminology-updates-for-microsoft-dataverse"></a>Atualizações de terminologia para o Microsoft Dataverse

A partir de novembro de 2020, o Common Data Service foi renomeado para [Microsoft Dataverse](/powerapps/maker/data-platform/data-platform-intro). Consulte o [anúncio oficial](https://powerapps.microsoft.com/blog/reshape-the-future-of-work-with-microsoft-dataverse-for-teams-now-generally-available/) no blog do Power Apps para saber mais. Em conjunto com essa alteração de nome, alguma terminologia no Dataverse foi atualizada. Por exemplo, *entidade* agora é *tabela* e *campo* agora é *coluna*. Para obter mais informações, consulte [Atualizações de terminologia](/powerapps/maker/data-platform/data-platform-intro#terminology-updates).

Nesta versão, a terminologia relacionada à integração do Dynamics 365 Human Resources com o Dataverse foi atualizada em todo o aplicativo para refletir essas alterações. Por exemplo, o formulário **Integração do Common Data Service** agora é **Integração do Microsoft Dataverse**.

Para saber mais sobre a integração do Dynamics 365 Human Resources com o Microsoft Dataverse, consulte [Configurar a integração do Microsoft Dataverse](./hr-admin-integration-common-data-service.md) e [Configurar tabelas virtuais do Microsoft Dataverse](./hr-admin-integration-common-data-service-virtual-entities.md).

## <a name="see-also"></a>Consulte também

[Novidades ou alterações no Human Resources](hr-admin-whats-new.md)</br>
[Visão geral do ciclo de lançamentos 1 de 2021 do Dynamics 365 Human Resources](/dynamics365-release-plan/2021wave1/human-resources/dynamics365-human-resources/)</br>
[Atualizar processo](hr-admin-setup-update-process.md)</br>
[Gerenciar recursos](hr-admin-manage-features.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]