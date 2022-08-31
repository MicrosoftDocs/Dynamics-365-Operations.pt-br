---
title: Atualizações de qualidade proativas
description: Este artigo fornece informações sobre a entrega proativa de atualizações de qualidade.
author: rashmansur
ms.date: 08/23/2022
ms.topic: article
audience: Application User, Developer, IT Pro
ms.reviewer: sericks
ms.search.region: Global
ms.author: rashmim
ms.search.validFrom: 2022-08-19
ms.search.form: ''
ms.dyn365.ops.version: 10.0.29
ms.openlocfilehash: 9d81cb15e9a127e7bea7ad9b5e0f50a1ee543f71
ms.sourcegitcommit: 78e85ad49634cd31459fdb7325cb273352bf1501
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/23/2022
ms.locfileid: "9338126"
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
- **Fallback de versão**: a liberação de versões será usada para agrupar todas as alterações em uma atualização de qualidade proativa. Se for necessário um fallback após uma implantação proativa, ele poderá ser feito por meio do sistema de liberação de versões.
- **Designação de sincronização da área restrita**: menos de 20% dos clientes têm várias áreas restritas e mantêm uma área restrita implantada onde a versão corresponde à produção, para ajudar na solução de problemas. Em breve, apresentaremos a capacidade dos clientes de especificar um ambiente de área restrita que não deve receber a implantação de atualização de qualidade proativa junto com outras áreas restritas, mas que a receberá posteriormente, junto com o ambiente de produção. Note que, se um cliente estiver usando uma área restrita para testar uma versão mais recente do que a produção dele, essa área restrita receberá atualizações de qualidade para a versão mais recente.
- 
## <a name="when-will-proactive-quality-updates-start"></a>Quando iniciarão as atualizações de qualidade proativas?

Espera-se que a distribuição de atualizações de qualidade proativa para ambientes de área restrita comece no final de setembro ou outubro de 2022 para clientes da nuvem pública do Azure. Os ambientes de avaliação também começarão a receber a implantação de atualizações proativas nesse momento. Em setembro, uma notificação será enviada a cada cliente para informá-lo sobre o plano esperado para seus ambientes. As exceções para o processo de distribuição de atualizações proativas serão permitidas somente para clientes regulamentados pelo FDA. Ainda estamos pensando como ambientes regulamentados e clientes de nuvem soberana e governamentais serão gerenciados.

Nos próximos seis meses, aumentaremos gradualmente a porcentagem de ambientes de área restrita que recebem atualizações proativas, até que todos os ambientes designados sejam incluídos e cheguem à atualização dos ambientes de produção. Durante todo o período, monitoraremos para garantir que o processo de implantação seja perfeito e que atinjamos nossa meta de payloads sem interrupção.

Como os clientes receberão, normalmente, payloads menores, esperamos que o processo de atualização seja simplificado. Ajustaremos a frequência da implantação de atualizações quando demonstrarmos a capacidade de executar o processo sem interrupção. Esse processo já opera de forma efetiva para a plataforma e os aplicativos do Dataverse, e oferece os aperfeiçoamentos previstos na qualidade do serviço. Estamos ansiosos para avançar da mesma forma com aplicativos de finanças e operações.
