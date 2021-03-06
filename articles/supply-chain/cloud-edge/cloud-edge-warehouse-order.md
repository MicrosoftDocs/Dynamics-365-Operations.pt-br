---
title: Ordens de depósito para unidades de escala de nuvem e borda
description: Este tópico fornece informações sobre o recurso de ordem de depósito usado como parte da carga de trabalho da unidade de escala de depósito.
author: perlynne
ms.date: 04/22/2021
ms.topic: article
ms.search.form: WHSWarehouseOrderLine, WHSWarehouseReceiptEntry, PurchTable
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: perlynne
ms.search.validFrom: 2021-04-13
ms.dyn365.ops.version: 10.0.19
ms.openlocfilehash: 080d45170c726cd0351ab344254aa36c1c56ba55
ms.sourcegitcommit: dc4898aa32f381620c517bf89c7856e693563ace
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/17/2021
ms.locfileid: "6271247"
---
# <a name="warehouse-orders-for-cloud-and-edge-scale-units"></a>Ordens de depósito para unidades de escala de nuvem e borda

[!include [banner](../includes/banner.md)]

> [!WARNING]
> Nem todas as funcionalidades comerciais têm suporte total na versão preliminar pública quando são usadas cargas de trabalho de unidade de escala. Se você estiver usando unidades de escala, certifique-se de usar somente esses processos descritos explicitamente por este tópico como aceitos.

## <a name="what-are-warehouse-orders"></a>O que são ordens de depósito?

As *ordens de depósito* são um tipo de ordem que foi criado para oferecer suporte a implantações de depósito e unidade de escala. Eles permitem que você receba estoque quando estiver executando uma carga de trabalho de depósito em uma unidade de escala. No momento, eles são usados com ordens de compra.

As ordens de depósito são usadas como parte do processamento de gerenciamento de depósito, por exemplo, quando o aplicativo móvel de Gerenciamento de Depósito é usado para registrar o estoque físico disponível durante o processamento de uma ordem de compra de entrada. As ordens de depósito são criadas como parte do processo de *Liberação para depósito* que está disponível para ordens de compra que especificam um depósito de unidades de escala e itens habilitados para usar os processos de gerenciamento de depósito.

> [!IMPORTANT]
> As ordens de depósito estão disponíveis somente em implantações que usam [cargas de trabalho de gerenciamento de depósito para unidades de escala de nuvem e de borda](cloud-edge-workload-warehousing.md).

## <a name="create-a-warehouse-order"></a>Criar uma ordem de depósito

Para criar uma ordem de depósito, siga estas etapas.

1. Entre na instância do Microsoft Dynamics 365 Supply Chain Management que está em execução no hub. (É necessário iniciar o processo *Liberar para o depósito* enquanto você estiver conectado no hub.)
1. Acesse **Compras \> Ordens de compra \> Todas ordens de compra**.
1. No Painel de Ação, na guia **Depósito**, no grupo **Ações**, selecione **Liberar para o depósito**.
1. Para exibir as linhas de ordem de depósito relacionadas, abra a ordem de compra relevante, selecione uma linha na seção **Linhas da ordem de compra** e, na barra de ferramentas, selecione **Depósito \> Linhas da ordem de depósito**. Para exibir todas as linhas, vá para **Gerenciamento de depósito \> Consultas e relatórios \> Linhas da ordem de depósito**.

Você também pode desencadear o processo *Liberar para o depósito* de um trabalho em lotes acessando **Gerenciamento de depósito > Liberar para o depósito > Liberação automática de ordens de compra**. Ao configurar o trabalho em lotes, você pode selecionar linhas específicas da ordem de compra com base em uma consulta. Um cenário típico seria configurar um trabalho em lotes recorrente que libera todas as linhas da ordem de compra confirmadas que devem chegar no dia seguinte.

## <a name="cancel-a-warehouse-order"></a>Cancelar uma ordem de depósito

Como parte do processo *Liberar para o depósito*, as transações de estoque da ordem de compra são vinculadas a ordens de depósito e bloqueadas para serem atualizadas pelo hub. Se você liberou para o depósito por engano ou se tiver algum outro motivo para reverter a criação de linhas da ordem de depósito, poderá solicitar o cancelamento de linhas da ordem de depósito.

Para cancelar linhas de uma ordem de depósito, siga estas etapas.

1. Entre na instância do Supply Chain Management que está em execução no hub.
1. Vá para **Gerenciamento de depósito \> Consultas e relatórios \> Linhas da ordem de depósito**.
1. Selecione a linha relevante.
1. No painel de ações, selecione **Cancelar linhas da ordem de depósito**.

> [!NOTE]
> A solicitação para cancelar linhas será negada para todas as linhas que já estiverem com cancelamento pendente ou que estiverem sendo processadas ativamente em um depósito que está executando sua carga de trabalho em uma unidade de escala.

## <a name="monitor-a-warehouse-order"></a>Monitorar uma ordem de depósito

Na exibição **Linhas da ordem de depósito**, você pode monitorar o andamento da remessa de entrada, revisando os valores na coluna **Quantidade restante para receber**. Para exibir detalhes relacionados ao trabalho feito usando o aplicativo móvel de Gerenciamento de Depósito, siga uma destas etapas.

- Vá para **Gerenciamento de depósito \> Consultas e relatórios \> Linhas da ordem de depósito** e use o filtro para localizar as linhas que você está procurando.
- Vá para **Compras e fornecimento \> Ordens de compra \> Todas as ordens de compra** e abra a ordem de compra relevante. Na seção **Linhas da ordem de compra**, selecione uma ou mais linhas e, em seguida, na barra de ferramentas, selecione **Depósito \> Entradas de recebimento de depósito**.

[!INCLUDE [cloud-edge-privacy-notice](../../includes/cloud-edge-privacy-notice.md)]


[!INCLUDE[footer-include](../../includes/footer-banner.md)]
