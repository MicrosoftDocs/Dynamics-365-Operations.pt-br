---
title: Visão geral de consolidação e da eliminação
description: Este artigo fornece informações gerais sobre o processo de consolidação e de eliminação. Inclui as respostas às perguntas frequentes.
author: panolte
ms.date: 11/11/2022
ms.topic: overview
ms.prod: ''
ms.technology: ''
ms.search.form: LedgerConsolidate
audience: Application User
ms.reviewer: twheeloc
ms.custom:
- "13151"
- intro-internal
ms.assetid: 9d8f55cb-b2cf-4e01-89cf-0e21f5c8ae1f
ms.search.region: Global
ms.author: panolte
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 757c7634fc929ead018d1ddcca4cc223c1a95638
ms.sourcegitcommit: cf6b764824bd1cf2c0dde6d37ddd0a7abab87ff0
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/16/2022
ms.locfileid: "9779898"
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

-  As regras de eliminação podem ser configuradas no sistema, e então processadas durante o processo de consolidação ou com uma proposta de eliminação. As regras podem ser lançadas em todas as empresas nas quais **Usar para o processo de eliminação financeira** está selecionado na configuração da entidade legal.
-   Uma empresa separada pode ser criada e usada para determinar e lançar manualmente transações de eliminação de lançamento. Esta empresa pode ser usada no processo de consolidação ou no relatório financeiro.
-  As contas e dimensões financeiras que são usadas para determinar a atividade intercompanhia podem ser filtradas em uma definição de linha ou de coluna no relatório financeiro e as capacidades detalhadas podem ser usadas. Uma coluna ou linha calculada pode ser usada para remover as contas e as dimensões financeiras no total consolidado.

Há vários cenários de consolidação e cada método pode controlar os cenários de maneiras diferentes.

## <a name="frequently-asked-questions"></a>Perguntas frequentes
Eu prefiro lançar eliminações em um banco de dados. Quais são as minhas opções?
 - Você tem várias opções. Você pode usar a opção **Consolidar online** e incluir eliminações durante o processo ou como uma proposta. As transações serão lançadas na empresa de consolidação. Como alternativa, você pode ter uma empresa separada na qual é possível criar uma eliminação manualmente e usar a empresa no relatório financeiro ou no processo de consolidação.

Precisamos de nossos resultados consolidados em várias moedas de relatórios.
 - A opção **Relatório financeiro** possui moedas de relatórios ilimitadas. OS dados são traduzidos na geração do relatório, com base no tipo de taxa de câmbio e do método de tradução da moeda que estão definidos na conta principal. No entanto, como a opção **Consolidar online** tem apenas uma moeda de relatório, é necessária uma empresa consolidada para cada moeda de relatórios, caso você use esta opção. A opção **Relatório financeiro** é o método recomendado.

Eu desejo ver o detalhe no nível da transação para cada empresa.
 - A opção **Relatório financeiro** é a solução, pois o detalhe no nível da transação pode ser visualizado como várias empresas são incluídas na definição da árvore do relatório.

Estamos usando o plano ou o controle de orçamento e ele deve ser consolidado.
 - A opção **Relatório financeiro** é a solução para consolidar todos os dados de planejamento ou de controle do orçamento.

Nossos subsidiários estão espalhados em todo mundo, e temos vários planos de contas. Qual é o melhor método para consolidar seus dados?
- Você tem várias opções quando for necessário processar vários planos de contas. Você pode usar a opção **Consolidar online** e optar por usar a conta de consolidação que é definida na conta principal ou grupo da conta de consolidação. Você também pode usar a opção **Relatório financeiro**, incluindo vários links para as dimensões financeiras na definição da linha e mapear as contas.

Nós exigimos vários níveis de consolidação. Em outras palavras, primeiro, nós consolidamos todos os nossos subsidiários europeus para a libra esterlina (GBP). Então, utilizaremos esses dados e converteremos o valor consolidado para dólares americanos. Como nós podemos fazer isto?
- Quando vários níveis se consolidação são necessários e várias moedas são usadas no mesmo nível, é necessário usar a opção **Consolidar online** a opção. Várias empresas de consolidação devem ser criadas e devem diferir em sua contabilidade e moedas de relatórios. Uma consolidação deve ser executada várias vezes. A opção **Relatório financeiro** sempre é convertida a partir da moeda da empresa de origem para a moeda selecionada.

Nós temos subsidiários em um sistema diferente. Como nós podemos consolidá-los?
- Use a opção **Consolidar com a importação** para usar os saldos em uma empresa de consolidação.

Algumas de nossas subsidiárias não são propriedade exclusiva. Qual é o melhor método para consolidá-los?
- Você tem várias opções para subsidiárias parciais. Ao usar a opção **Relatório financeiro**, é possível definir uma definição da árvore do relatório e a propriedade. Você também pode usar uma linha ou uma coluna calculada para representar o valor de propriedade parcial. Você pode exibir o interesse minoritário em sua própria linha em um relatório. Você também pode usar a opção **Consolide online**. A guia **Entidades legais** tem uma coluna **Propriedade**, na qual você pode definir a porcentagem que pertence à empresa pai.

Nossa organização deve mostrar consolidações por unidade de negócios ou deseja usar as hierarquias da organização.
- A opção **Relatório financeiro** é a solução. As hierarquias da organização que têm entidades legais ou dimensões financeiras podem ser descritas no relatório financeiro. Você também pode criar suas próprias hierarquias multiníveis usando uma definição de árvore do relatório que tenha uma combinação de entidade legal e valores de dimensão.

Temos mais de uma instância do sistema.
- Ao usar a opção **Exportar saldos da empresa** para expandir uma instância e usando a opção **Consolidar com importação** em outra instância, é possível consolidar os dados.

É possível fazer uma consolidação com meu orçamento no status **RASCUNHO**? 
- Não será possível processar ou concluir os orçamentos na empresa de consolidação. Recomendamos o uso do Financial Reporting para consolidar orçamentos de rascunho.

Para obter mais informações, consulte [Reavaliação de moeda em uma empresa de consolidação](../general-ledger/currency-revaluation-consolidation-company.md).




[!INCLUDE[footer-include](../../includes/footer-banner.md)]
