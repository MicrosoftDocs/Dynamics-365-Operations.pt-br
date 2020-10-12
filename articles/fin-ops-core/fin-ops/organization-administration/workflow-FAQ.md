---
title: Perguntas frequentes sobre fluxo de trabalho
description: Esse tópico responde perguntas frequentes sobre o sistema de fluxo de trabalho.
author: ChrisGarty
manager: AnnBe
ms.date: 09/21/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
audience: Application User, IT Pro
ms.reviewer: sericks
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: cgarty
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 4ba60c832b1f1ac5f514baef4cc0a9c36dd85af9
ms.sourcegitcommit: 175f9394021322c685c5b37317c2f649c81a731a
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/21/2020
ms.locfileid: "3826181"
---
# <a name="workflow-faq"></a>Perguntas frequentes sobre fluxo de trabalho

[!include [banner](../includes/banner.md)]

Esse tópico responde perguntas frequentes sobre o sistema de fluxo de trabalho.

## <a name="why-are-multiple-notifications-received-when-a-work-item-is-rejected"></a>Por que várias notificações são recebidas quando um item de trabalho é rejeitado?
Quando um item de trabalho é rejeitado, esse item de trabalho é concluído como anulado. Outro item de trabalho é criado e atribuído ao originador. Isso significa que há uma notificação para o originador do item de trabalho rejeitado, e uma notificação separada para o usuário atribuído ao novo item de trabalho com "alteração solicitada". 

Cada notificação é para um item de trabalho diferente, mas a similaridade pode causar confusão. Sempre estamos de olho em formas para aprimorar isso em uma versão futura.

## <a name="why-are-my-workflow-exports-failing"></a>Por que minhas exportações de fluxo de trabalho estão falhando?
Atualmente, existe uma limitação no recurso de exportação de fluxo de trabalho para prevenir que nomes de fluxo de trabalho excedam 48 caracteres. Usar um nome maior que 48 caracteres pode resultar em um erro de "Falha do servidor ao autenticar a solicitação" e/ou prevenir que um arquivo seja exportado sem um tipo de arquivo. A postagem de blog a seguir fornece mais detalhes, [Solução de problemas na exportação do fluxo de trabalho](https://community.dynamics.com/ax/b/elandaxdynamicsaxupgradesanddevelopment/archive/2019/04/10/workflow-export-troubleshooting).

## <a name="can-the-submitter-of-a-workflow-also-approve-the-workflow"></a>O emissor de um fluxo de trabalho também pode aprovar o fluxo de trabalho?
Sim, um emissor de fluxo de trabalho também poderá aprovar o fluxo de trabalho se ele estiver configurado dessa forma. Para impedir este comportamento, defina **Administração do sistema > Fluxo de trabalho > Parâmetros do fluxo de trabalho > Geral > Aprovador > Rejeitar aprovação pelo remetente** como **Sim**.

## <a name="can-i-add-alerts-to-workflows-to-provide-notifications-to-users"></a>Posso adicionar alertas a fluxos de trabalho para fornecer notificações a usuários?
Estes são alguns pontos importantes a serem observados para adicionar alertas a fluxos de trabalho para fornecer notificações:
- Alertas versus mecanismos de notificação de fluxo de trabalho
    - Os alertas podem ser configuradas para alterações de registro. Os fluxos de trabalho alteram registros. Então, é possível configurar um alerta relacionado a uma alteração de registro causada por um fluxo de trabalho. Porém, como os fluxos de trabalho têm opções de notificação internas diferentes, o uso de alertas não é ideal.
- Notificações padrão de fluxos de trabalho 
    - Os fluxos de trabalho têm notificações de email internas. Um cliente pode configurar as notificações para que os usuários recebam emails. Essas notificações não resultam em mensagens da Central de Ações para usuários.
    - Em uma atualização futura, adicionaremos uma mensagem da Central de Ações para que seja atribuído um item de trabalho de fluxo de trabalho a um usuário. 
- Como adicionar notificações a fluxos de trabalho
    - As mensagens da Central de Ações podem ser criadas para usuários específicos, como uma mensagem criada de um fluxo de trabalho em X++.
    - [Fluxos de trabalho têm eventos de negócios](https://docs.microsoft.com/dynamics365/unified-operations/dev-itpro/business-events/business-events-workflow) que o cliente pode usar para disparar fluxos com as notificações que ele está procurando.   

Em resumo, se um usuário não receber a notificação adequada da Central de Ações quando um item de trabalho de fluxo de trabalho for atribuído a ele, aproveite [Eventos de negócios de fluxo de trabalho](https://docs.microsoft.com/dynamics365/unified-operations/dev-itpro/business-events/business-events-workflow) com o Microsoft Power Automate para fornecer notificações adicionais ou diferentes.

## <a name="why-is-workflow-editor-not-able-to-start-under-ad-fs"></a>Por que o editor de fluxo de trabalho não consegue iniciar no AD FS?
Ao executar no Active Directory Federation Services (AD FS) em um ambiente atualizado, o editor do fluxo de trabalho pode ter problemas ao iniciar. Se isso acontecer, certifique-se de que a URL "https://dynamicsaxworkfloweditor/" seja adicionada à propriedade **Microsoft Dynamics 365 for Operations Local - Fluxo de trabalho - Aplicativo nativo** nas configurações do ADFS.

## <a name="why-am-i-getting-sql-deadlocks-on-workflow-processing"></a>Por que estou obtendo deadlocks de SQL no processamento do fluxo de trabalho? 
O valor padrão do campo para o **Número de itens de fluxo de trabalho por lote** na página **Parâmetros de fluxo de trabalho** é 0. O valor 0 faz com que o padrão seja alterado para 20 itens por lote. Tenha cuidado ao ajustar esse valor porque um grande número de itens por lote (> 40) pode causar deadlocks no SQL.

## <a name="what-is-the-workflow-enhanced-error-feature"></a>O que é o recurso de Erro Avançado do Fluxo de Trabalho?
O recurso de Erro Avançado do Fluxo de Trabalho na versão 10.0.13 adiciona códigos de erro para diferenciar classes diferentes de erros de fluxo de trabalho. As mensagens de erro relatadas serão quase parecidas, com pequenas diferenças para torná-las mais claras.
