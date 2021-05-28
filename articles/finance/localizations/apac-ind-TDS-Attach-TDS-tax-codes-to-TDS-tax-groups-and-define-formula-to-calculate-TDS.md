---
title: Anexar os códigos de imposto TDS aos grupos de impostos TDS e definir a fórmula para calcular o TDS
description: Este tópico explica como configurar grupos de impostos TDS (Imposto Deduzido na Fonte) e anexar códigos de imposto TDS aos grupos de impostos TDS. Para calcular o TDS para um grupo de impostos TDS, você deve definir a fórmula para os códigos de impostos TDS que estão anexados a ele.
author: kailiang
ms.date: 02/12/2021
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: roschlom
ms.custom: 15721
ms.assetid: b4b406fa-b772-44ec-8dd8-8eb818a921ef
ms.search.region: Global
ms.author: kailiang
ms.search.validFrom: 2021-02-12
ms.dyn365.ops.version: AX 10.0.17
ms.openlocfilehash: ec0d683153bd5ab731035159d32881fbdb352d70
ms.sourcegitcommit: 08ce2a9ca1f02064beabfb9b228717d39882164b
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/11/2021
ms.locfileid: "6023037"
---
# <a name="attach-tds-tax-codes-to-tds-tax-groups-and-define-the-formula-for-calculating-tds"></a>Anexar os códigos de imposto TDS aos grupos de impostos TDS e definir a fórmula para calcular o TDS

[!include [banner](../includes/banner.md)]

Este tópico explica como configurar grupos de impostos TDS (Imposto Deduzido na Fonte) e anexar códigos de imposto TDS aos grupos de impostos TDS. Para calcular o TDS para um grupo de impostos TDS, você deve definir a fórmula para os códigos de impostos TDS que estão anexados a ele.

Siga estas etapas para configurar um grupo de impostos TDS, anexar códigos de impostos TDS a ele e definir a fórmula para calcular o TDS.

1. Acesse **Imposto \> Impostos indiretos \> Imposto retido na fonte \> Grupos de impostos retidos na fonte**.

    [![Página Grupos de impostos retidos na fonte](./media/apac-ind-TDS-29.png)](./media/apac-ind-TDS-29.png)

2. No Painel de Ações, selecione **Novo** para criar um grupo de imposto retido na fonte para TDS e insira os detalhes necessários.
3. No campo **Tipo de imposto**, selecione **TDS**.
4. Na Guia Rápida **Configuração**, selecione **Adicionar** para criar uma linha.
5. No campo **Código de imposto retido na fonte**, selecione o código de imposto TDS para o grupo de impostos TDS. O campo **Nome do imposto retido na fonte** mostra o nome do código de imposto TDS e o campo **Valor** mostra o valor.
6. Para ignorar o limite e o limite de exceção definidos para o componente de imposto TDS anexado ao código de imposto TDS em transações TDS, marque a caixa de seleção **Esquecer limite**.
7. Para evitar que o grupo de impostos seja calculado nas transações, marque a caixa de seleção **Isento**.
8. No Painel de Ações, selecione **Designer** para abrir o designer de fórmulas, para que você possa definir a fórmula para calcular o TDS para o grupo de imposto TDS. Na página **Designer**, a guia **Impostos** mostra os códigos de imposto TDS que foram selecionados para o grupo de imposto TDS.

    [![Página Designer](./media/apac-ind-TDS-30.png)](./media/apac-ind-TDS-30.png)

9. Na guia **Cálculo**, selecione **Alt+N** para criar uma linha. O campo **ID** mostra a ID de prioridade gerada automaticamente para o cálculo de TDS.
10. No campo **Código do imposto**, selecione o código de imposto TDS para o qual definir a fórmula. Todos os códigos de imposto TDS que foram selecionados para o grupo de imposto TDS estão disponíveis para seleção neste campo.
11. No campo **Base de tributação**, selecione a base para o cálculo do TDS:

    - **Valor bruto** – Calcule o TDS com base no valor bruto da transação (ou seja, o valor da fatura) usando a expressão de cálculo definida para o código de imposto.
    - **Valor bruto excluído** – Calcule o TDS com base na expressão de cálculo definida para o código de imposto.

    > [!NOTE]
    > O campo **Base de tributação** não pode ser definido como **Valor bruto excluído** para o código de imposto TDS que tem uma ID de prioridade **1**.

12. O cálculo do TDS é baseado na fórmula definida no campo **Expressão de cálculo** para cada código de imposto anexado ao grupo de imposto TDS. Selecione o sinal de mais (**+**), sinal de menos (**-**), sinal de multiplicação (**\**_) ou sinal de divisão (_*/**) para inserir a expressão de cálculo para o código de imposto TDS selecionado no campo **Expressão de cálculo**.

    > [!NOTE]
    > Nenhuma expressão de cálculo pode ser definida para o código de imposto TDS que tem uma ID de prioridade de **1**.

13. Para definir a expressão de cálculo para o código de imposto TDS no campo **Expressão de cálculo**, adicione os códigos de imposto TDS que estão disponíveis na guia **Impostos**. Para adicionar códigos de imposto TDS no campo **Expressão de cálculo**, você pode usar qualquer um dos seguintes métodos:

    - Arraste o código de imposto necessário da guia **Impostos** para o campo **Expressão de cálculo**.
    - Toque duas vezes (ou clique duas vezes) no código de imposto necessário na guia **Impostos**.
    - Selecione e mantenha pressionado (ou clique com o botão direito) o código de imposto necessário na guia **Impostos** e, em seguida, selecione **Adicionar código de imposto**.

    > [!NOTE]
    > Insira uma expressão de cálculo antes de cada código de imposto TDS. Os códigos de imposto TDS que foram adicionados à expressão de cálculo aparecem entre colchetes (\[...\]).

14. Para limpar a expressão de cálculo definida para um código de imposto no campo **Expressão de cálculo**, selecione o botão **C**.
15. Para excluir um registro na guia **Cálculo**, selecione **Excluir**.
16. Feche a página.
