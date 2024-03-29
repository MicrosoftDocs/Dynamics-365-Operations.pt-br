---
title: Visão geral de pagamentos de fornecedor
description: Este procedimento orienta você ao longo de vários métodos usados para criar pagamentos de fornecedor, incluindo como usar uma proposta de pagamento ou inserir manualmente um pagamento único.
author: kweekley
ms.date: 06/25/2019
ms.topic: business-process
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: kfend
ms.custom: intro-internal
ms.search.region: Global
ms.author: kweekley
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 3aa53914f9e61b164660ff6f25c6d87f9386e9a8
ms.sourcegitcommit: 631d2cea52590af15f208e9af584446e85540fcf
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/07/2022
ms.locfileid: "8726256"
---
# <a name="vendor-payment-overview"></a>Visão geral de pagamentos de fornecedor

[!include [banner](../../includes/banner.md)]

Este procedimento orienta você ao longo de vários métodos usados para criar pagamentos de fornecedor, incluindo como usar uma proposta de pagamento ou inserir manualmente um pagamento único. Este procedimento usa a empresa de dados de demonstração USMF.

1. Acesse **Painel de Navegação > Módulos > Contas a pagar > Pagamentos > Diário de pagamentos**.
2. Clique em **Novo**.
3. Selecione o diário de pagamentos para salvar os pagamentos do fornecedor. 
4. Selecione o diário ou insira-o manualmente.
5. Clique em **Linhas**.
6. No **Painel de ação**, clique em **Proposta de pagamento**.
7. Clique em **Criar proposta de pagamento**. A proposta de pagamento é uma consulta utilizada para selecionar faturas para o pagamento. Você pode editar a lista de faturas a serem pagas antes de criar ou de gerar os pagamentos do fornecedor.
8. Selecionar faturas para o pagamento por data de vencimento, desconto à vista, ou ambos. 
9. Insira a data para comparação com a data de vencimento ou de desconto à vista. 
10. Opcional: Insira uma data de pagamento usada para todos os pagamentos. A data inserida aqui será a data de pagamento para todos os pagamentos criados, independentemente da data de vencimento ou da data de desconto à vista.  
11. Opcional: Insira uma data de pagamento mínimo que pode ser usada como a data de pagamento. A data de pagamento mínimo será a primeira data usada durante a criação dos pagamentos. Por exemplo, se uma fatura tem sua data de vencimento após a data de pagamento mínimo, a data de vencimento passará a ser a data de pagamento em vez da data de pagamento mínima, visando pagar a fatura na data mais distante possível.
12. Insira restrições de consulta adicionais na seção **Registros a serem incluídos**. O filtro é usado geralmente para restringir as faturas selecionadas para pagamento por grupo de fornecedores ou método de pagamento. Por exemplo, você pode adicionar um filtro para pagar somente faturas com cheque neste ciclo de pagamentos.
13. Insira restrições de consulta adicionais ou padrões de pagamento. Os parâmetros adicionais podem ser usados para definir a moeda de pagamento ou para permitir pagamentos centralizados para esse ciclo de pagamentos.  
14. Clique em **OK**. Após clicar em **OK**, os resultados da consulta serão exibidos. Se você não deseja visualizar a lista de faturas selecionadas para pagamento, você pode voltar para a guia rápida **Parâmetros** e alterar a opção **Criar pagamentos sem visualização da fatura** como "Sim".  
15. Escolha o botão **Exibir visão geral do pagamento** para visualizar os pagamentos que serão criados para o fornecedor na fatura selecionada.
16. Escolha o botão **Ocultar visão geral do pagamento** para ocultar os pagamentos. 
17. Clique em **Criar pagamentos**. Antes de escolher **Criar pagamentos**, você pode clicar com o botão direito do mouse na grade e exportar a lista de faturas para o Excel. O botão **Criar pagamentos** criará os pagamentos de fornecedor no diário de pagamentos.  
18. Examine os pagamentos e verifique se o método de pagamento está definido para todos os pagamentos. Se você gerar os pagamentos, como imprimir um cheque ou criar um pagamento eletrônico, o método de pagamento deve ser definido. O método de pagamento também padronizará a conta bancária a partir da qual o pagamento será feito.  
19. Clique em **Novo** para criar um pagamento único. Um pagamento único pode ser adicionado a um diário de pagamentos a qualquer momento antes do envio. Isso é feito clicando no botão **Novo** e adicionando as informações de pagamento manualmente, em vez de usar a **Proposta de pagamento**.  
20. Selecione o fornecedor para o qual o pagamento será feito.
21. Se existe uma fatura para pagar, selecione **Liquidar transações** para selecionar a fatura para pagamento. Se este for um pagamento antecipado, essa etapa é opcional. Você pode criar o pagamento sem selecionar nenhuma fatura. 
22. Marque todas as faturas que serão pagas. Se você usar a opção **Liquidar transações** para selecionar as faturas para pagamento, o valor do pagamento será calculado automaticamente com base nas faturas que você marcou para o pagamento e em qual valor você inseriu em **Quantia a liquidar**.
23. Clique em **OK**.
24. Se quiser excluir um pagamento, marque a linha.
25. Clique em **Excluir**. Excluir um pagamento apenas irá excluir o pagamento. Qualquer fatura marcada para pagamento ainda estará disponível para ser paga em outro pagamento.
26. Clique em **Sim**.
27. Escolha **Gerar pagamento** para imprimir cheques ou criar o arquivo de pagamento eletrônico.
28. Selecione o método de pagamento que deseja gerar. O diário de pagamento pode conter pagamentos de cheques e pagamentos eletrônicos, mas você só pode gerar um tipo de pagamento por vez.
29. Selecione a conta bancária da qual irá gerar os pagamentos.
30. Clique em **OK**. Pagamentos só serão gerados para pagamentos que correspondam ao **Método de pagamento** e à **Conta bancária** que você selecionou.
31. Se você está gerando **Cheques**, escolha **Documento** para garantir o destino de impressão correto para os cheques.
32. Clique em **OK**.
33. Clique em **OK** para gerar os pagamentos.
34. Clique em **Lançar** se todos os pagamentos foram aprovados e gerados. 



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]
