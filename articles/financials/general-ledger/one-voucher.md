---
title: "Um comprovante único"
description: "Um comprovante único para diários financeiros (diário geral, diário de ativo fixo, diário de pagamentos do fornecedor etc) permite que você insira várias transações do razão auxiliar no contexto de apenas um comprovante."
author: kweekley
manager: AnnBe
ms.date: 04/02/2018
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: 
audience: Application User
ms.reviewer: twheeloc
ms.search.scope: Core, Operations
ms.custom: 14091
ms.assetid: c64eed1d-df17-448e-8bb6-d94d63b14607
ms.search.region: Global
ms.author: kweekley
ms.search.validFrom: 2018-03-16
ms.dyn365.ops.version: 8.0.2
ms.translationtype: HT
ms.sourcegitcommit: a8b5a5af5108744406a3d2fb84d7151baea2481b
ms.openlocfilehash: 9f996131830f9bd4efd534143b3fb761c5ccc756
ms.contentlocale: pt-br
ms.lasthandoff: 04/13/2018

---

# <a name="one-voucher"></a>Um comprovante único

[!include [banner](../includes/banner.md)]

> [!NOTE]
>  Esta funcionalidade ficará disponível no Dynamics 365 for Finance and Operations versão 8.0, que ficará disponível na versão da Primavera 18.   

<a name="what-is-one-voucher"></a>O que é "Um comprovante único"?
======================

A funcionalidade existente para diários financeiros (diário geral, diário de ativo fixo, diário de pagamentos do fornecedor etc) permite que você insira várias transações do diário-razão auxiliar no contexto de apenas um comprovante. Nos referimos a esta funcionalidade como “Um comprovante único.” É possível criar Um comprovante único usando um dos seguintes métodos:

-   Configurar o nome do diário (**Contabilidade** \> **Configuração do diário** \>**Nomes de diário**), de forma que o campo **Novo comprovante** seja definido como **Apenas um número de comprovante**. * Cada linha que você adiciona ao diário agora será incluída no mesmo comprovante. Como cada linha será adicionada ao mesmo comprovante, o comprovante poderá ser inserido como um comprovante multilinha, como uma conta/contrapartida na mesma linha, ou como uma combinação.

[![Linha única](./media/same-line.png)](./media/same-line.png)
 
> [!IMPORTANT] 
> *  Observe que a definição de 'Um comprovante' NÃO inclui nomes de diários que são configurados como apenas **Um número de comprovante** e o usuário, em seguida, insere um comprovante que somente inclui tipos de contas contábeis.  Neste documento, 'Um comprovante' significa que há um comprovante que contém mais de um fornecedor, cliente, banco, ativo fixo ou projeto. 

-   Entre em um comprovante combinado onde não haja contrapartida.

[![Comprovante combinado](./media/Multi-line.png)](./media/Multi-line.png)

-   Entre em um comprovante onde a conta e a contrapartida contêm um tipo de conta de diário-razão auxiliar, como fornecedor/fornecedor, Cliente/cliente, fornecedor/cliente, ou banco/banco.

[![Comprovante do diário-razão auxiliar](./media/subledger.png)](./media/subledger.png)

<a name="issues-with-one-voucher"></a>Problemas com Um comprovante único
=======================

A funcionalidade Um comprovante único causa problemas durante liquidação, cálculo de imposto, reconciliação de um diário-razão auxiliar para a contabilidade, relatório financeiro e muito mais. (Por exemplo, para obter mais informações sobre problemas que podem ocorrer durante a liquidação, consulte [Comprovante único com vários registros de cliente ou de fornecedor](https://docs.microsoft.com/en-us/dynamics365/unified-operations/financials/accounts-payable/single-voucher-multiple-customer-vendor-records)). Para trabalhar e relatar corretamente, os processos e relatórios exigem detalhes de transação. Embora alguns cenários ainda possam funcionar corretamente, com base na configuração da organização, geralmente há problemas quando várias transações são inseridas em um comprovante.

Por exemplo, você lança o seguinte comprovante combinado.

[![Exemplo ](./media/example.png)](./media/example.png)

Em seguida, você gera o relatório **Despesas por fornecedor** no espaço de trabalho **Insights financeiros**. O relatório agrupa saldos da conta de despesa no grupo de fornecedores e no fornecedor. Ao gerar o relatório, o sistema não pode determinar em quais grupos de fornecedores/fornecedor incorreu a despesa de 250.00. Como os detalhes da transação estão faltando, o sistema assume os 250.00 inteiros incorridos pelo primeiro fornecedor encontrado no comprovante. Os 250.00, que estão incluídos no saldo da conta principal 600120, são mostrados naquele grupo de fornecedores/fornecedor. É muito é provável que o primeiro fornecedor do comprovante não seja o fornecedor correto, então o relatório está incorreto.

[![Despesas](./media/expenses.png)](./media/expenses.png)

<a name="the-future-of-one-voucher"></a>O futuro de Um comprovante único
=========================

Devido às saídas que foram anteriormente indicadas, a funcionalidade Um comprovante único terá ficado obsoleta. Porém, como há lacunas funcionais que dependem desta funcionalidade, a funcionalidade não se tornará obsoleta de uma só vez. Em vez disso, usaremos a seguinte agenda: 

- **Versão da Primavera 2018** – A funcionalidade será desativada, por padrão, através de um parâmetro da Contabilidade. Porém, você pode ativar a funcionalidade, se sua organização tiver um cenário que esteja nas lacunas do cenário de negócios listadas posteriormente neste tópico.

  -   Se um cliente tiver um cenário de negócios que não requer Um comprovante único, não ative a funcionalidade. Não corrigiremos "bugs" nas áreas que foram identificadas antes neste tópico, se essa funcionalidade for usada, mesmo se houver outra solução.

  -   Pare de usar Um comprovante único para integrações no Microsoft Dynamics 365 Finance and Operations, a menos que a funcionalidade seja obrigatória para uma das lacunas funcionais.

- **Outono de 2018 e versões posteriores** – As lacunas funcionais serão preenchidas. Depois que as lacunas funcionais forem preenchidas, a funcionalidade Um comprovante único será desativada permanentemente.

- > [!IMPORTANT]
  > Observe que a opção **Apenas um número de comprovante** não foi removida da configuração do nome de diário.  Esta opção ainda é suportada quando o comprovante contém apenas tipos de conta contábil.  Os clientes devem ter cuidado ao usar esta configuração porque o comprovante não será lançado, se for usada a opção **Apenas um número de comprovante**, mas, em seguida, inserir mais de um cliente, fornecedor, banco, ativo fixo ou projeto.  Além disso, os clientes ainda podem inserir uma mistura de tipos de conta contábil, como um pagamento dentro de um único comprovante que contém tipos de contas de Fornecedor/Banco.  

<a name="why-use-one-voucher"></a>Por que usar Um comprovante único?
====================

Com base em conversas com clientes, compilamos a seguinte lista de cenários nos quais os clientes usam a funcionalidade Um comprovante único ou os motivos pelos quais eles a usam. Alguns desses requisitos comerciais podem ser atendidos somente usando Um comprovante único. Porém, para muitos cenários, as alternativas podem atender aos mesmos requisitos de negócios.

<a name="scenarios-that-require-one-voucher"></a>Cenários que exigem Um comprovante único
----------------------------------

Os cenários a seguir podem ser realizados apenas usando a funcionalidade Um comprovante único. Essas lacunas funcionais serão preenchidas por outros recursos nas versões do Outono de 2018 e posteriores.

-   **Lançar pagamentos do fornecedor ou do cliente em um formulário de resumo para uma conta bancária**

    -   Uma organização comunica uma lista de fornecedores e valores ao banco, e o banco utiliza esta lista para pagar os fornecedores em nome da organização. O banco lança a soma dos pagamentos como uma retirada única na conta bancária.

>   A recapitulação dos pagamentos do fornecedor é suportada somente através de Um comprovante único. Cada fornecedor é inserido como uma linha separada para manter detalhes no diário-razão auxiliar de contas a pagar, mas o valor somado de todos os pagamentos é compensado para uma única linha da conta bancária. Portanto, a saída é mostrada como um valor único resumido no diário-razão auxiliar do banco.

-   Uma organização deposita pagamentos do cliente, ou o banco deposita pagamentos do cliente em nome da organização e o depósito é mostrado como uma quantia total na conta bancária.

>   A recapitulação de pagamentos do cliente geralmente é suportada através da funcionalidade de depósito. Entretanto, se você estiver usando a “transição” no método de pagamento, este cenário é suportado somente através da funcionalidade Um comprovante único. Os pagamentos do cliente são inseridos da mesma maneira descrita para recapitulação de pagamentos do fornecedor.

-   **Mecanismo para agrupar transações de um evento de negócios**

    -   Uma organização tem um evento de negócios que aciona várias transações. Porém, o departamento de contabilidade deseja exibir as entradas contábeis juntas para melhor a auditabilidade.

>   Se uma organização tiver que exibir as entradas contábeis de um evento de negócios juntas, ela deverá usar a funcionalidade Um comprovante único. 

- **Recursos específicos de país/região**

  -   O recurso Documento administrativo único (SAD) para Polônia atualmente exige que apenas um comprovante seja usado. Até uma opção de agrupamento ficar disponível para este recurso, você deve continuar usando a funcionalidade Um comprovante único. Pode haver recursos específicos adicionais de país que exigem a funcionalidade Um comprovante único.

- **Diário de pagamento antecipado de cliente com impostos em várias "linhas"**

  -   Um cliente faz um pagamento antecipado de uma ordem, e as linhas da ordem têm diferentes impostos que devem ser registrados para o pagamento antecipado. O pagamento antecipado do cliente é uma transação que simula as linhas da ordem, de forma que o imposto apropriado possa ser registrado para o valor em cada linha.

Neste cenário, os clientes do comprovante único são os mesmos clientes porque a transação simula as linhas de uma ordem do cliente. O pagamento antecipado deve ser inserido em um único comprovante porque o cálculo do imposto deve ser feito nas "linhas" do pagamento único que o cliente fez.

-   **Manutenção de ativo fixo: atualizar depreciação, dividir ativo, calcular depreciação na alienação**

As seguintes transações de ativo fixo também criam várias transações dentro de apenas um comprovante:
-   Uma aquisição adicional é feita em um ativo e a depreciação de 'atualização' é calculada.
-   Um ativo é dividido.
-   Um parâmetro para calcular a depreciação na alienação é habilitado e, em seguida, o ativo é descartado.

<a name="scenarios-that-dont-require-one-voucher"></a>Cenários que não exigem Um comprovante único
----------------------------------------

Os cenários a seguir podem ser realizados através de outros meios e não devem usar Um comprovante único.

-   **Lançar pagamentos do cliente em um formulário de resumo para a conta bancária**

Uma organização deposita pagamentos do cliente, ou o banco deposita pagamentos do cliente em nome da organização e o depósito é mostrado como uma quantia total na conta bancária.

A recapitulação de pagamentos do cliente é suportada através da funcionalidade de depósito quando a transição não é usada no método de pagamento.

-   **Remuneração**

Na remuneração, os saldos para um fornecedor e cliente são remunerados entre eles porque o fornecedor e o cliente são a mesma parte. Esta abordagem minimiza a troca de dinheiro entre uma organização e a parte do cliente/fornecedor.

A remuneração pode ser realizada inserindo o aumento ou a redução em comprovantes separados e o lançamento da contrapartida em uma conta contábil de compensação.

-   **Lançar resumo na contabilidade**

As organizações geralmente querem lançar o resumo na contabilidade para minimizar o volume de dados. Entretanto, as organizações normalmente ainda exigem que o detalhe da transação seja mantido. Quando o lançamento é feito em resumo através de apenas um comprovante, o detalhe da transação não é conhecido e não pode ser mantido.

   -   Como o detalhe da transação atualmente pode ser mantido, recomendamos que Um Comprovante não seja usado para lançar no resumo.
   -   Depois que o suporte do Um comprovante único for removido, podemos implementar o Documento de origem e as estruturas contábeis nos diários. Essas estruturas manterão o detalhe da transação e suportarão a recapitulação na contabilidade.

-   **Liquidar vários pagamentos não lançados na mesma fatura**

Esse cenário geralmente é encontrado em organizações de varejo nas quais os clientes podem usar vários métodos de pagamento para pagar as compras. Neste cenário, a organização deve ser capaz de registrar vários pagamentos não lançados e liquidá-los com a fatura de cliente.

Um novo recurso adicionado no Microsoft Dynamics 365 for Operations versão 1611 (Novembro de 2016) permite que vários pagamentos não contabilizados sejam liquidados com uma única fatura. Vários pagamentos do cliente não precisam mais ser inseridos em um único comprovante.

-   **Importar transações de extrato bancário**

Os bancos geralmente pagam e recebem pagamentos em nome de uma organização, e essas transações são registradas no Finance and Operations através de um arquivo que é recebido do banco. Geralmente, as organizações querem agrupar essas transações usando o número do extrato bancário no arquivo. Como cada transação é mostrada em detalhes no extrato bancário, nenhuma recapitulação é necessária no diário-razão auxiliar do banco.

As transações podem ser agrupadas usando outros campos no diário, como o número de lote do próprio diário ou o número do documento.

-   **Transferir saldos**

Talvez uma organização tenha que transferir o saldo de um fornecedor para outro em decorrência de um erro ou porque outro fornecedor assumiu a responsabilidade. As transferências desse tipo também ocorrem para tipos de conta como, clientes e contas bancárias.

As transferências de saldo de uma conta (fornecedor, cliente, conta bancária etc) para outra conta podem ser feitas através de comprovantes separados e a contrapartida pode ser lançada em uma conta contábil de compensação.

-   **Inserir saldo inicial.**

Geralmente as organizações inserem os saldos iniciais das contas do diário-razão auxiliar (fornecedores, clientes, ativos fixos etc) em uma transação de comprovante. Os saldos iniciais de cada conta do diário-razão auxiliar podem ser inseridos como comprovantes separados e a contrapartida pode ser lançada em uma conta contábil de compensação.

-   **Corrigir a entrada contábil de um documento lançado do cliente ou do fornecedor**

Pode ser que uma organização tenha que corrigir a conta contábil de Contas a receber ou de Contas a pagar para uma entrada contábil de uma fatura lançada, mas essa faturam possa ser estornada ou corrigida através de outro mecanismo.

Se uma correção tiver que ser feita na conta contábil do contas a receber ou do contas a pagar, um ajuste deverá ser feito diretamente à conta contábil. O ajuste realizado o não pode ser feito pelo lançamento através do fornecedor ou do cliente. Esta abordagem requer que o ajuste seja feito durante um "período de inatividade", de forma que a conta contábil possa permitir temporariamente entradas manuais.

-   **“O sistema permite isso”**

Geralmente as organizações usam a funcionalidade Um comprovante único meramente porque o sistema permite que elas utilize, sem entender as implicações.

