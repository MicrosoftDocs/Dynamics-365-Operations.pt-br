---
title: Configurar modelos de depreciação
description: Este procedimento mostra a você como criar um novo registro de ativos fixos e associá-lo a um grupo de ativos fixos.
author: moaamer
ms.date: 12/03/2021
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: AssetBookTable, AssetGroupBookSetup
audience: Application User
ms.reviewer: roschlom
ms.search.region: Global
ms.author: moaamer
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: be3b5578bd6509859c36f6a50ea9730e9ef1780e
ms.sourcegitcommit: c85eac17fbfbd311288b50664f9e2bae101c1fe6
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/03/2021
ms.locfileid: "7890703"
---
# <a name="set-up-value-models"></a>Configurar modelos de depreciação

[!include [banner](../../includes/banner.md)]
[!include [preview banner](../../includes/preview-banner.md)]

Este procedimento mostra a você como criar um novo registro de ativos fixos e associá-lo a um grupo de ativos fixos.

## <a name="create-a-book"></a>Criar um registro
1. Acesse **Ativos fixos \> Configuração \> Registros**.
2. Selecione **Novo**.
3. No campo **Registro**, insira um valor.
4. No campo **Descrição**, insira um valor.
5. Defina a opção **Calcular depreciação** como **Sim**.

    Se a opção **Calcular depreciação** estiver definida como **Sim**, o registro do ativo associado será incluído nas propostas de depreciação. Se estiver definido como **Não**, o registro do ativo não será depreciado automaticamente.

6. No campo **Perfil de depreciação**, insira ou selecione um valor.

    * Um perfil de depreciação alternativo também é conhecido como um método alternativo de depreciação. A proposta de depreciação alternará para esse perfil quando o perfil alternativo calcular um valor de depreciação que seja igual ou maior do que o perfil de depreciação padrão.
    * O perfil de depreciação extraordinário é usado para depreciação adicional para um ativo em condições incomuns. Por exemplo, você pode usá-lo para registrar a depreciação que resulta de acidentes naturais.
    * Se você selecionar **Criar ajustes de depreciação com ajustes de base**, os ajustes de depreciação serão criados automaticamente quando o valor do ativo for atualizado. Caso contrário, o valor do ativo atualizado afetará somente os cálculos de depreciação futuros.

7. Defina a opção **Criar ajustes de depreciação com ajustes de base** como **Sim**.

    * Por padrão, as transações do registro de ativos são lançadas na contabilidade. No entanto, você pode desabilitar o lançamento na contabilidade do registro definindo a opção **Lançar na contabilidade** como **Não**. Os registros que não são lançados na contabilidade geralmente são usados para relatórios de imposto. Essa opção fornece mais flexibilidade para excluir transações históricas do registro de ativos, porque as transações não foram confirmadas na contabilidade.
    * Por padrão, o campo **Nível de lançamento** é definido como **Nível atual** se o registro for lançado na contabilidade e **Nenhum** se não for. Atualize o valor do campo **Nível de lançamento** se as transações desse registro devem ser lançadas em um nível diferente.

8. Calcule a depreciação positiva.

    * Por padrão, a opção **Calcular depreciação positiva** está definida como **Não**. Essa configuração indica que a depreciação creditará o registro do ativo selecionado. Além disso, as opções **Permitir valor líquido contábil superior ao custo de aquisição** e **Permitir valor líquido contábil negativo** são ambas definidos como **Não**, e as configurações podem ser alteradas de forma independente. 
    * Para calcular o desvio padrão, defina a opção **Calcular depreciação positiva** como **Sim**. Essa configuração indica que a depreciação debitará o registro do ativo fixo. Quando a opção **Calcular depreciação positiva** estiver definida como **Sim**, as opções **Permitir valor líquido contábil superior ao custo de aquisição** e **Permitir valor líquido contábil negativo** serão automaticamente definidas como **Sim** e elas serão bloqueadas. Esse bloqueio ajuda a garantir que a depreciação positiva será aplicada somente aos ativos fixos que foram adquiridos com valor contábil negativo (crédito). 

10. No campo **Calendário**, insira ou selecione um valor.

    Os registros derivados lançarão transações em registros diferentes ao mesmo tempo. Você cria as transações com o registro principal e, durante um lançamento, uma cópia exata da transação será lançada no registro derivado. Não há recálculo com transações derivadas do registro, portanto ele não deve ser usado para transações de depreciação.

## <a name="associate-the-book-with-a-fixed-asset-group"></a>Associar o registro a um grupo de ativos fixos

1. Selecione **Grupo de ativos fixos**.
2. No campo **Grupo de ativo fixo**, insira ou selecione um valor.
3. No campo **Vida útil**, insira um número.

    * Os períodos de depreciação são calculados após a vida útil do ativo ser inserida.
    * A convenção de depreciação pode ser definida conforme necessário para fins fiscais.
    * Para ativos fixos associados a arrendamentos, o valor no campo **Vida útil** será substituído pelo menor do prazo de arrendamento no registro de ativos e na vida útil do ativo. Se a opção **Transferência de propriedade** estiver definida como **Sim** para o registro de arrendamento, o valor do campo **Vida útil** será sempre a vida útil do ativo.

[!INCLUDE[footer-include](../../../includes/footer-banner.md)]
