--- 
title: Inserir contratos de venda
description: "Este procedimento mostra como criar um contrato de venda que compromete um de seus clientes a comprar um produto por um valor acordado durante um período, em troca de descontos especiais."
author: omulvad
manager: AnnBe
ms.date: 11/10/2016
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: kfend
ms.search.scope: Operations
ms.search.region: Global
ms.search.industry: Service industries
ms.author: omulvad
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 55b22d246d6bfa9e8159fb844da95f61fcf07c62
ms.openlocfilehash: 099447252fe8fae5d44cf6cba87e8fbe0fd924e0
ms.contentlocale: pt-br
ms.lasthandoff: 07/28/2017

---
# <a name="enter-sales-agreements"></a>Inserir contratos de venda

[!include[task guide banner](../../includes/task-guide-banner.md)]

Este procedimento mostra como criar um contrato de venda que compromete um de seus clientes a comprar um produto

, com um valor acordado durante um período, em troca de descontos especiais. Você pode executar esse procedimento na empresa USMF de dados demo, ou usando seus próprios dados.


## <a name="set-up-sales-agreement-header"></a>Configurar cabeçalho do contrato de venda
1. Vá para Vendas e marketing > Contratos de venda > Contratos de venda.
2. Clique em Novo.
3. No campo Conta do cliente, clique no botão suspenso para abrir a pesquisa.
4. Na lista, localize e selecione o registro desejado.
5. Na lista, clique no link na linha selecionada.
6. No campo Classificação do contrato de venda, clique no botão suspenso para abrir a pesquisa.
7. Na lista, clique no link na linha selecionada.
8. Expanda a seção Geral.
9. No campo Compromisso padrão, selecione 'Compromisso de valor do produto'.
    * Um tipo compromisso é um critério obrigatório que você deve atribuir ao contrato para definir como o contrato do acordo será atendido. Os quatro tipos predefinidos permitem configurar o destino do compromisso do cliente, expresso como uma quantidade ou um valor. O tipo de compromisso de quantidade só pode ser aplicado a um produto específico, mas os tipos com base no valor são aplicáveis à vendas de produtos específicos e não específicos.  
10. No campo Data de vencimento, defina a data para uma data futura na qual você deseja que o contrato expire.
11. Clique em OK.

## <a name="set-up-product-value-commitment-lines"></a>Configurar linhas de compromisso com o valor do produto
1. Clique em Adicionar linha.
2. No campo Número de item, clique no botão suspenso para abrir a pesquisa.
3. Na lista, localize e selecione o PDV desejado.
4. Na lista, clique no link na linha selecionada.
    * O tipo de compromisso escolhido para o contrato afeta o tipo de informação que você pode inserir para as linhas do contrato. Por exemplo, para um contrato baseado em valor, especifique o valor líquido total (na moeda concordada) para o qual o cliente se compromete a comprar suas mercadorias. Neste exemplo os campos Quantidade e Unidade na linha não estão disponíveis porque você está criando um acordo para que o cliente compre um valor específico de um produto.   
5. No campo Valor líquido, insira o valor monetário que o cliente confirmou para compra.
6. No campo Percentual de desconto, insira um valor percentual que se aplica às linhas da ordem de venda do cliente que estão associadas a esse contrato.
7. Expanda a seção Detalhes da linha.
8. Selecione Sim no campo Imposição de valor máx.
    * Selecionar Imposição de valor máx. significa que o valor total de todas as linhas da ordem de venda que usam os preços promocionais especiais do compromisso, descontos e/ou condições de pagamento não devem exceder o valor especificado no compromisso.  
    * Os valores mínimo e máximo especificam um intervalo de valores que deve ser vendido em cada ordem de venda que usa o contrato selecionado.   
9. Expanda a seção Cabeçalho do contrato de venda.
    * A menos que o status do contrato seja definido como Em vigor, as ordens de venda não podem ser associadas ao contrato e, consequentemente, não podem contribuir para o atendimento desse contrato. Você pode alterar o status manualmente neste estágio. No entanto, o status normalmente é alterado quando você confirma o contrato para o cliente.  
10. No Painel de Ação, clique em Contrato de venda.
11. Clique em Confirmação.
    * Certifique-se de que a opção Marcar contrato como em vigor está definida como Sim.  
12. Selecione Sim no campo Imprimir relatório.
13. Clique em OK.
14. Feche a página.
    * O contrato agora está em vigor e você pode começar a vincular as ordens do cliente ao contrato, para deslocar em relação ao destino comprometido.  


