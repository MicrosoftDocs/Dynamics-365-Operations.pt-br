---
title: Criar alertas
description: "Este tópico fornece informações sobre os alertas e explica como criar uma regra de alerta para que você seja notificado sobre eventos, como uma data do evento ou uma alteração específica que ocorra."
author: tjvass
manager: AnnBe
ms.date: 03/20/2018
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: EventCreateRule
audience: Application user
ms.reviewer: sericks
ms.search.scope: Operations
ms.search.region: Global
ms.author: tjvass
ms.search.validFrom: 2018-3-30
ms.dyn365.ops.version: Platform update 15
ms.translationtype: HT
ms.sourcegitcommit: 454368ab5a467002ebf973db97fd98e31885dfe0
ms.openlocfilehash: 5bcd02e08a4ce5b601615b39bf95362cf92d3fec
ms.contentlocale: pt-br
ms.lasthandoff: 03/23/2018

---

# <a name="create-alerts"></a>Criar alertas

[!INCLUDE [banner](../includes/banner.md)]

[!INCLUDE [banner](../includes/pre-release.md)]

## <a name="getting-started"></a>Introdução
Antes de configurar uma regra de alerta, decida quando ou em quais situações deseja receber alertas. Quando souber qual evento deseja ser notificado, no Microsoft Dynamics 365 for Finance and Operations localize a página na qual aparecem os dados que causam o evento. O evento pode ser uma data de ocorrência ou uma alteração específica que ocorra. Portanto, você deve encontrar a página na qual a data é especificada ou onde aparece o campo que é alterado ou o novo registro que é criado. Quando tiver estas informações, você poderá criar a regra de alerta.

Quando cria uma regra de alerta, você define os critérios que o sistema deve atender para que um alerta seja acionado. Pense nos critérios como uma coincidência entre a ocorrência de um evento e o preenchimento de condições específicas. Quando um evento ocorre, o sistema inicia a verificação de acordo com as condições configuradas no Finance and Operations.

## <a name="events"></a>Eventos
O evento que aciona uma regra de alerta pode ser uma data que se aproxima ou uma alteração específica que ocorre. Os disparadores de eventos são definidos na Guia rápida **Alertar-me quando** da caixa de diálogo **Criar regra de alerta**. Os eventos disponíveis para um determinado campo dependem do disparador que é selecionado.

Por exemplo, se estiver configurando uma regra de alerta para o campo **Data de início**, os eventos da data de vencimento são apropriados. Portanto, o tipo de evento **vence em** fica disponível para aquele campo. Porém, para um campo como **Centro de custo**, um evento de data de vencimento não é apropriado. Portanto, o tipo de evento **vence em** não fica disponível. Em vez disso, o tipo de evento **foi alterado** estará disponível.

## <a name="event-types"></a>Tipos de evento
Três tipos de evento podem ocorrer:

- **Eventos do tipo Criar ou excluir** – Esses eventos disparam um alerta quando um registro é criado ou excluído.
- **Eventos do tipo Atualizar** – Esses eventos acionam um alerta quando os dados de um campo específico são alterados.
- **Eventos do tipo Data de vencimento** – Esses eventos disparam um alerta quando chega uma data.
    
As alterações ocorridas podem ser iniciadas por um usuário. Por exemplo, um usuário altera a data de entrega de uma ordem de compra. Como alternativa, as alterações podem ocorrer como parte de um processo. Por exemplo, o campo **Status** em uma página é alterado para refletir o ciclo de vida de vários processos no sistema.

## <a name="conditions"></a>Condições
Na guia rápida **Alertar-me para** da caixa de diálogo **Criar regra de alerta**, você pode usar condições para controlar quando você será alertado sobre os eventos.

Por exemplo, você pode especificar que o sistema deve alertá-lo quando o status das ordens de compra for alterado, mas apenas se o status corresponder a um determinado conjunto de condições. Especificamente, você quer ser alertado quando o status de uma ordem de compra for alterado para **Recebido**. Essa alteração no status é o evento que aciona o alerta.

Em seguida, você deverá decidir sobre quais ordens de compra você deseja ser alertado. Por exemplo, você pode selecionar uma das opções a seguir. Essas opções definem as condições da regra do alerta.

- **Registro selecionado atual** – Você recebe um alerta quando o status de uma ordem de compra específica for alterado para **Recebido**.
- **Todos os registros** – Você receberá um alerta quando o status de uma ordem de compra for alterado para um item na exibição da página ativa. Você pode usar a filtragem avançada disponível na página criar regras para criar regras para um conjunto específico de registros. Por exemplo, você pode criar um alerta que é disparado para todas as ordens de compra dos clientes em um grupo de clientes específico.
    
## <a name="expiry-of-rule"></a>Vencimento da regra
Na guia rápida **Alertar-me até** da caixa de diálogo **Criar regra de alerta**, você pode especificar quanto tempo a regra de alerta deve ficar ativa.

## <a name="alert-contents"></a>Conteúdo do alerta
Na guia rápida **Alertar-me com** da caixa de diálogo **Criar regra de alerta**, você pode especificar o texto do assunto e o texto da mensagem que as mensagens de alerta devem usar.

## <a name="user-id"></a>ID do usuário
Na guia rápida **Alertar-me com** da caixa de diálogo **Criar regra de alerta**, você pode especificar qual usuário deve receber as mensagens de alerta. Por padrão, seu ID de usuário é selecionado. Esta opção está restrita a administradores da organização.

## <a name="create-an-alert-rule"></a>Crie uma regra de alerta
1. Abra a página que contém os dados a serem monitorados.
2. No Painel de Ação, na guia **Opções**, no grupo **Compartilhar**, selecione **Criar regra de alerta**.
3. Na caixa de diálogo **Criar regra de alerta**, no campo **Campo**, selecione o campo a ser monitorado.
4. No campo **Evento**, selecione o tipo de evento.
5. Na guia rápida **Alertar-me para**, selecione uma opção.
6. Caso você queira que a regra de alerta se torne ativa em uma determinada data, na guia rápida **Alertar-me até**, selecione uma data final.
7. Na guia rápida **Alertar-me com**, no campo **Assunto**, aceite o cabeçalho padrão do assunto para a mensagem de e-mail ou insira um novo assunto. O texto é usado como o título do assunto da mensagem de email recebida quando um alerta é acionado.
8. No campo **Mensagem**, digite uma mensagem opcional. O texto é usado como a mensagem recebida quando um alerta é acionado.
9. Selecione **OK** para salvar as configurações e criar a regra de alerta.

