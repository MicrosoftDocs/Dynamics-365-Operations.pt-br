---
title: Atualizações de qualidade proativas
description: Este artigo fornece informações sobre a entrega proativa de atualizações de qualidade.
author: rashmansur
ms.date: 11/07/2022
ms.topic: article
audience: Application User, Developer, IT Pro
ms.reviewer: sericks
ms.search.region: Global
ms.author: rashmim
ms.search.validFrom: 2022-08-19
ms.search.form: ''
ms.dyn365.ops.version: 10.0.29
ms.openlocfilehash: ff2232c9e1010ad1e2524df0c7ed4d771b489ed1
ms.sourcegitcommit: 05069f7e5eb7a9335c0a62031d7663f88e4821df
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/09/2022
ms.locfileid: "9752289"
---
# <a name="proactive-quality-updates"></a>Atualizações de qualidade proativas

[!include[banner](../includes/banner.md)]

Nos últimos anos, a Microsoft fez um progresso contínuo no que denominamos [One Version](../../dev-itpro/lifecycle-services/oneversion-overview.md). A premissa de One Version é simples: quanto mais clientes usarem a mesma versão do software, maior será a qualidade oferecida. Encontramos e corrigimos os problemas uma vez, e mais clientes tiveram acesso a essas soluções com mais rapidez.

Essa premissa é confirmada pelos resultados: menos incidentes em nossos produtos. Quando os clientes não estão na mesma versão, é comum serem afetados por problemas para os quais já existe uma solução disponível. Fizemos grandes progressos com o Dynamics 365 Finance, o Dynamics 365 Supply Chain, o Dynamics 365 Project Operations e o Dynamics 365 Commerce. Graças a avanços técnicos recentes, agora é possível dar o próximo passo. As informações a seguir traçam um panorama do que faremos, do que já fizemos, além de como e quando apresentaremos os novos recursos sem interrupção.

## <a name="what-you-need-to-know"></a>O que você precisa saber

- Atualizações de qualidade proativas são aplicadas mensalmente.
- A Microsoft aplicará atualizações de qualidade proativas a qualquer ambiente de área restrita que esteja executando uma atualização de serviço que estava [em serviço](./public-preview-releases.md#targeted-release-schedule-dates-subject-to-change) quando as atualizações de qualidade proativas foram criadas.
- Exceções para atualizações de qualidade proativas serão permitidas para clientes regulamentados pela Food and Drug Administration (FDA) dos EUA.
- A Microsoft está determinando como as atualizações de qualidade proativas serão gerenciadas para ambientes regulamentados e para clientes de nuvem soberana e governamentais.
- As notificações relacionadas a atualizações de qualidade proativas são lançadas no [Centro de Mensagens do Microsoft 365](https://admin.microsoft.com/AdminPortal/) e em um banner no projeto do Microsoft Dynamics Lifecycle Services do cliente.
- Cinco dias antes de uma atualização de qualidade proativa ser aplicada a um ambiente, os clientes são notificados de que a atualização ocorrerá.
- Os clientes não podem cancelar ou adiar atualizações de qualidade proativas.
- As atualizações de qualidade proativas são instaladas durante a [janela de manutenção planejada](../../dev-itpro/deployment/plannedmaintenance-selfservice.md#windows) específica da região.
- As atualizações de qualidade são projetadas para ter um baixo risco de problemas ou regressões, o que é compatível com os dados da Microsoft.
- A Microsoft recomenda testes direcionados para problemas específicos ou hotfixes específicos relacionados a uma atualização de qualidade proativa.

## <a name="focus-on-quality-updates"></a>Foco em atualizações de qualidade

No momento, oferecemos sete [atualizações de serviço](public-preview-releases.md) por ano. Por exemplo, a versão 10.0.29 é uma atualização de serviço. Até recentemente, foram feitas oito atualizações por ano. No entanto, eliminamos uma atualização em resposta a comentários de clientes que revelou um desejo de evitar alterações próximo ao final do ano civil.

Não estamos alterando a cadência das atualizações de serviço. O próximo passo da jornada One Version é voltado para *atualizações de qualidade*. As atualizações de qualidade são compilações cumulativas de hotfixes. Elas não incluem novos recursos. A qualquer momento, a comunidade inteira de clientes é distribuída entre as três ou quatro atualizações de serviço mais recentes. No entanto, para qualquer atualização de serviço específica, dezenas de versões de atualização de qualidade distintas podem ser usadas no grupo, dependendo das datas de implantação por pessoas. Na próxima etapa, transmitiremos proativamente atualizações de qualidade. Já usamos esse modelo em nossos aplicativos baseados no Dataverse e vimos os resultados esperados da qualidade aprimorada e menos incidentes de suporte.

É claro que uma redução nos defeitos pode reduzir ou eliminar totalmente a necessidade de atualizações de qualidade. Temos várias iniciativas em curso para reduzir os defeitos que exigem atualizações de qualidade. Mesmo quando os conteúdos forem reduzidos na atualização de qualidade, a consistência na base de clientes melhorará a capacidade de suporte, obterá melhorias para os clientes mais rapidamente e reduzirá a frequência de clientes com problemas para os quais já existem soluções.

## <a name="making-proactive-distribution-possible"></a>Tornar possível a distribuição proativa

Vários avanços já foram implantados para permitir a entrega proativa de atualizações de qualidade:

- **Atualização do tempo de inatividade quase zero**: para enviar ambientes mais frequentes, é essencial que o impacto na disponibilidade do ambiente seja reduzido para preservar os contratos de nível de serviço (SLAs) do Dynamics 365. A atualização do tempo de inatividade quase zero foi originalmente apresentada para ajudar a melhorar a aplicação de patch do sistema operacional mensal usando um failover de cluster para ativar a imagem atualizada com interrupção mínima. O mecanismo para aplicar atualizações está sendo aprimorado para que seja ainda menos prejudicial, e abrangerá a aplicação de patch do sistema operacional e a implantação da atualização de qualidade.

    Para usuários interativos, uma sessão ativa pode ser interrompida e a repetição irá para o ambiente atualizado agora. Com a introdução do [agendamento de lotes com base na prioridade](../../dev-itpro/sysadmin/priority-based-batch-scheduling.md) o agendamento e o processamento em lotes são recuperados e retomados imediatamente após a atualização. O agendamento de lotes com base na prioridade será feito para os clientes antes que comecem a participar da distribuição proativa de atualizações de qualidade para ambientes de produção.

- **Horas escuras**: as horas escuras são definidas para cada região do Azure e as atualizações de tempo de inatividade quase zero ocorrerão no período de hora escura.

## <a name="the-proactive-update-process"></a>O processo de atualização proativo

A implantação de atualizações de qualidade proativas seguirá um processo de implantação seguro (SDP). As especificações do SDP evoluirão, mas as atualizações de qualidade serão inicialmente implantadas em ambientes de área restrita. Como a porcentagem de áreas restritas implantadas com êxito aumenta, a implantação em ambientes de produção será iniciada. Os sistemas de escuta monitorarão a telemetria do sistema e incidentes de Livesite, e interromperão a distribuição de uma versão específica se qualquer regressão for detectada. Caso desejem, os clientes ainda poderão extrair as atualizações de qualidade antes da implantação proativa.

Os dados atuais de gerenciamento de versões mostram que menos de 3% das regressões são introduzidas em atualizações de qualidade. Com o aumento do foco na eliminação da regressão e de um SDP aprimorado, o impacto potencial das regressões será bem menor do que os ganhos de qualidade obtidos por meio da agilidade na implantação de correções implantadas para clientes.

## <a name="process-changes"></a>Processar alterações

Um conjunto de alterações de processo está sendo implementado antes da ativação da implantação de atualização de qualidade proativa:

- **Esquema**: a ferramenta garante que as compilações de atualização de qualidade incluam somente alterações de esquema que possam ser aplicadas enquanto o serviço está online. Essa abordagem ajudará a manter a capacidade de aplicar a atualização com tempo de inatividade quase zero.
- **Maior investigação de alterações**: no momento, já existe uma etapa de processo extra para aprovar alterações para inclusão em uma atualização de qualidade. A investigação na etapa extra será maior para ajudar a reduzir o potencial de regressões. Alterações interruptivas não são permitidas em atualizações de qualidade e a maior investigação de alterações ajudará a garantir a atingir esse objetivo.
- **Visibilidade** – As notificações são enviadas pelo centro de administração, Lifecycle Services e outros canais disponíveis para futuras atualizações de qualidade proativas. Além disso, as equipes de suporte e os clientes potenciais de incidentes terão visibilidade sobre onde as atualizações de qualidade foram implantadas de forma proativa.

    > [!NOTE]
    > A equipe de Comunicações da Microsoft está investigando uma degradação contínua da ferramenta de email que está impedindo a entrega de notificações por email. Continue a monitorar o Centro de Mensagens do Microsoft 365 para integração e mensagens relacionadas à notificação.

- **Segurança contra falhas por versão de pré-lançamento** – A versão de pré-lançamento será usada para proteger as alterações de código sempre que aplicável em uma correção de bug de atualização de qualidade ou usar a versão de pré-lançamento de recurso existente relevante para a correção. Se for necessário um fallback ou desativar uma alteração após uma implantação proativa, isso poderá ser feito por meio do sistema de versão de pré-lançamento para evitar mais falhas.
- **Designação de sincronização da área restrita**: menos de 20% dos clientes têm várias áreas restritas e mantêm uma área restrita implantada onde a versão corresponde à produção, para ajudar na solução de problemas. Se um cliente estiver usando uma área restrita para testar uma versão mais recente do que a produção dele, essa área restrita receberá atualizações de qualidade para a versão mais recente.

## <a name="what-is-the-rollout-roadmap-for-quality-updates"></a>Qual é o mapa de distribuição para atualizações de qualidade?

Espera-se que a distribuição de atualizações de qualidade proativa para ambientes de área restrita comece no final de setembro ou outubro de 2022 para clientes da nuvem pública do Azure. Os ambientes de avaliação também começarão a receber a implantação de atualizações proativas nesse momento. Em setembro, uma notificação será enviada a cada cliente para informá-lo sobre o plano esperado para seus ambientes. As exceções para o processo de distribuição de atualizações proativas serão permitidas somente para clientes regulamentados pelo FDA. Ainda estamos pensando como ambientes regulamentados e clientes de nuvem soberana e governamentais serão gerenciados.

Nos próximos seis meses, aumentaremos gradualmente a porcentagem de ambientes de área restrita que recebem atualizações proativas, até que todos os ambientes designados sejam incluídos e cheguem à atualização dos ambientes de produção. Durante todo o período, monitoraremos para garantir que o processo de implantação seja perfeito e que atinjamos nossa meta de payloads sem interrupção.

Como os clientes receberão, normalmente, payloads menores, esperamos que o processo de atualização seja simplificado. Ajustaremos a frequência da implantação de atualizações quando demonstrarmos a capacidade de executar o processo sem interrupção. Esse processo já opera de forma efetiva para a plataforma e os aplicativos do Dataverse, e oferece os aperfeiçoamentos previstos na qualidade do serviço. Estamos ansiosos para avançar da mesma forma com aplicativos de finanças e operações.

## <a name="when-will-quality-updates-start-for-production-environments"></a>Quando as atualizações de qualidade serão iniciadas para ambientes de produção?
Neste momento, as atualizações de qualidade estão direcionando apenas áreas restritas. Atualizaremos este espaço com uma data de início para ambientes de produção quando tivermos dados e métricas mais concretos de atualizações proativas para áreas restritas para avaliar a prontidão para produção.

## <a name="what-is-the-schedule-for-sandbox-proactive-quality-updates"></a>Qual é a programação para atualizações de qualidade proativas?
Para obter informações sobre o período noturno de cada região, consulte [Quais são as janelas de manutenção planejadas por região?](../../dev-itpro/deployment/plannedmaintenance-selfservice.md#windows).

### <a name="proactive-quality-update-release-10028"></a>Versão de atualização de qualidade proativa: 10.0.28
**Versão do aplicativo: 10.0.1265.89**  
**Artigo da base de conhecimento mais recente correspondente: 745340**

| Estação | Regiões | Agenda concluída| Programação da área restrita
|---|---|---|---|
| Estação 1 | Canadá Central, Leste do Canadá, França Central, Índia central, Leste da Noruega, Oeste da Suíça | 15 a 18 de setembro de 2022, 19 a 22 de setembro de 2022 e 7 a 10 de outubro de 2022 | 25 a 28 de outubro de 2022 |
| Estação 2 | Sul da França, Sul da Índia, Oeste da Noruega, Norte da Suíça, Norte da África do Sul, Leste da Austrália, Sul do Reino Unido, Norte dos EAU, Leste do Japão, Sudeste da Austrália, Sudeste da Ásia | 25 a 28 de setembro de 2022 e 7 a 10 de outubro de 2022 | 25 a 28 de outubro de 2022 |
| Estação 3 | Leste da Ásia, Oeste do Reino Unido, Oeste do Japão, Sul do Brasil, Oeste da Europa, Leste dos EUA, EAU Central | 26 a 29 de setembro de 2022 e 7 a 10 de outubro de 2022 | 25 a 28 de outubro de 2022 |
| Estação 4 | Norte da Europa, EUA Central, Oeste dos EUA | 28 de setembro a 1 de outubro de 2022 e 7 a 10 de outubro de 2022 | 25 a 28 de outubro de 2022 |
| Estação 5 | DoD (Nuvem da comunidade governamental, China) | Não programado | Não programado |

### <a name="proactive-quality-update-release-10029"></a><a name="schedule"></a> Versão de atualização de qualidade proativa: 10.0.29
**Versão do aplicativo: 10.0.1326.70**  
**Artigo da base de conhecimento mais recente correspondente: 748926**

| Estação | Regiões | Agenda concluída | Programação da área restrita|
|---|---|---|---|
| Estação 1 | Canadá Central, Leste do Canadá, França Central, Índia central, Leste da Noruega, Oeste da Suíça | 14 de outubro a 17 de outubro de 2022, 2 de novembro a 5 de novembro de 2022 | 13 de novembro a 16 de novembro de 2022 |
| Estação 2 | Sul da França, Sul da Índia, Oeste da Noruega, Norte da Suíça, Norte da África do Sul, Leste da Austrália, Sul do Reino Unido, Norte dos EAU, Leste do Japão, Sudeste da Austrália, Sudeste da Ásia | 15 de outubro a 18 de outubro de 2022, 2 de novembro a 5 de novembro de 2022 | 13 de novembro a 16 de novembro de 2022 |
| Estação 3 | Leste da Ásia, Oeste do Reino Unido, Oeste do Japão, Sul do Brasil, Oeste da Europa, Leste dos EUA, EAU Central | 16 de outubro a 19 de outubro de 2022, 2 de novembro a 5 de novembro de 2022 | 13 de novembro a 16 de novembro de 2022 |
| Estação 4 | Norte da Europa, EUA Central, Oeste dos EUA | 17 de outubro a 20 de outubro de 2022, 2 de novembro a 5 de novembro de 2022 | 13 de novembro a 16 de novembro de 2022 |
| Estação 5 | DoD (Nuvem da comunidade governamental, China) | Não programado | Não programado |

### <a name="proactive-quality-update-release-10030"></a><a name="schedule"></a> Versão de atualização de qualidade proativa: 10.0.30
**Versão do aplicativo: a ser definida**
**Artigo da base de conhecimento mais recente correspondente: a ser definido**

| Estação | Regiões | Programação da área restrita |
|---|---|---|
| Estação 1 | Canadá Central, Leste do Canadá, França Central, Índia central, Leste da Noruega, Oeste da Suíça | 1 a 4 de dezembro de 2022 |
| Estação 2 | Sul da França, Sul da Índia, Oeste da Noruega, Norte da Suíça, Norte da África do Sul, Leste da Austrália, Sul do Reino Unido, Norte dos EAU, Leste do Japão, Sudeste da Austrália, Sudeste da Ásia | 2 a 5 de dezembro de 2022 |
| Estação 3 | Leste da Ásia, Oeste do Reino Unido, Oeste do Japão, Sul do Brasil, Norte da Europa, Leste dos EUA, EAU Central | 3 a 6 de dezembro de 2022 |
| Estação 4 | Oeste da Europa, EUA Central, Oeste dos EUA | 4 a 7 de dezembro de 2022 |
| Estação 5 | DoD (Nuvem da comunidade governamental, China) | Não programado |

> [!IMPORTANT] 
> Com cinco dias de antecedência, a Microsoft atualizará o agendamento anterior e enviará uma notificação para o conjunto de ambientes agendados para receber essas atualizações de qualidade. A agenda anterior é aplicável apenas a ambientes que receberam notificação sobre uma futura atualização. Para obter informações sobre o período noturno de cada região, consulte [Quais são as janelas de manutenção planejadas por região?](../../dev-itpro/deployment/plannedmaintenance-selfservice.md#windows).
>
> Para cada grupo de regiões, ou *estação*, onde uma atualização de qualidade está programada para ser implementada, a agenda mostra um intervalo de quatro dias. As atualizações de qualidade começarão apenas com ambientes de área restrita. Dessa forma, à medida que a porcentagem de áreas restritas implantadas com sucesso aumenta, a implantação em ambientes de produção começará com notificações prévias aos clientes.
> 
> As atualizações de qualidade sempre ocorrerão de forma contínua, o que nos permite segmentar um conjunto de ambientes por agendamento e concluir todos os conjuntos até o final do quarto dia em uma estação. Porém, isso não significa que uma atualização de ambiente durará quatro dias. Significa apenas que não podemos predeterminar qual conjunto de ambientes será atualizado em um dia específico nesse intervalo de quatro dias. Todas as atualizações serão realizadas durante a madrugada, com tempo de inatividade quase zero. As atualizações serão encerradas de forma definitiva durante a madrugada de uma região específica.

## <a name="how-are-the-dark-hours-handled-for-customers-that-have-one-finance-and-operations-apps-instance-but-are-active-in-multiple-time-zones"></a>Como as horas escuras são tratadas para clientes que têm uma instância de aplicativos de finanças e operações, mas estão ativas em vários fusos horários? 
Não há programações especiais fora das horas escuras nas quais existe uma instância de aplicativos de finanças e operações, pois pretendemos lançar atualizações de qualidade de maneira minimamente prejudicial com o [nZDT](../../dev-itpro/deployment/plannedmaintenance-selfservice.md#what-does-near-zero-downtime-maintenance-mean).

## <a name="what-is-the-current-rollout-cadence-for-proactive-quality-updates"></a>Qual é o mapa de distribuição atual para atualizações de qualidade proativas?
Atualmente, as atualizações de qualidade proativas (PQUs) são enviadas uma vez por mês para cada versão com suporte de uma Atualização de Serviço. Somente uma atualização por mês será enviada para ambientes de área restrita selecionados, a menos que os clientes se movam para uma nova versão de atualização de serviço. Nesse caso, é possível obter um PQU pré-agendado como parte de um trem existente para a atualização de serviço. Após a conclusão da distribuição mundial em 2023, a frequência dessas atualizações aumentará. Você sempre receberá um aviso prévio de pelo menos um mês sempre que houver uma alteração na frequência de envio.

## <a name="how-will-microsoft-ensure-the-quality-of-these-updates"></a>Como a Microsoft garantirá a qualidade dessas atualizações?
A Microsoft se esforça para manter o pipeline de lançamento suficientemente eficiente para fornecer cargas pequenas para manter o custo de validação baixo. Cada correção em uma atualização de qualidade passa por um processo de implantação rigoroso e seguro que ajuda a melhorar a qualidade e a confiabilidade, reduzindo o impacto do cliente. A implantação ocorrerá em estágios em ambientes de área restrita primeiro, seguidos por produção. As implantações em etapas permitem o monitoramento adequado para determinar se a implantação será segura. A distribuição será interrompida se forem detectados problemas com cada grupo de clientes implantados e nós garantiremos que cada etapa da distribuição tenha tempo suficiente para gerar problemas. Para cada atualização de qualidade futura, forneceremos visibilidade da programação por meio de atualizações na documentação e em emails públicos, para que os clientes possam se planejar com antecedência.

## <a name="can-customers-delay-reschedule-or-pause-a-quality-update"></a>Os clientes podem atrasar, reprogramar ou pausar uma atualização de qualidade?
Não. O principal objetivo das atualizações de qualidade é garantir que os conceitos básicos como segurança, privacidade, confiabilidade, disponibilidade e desempenho sejam continuamente aperfeiçoados para nossos clientes. Ao atrasar ou pausar uma atualização, a segurança, a disponibilidade e a confiabilidade estarão em risco.

## <a name="how-do-i-know-what-set-of-changes-went-into-a-quality-update-payload"></a>Como é possível saber qual conjunto de alterações foram feitas em uma carga de atualização de qualidade?
As etapas a seguir são uma solução temporária, pois continuamos trabalhando para fornecer uma solução ainda melhor para identificar a lista de alterações realizadas em uma carga de atualização de qualidade. 

Use o KB# 745340 para o trem de atualização de qualidade 10.0.28 e versão de aplicativo relacionada 10.0.1265.89.

1. No Lifecycle Services, abra a página **Detalhes do ambiente** da área restrita. 
2. Na seção **Atualizações disponíveis**, selecione **Visualizar atualização** para obter a versão mais recente da Atualização de Qualidade. 
3. Exporte o build para um arquivo CSV ou Microsoft Excel.
4. No arquivo exportado, classifique as informações com base no tempo (o mais antigo primeiro) e procure o número do KB 745340 na coluna **ID da atualização**. Agora deve ser possível ver a lista delta de KBs.
 
> [!NOTE]
> A exportação para um arquivo CSV ou Excel deve ocorrer antes da atualização do ambiente. Caso contrário, é possível usar um ambiente com configuração semelhante que não tenha a atualização instalada e seguir as etapas acima.

[![Exemplo de ambiente com atualização de qualidade.](./media/how-to-get-kb-list-pqu.png)](./media/how-to-get-kb-list-pqu.png)

## <a name="what-is-the-process-if-a-critical-issue-is-found-after-a-quality-update"></a>Qual será o processo se um problema crítico for encontrado após uma atualização de qualidade?
Um problema crítico ou regressão é um ou mais eventos que geralmente fazem com que vários clientes tenham uma experiência degradada com um ou mais dos nossos serviços. Esses problemas podem causar um tempo de inatividade não planejado, incluindo indisponibilidade, degradação do desempenho e interferência com o gerenciamento de serviços. Se houver um impacto amplo no cliente devido a essas regressões, a implantação de uma atualização de qualidade será interrompida até que possamos comunicar e corrigir o problema. Normalmente, a próxima atualização de qualidade terá a correção necessária para retomar a distribuição.

Se um ambiente de cliente único for afetado, entre em contato o suporte da Microsoft para abrir um tíquete. Com base na justificativa, a implantação da atualização de qualidade será interrompida em todos os outros ambientes do projeto até que o problema seja reduzido.

## <a name="can-customers-still-manually-apply-hotfix-updates-from-lifecycle-services"></a>Os clientes ainda podem aplicar atualizações de hotfix manualmente no Lifecycle Services?
Sim. Para garantir a paridade contínua com a forma como os hotfixes funcionam, as atualizações de hotfix ainda podem ser aplicadas a ambientes de cliente no Lifecycle Services. No entanto, é importante observar que os hotfixes implantados como parte de uma atualização de qualidade passam pelo SDP padrão antes da atualização ser implantada. Isso reduz o risco de regressões devido a uma qualidade superior. Recomendamos que você escolha uma atualização de qualidade em vez da aplicação manual de hotfixes para maior confiabilidade.

## <a name="can-customers-proactively-install-a-quality-update-build-ahead-of-the-schedule"></a>Os clientes podem instalar proativamente uma atualização de qualidade antes do previsto?
Sim. Você pode instalar uma atualização de qualidade proativamente. A Microsoft ignorará a atualização se a versão de compilação atual do ambiente for igual ou maior do que a atualização de qualidade em questão.

## <a name="if-an-environment-has-an-upcoming-scheduled-monthly-service-update-within-a-week-will-it-still-receive-quality-updates"></a>Se um ambiente tiver uma atualização de serviço mensal programada dentro de uma semana, ele ainda receberá atualizações de qualidade?
- As atualizações de qualidade não serão aplicadas a ambientes de produção se houver uma atualização de serviço iminente agendada dentro de uma semana a partir da data em que a atualização de qualidade está programada.
- Se um ambiente de área restrita tiver uma versão de compilação igual ou superior à da atualização de qualidade iminente, ele será ignorado.
- Se um ambiente de produção tiver uma versão de compilação igual ou superior à da atualização de qualidade iminente, ele será ignorado.
- Se uma área restrita tiver a mesma versão de compilação ou superior devido a uma atualização de qualidade ou uma atualização manual da produção, a produção ainda receberá a versão programada da atualização de serviço mensal. Se não desejar que o ambiente de produção programado seja atualizado para a versão de atualização de serviço, você poderá pausar a atualização de serviço no Lifecycle Services. 
- Recomendamos que você use a versão mais recente da atualização de qualidade para testar suas alterações para uma atualização de serviço futura para obter melhor estabilidade e resultados.

## <a name="if-an-environment-has-an-upcoming-scheduled-action-and-a-scheduled-quality-update-in-the-same-maintenance-window-will-it-still-receive-the-quality-update"></a>Se um ambiente tiver uma ação agendada futura e uma atualização de qualidade agendada na mesma janela de manutenção, ele ainda receberá a atualização de qualidade?
Se houver alguma contenção com uma ação pré-agendada, por exemplo, uma restauração pontual (PITR), a atualização de qualidade será reprogramada para a próxima janela de manutenção disponível dentro do intervalo de quatro dias. Para obter mais detalhes sobre a programação, consulte [Qual é a programação das atualizações de qualidade proativas?](#schedule). 

## <a name="can-an-environment-be-brought-back-to-its-previous-state-if-there-are-issues-after-a-quality-update-is-applied"></a>Um ambiente pode retornar ao estado anterior se houver problemas após a aplicação de uma atualização de qualidade?
Depois que uma atualização de qualidade for aplicada, não haverá reversão em nenhuma circunstância. Há apenas opções de encaminhamento de patch disponíveis para atenuar os problemas.

## <a name="what-about-fda-regulation-and-gpx"></a>E a regulamentação da FDA e a GPX?
O plano para clientes sujeitos a validação e regulamentação da FDA ainda está em evolução. Espere mais atualizações neste espaço em breve. Por enquanto, todos esses clientes estão isentos das atualizações de qualidade. Para garantir que um cliente esteja de acordo com os regulamentos da FDA, consulte [Oferta do Microsoft Azure GPX](/azure/compliance/offerings/offering-gxp).

## <a name="what-versions-of-service-updates-are-supported-for-these-quality-updates"></a>Que versões das atualizações de serviço são compatíveis com essas atualizações de qualidade?
Os clientes em todas as versões compatíveis de atualizações de serviço se qualificam para atualizações de qualidade. 

## <a name="finance-and-operations-apps-deployments-with-retail-components-typically-require-additional-work-in-addition-to-having-to-redeploy-mpos-how-will-these-quality-updates-impact-the-retail-sdk"></a>As implantações de aplicativos de finanças e operações com componentes de varejo geralmente exigem trabalho adicional, além da necessidade de reimplantar o MPOS. Como essas atualizações de qualidade afetarão o SDK do Retail? 
Como a natureza do hotfix em si não é alterada na carga de atualizações de qualidade, não antecipamos impactos adicionais relacionados aos componentes de varejo no momento.

## <a name="is-there-any-impact-to-cloud-hosted-environments-che"></a>Existe algum impacto nos ambientes hospedados na nuvem (CHE)? 
Os ambientes CHE estão fora do escopo de atualizações de qualidade porque estão fora do âmbito da Microsoft.

## <a name="are-there-any-integration-issues-with-microsoft-dataverse"></a>Há problemas de integração com o Microsoft Dataverse? 
Não há problemas de integração conhecidos para atualizações de qualidade com o Dataverse.

