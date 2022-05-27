---
title: Como configurar dimensões financeiras de saldo?
description: Este tópico descreve as opções para configurar e usar o recurso Dimensão financeira de balanceamento.
author: kweekley
ms.date: 08/25/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: DimensionDetails
audience: Application User
ms.reviewer: kfend
ms.search.region: Global
ms.author: kweekley
ms.search.validFrom: 2021-08-17
ms.dyn365.ops.version: 10.0.210
ms.openlocfilehash: cb3033a615200a358c1b28b0991bae4b84470ae0
ms.sourcegitcommit: e09f5c6d78d7942af950ae3f6407df2fedceeba4
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/06/2022
ms.locfileid: "8720101"
---
# <a name="how-do-i-set-up-balancing-financial-dimensions"></a>Como configurar dimensões financeiras de saldo?

[!include [banner](../includes/banner.md)]

Este tópico descreve as opções para configurar e usar o recurso Dimensão financeira de balanceamento.

## <a name="symptom"></a>Sintoma

Há duas opções para configurar dimensões financeiras de saldo. A primeira opção é usar o campo **Dimensão financeira de balanceamento** na página de configuração **Razão** (**Contabilidade \> Configuração do razão \> Razão**). A segunda opção é usar o campo **Exigir a dimensão a ser balanceada** na página **Dimensões financeiras** (**Contabilidade > Plano de contas \> Dimensões \> Dimensões financeiras**). Este tópico explica a diferença entre essas duas opções.

## <a name="resolution"></a>Resolução

As organizações normalmente usam dimensões de balanceamento para gerar um balanço que esteja balanceado no nível de dimensão financeira. Habilitar qualquer um dos recursos não trará dimensões lançadas e desbalanceadas para o balanço. Primeiro, você deve inserir as entradas de ajuste manualmente para trazer o balanço ao saldo antes de habilitar qualquer um dos recursos.

As duas opções são mutuamente exclusivas. A opção usada por sua organização deve se basear nas suas necessidades comerciais. Geralmente, ouvimos clientes que definem a dimensão de balanceamento na configuração do razão e na configuração da dimensão financeira e, em seguida, concluem algumas ou todas as configurações adicionais necessárias. No entanto, eles ainda não podem ser lançados devido a um desbalanceamento no nível da dimensão financeira.

As seções a seguir descrevem as duas opções e explicam como configurá-las.

### <a name="ledger--balancing-financial-dimension"></a>Razão – dimensão financeira de balanceamento

A dimensão de balanceamento na página configuração **Razão** é usada para habilitar a contabilidade interunidade. Siga estas etapas para ativar a funcionalidade.

1. Determine qual dimensão financeira será a dimensão de balanceamento.

    - Essa funcionalidade permite selecionar somente uma dimensão financeira como a dimensão de balanceamento.
    - Ainda não selecione a dimensão na página de configuração **Razão**.
    - Verifique se o balanço já está balanceado para a dimensão financeira selecionada.

2. Atualize a estrutura de conta para a dimensão financeira de balanceamento.

    - A dimensão financeira de balanceamento deve ser incluída em todas as estruturas de conta que são atribuídas ao razão.
    - A dimensão financeira não deve permitir espaços em branco na estrutura de conta. Essa restrição garante que cada entrada contábil lançada na Contabilidade contenha um valor de dimensão financeira. Uma dimensão em branco não é válida quando são usadas balanceamento de dimensões.

3. Na página **Contas para transações automáticas** (**Contabilidade \> Configuração de lançamento \> Contas para transações automáticas**), defina as contas de débito e crédito principais de interunidade.
4. Na página de configuração **Razão** (**Contabilidade \> Configuração do razão \> Razão**), no campo **Dimensão financeira de balanceamento**, selecione uma dimensão financeira a ser usada no balanceamento.

Se a dimensão financeira selecionada não estiver balanceada à medida que as transações forem inseridas e lançadas, o sistema adicionará automaticamente as entradas de débito ou crédito necessárias para equilibrar a entrada contábil durante o lançamento. As contas contábeis de débito e crédito para a transação interunidade são mostradas no comprovante lançado na Contabilidade. No entanto, elas não serão mostradas nos diários ou documentos de origem para os quais as entradas contábeis foram lançadas.

### <a name="financial-dimensions--require-the-dimension-to-be-balanced"></a>Dimensões financeiras – exigem que a dimensão esteja balanceada

Embora a dimensão de balanceamento na página **Dimensões financeiras** seja normalmente usada por empresas do setor público, a funcionalidade não está vinculada a nenhuma chave de configuração do setor público. Como não há limitação no sistema, você poderá usar essa funcionalidade, mesmo que sua organização não seja uma entidade de setor público.

Essa funcionalidade normalmente é usada na base de clientes do setor público porque requer que as definições de lançamento sejam usadas para balancear automaticamente cada transação. Ele não usa as contas de débito e crédito interunidade definidas na página **Contas para transações automáticas** para balancear automaticamente as entradas contábeis. Se uma entrada de contabilização não for balanceada no nível de dimensão após a aplicação das definições de lançamento, a transação não será lançada, mesmo que as contas de débito e crédito entre unidades sejam definidas.

Com frequência, ficamos sabendo de clientes que definem a dimensão de balanceamento na configuração do razão e na configuração da dimensão financeira. Nesse caso, o sistema usa a funcionalidade de dimensões financeiras. A configuração para balancear dimensões no nível da dimensão financeira tem precedência durante o lançamento. O lançamento não terá êxito se a definição de lançamento não criar uma entrada contábil balanceada no nível da dimensão financeira.

Siga estas etapas para ativar o uso de uma dimensão de balanceamento no nível de dimensão financeira.

1. Determine quais dimensões financeira serão as dimensões de balanceamento.

    - Você pode definir mais de uma dimensão financeira como uma dimensão de balanceamento.
    - Ainda não defina as dimensões financeiras que serão necessárias para equilibrar uma transação na página **Dimensões financeiras**.

2. Defina as definições de lançamento para cada tipo de documento de diário ou de origem usado por sua organização. As definições de lançamento consomem as contas contábeis de um diário ou documento de origem não lançado como "critérios de correspondência". A definição de lançamento retorna as "entradas geradas" que se tornam a entrada contábil. Se a definição de lançamento estiver configurada corretamente, a entrada gerada incluirá as contas contábeis de critérios de correspondência, além de contas adicionais para equilibrar a entrada contábil no nível da dimensão. Para obter mais informações, consulte [Definições de lançamento](posting-definitions.md). 
   
   Não há suporte para definições de lançamento em todos os tipos de transação. Por exemplo, as definições de lançamento não podem ser definidas para todas as transações inseridas por meio do diário geral ou do diário de ativos fixos. Se uma definição de lançamento não puder ser definida para um documento de diário ou de origem, a transação deverá ser balanceada manualmente no valor da dimensão financeira. Por exemplo, se uma entrada de diário geral é feita e a dimensão do departamento é a dimensão de saldo, você deve garantir que cada valor de departamento esteja no saldo.  Se a dimensão não for balanceada para cada valor de departamento, o comprovante não será lançado até que o desbalanceamento seja corrigido adicionando manualmente um débito interunidade ou um crédito ao comprovante. 

    > [!IMPORTANT]
    > Se for necessário balancear manualmente um número excessivo de transações, você **não** deverá usar a funcionalidade de dimensão de balanceamento na página **Dimensões financeiras**. Em vez disso, use a funcionalidade de dimensão de balanceamento na página de configuração **Razão**.

3. Depois que as definições de lançamento forem definidas, as dimensões financeiras poderão ser marcadas como necessárias para o balanceamento.

À medida que você insere e lança transações, as definições de lançamento são chamadas durante o lançamento para determinar as entradas contábeis. Se as dimensões financeiras forem balanceadas, a validação ocorrerá depois que as entradas contábeis forem determinadas. Se as dimensões financeiras não forem balanceadas, a transação não será lançada e você receberá uma mensagem informando que os débitos não são iguais aos créditos de uma dimensão específica.
