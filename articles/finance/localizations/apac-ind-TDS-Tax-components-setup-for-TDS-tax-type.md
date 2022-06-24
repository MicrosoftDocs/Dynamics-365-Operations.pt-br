---
title: Configurar os componentes de imposto para o tipo de imposto TDS
description: Este artigo explica como configurar os componentes do imposto retido na fonte para o tipo de Imposto Deduzido na Origem (TDS). Também explica como definir o limite que é usado para calcular o TDS para cada componente do TDS.
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
ms.openlocfilehash: df2eb10ce9e372bb1e984f6ae1a2e889bbd90ad0
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/03/2022
ms.locfileid: "8871147"
---
# <a name="set-up-tax-components-for-the-tds-tax-type"></a>Configurar os componentes de imposto para o tipo de imposto TDS

[!include [banner](../includes/banner.md)]

Este artigo explica como configurar os componentes do imposto retido na fonte para o tipo de Imposto Deduzido na Origem (TDS). Os componentes do TDS são TDS, sobretaxa, PE-Cess e SHE Cess. Este artigo também explica como definir o limite usado para calcular o TDS para cada componente do TDS. Além disso, você pode definir um limite de exceção que é usado para calcular o TDS para cada componente do TDS.

Siga estas etapas para configurar os componentes do TDS.

1. Acesse **Imposto \> Configuração \> Imposto retido na fonte \> Componentes de imposto retido na fonte**.

    [![Página Componentes de imposto retido na fonte.](./media/apac-ind-TDS-9.png)](./media/apac-ind-TDS-9.png)

2. No campo **Tipo de imposto**, selecione **TDS** para configurar componentes de imposto retido na fonte para o tipo de imposto TDS.
3. No Painel de Ações, selecione **Novo** para criar uma linha.
4. No campo **Componente do imposto retido na fonte**, insira um nome para o componente do TDS.
5. No campo **Grupo de componentes do imposto retido na fonte**, selecione o grupo de componente de imposto retido na fonte de TDS ao qual anexar o componente do TDS.
6. Na FastTab **Geral**, no campo **Descrição**, insira uma descrição do componente do TDS.
7. No Painel de Ações, selecione **Limite** para abrir a página **Limite**, para que você possa definir o limite que é usado para calcular o TDS para o componente do TDS.
8. Use os campos **Data inicial** e **Data final** para definir o período ao qual o limite é aplicável.
9. Na FastTab **Geral**, no campo **Limite**, insira o valor limite que é usado para calcular o TDS para o componente do TDS. O imposto será deduzido na fonte somente quando o valor cumulativo da fatura ultrapassar o limite.

    Por exemplo, se o valor limite for 10.000, o TDS será calculado depois que o valor cumulativo da fatura exceder 10.000 (em outras palavras, quando for 10.001 ou mais).

10. No campo **Limite de exceção**, insira o valor do limite de exceção que é usado para calcular o TDS para o componente do TDS. O imposto em uma linha da fatura será deduzido na fonte somente quando o valor ultrapassar o limite de exceção.

    Por exemplo, se o valor do limite de exceção for 5.000, o TDS será calculado em uma linha de fatura específica se o valor da linha da fatura exceder 5.000 (em outras palavras, se for 5.001 ou mais).

    [![Página Limite.](./media/apac-ind-TDS-10.png)](./media/apac-ind-TDS-10.png)

    > [!NOTE]
    > O valor do limite de exceção deve ser menor ou igual ao valor do limite.
    >
    > O imposto é deduzido para uma transação se o valor da transação ultrapassar o limite de exceção, mesmo se o valor da fatura cumulativa não ultrapassar o limite especificado no campo **Limite**.

11. Feche a página **Limite** para retornar à página **Componentes de imposto retido na fonte**.
12. No Painel de Ações, selecione **Copiar** para abrir a caixa de diálogo **Copiar componentes de imposto retido na fonte**, para que você possa copiar os componentes do TDS que foram configurados para um grupo de componentes do TDS para outro grupo de componentes do TDS.
13. No campo **De**, selecione o grupo de componentes do TDS do qual copiar os componentes do TDS. No campo **Até**, selecione o grupo de componentes de imposto retido na fonte para o qual copiar os componentes do TDS.

    > [!NOTE]
    > Os componentes do TDS comuns que estão anexados a ambos os grupos de componentes do TDS não são copiados.

14. Selecione **OK** para copiar e criar componentes do TDS para o outro grupo de componentes do TDS na página **Componentes de imposto retido na fonte**.

    [![Caixa de diálogo Copiar componentes de imposto retido na fonte.](./media/apac-ind-TDS-11.png)](./media/apac-ind-TDS-11.png)

15. Feche a página.
