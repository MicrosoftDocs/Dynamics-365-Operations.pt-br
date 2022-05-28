---
title: Práticas recomendadas para perfis de lançamento
description: Este tópico descreve as práticas recomendadas para a configuração de perfis de lançamento.
author: rachel-profitt
ms.date: 12/03/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: LedgerSystemSetup, CustPosting, VendPosting, InventPosting, AssetPosting, ProjPosting, AssetLeasePostingAccounts, ProjCategory, ITMCostTypeTable, ProdGroup, WrkCtrTable, WrkCtrResourceGroup, MainAccount, SysDatabaseLogSetup, CustGroup, VendGroup, InventItemGroup
audience: Application User
ms.reviewer: twheeloc
ms.custom: ''
ms.assetid: c64eed1d-df17-448e-8bb6-d94d63b14607
ms.search.region: Global
ms.author: kweekley
ms.search.validFrom: 2022-01-03
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 211dc42b80089eb1f59a435f09d6e9d9f956736b
ms.sourcegitcommit: 5d1772bdeb21a9bec6dc49e64550aaf34127a4e2
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/10/2022
ms.locfileid: "8734265"
---
# <a name="recommended-practices-for-posting-profiles"></a>Práticas recomendadas para perfis de lançamento

Há várias práticas recomendadas que você deve seguir ao configurar perfis de lançamento em todo o sistema. Este tópico descreve diferentes cenários e as práticas recomendadas correspondentes.

## <a name="setting-the-do-not-allow-manual-entry-flag"></a>Configurar o sinalizador Não permitir entrada manual

Na página **Contas principais**, a caixa de seleção **Não permitir entrada manual** deve ser marcada para todas as contas principais usadas em um perfil de lançamento. Essa configuração impede que os usuários enviem manualmente uma entrada de diário para a conta principal. Portanto, ele ajuda a garantir que o livro auxiliar permaneça no saldo com o livro-razão geral e a facilitar o processo de reconciliação.

Se forem necessários ajustes para uma conta controlada pelo sistema e automaticamente lançada, você poderá usar uma destas abordagens:

- Crie uma conta principal secundária em que os ajustes possam ser lançados. Em seguida, use uma conta de total ou uma linha especial em seus relatórios financeiros para agrupar e somar as contas.
- Reverta as transações originais no livro auxiliar apropriado, faça as correções necessárias e, em seguida, lance a transação novamente por meio do mesmo livro auxiliar.

## <a name="changing-posting-profiles-after-transactions-exist"></a>Alterar perfis de lançamento após a existência de transações

Se você alterar um perfil de lançamento após a existência de transações, a reconciliação poderá falhar, e o livro auxiliar e o livro-razão poderão ficar sem saldo. Em geral, recomendamos que você **não** altere o perfil de lançamento após a existência de transações.

Se forem necessárias alterações, siga as diretrizes a seguir para ajudar a garantir a integridade do sistema:

- Faça as mudanças durante o fechamento do período.
- Faça as alterações quando nenhuma outra transação estiver ocorrendo no sistema.
- Valide o livro-razão e reconcilie-o para o livro auxiliar antes e depois de fazer as alterações.
- As transações lançadas não serão atualizadas se você alterar o perfil de lançamento. Considere cuidadosamente se é necessário fazer alguma entrada de ajuste para a alteração.
- Se você estiver alterando perfis de lançamentos de estoque, considere como as mudanças afetarão o estoque disponível e os saldos do livro-razão. Algumas alterações podem exigir que você deixe o estoque em 0 (zero), feche e recoloque-o após a conclusão das mudanças.
- Sempre teste as alterações em um ambiente de não produção antes de fazê-las na produção.

## <a name="using-database-logging-to-audit-changes-to-posting-profiles"></a>Usar o log de banco de dados para auditar mudanças em perfis de lançamento

Considere a configuração do log de banco de dados para cada perfil de lançamento e tabelas de parâmetros que controlam os lançamentos. Em seguida, se um parâmetro ou perfil for alterado, você terá um registro de auditoria completo do valor que foi alterado, quem o alterou, quando ele foi alterado e qual era o valor anterior. Essas informações podem ser críticas durante seu processo de reconciliação e seu auditor pode exigir a documentação de suporte.

Para obter mais informações, consulte [Configurar o log de banco de dados](../../fin-ops-core/dev-itpro/sysadmin/configure-manage-database-log.md).

Use a tabela a seguir como referência para nomes de tabela comuns relacionados a perfis de lançamento e parâmetros de lançamento relacionados.

| Nome da página | Painel de navegação | Nome da tabela |
|-----------|-----------------|------------|
| Parâmetros de contas a pagar | Contas a pagar &gt; Configuração &gt; Parâmetros de contas a pagar | VendParm |
| Perfil de lançamentos do fornecedor | Contas a pagar &gt; Configuração &gt; Perfil de lançamento de fornecedor | VendPosting |
| Código de encargos | Contas a pagar &gt; Configuração de encargos &gt; Código de encargos ou Contas a receber &gt; Configuração de encargos &gt; Código de encargos | MarkupTable |
| Formas de pagamento | Contas a pagar &gt; Configuração de pagamento &gt; Formas de pagamento | VendPaymMode |
| Descontos à vista | Contas a pagar &gt; Configuração de pagamento &gt; Descontos à vista ou Contas a receber &gt; Configuração de pagamento &gt; Descontos à vista | CashDisc |
| Taxa de pagamento (Fornecedor) | Contas a pagar &gt; Configuração de pagamento &gt; Taxa de pagamento | VendPaymFee |
| Parâmetros de contas a receber | Contas a receber &gt; Configuração &gt; Parâmetros de contas a receber | CustParm |
| Perfis de lançamentos de cliente | Contas a receber &gt; Configuração &gt; Perfil de lançamento do cliente | CustPosting |
| Formas de pagamento | Contas a receber &gt; Configuração de pagamentos &gt; Formas de pagamento | CustPaymMode |
| Taxa de pagamento (Cliente) | Contas a receber &gt; Configuração de pagamentos &gt; Formas de pagamento | CustPaymFee |
| Parâmetros de arrendamento de ativo | Arrendamento de ativos &gt; Configuração &gt; Parâmetros de arrendamento de ativos | AssetLeasePostingAccounts<br>AssetLeaseJournalParameters<br>AssetLeaseExecutoryCostPostingAccounts |
| Contas Bancárias | Gerenciamento de pagamentos à vista e bancos &gt; Contas bancárias &gt; Contas bancárias | BankAccountsTable |
| Tipos de transação bancária | Gerenciamento de pagamentos à vista e bancos &gt; Configuração &gt; Tipos de transações bancárias | BankTransType |
| Regras de eliminação | Consolidações &gt; Configuração &gt; Regra de eliminação | LedgerEliminationRule<br>LedgerEliminationRuleLines |
| Categorias de despesa | Gerenciamento de despesa &gt; Configuração &gt; Geral &gt; Categorias de despesa | ProjCategories |
| Parâmetros do ativo fixo | Ativos fixos &gt; Configuração &gt; Parâmetros de ativos fixos | AssetParameters |
| Perfis de lançamentos de ativo fixo | Ativos fixos &gt; Configuração &gt; Perfis de postagem de ativo fixo | AssetLedgerAccounts<br>AssetDisposalParameters |
| Contas de reavaliação de moeda | Livro-razão geral &gt; Moedas &gt; Contas de reavaliação de moeda | CurrencyLedgerGainLossAccount |
| Contas para transações automáticas | Livro-razão geral &gt; Configuração de lançamento &gt; Contas para transações automáticas | LedgerSystemAccounts |
| Contabilidade intercompanhia | Livro-razão geral &gt; Configuração de lançamento &gt; Contas intercompanhia | LedgerIntercompany |
| Definições de lançamento de transação | Livro-razão geral &gt; Configuração de lançamento &gt; Definições de lançamento de transação | JournalizingDefinitionTrans |
| Definições de lançamento | Livro-razão geral &gt; Configuração de lançamento &gt; Definições de lançamento | JournalizingDefintion |
| Lançamento (Estoque) | Gerenciamento de estoque &gt; Configuração &gt; Lançamento &gt; Lançamento | InventPosting |
| Códigos de tipo de custo | Custo de entrega &gt; Configuração de custos &gt; Códigos de tipo de custo | ITMCostTypeTable |
| Recursos | Controle de produção &gt; Configuração &gt; Recursos &gt; Recursos | WrkCtrTable |
| Grupos de recursos | Controle de produção &gt; Configuração &gt; Recursos &gt; Grupos de recursos | WrkCtrResourceGroup |
| Perfis de produção | Controle de produção &gt; Configuração &gt; Produção &gt; Grupo de produção | ProdGroup |
| Categorias de custo | Controle de produção &gt; Configuração &gt; Roteiros &gt; Categorias de custo | ProjCategory |
| Grupos de projetos | Gerenciamento e contabilidade do projeto &gt; Configuração &gt; Lançamento &gt; Grupos de projetos | ProjGroup |
| Configuração de lançamento no livro-razão (Projetos) | Gerenciamento e contabilidade do projeto &gt; Configuração &gt; Lançamento &gt; Configuração de lançamento no livro-razão | ProjPosting |
| Contrapartidas padrão para despesas | Gerenciamento e contabilidade do projeto &gt; Configuração &gt; Lançamento &gt; Contrapartidas padrão para despesas | ProjDefaultOffsetSetup |
| Perfis de lançamento de gerenciamento de reembolso | Gerenciamento de reembolsos &gt; Configuração de lançamento de gerenciamento de reembolso &gt; Perfis de lançamento de gerenciamento de reembolso | TAMRebatePosting |
| Grupo de lançamentos no livro-razão (Impostos) | Imposto &gt; Configuração &gt; Imposto sobre vendas &gt; Grupo de lançamento no livro-razão | TaxAccountGroup |

## <a name="changing-groups-after-transactions-exist"></a>Alterar grupos após a existência de transações

Tenha cuidado ao alterar grupos em dados mestres. Se você estiver usando grupos para definir os perfis de lançamento, qualquer alteração em um grupo de um registro mestre poderá ter um impacto negativo na capacidade de reconciliar o livro-razão com o livro auxiliar. Por exemplo, você pode configurar o perfil de lançamento de estoque da receita da ordem de venda para que uma conta de receita diferente seja usada para cada grupo de itens. Se você alterar o grupo de itens atribuído a um item após a existência de transações, a receita das novas transações serão lançadas na conta atualizada. No entanto, qualquer receita lançada antes da alteração permanecerá na conta original.

## <a name="testing-posting-profiles"></a>Perfis de lançamento de testes

Antes da ativação e depois de fazer alterações ou inclusões nos seus perfis de lançamento ou parâmetros relacionados, você deve testar cada cenário. No mínimo, você deve testar cada tipo de lançamento para validar que o lançamento funcionará corretamente. No entanto, a abordagem recomendada é testar cada transação e combinação de perfis de lançamento.

Por exemplo, você tem dois perfis de lançamento de cliente, cada um com três registros específicos de grupos de clientes. Nesse caso, você deve testar cada tipo de transação.

**Perfis de lançamento:**

- **GEN**: o perfil de lançamento geral que tem um grupo para funcionários, um para clientes e outro para intercompanhia. Cada grupo aponta para uma conta de comércio de contas a receber diferente.
- **PRÉ**: perfil de lançamento de pagamento antecipado que tem um registro para todos os pagamentos antecipados que apontam para as contas de cliente pré-pago.

### <a name="testing-scenarios"></a>Cenários de teste

- Fatura de texto livre para um cliente no grupo de **Funcionários** que usa o perfil de lançamento **GEN**
- Fatura de texto livre para um cliente no grupo de **Funcionários** que usa o perfil de lançamento **PRE**
- Fatura de ordem de venda para um cliente no grupo de **Funcionários** que usa o perfil de lançamento **GEN**
- Fatura de ordem de venda para um cliente no grupo de **Funcionários** que usa o perfil de lançamento **PRE**
- Diário de pagamentos do cliente no grupo de **Funcionários** que usa o perfil de lançamento **GEN**
- Diário de pagamentos do cliente no grupo de **Funcionários** que usa o perfil de lançamento **PRE**

Para o exemplo anterior, repita um cenário de teste para cada grupo de clientes e repita cada grupo de cenários de teste para cada tipo de transação adicional (por exemplo, faturas do projeto e gerenciamento de serviços).

## <a name="reconciling-the-ledger-to-the-subledger"></a>Reconciliar o livro-razão com o livro auxiliar

O livro-razão deve ser reconciliado com o livro auxiliar a cada período. Muitos módulos contêm relatórios prontos para uso que podem ser utilizados para ajudar a fazer essa reconciliação. No entanto, dependendo dos requisitos locais, talvez seja necessário desenvolver relatórios personalizados ou estender os relatórios existentes para atender aos seus requisitos de relatórios.

Recomendamos que você faça uma simulação do período de fechamento e reconcilie cada um dos seus livros auxiliares com o livro-razão antes da ativação. Também é recomendável que você faça uma simulação de transferência de todos os saldos em aberto e transações abertas antes da ativação inicial. Como parte desse processo, você deve executar uma reconciliação completa para garantir que a migração de saldos e transações abertas seja balanceada com os sistemas herdados e que todos os livros auxiliares sejam balanceados com o livro-razão antes da criação de novas transações.
