---
title: Configuração, autorização, e captura de cartão de crédito
description: Este artigo fornece uma visão geral da autorização de cartão de crédito no Microsoft Dynamics 365 Finance. Ele inclui informações sobre como configurar o serviço de pagamento, adicionar um cartão de crédito a uma ordem de venda e anular uma autorização.
author: ShivamPandey-msft
ms.date: 08/22/2017
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: CreditCardProcessors, CustTable, SalesTable
audience: Application User
ms.reviewer: kfend
ms.custom: 3041
ms.assetid: 678f6899-bfa5-439b-aaca-b4affcc338ba
ms.search.region: Global
ms.author: shpandey
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: d363b8a909855d3495d78b8721e467d3f78ebbd6
ms.sourcegitcommit: d1683d033fc74adbc4465dd26f7b0055e7639753
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/05/2022
ms.locfileid: "8713995"
---
# <a name="credit-card-setup-authorization-and-capture"></a>Configuração, autorização, e captura de cartão de crédito

[!include [banner](../includes/banner.md)]

Este artigo fornece uma visão geral da autorização de cartão de crédito no Microsoft Dynamics 365 Finance. Ele inclui informações sobre como configurar o serviço de pagamento, adicionar um cartão de crédito a uma ordem de venda e anular uma autorização.

## <a name="setting-up-the-credit-card-payment-service"></a>Configuração do serviço de pagamento com cartão de crédito

Para usar cartões de crédito, você deve configurar e ativar um serviço de pagamento na página Serviços de pagamento. Um serviço de pagamento atua como uma ponte entre a entidade legal e o banco que processa encargos de cartão de crédito de um cliente. Você deve trabalhar com um provedor de cartão de crédito listado no campo do conector Pagamento configurar uma conta com esse fornecedor. Você deve então configurar as outras opções na página Serviços de pagamento, configurar tipos de cartão de crédito para American Express, Discover, MasterCard na página Tipos de cartão de crédito e ativar o provedor como o provedor padrão. Você também deve concluir estas etapas para concluir sua configuração:
-   Na página Parâmetros de contas a receber, especifique os parâmetros para o uso de autorizações de cartão de crédito.
-   Na página Condições de pagamento, configure as condições de pagamento para cartões de crédito. No campo Tipo de pagamento, selecione Cartão de crédito.
-   Na página Cartões de crédito do cliente, insira as informações de cartão de crédito para os clientes.

## <a name="adding-a-new-credit-card"></a>Adição de um novo cartão de crédito
Você pode criar novos registros de cartão de crédito na página Clientes usando Cliente, Configurar, Cartão de crédito. Você também pode criar registros de cartão de crédito quando inserir ordens de venda na página Ordem de venda usando Gerenciar, Cliente, Cartão de crédito, Registro.

## <a name="adding-a-credit-card-to-a-sales-order"></a>Adição de um cartão de crédito a uma ordem de venda

Você pode adicionar um cartão de crédito a uma ordem de venda selecionando um cartão de crédito na pesquisa de cartão de crédito da Guia Rápida Preço e descontos na página Ordem de venda. Para iniciar o processo de autorização, no Painel de Ação, na guia Gerenciar, selecione Cartão de crédito e Autorizar.

## <a name="authorizing-a-credit-card"></a>Autorização de um cartão de crédito

Quando um cartão de crédito é autorizado, o número do cartão e o nome do titular são verificados, e a linha de crédito disponível é confirmada. Opcionalmente, o valor de verificação do cartão e o endereço do titular do cartão são verificados. A linha de crédito disponível do cliente é, então, reduzida pelo valor da fatura. O serviço de pagamento envia a informação de que o cartão de crédito foi aprovado ou rejeitado. Quando a ordem de venda é faturada, o cartão é cobrado (capturado) pelo valor da fatura.

### <a name="card-verification-value"></a>Valor de verificação de cartão

Você pode solicitar o número de verificação do cartão, às vezes chamado de código de segurança do cartão. Para a American Express, é um número de quatro dígitos. Para Discover, MasterCard e Visa, é um número de três dígitos.

### <a name="address-verification"></a>Verificação de endereço

As informações de verificação de endereço são sempre enviadas ao provedor de pagamento. Você pode decidir quais informações são necessárias para que uma transação seja aceita. Verifique com seu fornecedor para determinar se ele aceita essas informações. Estas são as opções de verificação de endereço:
-   **Sempre aceitar transação** – aceite a transação, independentemente dos resultados de verificação de endereço.
-   **Titular da conta** – compare o nome do titular do cartão na transação com as informações da empresa de cartão de crédito.
-   **Endereço de cobrança** – compare o nome e o endereço de cobrança do titular do cartão para a transação com as informações da empresa de cartão de crédito.
-   **CEP de cobrança** – compare o nome, o endereço de cobrança e o CEP do titular do cartão da transação com as informações da empresa de cartão de crédito.

## <a name="data-support"></a>Suporte de dados
Para cada tipo de cartão de crédito compatível, você pode especificar o nível de suporte de dados. O nível controla quantas informações sobre uma transação são transferidas para o serviço de pagamento. Verifique com seu fornecedor para determinar se ele pode fornecer essas informações. Estas são as opções para o nível de suporte de dados:
-   **Nível 1** – transfira a data da transação, o valor da transação e a descrição.
-   **Nível 2** – transfira todas as informações de Nível 1, mais os endereços de remessa e do comerciante e as informações sobre impostos.
-   **Nível 3** – transfira todas as informações de Nível 2, além das informações de linha da ordem.

## <a name="partial-payments"></a>Pagamentos parciais
Se você enviar parte de uma ordem, o valor da ordem parcial será capturado, e a autorização correspondente ao valor da ordem total, será fechada. Uma nova autorização será enviada para o valor restante da ordem que ainda não foi remetida.

## <a name="voiding-an-authorization"></a>Anulando uma autorização 
Para anular uma autorização de cartão de crédito, você pode alterar o método de pagamento para outro método que não tenha um tipo de Cartão de crédito.







[!INCLUDE[footer-include](../../includes/footer-banner.md)]
