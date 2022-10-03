---
title: Atualizações de qualidade proativas
description: Este artigo fornece informações sobre a entrega proativa de atualizações de qualidade.
author: rashmansur
ms.date: 09/12/2022
ms.topic: article
audience: Application User, Developer, IT Pro
ms.reviewer: sericks
ms.search.region: Global
ms.author: rashmim
ms.search.validFrom: 2022-08-19
ms.search.form: ''
ms.dyn365.ops.version: 10.0.29
ms.openlocfilehash: c2d26b7c5e110d05806c064e15a3ad2af34d0fbd
ms.sourcegitcommit: fde2867524b6a851628185cbdeee60a6ad918d08
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/26/2022
ms.locfileid: "9592037"
---
# <a name="proactive-quality-updates"></a>Atualizações de qualidade proativas

[!include[banner](../includes/banner.md)]

Nos últimos anos, a Microsoft fez um progresso contínuo no que denominamos [One Version](../../dev-itpro/lifecycle-services/oneversion-overview.md). A premissa de One Version é simples: quanto mais clientes usarem a mesma versão do software, maior será a qualidade oferecida. Encontramos e corrigimos os problemas uma vez, e mais clientes tiveram acesso a essas soluções com mais rapidez.

Essa premissa é confirmada pelos resultados: menos incidentes em nossos produtos. Quando os clientes não estão na mesma versão, é comum serem afetados por problemas para os quais já existe uma solução disponível. Fizemos grandes progressos com o Dynamics 365 Finance, o Dynamics 365 Supply Chain, o Dynamics 365 Project Operations e o Dynamics 365 Commerce. Graças a avanços técnicos recentes, agora é possível dar o próximo passo. As informações a seguir traçam um panorama do que faremos, do que já fizemos, além de como e quando apresentaremos os novos recursos sem interrupção.

## <a name="focus-on-quality-updates"></a>Foco em atualizações de qualidade

No momento, oferecemos sete [atualizações de serviço](public-preview-releases.md) por ano. Por exemplo, a versão 10.0.29 é uma atualização de serviço. Até recentemente, foram feitas oito atualizações por ano. No entanto, eliminamos uma atualização em resposta a comentários de clientes que revelou um desejo de evitar alterações próximo ao final do ano civil.

Não estamos alterando a cadência das atualizações de serviço. O próximo passo da jornada One Version é voltado para *atualizações de qualidade*. As atualizações de qualidade são compilações cumulativas de hotfixes. Elas não incluem novos recursos. A qualquer momento, a comunidade inteira de clientes é distribuída entre as três ou quatro atualizações de serviço mais recentes. No entanto, para qualquer atualização de serviço específica, dezenas de versões de atualização de qualidade distintas podem ser usadas no grupo, dependendo das datas de implantação por pessoas. Na próxima etapa, transmitiremos proativamente atualizações de qualidade. Já usamos esse modelo em nossos aplicativos baseados no Dataverse e vimos os resultados esperados da qualidade aprimorada e menos incidentes de suporte.

É claro que uma redução nos defeitos pode reduzir ou eliminar totalmente a necessidade de atualizações de qualidade. Temos várias iniciativas em curso para reduzir os defeitos que exigem atualizações de qualidade. Mesmo quando os conteúdos forem reduzidos na atualização de qualidade, a consistência na base de clientes melhorará a capacidade de suporte, obterá melhorias para os clientes mais rapidamente e reduzirá a frequência de clientes com problemas para os quais já existem soluções.

## <a name="making-proactive-distribution-possible"></a>Tornar possível a distribuição proativa

Vários avanços já foram implantados para permitir a entrega proativa de atualizações de qualidade:

- **Atualização do tempo de inatividade quase zero**: para enviar ambientes mais frequentes, é essencial que o impacto na disponibilidade do ambiente seja reduzido para preservar os contratos de nível de serviço (SLAs) do Dynamics 365. A atualização do tempo de inatividade quase zero foi originalmente apresentada para ajudar a melhorar a aplicação de patch do sistema operacional mensal usando um failover de cluster para ativar a imagem atualizada com interrupção mínima. O mecanismo para aplicar atualizações está sendo aprimorado para que seja ainda menos prejudicial, e abrangerá a aplicação de patch do sistema operacional e a implantação da atualização de qualidade.

    Para usuários interativos, uma sessão ativa pode ser interrompida e a repetição irá para o ambiente atualizado agora. Com a introdução do [agendamento de lotes com base na prioridade](../../dev-itpro/sysadmin/priority-based-batch-scheduling.md), que agora está disponível com base na aceitação, o agendamento e o processamento em lotes são recuperados e retomados imediatamente após a atualização. O agendamento de lotes com base na prioridade será feito para os clientes antes que comecem a participar da distribuição proativa de atualizações de qualidade para ambientes de produção.

- **Horas escuras**: as horas escuras são definidas para cada região do Azure e as atualizações de tempo de inatividade quase zero ocorrerão no período de hora escura.

## <a name="the-proactive-update-process"></a>O processo de atualização proativo

A implantação de atualizações de qualidade proativas seguirá um processo de implantação seguro (SDP). As especificações do SDP evoluirão, mas as atualizações de qualidade serão inicialmente implantadas em ambientes de área restrita. O processo iniciará com ambientes que aceitam a implantação antecipada. Como a porcentagem de áreas restritas implantadas com êxito aumenta, a implantação em ambientes de produção será iniciada. Vale lembrar que o processo iniciará com ambientes que aceitam a implantação antecipada. Os sistemas de escuta monitorarão a telemetria do sistema e incidentes de Livesite, e interromperão a distribuição de uma versão específica se qualquer regressão for detectada. Caso desejem, os clientes ainda poderão extrair as atualizações de qualidade antes da implantação proativa.

Os dados atuais de gerenciamento de versões mostram que menos de 3% das regressões são introduzidas em atualizações de qualidade. Com o aumento do foco na eliminação da regressão e de um SDP aprimorado, o impacto potencial das regressões será bem menor do que os ganhos de qualidade obtidos por meio da agilidade na implantação de correções implantadas para clientes.

## <a name="process-changes"></a>Processar alterações

Um conjunto de alterações de processo está sendo implementado antes da ativação da implantação de atualização de qualidade proativa:

- **Esquema**: a ferramenta garante que as compilações de atualização de qualidade incluam somente alterações de esquema que possam ser aplicadas enquanto o serviço está online. Essa abordagem ajudará a manter a capacidade de aplicar a atualização com tempo de inatividade quase zero.
- **Maior investigação de alterações**: no momento, já existe uma etapa de processo extra para aprovar alterações para inclusão em uma atualização de qualidade. A investigação na etapa extra será maior para ajudar a reduzir o potencial de regressões. Alterações interruptivas não são permitidas em atualizações de qualidade e a maior investigação de alterações ajudará a garantir a atingir esse objetivo.
- **Visibilidade**: enviamos notificações por email e pelo Lifecycle Services (LCS) para atualizações futuras de qualidade proativa. Além disso, as equipes de suporte e os clientes potenciais de incidentes terão visibilidade sobre onde as atualizações de qualidade foram implantadas de forma proativa.
- **Segurança contra falhas por versão de pré-lançamento** – A versão de pré-lançamento será usada para proteger as alterações de código sempre que aplicável em uma correção de bug de atualização de qualidade ou usar a versão de pré-lançamento de recurso existente relevante para a correção. Se for necessário um fallback ou desativar uma alteração após uma implantação proativa, isso poderá ser feito por meio do sistema de versão de pré-lançamento para evitar mais falhas.
- **Designação de sincronização da área restrita**: menos de 20% dos clientes têm várias áreas restritas e mantêm uma área restrita implantada onde a versão corresponde à produção, para ajudar na solução de problemas. Se um cliente estiver usando uma área restrita para testar uma versão mais recente do que a produção dele, essa área restrita receberá atualizações de qualidade para a versão mais recente.

## <a name="what-is-the-rollout-roadmap-for-quality-updates"></a>Qual é o mapa de distribuição para atualizações de qualidade?

Espera-se que a distribuição de atualizações de qualidade proativa para ambientes de área restrita comece no final de setembro ou outubro de 2022 para clientes da nuvem pública do Azure. Os ambientes de avaliação também começarão a receber a implantação de atualizações proativas nesse momento. Em setembro, uma notificação será enviada a cada cliente para informá-lo sobre o plano esperado para seus ambientes. As exceções para o processo de distribuição de atualizações proativas serão permitidas somente para clientes regulamentados pelo FDA. Ainda estamos pensando como ambientes regulamentados e clientes de nuvem soberana e governamentais serão gerenciados.

Nos próximos seis meses, aumentaremos gradualmente a porcentagem de ambientes de área restrita que recebem atualizações proativas, até que todos os ambientes designados sejam incluídos e cheguem à atualização dos ambientes de produção. Durante todo o período, monitoraremos para garantir que o processo de implantação seja perfeito e que atinjamos nossa meta de payloads sem interrupção.

Como os clientes receberão, normalmente, payloads menores, esperamos que o processo de atualização seja simplificado. Ajustaremos a frequência da implantação de atualizações quando demonstrarmos a capacidade de executar o processo sem interrupção. Esse processo já opera de forma efetiva para a plataforma e os aplicativos do Dataverse, e oferece os aperfeiçoamentos previstos na qualidade do serviço. Estamos ansiosos para avançar da mesma forma com aplicativos de finanças e operações.

## <a name="when-will-quality-updates-start-for-production-environments"></a>Quando as atualizações de qualidade serão iniciadas para ambientes de produção?
Neste momento, as atualizações de qualidade estão direcionando apenas áreas restritas. Atualizaremos este espaço com uma data de início para ambientes de produção quando tivermos dados e métricas mais concretos de atualizações proativas para áreas restritas para avaliar a prontidão para produção.

## <a name="what-is-the-schedule-for-sandbox-quality-updates"></a>Qual é a programação para atualizações de qualidade de área restrita?
Para obter informações sobre as horas escuras de cada região, consulte [Qual é a programação das atualizações de qualidade proativas?](../../dev-itpro/deployment/plannedmaintenance-selfservice.md#what-is-the-schedule-for-proactive-quality-updates).

## <a name="how-are-the-dark-hours-handled-for-customers-that-have-one-finance-and-operations-apps-instance-but-are-active-in-multiple-time-zones"></a>Como as horas escuras são tratadas para clientes que têm uma instância de aplicativos de finanças e operações, mas estão ativas em vários fusos horários? 
Não há programações especiais fora das horas escuras nas quais existe uma instância de aplicativos de finanças e operações, pois pretendemos lançar atualizações de qualidade de maneira minimamente prejudicial com o [nZDT](../../dev-itpro/deployment/plannedmaintenance-selfservice.md#what-does-near-zero-downtime-maintenance-mean).

## <a name="how-will-microsoft-ensure-the-quality-of-these-updates"></a>Como a Microsoft garantirá a qualidade dessas atualizações?
A Microsoft se esforça para manter o pipeline de lançamento suficientemente eficiente para fornecer cargas pequenas para manter o custo de validação baixo. Cada correção em uma atualização de qualidade passa por um processo de implantação rigoroso e seguro que ajuda a melhorar a qualidade e a confiabilidade, reduzindo o impacto do cliente. A implantação ocorrerá em estágios em ambientes de área restrita primeiro, seguidos por produção. As implantações em etapas permitem o monitoramento adequado para determinar se a implantação será segura. A distribuição será interrompida se forem detectados problemas com cada grupo de clientes implantados e nós garantiremos que cada etapa da distribuição tenha tempo suficiente para gerar problemas. Para cada atualização de qualidade futura, forneceremos visibilidade da programação por meio de atualizações na documentação e em emails públicos, para que os clientes possam se planejar com antecedência.

## <a name="can-customers-delay-reschedule-or-pause-a-quality-update"></a>Os clientes podem atrasar, reprogramar ou pausar uma atualização de qualidade?
Não. O principal objetivo das atualizações de qualidade é garantir que os conceitos básicos como segurança, privacidade, confiabilidade, disponibilidade e desempenho sejam continuamente aperfeiçoados para nossos clientes. Ao atrasar ou pausar uma atualização, a segurança, a disponibilidade e a confiabilidade estarão em risco.

## <a name="how-can-one-know-the-set-of-changes-that-went-into-a-quality-update-payload"></a>Como é possível saber o conjunto de alterações feitas em uma carga de atualização de qualidade?
Você poderá examinar todos os artigos da base de dados de conhecimento em uma versão de atualização de qualidade na página **Detalhes do ambiente** no LCS, navegando até a seção **Atualização de qualidade**. 

## <a name="what-is-the-process-if-a-critical-issue-is-found-after-a-quality-update"></a>Qual será o processo se um problema crítico for encontrado após uma atualização de qualidade?
Um problema crítico ou regressão é um ou mais eventos que geralmente fazem com que vários clientes tenham uma experiência degradada com um ou mais dos nossos serviços. Esses problemas podem causar um tempo de inatividade não planejado, incluindo indisponibilidade, degradação do desempenho e interferência com o gerenciamento de serviços. Se houver um impacto amplo no cliente devido a essas regressões, a implantação de uma atualização de qualidade será interrompida até que possamos comunicar e corrigir o problema. Normalmente, a próxima atualização de qualidade terá a correção necessária para retomar a distribuição.

Se um ambiente de cliente único for afetado, entre em contato o suporte da Microsoft para abrir um tíquete. Com base na justificativa, a implantação da atualização de qualidade será interrompida em todos os outros ambientes do projeto até que o problema seja reduzido.

## <a name="can-customers-still-manually-apply-hotfix-updates-from-lcs"></a>Os clientes ainda podem aplicar atualizações de hotfix manualmente no LCS?
Sim. Para garantir a paridade contínua com a forma como os hotfixes funcionam, as atualizações de hotfix ainda podem ser aplicadas a ambientes de cliente no LCS. No entanto, é importante observar que os hotfixes implantados como parte de uma atualização de qualidade passam pelo SDP padrão antes da atualização ser implantada. Isso reduz o risco de regressões devido a uma qualidade superior. Recomendamos que você escolha uma atualização de qualidade em vez da aplicação manual de hotfixes para maior confiabilidade.

## <a name="can-customers-self-install-a-quality-update-build-by-themselves-ahead-of-the-schedule"></a>Os clientes podem instalar por conta própria a versão de uma atualização de qualidade antes da programação?
Sim. Você pode instalar uma atualização de qualidade proativamente. A Microsoft ignorará a atualização se a versão de compilação atual do ambiente for igual ou maior do que a atualização de qualidade em questão.

## <a name="if-an-environment-has-an-upcoming-scheduled-monthly-service-update-within-a-week-will-it-still-receive-quality-updates"></a>Se um ambiente tiver uma atualização de serviço mensal programada dentro de uma semana, ele ainda receberá atualizações de qualidade?
- As atualizações de qualidade não serão aplicadas se houver uma atualização de serviço iminente programada dentro de uma semana a partir da qual a atualização de qualidade está programada para ocorrer.
- Se um ambiente de área restrita tiver uma versão de compilação igual ou superior à da atualização de qualidade iminente, ele será ignorado.
- Se um ambiente de produção tiver uma versão de compilação igual ou superior à da atualização de qualidade iminente, ele será ignorado.
- Se uma área restrita tiver a mesma versão de compilação ou superior devido a uma atualização de qualidade ou uma atualização manual da produção, a produção ainda receberá a versão programada da atualização de serviço mensal. Se não desejar que o ambiente de produção programado seja atualizado para a versão de atualização de serviço, você poderá pausar a atualização de serviço no LCS. 
- Recomendamos que você use a versão mais recente da atualização de qualidade para testar suas alterações para uma atualização de serviço futura para obter melhor estabilidade e resultados.

## <a name="can-an-environment-be-brought-back-to-its-previous-state-if-there-are-issues-after-a-quality-update-is-applied"></a>Um ambiente pode retornar ao estado anterior se houver problemas após a aplicação de uma atualização de qualidade?
Depois que uma atualização de qualidade for aplicada, não haverá reversão em nenhuma circunstância. Há apenas opções de encaminhamento de patch disponíveis para atenuar os problemas.

## <a name="what-about-fda-regulation-and-gpx"></a>E a regulamentação da FDA e a GPX?
O plano para clientes sujeitos a validação e regulamentação da FDA ainda está em evolução. Espere mais atualizações neste espaço em breve. Por enquanto, todos esses clientes estão isentos das atualizações de qualidade.

## <a name="what-versions-of-service-updates-are-supported-for-these-quality-updates"></a>Que versões das atualizações de serviço são compatíveis com essas atualizações de qualidade?
Os clientes em versões inferiores a N-2 não receberão atualizações de qualidade. 

## <a name="finance-and-operations-apps-deployments-with-retail-components-typically-require-additional-work-in-addition-to-having-to-redeploy-mpos-how-will-these-quality-updates-impact-the-retailsdk"></a>As implantações de aplicativos de finanças e operações com componentes de varejo geralmente exigem trabalho adicional, além da necessidade de reimplantar MPOS. Como essas atualizações de qualidade afetarão o RetailSDK? 
Como a natureza dos hotfixes em si não é alterada na carga de atualizações de qualidade, não antecipamos nenhum impacto adicional no momento relacionado aos componentes de varejo.

## <a name="is-there-any-impact-to-cloud-hosted-environments-che-"></a>Existe algum impacto nos ambientes hospedados na nuvem (CHE)? ? 
Não.

## <a name="are-there-any-integration-issues-with-microsoft-dataverse"></a>Há problemas de integração com o Microsoft Dataverse? 
Não.

