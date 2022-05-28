---
title: Configurar autoridades de imposto retido na fonte para os tipos de imposto TDS
description: Este tópico explica como configurar autoridades de Imposto Deduzido na Origem (TDS).
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
ms.openlocfilehash: a6c802079153911f74a217eb67ff6743aebdcd33
ms.sourcegitcommit: 631d2cea52590af15f208e9af584446e85540fcf
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/07/2022
ms.locfileid: "8724548"
---
# <a name="set-up-withholding-tax-authorities-for-the-tds-tax-type"></a>Configurar autoridades de imposto retido na fonte para os tipos de imposto TDS

[!include [banner](../includes/banner.md)]

Este tópico explica como configurar autoridades de Imposto Deduzido na Origem (TDS).

1. Acesse **Imposto \> Impostos indiretos \> Autoridades de imposto retido na fonte**.

    [![Página Autoridades de imposto retido na fonte.](./media/apac-ind-TDS-12.png)](./media/apac-ind-TDS-12.png)

2. No campo **Tipo de imposto**, selecione **TDS** para configurar autoridades de imposto retido na fonte para o tipo de imposto TDS.
3. No Painel de Ações, selecione **Novo** para criar uma linha.
4. No campo **Autoridade do imposto retido na fonte**, informe o nome da autoridade TDS.
5. No campo **Descrição**, insira uma descrição.
6. Na FastTab **Geral**, no campo **Conta do fornecedor**, selecione a conta do fornecedor para a autoridade de TDS.

    > [!NOTE]
    > Você deve definir o nome do banco em que os fundos devidos ao fornecedor da autoridade de TDS serão depositados. O nome do banco é definido na página **Contas bancárias** (**Contas a pagar \> Todos os fornecedores \> Fornecedor \> Configurar \> Contas bancárias**).

7. Feche a página.
