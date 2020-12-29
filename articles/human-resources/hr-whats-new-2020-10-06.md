---
title: Novidades ou alterações no Dynamics 365 Human Resources (6 de outubro de 2020)
description: Este tópico descreve os recursos novos ou alterados no Microsoft Dynamics 365 Human Resources para 6 de outubro de 2020.
author: jcart1106
manager: tfehr
ms.date: 10/06/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-talent
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: anbichse
ms.search.scope: Human Resources
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: jcart
ms.search.validFrom: 2020-10-06
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: fe01a2b82b72bf38bb537ed7b2bf5560235817d9
ms.sourcegitcommit: e89bb3e5420a6ece84f4e80c11e360b4a042f59d
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/17/2020
ms.locfileid: "4529819"
---
# <a name="whats-new-or-changed-in-dynamics-365-human-resources-october-6-2020"></a>Novidades ou alterações no Dynamics 365 Human Resources (6 de outubro de 2020)

[!include [rename-banner](~/includes/cc-data-platform-banner.md)]

Este tópico descreve recursos que são novos, alterados ou que em breve serão lançados no Dynamics 365 Human Resources. Para obter mais informações sobre nosso processo de atualização e agenda, consulte [Processo de atualização](hr-admin-setup-update-process.md).

Para obter mais informações sobre novos recursos e suas datas de disponibilidade geral esperadas, consulte [Visão geral do Dynamics 365 Human Resources 2020 ciclo de lançamentos 2](https://docs.microsoft.com/dynamics365-release-plan/2020wave2/dynamics365-human-resources/).

## <a name="in-this-release"></a>Nesta versão

Esta versão inclui os novos recursos e correções de bugs a seguir. As alterações se aplicam ao número da compilação 8.1.3636.

### <a name="new-features"></a>Novos recursos

O seguinte recurso está geralmente disponível nesta versão.

| Recurso | Liberar planos | Documentação |
| --- | --- | --- |
| Insight adicional sobre calendários de licenças | [Fornecer insight adicional sobre exibições de calendário de licenças](https://docs.microsoft.com/dynamics365-release-plan/2020wave2/human-resources/dynamics365-human-resources/provide-additional-insight-leave-calendar-views) | [Exibir calendário da equipe e da empresa](hr-employee-self-service-calendar.md) |

### <a name="bug-fixes"></a>Correções de bug

As seguintes correções de bug estão incluídas nessa versão.

>[!NOTE]
> Nosso objetivo é obter essas informações para você o mais rápido possível. Este tópico poderá ser atualizado para incluir correções de bugs feitas no build após a publicação inicial deste tópico.

| Número do problema | Problema | descrição |
| --- | --- | --- |
| 448806 | **Tipo de Identificação Padrão** é exportado como **RecID** nos parâmetros do HCM | Essa alteração na entidade de parâmetros do Human Resources adiciona uma coluna adicional que exibe o **Tipo de Identificação Padrão**. |
| 492923 | Os registros de tarefas não estão sendo salvos no Lifecycle Services (LCS) | Agora, as gravações de tarefas podem ser salvas no LCS. |
| 429950 | A remuneração fixa não expira corretamente ao alterar a posição | Ao alterar a posição de um trabalhador na página **Transferir Trabalhador**, a data de remuneração final foi definida em um dia antes do término da posição. A data de término de remuneração agora é igual à data de término da posição. |
| 467214 | **Análise salarial** só será exibida se **Nome de conversão da taxa de pagamento** estiver definido como **Anual** | As taxas de pagamento de assalariado com um nome diferente de **Anual** não eram mostradas na Análise de Remuneração. Com essa atualização, a Análise de Remuneração usa agora todas as conversões de taxa de pagamento. Ao executar os relatórios por **Por hora** ou **Salário**, qualquer conversão de taxa de pagamento que use um período diferente de por hora será incluída no filtro **Salário** . Somente as taxas de pagamento com um período **Por hora** são incluídas no filtro **Por hora** . |
| 482464 | Ao exibir **Revisões**, a exibição **Detalhes** não é alterada para a exibição de grade após a aplicação de um filtro | Depois de aplicar um filtro, a grade de revisões é exibida conforme o esperado. |
| 483184 | O Human Resources não gera acúmulos de licenças quando você seleciona **Base da camada** como a **Data de início ajustada** em **Registro da licença** |A **Data de início ajustada** é preenchida e usada durante a geração de acúmulos de licenças.  |
| 509731 | A solicitação de folga para futuro trabalhador demitido causará um problema se ele solicitar uma folga após a data de demissão | As solicitações de folga agora podem ser enviadas para funcionários com uma data de demissão futura, desde que a solicitação seja anterior à data de demissão. |
| 510716 | A Análise de Remuneração inclui os funcionários homens e mulheres em **Média de pagamentos por hora para homens** | Na Análise de Remuneração, a **Média de pagamentos por hora para homens** na **Análise Demográfica de Remuneração** incluía a média de pagamentos para mulheres. Agora ele inclui apenas homens. |
| 511348 | O autoatendimento de benefícios deve mostrar apenas planos de benefícios válidos de hoje até o final do período de benefícios | Os planos de benefícios expirados foram exibidos para os funcionários na página **Registro de benefícios**. Essa correção remove esses planos. |
| 512706 | Defina os campos a seguir como somente leitura:<ul><li>BenefitPlanEmployeeEntity</li><li>EnrollmentConfirmed</li><li>EnrollmentConfirmedBy</li><li>EnrollmentConfirmedDateTime | Os botões **Adicionar** e **Remover** para detalhes de dimensão foram habilitados incorretamente após a conclusão da ação. Essa atualização para a página de **Detalhes da Ação de Posição** torna os campos não editáveis após a conclusão da ação. |

## <a name="in-preview"></a>Em visualização

Os novos recursos a seguir estão em versão preliminar. Para obter mais informações sobre a ativação e a desativação de recursos, consulte [Gerenciar recursos](hr-admin-manage-features.md).

| Recurso | Liberar planos | Documentação |
| --- | --- | --- |
| Aplicativo Human Resources no Microsoft Teams | [Experiência de licença e ausência de funcionário no Microsoft Teams](https://docs.microsoft.com/dynamics365-release-plan/2020wave1/dynamics365-human-resources/employee-leave-absence-experience-teams) | [Aplicativo Human Resources no Teams](https://go.microsoft.com/fwlink/?linkid=2127841)<br>[Gerenciar solicitações de licença no Teams](hr-teams-leave-app.md) |
| Aprovações e solicitações de fluxo de trabalho avançadas | [Aprimoramentos da experiência de fluxo de trabalho de gerenciamento de organização e pessoal](https://docs.microsoft.com/dynamics365-release-plan/2020wave2/human-resources/dynamics365-human-resources/organization-personnel-management-workflow-experience-enhancements) | [Opção de configuração para posicionar a lista Itens de trabalho atribuídos a mim](https://docs.microsoft.com/dynamics365/human-resources/hr-whats-new-2020-09-03#configuration-option-to-position-work-items-assigned-to-me-list-477004) |
| Entidades virtuais no Common Data Service para Human Resources | [Expandir dados principais do Dynamics 365 Human Resources no Common Data Service](https://docs.microsoft.com/dynamics365-release-plan/2020wave2/human-resources/dynamics365-human-resources/expand-dynamics-365-human-resources-core-data-common-data-service) | [Configurar entidades virtuais do Common Data Service](hr-admin-integration-common-data-service-virtual-entities.md) |

## <a name="coming-soon"></a>Em breve

Estes recursos novos estão agendados para versões futuras:

- **Entidades de lista de verificação incluídas no Common Data Service**: entidades de lista de verificação para Integração, Remoção, Transferências e Processos empresariais estarão disponíveis em breve no Common Data Service.

- **Códigos de motivo de gerenciamento de benefícios**: os códigos de motivo de gerenciamento de benefícios serão em breve combinados com os códigos de motivo existentes no Human Resources. Se você tiver criado códigos de motivo no gerenciamento de benefícios com mais de 15 caracteres, deverá alterar o nome do código de motivo no formulário **Códigos de motivo** de gerenciamento de benefícios para 15 caracteres ou menos. Depois de atualizar o nome, o código de motivo aparecerá no formulário de código de motivo existente em Gerenciamento de pessoal. Esta alteração estará disponível no futuro e não afetará a funcionalidade existente.

- **Links personalizados em Autoatendimento para gerentes**: para oferecer suporte a gerentes, estamos expandindo recursos no Autoatendimento para gerentes. Estamos adicionando a capacidade de adicionar links personalizados à guia **Minha equipe**. Esse recurso é semelhante ao recurso de links personalizados na guia **Minhas informações** do autoatendimento para funcionários. Para obter mais informações, consulte [Links personalizados no autoatendimento para gerentes](https://docs.microsoft.com/dynamics365-release-plan/2020wave2/human-resources/dynamics365-human-resources/custom-links-manager-self-service).

Para obter uma lista completa de recursos planejados e suas versões agendadas, consulte [Visão geral do Dynamics 365 Human Resources 2019 ciclo de lançamentos 2](https://docs.microsoft.com/dynamics365-release-plan/2019wave2/dynamics365-human-resources/).

## <a name="additional-resources"></a>Recursos adicionais

[Novidades ou alterações no Human Resources](hr-admin-whats-new.md)</br>
[Visão geral do ciclo de lançamentos 2 de 2020 do Dynamics 365 Human Resources](https://docs.microsoft.com/dynamics365-release-plan/2020wave2/dynamics365-human-resources/)</br>
[Atualizar processo](hr-admin-setup-update-process.md)</br>
[Gerenciar recursos](hr-admin-manage-features.md)
