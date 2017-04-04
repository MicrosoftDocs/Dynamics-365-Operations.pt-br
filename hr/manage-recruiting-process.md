---
title: Gerenciar um processo de recrutamento
description: "Este artigo descreve um conceito que os recrutadores podem usar para controlar as etapas do processo de recrutamento, incluindo os esforços para anunciar posições em aberto e para recrutar candidatos, rastrear informações sobre o candidato e sobre a solicitação de emprego, entrevistar candidatos e selecionar um ou mais candidatos para preencher as vagas em sua organização."
author: twheeloc
manager: AnnBe
ms.date: 04/04/2017
ms.topic: article
ms.prod: 
ms.service: Dynamics365Operations
ms.technology: 
ms.search.form: HRMApplication, HRMRecruitingTable
audience: Application User
ms.reviewer: twheeloc
ms.search.scope: AX 7.0.0, Operations, Core
ms.custom: 7501
ms.assetid: 1ad725bf-20e2-42a1-8068-111f7ddddad9
ms.search.region: Global
ms.author: twheeloc
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
translationtype: Human Translation
ms.sourcegitcommit: 6f4429202efd0506378d681188035c5cc69f56a1
ms.openlocfilehash: 551e15ed31953d6e5fc99a1177c1310194ea95d0
ms.lasthandoff: 03/31/2017


---

# <a name="manage-a-recruiting-process"></a>Gerenciar um processo de recrutamento

Este tópico descreve um conceito que os recrutas podem usar para controlar as etapas de um processo de recrutamento, incluindo esforços para anunciar posições abertas e para recrutar candidatos candidatos, o rastreamento do candidato e de informações, a entrevista de aplicativos, e marque um ou mais candidatos para preencher as posições abertas na organização.

<a name="overview"></a>Visão Geral
--------

Os projetos de recrutamento podem ajudar você a organizar as etapas que concluirá ao preencher posições em aberto em uma entidade legal. Candidato é a pessoa que se aplique de emprego a sua empresa.  Um aplicativo é a expressão de um candidato de juros de emprego por uma empresa e podem ser a ela um projeto de recrutamento expressar juros sobre a abertura específica.  Um único candidato pode ter várias solicitações de emprego na mesma entidade legal ou entre várias empresas na organização.

<a name="recruitment-projects"></a>Projetos de recrutamento
--------------------

Os projetos de recrutamento permitem que os recrutas acompanha o progresso para preencher uma ou várias posições abertas.  O projeto de recrutamento ao departamento e o trabalho para o qual ou mais posições está aberto. Os projetos de recrutamento também acompanham as seguintes informações para posições em aberto:
-   O número específico de posições em aberto
-   O gerente de contratação e um contato alternativo para a posição.
-   A data em que a requisição foi aprovada
-   O prazo final da solicitação de emprego
-   A data inicial estimada

O projeto de recrutamento contém o **Anúncio** usado no **Autoatendimento para funcionários** para anunciar a vaga. Para exibir a vaga para funcionários, o projeto de recrutamento deverá ter um **Anúncio de emprego**, o campo ** Exibir no autoatendimento para funcionários** deve ser definido como Sim, **Prazo final para solicitação de emprego** deve ser definido como uma data futura e o projeto de recrutamento deve ter um **Status do projeto** Iniciado. A tabela a seguir lista o status do projeto de recrutamento possíveis e sua descrição.

| **Status**    | **Indicates that…**                                                                  |
|-----------|------------------------------------------------------------------------------------------|
| Agendado | Os esforços de recrutamento estão sendo preparados.  Recrutar não foi iniciada ainda para o projeto. |
| Iniciado   | As solicitações de emprego estão sendo aceitas para as vagas neste projeto.                    |
| Concluído  | Todas as vagas para este projeto foram preenchidas.                                          |
| Cancelada  | O recrutamento foi cancelado para este projeto.                                           |

Os recrutadores também podem registrar a **Mídia** usada para anunciar a vaga por meio de lojas externas, bem como acompanhar os **Desenvolvimentos** em relação ao projeto ou às solicitações de emprego.

<a name="applicants"></a>Candidatos
----------

Candidato é a pessoa que se aplica a um trabalho em sua empresa.  Candidatos são compartilhados entre todas as entidades legais em sua organização que fornece a você uma grande de grupo talento para pesquisar de. Você pode manter as competências, as referências, as solicitações de acomodação e as informações pessoais dos candidatos. Quando você criar um registro do candidato, um registro para o candidato é criado no catálogo de endereços global. Você pode usar a página **Candidato** para atualizar as seguintes informações do catálogo de endereços global para os candidatos:
-   Informações de endereço
-   Informações de contato
-   Informações de identificação
-   Detalhes do nome
-   Informações pessoais

## <a name="applications"></a>Aplicativos
Você pode registrar informações das solicitações de emprego recebidas na página **Candidato**. A solicitação está a expressão de juros do candidato em uma oportunidade de emprego na organização.  Para criar uma solicitação de emprego, o candidato já deve constar como um candidato ou uma pessoa no sistema.
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

Uma ação de correspondência da **Solicitação de emprego** determina o modelo de documento ou de email que você usa para se comunicar com o candidato que enviou a solicitação. Você pode associar ** indicadores de solicitação ** com ações de correspondência para que você use valores das páginas do aplicativo, do candidato, a entrevista, e de projeto de recrutamento em suas comunicações com candidatos.  ** Modelos de email de solicitação ** podem ser criadas para as ações de correspondência para enviar email rapidamente candidatos que têm uma solicitação a determinada combinação de ação de status e de correspondência. Por exemplo, você pode enviar um email de confirmação a todas as solicitações de emprego com ** ** o status recebido e a ação de correspondência ** ** de recebimento.  Após enviado o email, você tem a opção para atualizar automaticamente o status de aplicativos.

## <a name="application-routing"></a>Roteamento da solicitação de emprego

Se uma solicitação de emprego deve ser revisada por vários trabalhadores, você pode usar a página **Roteamento da solicitação de emprego** para criar uma lista de circulação do trabalhador para gerenciar o processo.

## <a name="interviews"></a>Entrevistas

** O candidato entrevista ** pode ser programada ** de aplicativos ** página.  Use ** enviar informações reunião ** botão para enviar um arquivo de calendário com informações de planejamento da entrevista para o candidato e o entrevistador.

## <a name="skill-mapping"></a>Mapeamento de habilidades

**Mapeamento de habilidades** e **Perfis de mapeamento de habilidades** podem ser usados para identificar candidatos que possam ser uma boa opção para uma vaga.

## <a name="hiring-applicants"></a>Candidatos de contratação

Use a página **Solicitações de emprego** para contratar um candidato. Quando você contratar um candidato, o registro de solicitação de emprego terá o status **Empregado** e o registro pessoal no catálogo de endereços global do candidato será associado ao registro do novo trabalhador. As alterações nas informações do catálogo de endereços global para o registro de novos funcionários também são exibidos no registro do candidato. Isso pode ajudar a reduzir a entrada de dados se o novo trabalhador nunca se aplica para um trabalho diferentes em sua empresa.  Para contratar um trabalhador existente em uma nova posição, clique ** posição altere ** ** o status do aplicativo soltam-se ** para baixo para iniciar o processo de transferência.




