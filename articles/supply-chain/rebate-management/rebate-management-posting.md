---
title: Configuração de lançamento de gerenciamento de reembolso
description: Este tópico descreve como configurar perfis de lançamento. Os perfis de lançamento são usados para determinar as entradas de lançamento para linhas de cálculo de gerenciamento de reembolso.
author: sherry-zheng
ms.date: 02/19/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: TAMRebateGroup
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: chuzheng
ms.search.validFrom: 2021-02-19
ms.dyn365.ops.version: 10.0.18
ms.openlocfilehash: edffccfec552d90ce704190b4be0b4594964fa81
ms.sourcegitcommit: 3b87f042a7e97f72b5aa73bef186c5426b937fec
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/29/2021
ms.locfileid: "7574320"
---
# <a name="rebate-management-posting-setup"></a>Configuração de lançamento de gerenciamento de reembolso

[!include [banner](../includes/banner.md)]

Os perfis de lançamento de gerenciamento de reembolso são usados para determinar as entradas de lançamento para linhas de cálculo de gerenciamento de reembolso. Quando um perfil de lançamentos é selecionado no cabeçalho de negócio, ele se aplica a todas as linhas de negócio.

Esse recurso funciona entre empresas (entidades legais). Você pode especificar a empresa para a qual as provisões serão acumuladas e as reivindicações serão pagas. Também é possível definir contas de débito de provisão diferentes e dar baixa em contas de crédito por empresa de lançamento de origem.

Para configurar perfis de lançamento de gerenciamento de reembolso para clientes e fornecedores, acesse **Gerenciamento de reembolso \> Configuração de lançamento de gerenciamento de reembolso \> Perfis de lançamento de gerenciamento de reembolso**. A página **Perfis de lançamento de gerenciamento de reembolso** inclui um painel de lista que mostra todos os perfis existentes. Você pode usar os botões no Painel de Ações para adicionar perfis à lista ou removê-los.

As seções restantes deste tópico descrevem como usar os campos disponíveis ao criar ou editar um perfil.

## <a name="posting-profile-header"></a>Cabeçalho de perfil de lançamento

A tabela a seguir descreve as configurações disponíveis na seção de cabeçalho de cada Perfil de lançamento de gerenciamento de reembolso.

| Campo | Descrição |
|---|---|
| Perfil de lançamento | Insira um nome exclusivo para o perfil. |
| descrição | Insira uma descrição do perfil. |
| Módulo | Selecione o módulo ao qual os reembolsos e royalties do perfil estão associados (*Cliente* ou *Fornecedor*). |
| Tipo | Selecione o tipo de perfil (*Reembolso* ou *Royalty*). |
| Tipo de Pagamento | <p>Este campo determina o formato da saída do reembolso lançado.<p><p>Quando o campo **Tipo** é definido como *Reembolso*, os seguintes valores estão disponíveis:</p><ul><li>*Pagar usando contas a pagar* – quando você lança o reembolso de um cliente, é criada uma fatura de fornecedor para o fornecedor de remessa que é configurado no cliente de reembolso. Quando você lança o reembolso de um fornecedor, é criada uma fatura de fornecedor para a conta de fornecedor de reembolso.</li><li>*Deduções do cliente* – quando você lança o reembolso, é criado um diário de dedução do cliente para o cliente do reembolso.</li><li>*Deduções do cliente da fatura de imposto* – quando você lança o reembolso, é criada uma fatura de texto livre para o cliente do reembolso.</li><li>*Gasto comercial* – quando você lança o reembolso, é criado um diário de dedução do cliente para o cliente do reembolso.</li><li>*Relatórios* – quando você lança o reembolso, é criado um diário de dedução do cliente para o cliente do reembolso.</li></ul><p>Quando o campo **Tipo** é definido como *Royalty*, os seguintes valores estão disponíveis:</p><ul><li>*Pagar usando contas a pagar* – quando você lança o reembolso, é criada uma fatura de fornecedor para a conta de fornecedor de reembolso.</li><li>*Relatórios* – quando você lança o reembolso, é criada uma fatura de fornecedor para a conta de fornecedor de reembolso.</li></ul><p>Para obter mais informações, consulte a seção [Tipos de pagamento](#payment-types) a seguir. |
| Empresa | Selecione a empresa (entidade legal) para a qual as provisões serão acumuladas e as reivindicações serão pagas. |

### <a name="payment-types"></a>Tipos de pagamento

A tabela a seguir resume como as várias configurações do campo **Tipo de pagamento** afetam o local em que os pagamentos são lançados. Os pagamentos podem ser lançados em uma conta de cliente, conta de fornecedor ou conta de remessa, dependendo da transação de destino e do tipo de reembolso.

| Tipo de pagamento | Tipo de transação de destino | Tipo de reembolso | Pagamento a (conta de fatura) |
|---|---|---|---|
| Pagar usando contas a pagar | Diário de faturas de fornecedores | Reembolso de cliente | Conta de fornecedor de remessa do cliente |
| Pagar usando contas a pagar | Diário de faturas de fornecedores | Royalty de cliente | Conta de Fornecedor |
| Pagar usando contas a pagar | Diário de faturas de fornecedores | Reembolso de fornecedor | Conta de Fornecedor |
| Deduções do cliente | Diário | Reembolso de cliente | Conta do cliente |
| Deduções de cliente da fatura de imposto | Fatura de texto livre | Reembolso de cliente | Conta do cliente |
| Gasto comercial | Diário | Reembolso de cliente | Conta do cliente |
| Relatório | Diário | Reembolso de cliente | Conta do cliente |
| Relatório | Diário de faturas de fornecedores | Royalty de cliente | Conta de Fornecedor |
| Relatório | Diário de faturas de fornecedores | Reembolso de fornecedor | Conta de Fornecedor |

> [!NOTE]
> Considere os seguintes pontos ao configurar [Acordos de gerenciamento de reembolso](rebate-management-deals.md):
>
> - Para acordos em que o campo **Reconciliar por** está definido como *Negócio*, você não pode usar a conta de negócio dinâmica durante o lançamento. Você deve usar uma conta de cliente ou fornecedor especificada.
> - Para negócios em que o campo **Reconciliar por** está definido como *Linha*, você pode usar um perfil de lançamento que é deslocado para uma conta de negócio dinâmica na linha de negócio, pois o cliente ou fornecedor é definido por linha de negócio.

## <a name="posting-fasttab"></a>FastTab Lançamento

A tabela a seguir descreve os campos disponíveis na FastTab **Lançamento** de cada Perfil de lançamento de gerenciamento de reembolso.

| Campo | descrição |
|---|---|
| Tipo de crédito | Selecione se deseja creditar uma conta contábil ou um cliente. Se o campo **Tipo de pagamento** no cabeçalho estiver definido como *Deduções de cliente da fatura de imposto*, este campo será definido como *Conta contábil*. Para reembolsos de fornecedores, este campo é definido como *Conta contábil*. |
| Conta de crédito | Selecione a conta em que os valores de crédito são lançados quando são feitas provisões de reembolso. Essa conta também será usada como contrapartida quando o reembolso for lançado para creditar o cliente ou debitar o fornecedor. |
| Nome do diário<br>(Na seção **Provisão**) | Selecione o nome do diário a ser usado para registrar a provisão lançada. |
| Tipo | Selecione se deseja lançar o reembolso em uma conta contábil, um cliente ou fornecedor. Se o campo **Tipo de pagamento** no cabeçalho estiver definido como *Deduções de cliente da fatura de imposto*, este campo será definido como *Cliente/Fornecedor*. |
| Use a origem da conta | <p>Selecione um dos seguintes valores:</p><ul><li>*Conta fixa* – Se você selecionar este valor, deverá especificar uma conta no campo **Conta de reembolso**.</li><li>*Conta de linha de negócio* – Use a conta de cliente ou fornecedor especificada na linha de reembolso. Você só pode selecionar esse valor para negócios em que o campo **Reconciliar por** está definido como *Linha* e para linhas de negócio em que o campo **Código de conta** está definido como *Tabela*. Isso não se aplica aos perfis de lançamento de royalties do cliente ou reembolsos de fornecedores que são baseados em ordens de venda.</li></ul> |
| Conta de reembolso | A conta em que a despesa real de reembolsos será lançada. |
| Nome do diário<br>(No grupo de campos **Gerenciamento de reembolsos**) | Selecione o nome do diário a ser usado para lançar uma nota de crédito do valor do reembolso para o cliente ou fornecedor. Este campo não está disponível quando o campo **Tipo de pagamento** no cabeçalho é definido como *Deduções de cliente da fatura de imposto*. Para descontos de clientes, nomes de diários do tipo de diário *Diário* estarão disponíveis. Para royalties de clientes e reembolsos de fornecedores, nomes de diários do tipo de diário *Gravação de fatura do fornecedor* estarão disponíveis. |
| Grupo de impostos do item | Especifique se o reembolso é tributável. |
| Nome do diário<br>(No grupo de campos **Dar baixa**) | Se o reembolso lançado não for igual à provisão, poderá haver baixa da diferença. Selecione o nome do diário a ser usado para registrar a baixa lançada. |

## <a name="posting-by-company-fasttab"></a>FastTab Lançamento por empresa

A FastTab **Lançamento por empresa** de cada Perfil de lançamento de gerenciamento de reembolso permite especificar a conta de lançamento usada por cada empresa (entidade legal) na grade.

Use os botões da barra de ferramentas para adicionar empresas à grade e removê-las. Toda vez que você adicionar uma linha à grade, use o campo **Empresa** para especificar a entidade legal para essa linha. O campo **Nome** é definido automaticamente.

Selecione a linha de cada empresa e insira as seguintes informações usando os campos abaixo da grade:

- **Tipo de débito** – Selecione se deseja debitar uma conta contábil ou um fornecedor. Para reembolsos de cliente e royalties, este campo é definido como *Conta contábil*.
- **Conta de débito** – Insira a conta na qual o valor do débito é lançado quando as provisões de reembolso são feitas.
- **Conta principal** – Selecione a conta principal para baixas.
