---
title: Um comprovante único
description: Um comprovante único para diários financeiros (diário geral, diário de ativo fixo, diário de pagamentos do fornecedor etc) permite que você insira várias transações do razão auxiliar no contexto de apenas um comprovante.
author: kweekley
ms.date: 11/05/2018
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: LedgerJournalSetup, LedgerParameters, AssetProposalDepreciation
audience: Application User
ms.reviewer: kfend
ms.custom: 14091
ms.assetid: c64eed1d-df17-448e-8bb6-d94d63b14607
ms.search.region: Global
ms.author: kweekley
ms.search.validFrom: 2018-03-16
ms.dyn365.ops.version: 8.0.2
ms.openlocfilehash: fa7a519b87bd5933b8b672f9f9b3e230fd7f2eb4
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/03/2022
ms.locfileid: "8896395"
---
# <a name="one-voucher"></a>Um comprovante

[!include [banner](../includes/banner.md)]
[!include [preview banner](../includes/preview-banner.md)]


## <a name="what-is-one-voucher"></a>O que é "Um comprovante único"?

A funcionalidade existente para diários financeiros (diário geral, diário de ativo fixo, diário de pagamentos do fornecedor etc.) permite que você insira várias transações do diário-razão auxiliar (cliente, fornecedor, ativos fixos, projeto e banco) no contexto de apenas um comprovante. Microsoft se refere a esta funcionalidade como *Um comprovante único*. É possível criar Um comprovante único usando um dos seguintes métodos:

- Configurar o nome do diário (**Contabilidade** \> **Configuração do diário** \>**Nomes de diário**), de forma que o campo **Novo comprovante** seja definido como **Apenas um número de comprovante**. Cada linha que você adiciona ao diário agora será incluída no mesmo comprovante. Portanto, o comprovante poderá ser inserido como um comprovante multilinha, como uma conta/contrapartida na mesma linha, ou como uma combinação.

    [![Linha única.](./media/same-line.png)](./media/same-line.png)

    > [!IMPORTANT]
    > A definição de Um comprovante **não** cobre casos onde nomes de diários são definidos como **Apenas um número de comprovante**, mas o usuário insere um comprovante que inclui apenas tipos de contas contábeis. Neste artigo, 'Um comprovante' significa que há um comprovante que contém mais de um fornecedor, cliente, banco, ativo fixo ou projeto.

- Entre em um comprovante combinado onde não haja contrapartida.

    [![Comprovante combinado.](./media/Multi-line.png)](./media/Multi-line.png)

- Entre em um comprovante onde a conta e a contrapartida contêm um tipo de conta de diário-razão auxiliar, como **Fornecedor**/**Fornecedor**, **Cliente**/**Cliente**, **Fornecedor**/**Cliente** ou **Banco**/**Banco**.

    [![Comprovante do diário-razão auxiliar.](./media/subledger.png)](./media/subledger.png)

## <a name="issues-with-one-voucher"></a>Problemas com Um comprovante único

A funcionalidade Um comprovante único causa problemas durante liquidação, cálculo de imposto, reversão da transação, reconciliação de um diário-razão auxiliar para a contabilidade, relatório financeiro e muito mais. (Por exemplo, para obter mais informações sobre problemas que podem ocorrer durante a liquidação, consulte [Comprovante único com vários registros de cliente ou de fornecedor](../accounts-payable/single-voucher-multiple-customer-vendor-records.md).) Para trabalhar e relatar corretamente, os processos e relatórios exigem detalhes de transação. Embora alguns cenários ainda possam funcionar corretamente, dependendo da configuração da organização, geralmente há problemas quando várias transações são inseridas em um comprovante.

Por exemplo, você lança o seguinte comprovante combinado.

[![Exemplo de um comprovante de várias linhas.](./media/example.png)](./media/example.png)

Em seguida, você gera o relatório **Despesas por fornecedor** no espaço de trabalho **Insights financeiros**. Neste relatório, saldos da conta de despesa são agrupados por grupo de fornecedor e depois, fornecedor. Ao gerar o relatório, o sistema não pode determinar em quais grupos de fornecedores/fornecedor incorreu a despesa de 250,00. Como os detalhes da transação estão faltando, o sistema assume os 250,00 inteiros de despesa incorridos pelo primeiro fornecedor encontrado no comprovante. Portanto, os 250,00 de despesa, que estão incluídos no saldo da conta principal 600120, são mostrados naquele grupo de fornecedores/fornecedor. No entanto, é muito é provável que o primeiro fornecedor do comprovante não seja o fornecedor correto. Portanto, provavelmente o relatório está incorreto.

[![Relatório de despesas por fornecedor.](./media/expenses.png)](./media/expenses.png)

## <a name="the-future-of-one-voucher"></a>O futuro de Um comprovante único

Por causa dos problemas que podem ocorrer quando Um comprovante único é usado, essa funcionalidade no final será preterida. Porém, como há lacunas funcionais que dependem dessa funcionalidade, a substituição não ocorrerá toda de uma vez. Em vez disso, usaremos a seguinte agenda:

- **Versão da primavera de 2018** – a funcionalidade foi desativada por padrão por meio do parâmetro **Permitir várias transações em um comprovante** na guia **Geral** da página **Parâmetros da contabilidade**. Porém, você poderá reativá-la se sua organização tiver um cenário que esteja em uma das lacunas funcionais de negócios listadas posteriormente neste artigo.

    - Se o cenário comercial não exigir um comprovante, recomendamos que você deixe a funcionalidade desativada. Se você usá-lo apesar de existir outra solução, a Microsoft não corrigirá "bugs" nas áreas identificadas mais adiante neste artigo.
    - É recomendável que você pare de usar um comprovante para integrações, a menos que você precise da funcionalidade para uma das lacunas funcionais documentadas.

- **Versões posteriores** – vários requisitos comerciais podem ser atendidos somente usando um comprovante. A Microsoft deve garantir que todos os requisitos comerciais identificados ainda possam ser atendidos no sistema depois que a funcionalidade for preterida. Portanto, novos recursos provavelmente precisarão ser adicionados para preencher as lacunas funcionais. A Microsoft não pode fornecer uma solução específica, pois cada lacuna de recursos é diferente e deve ser avaliada com base nos requisitos comerciais. Algumas lacunas funcionais provavelmente serão substituídas por recursos que ajudam a atender a necessidades comerciais específicas. No entanto, outras lacunas podem ser preenchidas continuando a permitir a entrada em um diário, como quando um comprovante é usado, mas aperfeiçoando o sistema para rastrear mais detalhes, conforme necessário.

Depois que todas as lacunas funcionais forem preenchidas, a Microsoft comunicará que o recurso será preterido. No entanto, a substituição não será efetiva pelo menos um ano após a comunicação. Embora a Microsoft não possa fornecer uma estimativa sobre quando a funcionalidade de um comprovante será preterida, ela provavelmente terá, pelo menos, dois anos antes que a substituição ocorra. A política da Microsoft é deixar pelo menos 12 meses entre o anúncio da funcionalidade preterida e a substituição real, de forma que os clientes e os ISVs (fornecedores independentes de software) tenham tempo de reagir à alteração. Por exemplo, uma organização pode precisar atualizar processos comerciais, entidades e integrações.

A substituição de um comprovante é uma alteração significativa que será amplamente comunicada. Como parte dessa comunicação, a Microsoft atualizará este artigo, lançará uma postagem de blog no blog do Microsoft Dynamics 365 Finance, atualizará o artigo "Recursos removidos ou obsoletos", comunicará a alteração nas conferências apropriadas da Microsoft e assim por diante.

## <a name="why-use-one-voucher"></a>Por que usar Um comprovante único?

Com base em conversas com clientes, a Microsoft compilou a seguinte lista de cenários nos quais os clientes usam a funcionalidade Um comprovante único ou os motivos pelos quais eles a usam. Alguns desses requisitos comerciais podem ser atendidos somente usando Um comprovante único. Porém, para muitos cenários, as alternativas podem atender aos mesmos requisitos de negócios.

### <a name="scenarios-that-require-one-voucher"></a>Cenários que exigem Um comprovante único

Os cenários a seguir podem ser realizados apenas usando a funcionalidade Um comprovante único. Se sua organização tem algum desses cenários, você deve habilitar várias transações a serem inseridas em um comprovante mudando a alteração do parâmetro **Permitir várias transações em um comprovante** na página **Parâmetros de contabilidade**. Essas lacunas funcionais serão preenchidas por outros recursos nas versões posteriores.

> [!NOTE]
> [Para cada um dos seguintes cenários, o campo **Permitir várias transações em um comprovante** deve ser definido como Sim na Guia Rápida **Geral** na página **Parâmetros de contabilidade**].

### <a name="post-vendor-or-customer-payments-in-summary-form-to-a-bank-account"></a>Lançar pagamentos do fornecedor ou do cliente em um formulário de resumo para uma conta bancária

**Cenário** Uma organização comunica uma lista de fornecedores e valores ao banco, e o banco utiliza esta lista para pagar os fornecedores em nome da organização. O banco lança a soma dos pagamentos como uma retirada única na conta bancária.

A recapitulação dos pagamentos do fornecedor é suportada somente através de Um comprovante único. Cada fornecedor é inserido como uma linha separada para manter detalhes na sub-razão de contas a pagar. Entretanto, o valor somado para todos os pagamentos é deslocado para uma única linha da conta bancária. Portanto, a saída é mostrada como um valor único resumido no diário-razão auxiliar do banco.

**Cenário** Uma organização deposita pagamentos do cliente, ou o banco deposita pagamentos do cliente em nome da organização e o depósito é mostrado como uma quantia total na conta bancária.

A recapitulação de pagamentos do cliente geralmente é suportada através da funcionalidade de depósito. Entretanto, se você estiver usando a “transição” no método de pagamento, este cenário é suportado somente através da funcionalidade Um comprovante único. Os pagamentos do cliente são inseridos da mesma maneira descrita para recapitulação de pagamentos do fornecedor.

### <a name="mechanism-to-group-transactions-from-a-business-event"></a>Mecanismo para agrupar transações de um evento de negócios

**Cenário** Uma organização tem um evento de negócios que aciona várias transações. Porém, o departamento de contabilidade deseja exibir as entradas contábeis juntas para melhor a auditabilidade.

Se uma organização tiver que exibir as entradas contábeis de um evento de negócios juntas, ela deverá usar a funcionalidade Um comprovante único. 

### <a name="country-specific-features"></a>Recursos específicos de país/região

**Cenário** O recurso Documento administrativo único (SAD) para Polônia atualmente exige que apenas um comprovante seja usado. Até uma opção de agrupamento ficar disponível para este recurso, você deve continuar usando a funcionalidade Um comprovante único. Pode haver recursos específicos adicionais de país que exigem a funcionalidade Um comprovante único.

### <a name="customer-prepayment-payment-journal-that-has-taxes-on-multiple-lines"></a>Diário de pagamento antecipado de cliente com impostos em várias "linhas"

Neste cenário, os clientes do comprovante único são os mesmos clientes porque a transação simula as linhas de uma ordem do cliente. O pagamento antecipado deve ser inserido em um único comprovante porque o cálculo do imposto deve ser feito nas "linhas" do pagamento único que o cliente fez.

### <a name="customer-reimbursement"></a>Reembolso do cliente

**Cenário** Um cliente faz um pagamento antecipado de uma ordem, e as linhas da ordem têm diferentes impostos que devem ser registrados para o pagamento antecipado. O pagamento antecipado do cliente é uma transação que simula as linhas da ordem, de forma que o imposto apropriado possa ser registrado para o valor em cada linha.

Se a tarefa periódica de reembolso é executada a partir do Módulo de contas a receber, ela cria uma transação para mover o balanço de um cliente para um fornecedor. Para esse cenário, Um comprovante deve ser usado para reembolsar o cliente.

### <a name="fixed-asset-maintenance-catch-up-depreciation-split-asset-calculate-depreciation-on-disposal"></a>Manutenção de ativo fixo: atualizar depreciação, dividir ativo, calcular depreciação na alienação
Com a versão 10.0.21 e posterior, as transações de ativos fixos para atualizar a depreciação, dividir um ativo e calcular a depreciação para a alienação de um ativo serão criadas usando diferentes números de comprovante.

### <a name="bills-of-exchange-and-promissory-notes"></a>Notas promissórias e letras de câmbio
Letras de câmbio e notas promissórias requerem que Um comprovante seja usado, porque as transações movem o saldo do cliente e do fornecedor de um Contas a receber/Contas a pagar contáveis a outro, com base no estado do pagamento.

## <a name="scenarios-that-dont-require-one-voucher"></a>Cenários que não exigem Um comprovante único

Os cenários a seguir podem ser realizados através de outros meios e não devem usar Um comprovante único de funcionalidade.

### <a name="post-customer-payments-in-summary-form-to-the-bank-account"></a>Lançar pagamentos do cliente em um formulário de resumo para a conta bancária

Uma organização deposita pagamentos do cliente, ou o banco deposita pagamentos do cliente em nome da organização e o depósito é mostrado como uma quantia total na conta bancária.

A recapitulação de pagamentos do cliente é suportada através da funcionalidade de depósito quando a transição não é usada no método de pagamento.

### <a name="netting"></a>Remuneração

Na remuneração, os saldos para um fornecedor e cliente são remunerados entre eles porque o fornecedor e o cliente são a mesma parte. Esta abordagem minimiza a troca de dinheiro entre uma organização e a parte do cliente/fornecedor.

A remuneração pode ser realizada inserindo o aumento ou a redução em comprovantes separados e o lançamento da contrapartida em uma conta contábil de compensação.

### <a name="post-in-summary-to-the-general-ledger"></a>Lançar resumo na contabilidade

As organizações geralmente querem lançar o resumo na contabilidade para minimizar o volume de dados. Entretanto, as organizações normalmente ainda exigem que os detalhes da transação sejam mantidos. Quando o lançamento é feito em resumo através de apenas um comprovante, os detalhes da transação não são conhecidos e não podem ser mantidos.

- Como os detalhes da transação atualmente podem ser mantidos, recomendamos que Um Comprovante de organização **não** seja usado para lançar no resumo.
- Depois que o suporte do Um comprovante único for removido, podemos implementar o Documento de origem e as estruturas contábeis nos diários. Essas estruturas manterão os detalhes da transação e suportarão a recapitulação na contabilidade.


### <a name="settle-multiple-unposted-payments-to-the-same-invoice"></a>Liquidar vários pagamentos não lançados na mesma fatura

Esse cenário geralmente é encontrado em organizações nas quais os clientes podem usar vários métodos de pagamento para pagar as compras. Neste cenário, a organização deve ser capaz de registrar vários pagamentos não lançados e liquidá-los com a fatura de cliente.

Um novo recurso adicionado no Microsoft Dynamics 365 for Operations versão 1611 (Novembro de 2016) permite que vários pagamentos não contabilizados sejam liquidados com uma única fatura. Vários pagamentos do cliente não precisam mais ser inseridos em um único comprovante.

### <a name="import-bank-statement-transactions"></a>Importar transações de extrato bancário

Os bancos geralmente fazem e recebem pagamentos em nome de uma organização, e essas transações são registradas no Finance através de um arquivo que é recebido do banco. Geralmente, as organizações querem agrupar essas transações usando o número do extrato bancário no arquivo. Como cada transação é mostrada em detalhes no extrato bancário, nenhuma recapitulação é necessária no diário-razão auxiliar do banco.

As transações podem ser agrupadas usando outros campos no diário, como o número de lote do próprio diário ou o número do documento.


### <a name="transfer-balances"></a>Transferir saldos

Talvez uma organização tenha que transferir o saldo de um fornecedor para outro em decorrência de um erro ou porque outro fornecedor assumiu a responsabilidade. As transferências desse tipo também ocorrem para tipos de conta como, **clientes** e **contas bancárias**.

As transferências de saldo de uma conta (fornecedor, cliente, conta bancária etc.) para outra conta podem ser feitas através de comprovantes separados e a contrapartida pode ser lançada em uma conta contábil de compensação.

### <a name="enter-beginning-balances"></a>Inserir saldo inicial.

Geralmente as organizações inserem os saldos iniciais das contas do diário-razão auxiliar (fornecedores, clientes, ativos fixos etc) em uma transação de comprovante. Os saldos iniciais de cada conta do diário-razão auxiliar podem ser inseridos como comprovantes separados e a contrapartida pode ser lançada em uma conta contábil de compensação.

### <a name="correct-the-accounting-entry-of-a-posted-customer-or-vendor-document"></a>Corrigir a entrada contábil de um documento lançado do cliente ou do fornecedor

Pode ser que uma organização tenha que corrigir a conta contábil de Contas a receber ou de Contas a pagar para uma entrada contábil de uma fatura lançada, mas essa faturam possa ser estornada ou corrigida através de outro mecanismo.

Se uma correção tiver que ser feita na conta contábil do contas a receber ou do contas a pagar, um ajuste deverá ser feito diretamente à conta contábil. O ajuste realizado o não pode ser feito pelo lançamento através do fornecedor ou do cliente. Esta abordagem requer que o ajuste seja feito durante um "período de inatividade", de forma que a conta contábil possa permitir temporariamente entradas manuais.

### <a name="the-system-allows-it"></a>“O sistema permite isso”

Geralmente as organizações usam a funcionalidade Um comprovante único meramente porque o sistema permite que elas utilize, sem entender as implicações.


[!INCLUDE[footer-include](../../includes/footer-banner.md)]
