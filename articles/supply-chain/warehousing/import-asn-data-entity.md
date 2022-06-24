---
title: Importar ASNs de entrada por meio da entidade de dados V3
description: Este artigo explica como gerenciar a importação de avisos avançados de envio (ASNs) de entrada por meio da entidade de dados ASN de entrada.
author: GalynaFedorova
ms.date: 05/11/2022
ms.topic: article
ms.search.form: WHSInboundASNV3Entity, WHSInboundASNEntity, DMFEntity
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: gfedorova
ms.search.validFrom: 2021-06-04
ms.dyn365.ops.version: 10.0.19
ms.openlocfilehash: 0ac45e070d0473547c48da1380377de3d4bf60bd
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/03/2022
ms.locfileid: "8907106"
---
# <a name="import-inbound-asns-through-the-v3-data-entity"></a>Importar ASNs de entrada por meio da entidade de dados V3

[!include [banner](../../includes/banner.md)]

Os avisos avançados de envio (ASNs) notificam você sobre entregas de fornecedores. Eles ajudam o remetente a descrever o conteúdo de uma remessa e outras informações sobre ele, como os itens e embalagens.

OS ASNs podem ajudar os trabalhadores de depósito a aprender o que chegará quando. Dessa forma, eles podem se preparar. Além disso, os trabalhadores de depósito podem usar ASNs para combinar os detalhes de uma remessa à ordem de compra relacionada que foi criada anteriormente.

Este artigo apresenta um conjunto de cenários que mostram, por meio de exemplos, como trabalhar com os arquivos de ASN.

> [!IMPORTANT]
> O *ASN de entrada* aplica-se apenas a itens habilitados para gerenciamento de depósito avançado (WMS). Antes de receber um ASN, uma ordem de compra deve ser registrada no sistema com base no fornecedor que está enviando esse ASN.

## <a name="inbound-asn-v3-entity"></a>Entidade ASN V3 de entrada

Você importa ASNs de entrada usando a entidade de dados compostos *ASN V3 de entrada*. O *ASN V3 de entrada* aproveita as seguintes entidades:

- Cabeçalho de carga de entrada
- Cabeçalho da remessa de entrada
- Estruturas de embalagem de cargas de entrada
- Casos de estruturas de embalagem de cargas de entrada
- Linhas de caso de estruturas de embalagem de cargas de entrada
- Linhas de estruturas de embalagem de cargas de entrada

A entidade de dados compostos *ASN V3 de entrada* destina-se a cenários de integração assíncrona em que as importações baseadas em arquivos XML são usadas.

## <a name="xml-format-for-importing-asns"></a>Formato XML para importação de ASNs

A Microsoft Dynamics 365 Supply Chain Management permite o seguinte formato XML para importar ASNs. Cada nó no arquivo XML representa um atributo de uma entidade individual.

```xml
<?xml version="1.0" encoding="utf-8"?>
<Document>
    <WHSInboundLoadHeaderEntity>
        <WHSInboundShipmentHeaderEntity>
            <WHSInboundLoadPackingStructureEntity>
                <WHSInboundLoadPackingStructureCaseEntity>
                    <WHSInboundPackingStructureCaseLineV3Entity>
                    </WHSInboundPackingStructureCaseLineV3Entity>
                </WHSInboundLoadPackingStructureCaseEntity>
                <WHSInboundLoadPackingStructureLineV3Entity>
                </WHSInboundLoadPackingStructureLineV3Entity>
            </WHSInboundLoadPackingStructureEntity>
        </WHSInboundShipmentHeaderEntity>
    </WHSInboundLoadHeaderEntity>
</Document>
```

## <a name="examples"></a>Exemplos

As seguintes subseções fornecem exemplos de arquivos XML de importação do ASN para envios de fornecedores.

### <a name="example-1"></a>Exemplo 1

O exemplo a seguir mostra um arquivo XML para importar remessas de fornecedores para uma ordem de compra quando nenhum detalhe do caso é incluído.

```xml
<?xml version="1.0" encoding="utf-8"?>
<Document>
    <WHSInboundLoadHeaderEntity TRACTORNUMBER="0000101">
        <WHSInboundShipmentHeaderEntity VENDORSHIPMENTID="VendASN_01" VENDORADDRESSCOUNTRYREGIONID = "USA" VENDORADDRESSSTREET = "123 Coffee Street" VENDORADDRESSSTATEID = "WA" VENDORADDRESSCITY = "Redmond" VENDORADDRESSZIPCODE = "98052">
            <WHSInboundLoadPackingStructureEntity LICENSEPLATENUMBER="LP_ASN_001">
                <WHSInboundLoadPackingStructureLineV3Entity PURCHASEORDERNUMBER="00000176" ITEMNUMBER="A0001" QUANTITY="1" UNITSYMBOL="ea" />
            </WHSInboundLoadPackingStructureEntity>
        </WHSInboundShipmentHeaderEntity>
    </WHSInboundLoadHeaderEntity>
</Document>
```

### <a name="example-2"></a>Exemplo 2

O exemplo a seguir mostra um arquivo XML para importar remessas de fornecedores para uma ordem de compra quando detalhes do caso são incluídos.

```xml
<?xml version="1.0" encoding="utf-8"?>
<Document>
    <WHSInboundLoadHeaderEntity ESTIMATEDARRIVALDATETIME="2021-04-25T11:00:00+00:00">
        <WHSInboundShipmentHeaderEntity VENDORSHIPMENTID="MVR_SNN_0004">
            <WHSInboundLoadPackingStructureEntity LICENSEPLATENUMBER="MVR_SNN_0004" PACKEDTOTALQUANTITY="2.00">
                <WHSInboundLoadPackingStructureCaseEntity PARENTPACKINGSTRUCTURELICENSEPLATENUMBER="MVR_SNN_0004" LICENSEPLATENUMBER="MVR_SNN_0004A" PACKEDTOTALQUANTITY="2.00" />
                <WHSInboundLoadPackingStructureLine3Entity PURCHASEORDERNUMBER="00000175" ITEMNUMBER="A0001" PURCHASEORDERLINENUMBER="1" QUANTITY="2.00" UNITSYMBOL="ea" />
            </WHSInboundLoadPackingStructureEntity>
        </WHSInboundShipmentHeaderEntity>
    </WHSInboundLoadHeaderEntity>
</Document>
```

### <a name="example-3"></a>Exemplo 3

O exemplo a seguir mostra um arquivo XML para importar remessas de fornecedores para várias ordens de compra quando detalhes do caso são incluídos.

```xml
<?xml version="1.0" encoding="utf-8"?>
<Document>
    <WHSInboundLoadHeaderEntity TRACTORNUMBER="0000101">
        <WHSInboundShipmentHeaderEntity VENDORSHIPMENTID="VendASN_01" VENDORADDRESSCOUNTRYREGIONID = "USA" VendorAddressStreet = "123 Coffee Street" VENDORADDRESSSTATEID = "WA" VENDORADDRESSCITY = "Redmond" VENDORADDRESSZIPCODE = "98052">
            <WHSInboundLoadPackingStructureEntity LICENSEPLATENUMBER="LP_ASN_001">
                <WHSInboundLoadPackingStructureLineV3Entity PURCHASEORDERNUMBER="00000176" ITEMNUMBER="A0001" QUANTITY="100" UNITSYMBOL="ea" />
            </WHSInboundLoadPackingStructureEntity>
        </WHSInboundShipmentHeaderEntity>
        <WHSInboundShipmentHeaderEntity VENDORSHIPMENTID="VendASN_02" VENDORADDRESSCOUNTRYREGIONID = "USA" VendorAddressStreet = "123 Coffee Street" VENDORADDRESSSTATEID = "WA" VENDORADDRESSCITY = "Redmond" VENDORADDRESSZIPCODE = "98052">
            <WHSInboundLoadPackingStructureEntity LICENSEPLATENUMBER="LP_ASN_001">
                <WHSInboundLoadPackingStructureLineV3Entity PURCHASEORDERNUMBER="00000177" ITEMNUMBER="A0001" QUANTITY="200" UNITSYMBOL="ea" />
                <WHSInboundLoadPackingStructureLineV3Entity PURCHASEORDERNUMBER="00000177" ITEMNUMBER="P0004" QUANTITY="300" UNITSYMBOL="ea" ITEMBATCHNUMBER="BN0001" />
            </WHSInboundLoadPackingStructureEntity>
            <WHSInboundLoadPackingStructureEntity LICENSEPLATENUMBER="LP_ASN_002">
                <WHSInboundLoadPackingStructureCaseEntity LICENSEPLATENUMBER="LP_ASN_002_C01">
                    <WHSInboundLoadPackingStructureCaseLineV3Entity PURCHASEORDERNUMBER="00000177" ITEMNUMBER="A0001" QUANTITY="400" UNITSYMBOL="ea" />
                </WHSInboundLoadPackingStructureCaseEntity>
            </WHSInboundLoadPackingStructureEntity>
        </WHSInboundShipmentHeaderEntity>
    </WHSInboundLoadHeaderEntity>
</Document>
```

## <a name="inspect-the-results-of-importing-an-asn-file"></a>Inspecionar os resultados da importação de um arquivo ASN

Siga estas etapas para inspecionar os resultados da importação de um arquivo ASN.

1. Acesse **Gerenciamento de depósito \> Cargas \> Todas as cargas**.
1. Encontre e abra uma carga que foi criada como parte de uma importação ASN.
1. Na FastTab **Carga**, você deve ver valores baseados no arquivo XML.
1. Na FastTab **Linhas de carga**, você deve ver números de ordens de compra e detalhes do item que são baseados no arquivo XML.
1. No Painel de Ações, na guia **Enviar e receber**, no grupo **Receber**, selecione **Estrutura de embalagem** para revisar a estrutura de embalagem da carga.
1. Na FastTab **Paletes**, você deve ver placas de veículo baseadas no arquivo XML.
1. Na FastTab **Casos**, você deve ver casos baseados no arquivo XML.
1. Na FastTab **Itens**, você deve ver itens e quantidades baseadas no arquivo XML.

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
