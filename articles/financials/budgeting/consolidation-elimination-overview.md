---
title: Visão geral de consolidação e da eliminação
description: Este artigo fornece informações gerais sobre o processo de consolidação e de eliminação. Inclui as respostas às perguntas frequentes.
author: aprilolson
manager: AnnBe
ms.date: 01/11/2018
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: LedgerConsolidate
audience: Application User
ms.reviewer: roschlom
ms.search.scope: Core, Operations
ms.custom: 13151
ms.assetid: 9d8f55cb-b2cf-4e01-89cf-0e21f5c8ae1f
ms.search.region: Global
ms.author: aolson
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 266c594fda1609e4efdc8cdcd79767d94b755187
ms.sourcegitcommit: 8b4b6a9226d4e5f66498ab2a5b4160e26dd112af
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/01/2019
ms.locfileid: "1842752"
---
# <a name="consolidation-and-elimination-overview"></a>Visão geral de consolidação e da eliminação

[!include [banner](../includes/banner.md)]

Este artigo fornece informações gerais sobre o processo de consolidação e de eliminação. Inclui as respostas às perguntas frequentes.

Ao consolidar os dados, os resultados financeiros de várias empresas subsidiárias são combinados em resultados de uma única empresa consolidada. As subsidiárias podem estar em versões ou em sistemas diferentes, podem não ser propriedade exclusiva e podem usar ocorrências diferentes. Há várias opções para consolidar os dados:

-   **Consolidar online** – Esta opção consolida saldos diários por contas e por dimensões selecionados e os armazena em uma empresa de consolidação.
-   **Relatório financeiro** – Esta opção habilita a consolidação de transações e saldos e pode ser gerada a qualquer momento. Vários níveis de hierarquias podem ser criados e várias moedas de relatório podem ser exibidas.
-   **Consolidar com a importação** – Esta opção importa saldos em uma empresa de consolidação.
-   **Exportar saldos da empresa** – Esta opção fornece um arquivo de exportação dos saldos da empresa. O arquivo pode ser importado em outras instâncias ou sistemas. Relatórios financeiros também podem ser usados para exportar os saldos para um arquivo do Microsoft Excel.

As eliminações podem ser relatadas de várias maneiras:

-   As regras de eliminação podem ser configuradas no sistema, e então processadas durante o processo de consolidação ou com uma proposta de eliminação. As regras podem ser lançadas em todas as empresas nas quais **Usar para o processo de eliminação financeira** está selecionado na configuração da entidade legal.
-   Uma empresa separada pode ser criada e usada para determinar e lançar manualmente transações de eliminação de lançamento. Esta empresa pode ser usada no processo de consolidação ou no relatório financeiro.
-   As contas e dimensões financeiras que são usadas para determinar a atividade intercompanhia podem ser filtradas em uma definição de linha ou de coluna no relatório financeiro e as capacidades detalhadas podem ser usadas. Uma coluna ou linha calculada pode ser usada para remover as contas e as dimensões financeiras no total consolidado.

Há vários cenários de consolidação e cada método pode controlar os cenários de maneiras diferentes.

## <a name="frequently-asked-questions"></a>Perguntas frequentes
1.  Eu prefiro lançar eliminações em um banco de dados. Quais são as minhas opções?

Você tem várias opções. Você pode usar a opção **Consolidar online** e incluir eliminações durante o processo ou como uma proposta. As transações serão lançadas na empresa de consolidação. Como alternativa, você pode ter uma empresa separada na qual é possível criar uma eliminação manualmente e usar a empresa no relatório financeiro ou no processo de consolidação.

2.  Precisamos de nossos resultados consolidados em várias moedas de relatórios.

A opção **Relatório financeiro** possui moedas de relatórios ilimitadas. OS dados são traduzidos na geração do relatório, com base no tipo de taxa de câmbio e do método de tradução da moeda que estão definidos na conta principal. No entanto, como a opção **Consolidar online** tem apenas uma moeda de relatório, é necessária uma empresa consolidada para cada moeda de relatórios, caso você use esta opção. A opção **Relatório financeiro** é o método recomendado.

3.  Eu desejo ver o detalhe no nível da transação para cada empresa.

A opção **Relatório financeiro** é a solução, pois o detalhe no nível da transação pode ser visualizado como várias empresas são incluídas na definição da árvore do relatório.

4.  Estamos usando o plano ou o controle de orçamento e ele deve ser consolidado.
A opção **Relatório financeiro** é a solução para consolidar todos os dados de planejamento ou de controle do orçamento.

5.  Nossos subsidiários estão espalhados em todo mundo, e temos vários planos de contas. Qual é o melhor método para consolidar seus dados?

Você tem várias opções quando for necessário processar vários planos de contas. Você pode usar a opção **Consolidar online** e optar por usar a conta de consolidação que é definida na conta principal ou grupo da conta de consolidação. Você também pode usar a opção **Relatório financeiro**, incluindo vários links para as dimensões financeiras na definição da linha e mapear as contas.

6.  Nós exigimos vários níveis de consolidação. Em outras palavras, primeiro, nós consolidamos todos os nossos subsidiários europeus para a libra esterlina (GBP). Então, utilizaremos esses dados e converteremos o valor consolidado para dólares americanos. Como nós podemos fazer isto?

Quando vários níveis se consolidação são necessários e várias moedas são usadas no mesmo nível, é necessário usar a opção **Consolidar online** a opção. Várias empresas de consolidação devem ser criadas e devem diferir em sua contabilidade e moedas de relatórios. Uma consolidação deve ser executada várias vezes. A opção **Relatório financeiro** sempre é convertida a partir da moeda da empresa de origem para a moeda selecionada.

7.  Nós temos subsidiários em um sistema diferente. Como nós podemos consolidá-los?

Use a opção **Consolidar com a importação** para usar os saldos em uma empresa de consolidação.

8.  Algumas de nossas subsidiárias não são propriedade exclusiva. Qual é o melhor método para consolidá-los?

Você tem várias opções para subsidiárias parciais. Ao usar a opção **Relatório financeiro**, é possível definir uma definição da árvore do relatório e a propriedade. Você também pode usar uma linha ou uma coluna calculada para representar o valor de propriedade parcial. Você pode exibir o interesse minoritário em sua própria linha em um relatório. Você também pode usar a opção **Consolide online**. A guia **Entidades legais** tem uma coluna **Propriedade**, na qual você pode definir a porcentagem que pertence à empresa pai.

9.  Nossa organização deve mostrar consolidações por unidade de negócios ou deseja usar as hierarquias da organização.

A opção **Relatório financeiro** é a solução. As hierarquias da organização que têm entidades legais ou dimensões financeiras podem ser descritas no relatório financeiro. Você também pode criar suas próprias hierarquias multiníveis usando uma definição de árvore do relatório que tenha uma combinação de entidade legal e valores de dimensão.

10. Temos mais de uma instância do sistema.

Ao usar a opção **Exportar saldos da empresa** para expandir uma instância e usando a opção **Consolidar com importação** em outra instância, é possível consolidar os dados.


Para obter mais informações, consulte [Reavaliação atual em uma empresa de consolidação](../general-ledger/currency-revaluation-consolidation-company.md).


