---
title: Fluxo de trabalho de cliente
description: Este tópico fornece informações sobre o fluxo de trabalho de cliente. Você altera campos específicos de um cliente e envia essas alterações para aprovação usando o fluxo de trabalho antes que elas sejam adicionadas ao cliente.
author: abruer
ms.date: 08/24/2018
ms.topic: index-page
ms.prod: ''
ms.technology: ''
ms.search.form: Customer
audience: Application User
ms.reviewer: roschlom
ms.search.region: Global
ms.author: roschlom
ms.search.validFrom: 2018-08-30
ms.dyn365.ops.version: 8.0.4
ms.openlocfilehash: c74f18997b390d70b5012199fab1adc9734994f4
ms.sourcegitcommit: 408786b164b44bee4e16ae7c3d956034d54c3f80
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/05/2021
ms.locfileid: "7753817"
---
# <a name="customer-workflow"></a>Fluxo de trabalho de cliente

[!include [banner](../includes/banner.md)]

O fluxo de trabalho de cliente foi adicionado à versão 8.0.4. Você pode alterar campos específicos de um cliente e enviar essas alterações para aprovação usando o fluxo de trabalho antes que elas sejam adicionadas ao cliente.

## <a name="set-up-the-customer-workflow"></a>Configurar o fluxo de trabalho de cliente

Antes de usar o recurso fluxo de trabalho de cliente, você deve habilitá-lo.

1. Vá para **Contas a receber \> Configuração \> Parâmetros de contas a receber**.
2. Na guia **Geral**, na FastTab **Aprovação de cliente**, defina a opção **Habilitar aprovações de cliente** como **Sim** para habilitar o recurso.
3. No campo **Comportamento de entidade de dados**, selecione o comportamento que as entidades de dados devem usar quando os dados forem importados:

    - **Permitir alterações sem aprovação** – Uma entidade pode atualizar o registro do cliente sem processá-lo por meio do fluxo de trabalho.
    - **Rejeitar alterações** – As alterações não podem ser feitas no registro do cliente. Ocorrerá falha na importação dos campos habilitados para o fluxo de trabalho.
    - **Criar propostas de alteração** – Todos os campos serão alterados exceto os campos habilitados para o fluxo de trabalho. Os novos valores para esses campos serão adicionados ao cliente como alterações propostas, e o fluxo de trabalho será iniciado automaticamente.

4. Na lista de campos de cliente, marque a caixa de seleção **Habilitar** para cada campo a ser aprovado antes que as alterações sejam feitas.
5. Vá para **Contas a receber \> Configuração \> Fluxos de trabalho de contas a receber**.
6. Selecione **Novo**.
7. Selecione **Fluxo de trabalho da alteração proposta de cliente**. 
8. Configurar o fluxo de trabalho para que corresponda ao processo de aprovação. O elemento de aprovação do fluxo de trabalho **Aprovação de fluxo de trabalho para a alteração de cliente proposta** aplicará as alterações ao cliente.

## <a name="change-customer-information-and-submit-the-changes-to-the-workflow"></a>Altere as informações do cliente e envie as alterações para o fluxo de trabalho

Quando alterar um campo que está habilitado para o fluxo de trabalho, a página **Alterações propostas** será exibida. Esta página mostra o valor original do campo e do novo valor inserido. O campo que você alterou foi revertido para o valor original. Uma mensagem de status na página informa que as alterações não foram enviadas.

Cada vez que um campo que está habilitado para o fluxo de trabalho for alterado, o campo será adicionado à lista de alterações propostas. Para rejeitar o valor proposto para um campo, use o botão **Descartar** ao lado do campo na lista. Para rejeitar todas as alterações, use o botão **Descartar todas as alterações** na parte inferior da página. Selecione **OK** para fechar a página.

Após haver pelo menos uma alteração proposta, dois menus adicionais aparecerão no Painel de Ações: **Alterações propostas** e **Fluxo de trabalho**.

1. Selecione **Alterações propostas** para abrir a página **Alterações propostas** e revisar as alterações.
2. Selecione **Fluxo de trabalho \> Enviar** para enviar as alterações para o fluxo de trabalho.

    O status na página foi alterado para **Alterações com aprovação pendente**.

O fluxo de trabalho segue o processo de fluxo de trabalho padrão no aplicativo. O aprovador é direcionado à página **Cliente**, na qual é possível revisar as alterações na página **Alterações propostas** e, em seguida, selecionar **Fluxo de trabalho \> Aprovar** para aprovar o fluxo de trabalho. Depois que todas as aprovações forem concluídas, os campos serão atualizados com os valores que você propôs.


[!INCLUDE[footer-include](../../includes/footer-banner.md)]
