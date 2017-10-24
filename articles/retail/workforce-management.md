---
title: "Visão geral do gerenciamento da força de trabalho"
description: "Este tópico descreve como você pode usar o serviço do Gerenciamento da força de trabalho (WFM) para se beneficiar de clientes do ponto de venda (PDV), Modern POS e Cloud POS, de forma que os gerentes de loja possam gerenciar facilmente sua força de trabalho."
author: shalabhjainmsft
manager: AnnBe
ms.date: 7/20/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: josaw
ms.search.scope: Operations, Core
ms.custom: 260624
ms.assetid: a4f9d315-9951-451c-8ee6-37f9b3b15ef0
ms.search.region: global
ms.search.industry: Retail
ms.author: shajain
ms.search.validFrom: 2017-07-30
ms.dyn365.ops.version: Retail July 2017 update
ms.translationtype: HT
ms.sourcegitcommit: d67ad79c068651f32ce7dc776bc460698557bc29
ms.openlocfilehash: f747dce6b9595de50297cb5af7db523d5f26a844
ms.contentlocale: pt-br
ms.lasthandoff: 09/29/2017

---

# <a name="workforce-management-overview"></a>Visão geral do gerenciamento da força de trabalho

[!include[banner](includes/banner.md)]
    
O serviço Gerenciamento de força de trabalho (WFM) aproveita a vantagem dos clientes do ponto de venda (PDV) familiar, Modern PDV e Cloud PDV para permitir que os gerentes de loja gerenciem facilmente sua força de trabalho. O serviço WFM usa a estrutura de extensão para fazer download de pacotes relevantes no PDV. Esses pacotes são baixados quando o PDV é fechado e reaberto. Portanto, quando a Microsoft libera novos recursos para WFM, o aplicativo PDV deve ser fechado e reaberto.

Usando este serviço, os gerentes de loja criam e publicam facilmente a agenda de trabalho semanal para suas lojas. Os trabalhadores da loja podem exibir rapidamente suas próprias agendas e as agendas de seus colegas. Dessa forma, eles podem aprender quem trabalhará com eles durante os turnos atribuídos. Os trabalhadores da loja também podem criar solicitações de ausência, troca de turno e oferta de turno. Todas essas solicitações acionam um fluxo de trabalho definido.

Durante um turno, os trabalhadores da loja podem ter as vantagens do recurso de registro de entrada e de saída que é criado nos clientes PDV. Os dados são enviados em para matrizes (HQ) para processamento de pagamento. O recurso de entrada e de saída é um recurso existente do POS. Para obter mais informações sobre os cenários de instalação e suporte, consulte [Registro de entrada e saída](retail-time-attendance.md).

## <a name="supported-scenarios"></a>Cenários com suporte
Esta seção fornece mais informações sobre os cenários de suporte.

- **Criar e publicar agenda** – O serviço de WFM usa as permissões do PDV configuradas na matriz para determinar se um trabalhador tiver privilégios do gerente da loja. Somente os gerentes de loja podem criar e publicar agendas usando a operação de gerenciamento da agenda. Eles podem criar rapidamente uma agenda copiando e colando um turno de trabalho existente de um trabalhador para outro trabalhador. Eles também podem criar uma agenda importando a agenda de qualquer semana anterior para a semana atual.

    Se um plano não for publicado, ele fica em um estado em rascunho e parece diferente de uma agenda publicada. Os gerentes de loja podem publicar uma agenda clicando no botão **Publicar** em qualquer semana. Depois que a agenda for publicada por uma semana, as alterações estão publicadas automaticamente. Os exemplos de alterações incluem a adição ou exclusão de turnos ou de ausências de trabalho, ou edições para turnos de trabalho ou ausências. Os funcionários da loja podem exibir apenas as agendas que foram publicadas para várias semanas.
    
- **Criar e aprovar solicitações** – Os funcionários da loja podem criar três tipos de solicitações:

    - Solicitação de ausência
    - Troca de turno de solicitação
    - Oferta de turno de solicitação

    Essas solicitações podem ser criadas usando a operação de solicitações de Agenda. Cada solicitação segue um fluxo de trabalho definido e os trabalhadores podem ver facilmente o status atual de suas solicitações.
    
    As solicitações de ausência são enviadas automaticamente o gerente da loja para aprovação. Se houver vários gerentes de loja, todos os gerentes podem exibir uma determinada solicitação, mas somente um gerente pode aprová-la ou rejeitá-la. Os tipos de ausência são configurados na matriz de varejo usando a página **Tipos de licença e ausência** no módulo **Retail** . Depois que o gerente de loja aprovar ou rejeitar uma solicitação, ela é movida para a guia **Histórico** da operação de solicitações da Agenda.
    
    Uma troca de turno ou uma solicitação de oferta de turno vai para o trabalhador para o qual a solicitação foi enviada. O gerente da loja pode exibir a solicitação somente após este trabalhador ter aprovado-a. Portanto, se o trabalhador rejeitar a troca de turno ou a solicitação da oferta do turno, o gerente pode visualizá-la. O trabalhador que criou a solicitação também pode cancelá-la antes do gerente aprová-la ou negá-la.

- **Mostra os trabalhadores da loja ativos na exibição da agenda** – Quando um trabalhador for adicionado a uma loja, por exemplo, associando-a ao catálogo de endereços da loja, o trabalhador torna-se disponível para agendamento no serviço WFM. Um trabalho em lote recorrente que é nomeado **Processar dados do trabalhador para gerenciamento de força de trabalho** é executado na matriz. Esse trabalho prepara as associações de loja-trabalhador que serão enviadas para o Common Data Service (CDS).

    O mesmo processo é usado quando um trabalhador é removido de um loja. Entretanto, o trabalhador que é removido ainda será mostrado para semanas passadas, atuais e futuras, se um turno de trabalho ativo ou ausência for atribuído àquele trabalhador. Portanto, a menos que esses turnos de trabalho e ausências sejam excluídos, o trabalhador removido continuará sendo mostrado para essas semanas.

