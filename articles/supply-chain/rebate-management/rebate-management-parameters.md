---
title: Parâmetros de gerenciamento de reembolso
description: Este tópico descreve a página Parâmetros de gerenciamento de reembolso. Esta página contém configurações que afetam o lançamento, as atualizações de status, as sequências numéricas e outros comportamentos.
author: sherry-zheng
ms.date: 02/19/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: TAMRebateParameters
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: chuzheng
ms.search.validFrom: 2021-02-19
ms.dyn365.ops.version: 10.0.18
ms.openlocfilehash: 8f5c9734b2480329eed246bcbbfe3bd6e9991e0b
ms.sourcegitcommit: a58dfb892e43921157014f0784bd411f5c40e454
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/04/2022
ms.locfileid: "8688981"
---
# <a name="rebate-management-parameters"></a>Parâmetros de gerenciamento de reembolso

[!include [banner](../includes/banner.md)]

A página **Parâmetros de gerenciamento de reembolso** é usada para definir configurações que se aplicam ao módulo **Gerenciamento de reembolso**. Essas configurações afetam o lançamento, as atualizações de status, as sequências numéricas e outros comportamentos. A configuração desta página é compartilhada entre entidades legais e pode ser modificada por usuários com as permissões de segurança apropriadas.

Para abrir a página **Parâmetros de gerenciamento de reembolso**, acesse **Gerenciamento de reembolsos \> Configuração \> Parâmetros de gerenciamento de reembolso**. Defina os campos conforme descrito nas subseções a seguir.

## <a name="rebate-management-tab"></a>Guia Gerenciamento do reembolso

A tabela a seguir descreve os campos disponíveis na guia **Gerenciamento de reembolso** da página **Parâmetros de gerenciamento de reembolso**.

| Campo | Descrição |
|---|---|
| Status padrão | Selecione o status padrão para todos os novos acordos. Para definir o conjunto de valores de status que está disponível para seleção, use a [página **Status de reembolsos**](rebate-statuses.md). |
| Processar por dimensão | Selecione se as transações de provisão, de reembolso e de baixa devem ser processadas por dimensão financeira. Quando esta opção está ativada, o sistema usa as dimensões financeiras das transações de origem nas transações de destino. |
| Verifique se já foi lançado | <p>Selecione o comportamento do sistema se as transações de reembolso não lançadas forem processadas mais de uma vez para o mesmo período:</p><ul><li>**Aviso** – o sistema permite que os usuários substituam as linhas de transações originais, mas um aviso é exibido.</li><li>**Erro** – o sistema impede que usuários substituam as linhas de transações originais e uma mensagem de erro é exibida. |
| Lançar diários automaticamente | Selecione se o sistema deve lançar automaticamente os diários propostos. Esses diários incluem diários que são usados para provisões e deduções do cliente, além de diários de fatura de imposto do fornecedor. |
| Lançar automaticamente faturas de texto livre | Selecione se o sistema deve lançar automaticamente faturas de texto livre. Esta opção se aplica somente a faturas de texto livre em que o tipo de pagamento é definido como *Deduções de cliente da fatura de imposto*. |
| Referência da ordem do item de reembolso | Selecione a referência de reembolso a ser usada em ordens de venda e de compra geradas a partir do processo de reembolso (*Nenhum*, *Negociação de gerenciamento de reembolso*, *Número do gerenciamento de reembolsos*, *Número de transações de reembolso* ou *Notas do documento*). |
| Use o processo de declaração | <p>Defina esta opção como *Sim* para usar o processo de declaração. Dessa forma, você pode marcar transações que o Gerenciamento de reembolso cria como reivindicado ou não reivindicado e, depois, lançar somente as transações reivindicadas.</p><p>Por exemplo, você calcula os reembolsos para o valor mensal de transações, mas o cliente deixou dois dias não reivindicados. Nesse caso, as transações não reivindicadas serão recriadas na próxima vez que você executar a função *Processar* para o próximo período.</p><p>Se você definir esta opção como *Não*, todas as transações da declaração serão lançadas.</p> |
| Incluir diário de tipo de ordem | Para acordos ou linhas de acordos em que o tipo de transação está definido como *Ordem*, esta opção controla se uma ordem de venda do tipo *Diário* deve ser incluída. Ela trará flexibilidade se esses tipos de ordens forem usados em cenários em que um reembolso ainda não deva ser aplicado. |

## <a name="number-sequences-tab"></a>Guia Sequências numéricas

Use a guia **Sequências numéricas** na página **Parâmetros de gerenciamento de reembolso** para atribuir códigos de sequência numérica às diferentes sequências numéricas usadas pelo Gerenciamento de reembolso. A tabela a seguir descreve a finalidade de cada uma dessas sequências numéricas. Para obter mais informações sobre sequências numéricas, consulte [Visão geral de sequências numéricas](../../fin-ops-core/fin-ops/organization-administration/number-sequence-overview.md) e os tópicos relacionados.

| Demonstrativo | descrição |
|---|---|
| Negociação de gerenciamento de reembolsos | A sequência numérica atribui um valor de chave exclusivo a cada acordo de reembolso. Essa chave é usada quando acordos são criados. |
| Número de gerenciamento de reembolsos | A sequência numérica atribui um valor de chave exclusivo a cada reembolso. Essa chave é usada para identificar relações de reembolso. |
| Número da transação de reembolso | A sequência numérica atribui um valor de chave exclusivo a cada transação de reembolso. Essa chave é usada para identificar transações de reembolso. |
| Fatura de imposto | A sequência numérica atribui um valor de chave exclusivo a cada fatura de reembolso. Essa chave é usada quando os diários de reembolso são lançados automaticamente. |

## <a name="feature-visibility-tab"></a>Guia Visibilidade de recursos

O gerenciamento de reembolso adiciona recursos (campos e funções) a várias páginas usadas com frequência no Microsoft Dynamics 365 Supply Chain Management. Essas páginas incluem páginas relacionadas a ordens de venda e acordos de vendas. Se você estiver usando o Gerenciamento de reembolso, torne esses recursos visíveis em qualquer lugar antes de aproveitá-los. Se você não estiver usando o Gerenciamento de reembolso, poderá ocultar os recursos para mantê-los fora do caminho.

Na guia **Visibilidade de recursos** da página **Parâmetros de gerenciamento de reembolso**, defina a opção **Ativar** como *Sim* para tornar recursos de gerenciamento de reembolso visíveis sempre que estiverem disponíveis. Defina-a como *Não* para ocultar os recursos em páginas comuns fora do módulo **Gerenciamento de reembolso**. No entanto, mesmo quando a opção estiver definida como *Não*, o próprio módulo, incluindo a página **Parâmetros de gerenciamento de reembolso**, permanecerá disponível para usuários com as permissões apropriadas para acessá-lo.
