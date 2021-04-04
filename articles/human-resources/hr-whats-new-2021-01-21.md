---
title: Novidades ou alterações no Dynamics 365 Human Resources em 21 de janeiro de 2021
description: Este tópico descreve os recursos novos ou alterados no Microsoft Dynamics 365 Human Resources para 21 de janeiro de 2021.
author: marcelbf
manager: tfehr
ms.date: 01/21/2021
ms.topic: article
ms.prod: ''
ms.service: dynamics-human-resources
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: anbichse
ms.search.scope: Human Resources
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: marcelbf
ms.search.validFrom: 2021-01-21
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: fc3bb035686a46030514aca1f5ad03a2681845fd
ms.sourcegitcommit: 6affb3316be757c99e1fe9c7c7b312b93c483408
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/17/2021
ms.locfileid: "5463517"
---
# <a name="whats-new-or-changed-in-dynamics-365-human-resources-january-21-2021"></a>Novidades ou alterações no Dynamics 365 Human Resources em 21 de janeiro de 2021

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

Este tópico descreve recursos que são novos, alterados ou que em breve serão lançados no Dynamics 365 Human Resources.

Para obter mais informações sobre nosso processo de atualização e agenda, consulte [Processo de atualização](hr-admin-setup-update-process.md).

Para obter mais informações sobre novos recursos e suas datas de disponibilidade geral esperadas, consulte [Visão geral do Dynamics 365 Human Resources 2020 ciclo de lançamentos 2](https://docs.microsoft.com/dynamics365-release-plan/2020wave2/human-resources/dynamics365-human-resources/).


## <a name="in-this-release"></a>Nesta versão

Esta versão inclui os novos recursos e correções de bugs a seguir. As alterações se aplicam ao número da compilação 8.1.3866.

### <a name="new-features"></a>Novos recursos

Os seguintes recursos estão geralmente disponíveis nesta versão.

| Recurso | Liberar planos | Documentação |
| --- | --- | --- |
| Platform update 10.0.16(40) | -- | [Atualizações de plataforma para a versão 10.0.16 de aplicativos do Finance and Operations (fevereiro de 2021)](https://docs.microsoft.com/dynamics365/fin-ops-core/dev-itpro/get-started/whats-new-platform-updates-10-0-16) |
| Aprovações e solicitações de fluxo de trabalho avançadas | [Aprimoramentos da experiência de fluxo de trabalho de gerenciamento de organização e pessoal](https://docs.microsoft.com/dynamics365-release-plan/2020wave2/human-resources/dynamics365-human-resources/organization-personnel-management-workflow-experience-enhancements) | [Opção de configuração para posicionar a lista Itens de trabalho atribuídos a mim](https://docs.microsoft.com/dynamics365/human-resources/hr-whats-new-2020-09-03#configuration-option-to-position-work-items-assigned-to-me-list-477004) |
| Atualizações de conformidade à Lei de Serviços de Saúde Acessíveis (ACA) para o formulário 1095-C, formulário 1095-B e relatórios eletrônicos em benefícios herdados | -- | -- | 
| O gerenciamento de benefícios agora oferece suporte a relatórios de conformidade ACA para entidades legais baseadas nos EUA | -- | [Gerar relatórios de ACA no gerenciamento de benefícios](hr-benefits-management-aca-reports.md) |
| O gerenciamento de benefícios agora tem camadas da taxa de benefícios e entidades de camadas duplas da taxa de benefícios expostas  | -- | -- |

### <a name="bug-fixes"></a>Correções de bug

As seguintes correções de bug estão incluídas nessa versão.

> [!NOTE]
> Nosso objetivo é obter essas informações o mais rápido possível. Podemos atualizar este tópico para incluir correções de bugs feitas no build após a publicação inicial deste tópico.

| Número do problema | Problema |  Descrição |
| --- | --- | --- |
| 533079 | Erro de navegação "O formulário foi chamado incorretamente" ao tentar verificar as deduções. | Erro fixo ao verificar as deduções de benefícios com a exibição **A partir da data**. |
| 543641 | O CEP não é preenchido no relatório eletrônico.  | Corrigido um bug interno no CEP que não aparece em relatórios eletrônicos ACA para gerenciamento de benefícios quando o código de cobertura é de M a Q. |
| 542815 | A tela de contato pessoal no Autoatendimento para funcionários permite que os funcionários vejam os contatos pessoais de outros usuários. | Erro fixo no qual o formulário **Editar** para contatos pessoais de Autoatendimento de funcionário não restringe sua consulta o suficiente para garantir que apenas um único contato pessoal seja recuperado, permitindo que um usuário use atalhos de teclado para exibir os contatos de outras pessoas. |
| 536157 | Não é possível abrir a página **Integração do Microsoft Dataverse** na administração do sistema devido à chamada IsVirtualEntityPackageInstalled(). | A questão impede que a página **Integração do Microsoft Dataverse** seja carregada no Human Resources. |
| 533079 | Erro de navegação "O formulário foi chamado incorretamente" ao tentar verificar as deduções. | Ocorre erro fixo no formulário **Deduções** para o gerenciamento de benefícios quando exibido **A partir da data**. |
| 537264 | A FastTab **Informações pessoais** está ausente no registro de candidato. | As informações pessoais do candidato agora estão disponíveis no registro de candidato. |
| 537267 | A **Experiência profissional** não é exibida em registros de candidatos internos. | A FastTab **Experiência profissional** agora é exibida em registros de candidatos internos. Anteriormente, se o candidato era interno, a **Experiência profissional** era substituída pelo **Histórico de emprego**, que é o histórico de emprego do candidato na organização. Os dois são aplicáveis e devem ser exibidos para candidatos internos. |
| 537067 | **Tem permissão para contatar o empregador** não é exibida. | O controle **Tem permissão para contatar o empregador** foi adicionado ao painel **Editar experiência profissional** para um registro de candidato. |
| 525957 | O **Status do candidato** não é atualizado em candidatos internos quando a transferência é concluída. | Quando uma transferência é concluída (o botão **Alterar posição** ou **Continuar** é selecionado na página **Transferir trabalhador para uma nova atribuição de posição**), o **Status** no registro de candidato deve ser alterado para **Contratado**. |
| 537051 | Os símbolos monetários da rúpia indiana e da lira turca não são sincronizados corretamente para o Dataverse | Os símbolos da rúpia indiana e da lira turca agora são sincronizados corretamente para o Dataverse. |
| 534846 | As tabelas de recrutamento devem ser habilitadas para o gerenciamento de dados. | As novas tabelas criadas para recrutar solicitações e candidatos agora estão habilitadas para o gerenciamento de dados. Isso permite que o controle de alterações seja habilitado para as tabelas, permitindo o controle de alterações do OData em tabelas virtuais do Dataverse. |
| 533474 | Corrija a referência ausente para Microsoft.SqlServer.XEvent.dll. | As exceções de carregamento de montagem para Microsoft.SqlServer.XEvent.dll estavam bloqueando a configuração de tabelas virtuais do Dataverse em alguns ambientes. |
| 481122 | Espaço de trabalho **Pessoas** que mostra posições desativadas. | As posições desativadas foram exibidas como posições abertas no espaço de trabalho **Pessoas**. As posições desativadas não são mais exibidas. | 
| 541978 | Adicione o endereço de email principal à entidade BaseWorker. | Essa alteração adicionou o endereço de email principal do trabalhador ao HcmWorkerBaseEntity. |

## <a name="in-preview"></a>Em versão preliminar

Os novos recursos a seguir estão em versão preliminar. Para obter mais informações sobre a ativação e a desativação de recursos, consulte [Gerenciar recursos](hr-admin-manage-features.md).

| Recurso | Plano de versão | Documentação |
| --- | --- | --- |
| Aplicativo Human Resources no Microsoft Teams | [Experiência de licença e ausência de funcionário no Microsoft Teams](https://docs.microsoft.com/dynamics365-release-plan/2020wave1/dynamics365-human-resources/employee-leave-absence-experience-teams) | [Aplicativo Human Resources no Teams](https://go.microsoft.com/fwlink/?linkid=2127841)<br>[Gerenciar solicitações de licença no Teams](hr-teams-leave-app.md) |
| Integração com o LinkedIn Talent Hub | [Integração com o LinkedIn Talent Hub](https://docs.microsoft.com/dynamics365-release-plan/2020wave2/human-resources/dynamics365-human-resources/integration-linkedin-talent-hub) | [Integrar com o LinkedIn Talent Hub](https://docs.microsoft.com/dynamics365/human-resources/hr-admin-integration-linkedin) |
| Exibição de licenças interempresariais para gerentes | [Exibição de licenças interempresariais de funcionários para gerentes](https://docs.microsoft.com/dynamics365-release-plan/2020wave2/human-resources/dynamics365-human-resources/cross-company-view-employee-leave-managers) | [Configurar parâmetros de licença e ausência](https://docs.microsoft.com/dynamics365/human-resources/hr-leave-and-absence-parameters) |
|Fornecer insight adicional sobre saldos de licenças| [Fornecer insight adicional sobre saldos de licenças](https://docs.microsoft.com/dynamics365-release-plan/2020wave2/human-resources/dynamics365-human-resources/provide-additional-insight-into-leave-balances) | [Gerenciar licença de funcionário](https://docs.microsoft.com/dynamics365/human-resources/hr-leave-and-absence-manage-employee-leave) |
| Os gerentes podem enviar solicitações de recrutamento para vagas | [Os gerentes podem enviar uma solicitação de recrutamento para vagas em aberto](https://docs.microsoft.com/dynamics365-release-plan/2020wave2/human-resources/dynamics365-human-resources/manager-submit-request-recruit-open-positions) | [Adicionar uma solicitação de recrutamento](https://docs.microsoft.com/dynamics365/human-resources/hr-personnel-recruit#add-a-recruiting-request) |
| Perfil de candidato avançado no Gerenciamento de pessoal | [Perfil de candidato avançado no gerenciamento de pessoal](https://docs.microsoft.com/dynamics365-release-plan/2020wave2/human-resources/dynamics365-human-resources/enhanced-candidate-profile-personnel-management) | [Adicionar ou editar um perfil de candidato](https://docs.microsoft.com/dynamics365/human-resources/hr-personnel-recruit#add-or-edit-a-candidate-profile) |
| Habilitar integrações simplificadas com provedores de recrutamento | [Habilitar integrações simplificadas com provedores de recrutamento](https://docs.microsoft.com/dynamics365-release-plan/2020wave2/human-resources/dynamics365-human-resources/enable-simplified-integration-recruiting-providers) | [Candidatos de trabalho de recrutamento](https://docs.microsoft.com/dynamics365/human-resources/hr-personnel-recruit) |

## <a name="coming-soon"></a>Em breve
| Recurso | Detalhes |
| --- | --- |
| Confirmação de email para registros de benefícios | Este recurso fornecerá uma opção para enviar um email de confirmação aos funcionários quando eles verificarem as experiências de registro de benefícios no Autoatendimento para funcionários. Para obter mais informações, consulte [Configurar parâmetros de gerenciamento de benefícios por empresa](hr-benefits-setup-parameters-per-company.md). |
| As habilidades inseridas por um gerente para os funcionários podem ser aprovadas automaticamente por um fluxo de trabalho | Em breve. |

Para obter uma lista completa de recursos planejados e suas versões agendadas, consulte [Visão geral do Dynamics 365 Human Resources 2020 ciclo de lançamentos 2](https://docs.microsoft.com/dynamics365-release-plan/2020wave2/human-resources/dynamics365-human-resources/).

## <a name="terminology-updates-for-microsoft-dataverse"></a>Atualizações de terminologia para o Microsoft Dataverse

A partir de novembro de 2020, o Common Data Service foi renomeado para [Microsoft Dataverse](https://docs.microsoft.com/powerapps/maker/data-platform/data-platform-intro). Consulte o [anúncio oficial](https://powerapps.microsoft.com/blog/reshape-the-future-of-work-with-microsoft-dataverse-for-teams-now-generally-available/) no blog do Power Apps para saber mais. Em conjunto com essa alteração de nome, alguma terminologia no Dataverse foi atualizada. Por exemplo, *entidade* agora é *tabela* e *campo* agora é *coluna*. Para obter mais informações, consulte [Atualizações de terminologia](https://docs.microsoft.com/powerapps/maker/data-platform/data-platform-intro#terminology-updates).

Nesta versão, a terminologia relacionada à integração do Dynamics 365 Human Resources com o Dataverse foi atualizada em todo o aplicativo para refletir essas alterações. Por exemplo, o formulário **Integração do Common Data Service** agora é **Integração do Microsoft Dataverse**.

Para saber mais sobre a integração do Dynamics 365 Human Resources com o Microsoft Dataverse, consulte [Configurar a integração do Microsoft Dataverse](https://docs.microsoft.com/dynamics365/human-resources/hr-admin-integration-common-data-service) e [Configurar tabelas virtuais do Microsoft Dataverse](https://docs.microsoft.com/dynamics365/human-resources/hr-admin-integration-common-data-service-virtual-entities).

## <a name="see-also"></a>Consulte também

[Novidades ou alterações no Human Resources](hr-admin-whats-new.md)</br>
[Visão geral do ciclo de lançamentos 2 de 2020 do Dynamics 365 Human Resources](https://docs.microsoft.com/dynamics365-release-plan/2020wave2/human-resources/dynamics365-human-resources/)</br>
[Atualizar processo](hr-admin-setup-update-process.md)</br>
[Gerenciar recursos](hr-admin-manage-features.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]