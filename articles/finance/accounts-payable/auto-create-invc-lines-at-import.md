---
title: Gerar linhas de faturas ao importar faturas de fornecedor
description: Este tópico descreve a funcionalidade para gerar automaticamente linhas de fatura em faturas de fornecedor quando as faturas forem importadas.
author: sunfzam
ms.date: 09/10/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: roschlom
ms.custom: intro-internal
ms.assetid: ''
ms.search.region: Global
ms.author: shpandey
ms.search.validFrom: 2021-08-30
ms.dyn365.ops.version: 10.0.23
ms.openlocfilehash: 87dec3c142ae296975ab98432421be4548085c80
ms.sourcegitcommit: 9e8d7536de7e1f01a3a707589f5cd8ca478d657b
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/18/2021
ms.locfileid: "7647873"
---
# <a name="generate-invoice-lines-when-you-import-vendor-invoices"></a>Gerar linhas de faturas ao importar faturas de fornecedor

[!include [banner](../includes/banner.md)]
[!include [preview banner](../includes/preview-banner.md)]

Este tópico descreve a funcionalidade para gerar automaticamente linhas de fatura em faturas de fornecedor quando as faturas forem importadas.

Às vezes, as faturas de fornecedor contêm informações limitadas, como informações de destinatário e subtotais. No entanto, elas não contêm informações para itens de linha. Quando você importa faturas, o sistema pode gerar linhas de fatura automaticamente, com base nas informações da ordem de compra correspondente.

Para habilitar a criação automática de linhas de fatura, siga estas etapas.

1.  Acesse **Contas a pagar \> Configuração \> Parâmetros de contas a pagar**.
2.  Na guia **Automação de fatura de fornecedor**, em **Criação automática de linha para faturas importadas**, defina a opção **Criar linhas da fatura automaticamente** como **Sim**. 
4.  No campo **Escolher a quantidade padrão para criação automática de linhas de fatura**, selecione a quantidade que o sistema deve usar para gerar linhas de fatura automaticamente:

    - **Quantidade encomendada** – o sistema gerará linhas a partir das linhas de ordens de compra. Esse é o valor padrão.
    - **Quantidade de recebimento de produtos** – o sistema usará os números de ordens de compra para encontrar os recibos de produtos relevantes. Em seguida, ele usará as quantidades de recibos de produtos para gerar linhas de fatura.

## <a name="data-entity-changes"></a>Alterações da entidade de dados

Para dar suporte à funcionalidade descrita neste tópico, a entidade de dados **Cabeçalho da fatura de fornecedor** foi aprimorada. Três campos foram adicionados:

- **HeaderOnlyImport** – este campo deve ser definido como **Sim** para que o sistema gere linhas para os cabeçalhos de fatura.
- **PurchIdRange** – a lista de números de ordens de compra. Os números de nota fiscal podem ser um intervalo, como **INV0001..INV0009** (onde dois pontos separam o início e o fim do intervalo) ou valores discretos, como **INV0001, INV0003, INV0006**. Todas as ordens de compra devem pertencer à mesma conta de fornecedor no cabeçalho da fatura. Caso contrário, a seguinte mensagem de erro será exibida: "Falha ao gerar linhas de fatura. As ordens de compra têm contas de fornecedor diferentes."
- **PackingslipRange** – a lista de números de recibos de produtos. As linhas da fatura de fornecedor podem ser criadas de recibos de produtos. No entanto, os números de recibos de produtos normalmente não são incluídos nas faturas de fornecedor. Somente Insira os números de recibos de produtos nesse campo se você puder identificar claramente quais recibos de produtos são para as faturas específicas. As linhas da fatura podem ser geradas com base nos recibos de produtos. E, se esse campo for usado, a configuração do campo **Escolher a quantidade padrão para criação automática de linhas de fatura** na página **Parâmetros de contas a pagar** será ignorada. 

**Limitação**: se você inserir vários números de recibos de produtos, várias faturas de fornecedor pendentes serão criadas com o mesmo número de fatura. Você deve consolidá-las manualmente antes de processar a fatura. Em lançamentos futuros, planejamos habilitar o sistema para consolidar as faturas automaticamente, portanto, a limitação será removida.

Todos os recibos de produtos devem pertencer à mesma conta de fornecedor no cabeçalho da fatura.

## <a name="result"></a>Resultado

Se o sistema gerar linhas com êxito, a seguinte mensagem será registrada no histórico de automação de fatura de fornecedor: "Criar linhas da fatura automaticamente: Com êxito".

Se o sistema não gerar linhas, a seguinte mensagem de erro será registrada: "Criar linhas da fatura automaticamente: Com falha".
