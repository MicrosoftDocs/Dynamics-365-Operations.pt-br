---
title: Configurar taxas
description: As taxas no Microsoft Dynamics 365 Human Resources definem o quanto empregadores e funcionários contribuem para um benefício.
author: andreabichsel
ms.date: 06/25/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: BenefitWorkspace, HcmBenefitSummaryPart
audience: Application User
ms.search.scope: Human Resources
ms.custom: 7521
ms.assetid: ''
ms.search.region: Global
ms.author: anbichse
ms.search.validFrom: 2020-02-03
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: da006516f8b3a1d8eb0d4963187d01308f059619f95a52410391d9501aafbbc1
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/05/2021
ms.locfileid: "6732696"
---
# <a name="configure-rates"></a>Configurar taxas

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

As taxas definem o quanto empregadores e funcionários contribuem para um benefício. O valor pode ser uma quantia ou um número de créditos flexíveis, dependendo da sua configuração.

Use taxas para determinar o quanto funcionários e empregadores pagam por cada benefício, com base em vários fatores. As taxas de cobertura têm data efetiva para que você possa manter um registro histórico das taxas. 

## <a name="set-up-rates"></a>Configurar taxas

1. No espaço de trabalho **Gerenciamento de benefícios**, em **Configuração**, selecione **Taxas**.

2. Selecione **Novo**.

3. Especifique valores para os seguintes campos:

   | Campo | Descrição |
   | --- | --- |
   | **Taxa** | Um nome exclusivo que identifica a taxa de benefício. |
   | **Descrição** | Uma descrição da taxa de benefício. |
   | **Efetivação** | A data em que a taxa entra em vigor. A data atual do sistema é o valor padrão. Esta data deve ser igual ou anterior ao período do benefício. Uma boa prática é definir esta data como a data do plano de benefícios. |
   | **Vencimento** | A data final da taxa. 12/31/2154 (que representa nunca) é o valor padrão. |
   | **Usar camadas** |  Use este campo se você tiver uma lógica que deve ser usada para determinar uma taxa. Por exemplo, se uma taxa deve aumentar com base na idade, selecione um valor aqui. Selecione **Camada única** para uma taxa de benefício de camada única ou **Camada dupla** para uma taxa de benefício de camada dupla. Um exemplo de camada dupla é uma camada baseada no sexo e na idade. Depois de selecionar um valor, selecione **Ações** e, em seguida, selecione **Taxas de camadas**. Se você tiver uma taxa fixa que não muda, deixe este campo em branco. |
   | **Frequência de pagamento** | Especifique a frequência de pagamento da taxa de prêmio de benefício ao provedor de benefícios. As taxas inseridas na página descrita posteriormente neste tópico se basearão na frequência de pagamento que você especificar aqui. Por exemplo, se você inserir **Mensalmente** neste campo e inserir uma taxa de funcionário de **US$ 100**, pressupõe-se que o benefício custará ao funcionário US$ 100 por mês. No entanto, um funcionário pode ser pago duas vezes por mês, com base na frequência de pagamento de benefícios definida no registro do funcionário. Nesse caso, quando o funcionário se inscreve no autoatendimento para funcionários, o valor que ele paga será de US$ 50, pois a taxa que o autoatendimento para funcionários mostra é baseada na frequência de pagamento do funcionário. |
   | **Arredondamento da taxa de frequência de pagamento** | Os métodos para arredondar a taxa são: Padrão, Truncado, Normal, Para Baixo e Para Cima. </br></br><ul><li>**Padrão** – Sempre arredondar. Por exemplo, 10,611 será arredondado para 10,62. -10,231 será arredondado para -10,23. </li><li>**Truncado** – Sempre arredondar para baixo. Por exemplo, 10,619 será arredondado para 10,61. -10,231 será arredondado para -10,24. </li><li>**Normal** – Os valores decimais que terminam em 5 ou superior serão arredondados em diferença de zero. Os valores decimais que terminam em 4 ou menos serão arredondados de encontro a zero. Por exemplo, 10,615 será arredondado para 10,62. -10,235 será arredondado para -10,24. 10,614 será arredondado para 10,61. -10,234 será arredondado para -10,23. </li><li>**Para baixo** – Arredondar em direção a zero. Por exemplo, 10,619 será arredondado para 10,61. -10,231 será arredondado para -10,23. </li><li>**Para cima** – Arredondar em diferença de zero. Por exemplo, 10,619 será arredondado para 10,62. -10,231 será arredondado para -10,24. |
   | **Valor do funcionário não fumante** | O valor que o provedor de benefícios cobra de um funcionário não fumante. Esse é o valor que o empregador paga ao fornecedor de benefícios e deve se basear na frequência de pagamento para a configuração de taxa. |
   | **Valor do empregador não fumante** | O valor que o provedor de benefícios cobra de um funcionário não fumante. Este é o valor que o empregador paga ao fornecedor de benefícios e deve se basear na frequência de pagamento para a configuração de taxa. |
   | **Valor do funcionário fumante** | O valor que o provedor de benefícios cobra de um funcionário que fuma. Esse é o valor que o empregador paga ao fornecedor de benefícios e deve se basear na frequência de pagamento para a configuração de taxa. |
   | **Valor do empregador fumante** | O valor que o provedor de benefícios cobra de um funcionário que fuma. Esse é o valor que o empregador paga ao fornecedor de benefícios e deve se basear na frequência de pagamento para a configuração de taxa. |
   | **Valor administrativo** | O valor administrativo cobrado por um administrador de terceiros. Este é o valor que o empregador paga ao administrador de terceiros e deve se basear na frequência de pagamento para a configuração de taxa. |
   | **Taxa de crédito flexível** | O número de créditos flexíveis dos custos de benefício. Isso só se aplica a taxas para planos de benefícios associados a programas de crédito flexível. Se você usar taxas de camadas, a taxa de crédito flexível será definida Em Ações > Taxas de camadas. |
   | **Alterar a data de efetivação** | A data na qual a alteração da taxa de benefício entra em vigor. O sistema alterará automaticamente a taxa de benefícios e atualizará todos os planos de benefícios associados a essa taxa, desde que você execute o processamento da atualização de alterações de taxas. Não defina essa data, a menos que deseje que o sistema atualize automaticamente os planos de benefícios dos funcionários com base nessa taxa. Isso é normalmente reservado para processamento automático futuro de alteração de taxa. A data de efetivação da alteração deve estar entre as datas de efetivação e de vencimento. |
   | **Alteração de taxa concluída** | A caixa de seleção **Alteração de taxa concluída** será selecionada automaticamente após as alterações de taxa de benefícios serem concluídas pelo processamento de atualização de alterações de taxa. |

4. Para controlar e manter alterações na configuração das taxas de benefício, selecione **Ações** e **Manter versões**.

5. Selecione **Salvar**. 

## <a name="set-up-tier-rates"></a>Configurar taxas de camada

Você poderá usar as taxas de camada na configuração de taxa se a taxa variar dependendo de diversos fatores. Por exemplo, você pode configurar taxas de camadas para dizer que, se sua idade for até 34,99, o valor de não fumante será 2. Se a idade for de até 39,99, o valor de não fumante será 3.

Você também pode usar camadas duplas. Se você selecionar **Camada dupla** para o valor **Usar camadas** no formulário **Configuração de taxa**, poderá definir taxas com base em duas dimensões. Por exemplo, você pode configurar um sistema de camada dupla para dizer que, se você for homem e tiver até 34,99 anos de idade, o valor de não fumante será 2. Se você for homem e sua idade for de até 39,99, o valor de não fumante será 3. Se você for mulher e sua idade for de até 34,99, o valor de não fumante será 1,8. Se você for mulher e sua idade for de até 39,99, o valor de não fumante será 2,8.

> [!IMPORTANT]
> No registro de trabalhador, uma opção em **Informações pessoais** é usada para indicar se o funcionário é um fumante. Se o funcionário for registrado como um fumante, a taxa de fumantes será usada. (A indicação de fumante nunca é mostrada para o funcionário.)
   
1. No espaço de trabalho **Gerenciamento de benefícios**, em **Configuração**, selecione **Taxas**.

2. Selecione uma ou mais taxas na lista, selecione **Ações** e, em seguida, **Taxas de camadas**.

3. Selecione **Novo**.

3. Especifique valores para os seguintes campos:

   | Campo | descrição |
   | --- | --- | 
   | **Descrição** | O valor do campo **Descrição** é aplicado com base na descrição no registro de configuração da taxa. Isso ajuda a identificar a qual configuração de taxa as taxas de camadas estão vinculadas. |
   | **Código de camada** | Selecione um código de camada. Os códigos de camada são definidos no formulário códigos de camada. O sistema exibirá automaticamente a descrição do código de camada na grade à esquerda. |
   | **Tipo de camada** | Especifica o campo a ser usado como um critério de seleção para o processo de cálculo da taxa de camada. Por exemplo:</br></br><ul><li>Se for utilizada a **Idade**, o sistema usará a data de nascimento do funcionário no processo de cálculo da taxa de benefícios.</li><li>Se for usado o **Salário**, o sistema usará o salário de benefício anual do funcionário no processo de cálculo da taxa de benefícios.</li><li>Se for usado o **Tipo de trabalho**, o sistema usará o registro de cargo atual ativo do funcionário para determinar o tipo de trabalho pelo registro de trabalho vinculado ao cargo.</li></ul></br></br>Os tipos de camada são **Idade**, **Salário**, **Físico**, **Sexo**, **Equivalente ao horário integral**, **Tipo de trabalho**, **Região de remuneração** e **Nível**. | 
   | **Nível** | O valor a ser usado com o tipo de camada durante o processo de cálculo da taxa de benefícios. Por exemplo:</br></br><ul><li>Se o tipo de camada for **Idade**, este será o valor de idade.</li><li>Se o tipo de camada for **Salário**, este será o valor de salário.</li><li> Se o tipo de camada for **Tipo de trabalho**, este será o tipo de trabalho.</li></ul></br></br>Com um tipo de camada de **Idade** ou **Salário**, o valor no campo **Nível** representa o limite superior da camada. Com um tipo de camada de **Tipo de trabalho**, o sistema usa uma abordagem de correspondência exata durante a seleção da taxa de camada. |
   | **Tipo de cálculo** | Especifica como usar o valor no campo valor do cálculo e qual cálculo de matemática deve ser realizado, se necessário. Se o tipo de cálculo for um valor simples, o sistema usará os campos de valor como estão. Se o tipo de cálculo for por valor de salário ou cobertura, o sistema usará o valor de cálculo e a direção de cálculo em seu cálculo de matemática.</br></br>Se o tipo de cálculo for por valor de salário, o sistema usará a seguinte equação matemática:</br></br>Salário anual de benefício dividido pelo valor do cálculo (arredondado para cima ou para baixo) multiplicado pelos valores de fumante e não fumante por funcionário ou empregador.</br></br>Se o tipo de cálculo for por valor de cobertura, o sistema usará a seguinte equação matemática:</br></br>Valor de cobertura dividido pelo valor do cálculo (arredondado para cima ou para baixo) multiplicado pelos valores de fumante e não fumante por funcionário ou empregador.</br></br>Em ambos os cálculos, a direção do cálculo é usada para determinar se é necessário arredondar o salário anual de benefício ou o valor de cobertura dividido pelo valor de cálculo para cima ou para baixo. |
   | **Valor do cálculo** | O valor a ser usado durante o processo de cálculo da taxa de benefício. Esse valor será o divisor durante o cálculo matemático da taxa de camadas. |
   | **Direção do cálculo** | A direção para a qual o valor do resultado calculado deve ser arredondado. O sistema permite três direções de cálculo: em branco (método exato), **Aumentar** e **Diminuir**.</br></br><ul><li>Se estiver em branco, o sistema usará o cálculo exato do salário/valor de cobertura dividido pelo valor do cálculo. Se esse valor tiver uma fração, o sistema usará isso em seu cálculo.</li><li>Se **Aumentar**, o sistema aumentará o cálculo matemático do valor de salário/cobertura dividido pelo valor de cálculo para o próximo inteiro, o que significa que 12,25 aumentaria para 13.</li><li>Se **Diminuir**, o sistema diminuirá o cálculo matemático do valor de salário/cobertura dividido pelo valor de cálculo para o inteiro atual, o que significa que 12,25 diminuiria para 12.</li></ul> |
   | **Valor do funcionário não fumante** | O valor que um provedor de benefícios cobra de um funcionário não fumante. Este é o valor que o empregador paga ao fornecedor de benefícios e deve se basear na frequência de pagamento para a configuração de taxa. |
   | **Valor do empregador não fumante** | O valor que um provedor de benefícios cobra de um funcionário não fumante. Este é o valor que o empregador paga ao fornecedor de benefícios e deve se basear na frequência de pagamento para a configuração de taxa. |
   | **Valor do funcionário fumante** | O valor que um provedor de benefícios cobra de um funcionário não fumante. Este é o valor que o empregador paga ao fornecedor de benefícios e deve se basear na frequência de pagamento para a configuração de taxa. |
   | **Valor do empregador fumante** | O valor que um provedor de benefícios cobra de um funcionário não fumante. Este é o valor que o empregador paga ao fornecedor de benefícios e deve se basear na frequência de pagamento para a configuração de taxa. |
   | **Valor administrativo** | O valor administrativo cobrado por um administrador de terceiros. Este é o valor que o empregador paga ao administrador de terceiros e deve se basear na frequência de pagamento para a configuração de taxa. |
   | **Taxa de não fumantes para crédito flexível** | O número de créditos flexíveis dos custos de benefício, com base no cálculo definido para o nível de camada para não fumantes. Por exemplo, se o tipo de cálculo for **por valor de cobertura**, o valor de cálculo será 10.000 e a taxa de não fumante do crédito flexível será 6; isso significa que, se um funcionário não fumante escolher US$ 10.000 de cobertura, isso custará 6 créditos flexíveis. Se escolherem US$ 20.000 de cobertura, o custo será de 12 créditos flexíveis e assim por diante. |
   | **Taxa de fumantes para o crédito flexível** | O número de créditos flexíveis dos custos de benefício, com base no cálculo definido para o nível de camada para fumantes. |

5. Selecione **Salvar**. 



[!INCLUDE[footer-include](../includes/footer-banner.md)]
