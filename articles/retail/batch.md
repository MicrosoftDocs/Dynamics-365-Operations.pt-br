<?xml version="1.0" encoding="UTF-8"?>
<xliff xmlns:logoport="urn:logoport:xliffeditor:xliff-extras:1.0" xmlns:tilt="urn:logoport:xliffeditor:tilt-non-translatables:1.0" xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xmlns="urn:oasis:names:tc:xliff:document:1.2" xmlns:xliffext="urn:microsoft:content:schema:xliffextensions" version="1.2" xsi:schemaLocation="urn:oasis:names:tc:xliff:document:1.2 xliff-core-1.2-transitional.xsd">
  <file datatype="xml" source-language="en-US" original="batch.md" target-language="pt-BR">
    <header>
      <tool tool-company="Microsoft" tool-version="1.0-d915bc8" tool-name="mdxliff" tool-id="mdxliff"/>
      <xliffext:skl_file_name>batch.e70006.4456fc3d5bc4547fa8211642b11ca6df455fa187.skl</xliffext:skl_file_name>
      <xliffext:version>1.2</xliffext:version>
      <xliffext:ms.openlocfilehash>4456fc3d5bc4547fa8211642b11ca6df455fa187</xliffext:ms.openlocfilehash>
      <xliffext:ms.sourcegitcommit>aec1dcd44274e9b8d0770836598fde5533b7b569</xliffext:ms.sourcegitcommit>
      <xliffext:ms.lasthandoff>06/03/2019</xliffext:ms.lasthandoff>
      <xliffext:ms.openlocfilepath>articles\retail\batch.md</xliffext:ms.openlocfilepath>
    </header>
    <body>
      <group extype="content" id="content">
        <trans-unit xml:space="preserve" translate="yes" id="101" restype="x-metadata">
          <source>Improved handling of batch-tracked items</source><target logoport:matchpercent="70" state="translated" state-qualifier="leveraged-mt">Manuseio aprimorado de itens de lote rastreados</target>
        </trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="102" restype="x-metadata">
          <source>This topic describes the improvements that have been made to the handling of batches for batch-tracked items during the Retail statement posting process.</source><target logoport:matchpercent="70" state="translated" state-qualifier="leveraged-mt">Este tópico descreve os aprimoramentos feitos no manuseio de lotes para itens de lote rastreados durante o processo de lançamento de demonstrativo de varejo.</target>
        </trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="103">
          <source>Improved handling of batch-tracked items</source>
        <target logoport:matchpercent="70" state="translated" state-qualifier="leveraged-inherited">Manuseio aprimorado de itens de lote rastreados</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="104">
          <source>In Microsoft Dynamics 365 for Retail Point of Sale (POS), batch numbers can't be captured for batch-tracked items at the time of sale.</source><target logoport:matchpercent="70" state="translated" state-qualifier="leveraged-mt">No ponto de venda (PDV) do Microsoft Dynamics 365 for Retail, os números de lotes não podem ser capturados para itens de lote rastreados no momento da venda.</target>
        </trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="105">
          <source>However, for specific configurations, when sales are posted in the headquarters through customer orders or statement posting, the Microsoft Dynamics system expects that valid batch numbers for batch-tracked items exist, and that they will be used during the invoicing process.</source><target logoport:matchpercent="70" state="translated" state-qualifier="leveraged-mt">No entanto, para configurações específicas, quando as vendas lançadas na matriz por meio de ordens de cliente ou lançamento de demonstrativo, o sistema do Microsoft Dynamics espera que existam números de lote válidos para itens de lote rastreados e que eles sejam usados durante o processo de faturamento.</target>
        </trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="106">
          <source>If valid batch numbers are available for products, the customer order invoicing process and the sales order invoicing process from statement posting use them.</source><target logoport:matchpercent="70" state="translated" state-qualifier="leveraged-mt">Se os números de lote válidos estiverem disponíveis para os produtos, eles serão usados pelo processo de faturamento da ordem do cliente e pelo processo de faturamento da ordem de venda do lançamento de demonstrativo.</target>
        </trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="107">
          <source>Otherwise, the customer order invoicing process can't post, and the POS user receives an error message.</source><target logoport:matchpercent="70" state="translated" state-qualifier="leveraged-mt">Caso contrário, processo de faturamento da ordem do cliente não poderá fazer o lançamento e o usuário do PDV receberá uma mensagem de erro.</target>
        </trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="108">
          <source>Statement posting then goes into an error state.</source><target logoport:matchpercent="70" state="translated" state-qualifier="leveraged-mt">O lançamento do demonstrativo entrará então em um estado de erro.</target>
        </trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="109">
          <source>This error state occurs even when negative inventory has been turned on for the products.</source><target logoport:matchpercent="70" state="translated" state-qualifier="leveraged-mt">Esse estado de erro ocorrerá mesmo quando o estoque negativo tiver sido ativado para os produtos.</target>
        </trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="110">
          <source>Improvements that have been made in Microsoft Dynamics for Retail version 10.0.4 and later help guarantee that, when negative inventory is turned on for batch-tracked items, customer order invoicing and sales order invoicing through statement posting aren't blocked for those items if the inventory is 0 (zero) or a batch number isn't available.</source><target logoport:matchpercent="70" state="translated" state-qualifier="leveraged-mt">Os aprimoramentos feitos no Microsoft Dynamics for Retail versão 10.0.4 e posterior ajudam a garantir que, quando o estoque negativo for ativado para itens de lote rastreados, o faturamento da ordem do cliente e o faturamento da ordem venda por meio do lançamento de demonstrativo não serão bloqueados para esses itens se o estoque for 0 (zero) ou se um número de lote não estiver disponível.</target>
        </trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="111">
          <source>The new functionality uses a default batch ID for the sales lines when batch numbers aren't available.</source><target logoport:matchpercent="70" state="translated" state-qualifier="leveraged-mt">A nova funcionalidade usa uma ID de lote padrão para as linhas de venda quando os números de lotes não estão disponíveis.</target>
        </trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="112">
          <source>To define the default batch ID that is used for customer orders, on the <bpt id="p1">**</bpt>Retail parameters<ept id="p1">**</ept> page, on the <bpt id="p2">**</bpt>Customer orders<ept id="p2">**</ept> tab, on the <bpt id="p3">**</bpt>Order<ept id="p3">**</ept> FastTab, set the <bpt id="p4">**</bpt>Default batch id<ept id="p4">**</ept> field.</source><target logoport:matchpercent="70" state="translated" state-qualifier="leveraged-mt">Para definir a ID padrão do lote usada para ordens de cliente, na página <bpt id="p1">**</bpt>Parâmetros de varejo<ept id="p1">**</ept> , na guia <bpt id="p2">**</bpt>Ordens do cliente<ept id="p2">**</ept>, na FastTab <bpt id="p3">**</bpt>Ordem<ept id="p3">**</ept>, defina o campo <bpt id="p4">**</bpt>ID de lote padrão<ept id="p4">**</ept>.</target>
        </trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="113">
          <source>To define the default batch ID that is used for sales order invoicing through statement posting, on the <bpt id="p1">**</bpt>Retail parameters<ept id="p1">**</ept> page, on the <bpt id="p2">**</bpt>Posting<ept id="p2">**</ept> tab, on the <bpt id="p3">**</bpt>Inventory update<ept id="p3">**</ept> FastTab, set the <bpt id="p4">**</bpt>Default batch id<ept id="p4">**</ept> field.</source><target logoport:matchpercent="0" state="translated">Para definir a ID de lote padrão usada para o faturamento da ordem do cliente por meio do lançamento de demonstrativo, na página <bpt id="p1">**</bpt>Parâmetros de varejo<ept id="p1">**</ept>, na guia <bpt id="p2">**</bpt>Lançamento<ept id="p2">**</ept>, na FastTab <bpt id="p3">**</bpt>Atualização de estoque<ept id="p3">**</ept>, defina o campo <bpt id="p4">**</bpt>ID de lote padrão<ept id="p4">**</ept>.</target>
        </trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="114">
          <source>This functionality is available only when advanced warehousing is turned on for the specific store warehouse and items.</source><target logoport:matchpercent="70" state="translated" state-qualifier="leveraged-mt">Esta funcionalidade ficará disponível somente quando o armazenamento avançado for ativado para os depósitos e o itens de específicos da loja.</target>
        </trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="115">
          <source>In a later release, the functionality will also be supported for scenarios where advanced warehouse management isn't used.</source><target logoport:matchpercent="70" state="translated" state-qualifier="leveraged-mt">Em uma versão posterior, a funcionalidade também terá suporte para cenários em que o gerenciamento de armazenamento não é usado.</target>
        </trans-unit>
      </group>
    </body>
  </file>
</xliff>