---
title: Divisão de clientes em agendas de cobrança
description: Este artigo descreve como dividir um cliente quando a cobrança de assinatura é usada.
author: JodiChristiansen
ms.date: 11/04/2022
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: twheeloc
ms.search.scope: Core, Operations
ms.custom: 539093
ms.search.region: Global
ms.author: jchrist
ms.search.validFrom: 2022-11-05
ms.dyn365.ops.version: 10.0.31
ms.openlocfilehash: cfbe61ca4b7e809a8183f4622bf6db4fc83a4d83
ms.sourcegitcommit: 9e2e54ff7d15aa51e58309da3eb52366328e199d
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/04/2022
ms.locfileid: "9746307"
---
# <a name="customer-split-on-billing-schedules"></a>Divisão de clientes em agendas de cobrança

Em uma programação de cobrança, a *conta de fatura* é o cliente que recebe a fatura do pedido de venda para que possa pagar a fatura. Em alguns cenários, mais de um cliente pode pagar uma fatura. A funcionalidade **Divisão do cliente** permite adicionar mais clientes que podem ser cobrados pela mesma agenda de cobrança. Para habilitar esta funcionalidade, vá para **Cobrança de assinatura \> Cobrança de contrato recorrente \> Configuração \> Parâmetros de cobrança de contrato recorrentes** e defina a opção **Divisão do cliente** como **Sim**.

## <a name="customer-split-on-the-billing-schedule-header"></a>Divisão do cliente no cabeçalho da agenda de cobrança

Depois que uma agenda de cobrança é criada, mais clientes podem ser adicionados ao cabeçalho da agenda de cobrança.

Para adicionar um cliente, siga estas etapas.

1. Na guia **Agenda de cobrança**, selecione **Divisão do cliente**. Os campos **Conta do cliente** e **Nome da conta do cliente** na parte superior especificam o cliente atribuído como **Cliente de agenda de cobrança**.

    > [!NOTE]
    > A conta do cliente que você adiciona não pode ser igual à conta da fatura.

2. Na guia **Linhas divididas do cliente**, selecione **Adicionar linha**.
3. Selecione um cliente e insira a porcentagem de cada fatura para esse cliente.
4. Por padrão, as datas de início e término da programação de cobrança são usadas como datas de início e término. Insira datas de início e término diferentes se o novo cliente pagar a porcentagem especificada apenas por uma parte da programação de cobrança. Por exemplo, se a agenda de cobrança tiver uma data de início em 1º de janeiro e uma data de término em 31 de dezembro, e o novo cliente for cobrado 40% pelos primeiros nove meses, especifique 1º de janeiro como a data de início e 30 de setembro como a data de término e insira **40,00** como porcentagem.

Não é possível adicionar mais de um cliente às linhas de divisão de clientes. Nesse caso, a porcentagem total inserida não deve exceder 100%. Insira uma referência do cliente e uma requisição do cliente como campos informativos que serão exibidos na linha do pedido de venda durante o processo **Gerar fatura**.

Os detalhes da linha mostrarão as informações de contato, endereço de entrega, endereço de cobrança e detalhes de pagamento dos clientes adicionados. Essas informações também serão mostradas no pedido de venda para os clientes.

Ao adicionar informações sobre a divisão do cliente ao cabeçalho da agenda de cobrança, se houver linhas não faturadas na agenda de cobrança, você receberá a seguinte mensagem solicitando que você desfaça as alterações: "Você deseja rolar a alteração do cabeçalho para as linhas? As alterações atualizarão apenas as linhas de agenda de cobrança que não são faturadas." Selecione **Sim** para atualizar as informações sobre a divisão do cliente na linha de agenda de cobrança. As alterações não serão atualizadas se a linha de agenda de cobrança já tiver sido faturada.

Se uma agenda de cobrança for criada usando a opção **Copiar agenda**, as informações padrão serão inseridas nas linhas de cabeçalho da divisão do cliente. Não pode ser igual à conta do cliente.

Quando o processo **Gerar fatura** for concluído, vários pedidos de venda serão criados. (Várias faturas de vendas também serão criadas se o lançamento automático for usado.) Esses pedidos de vendas e faturas de vendas podem ser visualizados na guia **Fatura** na FastTab **Detalhes da linha** da página **Exibir detalhe de cobrança**. **Múltiplo** é exibido na linha de detalhes da cobrança para indicar que vários pedidos de vendas e faturas de vendas foram criados.

## <a name="customer-split-on-billing-schedule-lines"></a>Divisão do cliente em linhas de agenda de cobrança

A divisão do cliente pode ser adicionada a linhas de agenda de cobrança individuais se você desejar dividir apenas linhas de agenda de cobrança específicas. Marque a caixa de seleção **Divisão do cliente** na linha e, em seguida, selecione **Divisão do cliente** no menu da linha de agenda de cobrança para atualizar ou inserir as informações da divisão do cliente.

As informações de auditoria são atualizadas se a agenda de cobrança já tiver sido faturada, mas a porcentagem foi alterada na linha de agenda de cobrança. Todas as linhas cobradas após essa alteração usarão a nova porcentagem.

> [!NOTE]
> - A opção de divisão do cliente não pode ser usada com produtos em estoque.
> - Se a caixa de seleção **Receita não faturada** estiver marcada, a caixa de seleção **Divisão do cliente** não poderá ser marcada.
> - Se você usar a opção **Somente divisão de receita**, a linha principal terá a opção **Divisão do cliente**, mas os itens de linha secundária não.
