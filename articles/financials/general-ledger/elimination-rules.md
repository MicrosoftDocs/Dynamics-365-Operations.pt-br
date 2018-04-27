---
title: "Regras de eliminação"
description: "Este tópico fornece informações sobre regras de eliminação e as diversas opções para relatórios sobre eliminações."
author: aprilolson
manager: AnnBe
ms.date: 01/11/2018
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: LedgerEliminationRule
audience: Application User
ms.reviewer: twheeloc
ms.search.scope: Core, Operations
ms.custom: 13131
ms.assetid: 08fd46ef-2eb8-4942-985d-40fd757b74a8
ms.search.region: Global
ms.author: aolson
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: a0739304723d19b910388893d08e8c36a1f49d13
ms.openlocfilehash: 882b8f21be94b8cbb0c162c965ffc129b47d7edf
ms.contentlocale: pt-br
ms.lasthandoff: 03/26/2018

---

# <a name="elimination-rules"></a>Regras de eliminação

[!INCLUDE [banner](../includes/banner.md)]

Este tópico fornece informações sobre regras de eliminação e as diversas opções para relatórios sobre eliminações.

As transações de eliminação são necessárias quando uma entidade legal principal faz negócios com uma ou mais entidades legais subsidiárias e usa relatórios financeiros consolidados. Os demonstrativos financeiros consolidados devem incluir somente transações que ocorrem entre a organização consolidada e outras entidades fora das organizações. Portanto, as transações entre as entidade legais que fazem parte da mesma organização devem ser removidas, ou eliminadas, da contabilidade, de forma que não apareçam em relatórios financeiros. Há várias formas de relatar eliminações:

-   Uma regra de eliminação pode ser criada e processadas em uma empresa de consolidação ou de eliminação.
-   Os relatórios financeiros podem ser usados para mostrar as contas e dimensões de eliminações em uma linha ou em uma coluna específica.
-   Uma entidade legal independente podem ser usada para lançar entradas manuais de transação para rastrear eliminações.

Este tópico se concentra nas regras de eliminação processadas em uma empresa de consolidação ou de eliminação. Você pode configurar regras de eliminação para criar transações de eliminação em uma entidade legal que é especificada como a entidade legal de destino para eliminações ou a entidade legal de eliminação. Essas entidade legal de destino são conhecidas como a pessoa jurídica de eliminação. Os diários de eliminação podem ser integrados durante o processo de consolidação ou usando uma proposta de diário de eliminação. Antes de configurar as regras de eliminação, você deve se familiarizar com os seguintes termos:

-   **Entidade legal de origem** – a entidade legal em que os valores que estão sendo eliminados foram lançados.
-   **Entidade legal de destino** – a entidade legal em que as regras de eliminação são lançadas.
-   **Entidade legal de eliminação** – a entidade legal especificada como a entidade legal de destino para eliminações.
-   **Entidade legal consolidada** – a entidade legal criada para relatar resultados financeiros para um grupo de entidades legais. Os dados financeiros das entidades legais são consolidados nessa entidade legal e, em seguida, é criado um relatório financeiro com os dados combinados.

A tabela a seguir mostra os tipos de transações que podem ter para ser eliminadas.

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th>Tipo de transação</th>
<th>exemplo</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td>Entrada e faturamento de ordem de venda (processamento centralizado)</td>
<td>Você vende um produto para um cliente em nome de outra entidade legal na organização.</td>
</tr>
<tr class="even">
<td>Entrada de ordem de venda (intercompanhia/intracompanhia) e faturamento</td>
<td>Você vender produtos entre entidade legal na organização.</td>
</tr>
<tr class="odd">
<td>Ordens de compra (processamento centralizado)</td>
<td>Seu estoque de compras, fornecimentos, serviços, ativos fixos e outros produtos de um fornecedor em nome de outra entidade legal em sua organização.</td>
</tr>
<tr class="even">
<td>Gerenciamento de estoque (intercompanhia/intracompanhia)</td>
<td><ul>
<li>Transferir o estoque da pessoa jurídica para os ativos fixos de outra entidade legal na organização.</li>
<li>Transferir o estoque da pessoa jurídica para o estoque de outra entidade legal na organização.</li>
</ul></td>
</tr>
<tr class="odd">
<td>Rastreamento de estoque em trânsito</td>
<td>Transferir itens entre depósitos na mesma entidade legal, mas em locais geográficos diferentes.</td>
</tr>
<tr class="even">
<td>Processamento de fatura centralizada de contas a pagar</td>
<td>Você registra uma fatura em nome de outra entidade legal na organização.</td>
</tr>
<tr class="odd">
<td>Processamento de pagamento centralizado de contas a pagar</td>
<td>Você paga uma fatura em nome de outra entidade legal na organização.</td>
</tr>
<tr class="even">
<td>Gerenciamento de caixa/tesouraria (processamento centralizado)</td>
<td><ul>
<li>Você processa pagamentos de impostos, reembolsos de impostos, encargos de juros, empréstimos, adiantamentos, dividendos pagos e royalties pré-pagos/comissões.</li>
<li>Você paga uma despesa em nome de outra entidade legal na organização. A fatura é inserida nos registros da pessoa jurídica de destino, e você deve entre acordo entre entidade legal. Por exemplo, uma pessoa jurídica paga o relatório de despesas de um funcionário em outra entidade legal. Nesse caso, o relatório de despesas do funcionário tem despesas relacionadas a outra entidade legal.</li>
<li>Transferir dinheiro de uma entidade legal a outras na organização.</li>
</ul></td>
</tr>
<tr class="odd">
<td>Contas a receber (processamento centralizado)</td>
<td>Você recebe o pagamento à vista para a fatura de cliente de outra entidade legal, e você lhe o cheque na conta bancária de essa entidade legal.</td>
</tr>
<tr class="even">
<td>Folha de pagamento (processamento centralizado, intercompanhia/intracompanhia)</td>
<td><ul>
<li>Você paga a folha de pagamento de outra entidade legal. Por exemplo, uma entidade legal paga sua própria folha de pagamento para seus funcionários, mas cobra de volta trabalhos que um funcionário fez para outra entidade legal durante o aquele ciclo de pagamento. Ou, um funcionário trabalhou metade do tempo para a entidade legal A e de meio expediente da entidade legal, B e os benefícios seja entre todos os pagamentos. Nesses casos, o pagamento do funcionário inclui o pagamento das duas entidade legal. São lançados não só os salários, mas impostos, benefícios, deduções e acúmulos para salários também são lançados.</li>
<li>Transferências de trabalho de um departamento ou divisão para a outra.</li>
</ul></td>
</tr>
<tr class="odd">
<td>Ativos fixos (intercompanhia/intracompanhia)</td>
<td>Transferir ativos fixos para os ativos fixos ou estoque de outra entidade legal.</td>
</tr>
<tr class="even">
<td>Alocações (intercompanhia/intracompanhia)</td>
<td>Você processa alocações corporativas. Alocações são atividades para qualquer conta que está alocada, independentemente do módulo de origem.</td>
</tr>
</tbody>
</table>

## <a name="example"></a>exemplo
A pessoa jurídica, pessoa jurídica A, vende widgets a outra entidade legal em sua organização, entidade legal B. O exemplo a seguir mostra como as transações que ocorrem entre as duas entidades legais podem ter que ser eliminadas:

-   A Entidade legal A vende um widget que custa 10,00 para a entidade legal B por 10,00.
-   A Entidade legal A vende um widget que custa 10,00 para a entidade legal B por 10,00, mais 2,00 em custos de remessa.
-   A Entidade legal A vende um widget que custa 10,00 para a entidade legal B por 15,00 e reconhece uma margem na venda.
-   A Entidade legal A vende um widget do que custa 10,00 para a entidade legal B por 15,00 e reconhecem metade da margem na venda. A Entidade legal B reconhece a outra metade da margem na venda. Consequentemente, a receita é dividida. A receita dividida oferece um incentivo para a ordem de outra entidade legal na organização em vez de uma organização externa.

Todas essas transações criam transações intercompanhia lançadas em contas a vencer ou vencidas. Em adição, essas transações podem incluir valores de marcação se o valor de venda intercompanhia não for igual ao custo dos produtor que são vendidos.

## <a name="set-up-elimination-rules"></a>Configurar regras de eliminação
Ao configurar regras de eliminação no Microsoft Dynamics 365 for Finance and Operations, recomendamos que você crie uma dimensão financeira especificamente para fins de eliminação. A maioria dos clientes a nomeia como Parceiro comercial ou algo semelhante. Se optar por não usar uma dimensão financeira, certifique-se de ter contas principais específicas para transações intercompanhia apenas. 

A configuração das eliminações é encontrada na área Configuração do módulo Consolidações. Depois de digitar uma descrição para a regra, escolha a empresa na qual o diário de eliminação será lançado. Esta empresa deve ter a opção **Usar para o processo de eliminação financeira** selecionada na configuração da entidade legal. 

Você pode definir uma data em que a regra de eliminação se torna efetiva e é expirada, se necessário. Defina **Ativo** como **Sim** se quiser que ele fique disponível no processo da proposta de eliminação. Selecione um nome de diário com o tipo **Eliminação**.

Depois de definir os princípios, você poderá definir regras de processamento em reais **Linhas**. Há duas opções das eliminações, eliminar o valor líquido de modificação ou definir um valor fixo. 

Selecione a conta de origem. Você pode usar asterisco (\*) como curinga. Por exemplo, 1\* selecionaria todas as contas que começam com 1 como a fonte de dados da alocação. 

Depois de selecionar as contas de origem, a **Especificação da conta** determina a conta da empresa de destino que é usada. Selecione **Origem** se quiser usar a mesma conta principal definida na conta de **Origem**. Se você selecionar **Definido pelo usuário**, deverá especificar a conta de destino. 

A especificação da dimensão atua da mesma maneira. Se você selecionar **Origem**, ela usará as mesmas dimensões da empresa de destino na empresa de origem. Se você selecionar **Definido pelo usuário**, será necessário especificar as dimensões da empresa de destino, clicando no item de menu **Dimensões de destino**. 

Selecione as dimensões de origem e as dimensões financeiras e os valores usados como a fonte de eliminação.

## <a name="process-elimination-transactions"></a>Processar transações de eliminação
Há duas maneiras de processar transações de eliminação, durante o processo de consolidação online ou criando um diário de eliminação e executando o processo de proposta de eliminação. Esta seção concentra-se na criação do diário e na execução do processo de eliminação. 

Em uma empresa definida como empresa de eliminação, selecione **Diário de eliminação** no módulo Consolidações. Depois de selecionado o nome do diário, clique em **Linhas**. Você pode executar a proposta selecionando o menu **Propostas** e depois selecionando a **Proposta de eliminação**.

Selecione a empresa que é a origem de dados consolidados e escolha a regra que deseja processar. Insira uma data de início para iniciar a pesquisa dos valores de eliminação e a data de término para encerrar a data de pesquisa para valores de eliminação. O campo **Data de lançamento GL** é a data usada para lançar o diário na contabilidade. Após clicar em **OK**, você pode revisar os valores e lançar no diário.




