---
title: Lançar documentos fiscais brasileiros via demonstrativos de varejo na sede do Commerce
description: Este tópico descreve como lançar documentos fiscais brasileiros por meio de demonstrativos de varejo no Microsoft Dynamics 365 Commerce.
author: akviklis
manager: annbe
ms.date: 06/10/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: v-chgri
ms.search.region: Brazil
ms.search.industry: Retail
ms.author: akviklis
ms.search.validFrom: 2021-01-01
ms.dyn365.ops.version: 10.0.18
ms.openlocfilehash: 086a130bdebef3f34676a7a436dba9abb35a3c3e
ms.sourcegitcommit: 6dc2b877cf8ea9185a07964ec05c5ddb7a78471b
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/12/2022
ms.locfileid: "8407968"
---
# <a name="post-brazilian-fiscal-documents-via-retail-statements-in-commerce-headquarters"></a>Lançar documentos fiscais brasileiros via demonstrativos de varejo na sede do Commerce 

[!include[banner](../includes/banner.md)]

Este tópico descreve como lançar documentos fiscais brasileiros por meio de demonstrativos de varejo no Microsoft Dynamics 365 Commerce.

Depois de executar o P-jobs e lançar um demonstrativo de varejo, os documentos fiscais NFC-e (Nota Fiscal do Consumidor eletrônico) que foram emitidos através dos terminais do Ponto de Venda (PDV) do Commerce podem ser visualizados na página **Visualizar mensagem XML** na sede do Commerce.

## <a name="post-retail-statements"></a>Lançar demonstrativos de varejo

Os documentos NFC-e que são emitidos em PDV são publicados na sede do Commerce quando as declarações de varejo abertas são publicadas no módulo **Varejo e Commerce**. Os demonstrativos de varejo podem conter transações NFC-e e NF-e (Nota Fiscal eletrônica) para devoluções.

Para lançar um documento NFC-e que foi emitido em PDV, siga estas etapas.

1. Acesse **Varejo e Comércio \> TI de Varejo e Comércio \> Agenda de distribuição**.
1. Execute o **P-job** para o banco de dados do canal.
1. Acesse **Varejo e Comércio \> TI de Varejo e Comércio \> Lançamento do PDV**.
1. Execute o trabalho em lote de **Validar transações da loja**.
1. Execute o trabalho em lote **Calcular demonstrativos transacionais em lote**.
1. Execute o trabalho em lote **Lançar demonstrativos transacionais em lote**.
1. Acesse **Varejo e Comércio \> Consultas e relatórios \> demonstrativos lançados** e verifique se o demonstrativo foi lançado.

> [!NOTE]
> Esse procedimento faz um lançamento baseado em feed, conforme descrito em [Criação de ordens baseadas em feeds do Trickle para transações de lojas de varejo](../trickle-feed.md). Para obter mais informações, consulte [Demonstrativos de varejo](../retail-statements.md).

## <a name="view-fiscal-document-details-in-commerce-headquarters"></a>Veja detalhes do documento fiscal na sede do Commerce

Para ver detalhes do documento fiscal na sede do Commerce, siga estas etapas.

1. Para ver um documento NFC-e na sede do Commerce, acesse **Varejo e Comércio \> Consultas e relatórios \> Todos os documentos fiscais**. A página **Todos os documentos fiscais** mostra o mesmo formato que é mostrado quando você visualiza um documento fiscal NF-e modelo 55. Isso inclui o cabeçalho, linhas e todos os atributos. Para obter mais informações, consulte [Documentos fiscais e estrutura de documentos fiscais para o Brasil](../../finance/localizations/latam-bra-fiscal-documents-fiscal-document-framework.md).

    > [!NOTE]
    > Por padrão, se você abrir a página **Todos os documentos fiscais** na sede do Commerce, ele lista apenas os documentos fiscais NFC-e modelo 65. Para visualizar os retornos que possuem documentos fiscais NFC-e modelo 55, você deve alterar os critérios do filtro. No entanto, se você abrir a página **Todos os documentos fiscais** no módulo **Contabilidade**, ele listará todos os modelos de documentos fiscais de entrada e saída, incluindo o modelo 55 e o modelo 65.

1. Na página **Todos os documentos fiscais**, revise o campo **Status** para os documentos fiscais que deseja visualizar. Para as vendas autorizadas pela autoridade fiscal do estado, o campo **Status** será definido como **Aprovado**.
1. Selecione os documentos fiscais necessários e, em seguida, na guia **NF-e federal**, selecione **Documento XML**.
1. Na página **Visualizar mensagem XML**, nas guias **NF-e** e **Devolução de NF-e**, valide as solicitações e respostas XML disponíveis.
1. Na guia **Cancelar**, valide qualquer solicitação e resposta XML cancelada que estiver disponível.

## <a name="additional-resources"></a>Recursos adicionais

[Configurar e implantar a localização do Commerce para o Brasil](latam-bra-deployment.md)

[Localização do Commerce para o Brasil](latam-bra-commerce-localization.md)

[Funcionalidade de documento fiscal NFC-e no Comércio POS para o Brasil](latam-bra-nfce.md)

[Gerenciar informações do cliente no PDV para o Brasil](latam-bra-customer-information.md)

[Cancelamento e devolução de notas NFC-e no PDV do Commerce para o Brasil](latam-bra-nfce-cancel-return.md)

[Registro adiado de documentos NFC-e emitidos no modo de contingência offline](latam-bra-nfce-contingency-mode.md)
