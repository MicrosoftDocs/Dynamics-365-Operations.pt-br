---
title: Gerenciar informações do cliente no PDV para o Brasil
description: Este tópico descreve como gerenciar informações do cliente no Ponto de Venda (PDV) do Commerce para o Brasil.
author: akviklis
manager: annbe
ms.date: 06/10/2021
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-retail
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: v-chgri
ms.search.region: Brazil
ms.search.industry: Retail
ms.author: sepism
ms.search.validFrom: 2021-01-01
ms.dyn365.ops.version: 10.0.18
ms.openlocfilehash: eaf1689746ece7e44da8f683467b748d2ccd00925f750a29681ec5f166490b9b
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/05/2021
ms.locfileid: "6755868"
---
# <a name="manage-customer-information-in-pos-for-brazil"></a>Gerenciar informações do cliente no PDV para o Brasil

[!include [banner](../includes/banner.md)]

Este tópico descreve como gerenciar informações do cliente no Ponto de Venda (PDV) do Commerce para o Brasil. Essas informações incluem números do CNPJ (Cadastro Nacional da Pessoa Jurídica)/CPF (Cadastro de Pessoas Físicas). Você pode especificar o número de registro de impostos do cliente, o nome e as informações de endereço quando adicionar um cliente nomeado ao carrinho no PDV. Você também pode inserir informações manualmente para uma transação de vendas. As informações do cliente podem então ser impressas nos recibos fiscais DANFE (Documento Auxiliar de Nota Fiscal Eletrônica) e usadas para fins de faturamento.

Para obter mais informações sobre como configurar esta funcionalidade, consulte [Gerenciamento de informações do cliente](latam-bra-deployment.md#customer-information-management).

## <a name="example-scenarios"></a>Cenários de exemplo

Os cenários de exemplo a seguir mostram como gerenciar de informações do cliente no PDV do Commerce para o Brasil.

### <a name="scenario-1-make-a-sale-to-an-anonymous-customer"></a>Cenário 1: fazer uma venda para um cliente anônimo

Para fazer uma venda a um cliente anônimo, siga estas etapas.

1. Entre no POS.
1. Adicione itens ao carrinho.
1. Selecione **Adicionar informações do cliente** e selecione **Digitar manualmente**.
1. Digite o número do CNPJ/CPF ou ID de estrangeiro, nome e endereço do cliente e então selecione **OK**.
1. Registre os pagamentos da transação e, em seguida, finalize a transação.
1. Verifique se o recibo impresso contém o número do CNPJ/CPF ou ID de estrangeiro, nome e endereço do cliente.

### <a name="scenario-2-make-a-sale-to-an-existing-named-customer"></a>Cenário 2: fazer uma venda para um cliente nomeado existente

Para fazer uma venda a um cliente nomeado, siga estas etapas.

1. Entre no POS.
1. Adicione itens ao carrinho.
1. Selecione **Adicionar cliente** e então encontre e selecione o cliente desejado.
1. Adicione o cliente à transação.
1. Registre os pagamentos da transação e, em seguida, finalize a transação.
1. Verifique se o recibo impresso contém o número do CNPJ/CPF ou ID de estrangeiro, nome e endereço do cliente.

### <a name="scenario-3-make-a-sale-to-a-new-named-customer"></a>Cenário 3: fazer uma venda para um novo cliente nomeado

Para fazer uma venda a um novo cliente nomeado, siga estas etapas.

1. Entre no POS.
1. Adicione itens ao carrinho.
1. Selecione **Adicionar cliente** e depois **Criar cliente**.
1. Especifique os atributos do novo cliente.
1. No campo **CNPJ/CPF**, digite o número do CNPJ/CPF do cliente.
1. No campo **ID de estrangeiro**, digite o ID de estrangeiro do cliente, se for necessário.
1. Selecione **Adicionar endereço** e então digite as informações de contato e endereço do novo cliente.
1. Salve o registro do cliente e o registro de endereço do cliente e então adicione o cliente à transação.
1. Registre os pagamentos da transação e, em seguida, finalize a transação.
1. Verifique se o recibo impresso contém o número do CNPJ/CPF ou ID de estrangeiro, nome e endereço do cliente.

> [!NOTE]
> Se você tiver que especificar um cliente diferente para a transação, você deve primeiro limpar as informações do cliente. Em seguida, selecione outro cliente.

### <a name="scenario-4-change-the-customer-information-for-a-sale-to-a-named-customer"></a>Cenário 4: alterar as informações do cliente para uma venda para um cliente nomeado

Para alterar as informações do cliente para uma venda para um cliente nomeado, siga estas etapas.

1. Entre no POS.
1. Adicione itens ao carrinho.
1. Selecione **Adicionar cliente** e, em seguida, selecione uma conta do cliente para adicionar à transação.
1. Selecione **Adicionar informações do cliente** e então selecione **Limpar** para limpar as informações do cliente da transação.
1. Selecione **Digitar manualmente**.
1. Digite o número do CNPJ/CPF ou ID de estrangeiro, nome e endereço do cliente e então selecione **OK**.
1. Registre os pagamentos da transação e, em seguida, finalize a transação.
1. Verifique se o recibo impresso contém o número do CNPJ/CPF ou ID de estrangeiro, nome e endereço do cliente.

## <a name="additional-resources"></a>Recursos adicionais

[Configurar e implantar a localização do Commerce para o Brasil](latam-bra-deployment.md)

[Localização do Commerce para o Brasil](latam-bra-commerce-localization.md)

[Funcionalidade de documento fiscal NFC-e no Comércio POS para o Brasil](latam-bra-nfce.md)

[Cancelamento e devolução de documentos NFC-e no PDV do Commerce para o Brasil](latam-bra-nfce-cancel-return.md)

[Registro adiado de notas NFC-e emitidas no modo de contingência offline](latam-bra-nfce-contingency-mode.md)

[Lançar documentos fiscais brasileiros via demonstrativos de varejo na sede do Commerce](latam-bra-retail-statements.md)
