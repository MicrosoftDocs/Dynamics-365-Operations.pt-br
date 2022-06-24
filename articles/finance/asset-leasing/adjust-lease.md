---
title: Ajustar arrendamentos
description: O artigo explica como ajustar um arrendamento. O ajuste pode ser necessário, se os prazos de arrendamento forem modificados, o arrendamento for estendido ou outras circunstâncias são alteradas.
author: moaamer
ms.date: 03/18/2022
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: kfend
ms.custom: 4464
ms.assetid: 5f89daf1-acc2-4959-b48d-91542fb6bacb
ms.search.region: Global
ms.author: moaamer
ms.search.validFrom: 2020-10-28
ms.dyn365.ops.version: 10.0.14
ms.openlocfilehash: 48d1a261a43d6e3a68dfc0aae6f06c0d7d6b82db
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/03/2022
ms.locfileid: "8898317"
---
# <a name="adjust-leases"></a>Ajustar arrendamentos

[!include [banner](../includes/banner.md)]
[!include [preview banner](../includes/preview-banner.md)]

O artigo explica como ajustar um arrendamento. O ajuste pode ser necessário, se os prazos de arrendamento forem modificados, o arrendamento for estendido ou outras circunstâncias são alteradas. O arrendamento de ativo está em conformidade com a orientação do Tópico 842 da Codificação de Padrões Contábeis (ASC 842) e do Padrão Internacional de Relatórios Financeiros 16 (IFRS 16) fornecem informações sobre modificações de arrendamento. O 842-20-15-1 ASC define uma modificação de arrendamento como qualquer alteração nos termos e condições de um contrato que causa uma alteração no escopo de, ou a consideração, de um arrendamento. O parágrafo 39 do IFRS 16 afirma que um arrendatário deve reavaliar a responsabilidade com arrendamento de forma que reflita as alterações feitas nos pagamentos do arrendamento.

Para organizações que aderem a ASC 842 ou IFRS 16, um arrendamento é remedido para refletir uma alteração no valor presente dos pagamentos de arrendamento mínimos futuros (PVFMLP). Se o PVFMLP aumentar, a entrada de diário criada será um débito à conta de ativo de direito de uso (DDU) e um crédito na conta de responsabilidade com arrendamento para a diferença entre o novo PVFMLP e o PVFMLP anterior. Se o PVFMLP diminuir, a entrada de diário será um débito para a conta de responsabilidade com arrendamento e um crédito para a conta de ativo DDU da diferença.

Se o ajuste diminuir o ativo DDU após 0 (zero), o restante será creditado na conta de lançamento de modificação de arrendamento especificada na página **Contas de lançamento de arrendamento**. As contas de sistema para essas transações e outras entradas de ajuste, como alterações de classificação, custos diretos iniciais, incentivos ao arrendamento, pagamentos antecipados e custos de desmontagem que surgem das modificações de arrendamento.

Para obter orientação específica sobre transações de ajuste de arrendamento, recomendamos que você veja IFRS 16 e ASC 842.

## <a name="lease-adjustment-wizard"></a>Assistente de ajuste de arrendamento

Para ajustar um arrendamento, conclua as etapas a seguir. Os dados modificados atualizarão agendas de arrendamento após o lançamento do assistente de **Ajuste de arrendamento**. Você pode salvar seu trabalho, fechar o assistente a qualquer momento e voltar posteriormente para continuar o trabalho.

Para abrir o assistente de **Ajuste de arrendamento** no resumo de arrendamento, siga estas etapas.

1. Acesse **Arrendamento de ativo \> Arrendamento \> Resumo de arrendamento**. 
2. Selecione o arrendamento a ser ajustado e selecione **Assistente de ajuste**.
3. Siga as instruções do assistente para inserir as alterações necessárias.

Para abrir o assistente de **Ajuste de arrendamento** na página **Ajustes de arrendamento**, para um ajuste que já esteja em andamento, siga estas etapas.

1.  Acesse **Arrendamento \> Arrendamentos \> Ajustes de arrendamento**.
2.  Selecione um arrendamento que tenha um status de ajuste **Em andamento** e selecione **Assistente de ajuste**.
3.  Nos campos **Data de início da modificação** e **Data de lançamento**, insira as datas apropriadas.
4.  Selecione **Avançar**.

    O arrendamento é adicionado à página **Ajustes de arrendamento**, na qual você pode inserir as novas informações sobre ele.

    Após o ajuste do arrendamento, os campos de considerações de direito de uso se aplicam a ele. Se não houver custos diretos iniciais, incentivos ao arrendamento, pagamentos antecipados ou custos de desmontagem associados ao arrendamento modificado, deixe os campos correspondentes em branco. Os valores originais não se aplicam ao arrendamento atualizado. 

    Por exemplo, um arrendador fornece um incentivo de $1.000 para concordar com uma extensão de arrendamento. Nesse caso, ao ajustar o arrendamento para a conta da extensão, você insere **1.000** no campo **Incentivos ao arrendamento provenientes do ajuste**.

    As linhas do plano de pagamento agora mostram todos os pagamentos do mês, e dos meses posteriores, no campo **Data de início da modificação**. Como as modificações são potenciais, as linhas do plano de pagamento não podem começar antes do início da modificação. Para exibir as linhas do plano de pagamento anteriores à data inicial da modificação, acesse a página **Histórico da versão de arrendamento**.

8.  Selecione **Avançar**.

    A próxima página mostra detalhes importantes sobre o ajuste de arrendamento esperado, como os valores de transporte de responsabilidade com arrendamento antes da modificação e a nova responsabilidade com arrendamento esperada após a modificação. A página também mostra uma versão preliminar da entrada de diário para o ajuste de arrendamento esperado.

9.  Selecione **Enviar para fluxo de trabalho** para enviar o ajuste de arrendamento para o sistema de fluxo de trabalho se o fluxo de trabalho de ajuste de arrendamento estiver ativo e o ajuste ainda não tiver sido aprovado. Para obter mais informações sobre como usar o fluxo de trabalho de ajuste de arrendamento, consulte [Usar fluxos de trabalho de ajustes de arrendamento](use-create-lease-wrkflw.md).

    > [!NOTE]
    > Neste ponto, o sistema recalcula as variáveis de ajuste para verificar se nenhuma transação foi lançada no arrendamento desde que a visão geral do ajuste e a entrada do diário de ajuste foram calculadas primeiro. Se algum valor for alterado, a grade de visão geral de ajuste será atualizada e você poderá analisar as informações antes de reenviar os ajustes de arrendamento para o sistema de fluxo de trabalho.

10. Se um fluxo de trabalho não estiver ativo ou se o ajuste de arrendamento tiver sido aprovado, selecione **Concluir** para processar as alterações e lançar a entrada do diário de ajuste.

    > [!NOTE] 
    > Neste ponto, o sistema recalcula as variáveis de ajuste para verificar se nenhuma transação foi lançada no arrendamento desde que a visão geral do ajuste e a entrada do diário de ajuste foram calculadas primeiro. Se algum valor for alterado, a grade de visão geral de ajuste será atualizada e você poderá analisar as alterações antes de selecionar **Concluir**. Se o fluxo de trabalho estiver ativo e o ajuste de arrendamento tiver sido aprovado, todas as alterações feitas na visão geral do ajuste farão com que o status de aprovação seja redefinido como **Não enviado**. Nesse caso, você deve reenviar o ajuste de arrendamento para o sistema de fluxo de trabalho.

    Na página **Ajustes de arrendamento**, o status do ajuste agora é definido como **Concluído**.

    Na página **Ajustes de arrendamento**, você ainda pode exibir as FastTabs **Visão geral de ajuste** e **Versão preliminar de entrada de ajuste**. Os detalhes do arrendamento e as informações de data são mostrados no histórico de versões desse arrendamento.

    Uma nova versão de arrendamento e um novo conjunto de agendas são criados agora com as informações modificadas. 

13. Para exibir as novas agendas, acesse o arrendamento e selecione **Registros**.
14. Para exibir a agenda de pagamento recém-gerada, selecione **Agenda de pagamento**.
15. Para exibir a nova agenda de amortização da responsabilidade com arrendamento que é gerada pelas novas informações, feche a página **Agenda de pagamento** e abra a página **Agenda de amortização de passivo**.
16. Para exibir a agenda de depreciação de ativos recém-gerado, abra a página **Agenda de depreciação do ativo** na página **Detalhes do registro**.
17. Para exibir a entrada de diário de ajuste, selecione **Diários \> Diário de arrendamento de ativo**.

## <a name="cancel-a-lease-adjustment"></a>Cancelar um ajuste de arrendamento

Para excluir um ajuste de arrendamento em andamento, siga estas etapas.

1.  Acesse **Arrendamento \> Arrendamentos \> Ajustes de arrendamento**.
2.  Selecione esse ajuste de arrendamento em andamento a ser cancelado.
3.  Selecione **Cancelar ajuste**. 
4.  Selecione **OK**.

    > [!NOTE] 
    > Se você selecionar **Cancelar** no assistente de **Ajuste de arrendamento**, reverterá as alterações mais recentes concluídas no assistente, mas não removerá um ajuste em andamento.

## <a name="use-the-lease-adjustment-workflow"></a>Usar o fluxo de trabalho de ajuste de arrendamento

Esta seção explica como usar o fluxo de trabalho de ajuste de arrendamento. O fluxo de trabalho de ajuste de arrendamento ajuda você a gerenciar ajustes de arrendamento de forma consistente, fornecendo um conjunto de etapas de aprovação e atribuindo-os a usuários específicos que aprovam um ajuste de arrendamento antes que se torne final. Depois que o ajuste de arrendamento for aprovado no fluxo de trabalho, você poderá usar o assistente de **Ajuste de arrendamento** para concluir o ajuste de arrendamento.

1.  Para enviar um ajuste de arrendamento para aprovação, acesse **Arrendamento \> Arrendamentos \> Ajustes de arrendamento**.
2.  Selecione a ID de arrendamento do ajuste de arrendamento e selecione **Assistente de ajuste**.
3.  Na última página do assistente, selecione **Enviar para aprovação**.
4.  Insira um comentário sobre o ajuste e selecione **OK**.

    O status do fluxo de trabalho é alterado para **Aprovação pendente** e todos os campos do assistente são bloqueados para edição.

5.  Para aprovar o ajuste de arrendamento, acesse **Arrendamento \> Arrendamentos \> Ajustes de arrendamento**.
6.  Selecione a ID de arrendamento do ajuste de arrendamento e analise as FastTabs **Visão geral de ajuste** e **Versão preliminar de entrada de ajuste**.
7.  Selecione **Fluxo de trabalho \> Aprovado**.

    Na página **Ajustes de arrendamento**, o status do fluxo de trabalho agora é definido como **Aprovado**. Neste ponto, o ajuste de arrendamento está pronto para ser lançado por meio da entrada de diário de ajuste.

8.  Para continuar a processar o ajuste de arrendamento e lançar a entrada de ajuste, acesse **Arrendamento \> Arrendamentos \> Ajustes de arrendamento**.
9.  Selecione a ID de arrendamento do ajuste de arrendamento e selecione **Assistente de ajuste**.
10. Selecione **Avançar** até chegar à última página do assistente e selecione **Concluir**.

O sistema recalcula os valores de transporte do arrendamento para garantir que as variáveis de ajuste aprovadas sejam atuais. Se houver alterações, o status de aprovação será redefinido como **Rascunho** e você deverá reenviar o ajuste de arrendamento para o sistema de fluxo de trabalho.

## <a name="view-lease-versions"></a>Exibir versões de arrendamento

Se um arrendamento tiver sido ajustado, você poderá exibir as diferentes versões dele. Você também pode exibir agendas de históricos e detalhes do arrendamento passado.

1. Na página **Resumo de arrendamento**, selecione o arrendamento e, no Painel de Ação, selecione **Histórico da versão de arrendamento**.

    Se o arrendamento selecionado tiver sido ajustado, a página **Histórico da versão de arrendamento** mostrará as diferentes versões. O arrendamento original é rotulado como **1** e as versões subsequentes têm ordem numérica crescente.

    Para uma versão de arrendamento selecionada, é possível exibir as linhas das dimensões financeiras, dos detalhes do contrato, do local e da agenda de pagamento.

2. Para exibir agendas históricas, abra o arrendamento modificado na página **Resumo do arrendamento**, selecione o livro desejado e, no Painel de Ação, selecione **Histórico de versão do livro**.
3. Na página **Versão do registro**, selecione uma versão e uma agenda a ser exibida.

## <a name="adjust-a-lease-book"></a>Ajustar um registro de arrendamento

Siga estas etapas para ajustar apenas um registro de arrendamento.

1. Acesse **Arrendamento de ativo** \> **Arrendamento** \> **Resumo de arrendamento**.
2. Selecione e abra um arrendamento.
3. Na página **Detalhes do arrendamento**, selecione **Registros**.
4. Na página **Detalhes dos registros**, no Painel de Ações, no grupo **Manter**, selecione **Ajustar registro**. 
5. Remova as linhas da agenda de pagamento.
6. No campo **Data da modificação do arrendamento**, insira a data de modificação. Considere a possibilidade de remover todas as considerações adicionais sobre ativos/passivos (custo direto inicial, incentivo ao arrendamento, pagamento antecipado de arrendamento, custo de desmontagem e garantia de valor residual), se houver. 
7. Para ajudar a evitar cálculos imprecisos para o ajuste de arrendamento, adicione novas linhas da agenda de pagamento para as novas datas de pagamento que correspondam à data de modificação. 

> [!NOTE] 
> É recomendável usar o assistente **Ajuste de arrendamento** para ajustar um arrendamento. O assistente reduz o número de etapas manuais, fornece uma pré-visualização de saldos após o ajuste e permite alterar os valores antes do lançamento.

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
