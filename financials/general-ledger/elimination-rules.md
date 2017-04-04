---
title: "Regras de eliminação"
description: "Este tópico oferece informações sobre regras de eliminação e as opções mais sobre relatar para eliminações."
author: RobinARH
manager: AnnBe
ms.date: 04/04/2017
ms.topic: article
ms.prod: 
ms.service: Dynamics365Operations
ms.technology: 
ms.search.form: LedgerEliminationRule
audience: Application User
ms.reviewer: RobinARH
ms.search.scope: AX 7.0.0, Operations, Core
ms.custom: 13131
ms.assetid: 08fd46ef-2eb8-4942-985d-40fd757b74a8
ms.search.region: Global
ms.author: aolson
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
translationtype: Human Translation
ms.sourcegitcommit: db4b05bc55d735513d7580ca5908a1e84eb760c6
ms.openlocfilehash: 152b63fdfc78b3c4e79b93340d18c5cf69257024
ms.lasthandoff: 03/31/2017


---

# <a name="elimination-rules"></a>Regras de eliminação

Este tópico oferece informações sobre regras de eliminação e as opções mais sobre relatar para eliminações.

As transações de eliminação são necessárias quando uma entidade legal pai faz negócios com uma ou mais entidades legais subsidiárias e usa relatórios financeiros consolidados. Os demonstrativos financeiros consolidados devem incluir somente transações que ocorrem entre a organização consolidada e outras entidades fora das organizações. Portanto, as transações entre entidades legais que são parte da mesma organização devem ser removidas ou eliminadas, contabilidade, o que delass não aparecerão nos relatórios financeiros. Há várias formas de relatar eliminações:

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
<td>Você processar alocações corporativas. Alocações são atividades para qualquer conta que está alocada, independentemente do módulo de origem.</td>
</tr>
</tbody>
</table>

## <a name="example"></a>exemplo
A pessoa jurídica, A pessoa jurídica, parâmetros widgets a outra entidade legal em sua organização, entidade legal B. O exemplo a seguir mostra como as transações que ocorrem entre as duas entidade legal podem ter para ser eliminadas:

-   A Entidade legal A vendem um widget do que custa 10,00 para a entidade legal B por 10,00.
-   A Entidade legal A vendem um widget do que custa 10,00 para a entidade legal B por 10,00, mais 2,00 em custos de remessa.
-   A Entidade legal A vendem um widget do que custa 10,00 para a entidade legal B por 15,00 e reconhecem uma margem na venda.
-   A Entidade legal A vendem um widget do que custa 10,00 para a entidade legal B por 15,00 e reconhecem metade da margem na venda. A Entidade legal B reconhecem a outra metade da margem na venda. Consequentemente, a receita é dividida. A receita dividida oferece um incentivo para a ordem de outra entidade legal na organização em vez de uma organização externa.

Todas essas transações criam transações intercompanhia lançadas em contas a vencer ou vencidas. Em adição, essas transações podem incluir valores de marcação se o valor de venda intercompanhia não for igual ao custo dos produtor que são vendidos.

## <a name="set-up-elimination-rules"></a>Configurar regras de eliminação
Ao configurar regras de eliminação em dynamics 365 para operações, recomendamos que você criar uma dimensão financeira especificamente para fins de eliminação. A maioria de clientes ele parceiro comercial ou algo semelhante. Se você decidir não usar uma dimensão financeira, verifique ter contas principais que são específicas para transações intercompanhia apenas. 

O de instalação para eliminações é encontrado na área de instalação do módulo de consolidações. Depois de digitar uma descrição para a regra, escolha a empresa à qual o diário de eliminação será lançada. Essa será a empresa que ** uso para o processo de eliminação financeiro ** selecione a configuração da entidade legal. 

Você pode definir uma data em que a regra de eliminação se tornam efetivas e quando é expirada, se necessário. Defina ativos ** ** ** Sim ** se desejar estar disponível no processo de proposta de eliminação. Selecione um nome de diário de com um tipo ** ** eliminação.

Depois de definir os princípios, você poderá definir regras de processamento em reais ** ** linhas. Há duas opções das eliminações, eliminando o valor líquido de modificação ou definir um valor fixo. 

Selecione a conta de origem. Você pode usar um asterisco (\*) como uma curingas. Por exemplo, 1\* deve selecionar todas as contas que começam com um 1 como uma fonte de dados da alocação. 

Depois selecionado as contas de origem, ** especificação de conta ** determina a conta da empresa de destino que será usada. ** Origem ** selecione se quiser usar a mesma conta principal definida ** ** origem da conta. Se selecionar ** ** definido pelo usuário, você deve especificar uma conta de destino. 

O ato de especificação da dimensão da mesma maneira. Se selecionar ** ** origem, usará as mesmas dimensões na empresa de destino que a empresa de origem. Se selecionar ** ** definido pelo usuário, você precisará especificar as dimensões na empresa de destino clicando ** dimensões de destino ** o item de menu. 

Selecione as dimensões de origem e as dimensões financeiras e os valores usados como a fonte de eliminação.

## <a name="process-elimination-transactions"></a>Processar transações de eliminação
Há duas maneiras de processar transações de eliminação, durante o processo de consolidação online ou criando um diário e executar uma eliminação da proposta de eliminação suzana. Esta seção centra-se sobre a criação de diário e de execução o processo de eliminação. 

Uma empresa definida como uma empresa de eliminação, selecione ** ** diário de eliminação no módulo de consolidações. Depois selecionado o nome de diário, clique ** ** linhas. Você pode executar a proposta selecionando ** propostas ** o menu e selecionando ** ** proposta de eliminação.

Selecione a empresa que é a origem de dados consolidados, e escolha a regra que deseja processar. Insira uma data inicial para iniciar a pesquisa dos valores de eliminação, e fim a encerrar a data de pesquisa para valores de eliminação. ** Data de postagem de GL ** o campo é a data usada para lançar o diário na contabilidade. Após clicar ** OK **, examine os valores e lançar o diário.


