---
title: Perguntas frequentes sobre mesclagem de infraestrutura do Dynamics 365 Human Resources
description: Este tópico responde a perguntas frequentes sobre a mesclagem de infraestrutura para o Microsoft Dynamics 365 Human Resources e os aplicativos de Finanças e Operações.
author: twheeloc
ms.date: 08/13/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.custom: 7521
ms.assetid: ''
ms.search.region: Global
ms.author: twheeloc
ms.search.validFrom: 2020-10-13
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: a905d752af2cf8397acb4927aa99edb4c23bfa6a
ms.sourcegitcommit: a58dfb892e43921157014f0784bd411f5c40e454
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/04/2022
ms.locfileid: "8688110"
---
# <a name="dynamics-365-human-resources-infrastructure-merge-faq"></a>Perguntas frequentes sobre mesclagem de infraestrutura do Dynamics 365 Human Resources

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]



Este tópico responde a perguntas frequentes sobre a mesclagem de infraestrutura para o Microsoft Dynamics 365 Human Resources e os aplicativos de Finanças e Operações.

## <a name="what-is-the-dynamics-365-human-resources-infrastructure-merge"></a>O que é a mesclagem de infraestrutura do Dynamics 365 Human Resources?

O Dynamics 365 Human Resources é um aplicativo autônomo que usa uma infraestrutura diferente de outros aplicativos de finanças e operações, como Dynamics 365 Finance, Dynamics 365 Supply Chain Management, Dynamics 365 Commerce e Dynamics 365 Project Operations. A mesclagem de infraestrutura colocará o Dynamics 365 Human Resources na mesma infraestrutura de outros aplicativos de Finanças e Operações.

## <a name="value-and-benefits-of-the-infrastructure-merge"></a>Valor e benefícios da mesclagem de infraestrutura

### <a name="my-organization-uses-dynamics-365-human-resources-to-manage-its-hr-operations-what-benefits-will-we-see-from-these-changes"></a>Minha organização usa o Dynamics 365 Human Resources para gerenciar suas operações de RH. Quais são as vantagens que vemos com base nessas alterações?

- Essas alterações removem a confusão causada por vários conjuntos de recursos humanos (RH) no Dynamics 365.
- Elas fornecem a extensibilidade do Microsoft Power Platform e uma maneira de estender a lógica de negócios e as opções de recursos.
- Elas proporcionam consistência entre o Dynamics 365 Human Resources e outros aplicativos de Finanças e Operações em termos de Gerenciamento do ciclo de vida de aplicativos (ALM), Microsoft Dynamics Lifecycle Services (LCS), disponibilidade geográfica, extensibilidade e muito mais.
- Elas permitem que você aproveite os serviços compartilhados e a ferramenta, além de ajudar a reduzir os custos.

### <a name="my-organization-uses-the-human-resources-module-in-dynamics-365-finance-supply-chain-management-commerce-or-project-operations-what-benefits-will-we-see-from-these-changes"></a>Minha organização usa o módulo de Human Resources no Dynamics 365 Finance, no Supply Chain Management, no Commerce ou no Project Operations. Quais são as vantagens que vemos com base nessas alterações?

Os recursos e investimentos feitos no Dynamics 365 Human Resources serão disponibilizados para os clientes que estiverem usando o módulo de HR no Dynamics 365 Finance. Alguns desses recursos incluem gerenciamento de licenças e ausências, gerenciamento de benefícios e gerenciamento de tarefas.

### <a name="will-i-lose-any-features-or-capabilities-that-i-currently-use"></a>Vou perder algum recurso ou funcionalidade que uso atualmente?

Haverá paridade funcional entre o Dynamics 365 Human Resources e o módulo HR nos aplicativos do Financial and Operations. O Dynamics 365 Human Resources terá precedência para recursos semelhantes. Para obter mais informações, consulte [Visão geral do Gerenciamento de recursos](../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md).

### <a name="will-the-experience-change-for-my-users"></a>A experiência será alterada para meus usuários?

Os novos recursos de RH serão gerenciados por meio do Gerenciamento de recursos. Os clientes decidirão se desejam aceitá-los. Em alguns casos, os recursos podem ser modificados. Nesses casos, a documentação será fornecida.

### <a name="how-does-this-change-affect-me-if-i-am-an-existing-customer-and-i-use-both-the-hr-module-on-the-finance-and-operations-infrastructure-and-dynamics-365-human-resources-through-custom-integrations"></a>Como essa mudança me afetará se eu for um cliente existente e usar o módulo HR na infraestrutura do Finance and Operations e no Dynamics 365 Human Resources por meio de integrações personalizadas?

As integrações personalizadas entre o Dynamics 365 Human Resources e o módulo de HR no Dynamics 365 Finance não serão mais necessárias. Todos os dados HR residirão no mesmo banco de dados que outros aplicativos de Finanças e Operações.

## <a name="migration-from-dynamics-365-human-resources-to-finance-and-operations-apps"></a>Migração do Dynamics 365 Human Resources para os aplicativos de Finanças e Operações

### <a name="my-organization-uses-dynamics-365-human-resources-to-manage-hr-operations-what-do-we-have-to-plan-for-to-migrate-to-the-new-experience"></a>Minha organização usa o Dynamics 365 Human Resources para gerenciar as operações de RH. O que temos que planejar para migrar para a nova experiência?

Se sua organização usa o Dynamics 365 Human Resources, mas não usa nenhum outro aplicativo de Finanças e Operações, seu ambiente de do Human Resources será migrado para a nova infraestrutura. Grande parte desse processo de migração será automatizado. Haverá processos para migrar seu banco de dados e sincronizá-lo com a nova infraestrutura.

Além disso, as ferramentas estarão disponíveis para que você possa testar o processo de migração e validar os dados e a experiência antes de migrar seu ambiente de produção.

Se sua organização usa o Dynamics 365 Human Resources e outros aplicativos de Finanças e Operações, será necessário planejar mais tempo para a validação a fim de garantir que os dados sejam migrados corretamente para o novo ambiente. A migração para a nova infraestrutura mesclará os dados do ambiente do Human Resources com o ambiente do Finance and Operations. Os dados conflitantes exigem a entrada do usuário para determinar como o conflito deve ser resolvido. Os usuários e os administradores precisarão gerenciar os mapeamentos de dados em que há conflitos e testar a migração em ambientes de área restrita antes da migração dos ambientes de produção.

### <a name="my-organization-uses-the-human-resources-module-in-dynamics-365-finance-supply-chain-management-commerce-or-project-operations-what-do-we-have-to-plan-for-to-migrate-to-the-new-experience"></a>Minha organização usa o módulo de Human Resources no Dynamics 365 Finance, no Supply Chain Management, no Commerce ou no Project Operations. O que temos que planejar para migrar para a nova experiência?

Para organizações que estão usando o módulo HR em aplicativos de Finanças e Operações, a nova funcionalidade de recursos do Dynamics 365 Human Resources será aplicada ao seu ambiente por meio do processo de atualização One Version padrão. Você pode esperar ver a nova funcionalidade em seu ambiente à medida que se torna disponível a cada atualização. Você pode usar o gerenciamento de Recursos para ativar novos recursos, mas deve planejar a validação desses recursos. Siga os processos em vigor para validar outras atualizações no seu ambiente. Para obter mais informações sobre como as atualizações são aplicadas aos aplicativos de Finanças e Operações, consulte [Visão geral One Version](../fin-ops-core/dev-itpro/lifecycle-services/oneversion-overview.md).

### <a name="when-will-my-organization-be-migrated"></a>Quando minha organização será migrada?

A migração para cada organização dependerá de sua configuração atual e da prontidão para migrar para a nova infraestrutura. Essas datas estão sujeitas a alterações.

- As organizações que atualmente usam o módulo HR em aplicativos de Finanças e Operações receberão a funcionalidade do HR para o Dynamics 365 Human Resources, como parte do processo de atualização One Version regular. Os novos recursos estão planejados para serem disponibilizados no mercado a partir de janeiro de 2022.
- As organizações que atualmente usam somente o Dynamics 365 Human Resources terão acesso às ferramentas de migração para que possam começar a testar e iniciar a migração em meados de 2022. A data em que a migração para a nova infraestrutura deve ser concluída ainda não foi determinada. No entanto, será pelo menos um ano após a data em que as ferramentas de migração estiverem disponíveis.
- As organizações que atualmente usam o Dynamics 365 Human Resources e outros aplicativos de Finanças e Operações terão acesso às ferramentas de migração para que possam começar a testar e iniciar a migração no final de 2022. A data em que a migração para a nova infraestrutura deve ser concluída ainda não foi determinada. No entanto, será pelo menos um ano após a data em que as ferramentas de migração estiverem disponíveis.

Para obter mais informações sobre os novos recursos do Dynamics 365 Human Resources, consulte [Novidades ou alterações no Human Resources](./hr-admin-whats-new.md).

### <a name="my-organization-has-not-yet-gone-live-on-dynamics-365-human-resources-should-we-go-live-with-the-human-resources-module-in-the-finance-and-operations-apps-or-with-the-dynamics-365-human-resources-app-on-the-legacy-infrastructure"></a>A minha organização ainda não foi ativada no Dynamics 365 Human Resources. Devemos ativar o módulo do Human Resources nos aplicativos de Finanças e Operações ou com o aplicativo do Dynamics 365 Human Resources na infra-estrutura herdada?

Os itens importantes a serem considerados são o que a funcionalidade de RH é necessária e quando essa funcionalidade estará disponível na nova infra-estrutura. Se a organização precisar da funcionalidade principal para o gerenciamento de pessoal, que está disponível no momento no módulo HR dos aplicativos de Finanças e Operações na nova infraestrutura. A paridade de recursos entre o módulo HR dos aplicativos de Finanças e Operações e o aplicativo do Dynamics 365 Human Resources é esperada na versão 10.0.25, que está programada para ser disponibilizada no mercado em março de 2022. Recursos de integração, como o app do Teams e as integrações da entidade do Dataverse, estarão disponíveis em versões posteriores.

Se as necessidades da funcionalidade de HR da organização precisarem estar disponíveis na nova infraestrutura dentro do período de tempo no qual a organização ficará ativa, talvez seja mais fácil ativar o módulo de Human Resources nos aplicativos de Finanças e Operações. Isso resultará em uma migração mais fácil, já que será uma atualização padrão do aplicativo para o aplicativo do Dynamics 365 Human Resources e o cliente já estará na nova infra-estrutura. Se a organização decidir ativar o aplicativo do Dynamics 365 Human Resources na infraestrutura herdada, será necessário fazer uma migração de ambiente para a nova infra-estrutura. Isso pode ser evitado ativando a nova infra-estrutura.

### <a name="i-am-using-new-capabilities-that-are-available-only-in-dynamics-365-human-resources-such-as-leave-and-absence-and-benefits-management-will-these-capabilities-now-be-available-in-the-human-resources-module-on-the-finance-and-operations-infrastructure-too"></a>Estou usando novos recursos que estão disponíveis somente no Dynamics 365 Human Resources (como **Licença e ausência** e **Gerenciamento de benefícios**). Esses recursos agora estarão disponíveis no módulo de Human Resources na infraestrutura do Finance and Operations também?

Sim, todos os módulos do Dynamics 365 Human Resources funcionarão como estão nos aplicativos de Finanças e Operações e haverá 100% de paridade de recursos. Como parte da estratégia geral de migração para clientes que atualmente usam esses recursos no HR, os dados do cliente serão migrados para que continuem a funcionar na infraestrutura do Finance and Operations.

### <a name="i-use-the-new-dynamics-365-human-resources-benefits-management-capabilities-ive-built-custom-integrations-with-the-hr-module-on-the-finance-and-operations-infrastructure-so-that-i-can-take-advantage-of-the-payroll-capabilities-by-using-benefits-data-will-these-custom-integrations-be-required-going-forward"></a>Uso os novos recursos de gerenciamento de benefícios do Dynamics 365 Human Resources. Criei integrações personalizadas com o módulo HR na infraestrutura do Finance and Operations para poder aproveitar os recursos da folha de pagamento usando dados de benefícios. Essas integrações personalizadas serão necessárias no futuro?

Como parte da mesclagem da infraestrutura, os dados de HR são trazidos para o mesmo aplicativos de Finanças e Operações. A integração entre os módulos nos aplicativos de Finanças e Operações não será mais necessária.

### <a name="my-organization-uses-one-or-more-isv-solutions-with-dynamics-365-human-resources-will-our-isv-solutions-be-migrated-automatically"></a>Minha organização usa uma ou mais soluções de ISV com o Dynamics 365 Human Resources. As nossas soluções de ISV serão migradas automaticamente?

A experiência de migração para cada solução de fornecedor de software independente (ISV) variará, dependendo do método de integração da solução. A Microsoft trabalhará em conjunto com os ISVs para garantir uma transição tranquila para a nova infraestrutura.

### <a name="my-organization-uses-linkedin-talent-hub-integration-with-dynamics-365-human-resources-will-this-integration-continue-to-work-after-the-infrastructure-change-is-completed"></a>Minha organização usa a integração do LinkedIn Talent Hub com o Dynamics 365 Human Resources. A integração continuará a funcionar depois que a mudança de infraestrutura for concluída?

Não, a integração do LinkedIn Talent Hub não funcionará após a migração para a nova infraestrutura. O serviço para a integração do LinkedIn Talent Hub será desativado com a infra-estrutura herdada do Dynamics 365 Human Resources.

### <a name="my-organization-uses-the-human-resources-app-for-teams-will-the-app-continue-to-work-after-the-infrastructure-change-is-completed"></a>Minha organização usa o aplicativo Human Resources para o Teams. O aplicativo continuará a funcionar depois que a mudança de infraestrutura for concluída?

Sim, o aplicativo Human Resources para o Teams continuará funcionando após a migração para a nova infraestrutura.

### <a name="my-organization-has-configured-custom-security-in-dynamics-365-human-resources-will-our-custom-security-still-be-applied-after-the-infrastructure-change-is-completed"></a>Minha organização configurou a segurança personalizada no Dynamics 365 Human Resources. Nossa segurança personalizada ainda será aplicada depois que a mudança de infraestrutura for concluída?

Sim, as configurações de segurança personalizadas serão incluídas na migração de dados para a nova infraestrutura.

### <a name="we-are-using-data-integrator-to-move-data-between-dynamics-365-human-resources-and-finance-and-operations-apps-how-will-the-data-that-is-currently-being-integrated-be-affected"></a>Estamos usando o Integrador de dados para mover dados entre o Dynamics 365 Human Resources e os aplicativos de Finanças e Operações. Como os dados que estão sendo integrados serão afetados?

Os dados de RH atualmente controlados no Dynamics 365 Human Resources são sincronizados com o Dataverse. O integrador de dados pode, então, ser usado para sincronização unilateral com aplicativos de Finanças e Operações. Após a migração para a nova infraestrutura, os dados de HR serão nativos para os aplicativos de Finanças e Operações. O integrador de dados não será mais necessário para sincronizar os dados entre os aplicativos de Finanças e Operações e o Human Resources.

As tabelas de dados nativas atuais do Dataverse para o Human Resources continuarão a sincronizar os dados do ambiente na nova infraestrutura. As entidades serão convertidas para oferecer suporte à gravação dupla. Todas as outras integrações de dados configuradas por meio do Integrador de Dados em relação a essas tabelas para outros aplicativos do Dynamics 365 continuarão a funcionar como estão atualmente configurados.

### <a name="we-are-using-dual-write-to-move-hr-data-between-dataverse-and-other-finance-and-operations-apps-how-will-the-data-that-is-currently-being-integrated-be-affected-by-the-migration-to-the-new-infrastructure"></a>Estamos usando a gravação dupla para mover dados de HR entre o Dataverse e outros aplicativos de Finanças e Operações. Como os dados que estão sendo integrados serão afetados pela migração para a nova infraestrutura?

Os dados de HR serão nativos para os aplicativos de Finanças e Operações no ambiente na nova infraestrutura. A gravação dupla será usada para mover os dados de RH entre o novo ambiente e o ambiente do Dataverse.

### <a name="we-have-built-custom-integrations-from-dynamics-365-human-resources-to-one-or-more-external-systems-will-we-have-to-develop-new-integrations-after-the-infrastructure-change-is-completed"></a>Criamos integrações personalizadas do Dynamics 365 Human Resources para um ou mais sistemas externos. Teremos que desenvolver novas integrações depois que a mudança de infraestrutura for concluída?

Depende do ponto de extremidade da integração. Para obter mais informações sobre as tecnologias de integração que estão disponíveis nos aplicativos de Finanças e Operações e como escolher a melhor tecnologia de integração, consulte [Visão geral da integração](../fin-ops-core/dev-itpro/data-entities/integration-overview.md).

### <a name="we-have-extended-dataverse-for-dynamics-365-human-resources-will-these-extensions-be-migrated-automatically"></a>Estendemos o Dataverse para o Dynamics 365 Human Resources. Essas extensões serão migradas automaticamente?

Se os ambientes do Dynamics 365 Human Resources e do Finance and Operations que serão unidos ao ambiente na nova infraestrutura estiverem conectados ao mesmo ambiente do Dataverse, os dois aplicativos continuarão a ser conectados ao mesmo ambiente do Dataverse após a migração. Nenhuma migração será necessária para as extensões do Dataverse.

No entanto, se os ambientes do Dynamics 365 Human Resources e do Finance and Operations estiverem atualmente conectados a ambientes separados do Dataverse, os dois ambientes do Dataverse terão que ser combinados para que sejam conectados a um único ambiente na nova infraestrutura. Para esta migração do Dataverse, as tabelas do Dataverse que são padrão para as soluções do Human Resources podem ser conectadas e sincronizadas novamente com o novo ambiente do Dataverse. Quaisquer extensões para o ambiente do Dataverse não serão migradas automaticamente, mas devem ser reimplantadas no novo ambiente. Recomendamos que você use soluções gerenciadas para gerenciar as extensões do Dataverse. Para obter mais informações, consulte [Introdução a soluções](/powerapps/developer/data-platform/introduction-solutions).

### <a name="we-have-configured-microsoft-power-automate-flows-andor-microsoft-power-apps-to-work-with-dynamics-365-human-resources-will-these-microsoft-power-platform-components-be-migrated-and-work-automatically-after-the-infrastructure-change-is-completed"></a>Configuramos os fluxos do Microsoft Power Automate e/ou o Microsoft Power Apps para trabalhar com o Dynamics 365 Human Resources. Esses componentes do Microsoft Power Platform serão migrados e funcionarão automaticamente após a conclusão da mudança da infraestrutura?

O Power Apps, os fluxos do Power Automate e outras personalizações do Microsoft Power Platform são semelhantes às extensões do Dataverse. Se eles funcionarão automaticamente após a migração para a nova infraestrutura vai depender se o aplicativo Human Resources e os aplicativos de Finanças e Operações estão conectados ao mesmo ambiente do Power Apps antes da migração.

Se os aplicativos estiverem atualmente conectados ao mesmo ambiente do Power Apps, eles continuarão a ser conectados a esse ambiente do Power Apps após a migração para a nova infraestrutura. Neste caso, o Power Apps, os fluxos do Power Automate e outras personalizações do Microsoft Power Platform continuarão a funcionar sem nenhuma configuração adicional. Recomendamos que você use soluções gerenciadas para gerenciar suas extensões de aplicativo no Dataverse. Para obter mais informações, consulte [Introdução a soluções](/powerapps/developer/data-platform/introduction-solutions).

No entanto, se o aplicativo Human Resources e os aplicativos de Finanças e Operações estiverem conectados a ambientes separados do Power Apps, eles precisarão ser combinados como parte da migração. Essa tarefa exigirá que qualquer Power Apps e outras personalizações sejam reimplantadas no novo ambiente.

### <a name="we-have-enabled-dataverse-virtual-tables-for-dynamics-365-human-resources-what-will-happen-to-these-tables-during-the-migration"></a>Habilitamos as tabelas virtuais do Dataverse para o Dynamics 365 Human Resources. O que ocorrerá com essas tabelas durante a migração?

Após a migração, se o ambiente na nova infraestrutura permanecer conectado ao ambiente do Dataverse, que está atualmente conectado ao Dynamics 365 Human Resources, as tabelas virtuais do Dataverse que foram geradas nesse ambiente continuarão funcionando sem nenhuma configuração adicional.

No entanto, se o ambiente na nova infraestrutura estiver conectado a um ambiente do Dataverse diferente após a migração, as tabelas virtuais precisarão ser geradas novamente no novo ambiente do Dataverse.

### <a name="we-have-developed-an-integration-by-using-the-applicant-tracking-system-ats-api-payroll-api-dataverse-virtual-tables-for-dynamics-365-human-resources-or-other-entities-in-the-dataverse-web-api-will-these-integrations-continue-to-work-after-the-infrastructure-change-is-completed"></a>Desenvolvemos uma integração usando a API do ATS (sistema de acompanhamento de candidatos), a API da folha de pagamento, as tabelas virtuais do Dataverse para o Dynamics 365 Human Resources ou outras entidades na API Web do Dataverse. Essas integrações continuarão a funcionar depois que a mudança de infraestrutura for concluída?

Após a migração, se o ambiente na nova infraestrutura permanecer conectado ao ambiente do Dataverse, que está atualmente conectado ao Dynamics 365 Human Resources, todas as integrações desenvolvidas em relação à API Web do Dataverse continuarão a funcionar após a conclusão da migração.

No entanto, se o ambiente na nova infraestrutura estiver conectado a um ambiente do Dataverse diferente após a migração, todas as integrações que foram desenvolvidas em relação à API Web do Dataverse terão que ser reconfiguradas para que se conectem ao novo ambiente do Dataverse.

### <a name="is-there-an-impact-on-the-azure-region-when-my-environment-is-migrated"></a>Há algum impacto na região do Azure quando meu ambiente for migrado?

Espera-se que seu ambiente do Human Resources seja, normalmente, mantido na mesma região do Azure durante a migração. A única exceção ocorrerá se o ambiente do Human Resources for mesclado com um ambiente do Finance and Operations que esteja em uma região diferente. Nesse caso, o ambiente do Human Resources será migrado para a região do Azure do ambiente do Finance and Operations.

### <a name="my-organization-depends-on-workflows-in-dynamics-365-human-resources-for-one-or-more-business-processes-will-the-workflows-be-migrated-automatically"></a>Minha organização depende dos fluxos de trabalho no Dynamics 365 Human Resources para um ou mais processos comerciais. Os fluxos de trabalho serão migrados automaticamente?

Sim, as configurações de fluxo de trabalho, o histórico do fluxo de trabalho e os fluxos de trabalho em andamento atuais serão migrados.

### <a name="what-training-and-resources-will-be-available-to-help-with-the-migration-process"></a>Quais treinamentos e recursos estarão disponíveis para ajudar no processo de migração?

A documentação completa será fornecida para descrever cada etapa do processo de migração em detalhes. Recursos de treinamento adicionais, como vídeos e workshops, também podem estar disponíveis, dependendo da necessidade.

### <a name="my-organization-has-created-saved-views-in-dynamics-365-human-resources-to-improve-the-usability-of-the-interface-will-the-saved-views-be-migrated-automatically"></a>Minha organização criou Exibições salvas no Dynamics 365 Human Resources para melhorar a usabilidade da interface. As Exibições salvas serão migradas automaticamente?

Sim, as Exibições salvas serão migradas para a nova infraestrutura.

### <a name="we-are-using-ceridian-with-dynamics-365-human-resources-will-the-ceridian-integration-be-available-after-the-infrastructure-change-is-completed"></a>Estamos usando o Ceridian com o Dynamics 365 Human Resources. A integração do Ceridian estará disponível após a conclusão da mudança de infraestrutura? 

A integração com o Ceridian será migrada para a integração baseada na API da folha de pagamento. A integração baseada no arquivo que existe atualmente no Dynamics 365 Human Resources não será migrada para a infraestrutura do Finance and Operations. Para obter mais informações, consulte [Introdução à API da folha de pagamento](./hr-admin-integration-payroll-api-introduction.md).

### <a name="how-will-the-migration-affect-the-service-update-process"></a>Como a migração afetará o processo de atualização de serviço?

Após a migração, os clientes terão muito mais flexibilidade em termos de ALM e atualizações de serviço. As atualizações de serviço não serão mais aplicadas automaticamente aos ambientes do Human Resources. Em vez disso, o serviço seguirá os processos e a funcionalidade de atualização do serviço One Version. Portanto, as opções de configuração para atualizações estarão disponíveis por meio do LCS. Para obter mais informações, consulte [Visão geral One Version](../fin-ops-core/dev-itpro/lifecycle-services/oneversion-overview.md).

### <a name="how-will-the-migration-affect-my-lcs-project-for-dynamics-365-human-resources"></a>Como a migração afetará meu projeto do LCS para o Dynamics 365 Human Resources?

A migração para a nova infraestrutura moverá o gerenciamento de seus ambientes do Dynamics 365 Human Resources para um projeto de implementação do Finance and Operations no LCS. Se a migração estiver mesclando o Dynamics 365 Human Resources com um ambiente do Finance and Operations existente, seu projeto do LCS do Human Resources será mesclado com o projeto de implementação do LCS para o aplicativo de Finanças e Operações. Se você estiver usando somente o Dynamics 365 Human Resources atualmente, um novo projeto de implementação do LCS será criado e seu projeto do LCS do Human Resources existente será migrado para o novo projeto.

O novo projeto será o mesmo tipo de projeto que os aplicativos de Finanças e Operações. Ele terá os mesmos recursos e funcionalidades para o gerenciamento de ambiente. Para obter mais informações, consulte [Recursos do Lifecycle Services](../fin-ops-core/dev-itpro/lifecycle-services/lcs.md).

### <a name="we-have-linked-our-task-recordings-to-the-business-process-modeler-in-human-resources-how-will-the-business-process-modeler-be-migrated-and-merged-into-lcs"></a>Vinculamos nossas gravações de tarefas ao Modelador de processo de negócios no Human Resources. Como o Modelador de processo de negócios será migrado e mesclado no LCS?

As bibliotecas de processos de negócios para o projeto do LCS serão migradas para o novo projeto do LCS do Human Resources.

### <a name="my-organization-currently-uses-only-dynamics-365-human-resources-what-resources-are-available-so-that-we-can-learn-more-about-the-development-capabilities-after-the-infrastructure-change-is-completed"></a>Minha organização só usa o Dynamics 365 Human Resources no momento. Quais recursos estão disponíveis para que possamos aprender mais sobre os recursos de desenvolvimento após a conclusão da mudança na infraestrutura?

As opções de extensibilidade do Microsoft Power Platform e do Finance and Operations estarão disponíveis e podem ser usadas para desenvolvimento. Para obter mais informações, consulte [Desenvolver e personalizar a Home Page](../fin-ops-core/dev-itpro/dev-tools/developer-home-page.md).

### <a name="we-have-enabled-features-in-dynamics-365-human-resources-will-these-features-be-enabled-automatically-during-the-migration"></a>Habilitamos recursos no Dynamics 365 Human Resources. Esses recursos serão habilitados automaticamente durante a migração?

Para cada recurso, será determinado individualmente se um recurso será ou não habilitado automaticamente na nova infraestrutura. Essas informações serão incluídas na documentação do recurso.

### <a name="what-happens-to-my-byod-database-during-the-migration"></a>O que acontece com meu banco de dados BYOD durante a migração?

As configurações de importação e exportação para BYOD (traga seu próprio banco de dados) serão migradas para a nova infraestrutura.

### <a name="what-happens-to-my-azure-data-lake-during-the-migration"></a>O que acontece com meu Azure Data Lake durante a migração?

Qualquer exportação configurada atualmente para o Azure Data Lake Storage em aplicativos de Finanças e Operações manterá a mesma configuração após a migração.

### <a name="we-are-currently-using-dynamics-ax-2012-will-the-upgrade-tools-that-are-currently-available-be-used-to-upgrade-the-hr-module-in-ax-2012-to-dynamics-365-human-resources"></a>No momento, estamos usando o Dynamics AX 2012. As ferramentas de atualização que estão disponíveis atualmente serão usadas para atualizar o módulo de RH no AX 2012 para o Dynamics 365 Human Resources?

Sim. O Dynamics 365 Human Resources será incluído na base de código e infraestrutura mescladas para os aplicativos de Finanças e Operações. Uma atualização do Dynamics AX 2012 para o Dynamics 365 Human Resources usará o mesmo caminho de atualização e as mesmas ferramentas que são usadas para atualizar para a versão mais recente dos aplicativos de Finanças e Operações.

### <a name="we-use-document-handling-with-dynamics-365-human-resources-what-will-happen-to-the-documents-during-the-migration"></a>Usamos o manuseio de documentos com o Dynamics 365 Human Resources. O que ocorrerá com os documentos durante a migração?

Os documentos permanecerão no armazenamento de documentos existente. Eles serão mapeados novamente para o ambiente na nova infraestrutura.

### <a name="what-happens-to-the-batch-jobs-that-we-have-configured-in-dynamics-365-human-resources-after-the-migration"></a>O que acontece com os trabalhos em lote que foram configurados no Dynamics 365 Human Resources após a migração?

Os trabalhos em lote aplicáveis serão migrados automaticamente para a nova infraestrutura.

## <a name="licensing-impact"></a>Impacto de licenciamento

Esta documentação não substitui nenhuma das documentações legais que abrangem os direitos de uso.

### <a name="my-organization-uses-dynamics-365-human-resources-to-manage-its-hr-operations-does-our-licensing-or-cost-change"></a>Minha organização usa o Dynamics 365 Human Resources para gerenciar suas operações de RH. Nosso licenciamento ou nosso custo muda?

Os clientes que adquiriram licenças do Dynamics 365 Human Resources não serão afetados. Não há migração de licenciamento para esses clientes. A SKU (unidade de manutenção de estoque) adicional da área restrita que era específica para o Human Resources não será mais aplicável. Em vez disso, os clientes podem optar por comprar uma área restrita de Camada 2 de aplicativos de Finanças e Operações a um custo ligeiramente inferior. Os clientes existentes que compraram uma área restrita do Human Resources serão migrados para uma área restrita de Camada 2 de aplicativos de Finanças e Operações sem nenhum custo adicional.

### <a name="my-organization-uses-the-human-resources-module-in-dynamics-365-finance-supply-chain-management-commerce-or-project-operations-does-my-licensing-or-cost-change"></a>Minha organização usa o módulo de Human Resources no Dynamics 365 Finance, no Supply Chain Management, no Commerce ou no Project Operations. Meu licenciamento ou meu custo muda?

Os usuários existentes dos aplicativos do Dynamics 365 e os usuários do Dynamics 365 Finance autônomo, do Supply Chain Management, do Commerce e do Project Operations podem acessar o Human Resources como parte dessas licenças até fevereiro de 2025 ou até que o contrato de licenciamento atual expire, o que ocorrer primeiro. Você pode optar por mudar para as licenças do Human Resources antes se isso ajudar você a obter descontos mais vantajosos. A partir de fevereiro de 2025, todos os clientes existentes do CSP e do EA devem sair do módulo de HR e comprar licenças do Human Resources para aproveitar as vantagens dos novos recursos que estão sendo trazidos para os aplicativos de Finanças e Operações.

### <a name="my-organization-is-live-with-dynamics-365-finance-supply-chain-management-commerce-or-project-operations-will-we-be-required-to-purchase-an-additional-environment-to-support-the-infrastructure-merge"></a>Minha organização está ativa com o Dynamics 365 Finance, o Supply Chain Management, o Commerce ou o Project Operations. Será necessário adquirir um ambiente adicional para oferecer suporte à mesclagem da infraestrutura?

Ambientes adicionais não são necessários para dar suporte à mudança de infraestrutura.

