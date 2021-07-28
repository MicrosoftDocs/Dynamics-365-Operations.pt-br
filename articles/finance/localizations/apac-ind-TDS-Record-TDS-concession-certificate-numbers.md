---
title: Registrar os números dos certificados de concessão de TDS
description: Este tópico explica como registrar os números de certificados de concessão do Imposto Deduzido na Origem (Tax Deducted at Source, TDS) que são emitidos para os fornecedores.
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
ms.openlocfilehash: 97fce25ea8c556f001c84f6836a0a270a9f3524f
ms.sourcegitcommit: c08a9d19eed1df03f32442ddb65a2adf1473d3b6
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/06/2021
ms.locfileid: "6358377"
---
# <a name="record-tds-concession-certificate-numbers"></a>Registrar os números dos certificados de concessão de TDS

[!include [banner](../includes/banner.md)]

Este tópico explica como registrar os números de certificados de concessão do Imposto Deduzido na Origem (Tax Deducted at Source, TDS) que são emitidos para os fornecedores.

1. Vá para **Imposto \> Impostos indiretos \> Imposto retido na fonte \> Concessões de imposto retido na fonte**.
2. No campo **Tipo de imposto**, selecione **TDS** para registrar os certificados de concessão para o tipo de imposto TDS.
3. Na guia **Visão geral**, selecione **Alt+N** para criar uma linha.

    [![Cabeçalho da nova linha.](./media/apac-ind-TDS-34.png)](./media/apac-ind-TDS-34.png)

4. No campo **Código do imposto retido na fonte**, selecione o código de imposto TDS para o qual os certificados de concessão do fornecedor são emitidos. O campo **Nome do código do imposto retido na fonte** mostra o nome do código do imposto TDS.
5. Nos campos **De** e **Até**, defina o período de validade para o certificado de concessão que usa o código de imposto TDS para calcular o TDS para o fornecedor como uma concessão.
6. No campo **Comentários**, insira qualquer comentário.
7. No campo **Seção**, insira o código da seção legal sob o qual o certificado de concessão TDS está disponível.

    Se o código de seção for 197, o valor "A" aparecerá na coluna "Motivo para não dedução/menor dedução" no Formulário 26Q e na coluna "Motivo para não dedução/menor dedução/extrapolação (se houver)" no Formulário 27Q. Se o código de seção for 197A, o valor "B" aparecerá em ambos os locais.

8. Selecione a FastTab **Certificado** para registrar os números dos certificados de concessão TDS para os fornecedores.
9. No campo **Conta de fornecedor**, selecione a conta do fornecedor para a qual o certificado de concessão TDS foi emitido.
10. Nos campos **De** e **Até**, defina o período de validade do certificado de concessão TDS.

    O cálculo do TDS como uma concessão é baseado no período em que o certificado é criado para o fornecedor.

11. No campo **Certificado**, insira o número do certificado de concessão TDS.

    [![FastTab Certificado.](./media/apac-ind-TDS-33.png)](./media/apac-ind-TDS-33.png)

12. Feche a página.
