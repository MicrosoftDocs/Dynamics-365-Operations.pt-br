---
title: Vendas e marketing
description: "Você pode usar Vendas e marketing para obter, armazenar e usar vários tipos de dados no fluxo de vendas. Esses dados incluem a iniciativa de venda original, a ação de acompanhamento futuro e as vendas adicionais."
author: kfend
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: kfend
ms.search.scope: Core, AX 7.0.0, Operations, UnifiedOperations
ms.custom: 92303
ms.assetid: 65ca9992-bbfa-4224-bf0e-067a25c7e6a4
ms.search.region: Global
ms.author: kfend
ms.search.validFrom: 2016-02-28T00:00:00.000Z
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: Human Translation
ms.sourcegitcommit: 869151f2486b7a481e4694cfb6992d0ee2cfc008
ms.openlocfilehash: dddcc764bb11540b8207350c463d1adb2533e1c0
ms.contentlocale: pt-br
ms.lasthandoff: 06/13/2017

---

# <a name="sales-and-marketing"></a>Vendas e marketing

[!include[banner](../includes/banner.md)]


Você pode usar Vendas e marketing para obter, armazenar e usar vários tipos de dados no fluxo de vendas. Esses dados incluem a iniciativa de venda original, a ação de acompanhamento futuro e as vendas adicionais.

<a name="marketing"></a>Marketing
---------

Você usa campanhas e atividades de marketing para encontrar e criar relacionamentos com clientes potenciais, para que as interações iniciais possam desenvolver relacionamentos de vendas. O fluxo de processo a seguir ilustra o processo comercial do marketing. [![Processo comercial para Marketing](./media/marketing01.jpg)](./media/marketing01.jpg)

### <a name="relationships"></a>Relacionamentos

Em vendas e marketing, as interações iniciais com clientes potenciais podem ocorrer em diversas situações. Por exemplo, você pode encontrar um cliente em potencial enquanto você estiver participando de uma feira de negócios ou você pode ter um cliente potencial possível com um cliente após sua organização realizar uma campanha de emails em massa. É muito importante que você compreenda o fluxo da entidade da parte antes que se torne um cliente. O gráfico a seguir mostra o fluxo de relações de entidades como um cliente potencial torna-se um cliente real. [![SalesandMarketing01](./media/salesandmarketing01.jpg)](./media/salesandmarketing01.jpg)

### <a name="campaigns"></a>Campanhas

Uma campanha tem como alvo os contatos de clientes potenciais, clientes potenciais, oportunidades e clientes que foram selecionados para participar da campanha. No Microsoft Dynamics 365 for Finance and Operations, você pode criar vários tipos de campanhas, como telemarketing, endereçamento e campanhas de e-mail, para maximizar seu cliente potencial. Como sua campanha progride e você recebe respostas positivas, você pode começar o processo de vendas com os destinatários que responderam positivamente a campanha.

## <a name="sales"></a>Venda
Você pode usar a funcionalidade de venda para criar cotações de venda e vendas cruzadas para clientes novos e existentes, criar ordens de venda e criar notas fiscais de venda para clientes. O fluxo de processo a seguir ilustra o processo comercial de vendas. [![Processo empresarial para vendas](./media/sales01.jpg)](./media/sales01.jpg)

### <a name="sales-quotations"></a>Cotações de venda

Criar cotações de venda para apresentar aos clientes uma oferta de mercadorias ou serviços que você estará fornecendo. Um cliente pode solicitar uma cotação, ou você pode criar uma cotação em resposta a uma solicitação de um cliente potencial ou existente. Quando o cliente aprovar a cotação de venda, você poderá convertê-lo para uma ordem de venda.

### <a name="up-sellcross-sell"></a>Venda adicional/venda cruzada

Vendas diretas e vendas cruzadas são técnicas para vender produtos quando uma ordem é inserida para um cliente. Na venda, outro produto é sugerido em vez do produto atual. Na venda cruzada, outro produto é sugerido além do produto atual. Quando você configurar listas de produtos, você pode criar regras específicas para indicar quando um produto deve ser sugerido como um produto de vendas cruzadas ou agregadas.

### <a name="sales-orders"></a>Ordens de venda

Ao criar uma nova ordem de venda, é necessário selecionar o tipo de ordem de venda que deseja criar. Você tem cinco opções. **Observação:** depois de criar uma ordem de venda, qualquer tipo de ordem pode ser alterada, exceto o tipo **requisitos de itens** se a ordem de venda com um status de **entregue**.

| Tipo de ordem de venda  | Descrição                                                                                                                                                                                                                                                                                            |
|-------------------|--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Diário           | Use este tipo como um rascunho para uma ordem de venda. Este tipo não tem nenhum efeito sobre as quantidades em estoque e não gera transações de itens.                                                                                                                                                                    |
| Subscrição      | Use este tipo para as ordens recorrentes. Quando a ordem é faturada, o status da ordem é automaticamente definido para a ordem em aberto. A quantidade faturada entregue e as entregas remanescente são atualizadas. Você não pode usar esse tipo de ordem de venda se estiver usando a funcionalidade de gerenciamento de depósito. |
| Ordem de venda       | Use esse tipo quando um cliente tiver colocado ou confirmado uma ordem.                                                                                                                                                                                                                                        |
| Ordem devolvida    | Use este tipo quando o cliente devolver um item. Um número de item de devolução (número de ADM) é atribuído automaticamente.                                                                                                                                                                                            |
| Requisições de itens | Este tipo é criado automaticamente quando você faz uma venda de item por um módulo de Projeto.                                                                                                                                                                                                                       |

### <a name="sales-agreements"></a>Contratos de venda

Um contrato de venda é um contrato que confirma que o cliente pode comprar um produto em uma determinada quantidade ou valor por um período em troca de preços especiais e descontos. Os preços e os descontos do contrato de venda substituem os preços e os descontos que declarados em qualquer contrato comercial que possa existir. Um contrato de venda é válido para um período definido. Data de remessa especificada para uma venda na página **ordem de venda** deve estar no período válido. Por padrão, um contrato de venda fica em espera. Você pode encomendar de um contrato de venda somente quando ele estiver definido como **Eficaz**.

### <a name="backorders"></a>Ordens pendentes

Quando você insere e valida ordens, pode ser necessário gerenciar ordens pendentes e exceções para que a venda possa ser concluída. Ordens pendentes são ordens que ainda não foram entregues por um fornecedor (ordens de compra) ou para um um cliente (ordens de venda). É importante acompanhar as ordens pendentes. Por exemplo, se os fornecedores atrasam a entrega das mercadorias, você terá que alterar a data da entrega aos clientes e informá-los sobre o atraso. Você pode exibir ordens pendentes por item, cliente ou fornecedor.

#### <a name="viewing-backorders-by-item"></a>Exibir ordens pendentes por item

Exibindo ordens pendentes por item, você pode acompanhar o fluxo futuro esperado de transações relacionadas a um item específico. Por exemplo, você pode alterar as informações no campo.

-   O número de ordens de venda feitas para um item
-   Se as entregas do item pelos fornecedores ainda não foram feitas
-   Se devem ser pedidos mais itens, para que você possa entregar todas as ordens de venda no tempo correto.

Ao fazer essa seleção, você pode responder às solicitações dos clientes sobre o tempo de entrega do item. Além disso, você pode priorizar as ordens de venda pendentes e dividir os itens disponíveis entre as ordens.

#### <a name="viewing-backorders-by-customer"></a>Exibir ordens pendentes por cliente

A visão geral de ordens pendentes por cliente permite exibir o status das ordens restantes do cliente. Essa verificação é útil quando é necessário responder aos clientes que estão aguardando itens que foram adiados.

#### <a name="viewing-backorders-by-vendor"></a>Exibir ordens pendentes por fornecedor

A o exibir ordens pendentes por fornecedor, você pode acompanhar entregas desaparecidas e datas de entrega esperadas. Esta verificação também ajuda a priorizar as ordens pendentes quando as mercadorias chegam dos fornecedores e as ordens de venda precisam ser selecionadas para entrega.

### <a name="invoices"></a>Faturas

Você pode criar três tipos de notas fiscais durante o processo de vendas:

-   Fatura de cliente
-   Fatura de texto livre
-   Fatura pro forma

#### <a name="customer-invoice"></a>Fatura de cliente

Uma nota fiscal de cliente é um documento que uma organização dá a um cliente relacionado a uma venda. Você cria esse tipo de fatura de cliente com base em uma ordem de venda que inclui um cabeçalho e uma ou mais linhas para itens ou serviços. A fatura de cliente encerra a ordem de venda, a guia de remessa e o ciclo da fatura de venda.  

Você pode lançar e imprimir uma fatura de cliente único, com base em uma ordem de venda ou da guia de remessa e data. Você também pode lançar e imprimir várias faturas de cliente com base em guias de remessa e datas. Quando você lança uma única fatura de cliente usando a ordem de vendas, a quantidade **A faturar** de cada item é atualizada com o total das quantidades faturadas da ordem de venda selecionada.  

Se a quantidade **A faturar** e a quantidade **A entregar** de todos os itens na ordem de venda for 0 (zero), o status da ordem de venda é alterado para **Faturado**. Se a quantidade for diferente de zero, o status da ordem de venda permanecerá inalterado e notas fiscais adicionais poderão ser inseridas para ela. Se você planeja lançar e imprimir uma ou mais faturas de cliente com base em guias de remessa, você deve já ter lançado pelo menos uma guia de remessa para cada ordem de venda. A fatura de cliente baseia-se nessas guias de remessa e reflete as quantidades nelas indicadas.  

Você pode criar uma fatura de cliente com base nos itens de linha da guia de remessa que foram remetidos até a data, mesmo que todos os itens de determinada ordem de venda ainda não tenham sido remetidos. Você poderá fazer isso, por exemplo, se a sua entidade legal emitir uma fatura por cliente por mês cobrindo todas as entregas remetidas durante esse mês. Cada guia de remessa representa uma entrega parcial ou completa dos itens da ordem de venda.  

Quando você lança a fatura, a quantidade **A faturar** de cada item é atualizada com o total das quantidades entregues das guias de remessa selecionadas. Se a quantidade **A faturar** e a quantidade **A entregar** de todos os itens na ordem de venda for 0 (zero), o status da ordem de venda é alterado para **Faturado**. Se a quantidade for diferente de zero, o status da ordem de venda permanecerá inalterado e notas fiscais adicionais poderão ser inseridas para ela. As transações de estoque são atualizadas com o número da nota fiscal, e o status no campo da linha de ordem de venda é alterado para **Faturado**.

#### <a name="free-text-invoice"></a>Fatura de texto livre

Uma fatura de texto livre é uma fatura que não está associada a uma ordem de venda. Ela contém linhas de ordem que incluem contas contábeis, descrições de texto livre e um valor de venda. Você não pode inserir um número de item neste tipo de nota fiscal e forneça as informações apropriadas de impostos sobre vendas. Uma conta principal para a venda é indicada em cada linha da fatura. O saldo do cliente é lançado na conta resumo do perfil de lançamento usado para a fatura de texto livre.

#### <a name="pro-forma-invoice"></a>Fatura pro forma

Uma nota fiscal pro forma é uma nota fiscal preparada como uma previsão dos valores da nota fiscal real antes de a nota fiscal ser lançada. Você pode imprimir uma nota fiscal pro forma de uma nota fiscal de cliente ou de uma nota fiscal de texto livre.




