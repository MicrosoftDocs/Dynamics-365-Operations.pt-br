---
title: Modelos de etapa
description: Este artigo explica como configurar a funcionalidade de cobrança por etapa na Cobrança de assinatura.
author: JodiChristiansen
ms.date: 11/04/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: twheeloc
ms.custom: 539093
ms.search.region: Global
ms.author: jchrist
ms.search.validFrom: 2021-11-05
ms.dyn365.ops.version: 10.0.24
ms.openlocfilehash: d3c2cf751e4998c73bc3816e5b81e8d5963c8e53
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/03/2022
ms.locfileid: "8856760"
---
# <a name="milestone-billing"></a>Cobrança por etapa

[!include [banner](../includes/banner.md)]

Este artigo explica como definir modelos para a funcionalidade de cobrança por etapa na Cobrança de assinatura. Para cada linha do modelo de etapa, você pode definir a porcentagem ou o valor de alocação. Em seguida, você pode atribuir o modelo de etapa aos itens da agenda de cobrança que usam a funcionalidade de cobrança por etapa.

## <a name="add-a-template"></a>Adicionar um modelo

Para adicionar um modelo de etapa, siga estes passos.

1. Acesse **Cobrança de assinatura \> Cobrança de contrato recorrente \> Configurar \> Modelos de etapas**.
2. Selecione **Novo**.
3. No campo **Modelo de etapa**, insira um identificador exclusivo para o novo modelo.
4. No campo **Descrição**, insira uma descrição.
5. No campo **Método de alocação**, selecione um método de alocação.
6. Opcional: no campo **Valor total**, especifique o valor total do modelo.
7. Para adicionar uma linha, selecione **Adicionar**. Em seguida, no campo **Número do item**, selecione o número do item para a nova linha.
8. Siga uma destas etapas, dependendo do valor selecionado no campo **Método de alocação**:

    - Se você selecionou **Porcentagem** como o método de alocação, especifique o percentual de alocação para cada linha no campo **Porcentagem**. Se você especificar porcentagens, a soma das porcentagens mostrada no campo **Porcentagem total** deverá ser igual a **100**.
    - Se você selecionou **Valor variável** como o método de alocação, especifique o valor para cada linha no campo **Valor**.
    - Se você selecionou **Valor igual** como o método de alocação, não será necessário especificar um valor. Cada linha será atualizada com o percentual e o valor corretos, com base no número de itens adicionados ao modelo.

9. Selecione **Salvar**.

## <a name="delete-a-template"></a>Excluir um modelo

Para excluir um modelo de etapa, siga estes passos.

1. Selecione uma ou mais linhas para excluir e selecione **Excluir**.
2. Quando você for solicitado a confirmar a ação, selecione **Sim**.

## <a name="milestone-template-fields"></a>Campos do modelo de etapa

A página **Modelo de etapa** contém os campos a seguir.

| Campo | Descrição |
|-------|-------------| 
| Modelo de etapa | O identificador exclusivo do modelo de etapa. |
| Descrição | A descrição do modelo de etapa. |
| Método de alocação | <p>Selecione o método de alocação:</p><ul><li>**Porcentagem de conclusão** – um valor de conclusão cumulativo é usado para cada linha.</li><li>**Porcentagem** – um valor percentual pode ser especificado para a alocação. A soma de todas as porcentagens deve ser igual a 100.</li><li>**Valor variável** – um valor pode ser especificado para a alocação. O valor de alocação é especificado no nível da transação.</li><li>**Valor igual** – as porcentagens de alocação são calculadas automaticamente e igualmente divididas entre os itens no modelo.</li></ul> |
| Valor total | Especifique o valor da etapa do modelo. |
| **Linhas** | |
| Número do item | Selecione o número do item para o modelo de etapa. |
| Nome do produto | O nome do item. |
| Porcentagem | <p>Insira a porcentagem de alocação para a linha:</p><ul><li>Se o campo **Método de alocação** estiver definido como **Porcentagem**, especifique a porcentagem da linha.</li><li>Se o campo **Método de alocação** estiver definido como **Valor igual**, a porcentagem será dividida automaticamente em porcentagens iguais, com base no número de itens no modelo.</li></ul><p>A soma de todas as porcentagens deve ser igual a 100.</p><p>Se um **Valor total** for especificado no cabeçalho e você alterar o valor da **Porcentagem** da linha, o campo **Valor** será atualizado. Por outro lado, se você alterar o **Valor**, o valor de **Porcentagem** será atualizado.</p> |
| Valor | <p>O valor de alocação da linha:</p><ul><li>Se o campo **Método de alocação** estiver definido como **Valor variável**, especifique o valor da linha.</li><li>Se o campo **Método de alocação** estiver definido como **Valor igual**, o valor será automaticamente dividido em quantias iguais com base no número de itens no modelo e no **Valor total** especificado no cabeçalho.</li></ul><p>A soma de todos os valores deve ser igual ao **Valor total** especificado no cabeçalho.</p><p>Se um **Valor total** estiver especificado no cabeçalho e você alterar o **Valor** da linha, o valor de **Porcentagem** será atualizado. Por outro lado, se você alterar o valor de **Porcentagem**, o campo **Valor** será atualizado.</p> |
| **Totais** | |
| Percentual total | A soma das porcentagens. A soma de todas as porcentagens deve ser igual a 100. |
| Valor total | A soma das quantias do campo **Valor** para todas as linhas. Essa soma deve ser igual ao **Valor total** especificado no cabeçalho. |
| Valor restante | O valor restante. O valor é calculado como o **Valor total** do cabeçalho menos a soma das quantias do campo **Valor** para todas as linhas.|

## <a name="milestone-allocation"></a>Alocação de etapa

Antes de começar a usar a funcionalidade de etapas, você deve concluir estas tarefas.

1. Adicione um ou mais modelos de etapas.
2. Crie um grupo de agendas de cobrança. Especifique **Etapa** como o tipo de item e selecione um modelo.
3. Na página **Configuração de item** (**Cobrança de assinatura \> Cobrança de contrato recorrente \> Configurar \> Itens**), selecione uma relação de item e um modelo de etapa para a configuração do item.

Depois de criar os modelos de etapas, os grupos de agendas de cobrança e os itens, você pode criar uma agenda de cobrança que use a funcionalidade de etapas.

Para configurar uma agenda de cobrança que use etapas, siga estes passos.

1. Na lista **Todas/Agendas de cobranças ativas** da página **Agendas de cobrança**, selecione **Novo**.
2. Na página **Todas as agendas de cobrança**, crie uma nova agenda de cobrança e especifique uma conta de cliente e uma data de início.
3. Na seção **Linhas da agenda de cobrança**, selecione **Adicionar linha**. Em seguida, adicione um número de item e defina o campo **Tipo de item** como **Etapa**.

    Se um modelo de etapa padrão estiver configurado para o item, os eventos de etapas serão automaticamente adicionados às linhas da agenda de cobrança. As datas de término ficam em branco nas linhas das etapas.

    Se nenhum modelo de etapa estiver configurado para o item, selecione **Alocação de etapa**. Em seguida, na página **Alocação de etapa**, selecione um modelo de etapa e faça as atualizações necessárias. Depois, selecione **Fechar** para retornar à agenda de cobrança e conclua sua criação.

4. Para criar faturas para a agenda de cobrança, você deve atualizar a data de término de cada evento da etapa. Para uma única agenda de cobrança, você pode atualizar a data de término do evento da etapa nas linhas da agenda de cobrança. Para atualizar várias agendas de cobrança, selecione **Atualizar processo de data de conclusão**.
5. Depois de atualizar a data de término, você pode criar a fatura. Para uma única agenda de cobrança, selecione **Gerar fatura** na página **Todas as agendas de cobrança**. Para criar faturas para várias agendas de cobrança, selecione **Gerar fatura** ou **Gerar processamento em lote de faturas** em **Tarefas periódicas**.

## <a name="edit-milestone-allocation-on-a-billing-schedule-line"></a>Editar a alocação de etapa em uma linha de agenda de cobrança

Para editar a alocação de etapa em uma linha de agenda de cobrança, siga estes passos.

1. Na página **Agendas de cobrança** > **Todas ou agendas de cobrança ativas**, no campo **Número da agenda**, selecione o número da agenda de cobrança.
2. Na seção **Linhas da agenda de cobrança**, insira um item, especifique **Etapa** como o item e selecione **Alocação de etapa**.
3. No campo **Modelo de etapa**, selecione um modelo de etapa.
4. Selecione **Processar**. As linhas do modelo de etapa são adicionadas automaticamente às linhas da agenda de cobrança.

## <a name="milestone-allocation-fields"></a>Campos de alocação de etapa

A página **Alocação de etapa** contém os campos a seguir.

| Campo | Descrição |
|-------|-------------|
| Item pai | O número de item do pai. |
| Preço bruto | <p>O preço bruto do item. O valor corresponde ao **Valor líquido** da linha da agenda de cobrança.</p></p>Para um item pai da etapa, o valor padrão é o **Valor total** especificado para o modelo de etapa. Se o valor total for 0 (zero), o valor padrão será o **Valor líquido** da linha da agenda de cobrança.</p> |
| Modelo de etapa | A ID do modelo de etapa do item de linha. |
| Descrição do modelo | A descrição do modelo de etapa. |
| Método de alocação | O método de alocação usado para o modelo de etapa. |
| **Linhas** | Os valores padrão para todas as linhas se baseiam no modelo de etapa selecionado. Você pode alterá-los conforme necessário. |
| Número do item | O número do item para o modelo de alocação de etapa. |
| Nome do produto | O nome do produto. |
| Porcentagem | <p>A porcentagem de alocação para a linha. A soma de todas as porcentagens deve ser igual a 100.</p><p>Se você alterar o valor de **Porcentagem** da linha, o **Valor líquido** será atualizado. Por outro lado, se você alterar o **Valor líquido**, a **Porcentagem** será atualizada.</p> |
| Valor líquido | <p>O valor de alocação da linha. A soma dos valores líquidos deve ser igual ao **Preço bruto** especificado no cabeçalho.</p><p>Se você alterar o **Valor líquido** da linha, o valor de **Porcentagem** será atualizado. Por outro lado, se você alterar o valor da **Porcentagem**, o **Valor líquido** será atualizado.</p> |
| **Totais** | |
| Percentual total | A soma dos valores de **Porcentagem** para todas as linhas. Essa soma deve ser igual a 100. |
| Valor total | A soma das quantias de **Valor líquido** para todas as linhas. Essa soma deve ser igual ao **Preço bruto** especificado no cabeçalho. |
| Valor restante | O valor restante. O valor é calculado como o valor do **Preço bruto** do cabeçalho menos a soma das quantias de **Valor líquido** para todas as linhas. O valor final deve ser 0 (zero). |
