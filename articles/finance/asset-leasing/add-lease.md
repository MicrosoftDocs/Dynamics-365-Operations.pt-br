---
title: Adicionar ou copiar arrendamentos (Versão preliminar)
description: Este tópico descreve como criar um novo arrendamento inserindo informações sobre arrendamento de ativos ou copiando informações de um arrendamento existente.
author: moaamer
ms.date: 01/11/2022
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: twheeloc
ms.custom: 4464
ms.assetid: 5f89daf1-acc2-4959-b48d-91542fb6bacb
ms.search.region: Global
ms.author: moaamer
ms.search.validFrom: 2020-10-28
ms.dyn365.ops.version: 10.0.14
ms.openlocfilehash: b09a87c7d4f5ba076647218c3586d17a13e6c558
ms.sourcegitcommit: 7adf9ad53b4e6d1c4d5d612ce0977b76c61ec173
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/13/2022
ms.locfileid: "7967917"
---
# <a name="add-or-copy-leases-preview"></a>Adicionar ou copiar arrendamentos (Versão preliminar)

[!include [banner](../includes/banner.md)]

Este tópico explica como criar um arrendamento do zero no arrendamento do ativo e também como criar um arrendamento copiando um arrendamento existente. O processo de criação de um arrendamento a partir do zero envolve a inserção de informações para o novo arrendamento e, em seguida, a criação de um plano de arrendamento. Depois que pelo menos um arrendamento for configurado, talvez seja mais fácil copiar as informações de um arrendamento existente e editar essas informações, conforme necessário para criar um novo arrendamento.

## <a name="create-a-lease"></a>Criar um arrendamento

Siga estas etapas para criar um arrendamento no arrendamento do ativo.

1. Na página **Resumo de arrendamento**, no Painel de Ação, selecione **Novo**.
2. Insira as informações sobre o arrendamento. Os campos necessários têm bordas vermelhas.

A data de início do pagamento do arrendamento não pode ser anterior à data de início do arrendamento. Se inserir uma data de início do pagamento do arrendamento que for anterior à data de início do arrendamento, você receberá uma mensagem de erro.

Por padrão, a opção **Valor de pagamento de divisão** na Guia Rápida **Geral** da página **Detalhes do arrendamento** é definida como **Não** se a opção **Permitir divisão de pagamento** na página **Parâmetros de leasing de ativos** estiver definida como **Sim**. 

Se a opção **Valor do pagamento de divisão** estiver definida como **Sim**, o campo **Valor do pagamento** na Guia Rápida **Linhas da agenda de pagamento** será bloqueado. Ele será definido como o total dos valores de pagamento inseridos posteriormente no catálogo **Divisão do valor de pagamento**.

Selecione **Divisão de valor de pagamento** para abrir uma página na qual é possível adicionar os tipos de pagamento discriminados. O botão **Adicionar totais a valor de pagamento** moverá os totais para o campo **Valor do pagamento**.

> [!NOTE]
> Se você adicionar um valor de pagamento discriminado e selecionar a tecla **Esc**, os valores inseridos não serão adicionados ao campo **Valor do pagamento** na Guia Rápida **Linhas da agenda de pagamento**. Em vez disso, eles serão armazenados na caixa de diálogo **Divisão do valor de pagamento**. Se desejar que a caixa de diálogo mostre o valor total, selecione a coluna **Valor**, selecione e segure (ou clique com o botão direito do mouse) e, em seguida, selecione **Totalizar esta coluna**. 

O botão **Copiar linha** copiará a divisão de pagamento discriminada.

## <a name="create-a-lease-schedule"></a>Crie uma agenda de arrendamento

Depois de concluir a inserção das informações para o arrendamento, siga estas etapas para criar uma agenda de arrendamento.

> [!NOTE]
> As dimensões financeiras podem ser alteradas com base em quaisquer dimensões financeiras personalizadas.

1. Selecione **Criar agendas** para gerar os registros de arrendamento. Os registros de arrendamento incluem pagamento, amortização, depreciação e agendas de despesas.
2. Para acessar os registros de leasing e exibir os agendamentos recém-criados, selecione a guia **Livros**.

    A página **Detalhes do registro** mostra como o arrendamento é contabilizado pelos livros que foram alocados para ele. A partir daqui, você pode exibir as agendas de arrendamento.

    A agenda de pagamento contém as entradas da guia **Linhas da agenda de pagamento** na página **Adicionar arrendamento**. Você ainda pode alterar cada valor do pagamento e pagamento variável. A responsabilidade com o arrendamento é calculada com base na agenda de pagamento.

    > [!NOTE]
    > A data de início do pagamento do arrendamento deve ser igual ou posterior à data inicial do arrendamento. Você receberá uma mensagem de erro se a data de início do pagamento for anterior à data de início do arrendamento. 

4. Depois de concluir a revisão da agenda de pagamento, selecione **Confirmar agenda**. Depois que a agenda for confirmada, o arrendamento não estará mais disponível para edição.

    > [!NOTE]
    > O sistema calcula automaticamente o prazo de arrendamento das linhas da agenda de pagamento na página **Adicionar arrendamento**.
    >
    > Para calcular o prazo de arrendamento em meses, o sistema encontra a diferença entre a data inicial e a data final de uma linha específica da agenda de pagamento. Em seguida, ele passa para a próxima linha da agenda de pagamento e localiza a diferença novamente. Finalmente, o sistema soma todos os valores para determinar o prazo de arrendamento em meses.

5. Para exibir as despesas de juros do período calculado, abra a página **Agenda amortização de passivo**. Para exibir a depreciação de linha reta calculada, abra a página **Agenda de depreciação de ativo**.
6. Depois de concluir a revisão do valor calculado, você pode criar a entrada do diário de reconhecimento inicial na página **Reconhecimento inicial**. Você recebe uma mensagem que declara que o diário foi criado.

    > [!NOTE]
    > A entrada de diário não é lançada na contabilidade até que você coloque manualmente a entrada.

7. Para revisar a entrada de reconhecimento inicial proposta antes de lançá-la, selecione **Diário de arrendamento de ativo**.

    > [!NOTE]
    > O diário de arrendamento de ativo não pode ser criado manualmente. Ele é criado automaticamente quando as agendas de arrendamento são criadas.

8. Quando terminar de revisar a entrada do diário de reconhecimento inicial e estiver pronto para lançá-la, selecione **Lançar** para reconhecer o ativo de direito de uso (DDU) e a responsabilidade com arrendamento na Contabilidade.

## <a name="copy-a-lease"></a>Copiar um arrendamento

O arrendamento de ativos permite copiar os detalhes de um arrendamento para criar uma novo arrendamento com as mesmas informações. Em seguida, você poderá alterar os campos de arrendamento antes de criar os planos para o arrendamento copiado.

1. Na página **Resumo de arrendamento**, selecione o arrendamento a ser copiado e, no Painel de Ação, selecione **Copiar arrendamento**.

    > [!NOTE]
    > Se o parâmetro **Manual** estiver desativado para a sequência numérica das IDs de arrendamento, o próximo número na sequência será gerado automaticamente como a ID do arrendamento copiado. Se o parâmetro **Manual** estiver ativado, você receberá uma mensagem solicitando que você insira a ID de arrendamento antes de continuar a copiar o arrendamento.

2. Selecione **Copiar**. Os detalhes do arrendamento selecionado são copiados para um novo arrendamento. Em seguida, você poderá editar os detalhes do novo arrendamento antes de salvá-la e criar os prazos de arrendamento.

## <a name="asset-leasing-journal"></a>Diário de arrendamento de ativo

Todas as entradas de diário criadas no arrendamento de ativos estão contidas no diário de arrendamento de ativo. Na página **Diário de arrendamento de ativo** (**Arrendamento de ativo \> Lançamentos \> Diário de leasing do ativo**), você pode filtrar por status de lançamento, exibir entradas de diário específicas e comprovantes, e lançar entradas de diário não lançadas.

> [!NOTE]
> O diário de arrendamento de ativo não pode ser criado manualmente. Ele é criado automaticamente quando as agendas de arrendamento são criadas.


[!INCLUDE[footer-include](../../includes/footer-banner.md)]
