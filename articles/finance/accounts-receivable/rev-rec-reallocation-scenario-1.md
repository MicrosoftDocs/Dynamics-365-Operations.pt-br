---
title: Realocação de reconhecimento de receita — cenário 1
description: Este tópico passa por um cenário de realocação em que duas ordens de venda são inseridas, mas só são confirmadas. O mesmo cenário produzirá resultados semelhantes, se houver mais de duas ordens de venda em um estado confirmado.
author: kweekley
manager: aolson
ms.date: 12/21/2020
ms.topic: index-page
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: Customer
audience: Application User
ms.reviewer: roschlom
ms.search.region: Global
ms.author: kweekley
ms.search.validFrom: 2020-12-21
ms.dyn365.ops.version: 10.0.14
ms.openlocfilehash: 25fb32ce72555e573cd37a0ab092b51b99bb4372
ms.sourcegitcommit: eaf330dbee1db96c20d5ac479f007747bea079eb
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/15/2021
ms.locfileid: "5260868"
---
# <a name="revenue-recognition-reallocation--scenario-1"></a>Realocação de reconhecimento de receita — cenário 1

[!include [banner](../includes/banner.md)]

Este tópico passa por um cenário de realocação em que duas ordens de venda são inseridas, mas só são confirmadas. O mesmo cenário produzirá resultados semelhantes, se houver mais de duas ordens de venda em um estado confirmado.

Para este cenário, a opção **Lançar correções de fatura em Contas a receber** é definida como **Não** na guia **Reconhecimento de receita** da página **Parâmetros da contabilidade** (**Reconhecimento de receita \> Configurar \> Parâmetros da contabilidade**).

[![Lançar correções de fatura na opção de Contas a receber definida como Não](./media/06_rev-rec-scenarios.png)](./media/06_rev-rec-scenarios.png)

Uma ordem de venda é criada para o cliente US\_SI\_0003. O cliente está comprando um laptop (número de item S0012) e um plano de suporte (número de item S0008, "Serviço de Engenharia Sustentado"). A receita do laptop é reconhecida imediatamente (não há nenhuma agenda de reconhecimento de receita). A receita do plano de suporte será adiada e reconhecida durante 12 meses, conforme definido pelo intervalo de datas no contrato.

[![Linhas de ordem de venda para o laptop e o plano de suporte](./media/07_rev-rec-scenarios.png)](./media/07_rev-rec-scenarios.png)

A ordem de venda está confirmada. Como os dois itens estão configurados para alocação de preço de receita, o preço da receita é calculado quando a ordem de venda é confirmada. É possível exibir a receita que será reconhecida na página **Alocação de preço da receita** (na página **Ordem de venda**, no Painel de Ações, na guia **Gerenciar**, no grupo **Reconhecimento de receita**, selecione **Alocação de preço da receita**). A receita do laptop será lançada na Conta de receita no valor de $1.008,01. A receita do plano de suporte será lançada na Conta de receita adiada no valor de US$ 190,99. A soma dos preços da receita deve ser igual à soma das linhas configuradas para capturar a alocação de preço da receita (US$ 1.199,00).

[![Página Alocação de preço da receita](./media/08_rev-rec-scenarios.png)](./media/08_rev-rec-scenarios.png)

O cliente optou por não comprar serviços de instalação (número de item S0001) no momento da venda, mas depois mudou de ideia. Portanto, uma segunda ordem de venda é inserida para o mesmo cliente.

[![Linha da ordem de venda para serviços de instalação](./media/09_rev-rec-scenarios.png)](./media/09_rev-rec-scenarios.png)

A segunda ordem de venda está confirmada. Como essa ordem de venda contém apenas uma linha, a alocação de preço da receita não é executada ao confirmar a ordem de venda. A alocação de preço da receita ocorre somente se houver um ou mais itens exclusivos, e se esses itens forem configurados para a alocação de preço da receita.

Se essa nova ordem de venda for a única alteração no contrato do cliente, o processo de realocação poderá ser executado agora. Em uma das duas ordens de venda, selecione **Realocar preço com novas linhas da ordem** para abrir a página **Realocar preço com novas linhas da ordem**. Como alternativa, acesse **Reconhecimento de receita \> Tarefas periódicas \> Realocar preço com novas linhas da ordem**. Selecione as duas ordens de venda e as linhas correspondentes dela e depois selecione **Atualizar realocação**. A coluna **Valor realocado** mostra o novo preço da receita de cada linha da ordem de venda.

[![Novos preços de receita na página Realocar o preço com novas linhas da ordem](./media/10_rev-rec-scenarios.png)](./media/10_rev-rec-scenarios.png)

Se você selecionar **Comprovante esperado**, nada será exibido porque nenhuma fatura foi lançada.

Para concluir a realocação, selecione **Processar**. Você será solicitado a fornecer uma data de lançamento, mesmo que nada seja lançado. Depois que a realocação for concluída, a página **Alocação de preço da receita** de cada ordem de venda exibirá a alocação de preços de todos os itens nas duas ordens de venda. Em outras palavras, a página **Alocação de preço da receita** de cada ordem de venda incluirá um item que não existe nessa ordem de venda, pois faz parte do mesmo contrato, mas em uma ordem de venda diferente.

> [!TIP]
> Para fornecer um contexto sobre o motivo pelo qual esses itens adicionais são mostrados, você pode adicionar outras colunas à grade, como **ID de realocação** e **Ordem de venda**.
> 
> [![Colunas adicionais na página Alocações de preço de receita](./media/11_rev-rec-scenarios.png)](./media/11_rev-rec-scenarios.png)


[!INCLUDE[footer-include](../../includes/footer-banner.md)]