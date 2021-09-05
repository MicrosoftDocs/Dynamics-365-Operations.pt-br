---
title: Registrar números de certificados recuperáveis de TDS
description: Este tópico explica como usar a página Certificados recuperáveis para registrar os números e datas dos certificados de Imposto Deduzido na Origem (TDS) recebidos de um fornecedor, cliente ou razão específico.
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
ms.openlocfilehash: bc92a1321e6b2fe44bf7967c2aa1ad21dc353a03
ms.sourcegitcommit: dca3279a8b7cd5d0bcd4e4a3aa9938b337aa8849
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/19/2021
ms.locfileid: "7402439"
---
# <a name="record-tds-recoverable-certificate-numbers"></a>Registrar números de certificados recuperáveis de TDS

[!include [banner](../includes/banner.md)]

Este tópico explica como usar a página **Certificados recuperáveis** para registrar os números e datas dos certificados de Imposto Deduzido na Origem (TDS) recebidos de um fornecedor, cliente ou razão específico. Para atualizar os números e datas dos certificados do TDS que são registrados para transações TDS nesta página, use a página **Atualizar certificado** (**Contabilidade \> Periódico \> Imposto retido na fonte \> Atualizar certificado**). Depois de terminar de atualizar os números dos certificados do TDS, feche-os.

Siga estas etapas para registrar os números e datas dos certificados do TDS.

1. Acesse **Imposto \> Imposto indireto \> Imposto retido na fonte \> Certificados recuperáveis**.

    [![Página Certificados recuperáveis.](./media/apac-ind-TDS-49.png)](./media/apac-ind-TDS-49.png) 

2. Na página **Certificados recuperáveis**, no campo **Tipo de imposto**, selecione **TDS**.
3. Selecione **Novo** para criar um registro.
4. No campo **Número do certificado**, insira o número do certificado do TDS.
5. No campo **Tipo de conta**, selecione o tipo de conta para a qual o certificado do TDS é recebido: **Fornecedor**, **Cliente** ou **Razão**.
6. No campo **Conta**, selecione o fornecedor, cliente ou número da conta contábil, dependendo do tipo de conta que você selecionou. O campo **Nome** mostra o nome do fornecedor, cliente ou conta contábil.
7. No campo **Valor do certificado**, insira o valor do certificado do TDS.
8. No campo **Data**, insira a data do certificado para o número do certificado.
9. Selecione **Consultas** para abrir a página **Transações de certificado**, em que você pode exibir as transações do TDS para as quais o número e a data do certificado do TDS foram atualizados. Essas informações podem ser atualizadas na página **Atualizar certificado** (**Imposto \> Declarações \> Imposto retido na fonte \> Atualizar certificado**).

    A página **Atualizar certificado** mostra as seguintes informações para cada transação TDS:

    - **Data** – A data de lançamento da transação TDS.
    - **Comprovante** – O número do comprovante da transação de TDS.
    - **Origem** – O módulo em que a transação TDS foi criada.
    - **Conta** – O fornecedor, cliente ou número da conta contábil para o qual a transação TDS foi criada.
    - **Nome** – O nome do fornecedor, cliente ou conta contábil para o qual a transação TDS foi criada.
    - **Valor** – O valor da fatura sobre o qual o TDS foi calculado.
    - **Valor do imposto** – O valor do imposto TDS calculado para a transação.
    - **Data do certificado** – A data do certificado do TDS que foi atualizado para a transação TDS.
    - **Número do certificado** – Número do certificado TDS que foi atualizado para a transação TDS.

10. Na página **Certificados recuperáveis**, marque a caixa de seleção **Fechado** para fechar o número do certificado do TDS após terminar de atualizá-lo para transações TDS na página **Atualizar certificado**.

    Para marcar a caixa de seleção **Fechado** de todos os registros da página, selecione **Marcar todos**.

    > [!NOTE]
    > Os números do certificado do TDS para os quais a caixa de seleção **Fechado** está marcada não estão disponíveis na página **Atualizar certificado**.
