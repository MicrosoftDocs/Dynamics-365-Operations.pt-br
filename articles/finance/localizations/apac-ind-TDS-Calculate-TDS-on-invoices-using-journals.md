---
title: Calcular TDS em faturas usando diários
description: Este tópico lista as etapas para calcular o Imposto Deduzido na Origem (TDS) nos diários.
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
ms.openlocfilehash: cfe473f39ee729957924fd7c161aed01138cd507eea56766af35177891676f65
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/05/2021
ms.locfileid: "6778884"
---
# <a name="calculate-tds-on-invoices-using-journals"></a>Calcular TDS em faturas usando diários

[!include [banner](../includes/banner.md)]

Este tópico lista as etapas para calcular o Imposto Deduzido na Origem (TDS) nos diários.

Comece abrindo a página **Diários gerais** (**Contabilidade > Entradas de diário > Diários gerais**).

[![Diários Gerais.](./media/apac-ind-TDS-57.png)](./media/apac-ind-TDS-57.png)

1. Crie linhas de diário usando os formulários de diário listados na tabela. Selecione o tipo de conta e o tipo de contrapartida e insira o valor da transação. 

   > [!NOTE]
   > Na página **Diário de aprovações de fatura**, selecione **Localizar comprovantes** e selecione as faturas para calcular o TDS. Exiba as faturas criadas na página **Registro de fatura** ou na página **Localizar comprovantes**.  

2. Na guia **Geral** da página **Comprovante de diário**, exiba ou modifique o grupo do TDS padrão definido para o fornecedor ou cliente, no campo **Grupo de TDS**. O valor de TDS que é calculado nas linhas do diário é baseado na fórmula definida para os códigos de imposto TDS listados no campo **Grupo de TDS**. 

   > [!NOTE]
   > O campo **Grupo de impostos retidos na fonte** e o campo **Grupo de TCS** tornam-se indisponíveis quando você seleciona um grupo de TDS no campo **Grupo de TDS**. O campo **Grupo de impostos retidos na fonte** está disponível apenas na página **Diário geral**. O TDS é calculado apenas se a caixa de seleção **Calcular imposto retido na fonte** estiver marcada para o fornecedor ou cliente nas páginas **Todos os fornecedores** ou **Todos os clientes**.   

3. Selecione a guia **Informações sobre impostos**. Selecione os endereços alternativos de uma empresa configurada para a empresa neste campo, se necessário. Você pode ver o nome da empresa no campo **Nome**, que está no grupo do campo **Informações sobre a empresa**. 

4. Exiba a categoria da natureza do avaliado do fornecedor ou cliente no campo **Natureza do avaliado**, que está no grupo de campos **Imposto retido na fonte**. No campo **Número da Conta de Imposto** (**TAN**), exiba o TAN do nome da empresa selecionada que é exibido.  

5. Selecione **Imposto retido na fonte** no menu **Imposto retido na fonte** para abrir a página **Transações de retenção temporária de impostos**. Os seguintes campos são exibidos no painel superior da página **Transações de retenção temporária de impostos**.

   - **Valor do imposto retido na fonte no total** - O TDS total calculado para a transação do grupo de TDS.

   - **Valor** - A porcentagem total usada para calcular o TDS para a transação. A porcentagem total é baseada na fórmula definida para os códigos de imposto TDS anexados ao grupo de TDS.

   - **Valor do imposto retido na fonte ajustado no total** - O valor total de TDS ajustado para todos os códigos de imposto no grupo de TDS.

   - **TDS** - Se selecionado, um grupo de TDS é anexado à transação.

  Os campos nas guias **Visão geral**, **Geral** e **Ajuste** na página **Transações de retenção temporária de impostos** exibem o valor do TDS calculado e os detalhes do valor do TDS ajustado para cada código de imposto TDS anexado ao grupo de TDS.

6. Selecione **Limite** para abrir a página **Limite**. Exiba o limite e o limite de exceção definidos para o componente de imposto TDS anexado a um código de imposto TDS específico nesta página.

   Selecione **Designer de fórmulas** para abrir o formulário **Designer de fórmulas**. Exiba a fórmula definida para um código de imposto TDS específico nesta página. Feche as páginas **Designer de fórmula** e **Transações de imposto retido na fonte temporárias** para retornar à página **Comprovante de diário**.

8. Insira os outros detalhes necessários. Valide e lance o diário. O valor do TDS que é calculado nas faturas de compra é lançado na conta a pagar. O valor do TDS que é calculado nas faturas de vendas é lançado na conta a receber definida para cada código de imposto de TDS no grupo de TDS. As contas a pagar ou contas a receber para códigos de imposto TDS são definidas na página **Códigos de impostos retidos na fonte**.

9. Selecione **Imposto retido na fonte lançado** para abrir a página **Transações** **de retenção** **de imposto**. No campo **Valor**, a porcentagem total usada para calcular o TDS para a transação é exibida.

   Os campos nas guias **Visão geral**, **Geral** e **Valor** na página de transações de imposto retido na fonte exibem o valor do TDS calculado e os detalhes do valor do TDS ajustado para cada código de imposto TDS anexado ao grupo de TDS.
