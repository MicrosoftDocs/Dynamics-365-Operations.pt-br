---
title: Defina os parâmetros de TDS no Contas a pagar e no Contas a receber
description: Este artigo explica como definir parâmetros em Contas a pagar e Contas a receber para dar suporte a deduções de Imposto Deduzido na Origem (TDS).
author: kailiang
ms.date: 02/12/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: kfend
ms.custom: 15721
ms.assetid: b4b406fa-b772-44ec-8dd8-8eb818a921ef
ms.search.region: Global
ms.author: kailiang
ms.search.validFrom: 2021-02-12
ms.dyn365.ops.version: AX 10.0.17
ms.openlocfilehash: e547b92f9f7e0ccc5b92df4cd991ce402369b568
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/03/2022
ms.locfileid: "8883140"
---
# <a name="set-tds-parameters-in-accounts-payable-and-accounts-receivable"></a>Defina os parâmetros de TDS no Contas a pagar e no Contas a receber

[!include [banner](../includes/banner.md)]

Este artigo explica como definir parâmetros em Contas a pagar e Contas a receber para dar suporte a deduções de Imposto Deduzido na Origem (TDS).

1. Acesse **Imposto \> Configuração \> Parâmetros \> Parâmetros de contas a receber**.
2. Na guia **Atualizações**, selecione **Atualizar linhas da ordem** para abrir a caixa de diálogo **Atualizar linhas da ordem**.
3. Na seção **Grupo de TDS**, no campo **Atualizando grupo de TDS**, especifique o método a ser usado para atualizar o grupo de TDS no nível de linha. Esta configuração é usada quando o grupo de TDS é atualizado em um cabeçalho da ordem. As opções a seguir estão disponíveis:

    - **Nunca** – o grupo de TDS não é atualizado nas linhas da ordem quando é atualizado no cabeçalho da ordem.
    - **Sempre** – o grupo de TDS é atualizado automaticamente nas linhas da ordem quando é atualizado no cabeçalho da ordem.
    - **Avisar** – os usuários recebem uma mensagem que solicita que eles atualizem o grupo de TDS nas linhas da ordem.
4. Selecione **OK**.

    [![Caixa de diálogo Atualizar linhas da ordem.](./media/apac-ind-TDS-26.PNG)](./media/apac-ind-TDS-26.PNG)

5. Acesse **Imposto \> Configuração \> Parâmetros \> Parâmetros de contas a pagar**.
6. Na guia **Geral**, na FastTab **Divisão com base nas informações de entrega**, defina a opção **Recebimento de produtos** como **Sim** para lançar e dividir um recebimento de um produto com endereços de entrega e números de conta de impostos (TANS) diferentes. Se esta opção estiver definida como **Não**, não será possível lançar uma guia de remessa de compra que tenha endereços de entrega e TANS diferentes.
7. Defina a opção **Fatura** como **Sim** para lançar e dividir uma fatura de compra que tenha vários endereços de entrega e TANs.

    [![FastTab Divisão baseada nas informações de entrega.](./media/apac-ind-TDS-25.png)](./media/apac-ind-TDS-25.png)

8. Feche a página.
