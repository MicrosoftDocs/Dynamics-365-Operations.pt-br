<?xml version="1.0" encoding="UTF-8"?>
<xliff xmlns:logoport="urn:logoport:xliffeditor:xliff-extras:1.0" xmlns:tilt="urn:logoport:xliffeditor:tilt-non-translatables:1.0" xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xmlns="urn:oasis:names:tc:xliff:document:1.2" xmlns:xliffext="urn:microsoft:content:schema:xliffextensions" version="1.2" xsi:schemaLocation="urn:oasis:names:tc:xliff:document:1.2 xliff-core-1.2-transitional.xsd">
  <file datatype="xml" source-language="en-US" original="custom-fields-mobile.md" target-language="pt-BR">
    <header>
      <tool tool-company="Microsoft" tool-version="1.0-d915bc8" tool-name="mdxliff" tool-id="mdxliff"/>
      <xliffext:skl_file_name>custom-fields-mobile.2a9e5e.4343c875da05641c57b7784bf52f1c814dd26d20.skl</xliffext:skl_file_name>
      <xliffext:version>1.2</xliffext:version>
      <xliffext:ms.openlocfilehash>4343c875da05641c57b7784bf52f1c814dd26d20</xliffext:ms.openlocfilehash>
      <xliffext:ms.sourcegitcommit>19859d8566a8c7840066b2c10c6b08b67f1b83f4</xliffext:ms.sourcegitcommit>
      <xliffext:ms.lasthandoff>06/04/2019</xliffext:ms.lasthandoff>
      <xliffext:ms.openlocfilepath>articles\financials\project-management\custom-fields-mobile.md</xliffext:ms.openlocfilepath>
    </header>
    <body>
      <group extype="content" id="content">
        <trans-unit xml:space="preserve" translate="yes" id="101" restype="x-metadata">
          <source>Implement custom fields for the Microsoft Dynamics 365 Project Timesheet mobile app on iOS and Android</source><target logoport:matchpercent="0" state="translated">Implementar campos personalizados para o aplicativo móvel do Microsoft Dynamics 365 Project Timesheet no iOS e Android</target>
        </trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="102" restype="x-metadata">
          <source>This topic provides common patterns for using extensions to implement custom fields.</source><target logoport:matchpercent="0" state="translated">Este tópico fornece padrões comuns para o uso de extensões para implementar campos personalizados.</target>
        </trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="103">
          <source>Implement custom fields for the Microsoft Dynamics 365 Project Timesheet mobile app on iOS and Android</source>
        <target logoport:matchpercent="0" state="translated" state-qualifier="leveraged-inherited">Implementar campos personalizados para o aplicativo móvel do Microsoft Dynamics 365 Project Timesheet no iOS e Android</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="104">
          <source>This topic provides common patterns for using extensions to implement custom fields.</source>
        <target logoport:matchpercent="0" state="translated" state-qualifier="leveraged-inherited">Este tópico fornece padrões comuns para o uso de extensões para implementar campos personalizados.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="105">
          <source>The following topics are covered:</source><target logoport:matchpercent="82" state="translated" state-qualifier="fuzzy-match">Os tópicos a seguir estão cobertos:</target>
        </trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="106">
          <source>The various data types that the custom field framework supports</source><target logoport:matchpercent="0" state="translated">Os vários tipos de dados a que a estrutura de campo personalizado oferece suporte</target>
        </trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="107">
          <source>How to show read-only or editable fields on timesheet entries, and save user-provided values back to the database</source><target logoport:matchpercent="0" state="translated">Como mostrar campos somente leitura ou editáveis nas entradas de folha de ponto e salvar os valores fornecidos pelo usuário no banco de dados</target>
        </trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="108">
          <source>How to show read-only fields on the timesheet header</source><target logoport:matchpercent="0" state="translated">Como mostrar campos somente leitura no cabeçalho de folha de ponto</target>
        </trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="109">
          <source>How to integrate other custom business logic to enter default values in fields and do additional validation</source><target logoport:matchpercent="0" state="translated">Como integrar outra lógica de negócios personalizada para inserir valores padrão em campos e fazer uma validação adicional</target>
        </trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="110">
          <source>Audience</source>
        <target logoport:matchpercent="100" state="translated" state-qualifier="leveraged-tm">Público-alvo</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="111">
          <source>This topic is intended for developers who are integrating their custom fields into the Microsoft Dynamics 365 Project Timesheet mobile application that is available for Apple iOS and Google Android.</source><target logoport:matchpercent="0" state="translated">Este tópico é destinado a desenvolvedores que estão integrando seus campos personalizados no aplicativo móvel do Microsoft Dynamics 365 Project Timesheet que está disponível para Apple iOS e Google Android.</target>
        </trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="112">
          <source>The assumption is that readers are familiar with X++ development and project timesheet functionality.</source><target logoport:matchpercent="0" state="translated">A suposição é que os leitores estão familiarizados com o desenvolvimento do X ++ e a funcionalidade de folha de ponto do projeto.</target>
        </trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="113">
          <source>Data contract – TSTimesheetCustomField X++ class</source><target logoport:matchpercent="0" state="translated">Contrato dos dados – Classe TSTimesheetCustomField X++</target>
        </trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="114">
          <source>The <bpt id="p1">**</bpt>TSTimesheetCustomField<ept id="p1">**</ept> class is the X++ data contract class that represents information about a custom field for timesheet functionality.</source><target logoport:matchpercent="0" state="translated">A classe <bpt id="p1">**</bpt>TSTimesheetCustomField<ept id="p1">**</ept> é a classe de contrato de dados X++ que representa informações sobre um campo personalizado para a funcionalidade de folha de ponto.</target>
        </trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="115">
          <source>Lists of the custom field objects are passed on both the TSTimesheetDetails data contract and the TSTimesheetEntry data contract to show custom fields in the mobile app.</source><target logoport:matchpercent="0" state="translated">As listas dos objetos de campo personalizados são transmitidas no contrato de dados TSTimesheetDetails e no contrato de dados TSTimesheetEntry para mostrar campos personalizados no aplicativo móvel.</target>
        </trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="116">
          <source><bpt id="p1">**</bpt>TSTimesheetDetails<ept id="p1">**</ept> - The timesheet header contract.</source><target logoport:matchpercent="0" state="translated"><bpt id="p1">**</bpt>TSTimesheetDetails<ept id="p1">**</ept> - O contrato de cabeçalho da folha de ponto.</target>
        </trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="117">
          <source><bpt id="p1">**</bpt>TSTimesheetEntry<ept id="p1">**</ept> - The timesheet transaction contract.</source><target logoport:matchpercent="0" state="translated"><bpt id="p1">**</bpt>TSTimesheetEntry<ept id="p1">**</ept> - O contrato da transação da folha de ponto.</target>
        </trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="118">
          <source>Groups of these objects that have the same project information and <bpt id="p1">**</bpt>timesheetLineRecId<ept id="p1">**</ept> value constitute a line.</source><target logoport:matchpercent="0" state="translated">Grupos desses objetos com as mesmas informações do projeto e o valor <bpt id="p1">**</bpt>timesheetLineRecId<ept id="p1">**</ept> constituem uma linha.</target>
        </trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="119">
          <source>fieldBaseType (Types)</source><target logoport:matchpercent="0" state="translated">fieldBaseType (tipos)</target>
        </trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="120">
          <source>The <bpt id="p1">**</bpt>FieldBaseType<ept id="p1">**</ept> property on the <bpt id="p2">**</bpt>TsTimesheetCustom<ept id="p2">**</ept> object determines the type of the field that appears in the app.</source><target logoport:matchpercent="0" state="translated">A propriedade <bpt id="p1">**</bpt>FieldBaseType<ept id="p1">**</ept> no objeto <bpt id="p2">**</bpt>TsTimesheetCustom<ept id="p2">**</ept> determina o tipo do campo exibido no aplicativo.</target>
        </trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="121">
          <source>The following <bpt id="p1">**</bpt>Types<ept id="p1">**</ept> values that are supported.</source><target logoport:matchpercent="0" state="translated">Os valores <bpt id="p1">**</bpt>Tipos<ept id="p1">**</ept> a seguir que são compatíveis.</target>
        </trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="122">
          <source>Types value</source><target logoport:matchpercent="81" state="translated" state-qualifier="fuzzy-match">Tipos de valor</target>
        </trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="123">
          <source>Type</source>
        <target logoport:matchpercent="100" state="translated" state-qualifier="leveraged-tm">Tipo</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="124">
          <source>Notes</source>
        <target logoport:matchpercent="100" state="translated" state-qualifier="leveraged-tm">Observação</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="125">
          <source>0</source>
        <target logoport:matchpercent="100" state="translated" state-qualifier="leveraged-tm">0</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="126">
          <source>String (and Enum)</source><target logoport:matchpercent="0" state="translated">Sequência de caracteres (e enumeração)</target>
        </trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="127">
          <source>The field appears as a text field.</source><target logoport:matchpercent="0" state="translated">O campo aparece como um campo de texto.</target>
        </trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="128">
          <source>1</source>
        <target logoport:matchpercent="100" state="translated" state-qualifier="leveraged-tm">1</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="129">
          <source>Integer</source>
        <target logoport:matchpercent="100" state="translated" state-qualifier="leveraged-tm">Inteiro</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="130">
          <source>The value is shown as a number without decimal places.</source><target logoport:matchpercent="0" state="translated">O valor é mostrado como um número sem casas decimais.</target>
        </trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="131">
          <source>2</source>
        <target logoport:matchpercent="100" state="translated" state-qualifier="leveraged-tm">2</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="132">
          <source>Real</source>
        <target logoport:matchpercent="100" state="translated" state-qualifier="leveraged-tm">Real</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="133">
          <source>The value is shown as a number that has decimal places.</source><target logoport:matchpercent="84" state="translated" state-qualifier="fuzzy-match">O valor é mostrado como um número com casas decimais.</target>
        </trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="134">
          <source>To show the real value as a currency in the app, use the <bpt id="p1">**</bpt>fieldExtenededType<ept id="p1">**</ept> property.</source><target logoport:matchpercent="0" state="translated">Para mostrar o valor real como uma moeda no aplicativo, use a propriedade <bpt id="p1">**</bpt>fieldExtenededType<ept id="p1">**</ept>.</target>
        </trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="135">
          <source>You can use the <bpt id="p1">**</bpt>numberOfDecimals<ept id="p1">**</ept> property to set the number of decimal places that are shown.</source><target logoport:matchpercent="0" state="translated">Você pode usar a propriedade <bpt id="p1">**</bpt>numberOfDecimals<ept id="p1">**</ept> para definir o número de casas decimais exibidas.</target>
        </trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="136">
          <source>3</source>
        <target logoport:matchpercent="100" state="translated" state-qualifier="leveraged-tm">3</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="137">
          <source>Date</source>
        <target logoport:matchpercent="100" state="translated" state-qualifier="leveraged-tm">Data</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="138">
          <source>Date formats are determined by the user's <bpt id="p1">**</bpt>Date, times, and number format<ept id="p1">**</ept> setting that is specified under <bpt id="p2">**</bpt>Language and country/region preference<ept id="p2">**</ept> in <bpt id="p3">**</bpt>User options<ept id="p3">**</ept>.</source><target logoport:matchpercent="0" state="translated">Os formatos de data são determinados pelo formato <bpt id="p1">**</bpt>Formato de data, hora e número<ept id="p1">**</ept> do usuário, que é especificado em <bpt id="p2">**</bpt>Preferências de idioma e país/região<ept id="p2">**</ept> de <bpt id="p3">**</bpt>Opções do usuário<ept id="p3">**</ept>.</target>
        </trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="139">
          <source>4</source>
        <target logoport:matchpercent="100" state="translated" state-qualifier="leveraged-tm">4</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="140">
          <source>Boolean</source>
        <target logoport:matchpercent="100" state="translated" state-qualifier="leveraged-tm">Booleano</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="141">
          <source>15</source>
        <target logoport:matchpercent="100" state="translated" state-qualifier="leveraged-tm">15</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="142">
          <source>GUID</source>
        <target logoport:matchpercent="100" state="translated" state-qualifier="leveraged-tm">GUID</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="143">
          <source>16</source>
        <target logoport:matchpercent="100" state="translated" state-qualifier="leveraged-tm">16</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="144">
          <source>Int64</source><target logoport:matchpercent="0" state="translated">Int64</target>
        </trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="145">
          <source>If the <bpt id="p1">**</bpt>stringOptions<ept id="p1">**</ept> property isn't provided on the <bpt id="p2">**</bpt>TSTimesheetCustomField<ept id="p2">**</ept> object, a free-text field is provided to the user.</source><target logoport:matchpercent="0" state="translated">Se a propriedade <bpt id="p1">**</bpt>stringOptions<ept id="p1">**</ept> não for fornecida no objeto <bpt id="p2">**</bpt>TSTimesheetCustomField<ept id="p2">**</ept>, um campo de texto livre é fornecido ao usuário.</target>
        </trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="146">
          <source>The <bpt id="p1">**</bpt>stringLength<ept id="p1">**</ept> property can be used to set the maximum string length that users can enter.</source><target logoport:matchpercent="0" state="translated">A propriedade <bpt id="p1">**</bpt>stringLength<ept id="p1">**</ept> pode ser usada para definir o comprimento máximo de sequência de caracteres que os usuários poderão inserir.</target>
        </trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="147">
          <source>If the <bpt id="p1">**</bpt>stringOptions<ept id="p1">**</ept> property is provided on the <bpt id="p2">**</bpt>TSTimesheetCustomField<ept id="p2">**</ept> object, those list elements are the only values that users can select by using option buttons (radio buttons).</source><target logoport:matchpercent="0" state="translated">Se a propriedade <bpt id="p1">**</bpt>stringOptions<ept id="p1">**</ept> for fornecida no objeto <bpt id="p2">**</bpt>TSTimesheetCustomField<ept id="p2">**</ept>, esses elementos da lista são os únicos valores que os usuários podem selecionar usando os botões de opção.</target>
        </trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="148">
          <source>In this case, the string field can act as an enum value for the purpose of user entry.</source><target logoport:matchpercent="0" state="translated">Nesse caso, o campo de sequência de caracteres pode atuar como um valor de enumeração para fins de entrada do usuário.</target>
        </trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="149">
          <source>To save the value to the database as an enum, manually map the string value back to the enum value before you save to the database by using chain of command (see the “Use chain of command on the TSTimesheetEntryService class to save a timesheet entry from the app back to the database” section later in this topic for an example).</source><target logoport:matchpercent="0" state="translated">Para salvar o valor no banco de dados como uma enumeração, mapeie manualmente o valor da sequência para o valor de enumeração antes de salvar no banco de dados usando a cadeia de comando (consulte “Usar cadeia de comando na classe TSTimesheetEntryService para salvar uma entrada de folha de ponto do aplicativo ao banco de dados” posteriormente neste tópico para obter um exemplo).</target>
        </trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="150">
          <source>fieldExtendedType (TSCustomFieldExtendedType)</source><target logoport:matchpercent="0" state="translated">fieldExtendedType (TSCustomFieldExtendedType)</target>
        </trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="151">
          <source>You can use this property to format real values as currency.</source><target logoport:matchpercent="0" state="translated">Você pode usar essa propriedade para formatar valores reais como moeda.</target>
        </trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="152">
          <source>This approach is applicable only when the <bpt id="p1">**</bpt>fieldBaseType<ept id="p1">**</ept> value is <bpt id="p2">**</bpt>Real<ept id="p2">**</ept>.</source><target logoport:matchpercent="0" state="translated">Essa abordagem é aplicável somente quando o valor <bpt id="p1">**</bpt>fieldBaseType<ept id="p1">**</ept> é <bpt id="p2">**</bpt>Real<ept id="p2">**</ept>.</target>
        </trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="153">
          <source><bpt id="p1">**</bpt>TSCustomFieldExtendedType:None<ept id="p1">**</ept> – No formatting is applied.</source><target logoport:matchpercent="0" state="translated"><bpt id="p1">**</bpt>TSCustomFieldExtendedType:None<ept id="p1">**</ept> – Nenhuma formatação é aplicada.</target>
        </trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="154">
          <source><bpt id="p1">**</bpt>TSCustomFieldExtendedType::Currency<ept id="p1">**</ept> – Format the value as currency.</source><target logoport:matchpercent="0" state="translated"><bpt id="p1">**</bpt>TSCustomFieldExtendedType::Moeda<ept id="p1">**</ept> – Formate o valor como moeda.</target>
        </trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="155">
          <source>When currency formatting is active, the <bpt id="p1">**</bpt>stringValue<ept id="p1">**</ept> field can be used pass the currency code that should be shown in the app.</source><target logoport:matchpercent="0" state="translated">Quando a formatação da moeda está ativa, o campo <bpt id="p1">**</bpt>stringValue<ept id="p1">**</ept> pode ser usado para passar o código da moeda que deve ser exibido no aplicativo.</target>
        </trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="156">
          <source>The value is a read-only value.</source><target logoport:matchpercent="0" state="translated">O valor é um valor somente leitura.</target>
        </trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="157">
          <source>The <bpt id="p1">**</bpt>realValue<ept id="p1">**</ept> field contains the money amount that should be saved to the database.</source><target logoport:matchpercent="0" state="translated">O campo <bpt id="p1">**</bpt>realValue<ept id="p1">**</ept> contém o valor monetário que deve ser salvo no banco de dados.</target>
        </trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="158">
          <source>fieldSection (TSCustomFieldSection)</source><target logoport:matchpercent="0" state="translated">fieldSection (TSCustomFieldSection)</target>
        </trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="159">
          <source>You can use this property specify where the custom field should appear in the app.</source><target logoport:matchpercent="0" state="translated">É possível usar essa propriedade para especificar onde o campo personalizado deve aparecer no aplicativo.</target>
        </trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="160">
          <source><bpt id="p1">**</bpt>TSCustomFieldSection::Header<ept id="p1">**</ept> – The field will appear in the <bpt id="p2">**</bpt>View more details<ept id="p2">**</ept> section in the app.</source><target logoport:matchpercent="0" state="translated"><bpt id="p1">**</bpt>TSCustomFieldSection::Cabeçalho<ept id="p1">**</ept> – O campo aparecerá na seção <bpt id="p2">**</bpt>Exibir mais detalhes<ept id="p2">**</ept> no aplicativo.</target>
        </trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="161">
          <source>These fields are always read-only.</source><target logoport:matchpercent="0" state="translated">Esses campos são sempre somente leitura.</target>
        </trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="162">
          <source><bpt id="p1">**</bpt>TSCustomFieldSection::Line<ept id="p1">**</ept> – The field will appear after all the out-of-box line fields on timesheet entries.</source><target logoport:matchpercent="0" state="translated"><bpt id="p1">**</bpt>TSCustomFieldSection::Linha<ept id="p1">**</ept> – O campo aparecerá depois de todos os campos da linha pronta para uso nas entradas de folha de ponto.</target>
        </trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="163">
          <source>These fields can be either editable or read-only.</source><target logoport:matchpercent="0" state="translated">Esses campos podem ser editáveis ou somente leitura.</target>
        </trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="164">
          <source>fieldName (FieldNameShort)</source><target logoport:matchpercent="0" state="translated">fieldName (FieldNameShort)</target>
        </trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="165">
          <source>This property identifies the field when values that the app provides are saved back to the database.</source><target logoport:matchpercent="0" state="translated">Essa propriedade identifica o campo quando os valores fornecidos pelo aplicativo são salvos no banco de dados.</target>
        </trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="166">
          <source>tableName (TableNameShort)</source><target logoport:matchpercent="0" state="translated">tableName (TableNameShort)</target>
        </trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="167">
          <source>This property identifies the field when values that the app provides are saved back to the database.</source>
        <target logoport:matchpercent="0" state="translated" state-qualifier="leveraged-inherited">Essa propriedade identifica o campo quando os valores fornecidos pelo aplicativo são salvos no banco de dados.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="168">
          <source>isEditable (NoYes)</source><target logoport:matchpercent="0" state="translated">isEditable (NoYes)</target>
        </trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="169">
          <source>Set this property to <bpt id="p1">**</bpt>Yes<ept id="p1">**</ept> to specify that the field in the timesheet entry section should be editable by users.</source><target logoport:matchpercent="0" state="translated">Defina essa propriedade como <bpt id="p1">**</bpt>Sim<ept id="p1">**</ept> para especificar que o campo na seção de entrada de folha de ponto deve ser editável pelos usuários.</target>
        </trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="170">
          <source>Set the property to <bpt id="p1">**</bpt>No<ept id="p1">**</ept> to make the field read-only.</source><target logoport:matchpercent="0" state="translated">Defina a propriedade <bpt id="p1">**</bpt>Não<ept id="p1">**</ept> para tornar o campo somente leitura.</target>
        </trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="171">
          <source>isMandatory (NoYes)</source><target logoport:matchpercent="0" state="translated">isMandatory (NoYes)</target>
        </trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="172">
          <source>Set this property to <bpt id="p1">**</bpt>Yes<ept id="p1">**</ept> to specify that the field in the timesheet entry section should be mandatory.</source><target logoport:matchpercent="87" state="translated" state-qualifier="fuzzy-match">Defina essa propriedade como <bpt id="p1">**</bpt>Sim<ept id="p1">**</ept> para especificar que o campo na seção de entrada de folha de ponto deve ser obrigatório.</target>
        </trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="173">
          <source>label (str)</source><target logoport:matchpercent="0" state="translated">etiqueta (str)</target>
        </trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="174">
          <source>This property specifies the label that is shown next the field in the app.</source><target logoport:matchpercent="0" state="translated">Essa propriedade especifica o rótulo mostrado ao lado do campo no aplicativo.</target>
        </trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="175">
          <source>stringOptions (List of Strings)</source><target logoport:matchpercent="0" state="translated">stringOptions (lista de caracteres)</target>
        </trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="176">
          <source>This property is applicable only when <bpt id="p1">**</bpt>fieldBaseType<ept id="p1">**</ept> is set to <bpt id="p2">**</bpt>String<ept id="p2">**</ept>.</source><target logoport:matchpercent="0" state="translated">Essa propriedade é aplicável somente quando <bpt id="p1">**</bpt>fieldBaseType<ept id="p1">**</ept> é definido como <bpt id="p2">**</bpt>Sequência de caracteres<ept id="p2">**</ept>.</target>
        </trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="177">
          <source>If <bpt id="p1">**</bpt>stringOptions<ept id="p1">**</ept> is set, the string values that are available for selection via option buttons (radio buttons) are specified by the strings in the list.</source><target logoport:matchpercent="0" state="translated">Se <bpt id="p1">**</bpt>stringOptions<ept id="p1">**</ept> for definido, os valores de string disponíveis para seleção por meio de botões de opção são especificados pelas sequências de caracteres na lista.</target>
        </trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="178">
          <source>If no strings are provided, free-text entry in the string field is allowed (see the “Use chain of command on the TSTimesheetEntryService class to save a timesheet entry from the app back to the database” section later in this topic for an example).</source><target logoport:matchpercent="0" state="translated">Se nenhuma sequência de caracteres for fornecida, a entrada de texto livre no campo de sequência de caracteres será permitida (consulte a seção “Usar cadeia de comando na classe TSTimesheetEntryService para salvar uma entrada de folha de ponto do aplicativo ao banco de dados” posteriormente neste tópico para obter um exemplo) .</target>
        </trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="179">
          <source>stringLength (int)</source><target logoport:matchpercent="0" state="translated">stringLength (int)</target>
        </trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="180">
          <source>This property specifies the maximum length for a string field.</source><target logoport:matchpercent="0" state="translated">Essa propriedade especifica o comprimento máximo de um campo de sequência de caracteres.</target>
        </trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="181">
          <source>It's applicable only when <bpt id="p1">**</bpt>fieldBaseType<ept id="p1">**</ept> is set to <bpt id="p2">**</bpt>String<ept id="p2">**</ept>.</source><target logoport:matchpercent="79" state="translated" state-qualifier="fuzzy-match">É aplicável somente quando <bpt id="p1">**</bpt>fieldBaseType<ept id="p1">**</ept> é definido como <bpt id="p2">**</bpt>Sequência de caracteres<ept id="p2">**</ept>.</target>
        </trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="182">
          <source>numberOfDecimals (int)</source><target logoport:matchpercent="0" state="translated">numberOfDecimals (int)</target>
        </trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="183">
          <source>This property specifies the number of decimal places that are shown for a real field.</source><target logoport:matchpercent="0" state="translated">Essa propriedade especifica o número de casas decimais exibidas para um campo real.</target>
        </trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="184">
          <source>It's applicable only when <bpt id="p1">**</bpt>fieldBaseType<ept id="p1">**</ept> is set to <bpt id="p2">**</bpt>Real<ept id="p2">**</ept>.</source><target logoport:matchpercent="89" state="translated" state-qualifier="fuzzy-match">É aplicável somente quando <bpt id="p1">**</bpt>fieldBaseType<ept id="p1">**</ept> é definido como <bpt id="p2">**</bpt>Real<ept id="p2">**</ept>.</target>
        </trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="185">
          <source>orderSequence (int)</source><target logoport:matchpercent="0" state="translated">orderSequence (int)</target>
        </trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="186">
          <source>This property controls the order in which the custom fields are shown in the app when more than one custom field is specified.</source><target logoport:matchpercent="0" state="translated">Essa propriedade controla a ordem em que os campos personalizados são mostrados no aplicativo quando mais de um campo personalizado é especificado.</target>
        </trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="187">
          <source>Fields that have lower numbers are shown first.</source><target logoport:matchpercent="0" state="translated">Campos com números inferiores são mostrados primeiro.</target>
        </trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="188">
          <source>booleanValue (boolean)</source><target logoport:matchpercent="0" state="translated">booleanValue (booliano)</target>
        </trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="189">
          <source>For fields of the <bpt id="p1">**</bpt>Boolean<ept id="p1">**</ept> type, this property passes the Boolean value of the field between the server and the app.</source><target logoport:matchpercent="0" state="translated">Para os campos do tipo <bpt id="p1">**</bpt>Booliano<ept id="p1">**</ept>, essa propriedade transmite o valor booliano do campo entre o servidor e o aplicativo.</target>
        </trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="190">
          <source>guidValue (guid)</source><target logoport:matchpercent="0" state="translated">guidValue (guid)</target>
        </trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="191">
          <source>For fields of the <bpt id="p1">**</bpt>GUID<ept id="p1">**</ept> type, this property passes the globally unique identifier (GUID) value of the field between the server and the app.</source><target logoport:matchpercent="0" state="translated">Para campos do tipo <bpt id="p1">**</bpt>GUID<ept id="p1">**</ept>, essa propriedade transmite o valor de identificador global exclusivo (GUID) do campo entre o servidor e o aplicativo.</target>
        </trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="192">
          <source>int64Value (int64)</source><target logoport:matchpercent="0" state="translated">int64Value (int64)</target>
        </trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="193">
          <source>For fields of the <bpt id="p1">**</bpt>Int64<ept id="p1">**</ept> type, this property passes the int64 value of the field between the server and the app.</source><target logoport:matchpercent="89" state="translated" state-qualifier="fuzzy-match">Para os campos do tipo <bpt id="p1">**</bpt>Int64<ept id="p1">**</ept>, essa propriedade transmite o valor int64 do campo entre o servidor e o aplicativo.</target>
        </trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="194">
          <source>intValue (int)</source><target logoport:matchpercent="0" state="translated">intValue (int)</target>
        </trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="195">
          <source>For fields of the <bpt id="p1">**</bpt>Int<ept id="p1">**</ept> type, this property passes the int value of the field between the server and the app.</source><target logoport:matchpercent="92" state="translated" state-qualifier="fuzzy-match">Para os campos do tipo <bpt id="p1">**</bpt>Int<ept id="p1">**</ept>, essa propriedade transmite o valor int do campo entre o servidor e o aplicativo.</target>
        </trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="196">
          <source>realValue (real)</source><target logoport:matchpercent="0" state="translated">realValue (real)</target>
        </trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="197">
          <source>For fields of the <bpt id="p1">**</bpt>Real<ept id="p1">**</ept> type, this property passes the real value of the field between the server and the app .</source><target logoport:matchpercent="89" state="translated" state-qualifier="fuzzy-match">Para os campos do tipo <bpt id="p1">**</bpt>Real<ept id="p1">**</ept>, essa propriedade transmite o valor real do campo entre o servidor e o aplicativo.</target>
        </trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="198">
          <source>stringValue (str)</source><target logoport:matchpercent="0" state="translated">stringValue (str)</target>
        </trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="199">
          <source>For fields of the <bpt id="p1">**</bpt>String<ept id="p1">**</ept> type, this property passes the string value of the field between the server and the app.</source><target logoport:matchpercent="89" state="translated" state-qualifier="fuzzy-match">Para os campos do tipo <bpt id="p1">**</bpt>Sequência de caracteres<ept id="p1">**</ept>, essa propriedade transmite o valor de sequência de caracteres do campo entre o servidor e o aplicativo.</target>
        </trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="200">
          <source>It's also used for fields of the <bpt id="p1">**</bpt>Real<ept id="p1">**</ept> type that are formatted as currency.</source><target logoport:matchpercent="0" state="translated">Ela também é usada em campos do tipo <bpt id="p1">**</bpt>Real<ept id="p1">**</ept> que são formatados como moeda.</target>
        </trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="201">
          <source>For those fields, the property is used to pass the currency code to the app.</source><target logoport:matchpercent="0" state="translated">Para esses campos, a propriedade é usada para transmitir o código da moeda para o aplicativo.</target>
        </trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="202">
          <source>dateValue (date)</source><target logoport:matchpercent="0" state="translated">dateValue (data)</target>
        </trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="203">
          <source>For fields of the <bpt id="p1">**</bpt>Date<ept id="p1">**</ept> type, this property passes the date value of the field between the server and the app.</source><target logoport:matchpercent="89" state="translated" state-qualifier="fuzzy-match">Para os campos do tipo <bpt id="p1">**</bpt>Data<ept id="p1">**</ept>, essa propriedade transmite o valor de data do campo entre o servidor e o aplicativo.</target>
        </trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="204">
          <source>Show and save a custom field in the timesheet entry section</source><target logoport:matchpercent="0" state="translated">Mostrar e salvar um campo personalizado na seção de entrada de folha de ponto</target>
        </trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="205">
          <source>Below is a screenshot from the mobile app of a timesheet entry creation.</source><target logoport:matchpercent="0" state="translated">Veja abaixo uma captura de tela do aplicativo móvel de uma criação de entrada de folha de ponto.</target>
        </trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="206">
          <source>It shows the out-of-box fields and a custom field in the "Time entry" section called "Test string" with an enum value of "Second option" already set.</source><target logoport:matchpercent="0" state="translated">Ela mostra os campos prontos para uso e um campo personalizado na seção "Entrada de tempo" chamada "Sequência de caracteres de teste" com um valor de enumeração da "Segunda opção" já definido.</target>
        </trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="207">
          <source>Test string custom field in the app</source><target logoport:matchpercent="0" state="translated">Campo personalizado de sequência de caracteres de teste no aplicativo</target>
        </trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="208">
          <source>Below is a screenshot from the mobile app of the user selecting one of the enum options available for the "Test string" custom field.</source><target logoport:matchpercent="0" state="translated">Veja abaixo uma captura de tela do aplicativo móvel do usuário, selecionando uma das opções de enumeração disponíveis para o campo personalizado "Sequência de caracteres de teste".</target>
        </trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="209">
          <source>The two options are "First option" and "Second option" shown as radio buttons.</source><target logoport:matchpercent="0" state="translated">As duas opções são "Primeira opção" e "Segunda opção" mostradas como botões de opção.</target>
        </trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="210">
          <source>The second option is currently selected.</source><target logoport:matchpercent="0" state="translated">A segunda opção está atualmente selecionada.</target>
        </trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="211">
          <source>Option buttons (radio buttons) for the Test string custom field</source><target logoport:matchpercent="0" state="translated">Botões de opção para o campo personalizado de sequência de caracteres de teste</target>
        </trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="212">
          <source>Extend the TSTimesheetLine table so that it has a custom field</source><target logoport:matchpercent="0" state="translated">Estenda a tabela TSTimesheetLine para que ela tenha um campo personalizado</target>
        </trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="213">
          <source>In typical scenarios, it's likely that the data for a custom field in the timesheet entry section will be saved to the TSTimesheetLine table.</source><target logoport:matchpercent="0" state="translated">Em cenários típicos, é provável que os dados de um campo personalizado na seção de entrada de folha de ponto sejam salvos na tabela TSTimesheetLine.</target>
        </trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="214">
          <source>However, other tables can be used if the data can be retrieved based on a TSTimesheetTrans record that is provided, or if it doesn't have specific record context (for example, if the field is set as read-only in the project parameters).</source><target logoport:matchpercent="0" state="translated">Contudo, outras tabelas podem ser usadas se os dados puderem ser recuperados com base em um registro TSTimesheetTrans fornecido ou se ele não tiver contexto de registro específico (por exemplo, se o campo estiver configurado como somente leitura nos parâmetros do projeto).</target>
        </trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="215">
          <source>Note that custom fields don't have to have any backing database records.</source><target logoport:matchpercent="0" state="translated">Observe que os campos personalizados não precisam ter nenhum registro de banco de dados de apoio.</target>
        </trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="216">
          <source>They can be dynamically generated based on X++ logic.</source><target logoport:matchpercent="0" state="translated">Eles podem ser gerados dinamicamente com base na lógica X++.</target>
        </trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="217">
          <source>This approach can be useful in read-only scenarios (see the “Use chain of command on the TSTimesheetDetails class, buildCustomFieldListForHeader method to fill in timesheet details” section for an example of dynamically generated custom field values.)</source><target logoport:matchpercent="0" state="translated">Essa abordagem pode ser útil em cenários somente leitura (consulte a seção “Usar cadeia de comando na classe TSTimesheetDetails, no comando buildCustomFieldListForHeader para preencher detalhes da folha de ponto” para obter um exemplo de valores de campos personalizados gerados dinamicamente).</target>
        </trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="218">
          <source>Below is a screenshot from Visual Studio of the Application Object Tree.</source><target logoport:matchpercent="0" state="translated">Veja abaixo uma captura de tela do Visual Studio da árvore de objetos de aplicativo.</target>
        </trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="219">
          <source>It shows an extension of the TSTimesheetLine table with the TestLineString field added as a custom field.</source><target logoport:matchpercent="0" state="translated">Ela mostra uma extensão da tabela TSTimesheetLine com o campo TestLineString adicionado como um campo personalizado.</target>
        </trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="220">
          <source>Line string</source><target logoport:matchpercent="0" state="translated">Sequência de caracteres da linha</target>
        </trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="221">
          <source>Use chain of command on the buildCustomFieldList method of the TSTimesheetSettings class to show a field in the timesheet entry section</source><target logoport:matchpercent="0" state="translated">Use cadeia de comando no método buildCustomFieldList da classe TSTimesheetSettings para mostrar um campo na seção de entrada de folha de ponto</target>
        </trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="222">
          <source>This code controls the display settings for the field in the app.</source><target logoport:matchpercent="0" state="translated">Este código controla as configurações de exibição do campo no aplicativo.</target>
        </trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="223">
          <source>For example, it controls the type of field, the label, whether the field is mandatory, and what section the field appears in.</source><target logoport:matchpercent="0" state="translated">Por exemplo, ele controla o tipo de campo, o rótulo, se o campo é obrigatório e em qual seção o campo aparece.</target>
        </trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="224">
          <source>The following example shows a string field on time entries.</source><target logoport:matchpercent="0" state="translated">O exemplo a seguir mostra um campo de sequência de caracteres nas entradas de hora.</target>
        </trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="225">
          <source>This field has two options, <bpt id="p1">**</bpt>First option<ept id="p1">**</ept> and <bpt id="p2">**</bpt>Second option<ept id="p2">**</ept>, that are available via option buttons (radio buttons).</source><target logoport:matchpercent="0" state="translated">Esse campo tem duas opções, <bpt id="p1">**</bpt>Primeira opção<ept id="p1">**</ept> e <bpt id="p2">**</bpt>Segunda opção<ept id="p2">**</ept>, que estão disponíveis por meio de botões de opção.</target>
        </trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="226">
          <source>The field in the app is associated with the <bpt id="p1">**</bpt>TestLineString<ept id="p1">**</ept> field that is added to the TSTimesheetLine table.</source><target logoport:matchpercent="0" state="translated">O campo no aplicativo é associado ao campo <bpt id="p1">**</bpt>TestLineString<ept id="p1">**</ept> que é adicionado à tabela TSTimesheetLine.</target>
        </trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="227">
          <source>Note the use of the <bpt id="p1">**</bpt>TSTimesheetCustomField::newFromMetatdata()<ept id="p1">**</ept> method to simplify the initialization of the custom field properties: <bpt id="p2">**</bpt>fieldBaseType<ept id="p2">**</ept>, <bpt id="p3">**</bpt>tableName<ept id="p3">**</ept>, <bpt id="p4">**</bpt>fieldname<ept id="p4">**</ept>, <bpt id="p5">**</bpt>label<ept id="p5">**</ept>, <bpt id="p6">**</bpt>isEditable<ept id="p6">**</ept>, <bpt id="p7">**</bpt>isMandatory<ept id="p7">**</ept>, <bpt id="p8">**</bpt>stringLength<ept id="p8">**</ept>, and <bpt id="p9">**</bpt>numberOfDecimals<ept id="p9">**</ept>.</source><target logoport:matchpercent="0" state="translated">Observe o uso do método <bpt id="p1">**</bpt>TSTimesheetCustomField::newFromMetatdata()<ept id="p1">**</ept> para simplificar a inicialização das propriedades do campo personalizado: <bpt id="p2">**</bpt>fieldBaseType<ept id="p2">**</ept>, <bpt id="p3">**</bpt>tableName<ept id="p3">**</ept>, <bpt id="p4">**</bpt>fieldname<ept id="p4">**</ept>, <bpt id="p5">**</bpt>label<ept id="p5">**</ept>, <bpt id="p6">**</bpt>isEditable<ept id="p6">**</ept>, <bpt id="p7">**</bpt>isMandatory<ept id="p7">**</ept>, <bpt id="p8">**</bpt>stringLength<ept id="p8">**</ept> e <bpt id="p9">**</bpt>numberOfDecimals<ept id="p9">**</ept>.</target>
        </trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="228">
          <source>You can also set these parameters manually, as you prefer.</source><target logoport:matchpercent="0" state="translated">Você também pode definir esses parâmetros manualmente, como preferir.</target>
        </trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="229">
          <source>Use chain of command on the buildCustomFieldListForEntry method of the TSTimesheetEntry class to enter values in a timesheet entry</source><target logoport:matchpercent="75" state="translated" state-qualifier="fuzzy-match">Use cadeia de comando no método buildCustomFieldListForEntry da classe TSTimesheetEntry para inserir valores em uma entrada de folha de ponto</target>
        </trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="230">
          <source>The <bpt id="p1">**</bpt>buildCustomFieldListForEntry<ept id="p1">**</ept> method is used to enter values on the saved timesheet lines in the mobile app.</source><target logoport:matchpercent="0" state="translated">O método <bpt id="p1">**</bpt>buildCustomFieldListForEntry<ept id="p1">**</ept> é usado para inserir valores nas linhas de folha de ponto salvas no aplicativo móvel.</target>
        </trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="231">
          <source>It takes a TSTimesheetTrans record as a parameter.</source><target logoport:matchpercent="0" state="translated">Leva um registro TSTimesheetTrans como um parâmetro.</target>
        </trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="232">
          <source>Fields from that record can be used to fill in the custom field value in the app.</source><target logoport:matchpercent="0" state="translated">Os campos desse registro podem ser usados para preencher o valor do campo personalizado no aplicativo.</target>
        </trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="233">
          <source>Use chain of command on the TSTimesheetEntryService class to save a timesheet entry from the app back to the database</source><target logoport:matchpercent="0" state="translated">Use a cadeia de comando na classe TSTimesheetEntryService para salvar uma entrada de folha de ponto do aplicativo no banco de dados</target>
        </trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="234">
          <source>To save a custom field back to the database in typical usage, you must extend multiple methods:</source><target logoport:matchpercent="0" state="translated">Para salvar um campo personalizado no banco de dados em uso típico, você deve estender vários métodos:</target>
        </trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="235">
          <source>The <bpt id="p1">**</bpt>timesheetLineNeedsUpdating<ept id="p1">**</ept> method is used to determine whether the line record has been changed by the user in the app and must be saved to the database.</source><target logoport:matchpercent="0" state="translated">O método <bpt id="p1">**</bpt>timesheetLineNeedsUpdating<ept id="p1">**</ept> é usado para determinar se o registro de linha foi alterado pelo usuário no aplicativo e deve ser salvo no banco de dados.</target>
        </trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="236">
          <source>If performance isn't a concern, this method can be simplified so that it always returns <bpt id="p1">**</bpt>true<ept id="p1">**</ept>.</source><target logoport:matchpercent="0" state="translated">Se o desempenho não é uma preocupação, esse método pode ser simplificado para que ele sempre retorne <bpt id="p1">**</bpt>verdadeiro<ept id="p1">**</ept>.</target>
        </trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="237">
          <source>The <bpt id="p1">**</bpt>populateTimesheetLineFromEntryDuringCreate<ept id="p1">**</ept> and <bpt id="p2">**</bpt>populateTimesheetLineFromEntryDuringUpdate<ept id="p2">**</ept> methods can be extended so that they enter values in the TSTimesheetLine database record from the TSTimesheetEntry data contract record that is provided.</source><target logoport:matchpercent="0" state="translated">Os métodos <bpt id="p1">**</bpt>populateTimesheetLineFromEntryDuringCreate<ept id="p1">**</ept> e <bpt id="p2">**</bpt>populateTimesheetLineFromEntryDuringUpdate<ept id="p2">**</ept> podem ser estendidos para inserir valores no registro do banco de dados TSTimesheetLine a partir do registro de contrato de dados TSTimesheetEntry fornecido.</target>
        </trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="238">
          <source>In the example that follows, notice how the mapping between the database field and the entry field is manually done via X++ code.</source><target logoport:matchpercent="0" state="translated">No exemplo a seguir, observe como o mapeamento entre o campo do banco de dados e o campo de entrada é feito manualmente por meio do código X++.</target>
        </trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="239">
          <source>The <bpt id="p1">**</bpt>populateTimesheetWeekFromEntry<ept id="p1">**</ept> method can also be extended if the custom field that is mapped to the <bpt id="p2">**</bpt>TSTimesheetEntry<ept id="p2">**</ept> object must write back to the TSTimesheetLineweek database table.</source><target logoport:matchpercent="0" state="translated">O método <bpt id="p1">**</bpt>populateTimesheetWeekFromEntry<ept id="p1">**</ept> também pode ser estendido se o campo personalizado mapeado para o objeto <bpt id="p2">**</bpt>TSTimesheetEntry<ept id="p2">**</ept> precisar gravar na tabela de banco de dados TSTimesheetLineweek.</target>
        </trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="240">
          <source>The following example saves the <bpt id="p1">**</bpt>firstOption<ept id="p1">**</ept> or <bpt id="p2">**</bpt>secondOption<ept id="p2">**</ept> value that the user selects to the database as a raw string value.</source><target logoport:matchpercent="0" state="translated">O exemplo a seguir salva o valor <bpt id="p1">**</bpt>firstOption<ept id="p1">**</ept> ou <bpt id="p2">**</bpt>secondOption<ept id="p2">**</ept> que o usuário seleciona no banco de dados como um valor de sequência de caracteres não processado.</target>
        </trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="241">
          <source>If the database field is a field of the <bpt id="p1">**</bpt>Enum<ept id="p1">**</ept> type, those values can be manually mapped to an enum value and then saved to an enum field on the database table.</source><target logoport:matchpercent="0" state="translated">Se o campo do banco de dados for um campo do tipo <bpt id="p1">**</bpt>Enumeração<ept id="p1">**</ept>, esses valores poderão ser mapeados manualmente para um valor de enumeração e, em seguida, salvos em um campo de enumeração na tabela do banco de dados.</target>
        </trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="242">
          <source>Show a custom field in the timesheet header section</source><target logoport:matchpercent="75" state="translated" state-qualifier="fuzzy-match">Mostrar um campo personalizado na seção de cabeçalho de folha de ponto</target>
        </trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="243">
          <source>Below is a screenshot from the mobile app of a user viewing a timesheet.</source><target logoport:matchpercent="82" state="translated" state-qualifier="fuzzy-match">Veja abaixo uma captura de tela do aplicativo móvel de um usuário que visualiza uma folha de ponto.</target>
        </trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="244">
          <source>The "More information" button has been selected in the upper-right corner to show the "View more details" option.</source><target logoport:matchpercent="0" state="translated">O botão "Mais informações" foi selecionado no canto superior direito para mostrar a opção "Exibir mais detalhes".</target>
        </trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="245">
          <source>View more details command</source><target logoport:matchpercent="77" state="translated" state-qualifier="fuzzy-match">Comando Exibir mais detalhes</target>
        </trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="246">
          <source>Below is a screenshot from the mobile app showing the “More” section of a timesheet.</source><target logoport:matchpercent="75" state="translated" state-qualifier="fuzzy-match">Veja abaixo uma captura de tela do aplicativo móvel mostrando a seção “Mais” de uma folha de ponto.</target>
        </trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="247">
          <source>A custom field called “Utilization rate of this timesheet (computed custom field)” has been added to the timesheet header section.</source><target logoport:matchpercent="0" state="translated">Um campo personalizado chamado “Taxa de utilização desta folha de ponto (campo personalizado computado)” foi adicionado à seção de cabeçalho de folha de ponto.</target>
        </trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="248">
          <source>A read-only value of "0.667" is set on the custom field.</source><target logoport:matchpercent="0" state="translated">Um valor somente leitura de "0,667" é definido no campo personalizado.</target>
        </trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="249">
          <source>More section</source><target logoport:matchpercent="79" state="translated" state-qualifier="fuzzy-match">Seção Mais</target>
        </trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="250">
          <source>Extend the TSTimesheetTable table so that it has a custom field</source><target logoport:matchpercent="90" state="translated" state-qualifier="fuzzy-match">Estenda a tabela TSTimesheetTable para que ela tenha um campo personalizado</target>
        </trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="251">
          <source>In typical scenarios, it's likely that the data for a custom field in the header section will be pulled from the TSTimesheetHeader table.</source><target logoport:matchpercent="82" state="translated" state-qualifier="fuzzy-match">Em cenários típicos, é provável que os dados de um campo personalizado na seção de cabeçalho será extraído da tabela TSTimesheetHeader.</target>
        </trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="252">
          <source>However, other tables can be used if the data can be retrieved based on a TSTimesheetTable record that is provided, or if it doesn't have specific record context (for example, if the field is set as read-only in the project parameters).</source><target logoport:matchpercent="97" state="translated" state-qualifier="fuzzy-match">Contudo, outras tabelas podem ser usadas se os dados puderem ser recuperados com base em um registro TSTimesheetTable fornecido ou se ele não tiver contexto de registro específico (por exemplo, se o campo estiver configurado como somente leitura nos parâmetros do projeto).</target>
        </trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="253">
          <source>Note that custom fields don't have to have any backing database records.</source>
        <target logoport:matchpercent="0" state="translated" state-qualifier="leveraged-inherited">Observe que os campos personalizados não precisam ter nenhum registro de banco de dados de apoio.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="254">
          <source>They can be dynamically generated based on X++ logic.</source>
        <target logoport:matchpercent="0" state="translated" state-qualifier="leveraged-inherited">Eles podem ser gerados dinamicamente com base na lógica X++.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="255">
          <source>The example that follows shows this approach.</source><target logoport:matchpercent="0" state="translated">O exemplo a seguir mostra essa abordagem.</target>
        </trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="256">
          <source>Fields in the header section are always read-only in the app.</source><target logoport:matchpercent="0" state="translated">Os campos na seção de cabeçalho são sempre somente leitura no aplicativo.</target>
        </trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="257">
          <source>Use chain of command on the buildCustomFieldList method of the TSTimesheetSettings class to show a field in the header section</source><target logoport:matchpercent="89" state="translated" state-qualifier="fuzzy-match">Use cadeia de comando no método buildCustomFieldList da classe TSTimesheetSettings para mostrar um campo na seção do cabeçalho</target>
        </trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="258">
          <source>This code controls the display settings for the field in the app.</source>
        <target logoport:matchpercent="0" state="translated" state-qualifier="leveraged-inherited">Este código controla as configurações de exibição do campo no aplicativo.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="259">
          <source>For example, it controls the type of field, the label, whether the field is mandatory, and what section the field appears in.</source>
        <target logoport:matchpercent="0" state="translated" state-qualifier="leveraged-inherited">Por exemplo, ele controla o tipo de campo, o rótulo, se o campo é obrigatório e em qual seção o campo aparece.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="260">
          <source>The following example shows a computed value in the header section in the app.</source><target logoport:matchpercent="0" state="translated">O exemplo a seguir mostra um valor computado na seção de cabeçalho no aplicativo.</target>
        </trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="261">
          <source>Use chain of command on the buildCustomFieldListForHeader method of the TSTimesheetDetails class to fill in timesheet details</source><target logoport:matchpercent="75" state="translated" state-qualifier="fuzzy-match">Use cadeia de comando no método buildCustomFieldListForHeader da classe TSTimesheetDetails para preencher os detalhes de folha de ponto</target>
        </trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="262">
          <source>The <bpt id="p1">**</bpt>buildCustomFieldListForHeader<ept id="p1">**</ept> method is used to fill in the timesheet header details in the mobile app.</source><target logoport:matchpercent="71" state="translated" state-qualifier="fuzzy-match">O método <bpt id="p1">**</bpt>buildCustomFieldListForHeader<ept id="p1">**</ept> é usado para preencher os detalhes do cabeçalho de folha de ponto no aplicativo para dispositivos móveis.</target>
        </trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="263">
          <source>It takes a TSTimesheetTable record as a parameter.</source><target logoport:matchpercent="87" state="translated" state-qualifier="fuzzy-match">Leva um registro TSTimesheetTable como um parâmetro.</target>
        </trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="264">
          <source>Fields from that record can be used to fill in the custom field value in the app.</source>
        <target logoport:matchpercent="0" state="translated" state-qualifier="leveraged-inherited">Os campos desse registro podem ser usados para preencher o valor do campo personalizado no aplicativo.</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="265">
          <source>The following example doesn't read any values from the database.</source><target logoport:matchpercent="0" state="translated">O exemplo a seguir não lê nenhum valor do banco de dados.</target>
        </trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="266">
          <source>Instead, it uses X++ logic to generate a computed value that is then shown in the app.</source><target logoport:matchpercent="0" state="translated">Em vez disso, ele usa a lógica X++ para gerar um valor computado que é exibido no aplicativo.</target>
        </trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="267">
          <source>Other configurability/extensibility opportunities</source><target logoport:matchpercent="0" state="translated">Outras oportunidades de configurabilidade/extensibilidade</target>
        </trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="268">
          <source>Adding additional validation for the app</source><target logoport:matchpercent="0" state="translated">Adição de validação adicional para o aplicativo</target>
        </trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="269">
          <source>Existing logic for timesheet functionality at the database level will still work as expected.</source><target logoport:matchpercent="0" state="translated">A lógica existente para a funcionalidade de folha de ponto no nível do banco de dados ainda funcionará conforme o esperado.</target>
        </trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="270">
          <source>To interrupt the completion of save or submit operations and show a specific error message, you can add <bpt id="p1">**</bpt>throw error("message to user")<ept id="p1">**</ept> to the code via a chain of command extension.</source><target logoport:matchpercent="0" state="translated">Para interromper a conclusão de salvar ou enviar operações e mostrar uma mensagem de erro específica, você pode adicionar <bpt id="p1">**</bpt>gerar erro ("mensagem para usuário")<ept id="p1">**</ept> ao código por meio de uma cadeia de extensão de comando.</target>
        </trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="271">
          <source>Here are three examples of useful extensible methods:</source><target logoport:matchpercent="0" state="translated">Veja três exemplos de métodos extensíveis úteis:</target>
        </trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="272">
          <source>If <bpt id="p1">**</bpt>validateWrite<ept id="p1">**</ept> on the TSTimesheetLine table returns <bpt id="p2">**</bpt>false<ept id="p2">**</ept> during a save operation for a timesheet line, an error message is shown in the mobile app.</source><target logoport:matchpercent="0" state="translated">Se <bpt id="p1">**</bpt>validateWrite<ept id="p1">**</ept> na tabela TSTimesheetLine retornar <bpt id="p2">**</bpt>falso<ept id="p2">**</ept> durante uma operação de salvamento para uma linha da folha de ponto, uma mensagem de erro será mostrada no aplicativo móvel.</target>
        </trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="273">
          <source>If <bpt id="p1">**</bpt>validateSubmit<ept id="p1">**</ept> on the TSTimesheetTable table returns <bpt id="p2">**</bpt>false<ept id="p2">**</ept> during timesheet submission in the app, an error message is shown to the user.</source><target logoport:matchpercent="72" state="translated" state-qualifier="fuzzy-match">Se <bpt id="p1">**</bpt>validateSubmit<ept id="p1">**</ept> na tabela TSTimesheetTable retornar <bpt id="p2">**</bpt>falso<ept id="p2">**</ept> durante o envio da folha de ponto no aplicativo, uma mensagem de erro é mostrada ao usuário.</target>
        </trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="274">
          <source>Logic that fills in fields (for example, <bpt id="p1">**</bpt>Line Property<ept id="p1">**</ept>) during the <bpt id="p2">**</bpt>insert<ept id="p2">**</ept> method on the TSTimesheetLine table will still run.</source><target logoport:matchpercent="0" state="translated">A lógica que preenche os campos (por exemplo, <bpt id="p1">**</bpt>Propriedade da linha<ept id="p1">**</ept>) durante o método <bpt id="p2">**</bpt>inserir<ept id="p2">**</ept> na tabela TSTimesheetLine ainda será executada.</target>
        </trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="275">
          <source>Hiding and marking out-of-box fields as read-only via configuration</source><target logoport:matchpercent="0" state="translated">Ocultação e marcação de campos prontos para uso como somente leitura por meio de configuração</target>
        </trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="276">
          <source>From the project parameters, you can make out-of-box fields read-only or hidden in the mobile app.</source><target logoport:matchpercent="0" state="translated">Nos parâmetros do projeto, você pode criar campos prontos para uso somente leitura ou ocultos no aplicativo para dispositivos móveis.</target>
        </trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="277">
          <source>Set the options in the <bpt id="p1">**</bpt>Mobile timesheets<ept id="p1">**</ept> section on the <bpt id="p2">**</bpt>Timesheet<ept id="p2">**</ept> tab of the <bpt id="p3">**</bpt>Project management and accounting parameters<ept id="p3">**</ept> page.</source><target logoport:matchpercent="0" state="translated">Defina as opções na seção <bpt id="p1">**</bpt>Folhas de ponto móveis<ept id="p1">**</ept> na guia <bpt id="p2">**</bpt>Folha de ponto<ept id="p2">**</ept> da página <bpt id="p3">**</bpt>Parâmetros de gerenciamento e contabilidade de projetos<ept id="p3">**</ept>.</target>
        </trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="278">
          <source>Project parameters</source>
        <target logoport:matchpercent="100" state="translated" state-qualifier="leveraged-tm">Parâmetros do projeto</target></trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="279">
          <source>Changing the activities that are available for selection via extensions</source><target logoport:matchpercent="0" state="translated">Alteração das atividades que estão disponíveis para seleção por meio de extensões</target>
        </trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="280">
          <source>The activities that are available for selection for a project are filled in via the <bpt id="p1">**</bpt>getActivitiesForProject()<ept id="p1">**</ept> and <bpt id="p2">**</bpt>getActivityQuery()<ept id="p2">**</ept> methods in the <bpt id="p3">**</bpt>TsTimesheetProjectService<ept id="p3">**</ept> class.</source><target logoport:matchpercent="0" state="translated">As atividades disponíveis para seleção de um projeto são preenchidas por meio dos métodos <bpt id="p1">**</bpt>getActivitiesForProject()<ept id="p1">**</ept> e <bpt id="p2">**</bpt>getActivityQuery()<ept id="p2">**</ept> na classe <bpt id="p3">**</bpt>TsTimesheetProjectService<ept id="p3">**</ept>.</target>
        </trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="281">
          <source>You can use chain of command to change this behavior to match your business scenario for the activities that are available for selection for a specific project.</source><target logoport:matchpercent="0" state="translated">É possível usar a cadeia de comando para alterar esse comportamento para corresponder ao seu cenário de negócios para as atividades que estão disponíveis para seleção de um projeto específico.</target>
        </trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="282">
          <source>Entering a default project category on timesheet entries</source><target logoport:matchpercent="0" state="translated">Inserção de uma categoria de projeto padrão nas entradas de folha de ponto</target>
        </trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="283">
          <source>Entry of a default project category on timesheet entries occurs at three levels.</source><target logoport:matchpercent="0" state="translated">A entrada de uma categoria de projeto padrão nas entradas do quadro de horários ocorre em três níveis.</target>
        </trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="284">
          <source>You can use chain of command to extend the behavior at any or all of these levels to achieve the desired behavior.</source><target logoport:matchpercent="0" state="translated">Você pode usar a cadeia de comando para estender o comportamento em qualquer um ou todos esses níveis para obter o comportamento desejado.</target>
        </trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="285">
          <source>The following hierarchy is used:</source><target logoport:matchpercent="82" state="translated" state-qualifier="fuzzy-match">Esta é a hierarquia usada:</target>
        </trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="286">
          <source>The app tries to put the default category from the project resource.</source><target logoport:matchpercent="0" state="translated">O aplicativo tenta colocar a categoria padrão do recurso do projeto.</target>
        </trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="287">
          <source>This default category is set in the <bpt id="p1">**</bpt>getCurrentUserResource<ept id="p1">**</ept> and <bpt id="p2">**</bpt>getDelegatedResourcesForCurrentUser<ept id="p2">**</ept> methods in the <bpt id="p3">**</bpt>TSTimesheetSettingsService<ept id="p3">**</ept> class.</source><target logoport:matchpercent="0" state="translated">Essa categoria padrão é definida nos métodos<bpt id="p1">**</bpt>getCurrentUserResource<ept id="p1">**</ept> e <bpt id="p2">**</bpt>getDelegatedResourcesForCurrentUser<ept id="p2">**</ept> na classe <bpt id="p3">**</bpt>TSTimesheetSettingsService<ept id="p3">**</ept>.</target>
        </trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="288">
          <source>If the default category isn't provided at the project resource level, the app tries to pull it from the project activity.</source><target logoport:matchpercent="0" state="translated">Se a categoria padrão não for fornecida no nível do recurso do projeto, o aplicativo tentará extraí-la da atividade do projeto.</target>
        </trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="289">
          <source>This default category is set in the <bpt id="p1">**</bpt>getActivitiesForProject<ept id="p1">**</ept> method in the <bpt id="p2">**</bpt>TSTimesheetProjectService<ept id="p2">**</ept> class.</source><target logoport:matchpercent="0" state="translated">Essa categoria padrão é definida no método <bpt id="p1">**</bpt>getActivitiesForProject<ept id="p1">**</ept> na classe <bpt id="p2">**</bpt>TSTimesheetProjectService<ept id="p2">**</ept>.</target>
        </trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="290">
          <source>If the default category isn't provided at the project activity level, the default category it taken from the project parameters.</source><target logoport:matchpercent="82" state="translated" state-qualifier="fuzzy-match">Se a categoria padrão não for fornecida no nível de atividade do projeto, a categoria padrão será obtida dos parâmetros do projeto.</target>
        </trans-unit>
        <trans-unit xml:space="preserve" translate="yes" id="291">
          <source>This default category is set in the <bpt id="p1">**</bpt>getProjectDetailsbyRule<ept id="p1">**</ept> method in the <bpt id="p2">**</bpt>TSTimesheetProjectService<ept id="p2">**</ept> class.</source><target logoport:matchpercent="91" state="translated" state-qualifier="fuzzy-match">Essa categoria padrão é definida no método <bpt id="p1">**</bpt>getProjectDetailsbyRule<ept id="p1">**</ept> na classe <bpt id="p2">**</bpt>TSTimesheetProjectService<ept id="p2">**</ept>.</target>
        </trans-unit>
      </group>
    </body>
  </file>
</xliff>