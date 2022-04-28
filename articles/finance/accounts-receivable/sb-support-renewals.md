---
title: Suporte e renovações
description: Este tópico explica como configurar e usar o processo de suporte e renovação em ordens de venda para criar uma agenda de cobrança para itens de renovação.
author: JodiChristiansen
ms.date: 11/04/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: twheeloc
ms.search.scope: Core, Operations
ms.custom: 539093
ms.search.region: Global
ms.author: jchrist
ms.search.validFrom: 2021-11-05
ms.dyn365.ops.version: 10.0.24
ms.openlocfilehash: d59eee6e858c4f0051ec103adc4e1e99e79feec9
ms.sourcegitcommit: 4d7bc52e6cdf6afce3793893ba2aa07176302314
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/11/2022
ms.locfileid: "8560466"
---
# <a name="support-and-renewals"></a>Suporte e renovações 

Este tópico explica como inserir itens de suporte ou itens de renovação ao inserir ordens de venda. Esses itens são usados para calcular o valor de encargos para o contrato de suporte original e/ou o valor de renovação que é usado quando uma agenda cobrança é criada na cobrança de assinatura. Por exemplo, sua empresa vende um servidor para um cliente e você oferece uma assinatura de backup pelo primeiro ano e a opção de renovar a assinatura todos os anos. O *item de suporte* é a assinatura do primeiro ano e o *item de renovação* é a renovação para cada ano sucessivo.

Você pode inserir informações sobre o contrato de suporte, o contrato de renovação ou ambos. Ao inserir as informações do contrato de suporte, somente o item de suporte é adicionado à ordem de venda. Ao inserir as informações de contrato de renovação, o item de renovação é usado para criar uma agenda de cobrança.

## <a name="support-and-renewal-setup"></a>Configuração de suporte e renovação

Na página **Níveis de suporte e renovação** você pode configurar diferentes níveis de suporte para itens de suporte e renovação. O suporte ou a renovação pode ser uma porcentagem do valor do item original ou pode ser um valor padrão.

É possível selecionar os níveis de suporte padrão na página **Parâmetros de cobrança recorrente de contrato**.

Por exemplo, uma empresa pode oferecer os seguintes níveis de suporte e de renovação.

| Nível de suporte | Porcentagem de suporte | Porcentagem de renovação |
|---|---|---|
| Ilimitado | 40% | 30% |
| Dourado | 25% | 18% |
| Prata | 20% | 14% |
| Bronze | 15% | 10% |

Para criar um nível de suporte ou de renovação, siga estas etapas.

1. Na página **Níveis de suporte e renovação**, selecione **Novo**.
2. No campo **Nível de suporte**, insira um nome exclusivo.
3. No campo **Descrição**, insira uma descrição.
4. No campo **Método de cálculo de suporte**, selecione o método de cálculo de suporte. Se você selecionar **Porcentagem**, insira uma porcentagem de suporte no campo **Porcentagem de suporte**.
5. No campo **Método de cálculo de renovação**, selecione o método de cálculo de renovação. Se você selecionar **Porcentagem**, insira uma porcentagem de renovação no campo **Porcentagem de renovação**.
6. Selecione **Salvar**.

### <a name="fields"></a>Campos

A página **Níveis de suporte e renovação** contém os seguintes campos.

| Campo | Descrição |
|---|---|
| Nível de suporte | Um identificador exclusivo para o nível de suporte ou renovação (por exemplo, **Ouro** ou **Prata**). |
| Descrição | Uma descrição do nível de suporte ou de renovação. |
| Método de cálculo de suporte | Selecione o método de cálculo de suporte para o nível: **Porcentagem** ou **Valor padrão**. |
| Porcentagem de suporte | Se você selecionou **Porcentagem** como o método de cálculo de suporte, especifique a porcentagem usada para calcular o preço do item de suporte. Se você tiver selecionado **Valor padrão** como método de cálculo, o valor será especificado quando a transação for criada. |
| Método de cálculo de renovação | Selecione o método de cálculo de renovação para o nível: **Porcentagem** ou **Valor padrão**. |
| Porcentagem de renovação | Se você selecionou **Porcentagem** como o método de cálculo de renovação, especifique a porcentagem usada para calcular o preço do item de renovação. Se você tiver selecionado **Valor padrão** como método de cálculo, o valor será especificado quando a transação for criada. |

## <a name="support-and-renewal-process"></a>Processo de suporte e renovação

A funcionalidade de suporte e renovação pode aplicar diferentes níveis de suporte a itens e atualizar as informações de renovação na cobrança de assinatura.

Antes de usar a funcionalidade de suporte e renovação, as seguintes tarefas devem ser concluídas.

1. Na página **Níveis de suporte e renovação**, crie pelo menos um nível de suporte ou renovação.
2. Na página **Configuração de item**, associe um item aos itens de suporte e renovação. Esta tarefa é necessária somente se você deseja configurar valores padrão para itens de suporte e/ou renovação.
3. Na página **Parâmetros de cobrança recorrente de contrato**, especifique as configurações de suporte e renovação padrão para novos agendamentos de cobrança.

Para aplicar diferentes níveis de suporte a itens e atualizar as informações de renovação, siga estas etapas.

1. Na página **Todas as ordens de venda**, crie uma ordem de venda.
2. Na FastTab **Linhas de ordem de venda**, adicione um item.
3. Na guia **Fatura**, selecione **Suporte e renovação \> Adicionar suporte e renovação**.
4. Na página **Processo de suporte e renovação**, a seção cabeçalho é atualizada com as definições da página **Parâmetros de cobrança recorrente de contrato**. Esses valores se aplicam a todos os itens de suporte e renovação. (Por exemplo, se a frequência de cobrança estiver definida como **Anualmente**, todas as linhas de venda criadas com um item de renovação têm uma frequência anual). Para associar a ordem de venda a uma agenda de cobrança existente, selecione um valor no campo **Número da agenda de cobrança**.
5. Para alterar a data de início do suporte ou da renovação, defina a opção **Substituir data de início** como **Sim**.
6. Para adicionar ou editar o item de suporte, marque a caixa de seleção **Suporte** e insira um item de suporte no campo **Item de suporte**. O item será adicionado à ordem de venda.
7. Para adicionar ou editar o item de renovação, marque a caixa de seleção **Renovação** e insira um item de renovação no campo **Item de renovação**. Quando a ordem de venda for faturada, será criado uma agenda de cobrança que incluirá o item.
8. Selecione **OK**.
9. Na guia **Geral**, selecione **Fatura**. Quando a ordem de venda é lançada, a agenda de cobrança é criada. Uma notificação que inclui as informações da agenda de cobrança é exibida nos detalhes da mensagem.
10. Na página da lista **Todas/Agendas de cobrança ativas**, selecione o número da agenda de cobrança para revisar os detalhes da agenda de cobrança na página **Agendas de cobrança**.
11. Na FastTab **Linhas da agenda de cobrança**, selecione **Suporte e renovação** para revisar os detalhes das linhas que foram criadas.

> [!NOTE]
> Se a data inicial da renovação de uma linha da agenda de cobrança tiver que ser alterada, você pode editar o valor da **Data de início** para a linha na página **Agendas de cobrança**. Quando você abre a página **Exibir detalhe de cobrança** para a linha, o campo **Data de início da cobrança** é atualizado com a nova data. O valor da **Data de término da cobrança** é recalculado com base na frequência de cobrança. A data de início da renovação só poderá ser atualizada se a primeira fatura da agenda de cobrança de renovação não tiver sido criada e lançada. Depois que a primeira fatura é criada e lançada, a data de início não pode ser editada.

O processo de suporte e renovação está disponível apenas para a ordem de venda. Ao adicionar itens de suporte e renovação a uma ordem de venda, você pode criar uma nova agenda de cobrança ou adicionar o item de renovação a uma agenda de cobrança existente.

## <a name="support-and-renewal-audit"></a>Auditoria de suporte e renovação

Na página **Auditoria de suporte e renovação** é possível revisar os detalhes das linhas da agenda de cobrança que são criadas do item de renovação em uma ordem de venda. Esta opção fica disponível quando a linha da agenda de cobrança é um item de renovação.

Para editar as informações de suporte e renovação de uma linha da agenda de cobrança, siga estas etapas.

1. Na página **Todas as agendas de cobrança**, selecione o número da agenda de cobrança.
2. Na seção **Linhas da agenda de cobrança**, selecione uma linha e depois **Suporte e renovação**.
3. Revise todas as informações para o item de suporte ou de renovação.
4. Faça as alterações necessárias no nível de suporte ou a porcentagem ou o valor de renovação e insira um valor no campo **Motivo da alteração**.
5. Selecione **Processar**.

### <a name="fields"></a>Campos

A página **Auditoria de suporte e renovação** contém os seguintes campos.

| Campo | Descrição |
|-------|-------------|
| Número do item | O número de item da linha da agenda de cobrança. |
| Nome do produto | O nome do produto. |
| Nível do plano de suporte | Exibe ou altera o nível de suporte para o item de renovação. |
| Porcentagem de renovação | Insira a porcentagem de renovação usada quando o preço unitário é calculado para um item de renovação em uma agenda de cobrança. |
| Valor da renovação | Insira o valor de renovação usado quando o preço unitário é calculado para um item de renovação em uma agenda de cobrança. |
| Razão da alteração | Insira o motivo para alterar as informações de suporte e renovação. Você deve inserir um motivo ao alterar o valor de **Porcentagem de renovação**, **Quantia de renovação** ou **Nível do plano de suporte**. |
| Item de vendas original | O número do item de venda original da ordem de venda. |
| Valor líquido original | O valor líquido original do item. |
| Nível de suporte original | O nível de suporte original do item. |
| Porcentagem de renovação original | A porcentagem de renovação original do item. |
| Valor da renovação original | O valor de renovação original do item. |
| **Grade** | |
| Nível de suporte original | O nível de suporte anterior. |
| Porcentagem de renovação original | A porcentagem de renovação anterior. |
| Valor da renovação original | O valor de renovação anterior. |
| Modificação de | O nome do usuário que fez a alteração. |
| Data e hora da modificação | A data em que ocorreu a alteração. |
| Motivo | O motivo da alteração. |
