---
title: Visão geral das faturas de fornecedor
description: Este artigo fornece informações gerais sobre notas fiscais de fornecedor.
author: abruer
ms.date: 02/25/2022
ms.topic: overview
ms.prod: ''
ms.technology: ''
ms.search.form: VendorInvoiceWorkspace, VendInvoiceInfoListPage
audience: Application User
ms.reviewer: twheeloc
ms.custom:
- "13971"
- intro-internal
ms.assetid: 0ec4dbc0-2eeb-423b-8592-4b5d37e559d3
ms.search.region: Global
ms.author: abruer
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 565e45a1c396b9144b4a6437056a0040b2fbde1d
ms.sourcegitcommit: e0905a3af85d8cdc24a22e0c041cb3a391c036cb
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/06/2022
ms.locfileid: "9228741"
---
# <a name="vendor-invoices-overview"></a>Visão geral de faturas de fornecedor

[!include [banner](../includes/banner.md)]
[!include [preview banner](../includes/preview-banner.md)]


Este artigo fornece informações gerais sobre notas fiscais de fornecedor. As faturas do fornecedor são solicitações para pagamento dos produtos e serviços. As faturas do fornecedor podem representar uma cobrança para serviços em andamento, ou podem se basear em ordens de compra para itens e serviços específicos.

## <a name="vendor-invoices"></a>Faturas de fornecedor

Uma fatura do fornecedor de uma ordem de compra é uma fatura que é gerada quando produtos ou serviços são recebidos de acordo com uma ordem de compra que foi criada com um fornecedor. A fatura do fornecedor contém um cabeçalho e uma ou mais linhas para itens ou serviços. Uma fatura do fornecedor completa o ciclo da ordem de compra para a nota fiscal do fornecedor.

Embora algumas faturas de fornecedor sejam associadas a uma ordem de compra, as faturas do fornecedor também podem conter linhas que não correspondem às linhas da ordem de compra. Você também pode criar faturas de fornecedor que não estão associadas com qualquer ordem de compra. Essas faturas de fornecedor podem representar serviços contínuos, como uma cobrança de utilitário. Não é necessário fazer referência a uma ordem de compra ao adicionar um serviço em andamento.

Há várias formas de inserir uma fatura de fornecedor:

- O registro de fatura do fornecedor permite que você insira rapidamente faturas que não fazem referência a uma ordem de compra, para que você possa acumular a despesa. Ao usar o diário de aprovação de fatura do fornecedor, você pode selecionar essas faturas e publicá-las no saldo do fornecedor para reverter a provisão.
- O diário de faturas de fornecedor permite inserir rapidamente faturas que não fazem referência a uma ordem de compra, em uma única etapa.
- Junto com o grupo de faturas de fornecedor, o registro de fatura de fornecedor permite inserir rapidamente faturas para aumentar a despesa. Você pode abrir as ordens de compra associadas ao lançar a fatura com base na conta de despesas.
- As páginas **Faturas de fornecedor em aberto** e **Faturas de fornecedor pendentes** permitem criar faturas de fornecedor a partir de ordens de compra confirmadas.

A discussão a seguir fornece mais informações sobre como usar a página **Faturas de fornecedor em aberto** ou **Faturas de fornecedor pendentes** para criar uma fatura de fornecedor a partir de uma ordem de compra.

## <a name="understanding-invoice-line-quantities"></a>Entendendo as quantidades da linha da fatura

Ao abrir uma fatura de fornecedor de uma ordem de compra relacionada, o sistema cria linhas de fatura com base na ordem de compra. Por padrão, o sistema usa as quantidades do recibo de produtos. No entanto, você pode usar qualquer um dos seguintes comportamentos padrão:

- **Quantidade de recebimento atual** – Use esta opção para remessas parciais. O valor padrão do campo **Quantidade** será definido como a quantidade especificada no campo **Receber agora** na ordem de compra.
- **Quantidade encomendada** – Use esta opção para remessas completas. O valor padrão do campo **Quantidade** será definido com a quantidade especificada no campo **Encomendado** na ordem de compra.
- **Quantidade registrada** – Use esta opção se o item exigir registro, conforme especificado na página **Grupos de modelos de item**. O valor padrão no campo **Quantidade** é a quantidade de atualização física que foi registrada.
- **Quantidade de recebimento de produtos** – Use esta opção se um recebimento de produtos já tiver sido recebido para a ordem. O valor padrão do campo **Quantidade** é a quantidade total de recebimentos de produtos disponíveis.
- **Quantidade e serviços registrados** – Use esta opção se as quantidades foram registradas em diários de chegada para os itens em estoque ou itens que não estão armazenados. Esta opção também inclui serviços, independente do fato de os serviços estarem registrados ou não.

Se a entidade legal utiliza a conciliação de faturas, você pode exibir os resultados da conciliação de quantidade na coluna **Conciliação de quantidade de recebimento de produtos**. Você também pode usar o botão **Detalhes de conciliação** na guia **Revisão** do Painel de Ação para exibir os resultados da conciliação de quantidade.

## <a name="adding-a-line-that-wasnt-on-the-purchase-order"></a>Adicionar uma linha que não estava na ordem de compra

Você pode adicionar uma linha que não estava na ordem de compra para a fatura do fornecedor. Você deve selecionar um número de item ou categoria de suprimento. Você pode adicionar quantidades, preços e valores na linha. A linha será incluída somente nas políticas de conciliação para os totais de fatura.

## <a name="submitting-a-vendor-invoice-for-review"></a>Enviando uma fatura de fornecedor para revisão

Sua organização pode usar os fluxos de trabalho para gerenciar o processo de revisão para faturas de fornecedores. A revisão de fluxo de trabalho poderá ser necessária para o cabeçalho ou a linha da fatura, ou ambos. Os controles do fluxo de trabalho se aplicam ao cabeçalho ou linha, dependendo de onde o foco estiver ao selecionar no controle. Em vez do botão **Lançar**, um botão **Enviar** envia a fatura do fornecedor por meio do processo de revisão.

### <a name="preventing-invoice-from-being-submitted-to-workflow"></a>Impedir que a fatura seja enviada para o fluxo de trabalho 

A seguir, veja várias formas de impedir que uma fatura seja enviada para um fluxo de trabalho.

- **O total da fatura e o total registrado não são iguais.** O usuário que enviou a fatura receberá um alerta informando que os totais não são iguais. Esse alerta dá ao usuário a oportunidade de corrigir os saldos antes de reenviar a fatura ao sistema de fluxo de trabalho. Este recurso ficará disponível se o parâmetro **Proibir o envio para o fluxo de trabalho quando o total da fatura e o total da fatura registrada não forem iguais** na página **Gerenciamento de recursos** e o parâmetro **Opção de fluxo de trabalho quando o total faturado e o total registrado não são iguais** na página **Parâmetros de contas a pagar** forem ativados. 
- **A fatura contém encargos não alocados.** O usuário que enviou a fatura receberá um alerta informando que a fatura tem encargos não alocados. Dessa forma, o usuário pode corrigir a fatura antes de reenviá-la para o sistema de fluxo de trabalho. Este recurso está disponível se o parâmetro **Proibir o envio para o fluxo de trabalho quando há encargos não alocados em uma fatura de fornecedor** na parâmetro **Gerenciamento de recursos** e o parâmetro **Opção de fluxo de trabalho quando há encargos não distribuídos** na página **Parâmetros de contas a pagar** estiverem ativados.
- **A fatura contém o mesmo número de fatura de outra fatura lançada.** O usuário que enviou a fatura receberá um alerta de que foi encontrada uma fatura com número duplicado. O usuário pode corrigir o número duplicado antes de reenviar a fatura ao sistema de fluxo de trabalho. O alerta será mostrado se o parâmetro **Verificar o número de fatura usado** no Contas a pagar for definido como **Rejeitar duplicata**. Este recurso estará disponível se o parâmetro **Proibir o envio para o fluxo de trabalho quando o número da fatura já existir em uma fatura lançada e o sistema não estiver configurado para aceitar números de fatura duplicados** na página **Gerenciamento de recursos** estiver ativado.
- **A fatura contém uma linha em que a quantidade da fatura é menor que a quantidade de recebimento de produto correspondente.** O usuário que enviar a fatura ou tentar lançá-la receberá uma mensagem informando que as quantidades não são iguais. Essa mensagem dá ao usuário a oportunidade de corrigir os valores antes de reenviar a fatura ao sistema de fluxo de trabalho. Este recurso está disponível se o parâmetro **Bloquear lançamento e envio de faturas de fornecedor para o fluxo de trabalho** na página **Gerenciamento de recursos** e o parâmetro **Bloquear lançamento e envio para fluxo de trabalho** na página **Parâmetros de contas a pagar** estiverem ativados.

## <a name="matching-vendor-invoices-to-product-receipts"></a>Conciliando faturas de fornecedor com os recebimentos de produtos

Você pode inserir e salvar informações para as faturas de fornecedores e pode conciliar linhas de fatura a linhas de recebimento de produtos. Você também pode conciliar quantidades parciais para uma linha.

Você pode criar uma fatura de fornecedor com base nos itens de linha de recebimento de produtos até a data atual, mesmo que todos os itens de determinada ordem de compra ainda não tenham sido recebidos. Por exemplo, é possível usar esta opção se um fornecedor enviar uma fatura por mês cobrindo todas as entregas enviadas pelo fornecedor durante esse mês. Cada recebimento de produtos representa uma entrega parcial ou completa dos itens da ordem de compra.

Quando uma fatura está no fluxo de trabalho, o aprovador pode atualizar as quantidades da fatura para que correspondam ao valor no campo **Quantidade de recebimentos de produtos a serem conciliados**. Para fazer isso, selecione o recurso **Atualizar as quantidades da fatura para conciliar as quantidades do recibo do produto no de fluxo de** no espaço de trabalho **Gerenciamento de recursos**, e selecione **Habilitar**. Se um aprovador no processo do fluxo de trabalho tiver removido todas as conciliações de todos os recibos de produtos da linha da fatura, a linha da fatura será excluída. Quando esse recurso não está habilitado, as quantidades da fatura não são atualizadas para fatura no fluxo de trabalho.

Quando você lança a fatura, a **Quantidade a faturar** de cada item é atualizada com o total das quantidades recebidas dos recebimentos de produtos selecionados. Se a quantidade **A faturar** e a quantidade **A entregar** de todos os itens na ordem de compra for 0 (zero), o status da ordem de compra é alterado para **Faturado**. Se a quantidade **A faturar** for diferente de 0, o status da ordem de compra permanece inalterado, e faturas adicionais podem ser inseridas para ela.

Esta opção pressupõe que pelo menos um recebimento de produtos tenha sido lançado para a ordem de compra. A fatura de fornecedor baseia-se nesses recebimentos de produtos e reflete suas quantidades. As informações financeiras da nota fiscal baseiam-se nas que são inseridas quando você lança essa nota.

Para saber mais, consulte [Registrar fatura de fornecedor e corresponder com a quantidade recebida](../accounts-payable/tasks/record-vendor-invoice-match-against-received-quantity.md).

## <a name="configure-an-automated-task-for-vendor-invoice-workflow-to-post-the-vendor-invoice-using-a-batch-job"></a>Configurar uma tarefa automatizada para o fluxo de trabalho da fatura de fornecedor lançar a fatura de fornecedor usando um trabalho em lotes

Você pode adicionar uma tarefa de lançamento automatizada ao fluxo de trabalho da fatura de fornecedor para que as faturas sejam processadas em um lote. Lançar faturas em um lote permite que o processo do fluxo de trabalho continue sem precisar aguardar o lançamento ser concluído, o que aprimora o desempenho geral de todas as tarefas enviadas para o fluxo de trabalho.

Para lançar uma fatura de fornecedor em um lote, na página **Gerenciamento de recursos**, acione o parâmetro **Lançamento em lotes de fatura de fornecedor**. Os fluxos de trabalho de fatura de fornecedor são configurados ao acessar **Contas a pagar > Configuração > Fluxos de trabalho de contas a pagar**.

Você pode ver que a tarefa **Lançar a fatura de fornecedor usando um lote** no editor de fluxos de trabalho, independentemente do parâmetro do recurso, **Lançamento em lotes de fatura de fornecedor**, está habilitada. Quando o parâmetro do recurso não estiver habilitado, uma fatura que contenha **Lançar a fatura de fornecedor usando uma tarefa em lotes** não será processada no fluxo de trabalho até que o parâmetro seja habilitado. A tarefa **Lançar fatura de fornecedor usando um lote** não será usada no mesmo fluxo de trabalho da tarefa automatizada **Lançar faturas de fornecedor**. Além disso, a tarefa **Lançar a fatura de fornecedor usando um lote** deve ser o último elemento na configuração do fluxo de trabalho.

Você pode especificar o número de faturas a ser incluído no lote, e o número de horas a aguardar antes de reagendar um lote, acessando **Contas a pagar > Configuração > Parâmetros de contas a pagar > Fatura > Fluxo de trabalho da fatura**. 

## <a name="working-with-multiple-invoices"></a>Trabalhando com diversas faturas

Você pode trabalhar com várias faturas ao mesmo tempo e lançar todas elas ao mesmo tempo. Se você precisar criar várias faturas, use a página **Faturas de fornecedor pendentes**. Se você precisar lançar e imprimir várias faturas de fornecedor, use o **Diário de aprovação de fatura**. Se você estiver usando o **Diário de aprovação de fatura**, pelo menos um recebimento de produtos deverá ser lançado para a ordem de compra, e uma fatura para a ordem de compra deverá ser lançada em um registro de fatura. As informações financeiras para a nota fiscal vêm da nota fiscal que foi lançada no registro.

## <a name="recovering-vendor-invoices-that-are-being-used"></a>Recuperando faturas de fornecedor em uso

Quando uma fatura de fornecedor está sendo usada, ela não pode ser editada por outro usuário. Porém, às vezes o estado de uma fatura pode indicar que ela está em uso, mesmo que não esteja sendo ativamente editada. Por exemplo, o aplicativo pode ter parado de responder enquanto a fatura estava sendo editada ou um usuário pode ter deixado a fatura aberta inadvertidamente no aplicativo.

Você pode usar a página **Recuperar faturas de fornecedor** para recuperar ou liberar faturas de fornecedor que estiveram em uso por mais de quatro horas, para que possam ser editadas. É possível abrir essa página na navegação **Tarefa periódica** ou em um bloco no espaço de trabalho **Entrada de fatura de fornecedor**. Depois que uma fatura for recuperada, estará disponível para edição na página **Fatura de fornecedor**.

Você pode acessar a página **Recuperar faturas de fornecedor** somente se o direito e o privilégio de segurança **Recuperar faturas de fornecedor em uso** estão atribuídos a você. Além disso, o parâmetro **Permitir recuperação de fatura de fornecedor** na página **Parâmetros de contas a pagar** deve ser ativado.

## <a name="resetting-the-workflow-status-for-vendor-invoices-from-unrecoverable-to-draft"></a>Redefinição do status do fluxo de trabalho para faturas de fornecedor de Irrecuperável para Rascunho

Uma instância de fluxo de trabalho que foi interrompida por causa de um erro irrecuperável terá um status de fluxo de trabalho de **Irrecuperável**. Quando o status de um fluxo de trabalho de fatura de fornecedor for **Irrecuperável**, você poderá redefini-lo como **Rascunho** ao selecionar **Cancelar**. Você pode editar a fatura do fornecedor. Esse recurso estará disponível se o parâmetro **Redefinindo o status do fluxo de trabalho para faturas de fornecedor de Irrecuperável para Rascunho** na página **Gerenciamento de recursos** estiver ativado.

Você pode usar a página **Histórico do fluxo de trabalho** para redefinir o status do fluxo de trabalho como **Rascunho**. Você pode abrir essa página desde **Fatura de fornecedor** ou da navegação **Comum > Consultas > Fluxo de trabalho**. Para redefinir o status de fluxo de trabalho como **Rascunho**, selecione **Cancelar**. Você também pode redefinir o status de fluxo de trabalho como Rascunho ao selecionar a ação **Cancelar** na página **Fatura de fornecedor** ou **Faturas de fornecedor pendentes**. Depois que o status do fluxo de trabalho é redefinido como **Rascunho**, ele fica disponível para edição na página **Fatura de fornecedor**.

## <a name="viewing-the-invoice-total-on-the-pending-vendor-invoices-page"></a>Exibição do total da fatura na página Faturas de fornecedor pendentes

Você pode exibir o total da fatura na página **Faturas de fornecedor pendentes** ao habilitar o parâmetro **Exibir total da fatura em faturas de fornecedor pendentes** na página **Parâmetros de contas a pagar**. 

## <a name="vendor-open-transactions-report"></a>Relatório de transações abertas do fornecedor

O relatório **Transações abertas do fornecedor** fornece informações detalhadas sobre as transações abertas para cada fornecedor a partir da data especificada. Esse relatório é geralmente usado durante o procedimento de auditoria para verificar saldos entre transações de livros de fornecedores e transações de contas contábeis.

Para cada transação, o relatório inclui os seguintes detalhes:

- Número da fatura
- Data da transação
- Número do comprovante
- Valor da transação na moeda da transação e na moeda contábil
- Saldo de crédito na moeda da transação e na moeda contábil
- Saldo de débito na moeda da transação e na moeda contábil
- O valor do subtotal na moeda contábil
- Data de vencimento do pagamento

### <a name="filter-the-data-on-the-report"></a>Filtrar os dados no relatório

Quando você gera o relatório **Transações abertas do fornecedor**, os seguintes parâmetros padrão são disponibilizados. Você pode usá-los para filtrar os dados que serão incluídos no relatório.

- **Excluir liquidação futura** – marque esta caixa de seleção para excluir as transações que são liquidadas após a data inserida no campo **Transações abertas por**.
- **Transações abertas por** – insira uma data para incluir transações que estão abertas a partir dessa data. Se você não inserir uma data, esse campo será definido como a data máxima. A data máxima é a última data que o sistema aceitará, 31 de dezembro de 2154. Por padrão, na próxima vez que o relatório for executado, esse campo será definido como a última data inserida nele.

Você pode usar os filtros do campo **Registro a ser incluído** para limitar ainda mais os dados da transação incluídos no relatório.

## <a name="additional-resources"></a>Recursos adicionais

- [Configurar políticas de fatura de fornecedores](../accounts-receivable/tasks/set-up-vendor-invoice-policies.md)
- [Dados principais de nota fiscal no sistema AP usando a nota fiscal de fornecedor](tasks/key-invoice-data-ap-system-vendor-invoice.md)
- [Dados-chave de fatura em contas a pagar usando um diário de aprovações](tasks/key-invoice-data-into-ap-system-approval-journal.md)
- [Dados-chave de fatura no sistema de AP usando grupo de faturas](tasks/key-invoice-data-into-ap-system-invoice-pool.md)
- [Registrar uma fatura de fornecedor no diário de faturas](tasks/record-vendor-invoice-invoice-journal.md)


[!INCLUDE[footer-include](../../includes/footer-banner.md)]
