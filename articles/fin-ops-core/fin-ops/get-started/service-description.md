---
title: Descrição de serviço para aplicativos de finanças e operações
description: Este tópico fornece a descrição do serviço para aplicativos de finanças e operações.
author: tomhig
ms.date: 04/27/2022
ms.topic: article
audience: Application User, Developer, IT Pro
ms.reviewer: sericks
ms.search.region: Global
ms.author: whigginb
ms.search.validFrom: 2021-09-03
ms.openlocfilehash: 26b2821f33ea23dde1fda1d461baa5de1b4f9efc
ms.sourcegitcommit: d70f66a98eff0a2836e3033351b482466bd9c290
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/11/2022
ms.locfileid: "8740642"
---
# <a name="service-description-for-finance-and-operations-apps"></a>Descrição de serviço para aplicativos de finanças e operações

[!include[banner](../includes/banner.md)]

Os aplicativos de finanças e operações são ofertas de SaaS (software como serviço) de ERP (planejamento de recursos empresariais) criados no [Microsoft Azure](https://azure.microsoft.com/overview/what-is-azure/) e para ele. O serviço Finanças e operações fornece às empresas a funcionalidade de ERP que oferece suporte a suas necessidades exclusivas, ajudando-as a se ajustar aos ambientes comerciais em constantemente mudança, sem exigir que elas gerenciem a infraestrutura. Os aplicativos de finanças e operações podem incluir uma ou mais das seguintes áreas de solução:

- [Dynamics 365 Finance](/dynamics365/finance/)
- [Dynamics 365 Human Resources](/dynamics365/human-resources/)
- [Dynamics 365 Supply Chain Management](/dynamics365/supply-chain/)
- [Dynamics 365 Commerce](/dynamics365/commerce/)
- [Dynamics 365 Project Operations](/dynamics365/project-operations/)

Juntamente com [business intelligence](/power-bi/fundamentals/power-bi-service-overview), [infraestrutura](https://azure.microsoft.com/global-infrastructure/), [computação](/azure/service-fabric/service-fabric-overview), e [serviço de banco de dados](https://devblogs.microsoft.com/azure-sql/running-1m-databases-on-azure-sql-for-a-large-saas-provider-microsoft-dynamics-365-and-power-platform/), esses aplicativos permitem que as organizações executem processos comerciais operacionais e específicos do setor. Com o suporte do parceiro de implementação, os clientes determinam a configuração da lógica de aplicativos de negócios que melhor atende a seus processos comerciais exclusivos. A funcionalidade e os processos comerciais podem ser aumentados ou estendidos por meio de uma combinação de soluções a seguir:

- [Experiência de personalização interna](personalize-user-experience.md)
- Ferramentas do [Microsoft Power Platform](../../dev-itpro/power-platform/overview.md)
- [Kit de desenvolvimento do software (SDK) de Finanças e Operações](../../dev-itpro/dev-tools/developer-home-page.md) e [automação de compilação do Azure DevOps](../../dev-itpro/dev-tools/developer-home-page.md#build-automation-using-azure) [baseados no Visual Studio](https://visualstudio.microsoft.com)
- Soluções de ISV (fornecedor independente de software) do [AppSource](https://appsource.microsoft.com/partners)

Com base nas necessidades, os clientes escolhem a abordagem da solução. Eles funcionam com seu parceiro de implementação para definir, desenvolver e testar sua solução usando as ferramentas e práticas recomendadas fornecidas nos [LCS (Microsoft Dynamics Lifecycle Services)](../../dev-itpro/lifecycle-services/lcs.md). Há quatro cenários comuns:

- Configuração padrão "pronta para uso" de aplicativos de finanças e operações (sem extensões)
- Configuração de aplicativos de finanças e operações que inclui uma ou mais soluções de ISV
- Configuração de aplicativos de finanças e operações que inclui uma ou mais extensões específicas do cliente
- Configuração de aplicativos de finanças e operações que inclui uma combinação de extensões específicas do cliente e uma ou mais soluções de ISV

As organizações podem fazer a correspondência de seu crescimento comercial adicionando facilmente processos de usuários e de negócios por meio de um modelo simples e transparente de assinatura. Para obter mais informações sobre essas alterações, consulte o [Guia de licenciamento do Dynamics 365](https://www.microsoft.com/licensing/docs/view/Microsoft-Dynamics-365).

## <a name="operating-model"></a>Modelo de operação

O modelo de operação de aplicativos de finanças e operações define funções e responsabilidades específicas para o cliente, para o parceiro de implementação e para a Microsoft durante todo o ciclo de vida do serviço. Para obter mais informações, consulte [Operações de nuvem e manutenção](../../dev-itpro/lifecycle-services/cloud-operations-servicing.md).

### <a name="customer-activities"></a>Atividades do cliente

Os clientes trabalham com seus parceiros e o [Microsoft FastTrack](/dynamics365/fasttrack/) seguindo o [Guia de Implementação do Dynamics 365](https://community.dynamics.com/365/dynamics-365-fasttrack/p/dynamics365implementationguide), a estrutura e ferramentas e modelos de melhores práticas no [Success by Design](/dynamics365/fasttrack/success-by-design-overview) fornecidos no [Lifecycle Services](../../dev-itpro/lifecycle-services/lcs.md) para implementar sua solução. As atividades comuns incluem:

- Gerenciamento de segurança e identidades de usuário
- Definir, desenvolver e operar processos comerciais
- Definir, desenvolver, testar e operar extensões
- Monitorar e gerenciar implantações não relacionadas à produção
- Gerenciar atualizações de aplicativos e validar extensões
- Gerenciar soluções ISV e integrações de terceiros

### <a name="microsoft-responsibilities"></a>Responsabilidades da Microsoft

A Microsoft gerencia o serviço Finanças e operações implantando, monitorando ativamente e fazendo a manutenção dos ambientes de produção e de área restrita do cliente na assinatura do Microsoft SaaS. Esse gerenciamento inclui a alocação da infraestrutura de sistema necessária para executar o serviço e se comunicar proativamente com os clientes sobre a saúde do serviço. As responsabilidades incluem:

**Gerenciamento de infraestrutura**
- Segurança e isolamento
- Sistemas operacionais e virtualização
- Servidores, armazenamento e rede
- Capacidade de data center, rede, resfriamento

**Gerenciamento da plataforma de aplicativos**
- Monitoramento e notificações de aplicativos 24/7
- Diagnósticos, atualizações de plataforma, patches, atualizações de serviço
- Roteamento de aplicativos, balanceamento de carga, replicação de site
- Provisionamento e gerenciamento de ambiente
- Gerenciamento de banco de dados, HA (alta disponibilidade)/DR (recuperação de desastre), escala, operações
- Calcular implantação, expandir, reduzir

## <a name="system-configuration"></a>Configuração do sistema

Os aplicativos de finanças e operações são dimensionados de acordo com o volume da transações e a carga do usuário. Cada implementação de cliente produz uma solução exclusiva que consiste nos seguintes elementos:

- **Composição de dados** – um conjunto exclusivo de parâmetros que controlam o comportamento, o layout da organização, a estrutura de dados mestre (como dimensões financeiras e de estoque) e a granularidade do rastreamento de transações.
- **Extensão e configuração** – mecanismos de extensão que usam extensões de código, soluções de ISV e configurações exclusivas que incluem fluxos de trabalho, integrações e configurações de relatório.
- **Padrões de uso** – uma combinação exclusiva de uso online e em lote, juntamente com a capacidade de integração com sistemas de upstream e downstream para o fluxo de dados unificado e a capacidade de diferenciar com base nas exibições de informações que os clientes usam em seus processos comerciais.

A Microsoft configura ambientes de produção do cliente que são dimensionados para lidar com os volumes de transação e concorrência do usuário. A Microsoft é responsável pelas seguintes tarefas:

- Alocar corretamente os recursos dos ambientes de produção com base nas informações de criação de perfil do cliente no [avaliador de Assinatura do LCS](../../dev-itpro/lifecycle-services/subscription-estimator.md)
- Monitoramento e diagnóstico contínuos da disponibilidade de serviços dos ambientes de produção
- Análise e solução de problemas de desempenho do sistema com aplicativos de finanças e operações

Para garantir que uma implementação seja configurada para alto desempenho, os clientes deverão executar estas tarefas:

- Forneça informações de uso precisas sobre a implementação de Finanças e Operações no [Avaliador de assinatura do LCS](../../dev-itpro/lifecycle-services/subscription-estimator.md).
- Compile e teste extensões de desempenho e escala.
- Teste adequadamente as configurações de dados para desempenho.
- Garanta a escalabilidade fazendo [testes de desempenho](https://community.dynamics.com/365/b/techtalks/posts/performance-testing-approach-april-30-2018) antes da ativação.

## <a name="onboarding-and-implementation"></a>Integração e implementação

A tabela a seguir mostra eventos de implementação e integração comuns.

| Solicitar | Ação esperada da Microsoft | Ação esperada de parceiro de cliente/implementação |
|---|---|---|
| Compra da oferta inicial | Um projeto do LCS é criado após a compra da oferta, com base em um evento disparado pelo cliente. | Consulte o [processo comercial](before-you-buy.md) de EA (Enterprise Agreement) ou CSP (Provedor de Soluções de Nuvem). O parceiro cria um locatário para o cliente, se aplicável. |
| Compra do complemento | Conceda ao cliente acesso ao complemento selecionado durante a implementação. | Não Aplicável |
| Planejamento e análise de implementação | Fornecer ferramentas relevantes no LCS, como [BPM (Modelador de processo de negócios)](../../dev-itpro/lifecycle-services/bpm-overview.md) e [interoperabilidade com o Azure DevOps](../../dev-itpro/lifecycle-services/synchronize-bpm-vsts.md). | Fazer planejamento do projeto, configurar o Azure DevOps, concluir a integração do sistema e configurar contas de administrador. |

Para obter mais informações, consulte [Integração de um projeto de implementação](../imp-lifecycle/onboard.md).

## <a name="globalization"></a>Globalização

Os aplicativos de finanças e operações são fornecidos a partir de várias regiões do Azure ao redor do mundo. Os aplicativos de finanças e operações fornecem funcionalidade para oferecer suporte a diferentes países/regiões e idiomas nativos. Para obter mais informações, consulte [Recursos de localização e regulamentação](../../dev-itpro/lcs-solutions/country-region.md#localization-and-regulatory-features).

### <a name="countryregion-specific-considerations"></a>Considerações específicas do país/região

- Os clientes em organizações industriais ou comerciais reguladas que fazem negócios com entidades na França que exijam dados de residência local devem examinar [Finanças e Operações na França](../../dev-itpro/deployment/france-local-deployment.md).
- Os clientes com operações na China devem examinar o [guia estratégico do Azure China](/azure/china/) e [Finanças e Operações operado pela 21Vianet na China](../../dev-itpro/deployment/china-local-deployment.md).
- Os clientes com operações na Rússia devem revisar a [Legislação de localização de dados pessoais na Rússia](/business-applications-release-notes/october18/dynamics365-finance-operations/russian-regulations-on-prem#when-will-the-cloud-deployment-option-of-dynamics-365-for-finance-and-operations-be-generally-available-for-russia).

### <a name="general-data-protection-regulation-gdpr"></a>Regulamento Geral sobre a Proteção de Dados (GDPR)

Para os aplicativos de finanças e operações, a Microsoft atua como um processador. Como um processador de dados, o Finanças e Operações fornece processos e recursos que ajudam os clientes a cumprir as obrigações do RGPD como um controlador de dados. Para obter mais informações, consulte [Visão geral da GDPR](../../dev-itpro/gdpr/gdpr-guide.md).

## <a name="environment-and-data-management"></a>Ambiente e gerenciamento de dados

Esta seção descreve alguns eventos de ambiente e gerenciamento de dados típicos que ocorrem no serviço.

### <a name="environment-and-data-management-events-for-production-instances"></a>Eventos de gerenciamento de dados e ambiente para instâncias de produção

O LCS fornece [ferramentas de autoatendimento](../../dev-itpro/deployment/infrastructure-stack.md) e [operações de movimentação de banco de dados](../../dev-itpro/database/dbmovement-operations.md) que são usadas para executar tarefas de gerenciamento de dados e ambiente. Veja alguns exemplos:

**Evento:** [Solicitação de uma instância de produção](../imp-lifecycle/prepare-go-live.md#requesting-the-production-environment)

- Conclua a [lista de verificação de ativação](../imp-lifecycle/prepare-go-live.md) e envie-a para a equipe do [Microsoft FastTrack](/dynamics365/fasttrack/).
- Conclua o [avaliador de Assinatura do LCS](../../dev-itpro/lifecycle-services/subscription-estimator.md) antes de solicitar uma instância de produção.
- Conclua todas as tarefas de implementação especificadas na [metodologia do LCS](../../dev-itpro/lifecycle-services/create-methodology.md).

**Evento:** [Cópia de um banco de dados de área restrita para uma instância de produção](../../dev-itpro/database/dbmovement-scenario-goldenconfig.md)

- Realizado para uma ativação fictícia ou uma substituição de ativação real.

**Evento:** [Modo de manutenção](../../dev-itpro/sysadmin/maintenance-mode.md)

1. Ative o modo de manutenção no LCS.
2. Conclua a manutenção necessária.
3. Desative o modo de manutenção no LCS.

### <a name="environment-and-data-management-events-for-non-production-instances"></a>Eventos de gerenciamento de dados e ambiente para instâncias de não produção

O LCS fornece [provisionamento de autoatendimento](../../dev-itpro/deployment/infrastructure-stack.md) e [operações de movimentação de banco de dados](../../dev-itpro/database/dbmovement-operations.md) que são usadas para executar tarefas de gerenciamento de dados e ambiente. Veja alguns exemplos:

**Evento:** [Implantação de uma nova instância de área restrita](../../dev-itpro/deployment/deployenvironment-newinfrastructure.md)

- Verifique se todas as instâncias necessárias foram [planejadas](../imp-lifecycle/environment-planning.md) e se as ofertas aplicáveis do complemento foram compradas.
- Execute o processo de implantação no LCS.
- Conclua todas as tarefas especificadas nas listas de verificação do LCS.
    
>[!NOTE]
>Um ambiente de área restrita de desenvolvimento é uma VM (máquina virtual) [implantada na assinatura do Azure do cliente](../../dev-itpro/dev-tools/access-instances.md) e gerenciada pelo cliente.

**Evento:** [Cópia de um banco de dados de configuração dourada da área restrita para produção](../../dev-itpro/database/dbmovement-scenario-goldenconfig.md)

- Realizado para uma ativação fictícia ou uma substituição de ativação real.

**Evento:** [Restauração de um backup pontual de produção para uma instância de não produção](../../dev-itpro/database/database-pitr-prod-sandbox.md)

- Execute a opção [Atualizar banco de dados](../../dev-itpro/database/database-refresh.md) no LCs.
- Pós-cópia: exclua ou ofusque dados confidenciais por scripts, ajuste configurações de aplicativos específicos do ambiente (como pontos de extremidade de integração) e habilite ou adicione usuários. Observe que essas alterações são feitas pela aplicação de um [pacote de dados](../../dev-itpro/data-entities/data-entities-data-packages.md#import-a-data-package).

**Evento:** [Restauração pontual do banco de dados de instâncias de não produção](../../dev-itpro/database/database-point-in-time-restore.md)

- Aceite que o processo não pode ser desfeito.
- Execute a operação de restauração pontual no LCS.

**Evento:** Cópia de um banco de dados de área restrita de Camada 2 para uma área restrita de desenvolvimento para solução de problemas e [depuração](../../dev-itpro/database/dbmovement-scenario-debugdiag.md)

- Execute a operação de exportação do banco de dados no LCS no ambiente de área restrita de Camada 2.
- Importe e atualize o banco de dados no ambiente de desenvolvimento.

## <a name="data-backup-and-retention"></a>Backup e retenção de dados

Os bancos de dados para ambientes de Finanças e Operações na assinatura do SaaS são protegidos por backups automáticos. Para ambientes de produção, os backups automáticos serão mantidos por 28 dias, a menos que a Microsoft faça uma reversão. Para os ambientes de área restrita (Camada 2+), eles serão mantidos por sete dias. Uma reversão do ambiente de produção poderá ser realizada se ocorrer uma falha durante uma atualização de manutenção planejada.

Para obter mais informações sobre backups automáticos, consulte [Backups automatizados - Banco de Dados SQL do Azure e Instância Gerenciada do SQL](/azure/azure-sql/database/automated-backups-overview?tabs=single-database).

## <a name="service-activity-responsibilities"></a>Responsabilidades de atividade de serviço

A tabela a seguir descreve alguns cenários e atividades comuns do serviço. Também indica se a Microsoft, o cliente ou a Microsoft e o cliente têm a responsabilidade pelas atividades.

| Atividade | Responsabilidade da Microsoft | Responsabilidade do cliente |
|---|---|---|
| **Provisionamento de locatários iniciais** | | |
| Dimensione a carga projetada no LCS usando a ferramenta estimação de subscrição e solicite o provisionamento de determinados ambientes. | | X |
| Provisione todas as instâncias de produção e de não produção. | X | |
| Valide as instâncias de produção e de não produção implantadas. | | X |
| **Atualizações de serviço** | |
| Aplique atualizações de serviço a instâncias de produção e de não produção designadas. | X | |
| Aplique atualizações de serviço manualmente do LCS para instâncias de área restrita. Defina, desenvolva, teste a atualização e forneça o pacote de atualização de código novamente ao LCS. | | X |
| Solicite e agende que as atualizações de extensão sejam aplicadas à instância de produção. | | X |
| Crie um backup de código e de dados para a instância de produção antes da aplicação de qualquer atualização. | X | |
| No caso de falhas, reverta a instância de produção para o código e o backup de dados. | X | |
| **Gerenciamento de dados (backup, restauração e atualização)** | | |
| Faça backup do banco de dados. | X | |
| Determine a alta disponibilidade e um plano de recuperação de desastre. | X | |
| Monitore o desempenho do banco de dados de instâncias de produção. | X | |
| Ajuste o banco de dados de instâncias de produção para obter melhor desempenho. | X | |
| Execute a atualização point-in-time do banco de dados de instância de produção para uma instância de não produção. | | X |
| **Atualização da infraestrutura** | | |
| Atende atualizações regulares de infraestrutura. | X | |
| **Expansão e redução (usuários, armazenamento e instâncias)** | | |
| Compre usuários adicionais e complementos de não produção. | | X |
| Atualize alterações de uso na ferramenta avaliador de Assinatura do LCS. | | X |
| Relate qualquer problema de desempenho significativo que afete o uso do serviço. | | X |
| Gerencie proativamente os recursos necessários para o serviço aplicável. | X | |
| Investigue e solucione problemas de incidentes. | X | |
| **Segurança (acesso do usuário)** | | |
| Forneça ao usuário acesso ao serviço. | | X |
| Forneça acesso ao projeto LCS para o gerenciamento e a operação de instâncias que foram implantadas por meio do LCS. | | X |
| **Monitoramento de instâncias de produção** | | |
| Monitore as instâncias de produção 24/7. | X | |
| Notifique proativamente o cliente sobre incidentes que envolvem a instância de produção. | X | |
| **Gerenciamento e monitoramento de instâncias de não produção** | | |
| Gerencie instâncias de não produção usando o LCS. | | X |
| Monitore de instâncias de não produção. | | X |

## <a name="service-update-strategy"></a>Estratégia de atualização do serviço

De acordo com a [política de ciclo de vida do software](../../dev-itpro/migration-upgrade/versions-update-policy.md), os aplicativos de finanças e operações seguem a [Política de Ciclo de Vida Moderna](../../dev-itpro/migration-upgrade/versions-update-policy.md#modern-lifecycle-policy) da Microsoft, que abrange os produtos continuamente atendidos e com suporte. 

A Microsoft libera oito atualizações de serviço para os aplicativos de finanças e operações todo ano nos seguintes meses:

- Janeiro
- Fevereiro
- Abril
- Maio
- Julho
- Agosto
- Outubro
- Novembro

>[!NOTE]
>Abril e outubro são os principais ciclos de lançamentos de recursos. Os clientes podem pausar uma atualização de serviço individual por até três ciclos de atualização consecutivos.

Para obter mais informações, revise os seguintes tópicos:

- [Visão geral de atualizações do serviço One Version](../../dev-itpro/lifecycle-services/oneversion-overview.md)
- [Configurar atualizações de serviço por meio do LCS](../../dev-itpro/lifecycle-services/configure-service-updates.md)
- [Pausar atualizações de serviço por meio do LCS](../../dev-itpro/lifecycle-services/pause-service-updates.md)
- [Receber notificações sobre atualizações de serviço por meio do LCS](../../dev-itpro/lifecycle-services/notifications-service-updates.md)
- [Ferramentas de teste de regressão para validar atualizações de serviço](../../dev-itpro/perf-test/rsat/rsat-overview.md)
- [Roteiro e ciclos de lançamentos do Dynamics 365](https://dynamics.microsoft.com/roadmap/overview/)

## <a name="security-and-administrative-access"></a>Segurança e acesso administrativo

O acesso administrativo a um ambiente de produção de Finanças e Operações é estritamente controlado e registrado. Os dados do cliente são manuseados de acordo com os [Termos do Microsoft Online Services](https://www.microsoft.com/licensing/terms/productoffering). 

### <a name="customer-administrative-access"></a>Acesso administrativo do cliente

O administrador de locatários do cliente pode acessar instâncias de produção ou instâncias de não produção, conforme descrito na tabela a seguir:

| Tipo de ambiente | Finalidade | Nível de acesso do cliente |
|---|---|---|
| **Não produção**<br>Área restrita de Camada 1 | Um ambiente de não produção que os clientes implantam para fins de desenvolvimento, demonstração ou treinamento. | Uma área restrita de Camada 1 (também conhecida como um ambiente hospedado em nuvem) é uma VM gerenciada pelo cliente que é implantada na assinatura do Azure do cliente do LCS. Como é uma VM na assinatura do Azure do cliente, o cliente tem acesso administrativo total ao ambiente por meio da Área de Trabalho Remota. |
| **Não produção**<br>Área restrita de Camada 2 (ou superior) | Um ambiente de não produção que os clientes implantam para testes de aceitação de usuários, testes de integração, treinamento, preparo ou qualquer outro cenário de pré-produção. | As áreas restritas de Camada 2 e superior são implantadas na assinatura do SaaS de Finanças e Operações. O acesso aos bancos de dados SQL do Azure associados ao ambiente de não produção é concedido por meio do [acesso just-in-time](../../dev-itpro/database/database-just-in-time-jit-access.md). O acesso à Área de Trabalho Remota não está disponível. |
| **Produção** | Um ambiente de produção é implantado quando o projeto está [pronto para a ativação inicial](../imp-lifecycle/environment-planning.md#production-system-readiness). | Os ambientes de produção são implantados na assinatura do SaaS. Todo o acesso é feito por meio do navegador, de pontos de extremidade de serviço ou do LCS. |

### <a name="microsoft-administrative-access"></a>Acesso administrativo da Microsoft

A tabela a seguir mostra os diferentes níveis de acesso para diferentes administradores da Microsoft:

| Administrador | Dados do cliente |
|---|---|
| Equipe de respostas de Operações<br>(Limitado somente ao pessoal principal) | O acesso é concedido por meio de um tíquete de suporte. O acesso é auditado e limitado à duração da atividade de suporte. |
| CSS (Serviços de Atendimento ao Cliente) da Microsoft | Sem acesso direto. O cliente pode usar o compartilhamento de tela para trabalhar com a equipe de suporte para depurar problemas. |
| Engenharia | Sem acesso direto. A equipe de resposta de Operações pode usar o compartilhamento de tela para trabalhar com engenharia para depurar problemas. |
| Outros na Microsoft | Sem acesso. |

## <a name="monitoring"></a>Monitoramento

A Microsoft investiu em um conjunto de ferramentas extensivo para monitorar e diagnosticar as instâncias de produção dos clientes. A Microsoft monitora os ambientes de produção dos clientes 24 horas por dia, 7 dias por semana. Para obter mais informações, consulte [Suporte e monitoramento em produção](../imp-lifecycle/production-support-monitoring.md).

| Responsabilidades da Microsoft | Responsabilidades do cliente |
|---|---|
| <ul><li>Monitorar a disponibilidade do serviço.</li><li>Monitorar e alertar continuamente as métricas e os watchdogs de integridade para componentes críticos como o AOS (Servidor de Objetos de Aplicativo), Lote, DIXF (Estrutura de Importação/Exportação de Dados), Commerce e Management Reporter.</li><li>Monitorar a degradação de desempenho causada por serviços de infraestrutura (como o Azure Active Directory \[Azure AD\] e SQL do Azure).</li><li>Se a Microsoft determinar que um único processo ou trabalho em lotes está causando aberrações, esse processo ou trabalho será encerrado após a comunicação com o cliente.</li></ul> | <ul><li>Monitore alterações nas configurações e nas extensões dos aplicativos que podem causar problemas funcionais e de desempenho.</li><li>Os erros do aplicativo devem ser diagnosticados com as ferramentas de monitoramento. Use essas ferramentas para diagnosticar aberrações de desempenho relatados pelo usuário.</li><li>Informe a Microsoft se houver uma carga esperada no sistema além do uso de pico projetado.</li><li>Se o serviço aplicável não estiver disponível na instância de produção, o cliente poderá usar o LCS para relatar uma [interrupção da produção](../../dev-itpro/lifecycle-services/report-production-outage.md).</li></ul> |

Ao enviar solicitações de suporte online, por meio de LCS, os clientes permitem que a Microsoft forneça especialização técnica rápida e profunda da maneira mais eficiente e efetiva. Embora haja uma opção telefônica disponível, ela só deverá ser usada se a opção online não estiver disponível. Para obter mais informações, consulte [Opções de suporte telefônico](/power-platform/admin/support-overview?toc=%2Fdynamics365%2Ffin-ops-core%2Fdev-itpro%2Ftoc.json&bc=%2Fdynamics365%2Fbreadcrumb%2Ftoc.json#is-there-a-phone-number-i-can-call-to-contact-support).

## <a name="incident-management"></a>Gerenciamento de incidentes

A Microsoft responde a incidentes e os corrige com base nos níveis de severidade. Os níveis de severidade de incidentes da Microsoft podem ser alterados durante a avaliação inicial do incidente e, à medida que mais informações sobre o impacto e o escopo se tornarem disponíveis. Se o incidente for corrigido, a severidade do incidente permanecerá inalterada.

Para obter mais informações sobre os níveis de severidade, consulte [esta tabela de severidades](/power-platform/admin/support-overview#what-is-initial-response-time-and-how-quickly-can-i-expect-to-hear-back-from-someone-after-submitting-my-support-request).

## <a name="business-continuity-through-high-availability-and-disaster-recovery"></a>Continuidade de negócios por meio de alta disponibilidade e recuperação de desastre 

A Microsoft fornece continuidade de negócios e recuperação de desastres para instâncias de produção de aplicativos de finanças e operações no caso de paralisações em toda a região do Azure. Para obter mais informações, incluindo RTO (objetivo do tempo de recuperação de serviço) e RPO (objetivo de ponto de recuperação), consulte [Continuidade dos negócios e recuperação de desastres](../../dev-itpro/sysadmin/business-continuity-disaster-recovery.md).

- **Alta disponibilidade** – a funcionalidade ha fornece maneiras de evitar o tempo de inatividade causado pela falha de um único nó em um data center do Azure. As arquiteturas de nuvem de cada serviço usam conjuntos de disponibilidade do Azure para a camada computacional para evitar eventos de ponto único de falha. A HA para bancos de dados é fornecida por meio dos [recursos de HA do SQL do Azure](/azure/azure-sql/database/high-availability-sla).
- **Recuperação de desastre** – os [recursos de recuperação de desastre do Azure](/azure/best-practices-availability-paired-regions) protegem cada serviço contra paralisações que afetem amplamente todo o datacenter do Azure. Estes são alguns dos recursos:

    - Replicação geográfica ativa do SQL do Azure para o banco de dados primário (banco de dados comercial).
    - Cópias de redundância geográfica do Armazenamento de Blobs do Azure (que contém anexos de documento) em outras regiões do Azure.
    - Região secundária das replicações do Armazenamento de Blobs do Azure e do SQL do Azure.

Se a recuperação de desastre for usada para recuperar a instância de produção do cliente, a Microsoft e o cliente atenderão às responsabilidades de [gerenciamento de incidentes](service-description.md#incident-management).

Os planos e procedimentos de Recuperação de Desastre da Microsoft são examinados regularmente por meio de auditorias de SOC (Controles de Sistema e Organização). Essas auditorias de conformidade atestam o processo técnico e de procedimentos do DR da Microsoft, incluindo os aplicativos de Finanças e Operações do Dynamics 365. Os relatórios de auditoria de [conformidade com SOC](/compliance/regulatory/offering-soc-2) e todos os outros relatórios de conformidade estão disponíveis em [Ofertas de Conformidade da Central de Confiabilidade da Microsoft](/compliance/regulatory/offering-home).

## <a name="finance-and-operations-support-offerings"></a>Ofertas de suporte de Finanças e Operações

O suporte técnico está disponível em mercados onde os serviços de Finanças e Operações são oferecidos. [Experiências de suporte](../../dev-itpro/lifecycle-services/lcs-support.md) são fornecidas no LCS ou nos aplicativos de finanças e operações Veja alguns exemplos:

- [Pesquisa de problemas](../../dev-itpro/lifecycle-services/issue-search-lcs.md) no LCS
- [Suporte técnico integrado](../../dev-itpro/lifecycle-services/support-experience.md) nos aplicativos de finanças e operações
- [Suporte habilitado para a nuvem](../../dev-itpro/lifecycle-services/cloud-powered-support-lcs.md) no LCS

A Microsoft oferece aos clientes de Finanças e Operações três planos de suporte: Premier, Professional Direct e o suporte incluído na assinatura. O nível de suporte difere por plano. A tabela a seguir mostra uma comparação entre os três planos.

| Recurso de suporte | Premier | Professional Direct | Assinatura |
|---|---|---|---|
| Envio ilimitado de incidentes por quebra/conserto | Sim | Sim | Sim |
| Acesso 24/7 via LCS | Sim | Sim | Sim |
| Tempo de resposta ao incidente | Menos de uma hora | Menos de uma hora | Próximo dia útil |
| Horas de consultoria | Os pools são adquiridos por contrato. | Não | Não |
| Gerente de conta de suporte dedicado | Sim | Não | Não |
| Engenheiro de suporte dedicado | Envolvido em um contrato separado | Não | Não |

Para obter mais informações, consulte [Visão geral do suporte](/power-platform/admin/support-overview).

### <a name="process-to-engage-support"></a>Processo para envolver o suporte

No caso de incidentes que envolvam os aplicativos de finanças e operações, os clientes enviam tíquetes de suporte para a Microsoft por meio do LCS. O CSS lida com os incidentes, com base no plano de suporte do cliente e na severidade do incidente, conforme designado pelo CSS.

### <a name="service-level-agreement"></a>Contrato de Nível de Serviço

A Microsoft está comprometida com uma taxa de disponibilidade de 99,9% por mês do serviço. Se a Microsoft não conseguir manter o nível de serviço para o serviço aplicável conforme descrito no SLA (contrato de nível de serviço), o cliente poderá se qualificar para um crédito em relação a uma parte de suas taxas de serviço mensais para esse serviço. Para obter informações sobre como iniciar um crédito de serviço, consulte a seção "Solicitações" do [SLA](https://www.microsoft.com/licensing/docs/view/Service-Level-Agreements-SLA-for-Online-Services).

## <a name="important-resources"></a>Recursos importantes

- **[Central de Confiabilidade](https://www.microsoft.com/trust-center)** – obtenha informações sobre onde seus dados de Finanças e Operações estão armazenados, além de informações adicionais sobre privacidade, conformidade e procedimentos de segurança.
- **[Termos de licenciamento e documentação](https://www.microsoftvolumelicensing.com/)** – acesse rapidamente os termos de licenciamento, as condições e as informações complementares relevantes ao uso de produtos e serviços licenciados por meio de programas de licenciamento por volume da Microsoft.
- **[Condições de licenciamento](https://www.microsoft.com/licensing/product-licensing/)** – os recursos nesta página definem os termos e as condições para o software e os produtos de serviços online que você compra por meio dos programas de licenciamento comercial da Microsoft.
- **[Política de Ciclo de Vida da Microsoft](/lifecycle/)** – esta página fornece diretrizes consistentes e previsíveis para a disponibilidade de suporte durante toda a vida de um produto.
- **[Guia de licenciamento](https://www.microsoft.com/licensing/docs/view/Microsoft-Dynamics-365)** – use este guia para saber mais sobre como licenciar o Dynamics 365.
- **[Suporte ao cliente](https://dynamics.microsoft.com/support/)** – obtenha o suporte líder do setor para seus aplicativos Dynamics 365.
- **[Dynamics Lifecycle Services](https://lcs.dynamics.com/)** – gerencie seu ciclo de vida de aplicativos e obtenha implementações previsíveis, reproduzíveis e de alta qualidade.
- **[Guia de Implementação do Dynamics 365](https://aka.ms/D365ImplementationGuideFlip)** - O Guia de Implementação do Dynamics 365 documenta os princípios do Success by Design testados por tempo e fornece uma orientação prescritiva para arquitetar, criar, testar e implantar soluções do Dynamics 365.

## <a name="definitions"></a>Definições

### <a name="azure-region"></a>[Região do Azure](/azure/availability-zones/az-overview#regions)

Uma região geográfica em que existe um ou mais datacenters do Azure. Exemplos incluem os EUA e a Europa.

### <a name="business-process-modeler-bpm"></a>[Modelador de processo de negócios (MPB)](../../dev-itpro/lifecycle-services/bpm-overview.md)

Uma ferramenta no LCS que ajuda a concluir uma análise de lacuna para uma determinada implementação usando definições de processos empresariais da APQC (American Productivity & Quality Center) com suporte nos aplicativos de finanças e operações.

### <a name="cloud-solution-provider"></a>Provedor de soluções de nuvem

Um parceiro que faz parte do programa CSP (Provedor de Soluções de Nuvem)da Microsoft e fornece aos clientes serviços de nuvem de valor agregado, suporte, uma fatura e gerenciamento de clientes em escala.

### <a name="customer"></a>Cliente

Uma entidade comercial que consome aplicativos de finanças e operações e é representada por um locatário no Office 365.

### <a name="development-environment"></a>Ambiente de desenvolvimento

Um ambiente de área restrita que não seja de produção usado para desenvolver extensões. Os clientes implantam esse ambiente em sua própria assinatura do Azure desde o LCS. Esse ambiente também pode ser usado para demonstração, treinamento ou outras tarefas de teste. Também é conhecido como [área restrita de Camada 1](../imp-lifecycle/environment-planning.md#tier-1-vs-tier-2-and-higher).

### <a name="downtime"></a>Tempo de inatividade

Qualquer período no qual os usuários não podem entrar ou acessar seu locatário ativo por causa de uma falha na plataforma ou na infra-estrutura de serviço que a Microsoft não expirou, como determina o monitoramento de integridade automatizado e os logs do sistema. O tempo de inatividade não inclui tempo de inatividade programado, a indisponibilidade de recursos complementares de serviço, a incapacidade de acessar o serviço devido a suas modificações no serviço, ou períodos em que a capacidade da unidade de escala é excedida.

### <a name="implementation-partner"></a>Parceiro de implementação

O parceiro que o cliente seleciona para personalizar, configurar, implementar e gerenciar suas soluções de Finanças e Operações.

### <a name="incident"></a>Incidente

Um problema que os clientes encontram enquanto usam o serviço de Finanças e Operações e para o qual enviam um tíquete via LCs.

### <a name="microsoft-customer-support-services-css"></a>CSS (Serviços de Atendimento ao Cliente) da Microsoft

A equipe de suporte global da Microsoft dedicada ao fornecimento de serviços de qualidade para aplicativos de finanças e operações.

### <a name="microsoft-dynamics-lifecycle-services-lcs"></a>Microsoft Dynamics Lifecycle Services (LCS)

O portal administrativo para o gerenciamento do ciclo de vida de aplicativos de finanças e operações, desde a avaliação à implementação e até o gerenciamento e o suporte pós-produção. Para obter mais informações, consulte [Recursos do Lifecycle Services](../../dev-itpro/lifecycle-services/lcs.md).

### <a name="non-production-instance"></a>Instância de não produção

Qualquer uma das seguintes instâncias de um serviço usado pelo cliente para validar extensões e executar outras tarefas de desenvolvimento:

- **Área restrita de Camada 1** – instância do desenvolvedor (hospedado pelo cliente)
- **Área restrita de Camada 2** – instância de teste de aceitação padrão
- **Área restrita de Camada 3 – 5** – áreas restritas complementares

Para obter mais informações sobre as Camadas 2 a 5, consulte [Seleção do ambiente correto de Camada 2 ou superior](../imp-lifecycle/environment-planning.md#selecting-the-correct-tier-2-or-higher-environment).

### <a name="production-instance"></a>Instância de produção

Um ambiente de Finanças e Operações usado pelo cliente para gerenciar as transações diárias e os processos de negócios "ativos".

### <a name="sandbox-environment"></a>Ambiente de área restrita

Um ambiente de não produção que o cliente usa para demonstração, treinamento, teste de aceitação de usuários, validação de extensões e outras tarefas de teste.

### <a name="service"></a>Serviço

Qualquer um dos serviços principais incluídos nos aplicativos de finanças e operações.

### <a name="service-level-agreement-sla-for-microsoft-online-services"></a>SLA (contrato de nível de serviço) para serviços online da Microsoft

O SLA se aplica aos serviços online da Microsoft. Para obter mais informações, consulte [Contratos de Nível de Serviço](https://www.microsoft.com/licensing/docs/view/Service-Level-Agreements-SLA-for-Online-Services).

### <a name="service-update"></a>Atualização de serviço

Os ambientes de Finanças e Operações de serviços Microsoft em uma base consistente por meio de atualizações de serviço. Os clientes definem seu próprio calendário de atualização de serviço, com base nas necessidades comerciais. Para obter informações, consulte [Atualizações do serviço One Version](../../dev-itpro/lifecycle-services/oneversion-overview.md).

### <a name="success-by-design"></a>[Success by Design](/dynamics365/fasttrack/success-by-design-overview)

A estrutura que orienta sistematicamente uma implementação por meio de uma série de avaliações em estágios críticos para garantir a ótima arquitetura, a segurança, o desempenho e a experiência do usuário para uma solução do Dynamics 365.

### <a name="user"></a>Usuário

Uma única pessoa que use ambientes de Finanças e Operações e que esteja associada ao locatário de um cliente.
