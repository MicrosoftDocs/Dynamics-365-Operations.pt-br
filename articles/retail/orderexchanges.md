<?xml version="1.0" encoding="UTF-8"?>
<xliff xmlns:logoport="urn:logoport:xliffeditor:xliff-extras:1.0" xmlns:tilt="urn:logoport:xliffeditor:tilt-non-translatables:1.0" xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xmlns="urn:oasis:names:tc:xliff:document:1.2" xmlns:xliffext="urn:microsoft:content:schema:xliffextensions" version="1.2" xsi:schemaLocation="urn:oasis:names:tc:xliff:document:1.2 xliff-core-1.2-transitional.xsd">
  <file datatype="xml" source-language="en-US" original="orderexchanges.md" target-language="pt-BR">
    <header>
      <tool tool-company="Microsoft" tool-version="1.0-7889195" tool-name="mdxliff" tool-id="mdxliff"/>
      <xliffext:skl_file_name>orderexchanges.ba78aa.43571099727830e81c41416b6fe250dba398b3f8.skl</xliffext:skl_file_name>
      <xliffext:version>1.2</xliffext:version>
      <xliffext:ms.openlocfilehash>43571099727830e81c41416b6fe250dba398b3f8</xliffext:ms.openlocfilehash>
      <xliffext:ms.sourcegitcommit>9d4c7edd0ae2053c37c7d81cdd180b16bf3a9d3b</xliffext:ms.sourcegitcommit>
      <xliffext:ms.lasthandoff>05/15/2019</xliffext:ms.lasthandoff>
      <xliffext:ms.openlocfilepath>articles\retail\orderexchanges.md</xliffext:ms.openlocfilepath>
    </header>
    <body>
      <group extype="content" id="content">
        <trans-unit xml:space="preserve" translate="yes" id="101" restype="x-metadata">
          <source>Configure and process an exchange on a return order</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Configurar e processar uma troca em uma ordem de devolução</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="102" restype="x-metadata">
          <source>This topic explains how to configure an exchange on a return in Microsoft Dynamics 365 for Retail.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Este tópico explica como configurar uma troca em uma devolução no Microsoft Dynamics 365 for Retail.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="103">
          <source>Configure and process an exchange on a return order</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Configurar e processar uma troca em uma ordem de devolução</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="104">
          <source>In previous versions of Microsoft Dynamics 365 for Retail, returns against customer orders were processed by using the return order document in Retail Headquarters.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Em versões anteriores do Microsoft Dynamics 365 for Retail, as devoluções de ordens de clientes eram processadas usando-se o documento de ordem de devolução no Retail Headquarters.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="105">
          <source>However, the return order document can be used to process only products that are being returned.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">No entanto, o documento de ordem de devolução pode ser usado para processar somente os produtos que estão sendo devolvidos.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="106">
          <source>The returned products are indicated by a negative quantity on the return order lines.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Os produtos devolvidos são indicados por uma quantidade negativa nas linhas da ordem de devolução.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="107">
          <source>By contrast, sales are indicated by a positive quantity.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Em contraste, as vendas são indicadas por uma quantidade positiva.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="108">
          <source>However, the return order document doesn't support positive quantities.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Entretanto, o documento de ordem de devolução não suporta quantidades positivas.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="109">
          <source>Because of this limitation, previous versions of Retail didn't support scenarios where product exchanges are done by using the return order document.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Devido a essa limitação, versões anteriores do Retail não oferecem suporte aos cenários em que trocas de produto são feitas usando o documento de ordem de devolução.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="110">
          <source>However, functionality has been added to support scenarios where exchanges are done on return orders.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Entretanto, a funcionalidade foi adicionada para dar suporte a cenários em que as trocas são feitas sobre ordens de devolução.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="111">
          <source>Retail now uses the sales order document instead of the return order document to process these types of transactions.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">O Retail agora usa o documento da ordem de venda em vez do documento da ordem de devolução para processar esses tipos de transações.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="112">
          <source>Configure Retail to support exchanges on return orders</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Configure o Retail para oferecer suporte para trocas sobre ordens de devolução</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="113">
          <source>Follow these steps to configure the system to support exchanges on return orders.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Siga as etapas a seguir para configurar o sistema para dar suporte a trocas sobre ordens de devolução.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="114">
          <source>Go to <bpt id="p1">**</bpt>Retail <ph id="ph1">\&gt;</ph> Headquarters setup <ph id="ph2">\&gt;</ph> Parameters <ph id="ph3">\&gt;</ph> Retail parameters<ept id="p1">**</ept>.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Vá para <bpt id="p1">**</bpt>Varejo <ph id="ph1">\&gt;</ph> Configuração da sede <ph id="ph2">\&gt;</ph> Parâmetros <ph id="ph3">\&gt;</ph> Parâmetros de varejo<ept id="p1">**</ept>.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="115">
          <source>On the <bpt id="p1">**</bpt>Customer orders<ept id="p1">**</ept> FastTab, set the <bpt id="p2">**</bpt>Process return orders as sales orders<ept id="p2">**</ept> option to <bpt id="p3">**</bpt>Yes<ept id="p3">**</ept>.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Na FastTab <bpt id="p1">**</bpt>Ordens de cliente<ept id="p1">**</ept>, defina a opção <bpt id="p2">**</bpt>Processar ordens de devolução como ordens de venda<ept id="p2">**</ept> como <bpt id="p3">**</bpt>Sim<ept id="p3">**</ept>.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="116">
          <source>Run the <bpt id="p1">**</bpt>Global configuration distribution schedule<ept id="p1">**</ept> job (<bpt id="p2">**</bpt>1110<ept id="p2">**</ept>).</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Execute o trabalho <bpt id="p1">**</bpt>Agenda de distribuição global de configuração<ept id="p1">**</ept> (<bpt id="p2">**</bpt>1110<ept id="p2">**</ept>).</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="117">
          <source>Make an exchange</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Fazer uma troca</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="118">
          <source>After the system is configured as described in the previous section, the point of sale (POS) user will still select a sales order or sales invoice to process a return, as in previous versions of Retail.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Depois que o sistema for configurado como descrito na seção anterior, o usuário do PDV (ponto de venda) ainda selecionará uma ordem de venda ou fatura de venda para processar uma devolução, como em versões anteriores do Retail.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="119">
          <source>However, after the return items are added to the cart, the user will be able to add new sales lines to the cart.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">No entanto, depois que os itens de devolução forem adicionados ao carrinho, o usuário poderá adicionar novas linhas de venda ao carrinho.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="120">
          <source>For these new sales lines, the user must define all the attributes that are required in order to process a customer order line.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Para essas novas linhas de venda, o usuário deve definir todos os atributos necessários para processar uma linha da ordem de cliente.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="121">
          <source>These attributes include the delivery method and fulfillment location.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Esses atributos incluem o método de entrega e o local de atendimento.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="122">
          <source>The payment that is due for the transaction will be a net of the return order lines and sales order lines.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">O pagamento que é devido para a transação será um pagamento líquido das linhas da ordem de devolução e das linhas da ordem de venda.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="123">
          <source>When payment is tendered for the transaction, the return order will be posted as a sales order document in Retail Headquarters, and the system will immediately invoice the return lines.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Quando o pagamento for proposto para a transação, a ordem de devolução será lançada como um documento de ordem de venda no Retail Headquarters, e o sistema fará imediatamente o faturamento das linhas de devolução.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="124">
          <source>To provide better visibility into the various amounts for the cart, three new amount fields have been added to the cart.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Para fornecer uma melhor visibilidade dos vários valores do carrinho, três novos campos de valores foram adicionados ao carrinho.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="125">
          <source>You can use the screen designer to make these new fields available in the POS user interface (UI).</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Você pode usar o designer de tela para disponibilizar esses novos campos na IU (interface de usuário) do POS.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="126">
          <source><bpt id="p1">**</bpt>Deposit applied<ept id="p1">**</ept> – The deposit amount that is applied on a transaction when the user does a customer order pickup.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm"><bpt id="p1">**</bpt>Depósito aplicado<ept id="p1">**</ept> – O valor de depósito aplicado em uma transação quando o usuário faz uma retirada por ordem de cliente.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="127">
          <source>If there is no deposit override, and a 10-percent deposit is configured, the amount in this field is 90 percent of the total amount of the customer order.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Se não houver sobreposição de depósito, e um depósito de 10% estiver configurado, o valor neste campo será de 90% do valor total da ordem do cliente.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="128">
          <source><bpt id="p1">**</bpt>Carry out amount<ept id="p1">**</ept> – The total amount for lines where the delivery mode was set to <bpt id="p2">**</bpt>Carry out<ept id="p2">**</ept> when the customer order was created or edited, or during a customer order exchange.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm"><bpt id="p1">**</bpt>Executar valor<ept id="p1">**</ept> – O valor total das linhas em que o modo de entrega foi definido como <bpt id="p2">**</bpt>Executar<ept id="p2">**</ept> quando a ordem de cliente foi criada ou editada, ou durante uma troca da ordem de cliente.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="129">
          <source>The amount in this field includes taxes and charges.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">O valor neste campo inclui impostos e encargos.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="130">
          <source><bpt id="p1">**</bpt>Return amount<ept id="p1">**</ept> – The total amount for lines that have negative quantities during the customer order exchange.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm"><bpt id="p1">**</bpt>Valor da devolução<ept id="p1">**</ept> – O valor total das linhas que têm quantidades negativas durante a troca da ordem do cliente.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="131">
          <source>The amount in this field includes taxes and charges.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">O valor neste campo inclui impostos e encargos.</target></trans-unit>
      </group>
    </body>
  </file>
</xliff>