---
title: Solucionar problemas de operações de estoque
description: Este tópico descreve como corrigir problemas que podem ocorrer durante o trabalho com operações de estoque.
author: sherry-zheng
manager: tfehr
ms.date: 12/03/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: chuzheng
ms.search.validFrom: 2020-12-03
ms.dyn365.ops.version: Release 10.0.16
ms.openlocfilehash: 3a22229106753d265a90f0ef05f5ac82dc745bbd
ms.sourcegitcommit: 38d40c331c8894acb7b119c5073e3088b54776c1
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/15/2021
ms.locfileid: "4967146"
---
# <a name="troubleshoot-inventory-operations"></a>Solucionar problemas de operações de estoque

[!include [banner](../includes/banner.md)]

Este tópico descreve como corrigir problemas que podem ocorrer durante o trabalho com operações de estoque.

## <a name="i-cant-find-the-workflow-drop-down-dialog-box-for-inventory-journals"></a>Não consigo localizar a caixa de diálogo suspensa "Fluxo de trabalho" para diários de estoque.

### <a name="issue-description"></a>Descrição do problema

Você não consegue localizar a caixa de diálogo suspensa **Fluxo de trabalho** na página do diário ou as operações de fluxo de trabalho relacionadas não estão disponíveis.

Esse problema pode ocorrer por três motivos, conforme descrito nas subseções a seguir.

### <a name="issue-resolution-1"></a>Resolução de problema 1

Se o problema se aplica a todos os usuários, ele pode estar ocorrendo porque o fluxo de trabalho de aprovação não foi atribuído ao nome de diário. Para corrigir o problema, siga estas etapas.

1. Vá para **Gerenciamento de estoque &gt; Configuração &gt; Nomes de diário &gt; Estoque**.
1. No painel de lista, selecione um nome de diário para abrir suas configurações.
1. Na FastTab **Geral**, defina a opção **Fluxo de trabalho de aprovação** como *Sim*. Se você for solicitado a confirmar a alteração, selecione **Sim**.
1. No campo **Fluxo de trabalho**, selecione o fluxo de trabalho que você deseja usar para o nome de diário selecionado.

### <a name="issue-resolution-2"></a>Resolução de problema 2

Se o seu fluxo de trabalho usa código personalizado, podem ocorrer problemas após a atualização do sistema. Por exemplo, no fluxo de trabalho do diário, o botão **Enviar** pode estar esmaecido, assim, não é possível selecioná-lo para aprovar um envio.

Se o botão **Enviar** estiver esmaecido, seu fluxo de trabalho pode ter sido personalizado, o que significa que o método do fluxo de trabalho, `canSubmitToWorkflow()` em `FormDataUtil`, foi estendido. Para corrigir esse problema, altere a forma como você estende o método do `canSubmitToWorkflow()` para usar a estrutura no exemplo a seguir.

```xpp
[ExtensionOf(formStr(InventJournalMovement))]
public final class InventJournalMovement_extension
{
    public boolean canSubmitToWorkflow()
    {
        boolean ret = YourLogicOfCanSubmitToWorkflow();

        return ret;
    }
}
```

### <a name="issue-resolution-3"></a>Resolução de problema 3

Se o problema se aplica somente a alguns usuários específicos, esses usuários talvez não tenham os privilégios de segurança necessários para executar operações de fluxo de trabalho em diários de estoque. Verifique se cada usuário afetado tem o privilégio de segurança *Manter fluxo de trabalho do diário de estoque*. Por padrão, esse privilégio é atribuído a um direito que tem o mesmo nome e esse direito é aplicado às funções *Trabalhador de depósito* e *Gerente de depósito*.

## <a name="my-inventory-journal-remains-in-system-locked-status-and-the-workflow-batch-job-doesnt-work"></a>Meu diário de estoque permanece no status bloqueado pelo sistema e o trabalho em lotes do fluxo de trabalho não funciona.

### <a name="issue-description"></a>Descrição do problema

Um dos diários de estoque está bloqueado por alguma operação e não está sendo liberado. Por exemplo, se um erro desconhecido ocorrer durante o lançamento (que é uma operação de bloqueio do sistema), o diário poderá permanecer no status bloqueado pelo sistema. Nesse caso, o manipulador de itens de trabalho do fluxo de trabalho lançará um erro enquanto realiza a validação do bloqueio.

### <a name="issue-resolution"></a>Resolução do problema

Entre na instância do SQL Server para Supply Chain Management e verifique se **InventJournalTable.SystemBlocked** está definido como *1*. Se estiver, verifique se o diário não deve estar no status bloqueado e redefina **InventJournalTable.SystemBlocked** como *0*.

## <a name="my-inventory-journal-workflow-is-never-completed-and-the-journal-cant-be-edited-or-posted"></a>O fluxo de trabalho do meu diário de estoque nunca é concluído e o diário não pode ser editado ou lançado.

### <a name="issue-description"></a>Descrição do problema

Após o envio de um fluxo de trabalho de aprovação de diário, o processamento do fluxo de trabalho para de responder e não é possível editar ou processar os diários.

### <a name="issue-resolution"></a>Resolução do problema

Há vários motivos pelos quais o processamento do fluxo de trabalho pode não ser concluído. Verifique se há os seguintes problemas:

- Vá para **Gerenciamento de estoque &gt; Configuração &gt; Fluxos de trabalho de gerenciamento de estoque** e revise a configuração do fluxo de trabalho afetado. Para obter mais informações, consulte [Fluxos de trabalho de aprovação de diário de estoque](inventory-journal-workflow.md).
- O fluxo de trabalho pode estar encontrando uma exceção ou um erro. Analise o histórico do item de trabalho do fluxo de trabalho afetado para ver se ele inclui um erro de aplicativo que encerra o fluxo de trabalho.
- O diário de estoque pode ser atualizado ou editado somente se for aprovado. Se o cancelamento estiver ativo, você poderá tentar cancelar o diário. A execução do trabalho em lotes do fluxo de trabalho pode ser suspensa por vários motivos. Alguns desses motivos podem ser causados pelo problema de estrutura do fluxo de trabalho.

## <a name="inventory-journal-workflow-conditions-apply-only-at-the-journal-level-not-at-the-line-level"></a>As condições de fluxo de trabalho do diário de estoque se aplicam apenas no nível do diário, não no nível da linha

### <a name="issue-description"></a>Descrição do problema

Você pode enfrentar esse problema se, por exemplo, tentar configurar uma condição de fluxo de trabalho do diário de estoque no valor de custo. Configure a condição de forma que a etapa 1 seja executada apenas quando o valor de custo for menor do que 100. Depois, configure outra condição de forma que a etapa 2 seja executada apenas quando o valor de custo for maior do que ou igual a 100. Então, quando o fluxo de trabalho for executado, seu histórico mostrará somente uma linha, e a primeira condição será sempre avaliada como *verdadeira*, independentemente do valor enviado.

### <a name="issue-workaround"></a>Solução alternativa do problema

Na versão atual, as condições de fluxo de trabalho de estoque se aplicam apenas no nível do diário, não no nível da linha. Esse comportamento é por design. É recomendável definir seus critérios de condição somente em atributos no nível do diário.

## <a name="the-filter-pane-on-the-on-hand-list-page-doesnt-filter-results-as-i-expect"></a>O painel de filtros na página Lista disponível não filtra os resultados conforme o esperado.

### <a name="issue-description"></a>Descrição do problema

Os filtros no painel de filtros na página **Lista disponível** não filtram os resultados conforme o esperado.

### <a name="issue-resolution"></a>Resolução do problema

Esse comportamento é por design.

A página  **Lista disponível**  é montada com base em uma tabela de estoque disponível detalhada que inclui todas as dimensões disponíveis. No entanto, a lista nesta página é um resumo. Portanto, é possível combinar linhas da tabela de origem, agregando valores de acordo com as dimensões que são mostradas.

Os filtros configurados no painel de filtros se aplicam à tabela de origem, não à lista agregada. Às vezes, esse comportamento pode produzir resultados inesperados, como mostrado [nestes exemplos](inventory-on-hand-list.md#examples).

No entanto, os [filtros fornecidos na grade](inventory-on-hand-list.md#grid-filters) *se aplicam*  à lista agregada. Esses filtros incluem filtro rápido na parte superior da grade e o filtro para cada título de coluna.

## <a name="the-unit-and-unit-quantity-arent-working-correctly-in-the-inventory-journal"></a>A unidade e a quantidade de unidades não estão funcionando corretamente no diário de estoque.

### <a name="issue-description"></a>Descrição do problema

Você pode encontrar um ou ambos os problemas a seguir ao trabalhar com unidades e quantidades em um diário de estoque:

- Você não vê unidades ou quantidades de unidades no diário de estoque enquanto uma unidade de conversão é configurada para o produto liberado e você não consegue alterar a unidade no diário de estoque.
- Você vê os campos **Quantidade** e **Unidade** no diário de estoque, mas não vê o campo **Quantidade de unidades**. Se você alterar a unidade, inserir uma quantidade e lançar o diário, ele ainda mostrará a unidade de medida original para essa quantidade.

### <a name="issue-resolution"></a>Resolução do problema

Para corrigir esse problema, siga estas etapas.

1. No espaço de trabalho **Gerenciamento de recursos**, verifique se o recurso *Usar unidade de medida e quantidade de unidades em diários de estoque* está ativado. Esse recurso adiciona os campos **Unidade** e **Quantidade de unidades** ao diário.
1. Após a ativação do recurso, use os campos **Quantidade**, **Quantidade de unidades** e **Unidade** da seguinte maneira:

    - **Quantidade** – Especifique a quantidade usando a unidade padrão definida para o produto liberado. No entanto, a unidade padrão em si não é mostrada aqui. Se uma conversão for configurada entre a unidade padrão e a unidade selecionada no campo **Unidade**, o campo **Quantidade** será atualizado automaticamente com base nas seleções nos campos **Quantidade de unidades** e **Unidade**.
    - **Quantidade de unidades** – Especifique a quantidade usando a unidade selecionada no campo **Unidade**.
    - **Unidade** – Selecione a unidade a ser aplicada ao valor no campo **Quantidade de unidades**.

## <a name="i-receive-the-following-error-message-maximum-number-of-decimals-for-the-stock-keeping-unit-is-0"></a>Recebo a seguinte mensagem de erro: "O número máximo de decimais para a unidade de manutenção de estoque é 0."

### <a name="issue-description"></a>Descrição do problema

Ao tentar lançar uma transação de estoque ou uma reserva de estoque, você recebe a seguinte mensagem de erro: "O número máximo de decimais para a unidade de manutenção de estoque é 0."

Esse problema ocorre quando a quantidade da transação de estoque é especificada como um valor decimal que está abaixo do nível de precisão ao qual o campo oferece suporte. Por exemplo, uma quantidade de *0,5* foi especificada para uma transação de estoque, mas só há suporte para quantidades inteiras. Portanto, o valor deve ser *1* em vez de *0,5*.

### <a name="issue-resolution"></a>Resolução do problema

1. Execute o script a seguir na sua instância do SQL Server para arredondar quantidades nas transações de estoque. Esse script corrigirá os valores na tabela **inventTrans**.

    ```sql
    update it set it.QTY = round(it.qty, decimalPrecisionValue) from inventtrans it where it.DATAAREAID='XXXX' and it.PARTITION=XXXXXX and it.qty <> round(it.qty, decimalPrecisionValue) and exists (select 'x' from INVENTTABLEMODULE a, unitofmeasure b where  a.unitid =b.SYMBOL and a.partition=it.partition and a.PARTITION=b.PARTITION and  MODULETYPE =0 and  b.DECIMALPRECISION=decimalPrecisionValue and a.DATAAREAID='XXXX' and a.ITEMID =it.ITEMID and it.DATAAREAID=a.DATAAREAID)
    ```

1. Execute uma verificação de consistência disponível na qual a opção **corrigir erro** esteja ativada. Essa verificação corrigirá os valores na tabela **inventSum**.

> [!IMPORTANT]
> É altamente recomendável editar o script com cuidado conforme necessário para o seu ambiente, testá-lo em um ambiente de teste e verificar os dados resultantes antes de executá-lo em um ambiente de produção.


[!INCLUDE[footer-include](../../includes/footer-banner.md)]