---
title: Condições de Alocação
description: Este tópico fornece informações sobre o uso de condições de alocação em uma conta principal.
author: rachel-profitt
ms.date: 06/15/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: AccountingDistribution, LedgerAllocationRule, MainAccount, AllocationTerms
audience: Application User
ms.reviewer: roschlom
ms.custom: 17361
ms.assetid: 04c8548a-0af9-492b-954b-946b4f8ca023
ms.search.region: Global
ms.author: raprofit
ms.search.validFrom: 2020-06-15
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 5735cbdd4c8b137d01a56be0009b60d32c21e94e
ms.sourcegitcommit: 0e8db169c3f90bd750826af76709ef5d621fd377
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/01/2021
ms.locfileid: "5823659"
---
# <a name="allocation-terms"></a>Condições de Alocação

[!include [banner](../includes/banner.md)]

Este tópico fornece informações sobre o uso de condições de alocação em uma conta principal. Os termos de alocação são usados para distribuir valores nas várias combinações da conta contábil. Elas ajudam a garantir que as despesas ou as receitas sejam cobradas no objeto correto na contabilidade.

Cada condição de alocação que você cria em uma conta principal define a porcentagem de um comprovante a ser alocada de uma conta principal de origem única e uma combinação de dimensões financeiras. Além disso, você define a conta principal de destino e as dimensões financeiras nas quais o valor será alocado. 

Ao definir a dimensão financeira de origem para a alocação, você pode selecionar se cada dimensão é específica ou não específica. Específica indica que a dimensão financeira da transação de origem deve corresponder à dimensão selecionada. Quando você seleciona não específica, ela indica que qualquer valor para a dimensão financeira pode contribuir para uma correspondência.

Ao definir a conta contábil de destino para uma condição de alocação, você deve especificar a conta principal na qual o valor será alocado. Você pode usar a mesma conta principal na qual a transação de origem é lançada ou uma conta principal diferente. Se a mesma conta principal for usada, um aviso será exibido ao salvar o registro. Além de especificar a conta principal, você também deve especificar as dimensões de destino. Para cada dimensão, você pode especificar se deseja manter o valor de dimensão financeira de origem ou alterá-lo. Se você selecionar Não, deverá selecionar um novo valor para a dimensão financeira. Se você selecionar Sim, nenhuma informação adicional será especificada e o sistema manterá as dimensões financeiras originais ao lançar.

Não há limite para o número de termos de alocações que podem ser adicionados a uma conta principal; no entanto, a soma da porcentagem a ser alocada em um termo de alocação não pode exceder 100. Você pode criar alocações para menos de 100% se uma parte do valor original do comprovante deve permanecer nas dimensões financeiras de origem. Os termos de alocações podem ser adicionados a uma conta principal como uma substituição de entidade legal. Se você estiver usando um plano de contas compartilhado, os termos de alocação deverão ser definidos para cada entidade legal. Para acessar o botão **Termos de alocação**, primeiro você deve marcar a caixa de seleção **Alocação** na substituição da entidade legal.

## <a name="allocation-term-example"></a>Exemplo de termo de alocação
Você definiu um centro de custos para a sua organização chamado CORPORATIVO que é numerado 000. Quando as faturas são lançadas para despesas de utilitário, elas são codificadas para este centro de custos CORPORATIVO. Sua empresa definiu uma regra que todas as despesas utilitárias devem ser alocadas por uma porcentagem para cada um dos centros de custos individuais. As outras dimensões financeiras para o departamento e a unidade de negócios permanecerão a mesma.

Com este exemplo, uma nova condição de alocação será criada para a conta principal de despesas do utilitário. Uma linha seria criada para cada centro de custo com a porcentagem a ser alocada. Os **Critérios de seleção** para as dimensões financeiras de origem para cada linha seriam **Específicos** para o **Centro de custos** e o valor será definido como 000: CORPORATIVO. Para o departamento e a unidade de negócios, os **critérios de seleção** seriam não **Não específicos**.

Na guia rápida **Conta contábil de destino**, a conta principal será a mesma conta de despesa do utilitário e **Manter dimensões financeiras de origem** será definida como **Sim** para **Unidade de negócio** e **Departamento.** A opção **Manter dimensões financeiras de origem** será definida como **Não** para o **Centro de custos** e o valor selecionado será aquele respectivo centro de custo para o qual você está alocando. Se houver três centros de custos para alocar, serão criados três registros de termos de alocação. A única diferença entre cada termo de alocação é o centro de custos especificado na conta contábil de destino.

## <a name="create-an-allocation-term-on-a-main-account"></a>Criar uma condição de alocação em uma conta principal

1. No **Painel de navegação**, vá para **Módulos > Contabilidade > Plano de contas > Contas > Contas principais**.
2. Na lista, localize e selecione o registro desejado.
3. Na guia rápida **Substituições da entidade legal**, selecione **Adicionar**.
4. Selecione a **Empresa** e, em seguida, selecione **Adicionar**.
5. Marque a caixa de seleção **Alocação**.
6. Selecione **Termos de alocação**.
7. Selecione **Editar** para modificar o registro padrão ou selecione **Novo** para adicionar um registro.
8. No campo **Porcentagem**, insira a porcentagem das transações de comprovante que deseja alocar.
9. Na guia rápida **Dimensão financeira de origem**, nos **Critérios de seleção** para cada dimensão financeira, selecione uma opção.
    - Se você selecionar **Específica**, selecione o valor da dimensão financeira na caixa suspensa à direita.
    - Se você selecionar **Não específica**, nenhuma informação adicional será necessária para a dimensão financeira.
10. Na guia rápida da conta **Razão de destino** no campo **Para conta**, selecione a conta principal na qual você deseja alocar a porcentagem da transação de comprovante.
11. Em **Manter dimensões financeiras de origem** para cada dimensão financeira, selecione uma opção.
    - Se você selecionar **Não**, selecione o valor da dimensão financeira na caixa suspensa à direita, onde deseja que a transação de comprovante seja alocada.
    - Se você selecionar **Sim**, nenhuma informação adicional será necessária. O sistema manterá o valor no comprovante original ao lançar a alocação.
12. Repita as etapas de 7 a 11 para cada alocação adicional. A soma de todas as alocações é indicada no campo **Porcentagem total**. Esse valor não pode exceder 100.
13. Feche todas as páginas.

>[!NOTE] 
> Opcionalmente, você pode usar o botão **Copiar** para duplicar a alocação selecionada.

Quando uma condição de alocação for criada para uma conta principal, o sistema lançará automaticamente um novo comprovante quando um comprovante for lançado com as dimensões financeiras de origem nas condições de alocação.


[!INCLUDE[footer-include](../../includes/footer-banner.md)]