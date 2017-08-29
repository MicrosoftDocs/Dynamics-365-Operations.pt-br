---
title: "Dimensões financeiras e lançamento"
description: "Ao planejar e configurar seu plano de contas, você deve considerar como os diversos componentes funcionarão em conjunto quando você lançar um documento ou um diário. Esses componentes incluem estruturas de conta, regras avançadas e dimensões fixas e de balanceamento. Este tópico explica o que cada componente é e como eles funcionam em conjunto."
author: aprilolson
manager: AnnBe
ms.date: 08/04/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: 
audience: Application User
ms.reviewer: twheeloc
ms.search.scope: Core, AX 7.0.0, Operations, UnifiedOperations
ms.custom: 14091
ms.assetid: c64eed1d-df17-448e-8bb6-d94d63b14607
ms.search.region: Global
ms.author: aolson
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: July 2017 update
ms.translationtype: HT
ms.sourcegitcommit: addd8c6956a19828687fbda606a0531c0c5decec
ms.openlocfilehash: 6d47aa7df47f498fa751428fe659f0500dd00fc5
ms.contentlocale: pt-br
ms.lasthandoff: 08/09/2017

---

# <a name="financial-dimensions-and-posting"></a>Dimensões financeiras e lançamento 

[!include[banner](../includes/banner.md)]

Ao planejar e configurar seu plano de contas, você deve considerar como os diversos componentes funcionarão em conjunto quando você lançar um documento ou um diário. Esses componentes incluem estruturas de conta, regras avançadas e dimensões fixas e de balanceamento. Este tópico explica o que cada componente é e como eles funcionam em conjunto.

## <a name="chart-of-accounts-and-financial-dimension-components"></a>Plano de contas e componentes de dimensão financeira

O Microsoft Dynamics 365 for Finance and Operations, edição Enterprise, tem um sistema sofisticado baseado em regras para definir combinações válidas de contas principais e valores de dimensões financeiras. Esta seção fornece uma breve visão geral da funcionalidade de cada componente e explica onde você pode encontrar o componente.

### <a name="account-structures"></a>Estruturas de conta

Uma estrutura de conta é necessária quando você configura seu razão. Você deve definir e ativar pelo menos uma estrutura de conta e atribuí-la ao razão. A estrutura de conta deve incluir a conta principal. Você pode definir a ordem dos segmentos que funciona melhor para a empresa. Após a conta principal ser definida, o sistema pode determinar a estrutura de conta usada. Ao inserir a conta principal primeiro ou próximo à frente de uma estrutura, você pode ajudar a limitar os valores, além de ajudar o sistema a aplicar o último valor válido conhecido como um valor padrão. Você pode ter até 10 dimensões financeiras adicionais na estrutura de conta. A estrutura de conta define quais valores de dimensão são válidos em combinação com outros valores. Ela também define se os valores de dimensão devem ser inseridos.

### <a name="advanced-rules"></a>Regras avançadas

As regras avançadas são um componente opcional quando você configura o plano de contas. Você pode adicionar quantas regras avançadas desejar a uma estrutura de conta. As regras avançadas geralmente são usadas para lidar com cenários em que as dimensões financeiras adicionais devem ser rastreadas quando critérios específicos são atendidos. Por exemplo, se você usa uma conta de despesas de viagem, poderá rastrear informações adicionais, como o evento para o qual o funcionário está viajando. Se houver várias regras avançadas, elas serão aplicadas em ordem alfabética, com base nos nomes das regras. Os segmentos que uma regra adiciona podem ser aplicados apenas depois dos segmentos da estrutura de conta.

### <a name="balancing-dimension"></a>Dimensão de balanço

Opcionalmente, você pode definir uma dimensão financeira de balanço. Na página **Razão**, defina a dimensão financeira a ser balanceada. Sempre que as transações forem lançadas nessa dimensão financeira, o sistema criará automaticamente e lançará entradas para balancear a dimensão financeira.

### <a name="defaultfixed-financial-dimensions-on-the-main-account"></a>Dimensões financeiras padrão/fixas na conta principal

As dimensões padrão vêm de vários locais, como registros mestres (por exemplo, registros de cliente ou fornecedor), cabeçalhos de documento e da conta principal. Este tópico se concentra nas dimensões padrão na conta principal por entidade legal. É possível definir se uma conta principal tem um valor **Não fixa** ou **Fixa** para cada dimensão financeira usada em todas as estruturas de conta do razão. Se uma dimensão financeira estiver definida como **Não fixa**, ela usará um valor padrão, mas esse valor poderá ser substituído. Esse comportamento aplica-se a todos os valores padrão no sistema, até os valores padrão que vêm de registros mestres. Se uma dimensão financeira estiver definida como um valor **Fixa**, esse valor sempre será aplicado, não importa se ele veio de um valor padrão ou se o usuário o inseriu.

## <a name="order-in-which-default-dimensions-are-applied-during-posting"></a>Ordem em que as dimensões padrão são aplicadas durante o lançamento

As pessoas frequentemente têm dúvidas sobre a ordem em que os diversos elementos são executados. É muito importante que você compreenda a ordem em que as dimensões padrão são aplicadas, pois esse comportamento afeta a abordagem que você adota para a configuração.

> [!NOTE]
> Estas informações só se aplicam aos aplicativos de dimensões padrão no aplicativo. Se você importa dados usando o Microsoft Excel ou a Estrutura de Gerenciamento de Dados, o comportamento é diferente.

### <a name="example-1"></a>Exemplo 1

**Estrutura da conta**

| Conta principal            | Unidade de negócios           | Departamento              | Centro de custos             |
|-------------------------|-------------------------|-------------------------|-------------------------|
| Todos os valores são permitidos. | Todos os valores são permitidos. | Todos os valores são permitidos. | Todos os valores são permitidos. |

**Conta principal**

| Conta principal | Nome          | Pessoa jurídica em geral | Departamento                                 |
|--------------|---------------|--------------|--------------------------------------------|
| 401100       | Vendas do produto | USMF         | Fixa – 022 Departamento de vendas e marketing |

A ilustração a seguir mostra a dimensão padrão fixa configurada na conta principal 401100.

[![Dimensões financeiras padrão](./media/default-dimensions.png)](./media/default-dimensions.png)

Para este exemplo básico, inseriremos um diário geral em que a dimensão do departamento é configurada para usar o valor padrão **023** (Operações). Inseriremos e lançaremos uma conta contábil. A ilustração a seguir mostra a dimensão financeira padrão no cabeçalho de contabilidade.

[![Diários Gerais](./media/general-journal.png)](./media/general-journal.png)

A dimensão padrão no cabeçalho do diário fará com que o departamento 023 seja aplicado por padrão à linha da conta de vendas, A ilustração a seguir mostra a linha do diário geral, em que o valor da dimensão padrão **023** do cabeçalho é aplicado.

[![Comprovante de diário](./media/journal-voucher.png)](./media/journal-voucher.png)

No entanto, quando a linha é lançada, a dimensão fixa é aplicada e a linha é lançada no departamento 022. A ilustração a seguir mostra o comprovante lançado, onde a dimensão fixa é aplicada à conta de vendas.

[![Comprovantes de transações](./media/voucher-transactions.png)](./media/voucher-transactions.png)

### <a name="example-2"></a>Exemplo 2

Este exemplo usa a mesma configuração do primeiro exemplo. No entanto, adicionaremos um segundo componente e usaremos a dimensão Departamento como uma dimensão de balanço. Na ilustração a seguir, o **Departamento** é configurado como a dimensão financeira de balanço do razão USMF.

[![Razão](./media/ledger.png)](./media/ledger.png)

Quando a mesma configuração do cabeçalho de diário é usada e a mesma transação é lançada, a dimensão fixa é aplicada primeiro. Depois, a lógica de balanço é aplicada para ajudar a garantir que cada departamento tenha uma entrada balanceada. A ilustração a seguir mostra as transações de comprovantes que incluem a entrada de balanceamento depois que a dimensão fixa é aplicada.

[![Comprovantes de transações](./media/voucher-transactions2.png)](./media/voucher-transactions2.png)

### <a name="example-3"></a>Exemplo 3

Neste exemplo, adicionaremos uma regra avançada. A regra avançada especifica que, se a conta de vendas 401100 e o departamento 022 (Vendas e marketing) forem usados, o sistema deverá rastrear um segmento adicional denominado Cliente.

Este exemplo é importante devido à ordem. A estrutura de conta é determinada após a conta principal ser inserida. Se você fizer referência à configuração da estrutura de conta, o sistema poderá determinar que a conta principal, a unidade de negócios, o departamento e o centro de custo são relevantes. Neste ponto, a regra avançada não foi disparada, pois as dimensões fixas não são aplicadas até que as dimensões padrão sejam aplicadas ao comprovante do diário durante o lançamento. Na ilustração a seguir, o segmento Cliente não está presente, pois os critérios para a regra avançada não foram atendidos.

[![Conta contábil](./media/drop-down.png)](./media/drop-down.png)

O lançamento não terá êxito, pois a dimensão fixa foi aplicada no final do processo. A validação da dimensão determina que o segmento Cliente será necessário se a conta principal for 401100 e o departamento for 022. O lançamento não pode ocorrer devido ao erro de validação. A ilustração a seguir mostra a mensagem exibida depois que a validação da dimensão determina que o segmento Cliente é necessário.

[![Detalhes da mensagem](./media/message.png)](./media/message.png)

Neste exemplo, você deve substituir o valor padrão de forma que a regra avançada seja disparada e você possa inserir o segmento Cliente. No entanto, essa solução não é sempre possível, e alguns usuários desconhecem as regras de lançamento. Portanto, é importante que você compreenda a ordem em que as dimensões padrão são aplicadas quando você configura o plano de contas.

Para obter o que deseja neste exemplo, você pode alterar a configuração de várias maneiras. Por exemplo, você pode criar uma nova estrutura de conta para as contas de venda e incluir o segmento Cliente na estrutura. Você também pode adicionar mais linhas a uma estrutura de conta existente, e especificar a conta principal e os valores do departamento válido. Na estrutura de cliente adicional, pode ser útil ter uma estrutura de conta separada das contas de vendas em que o segmento Cliente está presente.

## <a name="additional-resources"></a>Recursos adicionais 

Alguns dos recursos a seguir referem-se a uma versão anterior do Finance and Operations. No entanto, muitas das informações sobre o aplicativo de dimensões padrão e muitos dos conceitos são os mesmos na versão anterior, e as referências ainda são válidas.

[Diários equilibrados para contabilidade interunidade](example-balanced-journals-interunit-accounting.md)

[Planejar seu plano de contas](plan-chart-of-accounts.md) 

[Planejando o plano de contas no AX 2012 (blog)](https://blogs.msdn.microsoft.com/axsa/2014/06/12/planning-your-chart-of-accounts-in-ax-2012-part-1-of-7/): esse link conduz à parte 1 de uma série de sete partes.

[Padronização de dimensão em distribuições contábeis](https://blogs.msdn.microsoft.com/ax_gfm_framework_team_blog/2013/12/16/dimension-defaulting-in-accounting-distributions-part-1-introduction/)

[Padronização de dimensão na estrutura Dimensões](https://blogs.msdn.microsoft.com/ax_gfm_framework_team_blog/2014/09/)

