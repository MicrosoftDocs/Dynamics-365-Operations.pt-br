---
title: Perguntas frequentes sobre fluxo de trabalho
description: Esse artigo responde perguntas frequentes sobre o sistema de fluxo de trabalho.
author: ChrisGarty
ms.date: 03/01/2022
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User, IT Pro
ms.reviewer: sericks
ms.search.region: Global
ms.author: cgarty
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: a72fd141bb1178a3a83385c512d1a655064d5b00
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/03/2022
ms.locfileid: "8896569"
---
# <a name="workflow-faq"></a>Perguntas frequentes sobre fluxo de trabalho

[!include [banner](../includes/banner.md)]


[!INCLUDE [PEAP](../../../includes/peap-1.md)]

Esse artigo responde perguntas frequentes sobre o sistema de fluxo de trabalho.

## <a name="why-are-multiple-notifications-received-when-a-work-item-is-rejected"></a>Por que várias notificações são recebidas quando um item de trabalho é rejeitado?
Quando um item de trabalho é rejeitado, esse item de trabalho é concluído como anulado. Outro item de trabalho é criado e atribuído ao originador. Isso significa que há uma notificação para o originador do item de trabalho rejeitado, e uma notificação separada para o usuário atribuído ao novo item de trabalho com "alteração solicitada". 

Cada notificação é para um item de trabalho diferente, mas a similaridade pode causar confusão. Sempre estamos de olho em formas para aprimorar isso em uma versão futura.

## <a name="why-are-my-workflow-exports-failing"></a>Por que minhas exportações de fluxo de trabalho estão falhando?
Atualmente, existe uma limitação no recurso de exportação de fluxo de trabalho para prevenir que nomes de fluxo de trabalho excedam 48 caracteres. Usar um nome maior que 48 caracteres pode resultar em um erro de "Falha do servidor ao autenticar a solicitação" e/ou prevenir que um arquivo seja exportado sem um tipo de arquivo. A postagem de blog a seguir fornece mais detalhes, [Solução de problemas na exportação do fluxo de trabalho](https://community.dynamics.com/365/financeandoperations/b/elandaxdynamicsaxupgradesanddevelopment/posts/workflow-export-troubleshooting).

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
    - [Fluxos de trabalho têm eventos de negócios](../../dev-itpro/business-events/business-events-workflow.md) que o cliente pode usar para disparar fluxos com as notificações que ele está procurando.   

Em resumo, se um usuário não receber a notificação adequada da Central de Ações quando um item de trabalho de fluxo de trabalho for atribuído a ele, aproveite [Eventos de negócios de fluxos de trabalho](../../dev-itpro/business-events/business-events-workflow.md) com o Microsoft Power Automate para fornecer notificações adicionais ou diferentes.

## <a name="why-is-workflow-editor-not-able-to-start-under-ad-fs"></a>Por que o editor de fluxo de trabalho não consegue iniciar no AD FS?
Ao executar no Active Directory Federation Services (AD FS) em um ambiente atualizado, o editor do fluxo de trabalho pode ter problemas ao iniciar. Se isso acontecer, certifique-se de que a URL "https://dynamicsaxworkfloweditor/" seja adicionada à propriedade **Microsoft Dynamics 365 for Operations Local - Fluxo de trabalho - Aplicativo nativo** nas configurações do ADFS.

## <a name="why-am-i-getting-sql-deadlocks-on-workflow-processing"></a>Por que estou obtendo deadlocks de SQL no processamento do fluxo de trabalho? 
O valor padrão do campo para o **Número de itens de fluxo de trabalho por lote** na página **Parâmetros de fluxo de trabalho** é 0. O valor 0 faz com que o padrão seja alterado para 20 itens por lote. Tenha cuidado ao ajustar esse valor porque um grande número de itens por lote (> 40) pode causar deadlocks no SQL.

## <a name="what-is-the-workflow-enhanced-error-feature"></a>O que é o recurso de Erro Avançado do Fluxo de Trabalho?
O recurso de Erro Avançado do Fluxo de Trabalho na versão 10.0.13 adiciona códigos de erro para diferenciar classes diferentes de erros de fluxo de trabalho. As mensagens de erro relatadas serão quase parecidas, com pequenas diferenças para torná-las mais claras.


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]
