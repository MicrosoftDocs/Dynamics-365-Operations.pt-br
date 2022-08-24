---
title: Gerar documentos eletrônicos ER para pagamentos usando uma configuração de formato
description: Este artigo descreve como usar uma nova configuração de formato de relatório eletrônico (ER) para gerar documentos eletrônicos para processar pagamentos.
author: kfend
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: kfend
ms.search.region: Global
ms.author: filatovm
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.search.form: VendPaymMode, LedgerJournalTable, LedgerJournalTransVendPaym, BankAccountTableLookUp
ms.openlocfilehash: b70b246e3618e8f083e5f6757ee8a97d8072a635
ms.sourcegitcommit: 87e727005399c82cbb6509f5ce9fb33d18928d30
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/12/2022
ms.locfileid: "9290864"
---
# <a name="er-generate-electronic-documents-for-payments-using-a-format-configuration"></a>Gerar documentos eletrônicos ER para pagamentos usando uma configuração de formato

[!include [banner](../../includes/banner.md)]

As etapas a seguir explicam como um usuário no papel de Administrador do Sistema ou Desenvolvedor de Relatório Eletrônico pode usar uma nova configuração de formato de Relatório Eletrônico (RE) para gerar documentos eletrônicos para processamento de pagamentos. Essas etapas podem ser executadas na empresa de amostra GBSI.

Para concluir estas etapas, primeiramente conclua as etapas no procedimento "Criar uma configuração com formato de documento de pagamento".


## <a name="change-the-configuration-of-the-electronic-payment-method"></a>Alterar a configuração do método do pagamento eletrônico
1. Acesse Contas a pagar > Configurar pagamento > Métodos de pagamento.
2. Ativar/desativar a seção Formato de arquivo para expandi-la, se necessário.
3. Use o Filtro Rápido para localizar registros. Por exemplo, filtre o campo Método de pagamento com um valor de "Electronic".
4. Clique em Editar.
5. Definir o campo Relatório eletrônico geral para Sim.
    * Selecione Sim para usar o Padrão eletrônico geral de relatório para a geração dos arquivos de pagamento.  
6. No campo Nome, clique no botão suspenso para abrir a pesquisa.
7. Selecionar configuração de formato BACS (fictício do Reino Unido).
8. Clique em Salvar.
9. Feche a página.

## <a name="test-the-format-of-generated-payment-files"></a>Testar o formato de arquivo de pagamento gerado
1. Acesse Contas a pagar > Pagamentos > Diário de pagamentos.
2. Clique em Novo.
3. Na lista, marque a linha selecionada.
4. No campo Nome, clique no botão suspenso para abrir a pesquisa.
5. Na lista, clique no link na linha selecionada.
    * Selecionar VendPay.  
6. Clique em Salvar.
7. Clique em Linhas.
8. No campo Empresa, digite "DEMF".
    * DEMF  
9. No campo Conta, especifique os valores "DE-01001".
    * DE - 01001  
10. No campo Descrição, digite "Pagamento".
    * Pagamento  
11. No campo Débito, insira um número.
    * 1000  
12. Clique na aba Pagamento.
13. No campo Método de pagamento, clique no botão suspenso para abrir a pesquisa.
14. Na lista, localize e selecione o PDV desejado.
    * Selecione o Valor eletrônico.  
15. Na lista, clique no link na linha selecionada.
16. Clique em Salvar.
17. Clique em Gerar pagamentos.
18. No campo Método de pagamento, clique no botão suspenso para abrir a pesquisa.
19. Na lista, localize e selecione o PDV desejado.
    * Selecione o Valor eletrônico.  
20. Na lista, clique no link na linha selecionada.
    * Selecione o Valor eletrônico.  
21. No campo Nome do arquivo, digite um valor.
    * Por exemplo, digite "Pagamentos".  
22. No campo Conta bancária, clique no botão suspenso para abrir a pesquisa.
23. Na lista, clique no link na linha selecionada.
    * Selecione o valor GBSI OPER.  
24. Clique em OK.
25. Clique em OK.
    * Analisar o arquivo de pagamento criada no formato XML. Compare-o com o layout de documento criado e defina atributos da transação de pagamento.  



[!INCLUDE[footer-include](../../../../includes/footer-banner.md)]
