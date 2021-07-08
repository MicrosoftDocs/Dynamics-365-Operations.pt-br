---
title: Importar ASNs de entrada por meio da entidade de dados V2
description: Este tópico explica como gerenciar a importação de avisos avançados de envio (ASNs) de entrada por meio da entidade de dados ASN V2 de entrada.
author: GalynaFedorova
ms.date: 05/31/2021
ms.topic: article
ms.search.form: WHSInboundASNV2Entity, WHSInboundASNEntity
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: v-gfedorova
ms.search.validFrom: 2021-06-04
ms.dyn365.ops.version: 10.0.19
ms.openlocfilehash: 470cc0c39f211a5d0f106c4c6e193867388e2b53
ms.sourcegitcommit: e6437d994c3be0c5bb4a9263af3aa8351020d83a
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/14/2021
ms.locfileid: "6249057"
---
# <a name="import-inbound-asns-through-the-v2-data-entity"></a><span data-ttu-id="ef76a-103">Importar ASNs de entrada por meio da entidade de dados V2</span><span class="sxs-lookup"><span data-stu-id="ef76a-103">Import inbound ASNs through the V2 data entity</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="ef76a-104">Os avisos avançados de envio (ASNs) notificam você sobre entregas de fornecedores.</span><span class="sxs-lookup"><span data-stu-id="ef76a-104">Advanced shipping notices (ASNs) notify you about vendor deliveries.</span></span> <span data-ttu-id="ef76a-105">Eles ajudam o remetente a descrever o conteúdo de uma remessa e outras informações sobre ele, como os itens e embalagens.</span><span class="sxs-lookup"><span data-stu-id="ef76a-105">They help the sender describe the contents of a shipment and additional information about it, such as the items and packaging.</span></span>

<span data-ttu-id="ef76a-106">OS ASNs podem ajudar os trabalhadores de depósito a aprender o que chegará quando.</span><span class="sxs-lookup"><span data-stu-id="ef76a-106">ASNs can help warehouse workers learn what is arriving when.</span></span> <span data-ttu-id="ef76a-107">Dessa forma, eles podem se preparar.</span><span class="sxs-lookup"><span data-stu-id="ef76a-107">Therefore, they can prepare.</span></span> <span data-ttu-id="ef76a-108">Além disso, os trabalhadores de depósito podem usar ASNs para combinar os detalhes de uma remessa à ordem de compra relacionada que foi criada anteriormente.</span><span class="sxs-lookup"><span data-stu-id="ef76a-108">In addition, warehouse workers can use ASNs to match the details of a shipment to the related purchase order that was previously created.</span></span>

<span data-ttu-id="ef76a-109">Este tópico apresenta um conjunto de cenários que mostram, por meio de exemplos, como trabalhar com os arquivos de ASN.</span><span class="sxs-lookup"><span data-stu-id="ef76a-109">This topic presents a collection of scenarios that show, through examples, how to work with ASN files.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="ef76a-110">O *ASN de entrada* aplica-se apenas a itens habilitados para gerenciamento de depósito avançado (WMS).</span><span class="sxs-lookup"><span data-stu-id="ef76a-110">*Inbound ASN* import applies only to items that are enabled for advanced warehouse management (WMS).</span></span> <span data-ttu-id="ef76a-111">Antes de receber um ASN, uma ordem de compra deve ser registrada no sistema com base no fornecedor que está enviando esse ASN.</span><span class="sxs-lookup"><span data-stu-id="ef76a-111">Before you receive an ASN, a purchase order must be registered in the system against the vendor who is sending that ASN.</span></span>

## <a name="inbound-asn-v2-entity"></a><span data-ttu-id="ef76a-112">Entidade ASN V2 de entrada</span><span class="sxs-lookup"><span data-stu-id="ef76a-112">Inbound ASN V2 entity</span></span>

<span data-ttu-id="ef76a-113">Você importa ASNs de entrada usando a entidade de dados compostos *ASN V2 de entrada*.</span><span class="sxs-lookup"><span data-stu-id="ef76a-113">You import inbound ASNs by using the *Inbound ASN V2* composite data entity.</span></span> <span data-ttu-id="ef76a-114">O *ASN V2 de entrada* aproveita as seguintes entidades:</span><span class="sxs-lookup"><span data-stu-id="ef76a-114">*Inbound ASN V2* takes advantage of the following entities:</span></span>

- <span data-ttu-id="ef76a-115">Cabeçalho de carga de entrada</span><span class="sxs-lookup"><span data-stu-id="ef76a-115">Inbound load header</span></span>
- <span data-ttu-id="ef76a-116">Cabeçalho da remessa de entrada</span><span class="sxs-lookup"><span data-stu-id="ef76a-116">Inbound shipment header</span></span>
- <span data-ttu-id="ef76a-117">Estruturas de embalagem de cargas de entrada</span><span class="sxs-lookup"><span data-stu-id="ef76a-117">Inbound load packing structures</span></span>
- <span data-ttu-id="ef76a-118">Casos de estruturas de embalagem de cargas de entrada</span><span class="sxs-lookup"><span data-stu-id="ef76a-118">Inbound load packing structure cases</span></span>
- <span data-ttu-id="ef76a-119">Linhas de caso de estruturas de embalagem de cargas de entrada</span><span class="sxs-lookup"><span data-stu-id="ef76a-119">Inbound load packing structure case lines</span></span>
- <span data-ttu-id="ef76a-120">Linhas de estruturas de embalagem de cargas de entrada</span><span class="sxs-lookup"><span data-stu-id="ef76a-120">Inbound load packing structure lines</span></span>

<span data-ttu-id="ef76a-121">A entidade de dados compostos *ASN V2 de entrada* destina-se a cenários de integração assíncrona em que as importações baseadas em arquivos XML são usadas.</span><span class="sxs-lookup"><span data-stu-id="ef76a-121">The *Inbound ASN V2* composite data entity is intended for asynchronous integration scenarios where XML file–based imports are used.</span></span>

## <a name="xml-format-for-importing-asns"></a><span data-ttu-id="ef76a-122">Formato XML para importação de ASNs</span><span class="sxs-lookup"><span data-stu-id="ef76a-122">XML format for importing ASNs</span></span>

<span data-ttu-id="ef76a-123">A Microsoft Dynamics 365 Supply Chain Management permite o seguinte formato XML para importar ASNs.</span><span class="sxs-lookup"><span data-stu-id="ef76a-123">Microsoft Dynamics 365 Supply Chain Management supports the following XML format for importing ASNs.</span></span> <span data-ttu-id="ef76a-124">Cada nó no arquivo XML representa um atributo de uma entidade individual.</span><span class="sxs-lookup"><span data-stu-id="ef76a-124">Each node in the XML file represents an attribute from an individual entity.</span></span>

```xml
<?xml version="1.0" encoding="utf-8"?>
<Document>
    <WHSInboundLoadHeaderEntity>
        <WHSInboundShipmentHeaderEntity>
            <WHSInboundLoadPackingStructureEntity>
                <WHSInboundLoadPackingStructureCaseEntity>
                    <WHSInboundPackingStructureCaseLineV2Entity>
                    </WHSInboundPackingStructureCaseLineV2Entity>
                </WHSInboundLoadPackingStructureCaseEntity>
                <WHSInboundLoadPackingStructureLineV2Entity>
                </WHSInboundLoadPackingStructureLineV2Entity>
            </WHSInboundLoadPackingStructureEntity>
        </WHSInboundShipmentHeaderEntity>
    </WHSInboundLoadHeaderEntity>
</Document>
```

## <a name="examples"></a><span data-ttu-id="ef76a-125">Exemplos</span><span class="sxs-lookup"><span data-stu-id="ef76a-125">Examples</span></span>

<span data-ttu-id="ef76a-126">As seguintes subseções fornecem exemplos de arquivos XML de importação do ASN para envios de fornecedores.</span><span class="sxs-lookup"><span data-stu-id="ef76a-126">The following subsections provide examples of ASN XML import files for vendor shipments.</span></span>

### <a name="example-1"></a><span data-ttu-id="ef76a-127">Exemplo 1</span><span class="sxs-lookup"><span data-stu-id="ef76a-127">Example 1</span></span>

<span data-ttu-id="ef76a-128">O exemplo a seguir mostra um arquivo XML para importar remessas de fornecedores para uma ordem de compra quando nenhum detalhe do caso é incluído.</span><span class="sxs-lookup"><span data-stu-id="ef76a-128">The following example shows an XML file for importing vendor shipments for one purchase order when no case details are included.</span></span>

```xml
<?xml version="1.0" encoding="utf-8"?>
<Document>
    <WHSInboundLoadHeaderEntity TRACTORNUMBER="0000101">
        <WHSInboundShipmentHeaderEntity VENDORSHIPMENTID="VendASN_01" VENDORADDRESSCOUNTRYREGIONID = "USA" VENDORADDRESSSTREET = "123 Coffee Street" VENDORADDRESSSTATEID = "WA" VENDORADDRESSCITY = "Redmond" VENDORADDRESSZIPCODE = "98052">
            <WHSInboundLoadPackingStructureEntity LICENSEPLATENUMBER="LP_ASN_001">
                <WHSInboundLoadPackingStructureLineV2Entity PURCHASEORDERNUMBER="00000176" ITEMNUMBER="A0001" QUANTITY="1" UNITSYMBOL="ea" />
            </WHSInboundLoadPackingStructureEntity>
        </WHSInboundShipmentHeaderEntity>
    </WHSInboundLoadHeaderEntity>
</Document>
```

### <a name="example-2"></a><span data-ttu-id="ef76a-129">Exemplo 2</span><span class="sxs-lookup"><span data-stu-id="ef76a-129">Example 2</span></span>

<span data-ttu-id="ef76a-130">O exemplo a seguir mostra um arquivo XML para importar remessas de fornecedores para uma ordem de compra quando detalhes do caso são incluídos.</span><span class="sxs-lookup"><span data-stu-id="ef76a-130">The following example shows an XML file for importing vendor shipments for one purchase order when case details are included.</span></span>

```xml
<?xml version="1.0" encoding="utf-8"?>
<Document>
    <WHSInboundLoadHeaderEntity ESTIMATEDARRIVALDATETIME="2021-04-25T11:00:00+00:00">
        <WHSInboundShipmentHeaderEntity VENDORSHIPMENTID="MVR_SNN_0004">
            <WHSInboundLoadPackingStructureEntity LICENSEPLATENUMBER="MVR_SNN_0004" PACKEDTOTALQUANTITY="2.00">
                <WHSInboundLoadPackingStructureCaseEntity PARENTPACKINGSTRUCTURELICENSEPLATENUMBER="MVR_SNN_0004" LICENSEPLATENUMBER="MVR_SNN_0004A" PACKEDTOTALQUANTITY="2.00" />
                <WHSInboundLoadPackingStructureLineV2Entity PURCHASEORDERNUMBER="00000175" ITEMNUMBER="A0001" PURCHASEORDERLINENUMBER="1" QUANTITY="2.00" UNITSYMBOL="ea" />
            </WHSInboundLoadPackingStructureEntity>
        </WHSInboundShipmentHeaderEntity>
    </WHSInboundLoadHeaderEntity>
</Document>
```

### <a name="example-3"></a><span data-ttu-id="ef76a-131">Exemplo 3</span><span class="sxs-lookup"><span data-stu-id="ef76a-131">Example 3</span></span>

<span data-ttu-id="ef76a-132">O exemplo a seguir mostra um arquivo XML para importar remessas de fornecedores para várias ordens de compra quando detalhes do caso são incluídos.</span><span class="sxs-lookup"><span data-stu-id="ef76a-132">The following example shows an XML file for importing vendor shipments for multiple purchase orders when case details are included.</span></span>

```xml
<?xml version="1.0" encoding="utf-8"?>
<Document>
    <WHSInboundLoadHeaderEntity TRACTORNUMBER="0000101">
        <WHSInboundShipmentHeaderEntity VENDORSHIPMENTID="VendASN_01" VENDORADDRESSCOUNTRYREGIONID = "USA" VendorAddressStreet = "123 Coffee Street" VENDORADDRESSSTATEID = "WA" VENDORADDRESSCITY = "Redmond" VENDORADDRESSZIPCODE = "98052">
            <WHSInboundLoadPackingStructureEntity LICENSEPLATENUMBER="LP_ASN_001">
                <WHSInboundLoadPackingStructureLineV2Entity PURCHASEORDERNUMBER="00000176" ITEMNUMBER="A0001" QUANTITY="100" UNITSYMBOL="ea" />
            </WHSInboundLoadPackingStructureEntity>
        </WHSInboundShipmentHeaderEntity>
        <WHSInboundShipmentHeaderEntity VENDORSHIPMENTID="VendASN_02" VENDORADDRESSCOUNTRYREGIONID = "USA" VendorAddressStreet = "123 Coffee Street" VENDORADDRESSSTATEID = "WA" VENDORADDRESSCITY = "Redmond" VENDORADDRESSZIPCODE = "98052">
            <WHSInboundLoadPackingStructureEntity LICENSEPLATENUMBER="LP_ASN_001">
                <WHSInboundLoadPackingStructureLineV2Entity PURCHASEORDERNUMBER="00000177" ITEMNUMBER="A0001" QUANTITY="200" UNITSYMBOL="ea" />
                <WHSInboundLoadPackingStructureLineV2Entity PURCHASEORDERNUMBER="00000177" ITEMNUMBER="P0004" QUANTITY="300" UNITSYMBOL="ea" ITEMBATCHNUMBER="BN0001" />
            </WHSInboundLoadPackingStructureEntity>
            <WHSInboundLoadPackingStructureEntity LICENSEPLATENUMBER="LP_ASN_002">
                <WHSInboundLoadPackingStructureCaseEntity LICENSEPLATENUMBER="LP_ASN_002_C01">
                    <WHSInboundLoadPackingStructureCaseLineV2Entity PURCHASEORDERNUMBER="00000177" ITEMNUMBER="A0001" QUANTITY="400" UNITSYMBOL="ea" />
                </WHSInboundLoadPackingStructureCaseEntity>
            </WHSInboundLoadPackingStructureEntity>
        </WHSInboundShipmentHeaderEntity>
    </WHSInboundLoadHeaderEntity>
</Document>
```

## <a name="inspect-the-results-of-importing-an-asn-file"></a><span data-ttu-id="ef76a-133">Inspecionar os resultados da importação de um arquivo ASN</span><span class="sxs-lookup"><span data-stu-id="ef76a-133">Inspect the results of importing an ASN file</span></span>

<span data-ttu-id="ef76a-134">Siga estas etapas para inspecionar os resultados da importação de um arquivo ASN.</span><span class="sxs-lookup"><span data-stu-id="ef76a-134">Follow these steps to inspect the results of importing an ASN file.</span></span>

1. <span data-ttu-id="ef76a-135">Acesse **Gerenciamento de depósito \> Cargas \> Todas as cargas**.</span><span class="sxs-lookup"><span data-stu-id="ef76a-135">Go to **Warehouse management \> Loads \> All loads**.</span></span>
1. <span data-ttu-id="ef76a-136">Encontre e abra uma carga que foi criada como parte de uma importação ASN.</span><span class="sxs-lookup"><span data-stu-id="ef76a-136">Find and open a load that was created as part of an ASN import.</span></span>
1. <span data-ttu-id="ef76a-137">Na FastTab **Carga**, você deve ver valores baseados no arquivo XML.</span><span class="sxs-lookup"><span data-stu-id="ef76a-137">On the **Load** FastTab, you should see values that are based on the XML file.</span></span>
1. <span data-ttu-id="ef76a-138">Na FastTab **Linhas de carga**, você deve ver números de ordens de compra e detalhes do item que são baseados no arquivo XML.</span><span class="sxs-lookup"><span data-stu-id="ef76a-138">On the **Load lines** FastTab, you should see purchase order numbers and item details that are based on the XML file.</span></span>
1. <span data-ttu-id="ef76a-139">No Painel de Ações, na guia **Enviar e receber**, no grupo **Receber**, selecione **Estrutura de embalagem** para revisar a estrutura de embalagem da carga.</span><span class="sxs-lookup"><span data-stu-id="ef76a-139">On the Action Pane, on the **Ship and receive** tab, in the **Receive** group, select **Packing structure** to review the packing structure of the load.</span></span>
1. <span data-ttu-id="ef76a-140">Na FastTab **Paletes**, você deve ver placas de veículo baseadas no arquivo XML.</span><span class="sxs-lookup"><span data-stu-id="ef76a-140">On the **Pallets** FastTab, you should see license plates that are based on the XML file.</span></span>
1. <span data-ttu-id="ef76a-141">Na FastTab **Casos**, você deve ver casos baseados no arquivo XML.</span><span class="sxs-lookup"><span data-stu-id="ef76a-141">On the **Cases** FastTab, you should see cases that are based on the XML file.</span></span>
1. <span data-ttu-id="ef76a-142">Na FastTab **Itens**, você deve ver itens e quantidades baseadas no arquivo XML.</span><span class="sxs-lookup"><span data-stu-id="ef76a-142">On the **Items** FastTab, you should see items and quantities that are based on the XML file.</span></span>

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
