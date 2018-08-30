--- 
title: Definir mapeamentos do modelo de ER e selecionar fontes de dados para eles
description: "As etapas a seguir explicam como um usuário no papel de Administrador do Sistema ou Desenvolvedor de Relatório Eletrônico pode selecionar fontes de dados para um modelo de dados do Relatório eletrônico (RE)."
author: NickSelin
manager: AnnBe
ms.date: 01/16/2017
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: kfend
ms.search.scope: Operations
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: e782d33f3748524491dace28008cd9148ae70529
ms.openlocfilehash: 2beda3555274fee3f17ad13c54c6823307216385
ms.contentlocale: pt-br
ms.lasthandoff: 08/09/2018

---
# <a name="define-er-model-mappings-and-select-data-sources-for-them"></a>Definir mapeamentos do modelo de ER e selecionar fontes de dados para eles

[!include [task guide banner](../../includes/task-guide-banner.md)]

As etapas a seguir explicam como um usuário no papel de Administrador do Sistema ou Desenvolvedor de Relatório Eletrônico pode selecionar fontes de dados para um modelo de dados do Relatório eletrônico (RE). As fontes de dados serão associadas a componentes individuais do modelo de dados selecionado durante o projeto e povoarão dados comerciais àquele modelo de dados durante a execução. Neste exemplo, você selecionará fontes de dados para um modelo de dados existentes que foi criado para a empresa de exemplo, Litware, Inc. Para concluir estas etapas, primeiro você deve concluir as etapas no procedimento "criar um novo modelo de dados".


## <a name="open-the-electronic-reporting-configurations-tree"></a>Abrir a árvore de configurações Relatório eletrônico
1. Ir para Administração da organização > Espaços de trabalho > Relatório eletrônico.
2. Clique em Configurações de relatórios.

## <a name="insert-a-new-model-mapping"></a>Inserir um novo mapeamento de modelo
1. Na árvore, selecione 'Pagamentos (modelo simplificado)'.
2. Clique em Designer.
3. Clique em Mapear modelo para fonte de dados.
4. Clique em Novo.
    * Isso irá criar um novo registro que mapeará o modelo de dados a fontes de dados. Neste exemplo, você mapeará o modelo de dados a fontes de dados para o tipo de pagamento desejado: transferência de crédito.     É possível projetar mais de um mapeamento para um modelo de dados específico. Por exemplo, você pode criar um mapeamento para os diferentes tipos de pagamentos, como para o débito direto ou para transferências de crédito. Neste exemplo, você irá criar um mapeamento para transferências de crédito.  
5. No campo Nome, digite 'Mapeamento CT'.
    * Mapeamento do CT  
6. No campo Descrição, digite 'Modelo de pagamento mapeando CT'.
    * Modelo de pagamento mapeando CT  
7. No campo Definição, digite "CustomerCreditTransferInitiation".
    * Início da Transferência de Crédito do Cliente  
8. Resolver altera a definição.
9. Clique em Salvar.

## <a name="define-required-data-sources-for-the-current-model-mapping"></a>Defina as fontes de dados necessárias para mapeamento de modelo atual
1. Clique em Designer.
2. Na árvore, selecione "Dynamics 365 for Operations\Registros da tabela".
3. Clique em Adicionar raiz.
    * Insira essa fonte de dados para acessar as transações de pagamento.  
4. No campo Nome, digite 'Transações'.
    * Transações  
5. No campo Rótulo, insira 'Transações'.
    * Transações  
6. No campo Ajuda, insira 'Linhas do diário-razão'.
    * Linhas do diário-razão  
7. Selecione Sim no campo Pedir consulta.
    * Selecione Sim.  
8. No campo Tabela, digite 'LedgerJournalTrans'.
    * LedgerJournalTrans  
9. Clique em OK.
    * Selecione a tabela LedgerJournalTrans como uma fonte de dados para o modelo de dados atual.  
10. Na árvore, selecione 'Funções\Campo calculado'.
11. Clique em Adicionar.
    * Clique em Adicionar para adicionar um novo campo calculado.  
12. No campo Nome, digite '$EndToEndID'.
    * $EndToEndID  
13. Clique em Editar fórmula.
14. Na árvore, selecione 'Cadeia de caracteres\CONCATENATE'.
15. Clique em Adicionar função.
16. Na árvore, expanda 'Transações'.
17. Na árvore, selecione 'Transações\Comprovante'.
18. Clique em Adicionar fonte de dados.
19. No campo Fórmula, insira "CONCATENATE(Transactions.Voucher, "-", ".
    * Digite [ , “-“, ] no final da fórmula.  
20. Na árvore, selecione 'Cadeia de caracteres\TEXTO'.
21. Clique em Adicionar função.
22. Na árvore, selecione 'Transações\ID-Registro(RecId)'.
23. Clique em Adicionar fonte de dados.
24. No campo Fórmula, insira "CONCATENATE(Transactions.Voucher, "-", TEXT(Transactions.RecId))".
    * Digite [))] no final da fórmula.  
25. Clique em Salvar.
    * Verifique se nenhum erro foi descoberto na fórmula criada. Consulte a aba ERROS abaixo do controle do editor da fórmula.  
26. Feche a página.
27. Clique em OK.
    * Adicione o campo calculado a essa fonte de dados.  
28. Clique em Adicionar.
    * Clique em Adicionar para adicionar um novo campo calculado.  
29. No campo Nome, digite '$Amount'.
    * $Amount  
30. Clique em Editar fórmula.
31. Na árvore, expanda 'Transações'.
32. Na árvore, selecione 'Transações\Débito(AmountCurDebit)'.
33. Clique em Adicionar fonte de dados.
34. No campo Fórmula, insira "Transactions.AmountCurDebit - ".
    * Digite [ - ] no final da fórmula.  
35. Na árvore, selecione 'Transações\Crédito(AmountCurCredit)'.
36. Clique em Adicionar fonte de dados.
37. Clique em Salvar.
38. Feche a página.
39. Clique em OK.
    * Isso irá adicionar o campo calculado $Amount à fonte de dados selecionada para o modelo de dados atual.  
40. Na árvore, selecione "Transações\$Valor".
41. Na árvore, expanda 'Transações'.
42. Na árvore, expanda ou recolha "Transações\$Valor".
43. Na árvore, expanda ou recolha "Transações".
44. Na árvore, selecione "Dynamics 365 for Operations\Registros da tabela".
45. Clique em Adicionar raiz.
    * Insira essa fonte de dados para acessar os detalhes da conta bancária da empresa.  
46. No campo Nome, digite 'BankAccount'.
    * BankAccount  
47. No campo Rótulo, insira 'Conta Bancária'.
    * Conta Bancária  
48. No campo Ajuda, insira 'Conta Bancária'.
    * Conta Bancária  
49. Selecione Sim no campo Pedir consulta.
    * Selecione Sim.  
50. No campo Tabela, digite 'BankAccountTable'.
    * BankAccountTable  
51. Clique em OK.
    * Selecione a tabela BankAccountTable como uma fonte de dados para o modelo de dados atual.  
52. Clique em Adicionar raiz.
    * Insira essa fonte de dados para acessar os requisitos da empresa.  
53. No campo Nome, digite 'Empresa'.
    * Empresa  
54. No campo Rótulo, digite um valor.
    * Informações da empresa  
55. No campo Ajuda, insira 'Informação da empresa'.
    * Informações da empresa  
56. Selecione Sim no campo Pedir consulta.
    * Selecione Sim.  
57. No campo Tabela, digite 'CompanyInfo'.
    * CompanyInfo  
58. Clique em OK.
    * Selecione a tabela CompanyInfo como uma fonte de dados para o modelo de dados atual.  
59. Na árvore, selecione 'Funções\Campo calculado'.
60. Clique em Adicionar raiz.
    * Insira um campo calculado como uma nova fonte de dados.  
61. No campo Nome, digite 'ProcessamentoDataHora'.
    * ProcessamentoDataHora  
62. No campo Rótulo, insira 'Data e hora de processamento'.
    * Data e hora de processamento  
63. Clique em Editar fórmula.
64. Na árvore, selecione "Data/hora\SESSIONNOW".
65. Clique em Adicionar função.
66. Clique em Salvar.
67. Feche a página.
68. Clique em OK.
    * Adiciona o campo calculado DataHoraProcessamento como uma fonte de dados para o modelo de dados atual.  
69. Clique em Salvar.
70. Feche a página.
71. Feche a página.
72. Feche a página.


