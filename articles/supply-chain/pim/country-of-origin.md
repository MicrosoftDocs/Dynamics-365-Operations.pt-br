---
title: País de origem
description: Muitas organizações emitem certificados para seus fornecedores a fim de garantir que os produtos atendam a padrões de certificação específicos. Esses certificados geralmente dependem do país de origem. Este artigo fornece informações sobre o recurso de país de origem, que permite vincular um produto ao país de origem e monitorar as certificações de produtos.
author: t-benebo
ms.date: 07/15/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: COOVendorCerts
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: benebotg
ms.search.validFrom: 2020-07-15
ms.dyn365.ops.version: 10.0.9
ms.openlocfilehash: 60d5a2067b8e3d311af89fb09cfa3b5c007db219
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/03/2022
ms.locfileid: "8882508"
---
# <a name="country-of-origin"></a>País de origem

[!include [banner](../includes/banner.md)]

Muitas organizações emitem certificados para seus fornecedores a fim de garantir que os produtos atendam a padrões de certificação específicos. Esses certificados geralmente dependem do país de origem. O recurso de país de origem permite vincular um produto ao país de origem e monitorar as certificações de produtos.

## <a name="turn-on-the-country-of-origin-feature"></a>Ativar o recurso de país de origem

A partir da versão 10.0.21 do Supply Chain Management, este recurso está ativado por padrão. Os administradores podem usar a página [Gerenciamento de recursos](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md) para verificar o status do recurso e ativá-lo ou desativá-lo, se necessário. Aqui o recurso está listado como:

- **Módulo:** *Gerenciamento de informações sobre produtos*
- **Nome do recurso:** *Recurso de gerenciamento do país de origem*

## <a name="configure-source-and-destination-countries"></a>Configurar países de origem e de destino

Antes de emitir um certificado para um produto, você deve vincular o produto ao país de destino e ao país de origem.

1. Acesse **Gerenciamento de informações sobre produtos \> Configuração \> Conformidade de produtos \> País de origem \> Regras do país de origem**.
2. Selecione uma configuração de país existente para editá-la ou selecione **Novo** no Painel de Ação para criar uma nova configuração de país.
3. Defina os valores a seguir para o país novo ou selecionado.

    | Campo | descrição |
    |---|---|
    | Nº de itens | Selecione o número de itens do produto. |
    | País/região de destino | Selecione o país para o qual você está enviando o produto. |
    | País de origem | Selecione o país do qual você está enviando o produto. |

A finalidade desta configuração é ajudá-lo a gerar um relatório de lista de materiais (BOM), no qual é possível incluir o país de origem de cada peça para a qual os países de origem e de destino foram especificados. Esse relatório vai ajudá-lo a obter uma visão holística de onde as peças vêm e aonde estão indo.

## <a name="keep-track-of-vendor-certificates"></a>Monitorar certificados de fornecedores

Você pode usar a página **Certificados de fornecedores do país de origem** para monitorar os certificados emitidos para fornecedores.

Você deve decidir quais documentos de certificado está emitindo e como vai relatá-los aos clientes. Este recurso ajuda a monitorar seus certificados. Ele também permite escolher se os números de certificados relevantes aparecerão em faturas, guias de remessa e/ou confirmações de ordens.

Para configurar as informações sobre o certificado, siga estas etapas.

1. Acesse **Gerenciamento de informações sobre produtos \> Configuração \> Conformidade de produtos \> País de origem \> Certificados de fornecedores do país de origem**.
2. Selecione uma configuração de certificado existente para editá-la ou selecione **Novo** no Painel de Ação para criar uma nova configuração de certificado.
3. Defina as configurações a seguir para o certificado novo ou selecionado.

    | Campo | descrição |
    |---|---|
    | Conta de Fornecedor | Selecione o fornecedor para o qual você emitiu o certificado. |
    | Nº de itens | Selecione o item para o qual você emitiu o certificado. |
    | País/região | O país ou a região de destino em que você deve usar este certificado. |
    | Número do certificado | Insira o número de identificação do certificado emitido. |
    | Em vigor | Selecione a primeira data em que o certificado atual é válido.|
    | Vencimento | Selecione a última data em que o certificado atual é válido. |
    | Imprimir na fatura | Marque esta caixa de seleção para imprimir o número do certificado nas faturas endereçadas ao país especificado durante o intervalo de datas especificado. |
    | Imprimir na guia de remessa | Marque esta caixa de seleção para imprimir o número do certificado nas guias de remessa endereçadas ao país especificado durante o intervalo de datas especificado. |
    | Imprimir na ordem de venda | Marque esta caixa de seleção para imprimir o número do certificado nas ordens de venda endereçadas ao país especificado durante o intervalo de datas especificado. |

## <a name="include-the-country-of-origin-on-bom-reports"></a>Incluir o país de origem nos relatórios de BOM

Ao gerar um relatório de BOM, você pode incluir o país de origem de cada peça para a qual especificou países de origem e de destino na página **Regras do país de origem**.

1. Acesse **Gerenciamento de informações do produto \> Produtos \> Produtos liberados**.
1. Selecione ou crie um produto para abrir sua página **Detalhes do produto liberado**.
1. No Painel de Ação, na guia **Engenharia**, no grupo **BOM**, selecione **Designer**.
1. Na página exibida, no Painel de Ação, selecione **BOM \> Imprimir**.
1. Na caixa de diálogo **Linhas da lista de materiais**, defina o campo **País de destino** como o país de destino que você deseja exibir no relatório.
1. Selecione **OK**.

Um relatório que mostra informações sobre o país de origem de cada peça é gerado e exibido. Veja aqui um exemplo do relatório.

![Relatório sobre o país de origem.](media/country-of-origin-report.png "Relatório sobre o país de origem")


[!INCLUDE[footer-include](../../includes/footer-banner.md)]