---
title: Criar uma fatura de cliente
description: Uma **fatura de cliente para uma ordem de venda** é uma nota que está relacionada a uma venda, e que uma organização fornece a um cliente.
author: ShivamPandey-msft
ms.date: 01/12/2018
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: CustFreeInvoice
audience: Application User
ms.reviewer: roschlom
ms.custom: 77772
ms.assetid: 00b4b40c-1576-4098-9aed-ac376fdeb8c5
ms.search.region: Global
ms.author: shpandey
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: c033684e56f97a5da80a1934ee1299229f58cfba
ms.sourcegitcommit: 0e8db169c3f90bd750826af76709ef5d621fd377
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/01/2021
ms.locfileid: "5830607"
---
# <a name="create-a-customer-invoice"></a>Criar uma fatura de cliente

[!include [banner](../includes/banner.md)]

Uma **fatura de cliente para uma ordem de venda** é uma nota que está relacionada a uma venda, e que uma organização fornece a um cliente. Esse tipo de fatura de cliente é criado com base em uma ordem de venda, que inclui linhas de ordem e números de item. Os números de item são especificados e lançados no razão. As entradas no diário-razão auxiliar não estão disponíveis para uma fatura de cliente de uma ordem de venda. Para obter mais informações, consulte [Criar faturas de ordem de venda](tasks/create-sales-order-invoices.md).

Uma **fatura de texto livre** não está relacionada a uma ordem de venda. Ela contém linhas de ordem que incluem contas contábeis, descrições de texto livre e um valor de venda que você insere. Não é possível inserir um número de item neste tipo de fatura. Você deverá inserir as informações apropriadas de impostos sobre vendas. Uma conta principal para a venda é indicada em cada linha da fatura, que você pode distribuir para diversas contas contáveis clicando em **Distribuir valores** na página **Fatura de texto livre**. Além disso, o saldo do cliente é lançado na conta resumo do perfil de lançamento usado para a fatura de texto livre.

Para obter mais informações, consulte: 

[Criar faturas de texto livre](../accounts-receivable/create-free-text-invoice-new.md)

[Criar um modelo de fatura de texto livre](../accounts-receivable/create-free-text-invoice-template-new.md)

[Atribuir um modelo de fatura de texto livre a um cliente](tasks/assign-free-text-invoice-template-customer.md)

[Gerar e lançar faturas de texto livre recorrentes](tasks/post-recurring-free-text-invoices.md)


Uma **fatura pro forma** é uma fatura preparada como uma previsão dos valores da fatura real antes de a fatura ser lançada. Você pode imprimir uma fatura pro forma de uma fatura de cliente de uma ordem de venda ou de uma fatura de texto livre.

## <a name="post-and-print-individual-customer-invoices-that-are-based-on-sales-orders"></a>Lançar e imprimir faturas de clientes individuais com base em ordens de venda
Use este processo para criar uma fatura com base em uma ordem de venda. É possível fazer isso se você decidir faturar o cliente antes de entregar as mercadorias ou os serviços. 

Quando você lança uma fatura, a quantidade **A faturar** de cada item é atualizada com o total das quantidades faturadas da ordem de venda selecionada. Se a quantidade **A faturar** e a quantidade **A entregar** de todos os itens na ordem de venda for 0 (zero), o status da ordem de venda é alterado para **Faturado**. Se a quantidade **A faturar** for diferente de 0 (zero), o status da ordem de venda permanece inalterado, e faturas adicionais podem ser inseridas para ela.

Você pode exibir o status da ordem de venda na página de listagem **Todas as ordens de venda**. Use a página de listagem **Abrir faturas de cliente** para exibir as faturas lançadas.

## <a name="post-and-print-individual-customer-invoices-that-are-based-on-packing-slips-and-the-date"></a>Lançar e imprimir faturas de cliente individuais com base em guias de remessa e data
Use este processo quando uma ou mais guias de remessa tiverem sido lançadas para a ordem de venda. A fatura de cliente baseia-se nessas guias de remessa e reflete as quantidades nelas indicadas. As informações financeiras da fatura baseiam-se nas que são inseridas quando você lança essa nota. 

Você pode criar uma fatura de cliente com base nos itens de linha da guia de remessa que foram remetidos até a data, mesmo que todos os itens de determinada ordem de venda ainda não tenham sido remetidos. Você poderá fazer isso, por exemplo, se a sua entidade legal emitir uma fatura por cliente por mês cobrindo todas as entregas remetidas durante esse mês. Cada guia de remessa representa uma entrega parcial ou completa dos itens da ordem de venda. 

Quando você lança a fatura, a quantidade **A faturar** de cada item é atualizada com o total das quantidades entregues das guias de remessa selecionadas. Se a quantidade **A faturar** e a quantidade **A entregar** de todos os itens na ordem de venda for 0 (zero), o status da ordem de venda é alterado para **Faturado**. Se a quantidade **A faturar** for diferente de 0 (zero), o status da ordem de venda permanece inalterado, e faturas adicionais podem ser inseridas para ela. 

As transações de estoque são atualizadas com o número da fatura, e o status no campo **Status da linha** na ordem de venda é alterado para **Faturado**. 

Exiba o status da ordem de venda na página de listagem **Todas as ordens de venda**.

## <a name="consolidate-sales-orders-or-packing-slips-for-posting"></a>Consolidar ordens de venda ou guias de remessa para lançamento
Use este processo quando uma ou mais ordens de venda estiverem prontas para serem faturadas, e você desejar consolidá-las em uma única fatura. 

Você pode selecionar várias faturas na página de listagem **Ordem de venda** e, em seguida, usar a função **Gerar faturas** para consolidá-las. Na página **Lançamento de fatura**, você pode alterar a configuração **Ordem resumida** para resumir por número de ordem (onde houver diversas guias de remessa para uma única ordem de venda) ou por valor de fatura (onde houver diversas ordens de venda para uma única conta de fatura). Use o botão **Organizar** para consolidar as ordens de venda em faturas únicas, com base nas configurações de **Ordem resumida**.

## <a name="additional-settings-that-change-the-posting-behavior"></a>Configurações adicionais que alteram o comportamento dos lançamentos
Os seguintes campos alteram o comportamento do processo de lançamento.

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th>Campo</th>
<th>Descrição</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td>Quantidade</td>
<td>Selecione as quantidades nas quais o lançamento do documento irá se basear. As opções que estão disponíveis variam dependendo do tipo de documento que você está lançando, como uma guia de remessa ou uma fatura.
<ul>
<li><strong>Entregar agora</strong> – Selecione todas as quantidades inseridas no campo <strong>Entregar agora</strong>. Use esta opção para confirmar ou entregar uma ordem parcial.</li>
<li><strong>Separado</strong> – Selecione todas as quantidades que foram separadas.</li>
<li><strong>Todas</strong> – selecione todas quantidades na ordem de venda que ainda não foram atualizadas pelo tipo de documento atual.</li>
<li><strong>Guia de remessa</strong> – Selecione todas as quantidades que foram atualizadas por uma guia de remessa.</li>
<li><strong>Quantidade separada e produtos não estocados</strong> – selecione todas as quantidades que foram separadas e todas as quantidades de produto que não estão armazenadas.</li>
</ul></td>
</tr>
<tr class="even">
<td>Lançamento</td>
<td><ul>
<li>Selecione esta opção para lançar em diário a ordem de venda.</li>
<li>Desmarque esta opção para imprimir uma ordem de venda pro forma. <strong>Observação:</strong> se você fez um acordo para um plano de pagamento, o plano de pagamento não será exibido na ordem de venda pro forma. Os planos de pagamento serão mostrados apenas nas ordens de venda reais.</li>
</ul></td>
</tr>
<tr class="odd">
<td>Seleção posterior</td>
<td>Selecione esta opção para aplicar a consulta selecionada mais tarde. Essa opção é usada para trabalhos em lotes. A consulta será executada quando o trabalho em lotes for executado.</td>
</tr>
<tr class="even">
<td>Reduzir quantidade</td>
<td>Selecione esta opção para reduzir automaticamente a quantidade entregue quando o documento for lançado, de tal modo que a quantidade entregue seja igual ao estoque disponível.</td>
</tr>
<tr class="odd">
<td>Imprimir</td>
<td>Selecione quando imprimir documentos:
<ul>
<li><strong>Atual</strong> – Imprimir documentos após cada fatura ser atualizada.</li>
<li><strong>Após</strong> – Imprimir documentos depois que todas as faturas estiverem atualizadas.</li>
</ul>
<strong>Observação:</strong> O campo <strong>Imprimir</strong> só ficará disponível se você selecionar a opção <strong>Imprimir fatura</strong>, <strong>Imprimir confirmação</strong>, <strong>Imprimir lista de separação</strong>, ou <strong>Imprimir guia de remessa</strong>. Por exemplo, na página <strong>Classificação de formulário</strong>, você configurou o sistema para classificar as informações por conta de fatura. Você pode então selecionar <strong>Depois</strong> para imprimir documentos em um lote que seja classificado por conta de fatura. Caso contrário, os documentos serão impressos antes de o processamento ser realizado e os documentos não serão classificados na ordem especificada na página <strong>Classificação de formulários</strong>.</td>
</tr>
<tr class="even">
<td>Imprimir fatura</td>
<td>Selecionar essa opção para imprimir a fatura. Se esta opção for desativada, você pode lançar uma fatura sem imprimi-la.</td>
</tr>
<tr class="odd">
<td>Enviar email</td>
<td>Selecione esta opção para enviar a fatura para uma ordem de venda para o cliente como um anexo de email após a fatura ser lançada. Os anexos são enviados como arquivos PDF e XML. Esta opção está disponível somente se você selecionar a opção <strong>Habilitar CFD (faturas eletrônicas)</strong> na página <strong>Parâmetros de fatura eletrônica</strong>. <strong>Observação:</strong> (MEX) Esse controle está disponível somente para entidades legais cujo endereço principal está localizado no México.</td>
</tr>
<tr class="even">
<td>Usar o destino do gerenciamento de impressão</td>
<td>Selecione esta opção para usar as configurações de impressão especificadas para a transação, documento, ou módulo na página <strong>Configuração do gerenciamento de impressão</strong>.</td>
</tr>
<tr class="odd">
<td>Verificar limite de crédito</td>
<td>Selecione as informações que devem ser analisadas quando uma verificação de limite de crédito for realizada.
<ul>
<li><strong>Nenhum</strong> – não existem requisitos para a verificação do limite de crédito.</li>
<li><strong>Saldo</strong> – o limite de crédito é comparado ao saldo do cliente.</li>
<li><strong>Saldo + guia de remessa ou recebimento de produtos</strong> – O limite de crédito é verificado em relação ao saldo do cliente e entregas.</li>
<li><strong>Saldo+tudo</strong> – o limite de crédito é verificado em relação ao saldo do cliente, entregas e ordens abertas.</li>
</ul></td>
</tr>
<tr class="even">
<td>Correção de crédito</td>
<td>Marque esta opção para exibir a nota de crédito como débito nas transações de comprovante.</td>
</tr>
<tr class="odd">
<td>Quantidade pendente de crédito</td>
<td>Se você estiver lançando uma nota de crédito, escolha esta opção para manter a quantidade restante na ordem. Se a opção estiver desmarcada, a quantidade restante será definida como 0 (zero).</td>
</tr>
<tr class="even">
<td>Atualização resumida de</td>
<td>Selecione como várias ordens de venda devem ser resumidas:
<ul>
<li><strong>Nenhum</strong> – não resuma ordens de venda. Por exemplo, uma fatura separada será criada para cada ordem de venda.</li>
<li><strong>Conta de fatura</strong> – Resumir todas as ordens selecionadas com base nos critérios configurados na página <strong>Parâmetros de atualização resumida</strong>.</li>
<li><strong>Ordem</strong> – resume um intervalo selecionado de ordens em uma ordem especificada. As ordens são resumidas com base nos critérios configurados na página <strong>Parâmetros de atualização resumida</strong>. Se você selecionar esta opção, será necessário selecionar um valor no campo <strong>Ordem de venda</strong>.</li>
<li><strong>Resumo automático</strong> – Se as atualizações de resumo tiverem sido especificadas na página <strong>Atualizações de resumo</strong>, resuma todas as ordens selecionadas com base nos critérios configurados na página <strong>Parâmetros de atualização resumida</strong>. Se atualizações resumidas não tiverem sido especificadas, a ordem será lançada separadamente.</li>
<li><strong>Guia de remessa</strong> – resume um intervalo selecionado em uma fatura para cada guia de remessa. Esse botão está disponível apenas se <strong>Guia de remessa</strong> estiver selecionada no campo <strong>Quantidade</strong>.</li>
</ul></td>
</tr>
</tbody>
</table>







[!INCLUDE[footer-include](../../includes/footer-banner.md)]