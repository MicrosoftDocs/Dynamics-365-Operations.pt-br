---
title: Fluxo de trabalho do fornecedor
description: Modifique as informações do fornecedor e o fluxo de trabalho de uso de aprová-las.
author: mikefalkner
manager: annbe
ms.date: 08/24/2018
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: Vendor
audience: Application User
ms.reviewer: roschlom
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: mikefalkner
ms.search.validFrom: 2018-08-30
ms.dyn365.ops.version: 8.0.4
ms.openlocfilehash: 112f9d6adeee583a63da8ab700d7adc179de2c1d
ms.sourcegitcommit: 8b4b6a9226d4e5f66498ab2a5b4160e26dd112af
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/01/2019
ms.locfileid: "1835301"
---
# <a name="vendor-workflow"></a>Fluxo de trabalho do fornecedor

[!include [banner](../includes/banner.md)]

Quando o fluxo de trabalho do fornecedor é usado, as alterações feitas em campos específicos são enviadas para o fluxo de trabalho para aprovação antes que sejam adicionadas ao fornecedor.

## <a name="set-up-the-vendor-workflow"></a>Configurar o fluxo de trabalho do fornecedor

Antes de usar o recurso fluxo de trabalho do fornecedor, você deve habilitá-lo.

1. Acesse **Contas a pagar \> Configuração \> Parâmetros de contas a pagar**.
2. Na guia **Geral**, na Guia Rápida **Aprovação do fornecedor** , defina a opção **Habilitar aprovações de fornecedor** como **Sim**.
3. No campo **Comportamento de entidade de dados**, selecione o comportamento que deverá ser usado quando os dados forem importados:

    - **Permitir alterações sem aprovação** – a entidade de dados pode atualizar o registro do fornecedor sem processá-lo por meio do fluxo de trabalho.
    - **Rejeitar alterações** – as alterações não podem ser feitas no registro do fornecedor. Ocorrerá falha na importação dos campos habilitados para o fluxo de trabalho.
    - **Criar propostas de alteração** – todos os campos serão alterados exceto os campos habilitados para o fluxo de trabalho. Os novos valores para esses campos serão adicionados ao fornecedor como alterações propostas, e o fluxo de trabalho será iniciado automaticamente.

4. Na lista de campos de fornecedor, marque a caixa de seleção **Habilitar** para cada campo a ser aprovado antes que as alterações sejam feitas.
5. Acesse **Contas a pagar \> Configuração \> Fluxos de trabalho de contas a pagar**.
6. Selecione **Novo**.
7. Selecione **Fluxo de trabalho das alterações propostas de fornecedor**. 
8. Configure o fluxo de trabalho para que corresponda ao processo de aprovação. O elemento de aprovação do fluxo de trabalho **Aprovação de fluxo de trabalho para a alteração proposta de fornecedor** aplicará as alterações ao fornecedor.

## <a name="change-vendor-information-and-submit-the-changes-to-the-workflow"></a>Alterar informações do fornecedor e enviar as alterações para o fluxo de trabalho

Quando alterar um campo que está habilitado para o fluxo de trabalho, a página **Alterações propostas** será exibida. Esta página mostra o valor original do campo e do novo valor inserido. O campo que você alterou foi revertido para o valor original. Uma mensagem de status também informa que as alterações não foram enviadas. 

Cada vez que um campo que está habilitado para o fluxo de trabalho for alterado, o campo será adicionado à lista na página **Alterações propostas**. Para rejeitar o valor proposto para um campo, use o botão **Descartar** ao lado do campo na lista. Para descartar todas as alterações, use o botão **Descartar todas as alterações** na parte inferior da página. Selecione **OK** para fechar a página.

Após de ter pelo menos uma alteração proposta, duas guias adicionais aparecerão no painel de ações: **Alterações propostas** e **Fluxo de trabalho**.

1. Selecione **Alterações propostas** para abrir a página **Alterações propostas** e revisar as alterações.
2. Selecione **Fluxo de trabalho \> para enviar as alterações para o fluxo de trabalho**.

    O status na página foi alterado para **Alterações com aprovação pendente**.

O fluxo de trabalho segue o processo padrão de fluxo de trabalho no Microsoft Dynamics 365 for Finance and Operations. O aprovador é direcionado à página **Fornecedor**, na qual pode revisar as alterações na página **Alterações propostas** e selecionar **Fluxo de trabalho \> Aprovar** para aprovar o fluxo de trabalho. Depois que todas as aprovações forem concluídas, os campos serão atualizados com os valores que você propôs.
