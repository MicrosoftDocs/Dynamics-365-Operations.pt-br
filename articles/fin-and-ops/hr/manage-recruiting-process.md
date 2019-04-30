---
title: Gerenciar processos de recrutamento
description: Este artigo descreve um conceito que os recrutadores podem usar para controlar as etapas do processo de recrutamento, incluindo os esforços para anunciar posições em aberto e para recrutar candidatos, rastrear informações sobre o candidato e sobre a solicitação de emprego, entrevistar candidatos e selecionar um ou mais candidatos para preencher as vagas em sua organização.
author: andreabichsel
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: HRMApplication, HRMRecruitingTable
audience: Application User
ms.reviewer: anbichse
ms.search.scope: Core, Operations
ms.custom: 7501
ms.assetid: 1ad725bf-20e2-42a1-8068-111f7ddddad9
ms.search.region: Global
ms.author: anbichse
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: dfdc1295e0b82672576acdf8e2756dbb36612f8b
ms.sourcegitcommit: 608e68b603afef9eb98d8fb25e90109c2473ef87
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/19/2019
ms.locfileid: "858804"
---
# <a name="manage-recruiting-processes"></a>Gerenciar processos de recrutamento

[!include [banner](../includes/banner.md)]

Este tópico descreve um conceito que os recrutadores podem usar para controlar as etapas em um processo de recrutamento, incluindo os esforços para anunciar posições em aberto e para recrutar candidatos, rastrear informações sobre o candidato e sobre a solicitação de emprego, entrevistar candidatos e selecionar um ou mais candidatos para preencher as vagas em sua organização.

## <a name="overview"></a>Visão Geral

Os projetos de recrutamento podem ajudar você a organizar as etapas que concluirá ao preencher posições em aberto em uma entidade legal. Um candidato é a pessoa que se candidata a um emprego em sua empresa. Uma solicitação de emprego é uma expressão de interesse do candidato que está sendo empregado por uma empresa e pode ser vinculado a um projeto de recrutamento para expressar interesse em uma determinada vaga. Um único candidato pode ter várias solicitações de emprego na mesma entidade legal ou entre várias empresas na organização.

## <a name="recruitment-projects"></a>Projetos de recrutamento

Os projetos de recrutamento permitem que os recrutadores acompanhem o progresso de preenchimento de uma ou mais posições abertas. O projeto de recrutamento identifica o departamento e o cargo para o qual estão abertas uma ou mais posições. Os projetos de recrutamento também acompanham as seguintes informações para posições em aberto:

- O número específico de posições em aberto
- O gerente de contratação e um contato alternativo para a posição.
- A data em que a requisição foi aprovada
- O prazo final da solicitação de emprego
- A data inicial estimada

O projeto de recrutamento contém o **Anúncio** usado no **Autoatendimento para funcionários** para anunciar a vaga. Para exibir a vaga para funcionários, o projeto de recrutamento deverá ter um **Anúncio de emprego**, o campo **Exibir no autoatendimento para funcionários** deve ser definido como Sim, **Prazo final para solicitação de emprego** deve ser definido como uma data futura e o projeto de recrutamento deve ter um **Status do projeto** Iniciado. A tabela a seguir lista os status de possíveis projetos de recrutamento e sua descrição.

| Status    | Indica que...                                                                         |
|-----------|-----------------------------------------------------------------------------------------|
| Agendado | Os esforços de recrutamento estão sendo preparados. O recrutamento ainda não foi iniciado para este projeto. |
| Iniciado   | As solicitações de emprego estão sendo aceitas para as vagas neste projeto.                   |
| Concluído  | Todas as vagas para este projeto foram preenchidas.                                         |
| Cancelada  | O recrutamento foi cancelado para este projeto.                                          |

Os recrutadores também podem registrar a **Mídia** usada para anunciar a vaga por meio de lojas externas, bem como acompanhar os **Desenvolvimentos** em relação ao projeto ou às solicitações de emprego.

## <a name="applicants"></a>Candidatos

Um candidato é a pessoa que se candidata a um cargo em sua empresa. Os candidatos são compartilhados entre todas as entidades legais em sua organização, oferecendo a você a oportunidade de pesquisar em um grande grupo de talentos. Você pode manter as competências, as referências, as solicitações de acomodação e as informações pessoais dos candidatos. Quando você criar um registro do candidato, um registro para o candidato é criado no catálogo de endereços global. Você pode usar a página **Candidato** para atualizar as seguintes informações do catálogo de endereços global para os candidatos:

- Informações de endereço
- Informações de contato
- Informações de identificação
- Detalhes do nome
- Informações pessoais

## <a name="applications"></a>Solicitações de emprego

Você pode registrar informações das solicitações de emprego recebidas na página **Candidato**. A solicitação de emprego é uma expressão do candidato de interesse em uma vaga de trabalho em sua organização. Para criar uma solicitação de emprego, o candidato já deve existir como um candidato ou como uma pessoa no sistema.

As solicitações de emprego enviadas por candidatos na rede foram enviadas em resposta a um anúncio de um cargo ou são solicitações não requeridas. Solicitações requeridas são associadas automaticamente ao projeto de recrutamento para o qual o anúncio de emprego foi criado. Solicitações de emprego não requeridas são associadas ao projeto de recrutamento especificado na área **Recrutamento** da página **Parâmetros de recursos humanos**.

### <a name="application-status"></a>Status da solicitação de emprego

O status da solicitação de emprego indica quando uma solicitação está em processo de recrutamento. A tabela a seguir lista os status de solicitações de emprego possíveis e sua descrição.

| Status    | Indica que...                                                                           |
|-----------|-------------------------------------------------------------------------------------------|
| Recebido  | A solicitação foi recebida.                                                             |
| Confirmada | Uma notificação pode ser enviada para o candidato para confirmar o recebimento da solicitação.            |
| Entrevista | Um convite para uma entrevista pode ser enviado para o candidato.                                     |
| Rejeição | Uma carta de rejeição pode ser enviada para o candidato.                                          |
| Cancelada  | Uma confirmação de retirada pode ser enviada para o candidato. Esse status é atribuído manualmente. |
| Empregado  | Uma oferta de emprego pode ser enviada para o candidato.                                         |

### <a name="correspondence-actions"></a>Ações de correspondência

Uma ação de correspondência da **Solicitação de emprego** determina o modelo de documento ou de e-mail que você usa para comunicar-se com o candidato que enviou a solicitação. Você pode associar **Indicadores de solicitação de emprego** a ações de correspondência para permitir que você use os valores das páginas Solicitação de emprego, Candidato, Entrevista e Projeto de recrutamento em suas comunicações com os candidatos. **Modelos de email de solicitação de emprego** podem ser criados para as ações de correspondência para enviar emails rapidamente para os candidatos de uma solicitação de emprego com uma determinada combinação de status e de ação de correspondência. Por exemplo, você pode enviar um email de confirmação a todas as solicitações de emprego com **Status** de Recebido e a **Ação de correspondência** de Recebido. Após enviar o email, você tem a opção de atualizar automaticamente o status das solicitações de emprego.

## <a name="application-routing"></a>Roteamento da solicitação de emprego

Se uma solicitação de emprego deve ser revisada por vários trabalhadores, você pode usar a página **Roteamento da solicitação de emprego** para criar uma lista de circulação do trabalhador para gerenciar o processo.

## <a name="interviews"></a>Entrevistas

As **Entrevistas de candidatos** podem ser agendadas na página **Solicitações de emprego**. Use o botão **Enviar informações de reunião** para enviar um arquivo do calendário com informações da agenda da entrevista para o candidato e o entrevistador.

## <a name="skill-mapping"></a>Mapeamento de habilidades

**Mapeamento de habilidades** e **Perfis de mapeamento de habilidades** podem ser usados para identificar candidatos que possam ser uma boa opção para uma vaga.

## <a name="hiring-applicants"></a>Candidatos de contratação

Use a página **Solicitações de emprego** para contratar um candidato. Quando você contratar um candidato, o registro de solicitação de emprego terá o status **Empregado** e o registro pessoal no catálogo de endereços global do candidato será associado ao registro do novo trabalhador. As alterações nas informações do catálogo de endereços global para o registro de novos funcionários também são exibidos no registro do candidato. Isso pode ajudar a reduzir a entrada de dados se o novo trabalhador se candidatar a um trabalho diferente dentro de sua empresa. Para contratar um trabalhador existente em uma nova posição, clique em **Alterar posição** na lista suspensa **Status da solicitação de emprego** para iniciar o processo de transferência.
