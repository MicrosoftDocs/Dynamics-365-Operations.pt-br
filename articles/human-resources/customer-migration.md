---
title: Perguntas frequentes sobre a migração do cliente do Human Resources
description: Este artigo responde a perguntas frequentes sobre a migração do Microsoft Dynamics 365 Human Resources para a infraestrutura mesclada de finanças e operações.
author: twheeloc
ms.date: 07/06/2022
ms.topic: overview
ms.prod: ''
ms.technology: ''
ms.search.form: LeavePlanFormPart, LeaveAbsenceWorkspace
audience: Application User
ms.assetid: ''
ms.search.region: Global
ms.author: twheeloc
ms.search.validFrom: 2020-02-03
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: 8a6f883da07bd1d3a6b0379f1582dc8556e166ff
ms.sourcegitcommit: 9310c943ac76896663e5604209034da9f8d6139c
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/14/2022
ms.locfileid: "9151073"
---
# <a name="human-resources-customer-migration"></a>Migração do cliente do Human Resources

## <a name="how-should-dynamics-365-human-resources-customers-plan-to-move-to-the-finance-and-operations-infrastructure"></a>Como os clientes do Dynamics 365 Human Resources devem planejar a mudança para a infraestrutura de finanças e operações?

Duas categorias de clientes do Microsoft Dynamics 365 Human Resources serão afetadas e precisarão fazer alterações para garantir que estejam na infraestrutura de finanças e operações mais recente:

- Clientes que usam o Dynamics 365 Human Resources e não têm outros aplicativos de operações do Dynamics 365
- Clientes que usam o Dynamics 365 Human Resources e o Dynamics 365 Finance, Dynamics 365 Supply Chain Management, Dynamics 365 Commerce ou Dynamics 365 Project Operations

Independentemente da categoria à qual pertencem, os clientes precisarão mover os dados para um ambiente recém-criado na infraestrutura de finanças e operações e validar que a mesclagem foi concluída com êxito.

No futuro, o aplicativo Dynamics 365 Human Resources terá seu próprio ambiente de finanças e operações, separado de outros aplicativos de operações. Dessa forma, os clientes poderão aproveitar as opções de extensibilidade sem a necessidade de mesclar os dados atuais. A Microsoft fornecerá ferramentas e um ambiente de área restrita que os clientes podem usar para testar e validar a migração de dados antes de serem movidos para um ambiente de produção. A ferramenta habilitará um processo quase automatizado e estará disponível entre agosto e novembro de 2022.

Os clientes que estiverem usando outros aplicativos na infraestrutura de finanças e operações terão a opção de mesclar seus dados do Human Resources com um ambiente existente. 

## <a name="when-will-customers-be-moved-to-the-finance-and-operations-infrastructure"></a>Quando os clientes serão transferidos para a infraestrutura de finanças e operações?

A transição para cada empresa dependerá da configuração e prontidão atuais da empresa para mudar para a infraestrutura de finanças e operações. Recomendamos que os clientes trabalhem com o parceiro da Microsoft para determinar o melhor caminho a ser seguido.

- As organizações que usam o módulo **Recursos Humanos** no Dynamics 365 Finance poderão habilitar novos recursos do Dynamics 365 Human Resources como parte do processo de atualização regular do One Version. Os novos recursos estão planejados para serem disponibilizados no mercado a partir de janeiro de 2022.
- As organizações que usam o Dynamics 365 Human Resources terão acesso à ferramenta que pode ser usada para concluir a mesclagem da infraestrutura. A Microsoft trabalhará com clientes na transição para ajudar a prevenir qualquer interrupção no serviço. Os clientes terão de 12 a 18 meses para fazer a transição, a partir do momento em que a ferramenta de migração for disponibilizada.
- As organizações que usam o Dynamics 365 Human Resources e o módulo **Recursos Humanos** podem mover sua infraestrutura autônoma de Recursos Humanos para a infraestrutura de finanças e operações. Outra opção é usar a ferramenta de mesclagem para colocar os ambientes em um único ambiente. Não há requisito ou período para mesclar os dois ambientes.

Para obter informações atualizadas, verifique regularmente os [Planos de lançamento](/dynamics365/release-plans/).

## <a name="will-customers-still-need-custom-integrations-between-dynamics-365-human-resources-and-the-human-resources-module"></a>Os clientes ainda precisarão de integrações personalizadas entre o Dynamics 365 Human Resources e o módulo Recursos Humanos?

- Os clientes que têm o Dynamics 365 Human Resources e outros ambientes de infraestrutura de finanças e operações que estão integrados no momento terão que continuar integrando os dois ambientes após a mesclagem.
- Os clientes que optarem por manter seu ambiente do Dynamics 365 Human Resources separado do ambiente de aplicativo de finanças e operações existentes precisarão continuar integrando os ambientes para disponibilizar os dados nos dois ambientes.
- Os clientes podem continuar usando o Integrador de Dados para copiar dados entre os dois ambientes. Os clientes que mesclam dados em um único ambiente após a migração não precisarão mais integrar os dados, pois todos os dados estarão em um banco de dados individual.

## <a name="will-customer-isv-solutions-automatically-be-migrated"></a>As soluções de ISV do cliente serão migradas automaticamente?

A experiência de migração para cada solução de fornecedor de software independente (ISV) variará, dependendo do método de integração da solução. A Microsoft trabalhará em conjunto com os ISVs com o intuito de fornecer uma transição tranquila para a infraestrutura de finanças e operações. Muitas soluções de ISV são criadas no Dataverse usando recursos do Microsoft Power Platform. Essas soluções dependem da integração do Dataverse entre o ambiente do Dynamics 365 Human Resources e o ambiente do Dataverse. A integração do Dataverse está sendo preterida como parte da mesclagem de infraestrutura. Na infraestrutura de finanças e operações, novos mapas de gravação dupla estão planejados para substituir a funcionalidade da integração do Dataverse.

## <a name="how-will-the-data-integrator-that-moves-data-between-dynamics-365-human-resources-and-other-dynamics-365-apps-be-affected"></a>Como o Integrador de Dados que move os dados entre o Dynamics 365 Human Resources e outros aplicativos do Dynamics 365 será afetado?

Depois que os clientes mudarem para a infraestrutura de finanças e operações, eles terão que continuar integrando os dados entre os dois ambientes. Os clientes podem continuar usando o Integrador de Dados para executar essas tarefas de migração de dados. Os clientes que planejam manter seu ambiente do Dynamics 365 Human Resources separado do ambiente de aplicativos de finanças e operações existentes precisarão continuar integrando os dados entre os dois ambientes. Para os clientes que mesclam os dois ambientes em um único ambiente, a integração entre os dois ambientes não será mais necessária.

## <a name="how-will-data-be-moved-between-dynamics-365-human-resources-on-the-finance-and-operations-infrastructure-and-dataverse-after-the-migration"></a>Como os dados serão movidos entre o Dynamics 365 Human Resources na infraestrutura de finanças e operações e Dataverse depois da migração?

A integração atual do Dataverse entre o Dynamics 365 Human Resources e o Dataverse está sendo preterida como parte da infraestrutura de finanças e operações. Há planos de apresentar mapas de gravação dupla para mapear as entidades de finanças e operações para as tabelas do Dataverse. Os clientes precisarão decidir quais mapas de gravação dupla são necessários para a implementação. É recomendável que as tabelas virtuais sejam usadas para integrações e soluções de ISV, a menos que haja uma necessidade comercial específica de que os dados sejam duplicados no Dataverse para execução da lógica comercial.

## <a name="how-does-the-migration-affect-dataverse-extensions-for-dynamics-365-human-resources"></a>Como a migração afeta as extensões do Dataverse para o Dynamics 365 Human Resources?

Os clientes serão solicitados a migrar para um ambiente de área restrita antes de migrar para o ambiente de produção. Quando os clientes migram o ambiente de área de restrita, eles têm que criar uma cópia de seu ambiente do Dataverse para se conectarem ao novo ambiente migrado de finanças e operações. É recomendável que um cliente copie os dados e as soluções para o ambiente, para que eles correspondam ao ambiente de produção atual do cliente.

Quando os clientes estiverem prontos para migrar seu ambiente de produção do Dynamics 365 Human Resources, a Microsoft migrará automaticamente o banco de dados e o Armazenamento de Blobs do Azure. O banco de dados e o armazenamento migrados apontarão o novo ambiente na infraestrutura de finanças e operações para o mesmo ambiente de produção do Dataverse. Para que os dados possam continuar sendo copiados para o Dataverse, os clientes terão de habilitar mapas de gravação dupla que são necessários para suas integrações, extensões e soluções de ISV criados no Dataverse.

## <a name="will-microsoft-power-platform-components-that-were-built-for-dynamics-365-human-resources-automatically-work-after-the-infrastructure-migration-is-completed"></a>Os componentes do Microsoft Power Platform que foram criados para o Dynamics 365 Human Resources funcionarão automaticamente depois que a migração de infraestrutura for concluída?

Os aplicativos criados no Power Apps, os fluxos criados no Power Automate e outras personalizações do Microsoft Power Platform, são como extensões do Dataverse. Durante a migração de ambientes de produção do cliente, não há impacto nos ambientes do Dataverse, incluindo extensões. Aplicativos, fluxos e outras personalizações do Microsoft Power Platform devem continuar funcionando sem exigir configuração adicional.

## <a name="what-will-happen-to-dataverse-virtual-table-entities-for-dynamics-365-human-resources-during-the-migration"></a>O que acontecerá com as entidades de tabela virtual do Dataverse para o Dynamics 365 Human Resources durante a migração?

Quando os clientes migrarem o ambiente do Dynamics 365 Human Resources para a infraestrutura de finanças e operações, o ambiente permanecerá conectado ao ambiente do Dataverse que atualmente está conectado ao Dynamics 365 Human Resources. As tabelas virtuais do Dataverse que foram geradas no ambiente continuarão funcionando sem a necessidade de qualquer configuração adicional. As tabelas virtuais talvez precisem ser regeneradas no ambiente do Dataverse conectado ao ambiente de finanças e operações existente do cliente.

## <a name="how-will-an-integration-that-uses-the-applicant-tracking-system-ats-api-payroll-api-dataverse-virtual-tables-for-dynamics-365-human-resources-or-other-entities-in-the-dataverse-web-api-work-after-the-infrastructure-merge-is-completed"></a>Como uma integração que usa a API do ATS (Sistema de Acompanhamento de Candidatos), a API da folha de pagamento, as tabelas virtuais do Dataverse para Dynamics 365 Human Resources, ou outras entidades na API Web do Dataverse funcionam após a conclusão da mesclagem da infraestrutura?

Quando os clientes migrarem o ambiente do Dynamics 365 Human Resources para a infraestrutura de finanças e operações, o ambiente permanecerá conectado ao ambiente do Dataverse que atualmente está conectado ao Dynamics 365 Human Resources. Todas as integrações que foram desenvolvidas para a API Web do Dataverse continuarão funcionando após a conclusão da migração.

## <a name="our-organization-has-configured-custom-security-in-dynamics-365-human-resources-will-it-still-be-applied-after-the-infrastructure-migration-is-completed"></a>Nossa organização configurou a segurança personalizada no Dynamics 365 Human Resources. Ela continuará sendo aplicada depois que a migração da infraestrutura for concluída?

Sim, as configurações de segurança personalizada serão incluídas na migração de dados.

## <a name="will-workflows-in-dynamics-365-human-resources-automatically-be-migrated"></a>Os fluxos de trabalho no Dynamics 365 Human Resources serão migrados automaticamente?

Sim, as configurações de fluxo de trabalho, o histórico do fluxo de trabalho e os fluxos de trabalho em processo atuais serão migrados para a infraestrutura mesclada.

## <a name="will-saved-views-in-dynamics-365-human-resources-automatically-be-migrated"></a>As exibições salvas no Dynamics 365 Human Resources serão migradas automaticamente?

Sim, as exibições salvas serão migradas para a nova infraestrutura mesclada.

## <a name="will-features-that-are-enabled-in-dynamics-365-human-resources-automatically-be-available-after-the-infrastructure-merge"></a>Os recursos habilitados no Dynamics 365 Human Resources estarão disponíveis automaticamente após a mesclagem da infraestrutura?

- Para clientes que usam o módulo **Recursos Humanos**, os recursos disponíveis somente no Dynamics 365 Human Resources serão gerenciados pelo Gerenciamento de recursos. Normalmente, esses recursos não serão habilitados por padrão. Todos os recursos que devem ser habilitados por padrão serão documentados.
- Para clientes que usam o Dynamics 365 Human Resources, os recursos estarão disponíveis na infraestrutura. Os recursos que não estiverem disponíveis serão documentados. Cada chave do Gerenciamento de recursos habilitada no ambiente atual do Dynamics 365 Human Resources será habilitada na infraestrutura mesclada. Para obter mais informações, consulte [Visão geral do Gerenciamento de recursos](/fin-ops/get-started/feature-management-overview.md).

## <a name="what-happens-to-byod-databases-during-the-migration"></a>O que acontece com os bancos de dados BYOD durante a migração?

As configurações de importação e exportação para BYOD (traga seu próprio banco de dados) serão migradas para a infraestrutura de finanças e operações.

## <a name="is-there-an-impact-on-the-azure-region-when-the-customer-environment-is-migrated"></a>Há algum impacto na região do Azure quando o ambiente do cliente for migrado?

O ambiente do Dynamics 365 Human Resources permanecerá na mesma região do Azure para a migração. Se houver uma necessidade de mover um ambiente para uma região do Azure diferente, os clientes terão de seguir as etapas padrão para migrar para uma nova região após a conclusão da migração.

## <a name="what-happens-to-azure-data-lakes-during-the-migration"></a>O que acontece com data lakes do Azure durante a migração?

Qualquer exportação configurada atualmente para o Data Lake do Azure em aplicativos de finanças e operações manterá a mesma configuração após a migração.

> [!NOTE]
> Os mapas de gravação dupla precisarão ser habilitados para continuar gravando dados do ambiente do Human Resources no Dataverse.

Os clientes que desejam exportar dados do Human Resources para o data lake podem habilitar esse recurso depois que a migração para a infraestrutura de finanças e operações for concluída. Para obter mais informações, consulte [Data lakes – Centro de Arquitetura do Azure](/azure/architecture/data-guide/scenarios/data-lake).

Os clientes podem vincular vários ambientes de finanças e operações ao mesmo data lake. No entanto, cada ambiente apontará para uma pasta e um contêiner diferentes. Os clientes que planejam mesclar os ambientes posteriormente devem planejar cuidadosamente sua abordagem.
 
## <a name="what-migration-will-be-required-if-a-customer-is-currently-using-the-human-resources-module"></a>Que migração será necessária se um cliente estiver usando o módulo Recursos Humanos no momento?

Os clientes que usam o módulo **Recursos Humanos** terão a nova funcionalidade de recurso do Dynamics 365 Human Resources aplicada ao seu ambiente por meio do processo de atualização padrão do One Version. Os clientes podem esperar ver a nova funcionalidade em seu ambiente à medida que se torna disponível a cada atualização. Os clientes podem usar o Gerenciamento de recursos para habilitar os recursos. Os clientes devem planejar a validação desses novos recursos usando os processos já existentes no local e usar para validar outras atualizações no ambiente.

## <a name="what-will-happen-to-custom-integrations-to-external-systems"></a>O que ocorrerá com as integrações personalizadas para sistemas externos?

Os clientes precisarão migrar suas integrações para o ambiente de finanças e operações. Como o ponto de extremidade desse ambiente é diferente, os clientes talvez precisem atualizar ou alterar as integrações para que elas apontem para o novo ambiente. Essa tarefa será basicamente um processo manual, e as alterações necessárias dependerão da arquitetura da integração. Os clientes devem trabalhar com seu parceiro Microsoft para determinar a melhor abordagem para mover integrações.

## <a name="what-will-happen-to-microsoft-power-platform-dataverse-extensions-if-customers-merge-a-dynamics-365-human-resources-environment-with-an-existing-finance-and-operations-environment"></a>O que ocorrerá com as extensões do Microsoft Power Platform (Dataverse) se os clientes mesclarem um ambiente do Dynamics 365 Human Resources com um ambiente existente de finanças e operações?

Se os clientes decidirem mesclar um ambiente do Dynamics 365 Human Resources e um ambiente existente de finanças e operações em uma única instância do Dataverse após a migração, seus ambientes do Dataverse deverão ser combinados como parte do processo de mesclagem. Essa tarefa exigirá que qualquer aplicativo criado usando o Power Apps, e outras personalizações, seja reimplantado no novo ambiente.

## <a name="what-will-happen-to-documents-during-the-migration"></a>O que ocorrerá com os documentos durante a migração?

Quando os clientes migram seu ambiente do Dynamics 365 Human Resources para a infraestrutura de finanças e operações, os documentos permanecem no armazenamento de documentos existente e serão automaticamente mapeados para o novo ambiente na infraestrutura de finanças e operações.

Em uma versão futura, serão fornecidas novas entidades de dados. Depois que essa alteração é feita, os clientes que optam por mesclar seu ambiente do Dynamics 365 Human Resources com um ambiente existente de finanças e operações poderão exportar documentos e movê-los para o ambiente existente.

## <a name="after-the-migration-what-happens-to-the-batch-jobs-that-were-configured-in-dynamics-365-human-resources"></a>Após a migração, o que acontece aos trabalhos em lote que foram configurados no Dynamics 365 Human Resources?

Os trabalhos em lote precisarão ser reconfigurados no ambiente de finanças e operações. Os clientes terão que avaliar cada trabalho em lote e compará-lo com a lista atual de trabalhos em lote no ambiente de finanças e operações. Os clientes também devem analisar o planejamento geral de lote ao mesclar os dois conjuntos de trabalhos em lote para determinar se devem ser feitas alterações no planejamento do lote, nas prioridades ou nos grupos de lotes.

## <a name="how-will-the-migration-affect-the-lcs-project-for-dynamics-365-human-resources"></a>Como a migração afetará o projeto do LCS para o Dynamics 365 Human Resources?

Os clientes serão solicitados a criar um novo projeto do Microsoft Dynamics Lifecycle Service (LCS) e terão que selecionar os aplicativos de finanças e operações como o produto e a **Implementação** como o tipo de projeto. Além disso, um novo campo para o tipo de subprojeto é disponibilizado quando um projeto do LCS é criado. Os clientes precisarão selecionar a opção para migração do Dynamics 365 Human Resources para migrar um projeto existente do LCS de Recursos Humanos para a infraestrutura de finanças e operações.

Os recursos dos projetos do LCS de finanças e operações são diferentes dos recursos dos projetos do LCS de Recursos Humanos.

Para entrar em produção, novos clientes terão que executar as seguintes tarefas:

- Concluir a integração do projeto.
- Concluir a metodologia.
- Preencher um avaliador de assinatura.
- Concluir o processo de preparação para ativação.

## <a name="how-will-the-business-process-modeler-be-migrated"></a>Como o Modelador de processo de negócios será migrado?

Os clientes serão solicitados a exportar a biblioteca do Modelador de processo de negócios do projeto do LCS de Recursos Humanos e importá-la no projeto do LCS de finanças e operações. Além disso, os clientes precisarão atualizar as configurações da Ajuda no aplicativo para que elas apontem para o novo projeto do LCS.

## <a name="how-will-the-service-update-process-be-affected-by-the-migration"></a>Como o processo de atualização de serviço será afetado pela migração?

Após a migração, os clientes terão muito mais flexibilidade no ALM (gerenciamento do ciclo de vida do aplicativo) e nas atualizações de serviço. As atualizações de serviço não serão mais aplicadas automaticamente aos ambientes do Human Resources. Em vez disso, o serviço seguirá a funcionalidade e os processos de atualização do serviço do One Version, e as opções de configuração para atualizações por meio do LCS serão habilitadas.

## <a name="will-customers-be-eligible-for-fasttrack-assistance-with-the-infrastructure-merge"></a>Os clientes estarão qualificados para a assistência do FastTrack com a fusão da infraestrutura?

A Microsoft ainda está definindo quais ferramentas e recursos estarão disponíveis no FastTrack para ajudar na mesclagem.

## <a name="licensing-impact"></a>Impacto de licenciamento

Para obter mais informações sobre como o licenciamento é afetado, consulte [Perguntas frequentes sobre a mesclagem de infraestrutura do Dynamics 365 Human Resources](hr-infrastructure-merge-faq.md#licensing-impact).
