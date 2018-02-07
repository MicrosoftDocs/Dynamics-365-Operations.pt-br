--- 
title: Definir esquemas de fidelidade
description: Este procedimento orienta como definir um esquema de fidelidade.
author: jashanno
manager: AnnBe
ms.date: 11/14/2017
ms.topic: business-process
ms.prod: 
ms.service: dynamics-365-retail
ms.technology: 
audience: Application User
ms.reviewer: josaw
ms.search.scope: Operations, Retail
ms.search.region: Global
ms.search.industry: Retail
ms.author: jashanno
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 8bbdbf882f6f73d03be0a036cb975109396e4a0d
ms.openlocfilehash: 1fc193e113961705f18488a4341652b3576fb275
ms.contentlocale: pt-br
ms.lasthandoff: 11/14/2017

---

# <a name="define-loyalty-schemes"></a>Definir esquemas de fidelidade

[!include[task guide banner](../includes/task-guide-banner.md)]

Este procedimento orienta como definir um esquema de fidelidade. Os esquemas de fidelidade são regras de ganhos e de resgate para um programa de fidelidade. Este procedimento usa a empresa de dados de demonstração USRT.

1. Vá para Varejo e comércio > Clientes > Fidelidade > Esquemas de fidelidade.
2. Clique em Novo.
3. No campo ID do esquema, digite um valor.
4. No campo Descrição, digite um valor.
5. No campo Nome, clique no botão suspenso para abrir a pesquisa.
    * Você pode ter vários esquemas de fidelidade para um programa de fidelidade. Os esquemas de fidelidade podem ser para todos os canais ou somente um subconjunto de canais.  
6. Na lista, localize e selecione o PDV desejado.
7. Na lista, clique no link na linha selecionada.
8. Clique em Salvar.
9. Clique em Adicionar linha.
10. No campo Tipo de atividade, selecione uma opção.
    * Selecione Comprar produtos por valor se você deseja que os clientes ganhem recompensas com base no valor que gastam. Selecione Comprar produtos por quantidade se você deseja que os clientes ganhem recompensas com base em quantos produtos eles compram.  Selecione Contagem de transações de venda se você deseja que os clientes ganhem recompensas para cada transação de vendas, independentemente do que for comprado ou da quantidade comprada.  
    * Selecione uma categoria. A categoria limitará a quais produtos esta regra de ganho se aplica.  
    * Se desejar que a regra de ganho se aplique a todos os produtos, deixe o campo em branco.  
11. No campo Valor/quantidade da atividade, insira um número.
    *  Para o tipo de atividade de Contagem de transações de venda, você deve usar sempre um valor de "1,0". Para tipos de atividades de Comprar pelo valor ou de Comprar por quantidade, qualquer transação que seja menor do que o valor inserido não acionará a regra de ganho. Por exemplo, se o tipo de atividade for Comprar pelo valor, e você inserir '10,00 ', uma transação de venda de “9,00 'não obterá recompensas para esta regra de ganho.  
12. No campo Moeda da atividade, digite um valor.
13. No campo ID do ponto de recompensa, clique no botão suspenso para abrir a pesquisa.
14. Na lista, clique no link na linha selecionada.
15. No campo Pontos de recompensa, insira um número.
    * Os pontos de recompensa de tipo de valor registrarão valores ganhos com decimais. Por exemplo, se a regra de ganho declarar 1 ponto de recompensa ganho para cada 1 dólar canadense gasto e o cliente gastar 1,25 em dólar canadense, o cliente ganhará 1,25 ponto de recompensa. Os pontos de recompensa de tipo de quantidade registrarão os valores ganhos em números inteiros. Usando o exemplo em que a regra de ganho declara 1 ponto de recompensa ganho para cada 1 dólar canadense gasto e o cliente gasta 1,25 em dólar canadense, o cliente ganhará 1,0 ponto de recompensa.  
16. Clique em Salvar.
17. Clique em Adicionar linha.
    * As regras de resgate são usadas quando o método de pagamento de fidelidade for usado.  
18. No campo ID do ponto de recompensa, clique no botão suspenso para abrir a pesquisa.
    * Somente os pontos de recompensa resgatáveis são mostrados.  
19. Na lista, clique no link na linha selecionada.
20. No campo Pontos de recompensa, insira um número.
21. No campo Tipo de resgate, selecione uma opção.
    * Selecionar o Pagamento por valor faz com que o campo Valor ou Quantidade seja tratado como um valor de moeda. Nesse caso, o valor dos pontos de recompensa usados por unidade monetária de pagamento é um índice fixo. Selecionar o Pagamento por quantidade faz com que o campo Valor ou Quantidade seja tratado como um valor de quantidade. Nesse caso, o valor de pontos de recompensa usado por quantidade de itens é um índice fixo, entretanto, o valor na moeda pode variar se o preço dos itens pagos com pontos de recompensa de fidelidade variar para a mesma quantidade. O tipo de resgate do desconto dos pontos de fidelidade é válido somente quando a chave de configuração de recursos específicos de país/região 'Rússia' estiver habilitada e os perfis de funcionalidade do PDV tiverem um código ISO “RU”.  
    * Selecione uma categoria. A categoria limitará a quais produtos esta regra de resgate se aplica.  
    * Se desejar que a regra de resgate se aplique a todos os produtos, deixe o campo em branco.  
22. No campo Valor ou quantidade, insira um número.
23. No campo Moeda, digite um valor.
24. Clique em Salvar.
25. Clique em Adicionar linha.
    * Selecione um ou mais nós a partir da lista de Nós da organização disponíveis e mova-os para a lista de Nós da organização selecionados clicando na seta entre as duas listas.  
26. Clique em OK.
27. Clique em Salvar.
    * Sempre que alterar os canais para um esquema de fidelidade, você deve executar Processar esquemas de fidelidade. Dessa forma, os canais terão esquemas de fidelidade atualizados.  


