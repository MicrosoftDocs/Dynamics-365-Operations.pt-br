---
title: " Cancelar notas fiscais do fornecedor"
description: Este tópico fornece informações sobre como cancelar uma nota fiscal do fornecedor para o Brasil.
author: ShylaThompson
manager: AnnBe
ms.date: 06/05/2018
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
audience: Application User
ms.reviewer: kfend
ms.search.region: Brazil
ms.author: roschlom
ms.search.validFrom: 2017-12-31
ms.dyn365.ops.version: 7.2999999999999998
ms.openlocfilehash: 162f8310685e0ef1f67e14a20e207d15e8e8527c
ms.sourcegitcommit: 38d40c331c8894acb7b119c5073e3088b54776c1
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/15/2021
ms.locfileid: "4962591"
---
# <a name="cancel-vendor-fiscal-documents"></a> Cancelar notas fiscais do fornecedor
[!include [banner](../includes/banner.md)]

Você pode cancelar as notas fiscais incorretas de fornecedor que uma entidade legal gera e emite para fornecedores que não são contribuintes. Ao cancelar uma nova fiscal incorreta de fornecedor, uma ordem de compra negativa é criada. Quando você lança uma ordem de compra negativa e executa o processo de integração do livro fiscal, todas as transações financeiras, contábeis e de imposto relacionadas à ordem de compra são revertidas nos livros fiscais.

1. Selecione **Contas a pagar** \> **Comum** \> **Ordens de compra** \> **Todas as ordens de compra**.
2. Selecione uma ordem de compra que tenha um tipo de compra de **Ordem devolvida** e um status de aprovação **Aprovado** ou **Confirmado**.
3. No Painel Ação, na guia **Compra**, selecione **Cancelar nota fiscal** para abrir a página **Cancelar nota fiscal**.
4. No Microsoft Dynamics AX 2012 R3 e na atualização cumulativa 6 ou posterior para Microsoft Dynamics AX 2012 R2: no campo **Código de motivo**, selecione o código de identificação do motivo para cancelar a nota fiscal de fornecedor.
5. No AX 2012 R3 e na atualização cumulativa 6 ou posterior do AX 2012 R2: no campo **Comentário do motivo**, insira ou atualize o motivo para cancelar a nota fiscal do fornecedor.

    > [!NOTE]
    > O motivo para o cancelamento deve ter no mínimo 15 caracteres.

6. Selecionar as faturas do fornecedor a serem canceladas.
7. Selecione **OK** para criar ordens de compra negativas para as faturas de fornecedor selecionadas.
8. No **Painel de Ação**, selecione **Fatura** \> **Fatura**.
9. Na página **Fatura de fornecedor**, selecione **Lançar** \> **Lançar** para lançar a fatura.

## <a name="see-also"></a>Consulte também

[Cancelar uma nota fiscal complementar de compra](https://github.com/MicrosoftDocs/DynamicsAX2012-technet/blob/master/dynamicsax2012-technet/bra-cancel-a-purchase-complementary-fiscal-document.md)

[Cancelar uma nota fiscal de cliente](https://github.com/MicrosoftDocs/Dynamics-365-Operations/blob/bra-cancel-cus-fis-doc/articles/financials/localizations/latam-bra-cancel-customer-fiscal-documents.md)
