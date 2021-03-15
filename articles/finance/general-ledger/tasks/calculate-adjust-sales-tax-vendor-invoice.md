---
title: Calcular e ajustar imposto na fatura de fornecedor
description: Este tópico explica como ajustar impostos em uma fatura de fornecedor no Dynamics 365 Finance.
author: twheeloc
manager: AnnBe
ms.date: 07/31/2019
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: LedgerJournalTable, LedgerJournalTransVendInvoice, VendTableLookup, TaxTmpWorkTrans
audience: Application User
ms.reviewer: roschlom
ms.search.region: Global
ms.author: roschlom
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 2536e87953267eae13cf3b42c2bd5476fc647c22
ms.sourcegitcommit: 38d40c331c8894acb7b119c5073e3088b54776c1
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/15/2021
ms.locfileid: "4994706"
---
# <a name="calculate-and-adjust-sales-tax-on-a-vendor-invoice"></a>Calcular e ajustar imposto na fatura de fornecedor

[!include [banner](../../includes/banner.md)]

Este tópico explica como ajustar impostos em uma fatura de fornecedor. Se o documento de origem exibir valores de imposto diferentes como calculados, você pode ajustar os valores antes do lançamento. Esta tarefa usa a empresa de demonstração DEMF.

1. No painel de navegação, vá para **Módulos > Contas a pagar > Faturas > Diário de faturas**.
2. Selecione **Novo**.
3. No campo **Nome** da nova linha, selecione uma opção no menu suspenso.
4. No Painel de Ações, selecione **Linhas**.
5. No campo **Conta**, especifique os valores desejados.
6. No campo **Fatura**, digite um valor.
7. No campo **Crédito**, insira um número.
8. No campo **Contrapartida**, especifique os valores desejados.
9. Selecione **Imposto**.
10. No campo **Valor total do imposto real**, insira um número.
11. Na guia **Ajuste**, os valores de impostos podem ser ajustados por código de imposto.
12. Selecione **Redefinir valor real a partir de valores calculados**.
13. Selecione **OK**.
14. Selecione **Salvar**.



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]