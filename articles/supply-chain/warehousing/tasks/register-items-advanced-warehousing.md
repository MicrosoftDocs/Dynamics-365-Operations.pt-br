---
title: Registrar itens para um item habilitado de depósito avançado usando um diário de entrada de item
description: Este tópico apresenta um cenário que mostra como registrar itens usando o diário de entrada de itens quando você estiver usando processos de gerenciamento de depósito avançado.
author: ShylaThompson
ms.date: 03/24/2021
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: WMSJournalTable, WMSJournalCreate, WHSLicensePlate
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.search.industry: Distribution
ms.author: kamaybac
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: c58aa1cec6c0bfe33fa1ef90267dcd8ac1218157
ms.sourcegitcommit: 0e8db169c3f90bd750826af76709ef5d621fd377
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/01/2021
ms.locfileid: "5830825"
---
# <a name="register-items-for-an-advanced-warehousing-enabled-item-using-an-item-arrival-journal"></a>Registrar itens para um item habilitado de depósito avançado usando um diário de entrada de item

[!include [banner](../../includes/banner.md)]

Este tópico apresenta um cenário que mostra como registrar itens usando o diário de entrada de itens quando você estiver usando processos de gerenciamento de depósito avançado. Normalmente isso é feito por um vendedor de remessa.

## <a name="enable-sample-data"></a>Habilitar dados de exemplo

Para trabalhar neste cenário usando os exemplos de registros e valores especificados neste tópico, você deve usar um sistema em que os dados de demonstração padrão são instalados e deve selecionar a entidade legal *USMF* antes de começar.

Você pode trabalhar por meio desse cenário substituindo valores de seus próprios dados desde que tenha os seguintes dados disponíveis:

- Você deve ter uma ordem de compra confirmada com uma linha de ordem de compra aberta.
- O item na linha deve ser estocado. Ele não deve usar grades de produto e não deve ter dimensões de rastreamento.
- O item deve estar associado a um grupo de dimensões de armazenamento com um processo de gerenciamento de depósito habilitado.
- O depósito usado deve ser habilitado para processos de gerenciamento de depósito, e a localização usada para recebimento deve ser controlada por placa de licença.

## <a name="create-an-item-arrival-journal-header-that-uses-warehouse-management"></a>Criar um cabeçalho do diário de entrada de item que use o gerenciamento de depósito

O seguinte cenário mostra como criar um cabeçalho do diário de entrada de item que usa o gerenciamento de depósito:

1. Verifique se o sistema contém uma ordem de compra confirmada que atende aos requisitos descritos na seção anterior. Este cenário usa uma ordem de compra para a empresa *USMF*, conta de fornecedor *1001*, depósito *51*, com uma linha de ordem para *10 PL* (10 paletes) do número de item *M9200*.
1. Anote o número da ordem de compra que você usará.
1. Acesse **Gerenciamento de estoque \> Entradas de diário \> Entrada de item \> Entrada de item**.
1. Selecione **Novo** no Painel de Ações.
1. A caixa de diálogo **Criar diário de gerenciamento de depósito** é aberta. Selecione um nome de diário no campo **Nome**.
    - Se estiver usando dados de exemplo *USMF*, selecione *WHS*.
    - Se você estiver usando seus próprios dados, o diário escolhido deverá ter **Verificar local de separação** definido como *Não* e **Gerenciamento de quarentena** definido como *Não*.
1. Defina **Referência** como *Ordem de compra*.
1. Defina **Número da conta** como *1001*.
1. Defina **Número** para o número da ordem de compra que você identificou para este exercício.

    ![Diário de entrada de itens](../media/item-arrival-journal-header.png "Diário de entrada de itens")

1. Selecione **OK** para criar o cabeçalho do diário.
1. Na seção **Linhas do diário**, selecione **Adicionar linha** e insira os seguintes dados:
    - **Número do item** – Defina como *M9200*. O **Local**, o **Depósito** e a **Quantidade** serão definidos com base nos dados da transação de estoque para os 10 paletes (1000 ea.).
    - **Local** – definido como *001*. Este local específico não controla as placas de licença.

    ![Linha do diário de entrada de itens](../media/item-arrival-journal-line.png "Linha do diário de entrada de itens")

    > [!NOTE]
    > O campo **Data** determina a data em que a quantidade disponível desse item será registrada no estoque.  
    >
    > A **ID do lote** será preenchida pelo sistema se puder ser identificada somente a partir das informações fornecidas. Caso contrário, você precisará inseri-la manualmente. Este é um campo obrigatório, que vincula esse registro a uma linha de documento de origem específica.  

1. No Painel de Ações, selecione **Validar**. Isso verifica se o diário está pronto para ser lançado. Se a validação falhar, você precisará corrigir os erros antes de poder lançar o diário.  
1. A caixa de diálogo **Verificar diário** é aberta. Selecione **OK**.
1. Analise a barra de mensagens. Deve haver uma mensagem denotando que a operação foi concluída.  
1. No Painel de Ações, selecione **Lançar**.
1. A caixa de diálogo **Lançar diário** é aberta. Selecione **OK**.
1. Analise a barra de mensagens. Deve haver mensagens denotando que a operação foi concluída.
1. Selecione **Funções > Recebimento de produtos** no Painel de Ações para atualizar a linha da ordem de compra e lançar um recebimento de produtos.


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]
