---
title: Detalhes da transação de estoque
description: Este artigo fornece uma visão geral da página de detalhes de transações que mostra detalhes de uma transação de estoque selecionada.
author: rachel-profitt
ms.date: 04/25/2022
ms.topic: article
ms.search.form: InventTrans, InventTransDetails
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: raprofit
ms.search.validFrom: 2022-04-25
ms.dyn365.ops.version: 10.0.27
ms.openlocfilehash: 55e29d5804f57cd86fb5ddac5d6c5576b7ea5f61
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/03/2022
ms.locfileid: "8859377"
---
# <a name="inventory-transaction-details"></a>Detalhes da transação de estoque

Use a página **Detalhes da transação** para exibir os detalhes de qualquer transação de estoque selecionada.

## <a name="open-the-transaction-details-page"></a>Abrir a página Detalhes da transação

Para abrir a página **Detalhes da transação**, siga as etapas a seguir.

1. Acesse **Gerenciamento de estoque \> Consultas e relatórios \> Transações**.
1. Selecione a transação que você deseja inspecionar.
1. No Painel de Ação, selecione **Detalhes da transação**.

## <a name="fasttabs-overview"></a>Visão geral das guias rápidas

A página **Detalhes da transação** é dividida em várias guias rápidas. A tabela a seguir descreve a finalidade de cada guia rápida.

| FastTab | Descrição |
|---|---|
| Geral | Esta guia rápida mostra informações básicas sobre a transação de estoque selecionada. Além dos campos que aparecem na página **Transações de estoque**, ela inclui os campos adicionais descritos posteriormente neste artigo. |
| Atualizações | Esta guia rápida mostra informações relacionadas aos aspectos físicos, financeiros e de liquidação da transação de estoque selecionada. Dependendo do status atual da transação, alguns campos podem ficar em branco. Entretanto, esses campos serão definidos automaticamente quando as transações forem lançadas. Além dos campos que aparecem na página **Transações de estoque**, esta guia rápida inclui os campos adicionais descritos posteriormente neste artigo. |
| Lançamentos do razão | Esta guia rápida mostra o tipo de lançamento e a conta contábil usados para a atualização física, atualização financeira, receita física, encargos físicos, receita financeira e encargos financeiros relacionados à transação de estoque selecionada. |
| Referências | Esta guia rápida mostra informações adicionais sobre a transação de origem que criou a transação de estoque selecionada. Por exemplo, essas informações podem incluir detalhes da ordem de compra ou ordem de venda. |
| Informações Relacionadas | Esta guia rápida mostra informações adicionais sobre a transação de estoque selecionada. Esses campos podem não ser definidos se você não estiver usando alguns recursos, como categorias de compras ou projetos. |
| Dimensões financeiras – física | Esta guia rápida mostra os valores de dimensão financeira que foram usados quando a atualização física foi lançada. Caso a atualização física não tenha sido lançada, os campos ficarão em branco. |
| Dimensões financeiras – financeira | Esta guia rápida mostra os valores de dimensão financeira que foram usados quando a atualização financeira foi lançada. Caso a atualização financeira não tenha sido lançada, os campos ficarão em branco. |
| Dimensões de estoque | Esta guia rápida mostra os valores de dimensão de estoque atribuídos à transação de estoque selecionada. Esses valores incluem o site, depósito, tamanho, cor, configuração, local, número de lote, número de série, status de estoque, placa de licença e proprietário. |

## <a name="fields-on-the-general-fasttab"></a>Campos na guia rápida Geral

A tabela a seguir descreve os campos na guia rápida **Geral** que também não aparecem na página **Transações de estoque**.

| Campo | Descrição |
|---|---|
| Participante | O nome da parte relevante para a transação de estoque selecionada. Por exemplo, uma transação de ordem de compra mostra o nome do fornecedor na ordem de compra e uma transação de ordem de venda mostra o nome do cliente. Este campo não está disponível para todos os tipos de transações de estoque. |
| Referência de estoque | Se outra transação de estoque estiver relacionada à transação de estoque selecionada, o tipo dessa outra transação. Por exemplo, se uma ordem de compra for marcada em uma ordem de venda, o campo **Referência de estoque** da transação da ordem de compra será definido como *Ordem de venda*. A marcação ocorre automaticamente para ordens de entrega direta e ordens entre empresas. Ao usar a marcação com métodos de custo diferentes de *custo padrão* e *média móvel*, o sistema criará liquidações e ajustes para as transações exatas marcadas. Dessa forma, você pode obter o custeio "real" que substitui a lógica do primeiro a entrar, primeiro a sair (FIFO); último a entrar, primeiro a sair (LIFO); ou média ponderada. |
| Nº de estoque | A transação específica relacionada à transação de estoque selecionada. Por exemplo, se uma ordem de compra for marcada em uma ordem de venda, o campo **Nº de estoque** da transação da ordem de compra será definido como o número da ordem de venda. |
| ID do projeto | Se a transação de estoque selecionada estiver relacionada a um projeto, este campo será definido para o número do projeto. |
| ID do lote | A ID de lote exclusiva que o sistema atribuiu à transação de estoque selecionada. |
| Lote de referência | Se outra transação de estoque estiver relacionada à transação de estoque selecionada, a ID de lote dessa outra transação. Por exemplo, se uma ordem de compra for marcada em uma ordem de venda, o campo **Lote de referência** da transação da ordem de compra será o valor **ID do lote** da transação de estoque da linha da ordem de venda. |
| Número da dimensão | Uma ID exclusiva que representa a combinação de todos os valores de dimensão de estoque atribuídos à transação de estoque selecionada. |
| Valor aberto | Um valor que indica se a transação de estoque selecionada foi liquidada pelo processo de fechamento de estoque. Se este campo estiver definido como *Sim*, a transação não foi liquidada. |
| Data esperada | Para transações de recebimento, a data em que se espera que ocorra o recebimento do estoque. Por exemplo, este campo pode mostrar a data de recebimento esperada em uma ordem de bloqueio de estoque ou a data de entrega em uma linha de ordem de compra. |
| Data de estoque | Este campo é definido quando uma transação de registro foi feita na ordem de recebimento antes do lançamento de um recebimento físico. |
| Transferência não financeira | Um valor que indica se a transação de estoque selecionada é uma transferência não financeira. Uma transferência não financeira ocorre quando uma alteração nas dimensões do estoque não é acompanhada financeiramente na página **Grupo de modelo do item**. |
| ID do lote de transferência | Se a transação de estoque selecionada for uma transferência não financeira, este campo será definido para o valor **ID do lote** da outra transação de estoque em que a transação selecionada foi liquidada. |

## <a name="fields-on-the-updates-fasttab"></a>Campos na guia rápida Atualizações

A tabela a seguir descreve os campos na guia rápida **Atualizações** que também não aparecem na página **Transações de estoque**.

| Campo | Descrição |
|---|---|
| Comprovante físico | O número do comprovante na contabilidade onde foi gerado o lançamento físico para a transação de estoque selecionada. |
| Roteiro | A rota relacionada à transação de estoque selecionada. Este campo é definido apenas para transações de lista de separação de produção em que a lista de materiais (BOM) ou linha de fórmula está relacionada a um item específico. |
| Guia de remessa | O número da guia de remessa que foi inserido para uma transação de recebimento de produto da ordem de compra. |
| Valor de custo físico | O valor que foi lançado na contabilidade para a atualização física. Para um produto de custo padrão, esse valor representa o custo padrão. Para outros métodos de custo, representa a média ponderada do produto no momento do lançamento. |
| Receita física | O valor da receita diferida que foi lançada na contabilidade para a atualização física. |
| ID da Carga | Se a transação atual estiver relacionada a uma carga no gerenciamento de transporte, este campo mostra o número exclusivo da carga que incluiu o item. |
| Lançado fisicamente | Um valor que indica se a transação de estoque selecionada foi lançada fisicamente. Se a transação atual for lançada na contabilidade, também haverá um comprovante físico. |
| Lançado financeiramente | Um valor que indica se a transação de estoque selecionada foi lançada financeiramente. Se a transação atual for lançada na contabilidade, também haverá um comprovante financeiro. |
| Encargo físico lançado | Um valor que indica se os encargos físicos relacionados à transação de estoque selecionada foram lançados. |
| Encargo financeiro lançado | Um valor que indica se os encargos financeiros relacionados à transação de estoque selecionada foram lançados. |
| Comprovante financeiro | O número do comprovante na contabilidade em que o lançamento financeiro foi gerado. |
| Fatura | O número da fatura que foi gerada; por exemplo, para uma ordem de compra ou ordem de venda. |
| Ajuste | O valor que foi ajustado na transação de estoque selecionada do processo de fechamento e ajuste de estoque. |
| Lucros e perdas, valor lançado | O valor da transação de estoque selecionada que foi lançada na demonstração de lucros e perdas. |
| Fatura não lançada | O número da fatura de uma ordem de compra relacionada que aparece na página **Fatura de fornecedor pendente**. |
| Fechado financeiramente | A data em que a transação foi totalmente liquidada. |
| Quantidade em PV coberta | A quantidade de peso variável coberta pela liquidação. |
| Quantidade liquidada | A quantidade liquidada para a transação de estoque selecionada. |
| Valor liquidado | O valor que foi liquidado para a transação de estoque selecionada. |
