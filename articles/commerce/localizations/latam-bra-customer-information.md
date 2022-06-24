---
title: Gerenciar informações do cliente no PDV para o Brasil
description: Este artigo descreve como gerenciar informações do cliente no PDV (Ponto de Venda) do Commerce para o Brasil.
author: akviklis
manager: annbe
ms.date: 12/01/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: v-chgri
ms.search.region: Brazil
ms.search.industry: Retail
ms.author: sepism
ms.search.validFrom: 2021-01-01
ms.dyn365.ops.version: 10.0.18
ms.openlocfilehash: b2396d6cf73364a7c5c8b1f06d1f46b1cbd00c9b
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/03/2022
ms.locfileid: "8848878"
---
# <a name="manage-customer-information-in-pos-for-brazil"></a>Gerenciar informações do cliente no PDV para o Brasil

[!include [banner](../includes/banner.md)]

Este artigo descreve como gerenciar informações do cliente no PDV (Ponto de Venda) do Commerce para o Brasil. Essas informações incluem os números do CNPJ (Cadastro Nacional da Pessoa Jurídica)/CPF (Cadastro de Pessoas Físicas), do CCM (Cadastro de Contribuintes Mobiliários) e da IE (Inscrição estadual). 

Você pode especificar o número de registro de imposto, o nome e o endereço do cliente quando criar ou editar o registro mestre de um cliente nomeado e um registro de endereço do cliente no PDV. Você também pode inserir manualmente as informações mínimas necessárias (incluindo o CNPJ) para uma transação de vendas. Em seguida, os números de registro de imposto do cliente poderão ser usados em pesquisas do cliente no PDV, adicionados ao carrinho, impressos nos recibos fiscais DANFE (Documento Auxiliar da Nota Fiscal Eletrônica) e usados para faturamento.

> [!NOTE]
> Não será possível especificar números de registro para clientes nomeados no PDV se a opção **Criar cliente no modo assíncrono** estiver habilitada no perfil de funcionalidade do PDV. O suporte ao modo assíncrono de criação do cliente poderá ser adicionado em atualizações futuras.

Para mais informações sobre como configurar essa funcionalidade, consulte [Gerenciamento de informações do cliente](latam-bra-deployment.md#customer-information-management) e [Ativar pesquisas de clientes com base nos números de registro de imposto no PDV](latam-bra-deployment.md#enable-customer-searches-based-on-tax-registration-numbers-in-pos).

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
1. Selecione **Adicionar cliente** e, em seguida, localize e selecione o cliente desejado (por exemplo, pesquisando números de registro de imposto).
1. Adicione o cliente à transação.
1. Registre os pagamentos da transação e, em seguida, finalize a transação.
1. Verifique se o recibo impresso contém os números de registro de imposto ou ID de estrangeiro, nome e endereço do cliente.

### <a name="scenario-3-make-a-sale-to-a-new-named-customer"></a>Cenário 3: fazer uma venda para um novo cliente nomeado

Para fazer uma venda a um novo cliente nomeado, siga estas etapas.

1. Entre no POS.
1. Adicione itens ao carrinho.
1. Selecione **Adicionar cliente** e depois **Criar cliente**.
1. Especifique os atributos do novo cliente.
1. No campo **CNPJ/CPF**, insira o CNPJ/CPF do cliente se ele não for estrangeiro.
1. No campo **IE**, insira a IE do cliente, se for necessário.
1. No campo **CCM**, insira o CCM do cliente, se for necessário.
1. No campo **ID de estrangeiro**, digite o ID de estrangeiro do cliente, se for necessário.
1. Selecione **Adicionar endereço** e então digite as informações de contato e endereço do novo cliente.
1. Salve o registro do cliente e o registro de endereço do cliente e então adicione o cliente à transação.
1. Registre os pagamentos da transação e, em seguida, finalize a transação.
1. Verifique se o recibo impresso contém os números de registro de imposto ou ID de estrangeiro, nome e endereço do cliente.

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
