---
title: Criar e processar não conformidades
description: Este tópico descreve como executar o gerenciamento de não conformidades, com base em uma ordem de qualidade existente.
author: perlynne
ms.date: 03/23/2021
ms.topic: business-process
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.search.industry: Distribution
ms.author: perlynne
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 06a56a694f7a80d65cb46d08744e78d8361cee3b
ms.sourcegitcommit: 8362f3bd32ce8b9a5af93c8e57daef732a93b19e
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/28/2021
ms.locfileid: "5956197"
---
# <a name="create-and-process-nonconformances"></a>Criar e processar não conformidades

[!include [banner](../../includes/banner.md)]

Este tópico descreve como executar o gerenciamento de não conformidades, com base em uma ordem de qualidade existente. Normalmente, o gerenciamento de não conformidade é feito por um auxiliar de qualidade. Como pré-requisito, você deve ter uma ordem de qualidade disponível. (Para obter mais informações sobre como criar uma ordem de qualidade, consulte [Verificar a qualidade de mercadorias](inspect-quality-goods.md)).

Antes que um usuário possa processar a aprovação de uma não conformidade, um trabalhador deve ser atribuído a ela no campo **Pessoa** na página **Usuários**. Além disso, antes que o usuário possa usar as notas do documento, a opção **Habilitar manuseio de documentos** deve ser definida como *Sim* nas opções do usuário.

## <a name="create-a-nonconformance"></a>Criar uma não conformidade

Para criar uma não conformidade, siga estas etapas.

1. Vá para **Gerenciamento de estoque \> Tarefas periódicas \> Gerenciamento de qualidade \> Não conformidades**.
1. No Painel de Ações, selecione **Novo**.
1. Na caixa de diálogo **Criar não conformidade**, no campo **Tipo de problema**, selecione o tipo de problema encontrado durante o processo de inspeção.
1. Selecione **OK**.

## <a name="approve-or-reject-a-nonconformance"></a>Aprovar ou rejeitar uma não conformidade

Para aprovar ou rejeitar uma não conformidade, siga estas etapas.

1. Vá para **Gerenciamento de estoque \> Tarefas periódicas \> Gerenciamento de qualidade \> Não conformidades**.
1. Na lista, selecione a não conformidade que deseja atualizar.

    > [!NOTE]
    > Você pode adicionar uma correção somente a não conformidades que foram aprovadas.

1. No Painel de Ações, selecione **Funções \> Aprovar não conformidade** para aprovar a não conformidade ou **Funções \> Recusar não conformidade** para rejeitá-la. Você pode associar não conformidades aprovadas a [operações relacionadas](../quality-operations.md). Dessa forma, você pode registrar o trabalho feito como parte do tratamento de não conformidade e do processamento do tratamento de correção.
1. Será solicitado que você confirme sua seleção. Selecione **Sim** para continuar.

## <a name="add-operations-and-other-details-to-nonconformances"></a>Adicionar operações e outros detalhes a não conformidades

Depois de criar uma não conformidade, você pode começar a adicionar operações relacionadas e especificar informações adicionais sobre essas operações. Você pode adicionar operações relacionadas somente a não conformidades que foram aprovadas.

Além das informações básicas, você pode adicionar os seguintes detalhes a uma operação:

- **Itens** – você pode criar uma lista de itens consumidos para realizar a correção. Por exemplo, os itens podem ser produtos necessários para reparar equipamentos ou ingredientes necessários à retrabalho de um produto acabado.
- **Encargos de qualidade** – você pode criar uma lista de encargos incorridos ou faturados para fontes externas.
- **Folha de ponto** – você pode criar um log do tempo gasto por cada trabalhador na operação.

As demais configurações são opcionais. O custo de cada item, encargos de qualidade e folha de ponto são somados e mostrados na operação. Não é possível editar diretamente o campo **Custo** na operação.

### <a name="create-an-operation-for-a-nonconformance"></a>Criar uma operação para uma não conformidade

Para criar uma operação para uma não conformidade, siga estas etapas.

1. Vá para **Gerenciamento de estoque \> Tarefas periódicas \> Gerenciamento de qualidade \> Não conformidades**.
1. Na lista, selecione a não conformidade que deseja atualizar.

    > [!NOTE]
    > Você pode adicionar ou atualizar operações somente a não conformidades que foram aprovadas.

1. No Painel de Ações, selecione **Operações relacionadas**.
1. Na página **Operações relacionadas**, no painel de Ações, selecione **Novo** para adicionar uma linha à grade. Defina os seguintes campos para a nova linha:

    - **Operação** – Selecione o código da operação que será executada para a não conformidade.
    - **Motivo** – Insira uma descrição detalhada que explique por que a operação é necessária.
    - **Ordem de venda** – se o código de operação selecionado estiver relacionado ao tipo de ordem de venda, selecione a ordem de venda à qual a operação está sendo vinculada.
    - **Ordem de compra** – se o código de operação selecionado estiver relacionado ao tipo de ordem de compra, selecione a ordem de compra à qual a operação está sendo vinculada.

1. Feche as páginas.

### <a name="add-items-to-an-operation"></a>Adicionar itens a uma operação

Para adicionar itens a uma operação, siga estas etapas.

1. Vá para **Gerenciamento de estoque \> Tarefas periódicas \> Gerenciamento de qualidade \> Não conformidades**.
1. Na lista, selecione a não conformidade que deseja atualizar.

    > [!NOTE]
    > Você pode adicionar ou atualizar operações somente a não conformidades que foram aprovadas.

1. No Painel de Ações, selecione **Operações relacionadas**.
1. Na página **Operações relacionadas**, selecione a operação à qual deseja adicionar itens.
1. No Painel de Ações, selecione **Itens**.
1. Na página **Operações relacionadas**, no painel de Ações, selecione **Novo** para adicionar uma linha à grade. Em seguida, defina os seguintes campos para a nova linha:

    - **Número do item** – selecione o produto que será consumido como parte da operação selecionada.
    - **Quantidade** – Insira o número de itens que serão consumidos.

    > [!NOTE]
    > Você pode exibir o custo do item no campo **Custo** na guia **Geral**. O custo que é mostrado vem do custo configurado na página **Produto liberado**. O custo não pode ser atualizado diretamente na página **Item de operação relacionado**. O custo de todos os itens adicionados na página **Itens de operação relacionados** é adicionado automaticamente ao campo **Custo** na página **Operações relacionadas**.

1. Repita a etapa anterior para cada item adicional que deve ser adicionado.
1. Feche as páginas.

### <a name="add-quality-charges-to-an-operation"></a>Adicionar encargos de qualidade a uma operação

Para adicionar encargos de qualidade a uma operação, siga estas etapas.

1. Vá para **Gerenciamento de estoque \> Tarefas periódicas \> Gerenciamento de qualidade \> Não conformidades**.
1. Na lista, selecione a não conformidade que deseja atualizar.

    > [!NOTE]
    > Você pode adicionar ou atualizar operações somente a não conformidades que foram aprovadas.

1. No Painel de Ações, selecione **Operações relacionadas**.
1. Na página **Operações relacionadas**, selecione a operação à qual deseja adicionar encargos de qualidade.
1. No Painel de Ações, selecione **Encargos de qualidade**.
1. Na página **Encargos de operações relacionadas**, no Painel de Ações, selecione **Novo** para adicionar uma linha à grade. Defina os seguintes campos para a nova linha:

    - **Código de encargos** – Selecione o encargo de qualidade ao qual você deseja adicionar.
    - **Descrição** – Insira uma descrição detalhada do encargo.
    - **Valor dos encargos** – Insira o valor do encargo.

1. Repita a etapa anterior para cada encargo adicional que deve ser adicionado.
1. Feche as páginas.

> [!NOTE]
> O valor no campo **Valor de encargos** é somado automaticamente a todos os encargos de qualidade e adicionado a quaisquer valores no campo **Custo** na página **Operações relacionadas**.

### <a name="create-a-timesheet-on-an-operation"></a>Criar uma folha de ponto em uma operação

Para adicionar uma folha de ponto em uma operação, siga estas etapas.

1. Vá para **Gerenciamento de estoque \> Tarefas periódicas \> Gerenciamento de qualidade \> Não conformidades**.
1. Na lista, selecione a não conformidade que deseja atualizar.

    > [!NOTE]
    > Você pode adicionar ou atualizar operações somente a não conformidades que foram aprovadas.

1. No Painel de Ações, selecione **Operações relacionadas**.
1. Na página **Operações relacionadas**, selecione a operação à qual deseja adicionar uma folha de ponto.
1. No Painel de Ação, selecione **Folha de Ponto**.
1. Na página **Folhas de ponto da operação relacionada**, no Painel de Ações, selecione **Novo** para adicionar uma linha à grade. Defina os seguintes campos para a nova linha:

    - **Data** – especifique a data em que o trabalho foi concluído. Por padrão, esse campo é definido como a data atual.
    - **Trabalhador** – selecione o trabalhador que fez o trabalho. Por padrão, este campo é definido ao trabalhador atribuído ao usuário atual.
    - **Horas de operação** – insira o número de horas que foram trabalhadas na operação selecionada.
    - **Faturado** – Marque esta caixa de seleção se o tempo tiver sido cobrado de um cliente ou fornecedor em uma fatura.

    > [!NOTE]
    > Você pode exibir o custo no campo **Custo** na guia **Geral**. O custo é calculado usando a taxa definida na página **Parâmetros de gerenciamento de estoque**.

1. Repita a etapa anterior para cada linha da folha de ponto adicional que deve ser adicionada.
1. Feche as páginas.

> [!NOTE]
> O valor no campo **Custo** é somado a todas as linhas da planilha de ponto e adicionado a quaisquer outros valores no campo **Custo** na página **Operações relacionadas**.

## <a name="add-a-correction-to-a-nonconformance"></a>Adicionar uma correção a uma não conformidade

Para adicionar uma correção a uma não conformidade, siga estas etapas.

1. Vá para **Gerenciamento de estoque \> Tarefas periódicas \> Gerenciamento de qualidade \> Não conformidades**.
1. Na lista, selecione a não conformidade que deseja atualizar.

    > [!NOTE]
    > Você pode adicionar uma correção somente a não conformidades que foram aprovadas.

1. No Painel de Ações, selecione **Correções**.
1. Na página **Correções**, no Painel de Ações, selecione **Novo** para adicionar uma linha à grade. Defina os seguintes campos para a nova linha:

    - **Diagnóstico** – Selecione o tipo de diagnóstico que identifica o tipo de correção que você está criando.
    - **Trabalhador** – Selecione a pessoa responsável pela correção.
    - **Prioridade de correção** – Selecione uma opção para indicar como a correção deve ser priorizada (*Baixa*, *Normal* ou *Alta*).
    - **Data da solicitação** – Insira a data em que a ação corretiva foi solicitada.
    - **Data planejada** – Insira a data em que a correção deve ser concluída.
    - **Solução de curto prazo** – Marque esta caixa de seleção se a ação corretiva corrigir a não conformidade somente por um curto período.

1. Feche as páginas.

## <a name="mark-a-correction-as-completed"></a>Marcar uma correção como concluída

Para marcar uma correção de não conformidade como concluída, siga estas etapas.

1. Vá para **Gerenciamento de estoque \> Tarefas periódicas \> Gerenciamento de qualidade \> Não conformidades**.
1. Na lista, selecione a não conformidade que deseja atualizar.

    > [!NOTE]
    > Você pode adicionar uma correção somente a não conformidades que foram aprovadas.

1. No Painel de Ações, selecione **Correções**.
1. Na página **Correções**, na grade, selecione a correção que deseja marcar como concluída.
1. No Painel de Ações, clique em **Marcar como concluída**.
1. Será solicitado que você confirme sua seleção. Selecione **OK** para continuar. O campo **Data e hora de conclusão** é definido como a data e a hora atuais, e a caixa de seleção **Concluído** será marcada.
1. Feche a página.

## <a name="reopen-a-completed-correction"></a>Reabrir uma correção como concluída

Para reabrir uma correção concluída, siga estas etapas.

1. Vá para **Gerenciamento de estoque \> Tarefas periódicas \> Gerenciamento de qualidade \> Não conformidades**.
1. Na lista, selecione a não conformidade que deseja atualizar.
1. No Painel de Ações, selecione **Correções**.
1. Na página **Correções**, na grade, selecione a correção que deseja reabrir.
1. No Painel de Ação, selecione **Reabrir**.
1. Será solicitado que você confirme sua seleção. Selecione **OK** para continuar. O valor é desmarcado do campo **Data e hora de conclusão** e a caixa de seleção **Concluída** será desmarcada.
1. Feche a página.

Agora você pode fazer edições adicionais ou atualizações na correção. Quando terminar, você poderá marcar a correção como concluída novamente.

## <a name="close-a-nonconformance"></a>Fechar uma não conformidade

Para fechar uma não conformidade, siga estas etapas.

1. Vá para **Gerenciamento de estoque \> Tarefas periódicas \> Gerenciamento de qualidade \> Ordens de qualidade**.
1. Selecione uma ordem de qualidade na grade.
1. No Painel de Ações, selecione **Consultas \> Não conformidades**.
1. Na página **Não conformidades**, selecione a não conformidade de destino na grade.
1. No Painel de Ações, selecione **Funções \> Fechar não conformidades**.
1. Será solicitado que você confirme sua seleção. Selecione **Sim** para continuar.
1. Feche as páginas.

## <a name="additional-resources"></a>Recursos adicionais

- [Visão geral do gerenciamento de qualidade](../quality-management-processes.md)
- [Habilitar gerenciamento de qualidade e não conformidade](../enable-quality-management.md)
- [Trabalhadores responsáveis por aprovar não conformidades](../quality-responsible-workers.md)
- [Zonas de quarentena para não conformidades](../quality-quarantine-zones.md)
- [Tipos de diagnóstico para não conformidades](../quality-diagnostic-types.md)
- [Encargos de qualidade para não conformidades](../quality-charges.md)
- [Operações para não conformidades](../quality-operations.md)
- [Gerenciamento de qualidade para processos de depósito](../quality-management-for-warehouses-processes.md)

[!INCLUDE[footer-include](../../../includes/footer-banner.md)]
