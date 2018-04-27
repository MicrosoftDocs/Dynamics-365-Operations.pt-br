---
title: "Visão geral dos alertas"
description: "Este tópico fornece informações gerais sobre alertas no Microsoft Dynamics 365 for Finance and Operations. Você pode usar alertas para manter-se informado sobre os eventos que deseja acompanhar durante o dia útil."
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
ms.search.scope: Operations, Core
ms.search.region: Global
ms.author: tjvass
ms.search.validFrom: 2018-3-30
ms.dyn365.ops.version: Platform update 15
ms.translationtype: HT
ms.sourcegitcommit: a8b5a5af5108744406a3d2fb84d7151baea2481b
ms.openlocfilehash: ad9373faa19761cccca2b5d581de05f0ac9dd165
ms.contentlocale: pt-br
ms.lasthandoff: 04/13/2018

---

# <a name="alerts-overview"></a>Visão geral dos alertas

[!INCLUDE [banner](../includes/banner.md)]

[!INCLUDE [banner](../includes/pre-release.md)]

## <a name="about-alerts"></a>Sobre alertas
Alertas de um sistema de notificação para eventos críticos no Microsoft Dynamics 365 for Finance and Operations. Você pode usar alertas para manter-se informado sobre os eventos que deseja acompanhar durante o dia útil. Você pode criar facilmente seu próprio conjunto de regras de alerta para ser alertado sobre entregas atrasadas, ordens excluídas, preços alterados ou outros eventos pelos quais você deve ser o responsável.

No planejamento de recursos empresariais (ERP), há vários cenários típicos no qual o recurso de alertas no Finance and Operations pode ser usado. Aqui estão alguns exemplos.

### <a name="scenario-1-create-an-alert-rule-for-new-sales-orders"></a>Cenário 1: Criar uma regra de alerta para novas ordens de venda
1. Abra a página **Todas as ordens de venda**.
2. No Painel de Ação, na guia **Opções**, no grupo **Compartilhar**, selecione **Criar um alerta personalizado**.
3. Na caixa de diálogo **Criar regra de alerta** , na guia rápida **Alertar-me quando**, no campo **Evento** , selecione **O registro foi criado**.

### <a name="scenario-2-create-an-alert-rule-for-postponement-of-a-delivery-date"></a>Cenário 2: Criar uma regra de alerta para o adiamento de uma data de entrega
1. Abra a página **Todas as ordens de compra**.
2. Selecione um ID da ordem de compra para acessar os detalhes da ordem de compra.
3. Expanda a guia rápida **cabeçalho da Ordem de compra**.
4. No Painel de Ação, na guia **Opções**, no grupo **Compartilhar**, selecione **Criar um alerta personalizado**.
5. Na caixa de diálogo **Criar regra de alerta** , na guia rápida **Alertar-me quando**, no campo **Campo** , selecione **Data de entrega**.
6. No campo **Evento** , selecione **foi adiado**.
    
Depois que você fechar a caixa de diálogo **Criar regra de alerta**, sua regra aparecerá na página **Gerenciar regras de alerta**. Você pode usar a página **Gerenciar regras de alerta** para atualizar suas regras de alerta existentes. Por exemplo, você pode alterar os disparadores do evento, atualizar as notificações de eventos e atualizar as datas de vencimento. Para abrir a página **Gerenciar regras de alerta**, use o botão **Alertar-me** na guia **Opções** do Painel de Ação.

## <a name="what-occurs-when-an-alert-rule-is-created"></a>O que acontece quando uma regra de alerta é criada?
Ao criar regras de alerta, é possível associar um evento predefinido com um campo específico. Por exemplo, a data especificada no campo é atingida ou o conteúdo do campo é alterado. Como alternativa, é possível associar um evento aos registros de uma página específica. Por exemplo, um registro é criado ou um registro é excluído.

Quando o evento selecionado ocorre para o campo ou para um registro da página, um alerta é enviado a você. Por exemplo, você cria uma regra na qual associa o campo **Data de entrega** em uma linha específica da ordem de compra ao evento **venceu neste período** . Você define o período como cinco dias. Neste caso, um alerta é enviado cinco dias após a data de entrega dessa linha de ordem de compra.

Além disso, é possível refinar as regras de alerta definindo as condições. Por exemplo, você pode ser alertado sobre novas ordens de compra criadas para contas de fornecedor específicas.

## <a name="preparing-for-an-alert"></a>Preparando um alerta
Antes de configurar uma regra de alerta, decida quando ou em quais situações deseja receber alertas. Quando souber sobre qual evento deseja ser notificado no Finance and Operations, localize a página na qual aparecem os dados que causam o evento. O evento pode ser uma data de ocorrência ou uma alteração específica que ocorra. Portanto, você deve encontrar a página na qual a data é especificada ou onde aparece o campo que é alterado ou o novo registro que é criado. Quando tiver estas informações, você poderá criar a regra de alerta.

## <a name="components-of-an-alert-rule"></a>Componentes de uma regra de alerta
Uma regra de alerta tem cinco componentes:

- **Evento** – O evento que aciona uma regra de alerta pode ser uma data de ocorrência ou uma alteração específica que ocorre. Você define eventos na guia rápida **Enviar alertas de email para alterações do status do trabalho** da caixa de diálogo **Criar regra de alerta**.
- **Condição** – Na guia rápida **Alertar-me para** da caixa de diálogo **Criar regra de alerta**, você pode selecionar o escopo da condição para controlar quando será alertado sobre os eventos. Você pode aplicar a regra no registro atual ou apenas em todos os registros visíveis da página. Se a regra se aplicar em entidades legais, você pode definir a opção **Em toda a organização** como **Sim**.
- **Expiração da regra** – Na guia rápida **Alertar-me até** da caixa de diálogo **Criar regra de alerta**, você pode especificar por quanto tempo a regra de alerta deve ficar ativa.
- **Conteúdo** – Na guia rápida **Alertar-me com** da caixa de diálogo **Criar regra de alerta** é possível especificar o texto do assunto e o texto da mensagem que as mensagens de alerta devem usar.
- **Usuário** – Na guia rápida **Quem alertar** da caixa de diálogo **Criar regra de alerta** é possível especificar qual usuário deve receber as mensagens de alerta. Por padrão, seu ID de usuário é selecionado.

    > [!NOTE]
    > Esta opção está restrita a administradores da organização.

## <a name="email-notifications-from-alerts"></a>Notificações por email de alertas
As notificações por email de alertas ainda não estão habilitadas. Isso será habilitado em uma atualização futura.

