---
title: Transação da carta de garantia
description: Este procedimento mostra o processo de Carta de garantia.
author: kweekley
ms.date: 11/15/2022
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: Reasons, SalesTableListPage, SalesCreateOrder, SalesTable, BankLGRequestForm, BankLGRequestFormRequest, BankLGGuarantee, BankLGFormSubmitToBank, BankDocumentAgreementLineLookup, BankLGFormReceiveFromBank, LedgerJournalTable, LedgerJournalTransDaily, BankLGRequestFormGiveToBeneficiary, BankLGFormGiveToBeneficiary, BankLGRequestFormIncreaseValue, BankLGFormIncreaseValue, BankLGRequestFormLiquidate, BankLGFormLiquidate
audience: Application User
ms.reviewer: twheeloc
ms.search.region: Global
ms.author: kweekley
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 786aecf69bae3d07ac80a55b4dc835dd8129bd59
ms.sourcegitcommit: 81bb8e51951395be3f18f45212e47e6c41656f6a
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/23/2022
ms.locfileid: "9803955"
---
# <a name="letter-of-guarantee-transaction"></a>Transação da carta de garantia

[!include [banner](../../includes/banner.md)]

Este procedimento mostra o processo de Carta de garantia.



As tarefas a seguir devem ser concluídas antes de concluir este procedimento:

- Configurar recursos bancários e perfis de lançamento para uma carta de garantia.

- Criar um contrato de recursos bancários para uma carta de garantia.



Este procedimento usa a empresa de dados de demonstração USMF.


## <a name="create-sales-order-with-letter-of-guarantee"></a>Criar Ordem de venda com a Carta de garantia
1. Acesse **Contas a receber > Ordens > Todas as ordens de venda**.
2. Clique em **Novo**.
3. No campo **Conta de cliente**, insira ou selecione um valor.
4. Expanda a seção **Geral**.
5. No campo **Local**, insira ou selecione um valor.
6. Na lista, clique no link na linha selecionada.
7. No campo **Depósito**, insira ou selecione um valor.
8. Na lista, clique no link na linha selecionada.
9. No campo **Tipo de documento bancário**, selecione **Carta de garantia**.
10. Clique em **OK**.
11. No campo **Número do item**, insira ou selecione um valor.
12. No campo **Preço unitário**, insira um número.
13. Expanda a seção **Detalhes da linha**.
14. Clique na guia **Entrega**.

>[!Note] 
>Selecione **Controle da data de entrega** = **Nenhum**  

15. No campo **Data de remessa solicitada**, insira uma data.
16. No campo **Data de remessa confirmada**, insira uma data.

## <a name="process-letter-of-guarantee_request"></a>Processar carta de garantia_Solicitar
1. No Painel de Ação, clique em **Gerenciar**.
2. Clique em **Carta de garantia**.
3. No Painel de Ação, clique em **Carta de garantia**.
4. Clique em **Solicitar** para abrir a caixa de diálogo suspensa.
5. No campo **Tipo**, insira ou selecione um valor.
6. Na lista, clique no link na linha selecionada.
7. No campo **Valor**, insira um número.
8. No campo **Data de vencimento**, insira uma data e hora.
9. Clique em **OK**.
10. Feche a página.

## <a name="process-letter-of-guarantee_submit-to-bank"></a>Processar carta de garantia ao banco_Enviar ao banco
1. Vá para **Gerenciamento de caixa e bancos > Cartas de garantia >Cartas de garantia**.
2. Na lista, localize e selecione o PDV desejado.
3. Clique em **Enviar ao banco** para abrir a caixa de diálogo suspensa.
4. No campo **Conta bancária**, insira ou selecione um valor.
5. Na lista, clique no link na linha selecionada.
6. Clique em **OK**.

## <a name="process-letter-of-guarantee_receive-from-bank"></a>Processar carta de garantia_Receber do banco
1. Clique em **Receber do banco** para abrir a caixa de diálogo suspensa.
2. Insira um valor no campo **Número do banco**.
    * Verifique os valores nos campos **Margem** e **Despesa**.  
3. Clique em **OK**.
4. Expanda a seção **Ações**.
    * Verifique o registro 'Receber do banco'.  
5. Clique para seguir o link no campo **Número do lote do diário**.
6. Clique em **Linhas**.
    * Verifique o lançamento de entradas de diário.  
7. Feche a página.

## <a name="process-letter-of-guarantee_give-to-beneficiary"></a>Processar carta de garantia_Conceder ao beneficiário
1. Acesse **Contas a receber > Ordens > Todas as ordens de venda**.
2. Na lista, clique no link na linha selecionada.
3. No Painel de Ação, clique em **Gerenciar**.
4. Clique em **Carta de garantia**.
5. No Painel de Ação, clique em **Carta de garantia**.
6. Clique em **Conceder ao beneficiário** para abrir a caixa de diálogo suspensa.
7. Clique em **OK**.
8. Vá para **Gerenciamento de caixa e bancos > Cartas de garantia >Cartas de garantia**.
9. Na lista, localize e selecione o PDV desejado.
10. Clique em **Conceder ao beneficiário** para abrir a caixa de diálogo suspensa.
11. Clique em **OK**.
12. Expanda a seção **Ações**.
    * Valide o registro 'Conceder ao beneficiário'.  

## <a name="process-letter-of-guarantee_increase-value"></a>Processar carta de garantia_Aumentar valor
1. Acesse **Contas a receber > Ordens > Todas as ordens de venda**.
2. Na lista, clique no link na linha selecionada.
3. No Painel de Ação, clique em **Gerenciar**.
4. Clique em **Carta de garantia**.
5. No Painel de Ação, clique em **Carta de garantia**.
6. Clique em **Aumentar valor** para abrir a caixa de diálogo suspensa.
7. No campo **Valor a ser adicionado**, insira um número.
8. Clique em **OK**.
9. Vá para **Gerenciamento de caixa e bancos > Cartas de garantia >Cartas de garantia**.
10. Na lista, localize e selecione o PDV desejado.
11. Clique em **Aumentar valor** para abrir a caixa de diálogo suspensa.
12. Clique em **OK**.
13. Expanda a seção **Ações**.
    * Verifique o registro 'Aumentar valor'.  
14. Na lista, localize e selecione o PDV desejado.
15. Clique para seguir o link no campo **Número do lote do diário**.
16. Clique em **Linhas**.
    * Verifique as entradas de diário lançadas.  

## <a name="process-letter-of-guarantee_liquidate"></a>Processar carta de garantia_Liquidar
1. Acesse **Contas a receber > Ordens > Todas as ordens de venda**.
2. Na lista, clique no link na linha selecionada.
3. No Painel de Ação, clique em **Gerenciar**.
4. Clique em **Carta de garantia**.
5. No Painel de Ação, clique em **Carta de garantia**.
6. Clique em **Liquidar** para abrir a caixa de diálogo suspensa.
7. Clique em **OK**.
8. Vá para **Gerenciamento de caixa e bancos > Cartas de garantia >Cartas de garantia**.
9. Na lista, localize e selecione o PDV desejado.
10. Clique em **Liquidar** para abrir a caixa de diálogo suspensa.
11. Clique em **OK**.
12. Expanda a seção **Ações**.
    * Verifique o registro 'Liquidar'.  
13. Na lista, localize e selecione o PDV desejado.
14. Clique para seguir o link no campo **Número do lote do diário**.
15. Clique em **Linhas**.
    * Verifique as entradas de diário lançadas.  
16. Feche a página.



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]
