<?xml version="1.0" encoding="UTF-8"?>
<xliff xmlns:logoport="urn:logoport:xliffeditor:xliff-extras:1.0" xmlns:tilt="urn:logoport:xliffeditor:tilt-non-translatables:1.0" xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xmlns="urn:oasis:names:tc:xliff:document:1.2" xmlns:xliffext="urn:microsoft:content:schema:xliffextensions" version="1.2" xsi:schemaLocation="urn:oasis:names:tc:xliff:document:1.2 xliff-core-1.2-transitional.xsd">
  <file datatype="xml" source-language="en-US" original="Notifications-POS.md" target-language="pt-BR">
    <header>
      <tool tool-company="Microsoft" tool-version="1.0-7889195" tool-name="mdxliff" tool-id="mdxliff"/>
      <xliffext:skl_file_name>Notifications-POS.74d2b9.6c813cfea9b570e8dfd5dbe7f3ca1f4ba8594420.skl</xliffext:skl_file_name>
      <xliffext:version>1.2</xliffext:version>
      <xliffext:ms.openlocfilehash>6c813cfea9b570e8dfd5dbe7f3ca1f4ba8594420</xliffext:ms.openlocfilehash>
      <xliffext:ms.sourcegitcommit>ffc37f7c2a63bada3055f37856a30424040bc9a3</xliffext:ms.sourcegitcommit>
      <xliffext:ms.lasthandoff>05/16/2019</xliffext:ms.lasthandoff>
      <xliffext:ms.openlocfilepath>articles\retail\Notifications-POS.md</xliffext:ms.openlocfilepath>
    </header>
    <body>
      <group extype="content" id="content">
        <trans-unit xml:space="preserve" translate="yes" id="101" restype="x-metadata">
          <source>Show order notifications in the point of sale (POS)</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Mostrar notificações de ordem no ponto de venda (PDV)</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="102" restype="x-metadata">
          <source>This topic describes how to enable order notifications in the point of sale and the notification framework.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Este tópico descreve como habilitar notificações de ordem no ponto de venda e a estrutura de notificação.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="103">
          <source>Show order notifications in the point of sale (POS)</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Mostrar notificações de ordem no ponto de venda (PDV)</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="104">
          <source>In the modern retail environment, store associates are assigned various tasks, such as helping customers, entering transactions, doing stock counts, and receiving orders in the store.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">No ambiente de varejo moderno, são atribuídas várias tarefas aos associados da loja, como auxiliar os clientes, inserir transações, executar contagens de estoque e receber ordens na loja.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="105">
          <source>The point of sale (POS) client provides a single application where associates can perform all these tasks and many others.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">O cliente do ponto de venda (PDV) fornece um único aplicativo no qual os associados podem executar todas essas tarefas e muitas outras.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="106">
          <source>Because various tasks must be performed during the day, associates might have to be notified when something requires their attention.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Como várias tarefas devem ser executadas durante o dia, os associados talvez precisem ser notificados quando algo exigir sua atenção.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="107">
          <source>The notification framework in the POS helps by letting retailers configure role-based notifications.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">A estrutura de notificação no PDV ajuda, permitindo que os varejistas configurem notificações baseadas em funções.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="108">
          <source>In Microsoft Dynamics 365 for Retail with application update 5, these notifications can be configured only for POS operations.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">No Microsoft Dynamics 365 for Retail com a atualização do aplicativo 5, essas notificações podem ser configuradas somente para operações de PDV.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="109">
          <source>Currently, the system can show notifications only for order fulfillment operations.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">No momento, o sistema pode mostrar notificações somente para operações de atendimento da ordem.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="110">
          <source>However, because the framework is designed to be extensible, developers will eventually be able to write a notification handler for any operation and show the notifications for that operation in the POS.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">No entanto, como a estrutura é criada para ser extensível, os desenvolvedores poderão gravar um manipulador de notificação para qualquer operação e mostrar as notificações para essa operação no PDV.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="111">
          <source>Enable notifications for order fulfillment operations</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Habilitar notificações para operações de atendimento da ordem</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="112">
          <source>To enable notifications for order fulfillment operations, follow these steps.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Para habilitar as notificações para operações de atendimento da ordem, siga estas etapas.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="113">
          <source>Go to <bpt id="p1">**</bpt>Retail<ept id="p1">**</ept> <ph id="ph1">&amp;gt;</ph> <bpt id="p2">**</bpt>Channel setup<ept id="p2">**</ept> <ph id="ph2">&amp;gt;</ph> <bpt id="p3">**</bpt>POS setup<ept id="p3">**</ept> <ph id="ph3">&amp;gt;</ph> <bpt id="p4">**</bpt>POS<ept id="p4">**</ept> <ph id="ph4">&amp;gt;</ph> <bpt id="p5">**</bpt>Operations<ept id="p5">**</ept>.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Vá para <bpt id="p1">**</bpt>Varejo<ept id="p1">**</ept> <ph id="ph1">&amp;gt;</ph> <bpt id="p2">**</bpt>Configuração de canal<ept id="p2">**</ept> <ph id="ph2">&amp;gt;</ph> <bpt id="p3">**</bpt>Configuração do PDV<ept id="p3">**</ept> <ph id="ph3">&amp;gt;</ph> <bpt id="p4">**</bpt>PDV<ept id="p4">**</ept> <ph id="ph4">&amp;gt;</ph> <bpt id="p5">**</bpt>Operações<ept id="p5">**</ept>.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="114">
          <source>Search for the <bpt id="p1">**</bpt>Order fulfillment<ept id="p1">**</ept> operation, and select the <bpt id="p2">**</bpt>Enable notifications<ept id="p2">**</ept> check box for it to specify that the notification framework should listen to the handler for this operation.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Procure a operação <bpt id="p1">**</bpt>Atendimento da ordem<ept id="p1">**</ept> e marque a caixa de seleção <bpt id="p2">**</bpt>Habilitar notificações<ept id="p2">**</ept> para que ela especifique que a estrutura de notificação deve detectar o manipulador para essa operação.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="115">
          <source>If the handler is implemented, notifications for this operation will then be shown in the POS.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Se o manipulador for implementado, as notificações para essa operação serão mostradas no PDV.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="116">
          <source>Go to <bpt id="p1">**</bpt>Retail<ept id="p1">**</ept> <ph id="ph1">&amp;gt;</ph> <bpt id="p2">**</bpt>Employees<ept id="p2">**</ept> <ph id="ph2">&amp;gt;</ph> <bpt id="p3">**</bpt>Workers<ept id="p3">**</ept> <ph id="ph3">&amp;gt;</ph>, under Retail tab, open the POS permissions associated with the worker.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Vá para <bpt id="p1">**</bpt>Varejo<ept id="p1">**</ept> <ph id="ph1">&amp;gt;</ph> <bpt id="p2">**</bpt>Funcionários<ept id="p2">**</ept> <ph id="ph2">&amp;gt;</ph> <bpt id="p3">**</bpt>Trabalhadores<ept id="p3">**</ept> <ph id="ph3">&amp;gt;</ph>, na guia Varejo, abra as permissões de PDV associadas ao trabalhador.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="117">
          <source>Expand the <bpt id="p1">**</bpt>Notifications<ept id="p1">**</ept> FastTab, add the <bpt id="p2">**</bpt>Order fulfillment<ept id="p2">**</ept> operation, and set the <bpt id="p3">**</bpt>Display order<ept id="p3">**</ept> field to <bpt id="p4">**</bpt>1<ept id="p4">**</ept>.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Expanda a Guia Rápida <bpt id="p1">**</bpt>Notificações<ept id="p1">**</ept>, adicione a operação <bpt id="p2">**</bpt>Atendimento da ordem<ept id="p2">**</ept> e defina o campo <bpt id="p3">**</bpt>Ordem de exibição<ept id="p3">**</ept> como <bpt id="p4">**</bpt>1<ept id="p4">**</ept>.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="118">
          <source>If more than one notification is configured, this field is used to arrange the notifications.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Se mais de uma notificação for configurada, esse campo será usado para organizar as notificações.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="119">
          <source>Notifications that have a lower <bpt id="p1">**</bpt>Display order<ept id="p1">**</ept> value appear above notifications that have a higher value.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">As notificações que têm um valor de <bpt id="p1">**</bpt>Ordem de exibição<ept id="p1">**</ept> mais baixo aparecem acima das notificações que têm um valor mais alto.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="120">
          <source>Notifications that have a <bpt id="p1">**</bpt>Display order<ept id="p1">**</ept> value of <bpt id="p2">**</bpt>1<ept id="p2">**</ept> are at the top.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">As notificações em que o valor de <bpt id="p1">**</bpt>Ordem de exibição<ept id="p1">**</ept> é <bpt id="p2">**</bpt>1<ept id="p2">**</ept> aparecem na parte superior.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="121">
          <source>Notifications are shown only for operations that are added on the <bpt id="p1">**</bpt>Notifications<ept id="p1">**</ept> FastTab, and you can add operations there only if the <bpt id="p2">**</bpt>Enable notifications<ept id="p2">**</ept> check box for those operations has been selected on the <bpt id="p3">**</bpt>POS operations<ept id="p3">**</ept> page.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">As notificações são mostradas somente para operações adicionadas na Guia Rápida <bpt id="p1">**</bpt>Notificações<ept id="p1">**</ept>, e você só poderá adicionar operações lá se a caixa de seleção <bpt id="p2">**</bpt>Habilitar notificações<ept id="p2">**</ept> para essas operações tiver sido selecionada na página <bpt id="p3">**</bpt>Operações de PDV<ept id="p3">**</ept>.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="122">
          <source>Additionally, notifications for an operation are shown to workers only if the operation is added to the POS permissions for those workers.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Além disso, as notificações para uma operação são mostradas aos trabalhadores somente se a operação for adicionada às permissões de PDV para esses trabalhadores.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="123">
          <source>Notifications can be overridden at the user level.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">As notificações podem ser substituídas no nível do usuário.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="124">
          <source>Open the worker's record, select <bpt id="p1">**</bpt>POS permissions<ept id="p1">**</ept>, and then edit the user's notification subscription.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Abra o registro do trabalhador, selecione <bpt id="p1">**</bpt>Permissões do PDV<ept id="p1">**</ept> e, em seguida, edite a subscrição de notificação do usuário.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="125">
          <source>Go to <bpt id="p1">**</bpt>Retail<ept id="p1">**</ept> <ph id="ph1">&amp;gt;</ph> <bpt id="p2">**</bpt>Channel setup<ept id="p2">**</ept> <ph id="ph2">&amp;gt;</ph> <bpt id="p3">**</bpt>POS setup<ept id="p3">**</ept> <ph id="ph3">&amp;gt;</ph> <bpt id="p4">**</bpt>POS profiles<ept id="p4">**</ept> <ph id="ph4">&amp;gt;</ph> <bpt id="p5">**</bpt>Functionality profiles<ept id="p5">**</ept>.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Vá para <bpt id="p1">**</bpt>Varejo<ept id="p1">**</ept> <ph id="ph1">&amp;gt;</ph> <bpt id="p2">**</bpt>Configuração de canal<ept id="p2">**</ept> <ph id="ph2">&amp;gt;</ph> <bpt id="p3">**</bpt>Configuração do PDV<ept id="p3">**</ept> <ph id="ph3">&amp;gt;</ph> <bpt id="p4">**</bpt>Perfis de PDV<ept id="p4">**</ept> <ph id="ph4">&amp;gt;</ph> <bpt id="p5">**</bpt>Perfis de funcionalidade<ept id="p5">**</ept>.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="126">
          <source>In the <bpt id="p1">**</bpt>Notification interval<ept id="p1">**</ept> field, specify how often notifications should be pulled.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">No campo <bpt id="p1">**</bpt>Intervalo de notificação<ept id="p1">**</ept>, especifique a frequência de recebimento de notificações.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="127">
          <source>For some notifications, the POS must make real-time calls to the back-office application.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Para algumas notificações, o PDV deve fazer chamadas em tempo real para o aplicativo de back office.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="128">
          <source>These calls consume the compute capacity of your back-office application.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Essas chamadas consomem a capacidade de computação do seu aplicativo de back office.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="129">
          <source>Therefore, when you set the notification interval, you should consider both your business requirements and the impact of real-time calls to the back-office application.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Portanto, ao definir o intervalo de notificação, você deve considerar suas necessidades comerciais e o impacto de chamadas em tempo real no aplicativo de back office.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="130">
          <source>A value of <bpt id="p1">**</bpt>0<ept id="p1">**</ept> (zero) turns off notifications.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Um valor de <bpt id="p1">**</bpt>0<ept id="p1">**</ept> (zero) desativa as notificações.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="131">
          <source>Go to <bpt id="p1">**</bpt>Retail<ept id="p1">**</ept> <ph id="ph1">&amp;gt;</ph> <bpt id="p2">**</bpt>Retail IT<ept id="p2">**</ept> <ph id="ph2">&amp;gt;</ph> <bpt id="p3">**</bpt>Distribution schedule<ept id="p3">**</ept>.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Vá para <bpt id="p1">**</bpt>Varejo<ept id="p1">**</ept> <ph id="ph1">&amp;gt;</ph> <bpt id="p2">**</bpt>TI de varejo<ept id="p2">**</ept> <ph id="ph2">&amp;gt;</ph> <bpt id="p3">**</bpt>Agenda de distribuição<ept id="p3">**</ept>.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="132">
          <source>Select the <bpt id="p1">**</bpt>1060<ept id="p1">**</ept> (<bpt id="p2">**</bpt>Staff<ept id="p2">**</ept>) schedule to synchronize notification subscription settings, and then select <bpt id="p3">**</bpt>Run now<ept id="p3">**</ept>.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Selecione a agenda <bpt id="p1">**</bpt>1060<ept id="p1">**</ept> (<bpt id="p2">**</bpt>Equipe<ept id="p2">**</ept>) para sincronizar as configurações de subscrição de notificação e, em seguida, selecione <bpt id="p3">**</bpt>Executar agora<ept id="p3">**</ept>.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="133">
          <source>Next, select the <bpt id="p1">**</bpt>1070<ept id="p1">**</ept> (<bpt id="p2">**</bpt>Channel configuration<ept id="p2">**</ept>) schedule to synchronize the permission interval, and then select <bpt id="p3">**</bpt>Run now<ept id="p3">**</ept>.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Em seguida, selecione a agenda <bpt id="p1">**</bpt>1070<ept id="p1">**</ept> (<bpt id="p2">**</bpt>Configuração do canal<ept id="p2">**</ept>) para sincronizar o intervalo de permissão e, em seguida, selecione <bpt id="p3">**</bpt>Executar agora<ept id="p3">**</ept>.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="134">
          <source>View notifications in the POS</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Exibir notificações no PDV</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="135">
          <source>After you complete the preceding steps, the workers will be able to view the notifications in the POS.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Depois que você concluir as etapas anteriores, os trabalhadores poderão exibir as notificações no PDV.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="136">
          <source>To view notifications, press the notification icon in the top right corner of the POS.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Para exibir as notificações, pressione o ícone de notificação no canto superior direito do PDV.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="137">
          <source>A notification center appears and shows notifications for the order fulfillment operation.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Um centro de notificações aparecerá e mostrará as notificações para a operação de atendimento da ordem.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="138">
          <source>The notification center should show the following groups in the order fulfillment operation:</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">O centro de notificações deve mostrar os seguintes grupos na operação de atendimento da ordem:</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="139">
          <source><bpt id="p1">**</bpt>Store pickup<ept id="p1">**</ept> – This group shows the count of orders that have a delivery mode of <bpt id="p2">**</bpt>Pickup<ept id="p2">**</ept>, and that are scheduled for pickup from the current store.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm"><bpt id="p1">**</bpt>Retirada na loja<ept id="p1">**</ept> – Este grupo mostra a contagem de ordens que têm o modo de entrega <bpt id="p2">**</bpt>Retirada<ept id="p2">**</ept> e cuja retirada está agendada na loja atual.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="140">
          <source>You can press the number on the group to open the <bpt id="p1">**</bpt>Order fulfillment<ept id="p1">**</ept> page.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Você pode pressionar o número no grupo para abrir a página <bpt id="p1">**</bpt>Atendimento da ordem<ept id="p1">**</ept>.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="141">
          <source>In this case, the page will be filtered so that it shows only the active orders that are set up for pickup from the current store.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Nesse caso, a página será filtrada para mostrar somente as ordens ativas configuradas para retirada na loja atual.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="142">
          <source><bpt id="p1">**</bpt>Ship from store<ept id="p1">**</ept> – This group shows the count of orders that have the delivery mode of <bpt id="p2">**</bpt>Shipping<ept id="p2">**</ept>, and that are scheduled for shipment from the current store.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm"><bpt id="p1">**</bpt>Remeter da loja<ept id="p1">**</ept> – Este grupo mostra a contagem de ordens que têm o modo de entrega <bpt id="p2">**</bpt>Remessa<ept id="p2">**</ept> e cuja remessa está agendada na loja atual.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="143">
          <source>You can press the number on the group to open the <bpt id="p1">**</bpt>Order fulfillment<ept id="p1">**</ept> page.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Você pode pressionar o número no grupo para abrir a página <bpt id="p1">**</bpt>Atendimento da ordem<ept id="p1">**</ept>.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="144">
          <source>In this case, the page will be filtered so that it shows only the active orders that are set up for shipment from the current store.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Nesse caso, a página será filtrada para mostrar somente as ordens ativas configuradas para remessa da loja atual.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="145">
          <source>When new orders are assigned to the store for fulfillment, the notification icon changes to indicate that there are new notifications, and the count for the appropriate groups is updated.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Quando novas ordens são atribuídas à loja para o atendimento, o ícone de notificação é alterado para indicar que há novas notificações, e a contagem dos grupos apropriados é atualizada.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="146">
          <source>Even though the groups are refreshed at regular intervals however, POS users can manually refresh the groups at any time by selecting the <bpt id="p1">**</bpt>Refresh<ept id="p1">**</ept> button next to the group.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Embora os grupos sejam atualizados em intervalos regulares, os usuários do PDV podem atualizá-los manualmente a qualquer momento selecionando o botão <bpt id="p1">**</bpt>Atualizar<ept id="p1">**</ept> ao lado do grupo.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="147">
          <source>Lastly, if a group has a new item, that the current worker hasn't viewed, then the group shows a burst symbol to indicate new content.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Por fim, se um grupo tiver um novo item, que o trabalhador atual não viu, então o grupo mostrará um símbolo intermitente para indicar o novo conteúdo.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="148">
          <source>Enable live content on POS buttons</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Habilitar conteúdo ao vivo nos botões do PDV</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="149">
          <source>POS buttons can now show a count to help workers easily determine which tasks require their immediate attention.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Os botões do PDV agora podem mostrar uma contagem para ajudar os trabalhadores a determinar facilmente quais tarefas exigem a sua atenção imediata.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="150">
          <source>To show this number on a POS button, you must complete the notification setup that is described earlier in this topic (that is, you must enable notifications for an operation, set up a notification interval, and update the POS permission group for the worker).</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Para mostrar esse número em um botão do PDV, você deve concluir a configuração de notificação descrita anteriormente neste tópico (isto é, você deve habilitar as notificações para uma operação, configurar um intervalo de notificação e atualizar o grupo de permissões de PDV para o trabalhador).</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="151">
          <source>Additionally, you must open the button grid designer, view the button's properties, and select the <bpt id="p1">**</bpt>Enable live content<ept id="p1">**</ept> check box.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Além disso, você deve abrir o designer da grade de botões, exibir as propriedades do botão e marcar a caixa de seleção <bpt id="p1">**</bpt>Habilitar conteúdo ao vivo<ept id="p1">**</ept>.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="152">
          <source>In the <bpt id="p1">**</bpt>Content alignment<ept id="p1">**</ept> field, you can select whether the count appears in the upper-right corner of the button (<bpt id="p2">**</bpt>Top right<ept id="p2">**</ept>) or in the center (<bpt id="p3">**</bpt>Center<ept id="p3">**</ept>).</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">No campo <bpt id="p1">**</bpt>Alinhamento de conteúdo<ept id="p1">**</ept>, você pode selecionar se a contagem será exibida no canto superior direito do botão (<bpt id="p2">**</bpt>Superior direito<ept id="p2">**</ept>) ou no centro (<bpt id="p3">**</bpt>Centralizado<ept id="p3">**</ept>).</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="153">
          <source>The live content can be enabled for operations only if the <bpt id="p1">**</bpt>Enable notifications<ept id="p1">**</ept> check box has been selected for them on the <bpt id="p2">**</bpt>POS operations<ept id="p2">**</ept> page, as described earlier in this topic.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">O conteúdo ao vivo poderá ser habilitado para operações somente se a caixa de seleção <bpt id="p1">**</bpt>Habilitar notificações<ept id="p1">**</ept> tiver sido selecionada para elas na página <bpt id="p2">**</bpt>Operações de PDV<ept id="p2">**</ept>, conforme descrito anteriormente neste tópico.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="154">
          <source>The following illustration shows the live content settings in the button grid designer.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">A ilustração a seguir mostra as configurações de conteúdo ao vivo no designer da grade de botões.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="155">
          <source><bpt id="p1">![</bpt>Live content settings in the button grid designer<ept id="p1">]</ept><bpt id="p2">(./media/ButtonGridDesigner.png "</bpt>Live content settings in the button grid designer<ept id="p2">")</ept></source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm"><bpt id="p1">![</bpt>Configurações de conteúdo ao vivo no designer da grade de botões<ept id="p1">]</ept><bpt id="p2">(./media/ButtonGridDesigner.png "</bpt>Configurações de conteúdo ao vivo no designer da grade de botões<ept id="p2">")</ept></target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="156">
          <source>To show the notification count on a button, you need to ensure that the correct screen layout is being updated.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Para mostrar a contagem de notificação em um botão, você deve garantir que o layout de tela correto está sendo atualizado.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="157">
          <source>To determine the screen layout that is being used by the POS, select the <bpt id="p1">**</bpt>Settings<ept id="p1">**</ept> icon in upper-right corner and note the <bpt id="p2">**</bpt>Screen layout ID<ept id="p2">**</ept> and <bpt id="p3">**</bpt>Layout resolution<ept id="p3">**</ept>.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">Para determinar o layout de tela que está sendo usado pelo POS, selecione o ícone <bpt id="p1">**</bpt>Configurações<ept id="p1">**</ept> no canto superior direito e anote a <bpt id="p2">**</bpt>ID de layout de tela<ept id="p2">**</ept> e <bpt id="p3">**</bpt>Resolução de tela<ept id="p3">**</ept>.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="158">
          <source>Now using Edge browser, go to the <bpt id="p1">**</bpt>Screen layout<ept id="p1">**</ept> page in Dynamics 365 for Finance and Operations, find the <bpt id="p2">**</bpt>Screen layout ID<ept id="p2">**</ept> and <bpt id="p3">**</bpt>Layout resolution<ept id="p3">**</ept> identified above and select the <bpt id="p4">**</bpt>Enable live content<ept id="p4">**</ept> check box.</source>
        <target logoport:matchpercent="100" state="translated" state-qualifier="leveraged-tm">Agora, usando o navegador Edge, vá para a página <bpt id="p1">**</bpt>Layout de tela<ept id="p1">**</ept> no Dynamics 365 for Finance and Operations, encontre a <bpt id="p2">**</bpt>ID de layout de tela<ept id="p2">**</ept> e <bpt id="p3">**</bpt>Resolução de layout<ept id="p3">**</ept> identificadas acima e marque a caixa de seleção <bpt id="p4">**</bpt>Habilitar conteúdo ao vivo<ept id="p4">**</ept>.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="159">
          <source>Go to <bpt id="p1">**</bpt>Retail <ph id="ph1">\&gt;</ph> Retail IT <ph id="ph2">\&gt;</ph> Distribution schedule<ept id="p1">**</ept> and run the 1090 (Registers) job to synchronize layout changes.</source><target logoport:matchpercent="98" state="translated" state-qualifier="fuzzy-match">Vá para <bpt id="p1">**</bpt>Varejo <ph id="ph1">\&gt;</ph> TI de Varejo <ph id="ph2">\&gt;</ph> Agenda de distribuição<ept id="p1">**</ept> e execute o trabalho 1090 (Registros) para sincronizar as alterações de layout.</target>
        </trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="160">
          <source><bpt id="p1">![</bpt>Find the screen layout used by POS<ept id="p1">]</ept><bpt id="p2">(./media/Choose_screen_layout.png "</bpt>Find the screen layout <ept id="p2">")</ept></source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm"><bpt id="p1">![</bpt>Encontrar o layout de tela usado pelo POS<ept id="p1">]</ept><bpt id="p2">(./media/Choose_screen_layout.png "</bpt>Encontrar o layout de tela<ept id="p2">")</ept></target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="161">
          <source>The following illustration shows the effect of selecting <bpt id="p1">**</bpt>Top right<ept id="p1">**</ept> versus <bpt id="p2">**</bpt>Center<ept id="p2">**</ept> in the <bpt id="p3">**</bpt>Content alignment<ept id="p3">**</ept> field for buttons of various sizes.</source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm">A ilustração a seguir mostra o efeito de selecionar <bpt id="p1">**</bpt>Superior direito<ept id="p1">**</ept> versus <bpt id="p2">**</bpt>Centralizado<ept id="p2">**</ept> no campo <bpt id="p3">**</bpt>Alinhamento de conteúdo<ept id="p3">**</ept> para botões de vários tamanhos.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="162">
          <source><bpt id="p1">![</bpt>Live content on POS buttons<ept id="p1">]</ept><bpt id="p2">(./media/ButtonsWithLiveContent.png "</bpt>Live content on POS buttons<ept id="p2">")</ept></source>
        <target logoport:matchpercent="101" state="translated" state-qualifier="leveraged-tm"><bpt id="p1">![</bpt>Conteúdo ao vivo nos botões do PDV<ept id="p1">]</ept><bpt id="p2">(./media/ButtonsWithLiveContent.png "</bpt>Conteúdo ao vivo nos botões do PDV<ept id="p2">")</ept></target></trans-unit>
      </group>
    </body>
  </file>
</xliff>