---
title: Configurar a Validação da conciliação de faturas de contas a pagar
description: Este tópico fornece informações sobre como configurar a validação na Conciliação de faturas de contas a pagar.
author: abruer
manager: AnnBe
ms.date: 06/26/2019
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: VendParameters
audience: Application User
ms.reviewer: twheeloc
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: abruer
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: d501dc6580c699c9b11db5b762d9e4e5fb17df5c
ms.sourcegitcommit: 890734e916efec5a926b03c9729a6eaf32b310fd
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/27/2019
ms.locfileid: "1703797"
---
# <a name="set-up-accounts-payable-invoice-matching-validation"></a>Configurar a Validação da conciliação de faturas de contas a pagar

[!include [task guide banner](../../includes/task-guide-banner.md)]

Antes de começar, verifique se a configuração conciliação de faturas está marcada. Se sua entidade legal acompanha os gastos, como fretes, usando encargos, verifique se a tecla de configuração Cobranças está selecionada.  A conciliação de faturas de contas a pagar é o processo de conciliar as informações da fatura do fornecedor e do recebimento do produto. As diferenças entre esses documentos são chamadas discrepâncias de conciliação. As discrepâncias de conciliação são comparadas com as tolerâncias especificadas. Se uma discrepância de conciliação exceder a porcentagem ou o valor de tolerância, os ícones de variação de conciliação serão exibidos na página **Fatura de fornecedor** e na página **Detalhes da conciliação da fatura**.

## <a name="determine-which-invoice-matching-validation-to-use"></a>Determine a validação de conciliação de fatura a ser usada
Quatro tipos de validação de conciliação diferentes estão disponíveis. 

- **Conciliação em nível de linha** – O tipo mais comum de conciliação é a conciliação de linhas. A conciliação em nível de linha pode ser dupla ou tripla A conciliação em nível de linha padrão pode ser especificada para uma entidade legal na página **Parâmetro de contas a pagar**. A conciliação dupla compara o preço unitário da fatura com o preço unitário da ordem de compra. A conciliação tripla adicionalmente compara a quantidade da fatura com a quantidade de recebimento de produtos conciliados.
- **Conciliação de totais de fatura** – Concilia os valores totais na fatura com valores totais da ordem de compra. Esse tipo de conciliação de faturas inclui o menor valor de detalhe, de forma que você possa usar esta opção para configurar os controles que minimizam o tempo da equipe que são necessários para rever as informações na conciliação de faturas. Seis totais são comparadas, incluindo o desconto de um subtotal, total, encargos, impostos, os redondos saída, e o valor de nota fiscal. O sistema validará se algum valores em uma nota fiscal se afastam os valores previstos por mais de uma variação aceitável.
- **Conciliação de encargos** – Concilia as informações de encargos (valores) na fatura com as informações de encargo (valores) na ordem de compra.
- **Totais de preço para conciliação de item de linha** – Este tipo de conciliação é útil para empresas que receberão normalmente várias faturas para uma linha de ordem de compra. Se você receber apenas em uma fatura por linha de ordem de compra, este tipo de conciliação não é necessária. Esta conciliação exige que a conciliação dupla ou tripla esteja ativada e funcione como uma validação de valor líquido com limite máximo, com base em uma porcentagem de tolerância e valores.  Você pode comparar as informações de preço para o valor líquido de cada linha da fatura e todas as linhas na fatura pendentes e lançadas anteriormente, com o valor líquido da linha da ordem de compra correspondente. O valor líquido é determinado pela seguinte fórmula: (Preço unitário * Quantidade da linha) + Encargos da linha - Descontos da linha. Ao combinar os totais de preços por porcentagem, o sistema compara os valores usando a moeda da transação. Ao combinar totais de preço por valor, o sistema compara os valores usando a moeda contábil.

## <a name="set-up-parameters-to-enable-invoice-matching-validation"></a>Configure parâmetros para habilitar a validação de conciliação de faturas
1. Vá para **Contas a pagar > Configuração > Parâmetros de contas a pagar**.
2. Selecione a guia **Validação de fatura**.
3. Marque ou desmarque a caixa de seleção **Habilitar validação da conciliação de faturas**.
    * Selecione se deseja exigir aprovação antes que uma fatura que contém discrepâncias na conciliação de faturas seja lançada. Se **Permitir com aviso** estiver definido, a indicação visual será exibida quando uma discrepância na conciliação de faturas exceder a tolerância. No entanto, você poderá lançar a nota fiscal. Para usar fluxos de trabalho junto com a validação de conciliação de faturas, verifique se o campo **Lançar fatura com discrepâncias** está definido como **Permitir com aviso** para evitar precisar aprovar várias vezes.  
    * No campo **Atualizar automaticamente o status de conciliação do cabeçalho da fatura**, selecione se as correspondências serão executadas automaticamente durante a entrada de dados da fatura pelo sistema. A configuração recomendada é **Sim**, a menos que você tenha preocupações com o desempenho da entrada de dados. Desabilitar as atualizações automáticas pode habilitar o desempenho do sistema mais rápido porque a validação de conciliação de nota fiscal será ignorada durante a entrada de dados. O auxiliar de entrada de dados precisa atualizar manualmente o status de conciliação de fatura para ver os resultados de validação de conciliação de fatura quando ele está definido como **Não**.  
4. Defina **Conciliação de totais de fatura**.
5. Marque ou desmarque a caixa de seleção **Conciliar totais de fatura** para coincidir os totais de faturas atuais com os totais esperados.
    * Selecione se um ícone será exibido se uma discrepância da conciliação de faturas exceder a tolerância. Você pode exibir o ícone quando uma discrepância positiva exceder a tolerância ou quando uma discrepância positiva ou negativa exceder a tolerância.  
    * Por exemplo, a tolerância é 5 e o valor total da fatura da ordem de compra é 100,00. Portanto, um ícone de conciliação do preço será exibido se o valor total da fatura na fatura exceder 105,00. Se você selecionar **Se maior que ou menor que a tolerância**, um ícone também será mostrado se o valor da fatura for menor que 95,00.  
6. No campo **Porcentagem de tolerância de totais de fatura**, insira a variação de porcentagem que seja aceitável. Este é o valor padrão da empresa. Esse valor pode ser substituído para fornecedores específicos, usando a página **Tolerâncias de totais de fatura**. Para obter informações sobre como substituir a porcentagem de tolerância de totais de faturas para um fornecedor específico, consulte “Configure a tolerância de conciliação de totais de faturas de fornecedores” mais adiante neste tópico.
7. Defina **Conciliação de preço e quantidade**.
8. No campo **Política de conciliação de linha**, selecione um valor a ser usado como a política padrão para a entidade legal com a qual você está trabalhando. **Não necessário** significa que não há verificação de preços de linha de fatura individual para preço de ordem de compra ou quantidades de fatura para quantidades de guia de remessa necessárias. **Conciliação dupla** significa que a verificação das linhas da fatura é necessária, mas apenas a ordem de compra e documentos da fatura do fornecedor estão envolvidos na verificação. O recebimento de produtos não é faturado nas validações de conciliação. **Conciliação tripla** significa que o preço unitário líquido da fatura será comparado ao preço unitário líquido da ordem de compra correspondente e a quantidade de recebimento do produto correspondente será comparada à quantidade da fatura.
9. Para permitir que um nível diferente de conciliação seja aplicado a um item, fornecedor, combinação de fornecedor e item ou linha da ordem de compra, selecione um valor no campo **Permitir a substituição da política de conciliação**. A política de conciliação da entidade legal pode ser sobrescrita por um fornecedor, item ou combinação de fornecedor e item específicos na página de **Política de conciliação**.
    * Se você usar uma política de conciliação da linha de correspondência ou da conciliação dupla ou tripla, poderá configurar percentuais de tolerância de preços para a pessoa jurídica, itens e fornecedores, na página **Tolerância do preço de item**. A tolerância de preços padrão da entidade legal será definida como zero por cento para conciliação dupla ou tripla. Quando as faturas são comparadas com as informações em ordens de compra, a porcentagem da tolerância de preço aplicável é procurada.   
10. Para conciliar os totais de preço por itens de linha ou faturas, selecione um valor no campo **Conciliar totais de preço**. Esse tipo de correspondência é útil quando o fornecedor envia várias notas fiscais para a mesma linha da ordem de compra. Você pode comparar as informações de preço para o valor líquido de cada linha da fatura e todas as linhas na fatura pendentes e lançadas anteriormente, com o valor líquido da linha da ordem de compra correspondente.  As opções são **Não**, **Porcentagem**, **Valor**, ou **Porcentagem e valor**.
11. No campo **Porcentagem total de tolerância de preços de compra** , insira uma porcentagem de variação que você aceitará. Esse campo só estará disponível quando **Conciliar totais de preço** estiver definido como **Porcentagem** ou **Porcentagem e valor**.
12. No campo **Total tolerância de preços de compra** , insira um valor em moeda contábil. Esse campo só estará disponível quando **Conciliar totais de preço** estiver definido como **Valor** ou **Porcentagem e valor**.
13. No campo **Exibir ícone de conciliação do total de preço**, selecione quando um ícone é exibido se a discrepância para a conciliação de faturas exceder a tolerância para o preço unitário líquido. O ícone pode ser exibido quando uma discrepância positiva exceder a tolerância ou quando uma discrepância positiva ou negativa exceder a tolerância.
Por exemplo, a tolerância é 5 por cento e o total do preço da linha na ordem de compra for de 10,00. Portanto, um ícone de conciliação do preço será exibido se preço total da linha na fatura exceder 10,50. Se você selecionar **Se maior que ou menor que a tolerância**, um ícone também será mostrado se o valor da fatura for menor que 9,50.
13. Defina a Conciliação de encargos.
14. Para conciliar os encargos reais com os encargos esperados, com base nas informações nas ordens de compra, marque a caixa de seleção **Conciliar encargos**.

## <a name="set-up-unit-price-tolerance-percentages"></a>Configure porcentagens de tolerância de preços unitários
Vá para **Contas a pagar > Configuração > Configuração de conciliação de faturas > Tolerâncias de preço** para definir porcentagens de tolerância de preços permitidos. Se você usar uma diretiva de conciliação da linha de correspondência ou da conciliação dupla ou tripla, você pode configurar percentuais de tolerância de preços para a pessoa jurídica, itens e fornecedores, na página de tolerância de preços de item. Quando as faturas são comparadas com as informações em ordens de compra, a porcentagem da tolerância de preço aplicável é procurada. A busca é realizada na seguinte ordem:
* Tabela/Tabela
* Tabela/Grupo
* Tabela/Tudo
* Grupo/Tabela
* Grupo/Grupo
* Grupo/Tudo
* Tudo/Tabela
* Tudo/Grupo
* Tudo/Tudo

A tolerância de preços de entidade legal padrão é 0 por cento e a tolerância de preço é aplicada a todos os itens e todas as contas (All, All). Você não pode excluir o registro da tolerância de preço padrão da entidade legal.

Por padrão, as discrepâncias de preço negativo são permitidas. No entanto, você não pode inserir um número negativo como a porcentagem da tolerância de preço. Para rastrear porcentagens da tolerância de preço negativo, selecione **Se maior que ou menor que tolerância** no campo **Exibir ícone de coincidir preço unitário** na página **Parâmetros de contas a pagar**. Insira percentuais de tolerância de preços na página **Tolerâncias de preços**.

## <a name="set-up-matching-policy-override"></a>Configure a substituição da política de conciliação

Vá para **Contas a pagar > Configuração > Configuração de conciliação de faturas > Política de conciliação** para definir a entrada padrão para o campo Política de conciliação para linhas no formulário Ordem de compra. Esta é uma configuração opcional. Use este formulário para configurar uma conciliação dupla ou tripla para itens, fornecedores, ou combinações de item e fornecedor. Essas entradas permitem que você defina políticas de conciliação mais granuladas do que a política de conciliação de entidade legal definida na página **Parâmetros de contas a pagar**. A política de conciliação da linha de entidade legal padrão aplica-se a todos os itens e fornecedores, exceto aqueles para os quais uma política de conciliação de linha diferente é especificado nessa página.

Nesta página, selecione o **Nível de política de conciliação**. Selecione o nível na hierarquia da política de conciliação para definir as políticas de conciliação de linha.

- **Item e fornecedor** – Especifique a política de conciliação para itens específicos comprados de fornecedores específicos.
- **Item** – Especifique a política de conciliação para itens específicos comprados de qualquer fornecedor, exceto aqueles especificados nos níveis de item e fornecedor.
- **Fornecedor** – Especifique a política de conciliação para todos os itens comprados de fornecedores específicos, exceto aqueles especificados nos níveis de item e fornecedor.
  
A seguinte hierarquia é usada para determinar a política de conciliação que é utilizada:
  *  Item e fornecedor
  *  Item
  *  Fornecedor
  *  Pessoa jurídica em geral
  
## <a name="set-up-invoice-totals-matching-tolerance-for-vendors"></a>Configure a tolerância de conciliação de totais de faturas de fornecedores

Vá para **Contas a pagar > Configuração > Configuração de conciliação de faturas > Tolerâncias de totais de fatura** para especificar tolerâncias específicas de fornecedor para conciliação de totais de fatura. O cálculo de conciliação usa a porcentagem de tolerância de totais de fatura da conta de fornecedor especificada como a conta da ordem na fatura de fornecedor. Se a conta do fornecedor não tiver uma porcentagem de tolerância especificada para totais de fatura, a porcentagem de tolerância de totais de fatura especificada para a entidade legal na página **Parâmetros de contas a pagar** será usada.

1. Para especificar tolerâncias para fornecedores individuais que substituam a tolerância padrão, selecione uma **Conta do fornecedor**.
2. Insira a porcentagem de variação que será aceita para este fornecedor.
