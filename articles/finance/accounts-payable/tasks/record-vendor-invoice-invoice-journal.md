---
title: Registrar uma fatura de fornecedor no diário de faturas
description: Este guia de tarefa mostrará como registrar as notas fiscais de fornecedor que não estão associadas às ordens de compra.
author: abruer
manager: AnnBe
ms.date: 07/11/2019
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: VendInvoiceWorkspace, LedgerJournalTable, LedgerJournalTransVendInvoice
audience: Application User
ms.reviewer: roschlom
ms.search.region: Global
ms.author: abruer
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 18d8b74bd8783c23e548a3185414d1461bc1d869
ms.sourcegitcommit: 38d40c331c8894acb7b119c5073e3088b54776c1
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/15/2021
ms.locfileid: "4971819"
---
# <a name="record-a-vendor-invoice-in-the-invoice-journal"></a>Registrar uma fatura de fornecedor no diário de faturas

[!include [banner](../../includes/banner.md)]

Este guia de tarefa mostrará como registrar as notas fiscais de fornecedor que não estão associadas às ordens de compra. Exemplos deste tipo de nota fiscal incluem despesas de fornecimentos ou serviços.  Este registro usa a empresa de dados de demonstração USMF.

1. Vá para **Painel de navegação > Módulos > Contas a pagar > Espaços de trabalho > Entrada de fatura de fornecedor**.
2. No **Painel de ação**, clique em **Diário de nova fatura**.
3. Clique em **Novo**.
4. No campo **Nome**, insira o nome do diário ou clique no botão suspenso para abrir a pesquisa.
5. No campo **Descrição**, digite um valor.
6. No **Painel de ação**, clique em **Linhas**. No campo **Data**, insira a data de lançamento que atualizará a Contabilidade.  
7. No campo **Conta**, especifique a **Conta do fornecedor**.
8. No campo **Fatura**, insira o número da fatura.
9. No campo **Descrição**, digite um valor.
10. No campo **Crédito**, insira um número.
11. No campo **Contrapartida**, insira o número da conta ou clique no botão suspenso para abrir a pesquisa
    * O **Grupo de impostos** terá o padrão retirado da conta do fornecedor.  
    * O **Grupo de impostos do item** terá o padrão retirado da conta principal especificada no campo **Contrapartida**.  
    * A **Data de vencimento** será calculada com base nos Termos de pagamento.  
    * O **Desconto à vista** terá o padrão retirado da Conta do fornecedor.
12. Se você tiver habilitado o fluxo de trabalho Diário de fatura de fornecedor, clique em **Fluxo de trabalho > Enviar**.
    * Quando o envio for aprovado, a data será adiantada para o primeiro dia do próximo período aberto, se a data de lançamento da transação cair em um período que esteja Em retenção ou Fechado para lançamento contábil.
12. Clique em **Enviar**.
13. Feche a página.

