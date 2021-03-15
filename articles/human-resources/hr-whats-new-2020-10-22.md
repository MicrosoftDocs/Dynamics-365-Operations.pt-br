---
title: Novidades ou alterações no Dynamics 365 Human Resources 22 de outubro de 2020
description: Este tópico descreve os recursos novos ou alterados no Microsoft Dynamics 365 Human Resources para 22 de outubro de 2020.
author: jcart1106
manager: tfehr
ms.date: 10/22/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-human-resources
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: anbichse
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: jcart
ms.search.validFrom: 2020-10-20
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: 41b4e92720c6a9f830d940900c3c6e5b0a173de0
ms.sourcegitcommit: f8bac7ca2803913fd236adbc3806259a17a110f4
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/06/2021
ms.locfileid: "5130822"
---
# <a name="whats-new-or-changed-in-dynamics-365-human-resources-october-22-2020"></a>Novidades ou alterações no Dynamics 365 Human Resources 22 de outubro de 2020

[!include [rename-banner](~/includes/cc-data-platform-banner.md)]

Este tópico descreve recursos que são novos, alterados ou que em breve serão lançados no Dynamics 365 Human Resources. Para obter mais informações sobre nosso processo de atualização e agenda, consulte [Processo de atualização](hr-admin-setup-update-process.md).

Para obter mais informações sobre novos recursos e suas datas de disponibilidade geral esperadas, consulte [Visão geral do Dynamics 365 Human Resources 2020 ciclo de lançamentos 2](https://docs.microsoft.com/dynamics365-release-plan/2020wave2/human-resources/dynamics365-human-resources/).

## <a name="in-this-release"></a>Nesta versão

Esta versão inclui os novos recursos e correções de bugs a seguir. As alterações se aplicam ao número da compilação 8.1.3680.

### <a name="new-features"></a>Novos recursos

Os seguintes recursos estão geralmente disponíveis nesta versão.

| Recurso | Liberar planos | Documentação |
| --- | --- | --- |
| Platform update 10.0.14(38) | -- | [Atualizações de plataforma para a versão 10.0.14 de aplicativos do Finance and Operations (novembro de 2020)](https://docs.microsoft.com/dynamics365/fin-ops-core/dev-itpro/get-started/whats-new-platform-updates-10-0-14) |
| Aprimoramentos da experiência de fluxo de trabalho de gerenciamento de organização e pessoal | [Aprimoramentos da experiência de fluxo de trabalho de gerenciamento de organização e pessoal](https://docs.microsoft.com/dynamics365-release-plan/2020wave2/human-resources/dynamics365-human-resources/organization-personnel-management-workflow-experience-enhancements) | [Opção de configuração para a lista Posicionar itens de trabalho atribuídos a mim](https://docs.microsoft.com/dynamics365/human-resources/hr-whats-new-2020-09-03#configuration-option-to-position-work-items-assigned-to-me-list-477004) |


### <a name="bug-fixes"></a>Correções de bug

As seguintes correções de bug estão incluídas nessa versão.

> [!NOTE]
> Nosso objetivo é obter essas informações o mais rápido possível. Podemos atualizar este tópico para incluir correções de bugs feitas no build após a publicação inicial deste tópico.

| Número do problema| Problema  | descrição|
| --- | --- | --- |
| 437922 | A importação de horas de FMLA usando a entidade DMF resulta em um erro somente leitura. | O uso da entidade Horas de FMLA para importar horas associadas a um caso de FMLA falhou. Adicionamos lógica para garantir que as horas importadas não ultrapassem as horas restantes para o caso. |
| 512019 | Valor incorreto de **Último postergar**. | Na página **Folga**, a alteração de **A partir da data** para o primeiro dia do próximo período fiscal exibiu um valor de **Último postergar** para o tipo **Licença anual**. Agora ele exibe o valor correto. |
| 458639 | A entidade **Contatos do trabalhador** não dá suporte ao modo de controle de alterações. | Atualizamos a entidade **Contatos do trabalhador** para que você possa usá-la em cenários de BYOD (traga seu próprio banco de dados).|
| 505347 | Os gerentes de treinamento podem enviar uma solicitação de licença para um funcionário quando o recurso Trabalhador simplificado tiver sido habilitado. | Funções que não sejam Assistente de RH e Gerente de RH não têm permissão para enviar solicitações de folga para funcionários. |
| 513490 | Log de gerenciamento de benefícios: adicionar log de planos sem opções de cobertura. | Habilitamos o log de resultados para o **Plano sem opções de cobertura**. Agora, eles são exibidos na tabela **Resultados do processo** e são classificados corretamente para serem exibidos na parte superior. |
| 517021 | Não é possível selecionar vários planos com o mesmo código de **Tipo de plano** se o **Tipo de plano** tiver um registro por tipo. | Alteramos as restrições para a seleção de planos em que apenas um registro é permitido. As restrições agora estão no nível de **Código de tipo de plano**, em vez de **Tipo de plano**. Essa alteração permite planos como HSA e FSA, que são os dois tipos, mas você pode fornecer a eles um **Código de tipo de plano** separado. Dessa forma, você pode selecionar ambos para o mesmo período de inscrição. |
| 444791 | Não é possível exibir a remuneração no Autoatendimento para funcionários quando **Restringir acesso** está ativado no Plano de remuneração. | No cartão **Remuneração** do Autoatendimento para funcionários, o valor de remuneração atual e o percentual de aumento exibiam "0" se o funcionário tivesse sido inscrito em um plano com **Acesso restrito** ativado e atribuído a funções específicas. Resolvemos esse problema para que o funcionário e o gerente sempre possam ver detalhes de remuneração por conta própria e ver a de seus subordinados diretos. |
| 457542 | Atualizar detalhes do curso depois que o curso é fechado também não atualiza as mesmas informações para o funcionário que fez o curso. | As informações do funcionário agora são atualizadas corretamente quando você altera os detalhes do curso depois que um curso é fechado e reaberto. |
| 515342 | Não é possível inserir dados por meio de **CDSLeaveRequestDetailEntity**. A empresa não é encontrada ou não existe. | Agora você pode usar **CDSLeaveRequestDetailEntity** para inserir dados. |
| 514743 | Erro no formulário **Parâmetro de email** ao usar o Microsoft Exchange. | A mensagem "Não foi possível carregar os arquivos ou o assembly..." exibida na página **Parâmetros de email** quando o provedor de email foi definido como **Exchange**. Essa correção também permite que a página **Parâmetros de email** seja carregada e salva conforme o esperado. |


## <a name="in-preview"></a>Em visualização

Os novos recursos a seguir estão em versão preliminar. Para obter mais informações sobre a ativação e a desativação de recursos, consulte [Gerenciar recursos](hr-admin-manage-features.md).

| Recurso | Liberar planos | Documentação |
| --- | --- | --- |
| Aplicativo Human Resources no Microsoft Teams | [Experiência de licença e ausência de funcionário no Microsoft Teams](https://docs.microsoft.com/dynamics365-release-plan/2020wave1/dynamics365-human-resources/employee-leave-absence-experience-teams) | [Aplicativo Human Resources no Teams](https://go.microsoft.com/fwlink/?linkid=2127841)<br>[Gerenciar solicitações de licença no Teams](hr-teams-leave-app.md) |
| Aprovações e solicitações de fluxo de trabalho avançadas | [Aprimoramentos da experiência de fluxo de trabalho de gerenciamento de organização e pessoal](https://docs.microsoft.com/dynamics365-release-plan/2020wave2/human-resources/dynamics365-human-resources/organization-personnel-management-workflow-experience-enhancements) | [Opção de configuração para posicionar a lista Itens de trabalho atribuídos a mim](https://docs.microsoft.com/dynamics365/human-resources/hr-whats-new-2020-09-03#configuration-option-to-position-work-items-assigned-to-me-list-477004) |
| Entidades virtuais no Dataverse para Human Resources | [Expandir dados principais do Dynamics 365 Human Resources no Dataverse](https://docs.microsoft.com/dynamics365-release-plan/2020wave2/human-resources/dynamics365-human-resources/expand-dynamics-365-human-resources-core-data-common-data-service) | [Configurar entidades virtuais do Dataverse](hr-admin-integration-common-data-service-virtual-entities.md) |
| Integração com o LinkedIn Talent Hub | [Integração com o LinkedIn Talent Hub](https://docs.microsoft.com/dynamics365-release-plan/2020wave2/human-resources/dynamics365-human-resources/integration-linkedin-talent-hub) | [Integrar com o LinkedIn Talent Hub](https://docs.microsoft.com/dynamics365/human-resources/hr-admin-integration-linkedin) |
| Links personalizados no Autoatendimento para gerentes | [Links personalizados no autoatendimento para gerentes](https://docs.microsoft.com/dynamics365-release-plan/2020wave2/human-resources/dynamics365-human-resources/custom-links-manager-self-service) | [Links personalizados no autoatendimento para gerentes](https://aka.ms/MSSCustomLinks) |

## <a name="coming-soon"></a>Em breve

Para obter uma lista completa de recursos planejados e suas versões agendadas, consulte [Visão geral do Dynamics 365 Human Resources 2020 ciclo de lançamentos 2](https://docs.microsoft.com/dynamics365-release-plan/2020wave2/human-resources/dynamics365-human-resources/).


## <a name="see-also"></a>Consulte também

[Novidades ou alterações no Human Resources](hr-admin-whats-new.md)</br>
[Visão geral do ciclo de lançamentos 2 de 2020 do Dynamics 365 Human Resources](https://docs.microsoft.com/dynamics365-release-plan/2020wave2/human-resources/dynamics365-human-resources/)</br>
[Atualizar processo](hr-admin-setup-update-process.md)</br>
[Gerenciar recursos](hr-admin-manage-features.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]