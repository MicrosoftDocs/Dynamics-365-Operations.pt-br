---
title: Criação de ordens baseadas em um fluxo constante para transações de loja de varejo
description: Este tópico descreve a criação de ordens baseadas em um fluxo constante para transações de loja no Microsoft Dynamics 365 Commerce.
author: analpert
ms.date: 01/11/2021
ms.topic: index-page
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: josaw
ms.custom: ''
ms.assetid: ''
ms.search.region: global
ms.search.industry: Retail
ms.author: josaw
ms.search.validFrom: 2019-09-30
ms.dyn365.ops.version: ''
ms.openlocfilehash: 67b66cd4bf2a77f3ab7f33f691156e38cc13770a
ms.sourcegitcommit: 27475081f3d2d96cf655b6afdc97be9fb719c04d
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/12/2022
ms.locfileid: "7964619"
---
# <a name="trickle-feed-based-order-creation-for-retail-store-transactions"></a>Criação de ordens baseadas em um fluxo constante para transações de loja de varejo

[!include [banner](includes/banner.md)]

No Microsoft Dynamics 365 Commerce versão 10.0.5 e posterior, é recomendável fazer a transição de todos os processos de lançamento de demonstrativo para os processos de lançamento de demonstrativo baseados em fluxo constante. Os benefícios comerciais e o desempenho significativo estão associados ao uso da funcionalidade do fluxo constante. As transações de venda são processadas durante todo o dia. As transações de gerenciamento de caixa e meio de pagamento são processadas no demonstrativo financeiro no final do dia. A funcionalidade de fluxo constante permite o processamento contínuo de ordens de venda, faturas e pagamentos. Portanto, o estoque, a receita e os pagamentos são atualizados e reconhecidos em tempo quase real.

## <a name="use-trickle-feed-based-posting"></a>Usar o lançamento baseado em um fluxo constante

> [!IMPORTANT]
> Antes de habilitar o lançamento baseado em fluxo constante, você deve garantir que não existam demonstrativos calculados e não lançados. Lance todos os demonstrativos antes de habilitar o recurso. Você pode verificar se há demonstrativos abertos no espaço de trabalho **Finanças da loja**.

Para habilitar o lançamento de transações de varejo baseado em fluxo constante, habilite o recurso **Demonstrativos de varejo – Fluxo constante** no espaço de trabalho **Gerenciamento de recursos**. O demonstrativo será dividido em dois tipos: demonstrativos transacionais e demonstrativos financeiros.

### <a name="transactional-statements"></a>Demonstrativos transacionais

O processamento do demonstrativo transacional deve ser executado em uma frequência alta ao longo do dia, de modo que os documentos sejam criados quando as transações forem carregadas na matriz do Commerce. As transações são carregadas das lojas na matriz do Commerce quando você executa o **Trabalho P**. Você também deve executar o trabalho **Validar transações de loja** para validar transações de modo que o demonstrativo transacional as escolha.

Agende os seguintes trabalhos para serem executados em uma frequência alta:

- Para calcular um demonstrativo transacional, execute o trabalho **Calcular demonstrativos transacionais em lote** (**Retail e Commerce \> TI de Retail e Commerce \> Lançamento do PDV \> Calcular demonstrativos transacionais em lote**). Esse trabalho selecionará todas as transações não lançadas e validadas e as adicionará a um novo demonstrativo transacional.
- Para lançar demonstrativos transacionais em um lote, execute o trabalho **Lançar demonstrativos transacionais em lote** (**Retail e Commerce \> TI de Retail e Commerce \> Lançamento do PDV \> Lançar demonstrativos transacionais em lote**). Esse trabalho executará o processo de lançamento e criará ordens de venda, faturas de venda, diários de pagamento, diários de desconto e transações de receita/despesa para demonstrativos não lançados que não contêm erros. 

### <a name="financial-statements"></a>Demonstrativos financeiros

O processamento do demonstrativo financeiro destina-se a ser um processo de fechamento do dia. Esse tipo de processamento de demonstrativo oferece suporte somente ao método de fechamento de **Turno** e selecionará somente turnos fechados. Os demonstrativos são limitados à reconciliação financeira. Eles criarão somente os diários para os valores de diferença entre o valor contado e o valor da transação de meios de pagamento, e diários para outras transações de gerenciamento de caixa.

Os demonstrativos financeiros também permitem a revisão das seguintes transações: transações de declaração de meios de pagamento, transações de pagamento, transações de meio de pagamento bancário e transações de meio de pagamento do cofre. A página de detalhes do meio de pagamento só fica visível quando um demonstrativo financeiro é selecionado.

![Imagem mostrando a seção de detalhes do meio de pagamento do formulário de demonstrativos lançados somente quando um demonstrativo financeiro é selecionado.](./media/Trickle-feed-posted-statements-transaction-view.png)

Agendar as horas de início e término dos seguintes trabalhos de demonstrativo financeiro com base no final esperado do dia:

- Para calcular um demonstrativo financeiro, execute o trabalho **Calcular demonstrativos financeiros em lote** (**Retail e Commerce \> TI de Retail e Commerce \> Lançamento do PDV \> Calcular demonstrativos financeiros em lote**). Este trabalho coletará todas as transações financeiras não lançadas e as adicionará a um novo demonstrativo financeiro.
- Para lançar demonstrativos financeiros em um lote, execute o trabalho **Lançar demonstrativos financeiros em lote** (**Retail e Commerce \> TI de Retail e Commerce \> Lançamento do PDV \> Lançar demonstrativos financeiros em lote**).

### <a name="manually-create-statements"></a>Criar demonstrativos manualmente

Os tipos de demonstrativo transacional e financeiro também podem ser criados manualmente. 

1. Acesse **Retail e Commerce \> Canais \> Lojas** e selecione **Demonstrativos**. 
2. Selecione **Novo** e, em seguida, selecione o tipo de demonstrativo a ser criado. Os campos na página **Demonstrativos** mostrarão os dados relevantes ao tipo de demonstrativo selecionado, bem como as ações em **Grupo de demonstrativos** mostrarão ações relevantes.

[!INCLUDE[footer-include](../includes/footer-banner.md)]
