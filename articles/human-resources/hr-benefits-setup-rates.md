---
title: Configurar taxas
description: As taxas no Microsoft Dynamics 365 Human Resources definem o quanto empregadores e funcionários contribuem para um benefício.
author: andreabichsel
manager: AnnBe
ms.date: 04/06/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-human-resources
ms.technology: ''
ms.search.form: BenefitWorkspace, HcmBenefitSummaryPart
audience: Application User
ms.reviewer: anbichse
ms.search.scope: Human Resources
ms.custom: 7521
ms.assetid: ''
ms.search.region: Global
ms.author: anbichse
ms.search.validFrom: 2020-02-03
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: c90a45b79f2a383f0ace0cb07e791f6613d7a3c3
ms.sourcegitcommit: ba340f836e472f13f263dec46a49847c788fca44
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/04/2020
ms.locfileid: "3429902"
---
# <a name="configure-rates"></a>Configurar taxas

As taxas no Microsoft Dynamics 365 Human Resources definem o quanto empregadores e funcionários contribuem para um benefício. O valor pode ser um valor ou créditos flexíveis, dependendo da configuração.

Use taxas para determinar o quanto funcionários e empregadores pagam por cada benefício, com base em vários fatores. As taxas de cobertura têm data efetiva para que você possa manter um registro histórico das taxas. 

## <a name="set-up-rates"></a>Configurar taxas

1. No espaço de trabalho **Gerenciamento de benefícios**, em **Configuração**, selecione **Taxas**.

2. Selecione **Novo**.

3. Especifique valores para os seguintes campos:

   | Campo | Descrição |
   | --- | --- |
   | **Taxa** | Um nome exclusivo que identifica a taxa de benefício. |
   | **Descrição** | Uma descrição da taxa de benefício. |
   | **Efetivação** | A data em que a taxa tem efeito. A data atual do sistema é o valor padrão. 
   | **Expiração** | A data final da taxa. 12/31/2154 (que representa nunca) é o valor padrão. |
   | **Usar camadas** | A camada a ser usada para o cálculo da taxa de benefício. Uma camada única para uma taxa de benefício de camada única ou uma camada dupla para uma taxa de benefício de camada dupla. Um exemplo de uma camada dupla é uma camada com base no sexo e na idade. |
   | **Frequência de pagamento** | A frequência de pagamento que determina a frequência de pagamento da taxa de prêmio de benefício ao provedor de benefícios. Por exemplo, se a frequência de pagamento for mensal, a taxa de benefício representará o valor do pagamento mensal. |
   | **Arredondamento da taxa de frequência de pagamento** | O método para arredondar a taxa: padrão ou truncado. |
   | **Valor do funcionário não fumante** | O valor que o provedor de benefícios cobra de um funcionário não fumante. Esse é o valor que o empregador paga ao fornecedor de benefícios e deve se basear na frequência de pagamento para a configuração de taxa. |
   | **Valor do empregador não fumante** | O valor que o provedor de benefícios cobra de um funcionário não fumante. Esse é o valor que o empregador paga ao fornecedor de benefícios e deve se basear na frequência de pagamento para a configuração de taxa. |
   | **Valor do funcionário fumante** | O valor que o provedor de benefícios cobra de um funcionário que fuma. Esse é o valor que o empregador paga ao fornecedor de benefícios e deve se basear na frequência de pagamento para a configuração de taxa. |
   | **Valor do empregador fumante** | O valor que o provedor de benefícios cobra de um funcionário que fuma. Esse é o valor que o empregador paga ao fornecedor de benefícios e deve se basear na frequência de pagamento para a configuração de taxa. |
   | **Valor administrativo** | O valor administrativo cobrado por um administrador de terceiros. Esse é o valor que o empregador paga ao administrador de terceiros e deve se basear na frequência de pagamento para a configuração de taxa. |
   | **Taxa de crédito flexível** | O número de créditos flexíveis dos custos de benefício. Isso só se aplica a taxas para planos de benefícios associados a programas de crédito flexível. Se você usar taxas de camadas, a taxa de crédito flexível será definida Em Ações > Taxas de camadas. |
   | **Alterar a data de efetivação** | A data na qual a alteração da taxa de benefício entra em vigor. O sistema alterará automaticamente a taxa de benefícios e atualizará todos os planos de benefícios associados a essa taxa, desde que você execute o processamento da atualização de alterações de taxas. Não defina essa data, a menos que deseje que o sistema atualize automaticamente os planos de benefícios dos funcionários com base nessa taxa. Isso é normalmente reservado para processamento automático futuro de alteração de taxa. A data de efetivação da alteração deve estar entre as datas de efetivação e de vencimento. |
   | **Alteração de taxa concluída** | A caixa de seleção **Alteração de taxa concluída** será selecionada automaticamente após as alterações de taxa de benefícios serem concluídas pelo processamento de atualização de alterações de taxa. |

4. Para controlar e manter alterações na configuração das taxas de benefício, selecione **Ações** e **Manter versões**.

5. Selecione **Salvar**. 

## <a name="set-up-tier-rates"></a>Configurar taxas de camada

Você poderá usar as taxas de camada na configuração de taxa se a taxa variar dependendo de diversos fatores. Por exemplo, você pode configurar taxas de camadas para dizer que, se sua idade for até 34,99, o valor de não fumante será 2. Se a idade for de até 39,99, o valor de não fumante será 3.

Você também pode usar camadas duplas. Se você selecionar **Camada dupla** para o valor **Usar camadas** no formulário **Configuração de taxa**, poderá definir taxas com base em duas dimensões. Por exemplo, você pode configurar um sistema de camada dupla para dizer que, se você for homem e tiver até 34,99 anos de idade, o valor de não fumante será 2. Se você for homem e sua idade for de até 39,99, o valor de não fumante será 3. Se você for mulher e sua idade for de até 34,99, o valor de não fumante será 1,8. Se você for mulher e sua idade for de até 39,99, o valor de não fumante será 2,8.

1. No espaço de trabalho **Gerenciamento de benefícios**, em **Configuração**, selecione **Taxas**.

2. Selecione uma ou mais taxas na lista, selecione **Ações** e, em seguida, **Taxas de camadas**.

3. Selecione **Novo**.

3. Especifique valores para os seguintes campos:

   | Campo | Descrição |
   | --- | --- | 
   | **Descrição** | O valor do campo Descrição será aplicado a partir da descrição no registro de configuração da taxa. Isso ajuda a identificar a qual configuração de taxa as taxas de camadas estão vinculadas. |
   | **Código de camada** | Selecione um código de camada. Os códigos de camada são definidos no formulário códigos de camada. O sistema exibirá automaticamente a descrição do código de camada na grade à esquerda. |
   | **Tipo de camada** | Especifica o campo a ser usado como um critério de seleção para o processo de cálculo da taxa de camada. Por exemplo:</br></br><ul><li>Se a idade for usada, o sistema usará a data de nascimento do funcionário no processo de cálculo da taxa de benefícios.</li><li>Se o salário for usado, o sistema usará o salário de benefício anual do funcionário no processo de cálculo da taxa de benefícios.</li><li>Se o tipo de trabalho for usado, o sistema usará o registro de posição ativo atual do funcionário para determinar o tipo de trabalho pelo registro de trabalho vinculado à posição.</li></ul></br></br>Os tipos de camada são idade, salário, físico, sexo, equivalente ao horário integral, tipo de trabalho, região de remuneração e nível. | 
   | **Nível** | O valor a ser usado com o tipo de camada durante o processo de cálculo da taxa de benefícios. Por exemplo:</br></br><ul><li>Se o tipo de camada for idade, este será o valor de idade.</li><li>Se o tipo de camada for salário, este será o valor de salário.</li><li> Se o tipo de camada for tipo de trabalho, este será tipo de trabalho.</li></ul></br></br>Com um tipo de camada de idade ou salário, o sistema usa uma abordagem crescente durante a seleção de taxa de níveis, o que significa que o valor no campo nível representa o limite inferior da camada. Com um tipo de camada de tipo de trabalho, o sistema usa uma abordagem de correspondência exata durante a seleção de taxa de camada. |
   | **Tipo de cálculo** | Especifica como usar o valor no campo valor do cálculo e qual cálculo de matemática deve ser realizado, se necessário. Se o tipo de cálculo for um valor simples, o sistema usará os campos de valor como estão. Se o tipo de cálculo for por valor de salário ou cobertura, o sistema usará o valor de cálculo e a direção de cálculo em seu cálculo de matemática.</br></br>Se o tipo de cálculo for por valor de salário, o sistema usará a seguinte equação matemática:</br></br>Salário anual de benefício dividido pelo valor do cálculo (arredondado para cima ou para baixo) multiplicado pelos valores de fumante e não fumante por funcionário ou empregador.</br></br>Se o tipo de cálculo for por valor de cobertura, o sistema usará a seguinte equação matemática:</br></br>Valor de cobertura dividido pelo valor do cálculo (arredondado para cima ou para baixo) multiplicado pelos valores de fumante e não fumante por funcionário ou empregador.</br></br>Em ambos os cálculos, a direção do cálculo é usada para determinar se é necessário arredondar o salário anual de benefício ou o valor de cobertura dividido pelo valor de cálculo para cima ou para baixo. |
   | **Valor do cálculo** | O valor a ser usado durante o processo de cálculo da taxa de benefício. Esse valor será o divisor durante o cálculo matemático da taxa de camadas. |
   | **Direção do cálculo** | A direção (aumentar ou diminuir) em que o valor do resultado calculado deve ser arredondado. O sistema dá suporte a três direções de cálculo: em branco (método exato), aumentar e diminuir.</br></br><ul><li>Se estiver em branco, o sistema usará o cálculo exato do salário/valor de cobertura dividido pelo valor do cálculo. Se esse valor tiver uma fração, o sistema usará isso em seu cálculo.</li><li>Se aumentar, o sistema aumentará o cálculo matemático do valor de salário/cobertura dividido pelo valor de cálculo para o próximo inteiro, o que significa que 12,25 aumentaria para 13.</li><li>Se diminuir, o sistema diminuirá o cálculo matemático do valor de salário/cobertura dividido pelo valor de cálculo para o inteiro atual, o que significa que 12,25 diminuiria para 12.</li></ul> |
   | **Valor do funcionário não fumante** | O valor que um provedor de benefícios cobra de um funcionário não fumante. Esse é o valor que o empregador paga ao fornecedor de benefícios e deve se basear na frequência de pagamento para a configuração de taxa. |
   | **Valor do empregador não fumante** | O valor que um provedor de benefícios cobra de um funcionário não fumante. Esse é o valor que o empregador paga ao fornecedor de benefícios e deve se basear na frequência de pagamento para a configuração de taxa. |
   | **Valor do funcionário fumante** | O valor que um provedor de benefícios cobra de um funcionário não fumante. Esse é o valor que o empregador paga ao fornecedor de benefícios e deve se basear na frequência de pagamento para a configuração de taxa. |
   | **Valor do empregador fumante** | O valor que um provedor de benefícios cobra de um funcionário não fumante. Esse é o valor que o empregador paga ao fornecedor de benefícios e deve se basear na frequência de pagamento para a configuração de taxa. |
   | **Valor administrativo** | O valor administrativo cobrado por um administrador de terceiros. Esse é o valor que o empregador paga ao administrador de terceiros e deve se basear na frequência de pagamento para a configuração de taxa. |
   | **Taxa de não fumantes para crédito flexível** | O número de créditos flexíveis dos custos de benefício, com base no cálculo definido para o nível de camada para não fumantes. Por exemplo, se o tipo de cálculo for **por valor de cobertura**, o valor de cálculo será 10.000 e a taxa de não fumante do crédito flexível será 6; isso significa que, se um funcionário não fumante escolher US$ 10.000 de cobertura, isso custará 6 créditos flexíveis. Se escolherem US$ 20.000 de cobertura, o custo será de 12 créditos flexíveis e assim por diante. |
   | **Taxa de fumantes para o crédito flexível** | O número de créditos flexíveis dos custos de benefício, com base no cálculo definido para o nível de camada para fumantes. |

5. Selecione **Salvar**. 
