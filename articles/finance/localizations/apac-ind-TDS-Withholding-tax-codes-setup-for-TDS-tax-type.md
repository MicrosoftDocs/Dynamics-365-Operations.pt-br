---
title: Configurar códigos de impostos retidos na fonte para o tipo de imposto TDS
description: Este artigo explica como configurar códigos de impostos para Imposto Deduzido na Origem (TDS).
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
ms.openlocfilehash: fabe14b74c445434c37cb6ee79597d37affb162d
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/03/2022
ms.locfileid: "8904373"
---
# <a name="set-up-withholding-tax-codes-for-the-tds-tax-type"></a>Configurar códigos de impostos retidos na fonte para o tipo de imposto TDS

[!include [banner](../includes/banner.md)]

Este artigo explica como configurar códigos de impostos para Imposto Deduzido na Origem (TDS).

1. Acesse **Imposto \> Impostos indiretos \> Imposto retido na fonte \> Códigos de impostos retidos na fonte**.

    [![Página Códigos de impostos retidos na fonte.](./media/apac-ind-TDS-17.png)](./media/apac-ind-TDS-17.png)

2. No Painel de Ações, selecione **Novo** para criar um código de imposto retido na fonte para TDS e insira os detalhes necessários.
3. Na FastTab **Geral**, no campo **Tipo de imposto**, selecione **TDS** para categorizar o código de imposto como um código de imposto TDS.
4. No campo **Período de liquidação**, selecione o período de liquidação de TDS para o código do imposto TDS.
5. No campo **Conta principal**, selecione a conta contábil na qual o valor de TDS deve ser lançado.
6. No campo **Conta a receber**, selecione a conta a receber para a qual o valor TDS deduzido nas transações de vendas deve ser lançado.

    O campo **Origem** é definido automaticamente como **Porcentagem do valor bruto** e o valor não pode ser alterado.

    > [!NOTE]
    > Não é possível definir a origem para a **Porcentagem do valor líquido** dos códigos de imposto do tipo de imposto TDS.

7. No campo **Componente do imposto retido na fonte**, selecione o componente do imposto TDS para o código do imposto de TDS.
8. No Painel de Ações, selecione **Valores** para abrir a página **Valores da retenção de imposto**.
9. No campo **Data inicial**, informe a data inicial para o valor de TDS. No campo **Data final**, informe a data final.

    > [!NOTE]
    > Os campos **Limite mínimo**, **Limite superior** e **Excluir %** não estão disponíveis para códigos de imposto do tipo de imposto TDS.

10. No campo **Valor**, insira a porcentagem de TDS para o código do imposto TDS.
11. Feche a página **Valores da retenção de imposto** para retornar à página **Códigos de imposto retido na fonte**.

    > [!NOTE]
    > O botão **Limites** na página **Códigos de impostos retidos na fonte** não está disponível para códigos de imposto do tipo de imposto TDS.

12. Feche a página.
