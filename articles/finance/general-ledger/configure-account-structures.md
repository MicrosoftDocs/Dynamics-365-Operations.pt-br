---
title: Configurar estruturas de conta
description: Este artigo fornece informações sobre estruturas de contas e dimensões financeiras.
author: aprilolson
ms.date: 10/14/2022
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: LedgerEliminationRule
audience: Application User
ms.reviewer: twheeloc
ms.custom: 13131
ms.assetid: 08fd46ef-2eb8-4942-985d-40fd757b74a8
ms.search.region: Global
ms.author: aolson
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: b3fbdd6e2cac61c358848a21e1126bea900e86b2
ms.sourcegitcommit: c6c2486be2359bd30106f7f52bda788239147d8c
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/22/2022
ms.locfileid: "9713922"
---
# <a name="configure-account-structures"></a>Configurar estruturas de conta

[!include[banner](../includes/banner.md)]

As estruturas da conta usam a conta principal e as dimensões financeiras para criar um conjunto de regras que determina a ordem e os valores usados ao inserir o número de conta. Você pode configurar quantas estruturas de contas você precisar para sua empresa. As estruturas de conta são atribuídas à configuração do razão da empresa para que possam ser compartilhadas.

Ao criar uma estrutura da conta, o número máximo de segmentos é 11. Se você precisar de mais de 11 segmentos, avalie bem a configuração e os requisitos, porque isso afetará a experiência do usuário. Considere se um segmento pode ser obtido de um cenário de relatório usando uma hierarquia, em vez de durante a entrada de dados, usando um campo definido pelo usuário. Por exemplo, se quiser relatar a localização, mas puder configurá-la por departamento ou centro de custos, você não precisará do local como uma dimensão financeira. Se após avaliação você determinar mais de 11 segmentos necessários, você pode adicionar segmentos adicionais usando regras avançadas.

As estruturas de conta exigem a conta principal. A conta principal não precisa ser o primeiro segmento da estrutura, mas ela identifica qual estrutura de conta está sendo usada na entrada do número da conta. Em função disso, um valor de conta principal só pode existir em uma estrutura atribuída ao razão de forma que não haja sobreposição. Depois que a estrutura da conta for identificada, a lista de valores permitidos é filtrada para orientar o usuário através da seleção somente de valores de dimensão, reduzindo a possibilidade de uma entrada de diário incorreta.

> [!NOTE] 
> Se planejar o orçamento com uma dimensão financeira, ela precisará ser parte de uma estrutura da conta. Atualmente, o orçamento não utiliza regras avançadas.

## <a name="example"></a>Exemplo
Para ilustrar uma prática recomendada para configurar uma estrutura de conta, vamos supor que uma empresa quer rastrear suas contas de balanço (100000..399999) em nível de conta e dimensão financeira da unidade de negócios. Para contas de receita e de despesas (400000..999999) elas rastreiam as dimensões financeiras Unidade de Negócio, Departamento e Centro de Custo. Se fizerem uma venda, também rastreiam o Cliente. Com base nesse cenário, recomendamos ter duas estruturas de conta atribuídas ao razão da empresa, uma para contas de Balanço e outra para contas de Lucros e Perdas. Para otimizar a experiência e a validação do usuário, o cliente deve ter uma regra avançada que somente é usada quando uma conta de vendas for usada.

**Estrutura de conta de balanço**

|Conta principal          | Unidade de negócios    |
|----------------------|-----------|
|100000..399999 | *;"&nbsp;"|

**Estrutura de conta de lucros e perdas**

|Conta principal          | Unidade de negócios    |Departamento          | Centro de custos    | &nbsp; |
|----------------------|------------------|--------------------|-----------|---|
|400000..999999 | \*;"&nbsp;"| \*;"&nbsp;"| \*;"&nbsp;"| \*;"&nbsp;"|

**Regra avançada para adicionar um cliente**

Critérios: Onde a conta principal estiver entre 400000 e 499999, então adicione o cliente. Não pode ficar em branco.

|Cliente         |
|-----------------|
|\* |

Neste exemplo simplificado, todos os valores em branco são permitidos, por isso, \* e "&nbsp;" são usados.

## <a name="segments-and-allowed-values"></a>Segmentos e valores permitidos
A seção **Segmentos** e **Detalhes de valores permitido** fornece uma grade com a experiência para inserir as regras que serão seguidas na validação durante a postagem. Você pode digitar diretamente nas células na grade, importá-la do Excel ou usar a seção **Detalhes de valores permitidos** para guiá-lo através delas.

A seção **Detalhes de valores permitidos** o orienta pelos critérios de criação usando os **Operadores** como por exemplo, começa com, está entre, inclui e muitos outros.

[![Permitir valores.](./media/account.png)](./media/account.png) 

Os valores permitidos serão padronizados em um diário ou página de entrada de distribuição contábil quando não houver outros valores possíveis para selecionar de acordo com a configuração da estrutura de conta.

Veja um exemplo da **Estrutura de conta de lucros e perdas**.

|Conta principal          | Unidade de negócios    |Departamento          | Centro de custos    |
|----------------------|-----------|----------------------|-----------|
|400000..999999 | 002 | 022 | 014 |

Ao inserir um diário e selecionar uma conta no intervalo de lucros e perdas, a seleção da unidade de negócios "002" fará com que os valores 022 e 014 sejam o padrão no controle de conta. Tal comportamento também ocorrerá com a página de distribuição contábil. 

## <a name="more-than-seven-criteria-needed"></a>É preciso ter mais de 7 critérios

Se tiver mais de 7 critérios que são necessários, você poderá continuar adicionando-os na próxima linha. Você observará ao trabalhar na seção **Detalhes de valores permitidos** que os critérios **+Adicionar novo** não estão mais ativos depois que o sétimo critério for inserido. Isso ocorre devido a muitos fatores, como: 
 - Largura da coluna 
 - Como os dados são armazenados 
 - Desempenho do controle **Detalhes do valor permitido**
 - Usabilidade  

> [!NOTE]
> Não há suporte para um upgrade do Microsoft Dynamics AX 2012 em que é possível especificar mais de 7 critérios. É preciso fazer a correção antes de completar o upgrade para os os aplicativos de finanças e operações. 

Para continuar adicionando critérios adicionais, clique em **Duplicar no Segmento** e **Seção de valores permitidos**. Isso copiará os critérios para uma nova linha. Em seguida, você pode digitar ou modificar a seção **Detalhes de valores permitido**.

## <a name="best-practices"></a>Práticas Recomendadas
Configure suas estruturas de conta seguindo algumas práticas recomendadas. Entretanto, esta é apenas uma orientação para uma discussão holística sobre sua empresa, plano de crescimento e plano de manutenção sejam consideradas como parte dessa discussão.

- A conta principal deve ser a primeira ou estar próxima do início da estrutura de conta para que a experiência do usuário na entrada de conta seja a mais intuitiva possível.
  
  - Verifique se as soluções de terceiros que você pretende usar dão suporte à conta principal na primeira posição.

- Reutilize as estruturas de contas o quanto possível para reduzir a manutenção em todas as suas entidades legais.

- Por variações em entidades legais, use regras avançadas de forma que as estruturas de conta possam ser reutilizadas.

- Ao definir valores permitidos, use intervalos e curingas, o máximo que puder. Isso não só permite que você cresça e mude sem manutenção, mas o sistema também funciona de maneira melhor com essa configuração.

- Coloque não apenas um asterisco para cada segmento na estrutura da conta e não confie unicamente em regras avançadas. Isso pode ser difícil de gerenciar e muitas vezes leva a erros do usuário durante a manutenção que podem tornar o sistema incapaz de lançar.

## <a name="account-structure-activation"></a>Ativação da estrutura de conta
Quando estiver satisfeito com sua nova configuração ou com uma alteração em uma estrutura de conta, você deverá ativá-la. Se uma estrutura de conta for atribuída a um razão, essa ativação pode ser um processo de execução longa, pois todas as transações não lançadas no sistema devem ser sincronizadas com a nova estrutura. As alterações da estrutura de conta não afetam as transações lançadas. A partir da versão 10.0.31 do aplicativo, o gerenciamento de recursos passa a contar com um novo recurso chamado de **Melhoria no desempenho da ativação da estrutura de conta**. Para mais informações sobre esse novo recurso para a ativação da estrutura da conta, consulte [Melhoria no desempenho da ativação da estrutura de conta](account-structure-improvement.md). 

Para obter mais informações, consulte [Planejar seu plano de contas](plan-chart-of-accounts.md), [Dimensões financeiras](financial-dimensions.md) e [Inserir a conta e as combinações de dimensões (controle segmentado de entradas)](enter-account-dimension-combinations-segmented-entry-control.md).


[!INCLUDE[footer-include](../../includes/footer-banner.md)]
