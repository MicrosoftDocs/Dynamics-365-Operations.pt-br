---
title: Reconhecimento de receita em ordens de venda
description: Este artigo descreve a funcionalidade básica para reconhecer receitas em ordens de venda e faturas. O reconhecimento de receita está disponível na ordem de venda e na fatura correspondente criada com a ordem de venda.
author: kweekley
ms.date: 08/24/2018
ms.topic: index-page
ms.prod: ''
ms.technology: ''
ms.search.form: Customer
audience: Application User
ms.reviewer: kfend
ms.search.region: Global
ms.author: kweekley
ms.search.validFrom: 2018-08-30
ms.dyn365.ops.version: 8.0.4
ms.openlocfilehash: 5df7341160940f5c5db0dd4c5d86e4d9698d22e2
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/03/2022
ms.locfileid: "8899947"
---
# <a name="revenue-recognition-on-sales-orders"></a>Reconhecimento de receita em ordens de venda

[!include [banner](../includes/banner.md)]

> [!NOTE]
> O recurso Reconhecimento de receita não pode ser ativado por meio do Gerenciamento de recursos. No momento, você deve usar as chaves de configuração para ativá-lo.

Este artigo descreve a funcionalidade básica para reconhecer receitas em ordens de venda e faturas. O reconhecimento de receita está disponível em uma ordem de venda e na fatura correspondente criada com a ordem de venda. A ordem de venda também pode ser criada com um projeto de Tempo e materiais.

> [!NOTE]
> Nas ilustrações deste artigo, colunas foram ocultadas ou adicionadas às grades para melhorar a apresentação de conceitos. Portanto, as páginas e os dados nas ilustrações podem ser diferentes daqueles que você vê no produto.

## <a name="enter-a-sales-order"></a>Inserir uma ordem de venda

A ordem de venda a seguir é inserida e inclui três itens configurados para o reconhecimento de receita.

[![Inserir uma ordem de venda.](./media/revenue-recognition-so-basic-sales-order-header.png)](./media/revenue-recognition-so-basic-sales-order-header.png)

Há dois conceitos para o reconhecimento de receita:

- **Determinar o preço da receita.** O preço da receita é calculado com base na instalação de produtos lançados. O preço de receita nunca é exibido para o cliente, mas usado para a contabilidade de fatura da ordem de venda. As linhas de ordem de venda e os documentos impressos como parte das vendas continuam a mostrar a unidade/preço da tabela.
- **Determinar quando o reconhecimento de receita deve ocorrer.** Uma agenda de receita é usada para determinar quando a receita deve ser reconhecida.

    Neste exemplo, o primeiro item, S0001, é atribuído a um a agenda de receita **1O** (uma ocorrência). Essa linha representará um cenário semelhante a um marco, no qual a receita é reconhecida após a instalação. Portanto, a receita será adiada até que a instalação seja concluída.

    O segundo item, S0008, é um item de serviço configurado como um item de suporte pós-contrato (PCS). Os serviços sustentados da engenharia são proporcionados ao cliente durante um período de 12 meses. Portanto, uma agenda de receita **12M** é atribuída ao produto por padrão. Como esse item é do PCS, a data de início e término do contrato devem ser definidas. Por padrão, as datas de início e término do contrato são encontradas em Detalhes do item — guia Configuração. Na agenda de receita, as definições são configuradas para **12M** de modo que os termos do contrato sejam automaticamente preenchidos conforme mostrado na ilustração.

    [![Agendas de receita.](./media/revenue-recognition-so-basic-revenue-schedules.png)](./media/revenue-recognition-so-basic-revenue-schedules.png)

    O terceiro item, S0012, é hardware, e nenhuma agenda de receita é atribuída por padrão. A receita para o hardware é reconhecida logo após o item ter sido faturado.

## <a name="confirm-the-sales-order"></a>Confirmar a ordem de venda

Para exibir detalhes sobre o preço da receita e a agenda de receita, use os botões no grupo **Reconhecimento de receita** na guia **Gerenciar** no Painel de Ações da ordem de venda. Como a ordem de venda não foi confirmada nesse momento, os botões usados para o reconhecimento de receita não estão disponíveis. Esses botões ficam disponíveis ou indisponíveis conforme a ordem de venda avança os estágios que levam ao atendimento.

[![Cabeçalho de ordem de venda.](./media/revenue-recognition-so-basic-sales-order-header-02.png)](./media/revenue-recognition-so-basic-sales-order-header-02.png)

Os três primeiros botões fornecem detalhes sobre o preço de receita para os itens na configuração da ordem de venda para o reconhecimento de receita.

- **Alocação de preço da receita** — Esse botão ficará disponível depois que a ordem de venda for confirmada ou a fatura for lançada. Confirmação de ordem de venda e lançamento de fatura calculam a receita para reconhecer o preço que será reconhecido ou adiado na entrada contábil. Dependendo da configuração, o preço da receita calculado pode diferir do preço unitário que é mostrado ao cliente.
- **Realocar preço com novas linhas da ordem** — Esse botão ficará disponível depois que a ordem de venda for confirmada ou a fatura for lançada. O processo de realocação é usado para recalcular a receita que deve ser reconhecida depois que uma nova linha for adicionada à ordem de venda atual, após ser faturada, ou a uma nova ordem de venda. Nos dois casos, a adição de um novo item causa alteração no contrato. Portanto, o preço da receita deve ser realocado.
- **Atualizar preço da receita de alocação** — Esse botão ficará disponível depois que a ordem de venda for confirmada, mas ficará indisponível depois que a ordem de venda for faturada. A atualização é usada para executar novamente a alocação de preço de receita sem ter que confirmar a ordem de venda. Depois que a ordem de venda é faturada, o preço de receita não pode ser recalculado.

Os dois últimos botões fornecem detalhes sobre a agenda da receita para esses itens na ordem de venda que contêm uma agenda de receita.

- **Agenda de reconhecimento da receita estimada** — Esse botão ficará disponível depois que a ordem de venda for confirmada, mas ficará indisponível depois que a ordem de venda for faturada. Abre uma página que mostra a agenda da receita estimada. A agenda final pode ser alterada, pois a agenda estimada usa a data de remessa solicitada, sendo que a agenda final usa a data de remessa real.
- **Agenda de reconhecimento de receita** — Esse botão ficará disponível depois que a ordem de venda for faturada. A agenda de reconhecimento de receita final não será criada após a confirmação ou quando a guia de remessa for criada. Criado somente quando a ordem de venda tiver sido faturada.

Neste exemplo, a alocação de preço da receita ocorreu quando a ordem de venda foi confirmada. Observe, mesmo que os preços de receita sejam alocados de outra forma, o valor total no campo **Reconhecer a receita** ainda deverá ser igual à soma das linhas da ordem de venda faturadas para o cliente. Por exemplo, soma das linhas da ordem de venda, excluindo impostos, é US$ 1.499. Portanto, a soma dos valores **Reconhecer a receita** também deve ser US$ 1.499.

[![Alocação de preço da receita.](./media/revenue-recognition-so-basic-revenue-price-allocation.png)](./media/revenue-recognition-so-basic-revenue-price-allocation.png)

A agenda de reconhecimento de receita estimada também é criada. A agenda de receita usa o valor **Reconhecer a receita** como a quantidade a ser adiada. O item S0001 adia US$ 321,21 em vez de US$ 300, e o item S0008 adia US$ 160,61 em vez de US$ 100. O item S0012 não é exibido na agenda estimada, pois a receita não é adiada. Após o lançamento, o item S0012 lança US$ 1.017,18 diretamente na conta contábil da receita.

[![Agenda de reconhecimento de receita estimada.](./media/revenue-recognition-so-basic-expected-rev-rec-schedule.png)](./media/revenue-recognition-so-basic-expected-rev-rec-schedule.png)

## <a name="create-the-packing-slip"></a>Criar guia de remessa

Em seguida, a guia de remessa poderá ser criada para a ordem de venda. Nenhuma receita é reconhecida quando a guia de remessa é lançada. Se a ordem de venda não foi confirmada, lançar a guia de remessa não dispara o cálculo de preço da receita. Também não dispara a criação da agenda de reconhecimento de receita estimada ou final. Se o grupo de modelo de item estiver configurado para adiar a receita na guia de remessa, continuará a lançamento usando as contas contábeis do perfil atual de lançamento, não as novas contas de receita adiada usadas no lançamento da fatura.

## <a name="create-the-invoice"></a>Criar fatura

A etapa final é faturar a ordem de venda. Se olhar o comprovante a fatura, você observará que a receita dos itens S0001 e S0008 foi adiada (US$ 321,21 + 160,61 = 481,82), e o valor restante para o item S0012 foi lançado na receita (1.017,18). Esses valores somam até US$ 1.499, correspondendo à soma das linhas de ordem de venda.

[![Comprovantes de transações.](./media/revenue-recognition-so-voucher-transactions.png)](./media/revenue-recognition-so-voucher-transactions.png)

Depois que a fatura é criada, os botões **Alocação de preço da receita**, **Realocar o preço com novas linhas de ordem** e **Agenda de reconhecimento de receita** para o reconhecimento de receita são disponibilizados, mas os botões **Atualizar preço da receita de alocação** e **Agenda de reconhecimento de receita estimada** não estão disponíveis.

[![Disponibilidade do botão de reconhecimento de receita disponível.](./media/revenue-recognition-so-basic-after-invoice-buttons.png)](./media/revenue-recognition-so-basic-after-invoice-buttons.png)

O botão **Alocação de preço da receita** ainda está disponível, permitindo exibir o cálculo de preço da receita. Se nada for alterado na ordem de venda após ter sido confirmada, lançar a fatura não mudará o valor calculado no campo **Reconhecer a receita**.

A agenda de reconhecimento de receita estimada será removida e substituída pela agenda de reconhecimento de receita final. Os detalhes da agenda de receita serão mantidos para cada linha de ordem de venda e são usados para liberar a receita adiada para a receita atual conforme as obrigações contratuais são atendidas.

[![Agenda de reconhecimento de receita final.](./media/revenue-recognition-so-revenue-recognition-schedule.png)](./media/revenue-recognition-so-revenue-recognition-schedule.png)


[!INCLUDE[footer-include](../../includes/footer-banner.md)]
