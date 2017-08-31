--- 
title: "Configurar e gerar informações de classificação por vencimento de contas a receber"
description: "Esta guia ajudará a configurar uma definição do período de classificação por vencimento, para classificar por vencimento saldos do cliente e saldos de exibição na lista de saldos classificados por vencimento, além da página das coleções."
author: mikefalkner
manager: AnnBe
ms.date: 11/14/2016
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: twheeloc
ms.search.scope: Operations
ms.search.region: Global
ms.author: mfalkner
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: f01d88149074b37517d00f03d8f55e1199a5198f
ms.openlocfilehash: ed23bcfed4e256ecc16264a181161c7119cd9bb3
ms.contentlocale: pt-br
ms.lasthandoff: 07/27/2017

---
# <a name="set-up-and-generate-accounts-receivable-aging-information"></a>Configurar e gerar informações de classificação por vencimento de contas a receber

[!include[task guide banner](../../includes/task-guide-banner.md)]

Esta guia ajudará a configurar uma definição do período de classificação por vencimento, para classificar por vencimento saldos do cliente e saldos de exibição na lista de saldos classificados por vencimento, além da página das coleções. Este registro usa a empresa de dados de demonstração USMF.


## <a name="create-an-aging-period-definition"></a>Crie uma definição de período de classificação por vencimento
1. Vá para Crédito e coleções > Configuração > Definições de período de classificação por vencimento.
2. Clique em Novo.
3. No campo de definição do período de classificação por vencimento, digite um valor.
4. No campo Descrição, digite um valor.
5. Clique em Adicionar abaixo para inserir um novo período de classificação por vencimento.
6. No campo Período, insira a descrição a ser mostrada no relatório de classificação por vencimento.
7. No campo Unidade, insira um número.
8. No campo Intervalo, selecione uma opção.
    * O período do razão no período corresponde ao calendário do razão. O dia, a semana, o mês, trimestre e o ano definem o tamanho do intervalo por tipo de data. Ilimitado seleciona todas as transações antes ou depois do período anterior, caso seja o primeiro período ou o último.  
9. No campo Indicador de classificação por vencimento, selecione uma opção.
10. Selecione o período na parte superior da grade. Atualize a descrição para descrever o mais antigo na definição do período de classificação por vencimento
11. No campo Período, insira a nova descrição do período de classificação por vencimento.
12. Feche a página.

## <a name="age-the-balances"></a>Saldos com vencimento
1. Vá para Crédito e coleções > Tarefas periódicas > Classificar saldos de cliente por vencimento.
2. No campo de definição do período de classificação por vencimento, selecione a definição do período de classificação por vencimento que você criou.
    * Você pode ter um instantâneo ativo para cada definição do período de classificação por vencimento.  
    * Todas os clientes são processados por padrão. Você pode usar essa seleção para calcular um único grupo de conjuntos de clientes.  
    * Selecione a data da transação que será usada para a classificação por vencimento.  
    * Selecione a data “a partir de”para classificação de vencimento. O padrão é a data atual, mas se você alterar este campo à data selecionada, você poderá escolher a data desejada. Para processamento em lotes, use a data de hoje.  
3. Expanda a Variação de empresa. Você pode selecionar as empresas que serão incluídas no instantâneo. A empresa atual é selecionada por padrão.
4. Clique em OK para processar o instantâneo. Levará algum tempo para que o controle deslizante desapareça e verifique o centro da mensagem para uma mensagem.

## <a name="view-the-balances-on-the-aged-balances-list-and-on-the-collection-page"></a>Exibir os saldos na lista de saldos classificados por vencimento e na página de cobrança
1. Vá para Crédito e coleções > Cobranças > Saldos antigos.
    * A página de listagem mostra os saldos do cliente. O ícone classificação por vencimento mostra o período de classificação por vencimento da transação mais antigo.  
2. Selecione um cliente com um saldo.
3. Expanda a área de classificação por vencimento da caixa de fatos para exibir os saldos classificados por vencimento.
    * A definição do período de classificação por vencimento da caixa de fatos são tiradas da definição do período de classificação por vencimento padrão especificado nos parâmetros. Você pode alterá-la usando o menu Coletar.  


