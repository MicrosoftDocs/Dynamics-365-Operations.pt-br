---
title: Novidades ou alterações no Dynamics 365 Human Resources (20 de agosto 2020)
description: Este tópico descreve os recursos novos ou alterados no Microsoft Dynamics 365 Human Resources para 20 de agosto de 2020.
author: andreabichsel
ms.date: 08/20/2020
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
ms.author: jaredha
ms.search.validFrom: 2020-08-20
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: 69304cbffafa4c20dbbbb31d5c19920f669761b9
ms.sourcegitcommit: 3cdc42346bb653c13ab33a7142dbb7969f1f6dda
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/31/2021
ms.locfileid: "5800156"
---
# <a name="whats-new-or-changed-in-dynamics-365-human-resources-august-20-2020"></a>Novidades ou alterações no Dynamics 365 Human Resources (20 de agosto 2020)

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

[!include [rename-banner](~/includes/cc-data-platform-banner.md)]

Este tópico descreve recursos que são novos ou foram alterados no Dynamics 365 Human Resources. As alterações se aplicam ao número da compilação 8.1.3478. Os números entre parênteses em alguns cabeçalhos referem-se aos números de suporte do Lifecycle Services (LCS) para referência.

## <a name="show-upcoming-and-pending-leave-of-absence-information-to-cards-in-people-workspace"></a>Mostrar informações de licença futura e pendente para cartões no espaço de trabalho Pessoas

As opções de solicitação de licença pendentes e futuras agora estão disponíveis nos cartões de licença e ausência no espaço de trabalho **Pessoas**.

## <a name="private-field-isnt-yes-by-default-for-employee-role-in-employee-self-service-477106"></a>O campo particular não é Sim por padrão para a função Funcionário no Autoatendimento para funcionários (477106)

O campo **Privado** agora é padronizado como **Sim** quando os funcionários adicionam novos registros de endereço usando a página **Informações pessoais** no Autoatendimento para funcionários. 

## <a name="candidates-to-hire-fasttab-in-personnel-management-shows-an-incorrect-count-of-candidates-470110"></a>A guia rápida Candidatos a serem contratados no Gerenciamento de pessoal mostra uma contagem incorreta de candidatos (470110)

A página **Gerenciamento de pessoal** agora exibe com precisão o número de candidatos a serem contratados. 

## <a name="cant-enter-sickness-for-terminated-employee-when-accrual-is-set-to-zero-446195"></a>Não é possível inserir doença para funcionário demitido quando a competência estiver definida como zero (446195)

As transações de licença agora são permitidas no futuro para funcionários que foram demitidos e a acumulação é definida como zero. As transações de licença podem ser inseridas até a data de demissão do funcionário. 

## <a name="adding-custom-fields-to-the-new-worker-form-disables-the-fields-in-the-action-pane-for-manage-leave-473314"></a>A adição de campos personalizados ao formulário do novo trabalhador desativa os campos no painel de ação para Gerenciar licença (473314)

As opções do painel de ação no novo formulário do **Trabalhador** em **Gerenciar licença** não será desativada se os campos personalizados forem adicionados ao formulário do novo **Trabalhador**.

## <a name="making-the-leave-comment-field-mandatory-allows-a-leave-request-to-be-submitted-when-no-comment-is-entered-473543"></a>Tornar o campo de comentário da Licença obrigatório permite que uma solicitação de licença seja enviada quando nenhum comentário for inserido (473543)

Os campos de comentário agora podem ser obrigatórios e as solicitações de licença honram essa configuração. Os campos obrigatórios são um recurso de visualização.

### <a name="dmf-entity-available-for-accrual-suspensions"></a>Entidade DMF disponível para suspensões de acúmulos

Uma entidade DMF disponível para suspensões de acúmulos.

## <a name="in-preview"></a>Em visualização

### <a name="mandatory-fields"></a>Campos obrigatórios

Você pode tornar campos obrigatórios usando recursos de personalização de Recursos Humanos. Este recurso exige **Exibições salvas**. Para obter mais informações sobre exibições salvas, consulte:

- [Exibições salvas - disponibilidade geral](https://docs.microsoft.com/dynamics365-release-plan/2020wave2/finance-operations/finance-operations-crossapp-capabilities/saved-views--general-availability) no plano do Dynamics 365 versão 2020 onda 2
- [Criar formulários que utilizam totalmente as exibições salvas](https://docs.microsoft.com/dynamics365/fin-ops-core/dev-itpro/user-interface/understanding-saved-views)

### <a name="human-resources-application-in-teams"></a>Aplicativo Human Resources no Teams

Os funcionários podem exibir e solicitar tempo fora do trabalho no Microsoft Teams. Eles podem interagir com um bot para criar solicitações de licença. Para obter mais informações, consulte:

- [Licença e ausência do funcionário no Microsoft Teams](https://docs.microsoft.com/dynamics365-release-plan/2020wave1/dynamics365-human-resources/employee-leave-absence-experience-teams) no plano do Dynamics 365 versão 2020 onda 1
- [Aplicativo Human Resources no Teams](https://go.microsoft.com/fwlink/?linkid=2127841)

## <a name="coming-soon"></a>Em breve

### <a name="human-resources-app-in-teams-preview-features"></a>Aplicativo Recursos Humanos nos recursos de visualização do Teams
 
-  **Notificações**: os remetentes e aprovadores de solicitações de folga serão notificados no aplicativo de Recursos Humanos no Teams. Os aprovadores poderão aprovar ou negar solicitações de folga, e os remetentes serão notificados, caso a solicitação tenha sido aprovada ou negada.
 
- **Calendário de folga do gerente**: Os gerentes poderão ver o tempo de folga aprovado e pendente para seus subordinados direto em um modo de exibição de calendário. Esta exibição fornece uma compreensão fácil de quando os membros da equipe estão ausente do trabalho.

### <a name="checklist-entities-included-in-dataverse"></a>Entidades de lista de verificação incluídas no Dataverse

Entidades de lista de verificação relativas a Integração, Remoção, Transferências e Processos empresariais estarão disponíveis em breve no Dataverse.

## <a name="known-issues"></a>Problemas conhecidos

O espaço de trabalho **Gerenciamento de recursos** pode estar exibindo recursos que estão desabilitados como recursos de visualização quando estão geralmente disponíveis. A seguir, é exibida uma lista de recursos geralmente disponíveis que mostram um status incorreto. 

- Gerenciamento de benefícios
- Gerenciamento de casos
- Log de banco de dados (auditoria)
- Acúmulo de licenças para uma única empresa ou um único plano
- Suspensão de acúmulo de licença e ausência
- Código de motivo de ajuste de saldo e comentário
- Comprar e vender licenças
- Calendário de licenças e ausências
- Regras de postergação de licença
- Auditoria de acúmulo de licenças
- Exclusão de acúmulo de licenças
- Arredondamento do acúmulo de licenças
- Configurar vários tipos de licença em um único plano de licença
- Atualizar aprimoramentos de folgas
- Usar o FTE de um funcionário para acúmulos
- Exibição da remuneração interempresarial
- Imprima avaliações de desempenho
- Correções de feriados do acúmulo de licenças

### <a name="benefit-plan-employee-entity"></a>Entidade Funcionário do plano de benefícios 

Recentemente descobrimos dois problemas com relação à entidade **BenefitsPlanEmployee**. Ao importar as inscrições do trabalhador, o **Código de cobertura** e o **Código do tipo de plano** estão sendo definidos incorretamente. Esse problema faz com que os planos de benefícios do funcionário sejam exibidos incorretamente no formulário **Plano de benefícios do trabalhador** e no formulário **Abrir a inscrição** no Autoatendimento para funcionários. Esse problema também pode afetar a capacidade do funcionário de selecionar planos no Autoatendimento para funcionários. No momento, não há uma solução alternativa. Estamos tratando isso como uma correção de alta prioridade e implantarei a correção em nossa próxima versão.

## <a name="see-also"></a>Consulte também

[Novidades ou alterações no Human Resources](hr-admin-whats-new.md)</br>
[Visão geral da onda 2 da versão 2019 do Dynamics 365 Human Resources](https://docs.microsoft.com/dynamics365-release-plan/2019wave2/dynamics365-human-resources/)</br>
[Atualizar processo](hr-admin-setup-update-process.md)</br>
[Gerenciar recursos](hr-admin-manage-features.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]