--- 
title: "Mapear modelos de dados de relatórios eletrônicos (ER) para fontes de dados selecionadas"
description: "As etapas a seguir explicam como um usuário na função de Administrador do Sistema ou Desenvolvedor de Relatórios Eletrônicos pode mapear um modelo de dados de ER a fontes de dados selecionadas do Dynamics 365 for Finance and Operations, Enterprise edition (novembro, 2016)."
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
ms.openlocfilehash: f347c19d940330c830509be4d11127f9e3324deb
ms.contentlocale: pt-br
ms.lasthandoff: 08/09/2018

---
# <a name="map-electronic-reporting-er-data-models-to-selected-data-sources"></a>Mapear modelos de dados de relatórios eletrônicos (ER) para fontes de dados selecionadas

[!include [task guide banner](../../includes/task-guide-banner.md)]

As etapas a seguir explicam como um usuário na função de Administrador do Sistema ou Desenvolvedor de Relatórios Eletrônicos pode mapear um modelo de dados de ER a fontes de dados selecionadas do Dynamics 365 for Finance and Operations. Esse mapeamento de modelo será usado posteriormente como uma fonte de dados em uma configuração de formato que será usada para gerenciar documentos de pagamento eletrônico. Neste exemplo, você mapeia um modelo de dados para a empresa exemplo, Litware, Inc., em fontes de dados. Para concluir essas etapas, você deve primeiro concluir as etapas do procedimento 'Selecionar fontes de dados para mapeamento de modelo'.


## <a name="open-er-configurations-tree"></a>Abra a árvore de Configurações de ER
1. Ir para Administração da organização > Espaços de trabalho > Relatório eletrônico.
2. Clique em Configurações.

## <a name="select-created-model-mapping"></a>Selecione o mapeamento de modelo criado
1. Na árvore, selecione 'Pagamentos (modelo simplificado)'.
    * Verifique se a configuração do modelo “Pagamentos (modelo simplificado)“ foi criada antecipadamente. Caso contrário, pare agora e retorne após a conclusão da guia de tarefas "Criar uma nova configuração com modelo de dados do domínio selecionado"  
2. Clique em Designer de modelo.
3. Clique em Mapear modelo para fonte de dados.
4. Selecione o registro de 'Mapeamento CT'.
    * Mapeamento do CT  

## <a name="bind-created-data-sources-to-data-model-elements"></a>Associe fontes de dados criadas a elementos do modelo de dados
1. Clique em Designer.
2. Na árvore, selecione 'Data e hora de processamento(ProcessingDateTime)'.
3. Na árvore, selecione 'Data de processamento(DataHoraProcessamento)'.
4. Clique em Associar.
5. Na árvore, selecione 'Identificação de mensagem de pagamento(IdentificaçãoMensagem)'.
6. Na árvore, expanda 'Transações'.
7. Na árvore, selecione 'Transações\Número do lote do diário(JournalNum)'.
8. Clique em Associar.
9. Na árvore, selecione 'Pagamentos'.
10. Na árvore, selecione 'Transações'.
11. Clique em Associar.
12. Na árvore, expanda 'Pagamentos = Transações'.
13. Na árvore, expanda 'Pagamentos = Transações\Credor'.
14. Na árvore, expanda 'Pagamentos = Transações\Credor\Conta'.
15. Na árvore, selecione 'Pagamentos = Transações\Credor\Conta\Código de moeda(Currency)'.
16. Na árvore, expanda 'Transações\vendBankAccountInTransactionCompany()'.
17. Na árvore, selecione 'Transações\vendBankAccountInTransactionCompany()\Moeda(CurrencyCode)'.
18. Clique em Associar.
19. Na árvore, selecione 'Pagamentos = Transações\Credor\Conta\Código IBAN(IBAN)'.
20. Na árvore, selecione 'Transações\vendBankAccountInTransactionCompany()\IBAN(BankIBAN)'.
21. Clique em Associar.
22. Na árvore, selecione 'Pagamentos = Transações\Credor\Conta\Número'.
23. Na árvore, selecione 'Transações\vendBankAccountInTransactionCompany()\Número da conta bancária(AccountNum)'.
24. Clique em Associar.
25. Na árvore, expanda 'Pagamentos = Transações\Credor\Agente'.
26. Na árvore, selecione 'Pagamentos = Transações\Credor\Agente\Nome'.
27. Na árvore, selecione 'Transações\vendBankAccountInTransactionCompany()\Nome'.
28. Clique em Associar.
29. Na árvore, selecione 'Pagamentos = Transações\Credor\Agente\Número do banco(RoutingNumber)'.
30. Na árvore, selecione 'Transações\vendBankAccountInTransactionCompany()\Número do banco(RegistrationNum)'.
31. Clique em Associar.
32. Na árvore, selecione 'Pagamentos = Transações\Credor\Agente\Código SWIFT(SWIFT)'.
33. Na árvore, selecione 'Transações\vendBankAccountInTransactionCompany()\Código SWIFT(SWIFTNo)'.
34. Clique em Associar.
35. Na árvore, selecione 'Pagamentos = Transações\Credor\Nome'.
36. Na árvore, expanda 'Transações\fingVendTable()'.
37. Na árvore, selecione 'Transactions\findVendTable()\name()'.
38. Clique em Associar.
39. Na árvore, selecione 'Pagamentos = Transações\Código de moeda(Currency)'.
40. Na árvore, expanda 'Transações\>Relações'.
41. Na árvore, expanda 'Transações\>Relações\Tabela de moedas(Currency)'.
42. Na árvore, selecione 'Transações\>Relações\Tabela de moedas(Currency)\Código de moeda(CurrencyCodeISO)'.
43. Clique em Associar.
44. Na árvore, expanda 'Pagamentos = Transações\Devedor'.
45. Na árvore, expanda 'Pagamentos = Transações\Devedor\Conta'.
46. Na árvore, selecione 'Pagamentos = Transações\Devedor\Conta\Código de moeda(Currency)'.
47. Na árvore, selecione 'Conta Bancária(BankAccount)'.
48. Na árvore, expanda 'Conta Bancária(BankAccount)'.
49. Na árvore, selecione 'Conta Bancária(BankAccount)\Moeda(CurrencyCode)'.
50. Clique em Associar.
51. Na árvore, selecione 'Conta Bancária(BankAccount)\IBAN'.
52. Na árvore, selecione 'Pagamentos = Transações\Devedor\Conta\Código IBAN(IBAN)'.
53. Clique em Associar.
54. Na árvore, selecione 'Pagamentos = Transações\Devedor\Conta\Número'.
55. Na árvore, selecione 'Conta Bancária(BankAccount)\Número da conta bancária(AccountNum)'.
56. Clique em Associar.
57. Na árvore, expanda 'Pagamentos = Transações\Devedor\Agente'.
58. Na árvore, selecione 'Pagamentos = Transações\Devedor\Agente\Nome'.
59. Na árvore, selecione 'Conta Bancária(BankAccount)\Nome'.
60. Clique em Associar.
61. Na árvore, selecione 'Pagamentos = Transações\Devedor\Agente\Número do banco(RoutingNumber)'.
62. Na árvore, selecione 'Conta Bancária(BankAccount)\Número do banco(RegistrationNum)'.
63. Clique em Associar.
64. Na árvore, selecione 'Pagamentos = Transações\Devedor\Agente\Código SWIFT(SWIFT)'.
65. Na árvore, selecione 'Conta Bancária(BankAccount)\Código SWIFT(SWIFTNo)'.
66. Clique em Associar.
67. Na árvore, selecione 'Pagamentos = Transações\Devedor\Nome'.
68. Na árvore, selecione 'Informações da empresa(Company)'.
69. Na árvore, expanda 'Informações da empresa(Company)'.
70. Na árvore, selecione 'Informações da empresa(Company)\Nome'.
71. Clique em Associar.
72. Na árvore, selecione 'Pagamentos = Transações\Descrição'.
73. Na árvore, selecione 'Transações\Descrição(Txt)'.
74. Clique em Associar.
75. Na árvore, selecione 'Pagamentos = Transações\Código de identificação ponto a ponto(End2EndID)'.
76. Na árvore, selecione 'Transações\$EndToEndID'.
77. Clique em Associar.
78. Na árvore, selecione 'Pagamentos = Transações\Valor instruído(InstructedAmount)'.
79. Na árvore, selecione "Transações\$Valor".
80. Clique em Associar.
81. Na árvore, selecione 'Pagamentos = Transações\Data da transação(TransactionDate)'.
82. Na árvore, selecione 'Transações\Data(TransDate)'.
83. Clique em Associar.

## <a name="validate-created-mapping"></a>Valide o mapeamento criado
1. Clique em Validar.
    * Valide o novo mapeamento para garantir que todas as associações são aprovadas.  
2. Clique na seta para expandir ou recolher a seção Lista de erros.
3. Clique em Salvar.
4. Feche a página.
5. Feche a página.
6. Feche a página.

## <a name="change-the-status-of-the-current-version-of-model-configuration"></a>Altere o status da versão atual da configuração de modelo.
1. Clique em Alterar status.
    * Altere o status da configuração do modelo criado - de Rascunho para Concluído para torná-lo disponível para design de formato de pagamento.  
2. Clique em Concluir.
    * Selecione Concluído.  
3. No campo Descrição, digite um valor.
    * Por exemplo, "versão 1".  
4. Clique em OK.
5. Selecione a versão concluída da configuração atual.
    * Observe que a configuração criada será salva como versão 1 concluída.  


