---
title: Ajustar arrendamentos
description: O tópico explica como ajustar um arrendamento. O ajuste pode ser necessário, se os prazos de arrendamento forem modificados, o arrendamento for estendido ou outras circunstâncias são alteradas.
author: moaamer
manager: Ann Beebe
ms.date: 10/28/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: roschlom
ms.search.scope: Core, Operations, Retail
ms.custom: 4464
ms.assetid: 5f89daf1-acc2-4959-b48d-91542fb6bacb
ms.search.region: Global
ms.author: moaamer
ms.search.validFrom: 2020-10-28
ms.dyn365.ops.version: 10.0.14
ms.openlocfilehash: 9d1c6e20e72fb2816c32e71e8921a94724ae5656
ms.sourcegitcommit: aeee39c01d3f93a6dfcf2013965fa975a740596a
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/28/2020
ms.locfileid: "4440563"
---
# <a name="adjust-leases"></a>Ajustar arrendamentos

[!include [banner](../includes/banner.md)]

O tópico explica como ajustar um arrendamento. O ajuste pode ser necessário, se os prazos de arrendamento forem modificados, o arrendamento for estendido ou outras circunstâncias são alteradas. O arrendamento de ativo está em conformidade com a orientação do Tópico 842 da Codificação de Padrões Contábeis (ASC 842) e do Padrão Internacional de Relatórios Financeiros 16 (IFRS 16) fornecem informações sobre modificações de arrendamento. O 842-20-15-1 ASC define uma modificação de arrendamento como qualquer alteração nos termos e condições de um contrato que causa uma alteração no escopo de, ou a consideração, de um arrendamento. O parágrafo 39 do IFRS 16 afirma que um arrendatário deve reavaliar a responsabilidade com arrendamento de forma que reflita as alterações feitas nos pagamentos do arrendamento.

Para organizações que aderem a ASC 842 ou IFRS 16, um arrendamento é remedido para refletir uma alteração no valor presente dos pagamentos de arrendamento mínimos futuros (PVFMLP). Se o PVFMLP aumentar, a entrada do diário que é criada será um débito ao ativo de direito de uso (ROU) e um crédito na responsabilidade com arrendamento para a diferença entre o novo PVFMLP e PVFMLP anterior. Se o PVFMLP diminuir, a entrada de diário será um débito para responsabilidade com arrendamento e um crédito para o ativo ROU da diferença.

Se o ajuste diminuir o ativo de ROU após 0 (zero), o restante será creditado na conta de lançamento de modificação de arrendamento especificada na página **Contas de lançamento de arrendamento**. As contas de sistema para essas transações e outras entradas de ajuste, como alterações de classificação, custos diretos iniciais, incentivos ao arrendamento, pagamentos antecipados e custos de desmontagem que surgem das modificações de arrendamento.

Para obter orientação específica sobre transações de ajuste de arrendamento, recomendamos que você veja IFRS 16 e ASC 842.

Para ajustar um arrendamento, siga estas etapas. Os dados modificados atualizarão as agendas de arrendamento depois que o processo Criar agenda for executado.

1. Vá para **Arrendamento de ativo \> Arrendamento \> Resumo de arrendamento**.
2. Na página **Resumo do arrendamento**, selecione o arrendamento a ser ajustado e selecione **Ajustar arrendamento**.
3. Na página **Ajustar arrendamento**, insira as novas informações para arrendamento ajustado.

    Observe que a página **Ajustar arrendamento** é semelhante à página **Adicionar arrendamento**. Além disso, assim como a data de início que você especifica ao adicionar um arrendamento determina quando o novo arrendamento começa, o campo **Data de Modificação** na página **Ajustar arrendamento** determina quando o arrendamento modificado começa. Essa data não pode ser posterior à data inicial nas linhas da agenda de pagamento.

    > [!NOTE]
    > Os campos de **Considerações de ROU** se aplicam ao ajuste de arrendamento. Se nenhum custo direto inicial, incentivos ao arrendamento, pagamentos antecipados ou custos de desmontagem estiverem associados ao arrendamento modificado, deixe esses campos em branco. Os valores originais não se aplicam ao arrendamento atualizado. Os custos adicionais incorridos quando o arrendamento for modificado devem ser inseridos na página **Ajustar arrendamento**.
    > 
    > Por exemplo, um arrendador fornece um incentivo de $1.000 para concordar com uma extensão de arrendamento. Nesse caso, ao ajustar o arrendamento para a conta da extensão, você insere **1.000** no campo **Incentivos ao arrendamento**. Se nenhum incentivo estiver associado ao ajuste de arrendamento, você deverá limpar qualquer valor que tenha sido inserido anteriormente neste campo. A mesma lógica é aplicada a outras considerações de ROU.

    As linhas da agenda de pagamento do arrendamento ajustado devem ser criadas em uma base de potencial. As linhas da agenda de pagamento criadas em uma base potencial não podem ser iniciadas antes que as modificações de arrendamento tenham efeito.

    As etapas a seguir são quase idênticas às etapas para reconhecer inicialmente um arrendamento.

4. Selecione **Criar agendas** para gerar a agenda de pagamento ajustado. Você recebe uma mensagem que indica que a agenda de pagamento foi criada para o arrendamento.

    > [!IMPORTANT]
    > Antes de selecionar **Criar agendas**, verifique se a data de modificação e as linhas da agenda de pagamento estão precisas. Certifique-se também de que todos os custos diretos iniciais, incentivos de arrendamento, pagamentos antecipados ou custos de desmontagem correspondam somente aos custos que surjam do ajuste.

5. Para exibir a agenda de pagamento recém-criada, selecione **Livros** e abra a página **Agenda de pagamento**.
6. Na página **Agenda de pagamento**, você pode editar os valores de pagamento ajustados antes de confirmar a agenda de pagamento. Para confirmar a agenda, selecione **Confirmar agenda**.

    Quando a agenda de pagamento é confirmada, a nova depreciação de ativo e as novas agendas de responsabilidade com arrendamento são criadas.

7. Para exibir a nova agenda de amortização da responsabilidade com arrendamento que é gerada pelas novas entradas, feche a página **Agenda de pagamento** e abra a página **Agenda de amortização de passivo**.
8. Para exibir a agenda de depreciação de ativos recém-gerado, abra a página **Agenda de depreciação do ativo** na página **Detalhes do registro**.
9. Para gerar a entrada do diário de ajuste, selecione **Função \> Ajuste de arrendamento**. Você recebe uma mensagem que declara que a entrada de diário do ajuste foi criada. 
10. Para exibir a entrada de diário, selecione **Diários \> Entrada de diário do ativo**.
11. Para lançar a entrada de diário, selecione a linha e, em seguida, selecione **Lançar**.

## <a name="view-lease-versions"></a>Exibir versões de arrendamento

Se um arrendamento tiver sido modificado, você poderá exibir as diferentes versões dele. Você também pode exibir agendas de históricos e detalhes do arrendamento passado.

1. Na página **Resumo de arrendamento**, selecione o arrendamento e, no Painel de Ação, selecione **Histórico da versão de arrendamento**.

    Se o arrendamento selecionado tiver sido ajustado, a página **Histórico da versão de arrendamento** mostrará as diferentes versões dele. O arrendamento original é rotulado como **1** e as versões subsequentes têm ordem numérica crescente.

    Para uma versão de arrendamento selecionada, é possível exibir as linhas das dimensões financeiras, dos detalhes do contrato, do local e da agenda de pagamento.

2. Para exibir agendas históricas, abra o arrendamento modificado na página **Resumo do arrendamento**, selecione o livro desejado e, no Painel de Ação, selecione **Histórico de versão do livro**.
3. Na página **Versão do registro**, selecione a versão desejada e a agenda desejada a ser exibida.
