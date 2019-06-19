---
title: Implementar campos personalizados para o aplicativo móvel do Microsoft Dynamics 365 Project Timesheet no iOS e Android
description: Este tópico fornece padrões comuns para o uso de extensões para implementar campos personalizados.
author: KimANelson
manager: AnnBe
ms.date: 05/29/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.search.industry: Service industries
ms.author: knelson
ms.dyn365.ops.version: 10.0.3
ms.search.validFrom: 2019-05-29
ms.openlocfilehash: 4343c875da05641c57b7784bf52f1c814dd26d20
ms.sourcegitcommit: 19859d8566a8c7840066b2c10c6b08b67f1b83f4
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/04/2019
ms.locfileid: "1617987"
---
# <a name="implement-custom-fields-for-the-microsoft-dynamics-365-project-timesheet-mobile-app-on-ios-and-android"></a><span data-ttu-id="05af2-103">Implementar campos personalizados para o aplicativo móvel do Microsoft Dynamics 365 Project Timesheet no iOS e Android</span><span class="sxs-lookup"><span data-stu-id="05af2-103">Implement custom fields for the Microsoft Dynamics 365 Project Timesheet mobile app on iOS and Android</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="05af2-104">Este tópico fornece padrões comuns para o uso de extensões para implementar campos personalizados.</span><span class="sxs-lookup"><span data-stu-id="05af2-104">This topic provides common patterns for using extensions to implement custom fields.</span></span> <span data-ttu-id="05af2-105">Os tópicos a seguir estão cobertos:</span><span class="sxs-lookup"><span data-stu-id="05af2-105">The following topics are covered:</span></span>

- <span data-ttu-id="05af2-106">Os vários tipos de dados a que a estrutura de campo personalizado oferece suporte</span><span class="sxs-lookup"><span data-stu-id="05af2-106">The various data types that the custom field framework supports</span></span>
- <span data-ttu-id="05af2-107">Como mostrar campos somente leitura ou editáveis nas entradas de folha de ponto e salvar os valores fornecidos pelo usuário no banco de dados</span><span class="sxs-lookup"><span data-stu-id="05af2-107">How to show read-only or editable fields on timesheet entries, and save user-provided values back to the database</span></span>
- <span data-ttu-id="05af2-108">Como mostrar campos somente leitura no cabeçalho de folha de ponto</span><span class="sxs-lookup"><span data-stu-id="05af2-108">How to show read-only fields on the timesheet header</span></span>
- <span data-ttu-id="05af2-109">Como integrar outra lógica de negócios personalizada para inserir valores padrão em campos e fazer uma validação adicional</span><span class="sxs-lookup"><span data-stu-id="05af2-109">How to integrate other custom business logic to enter default values in fields and do additional validation</span></span>

## <a name="audience"></a><span data-ttu-id="05af2-110">Público-alvo</span><span class="sxs-lookup"><span data-stu-id="05af2-110">Audience</span></span>

<span data-ttu-id="05af2-111">Este tópico é destinado a desenvolvedores que estão integrando seus campos personalizados no aplicativo móvel do Microsoft Dynamics 365 Project Timesheet que está disponível para Apple iOS e Google Android.</span><span class="sxs-lookup"><span data-stu-id="05af2-111">This topic is intended for developers who are integrating their custom fields into the Microsoft Dynamics 365 Project Timesheet mobile application that is available for Apple iOS and Google Android.</span></span> <span data-ttu-id="05af2-112">A suposição é que os leitores estão familiarizados com o desenvolvimento do X ++ e a funcionalidade de folha de ponto do projeto.</span><span class="sxs-lookup"><span data-stu-id="05af2-112">The assumption is that readers are familiar with X++ development and project timesheet functionality.</span></span>

## <a name="data-contract--tstimesheetcustomfield-x-class"></a><span data-ttu-id="05af2-113">Contrato dos dados – Classe TSTimesheetCustomField X++</span><span class="sxs-lookup"><span data-stu-id="05af2-113">Data contract – TSTimesheetCustomField X++ class</span></span>

<span data-ttu-id="05af2-114">A classe **TSTimesheetCustomField** é a classe de contrato de dados X++ que representa informações sobre um campo personalizado para a funcionalidade de folha de ponto.</span><span class="sxs-lookup"><span data-stu-id="05af2-114">The **TSTimesheetCustomField** class is the X++ data contract class that represents information about a custom field for timesheet functionality.</span></span> <span data-ttu-id="05af2-115">As listas dos objetos de campo personalizados são transmitidas no contrato de dados TSTimesheetDetails e no contrato de dados TSTimesheetEntry para mostrar campos personalizados no aplicativo móvel.</span><span class="sxs-lookup"><span data-stu-id="05af2-115">Lists of the custom field objects are passed on both the TSTimesheetDetails data contract and the TSTimesheetEntry data contract to show custom fields in the mobile app.</span></span>

- <span data-ttu-id="05af2-116">**TSTimesheetDetails** - O contrato de cabeçalho da folha de ponto.</span><span class="sxs-lookup"><span data-stu-id="05af2-116">**TSTimesheetDetails** - The timesheet header contract.</span></span>
- <span data-ttu-id="05af2-117">**TSTimesheetEntry** - O contrato da transação da folha de ponto.</span><span class="sxs-lookup"><span data-stu-id="05af2-117">**TSTimesheetEntry** - The timesheet transaction contract.</span></span> <span data-ttu-id="05af2-118">Grupos desses objetos com as mesmas informações do projeto e o valor **timesheetLineRecId** constituem uma linha.</span><span class="sxs-lookup"><span data-stu-id="05af2-118">Groups of these objects that have the same project information and **timesheetLineRecId** value constitute a line.</span></span>

### <a name="fieldbasetype-types"></a><span data-ttu-id="05af2-119">fieldBaseType (tipos)</span><span class="sxs-lookup"><span data-stu-id="05af2-119">fieldBaseType (Types)</span></span>

<span data-ttu-id="05af2-120">A propriedade **FieldBaseType** no objeto **TsTimesheetCustom** determina o tipo do campo exibido no aplicativo.</span><span class="sxs-lookup"><span data-stu-id="05af2-120">The **FieldBaseType** property on the **TsTimesheetCustom** object determines the type of the field that appears in the app.</span></span> <span data-ttu-id="05af2-121">Os valores **Tipos** a seguir que são compatíveis.</span><span class="sxs-lookup"><span data-stu-id="05af2-121">The following **Types** values that are supported.</span></span>

| <span data-ttu-id="05af2-122">Tipos de valor</span><span class="sxs-lookup"><span data-stu-id="05af2-122">Types value</span></span> | <span data-ttu-id="05af2-123">Tipo</span><span class="sxs-lookup"><span data-stu-id="05af2-123">Type</span></span>              | <span data-ttu-id="05af2-124">Observação</span><span class="sxs-lookup"><span data-stu-id="05af2-124">Notes</span></span> |
|-------------|-------------------|-------|
| <span data-ttu-id="05af2-125">0</span><span class="sxs-lookup"><span data-stu-id="05af2-125">0</span></span>           | <span data-ttu-id="05af2-126">Sequência de caracteres (e enumeração)</span><span class="sxs-lookup"><span data-stu-id="05af2-126">String (and Enum)</span></span> | <span data-ttu-id="05af2-127">O campo aparece como um campo de texto.</span><span class="sxs-lookup"><span data-stu-id="05af2-127">The field appears as a text field.</span></span> |
| <span data-ttu-id="05af2-128">1</span><span class="sxs-lookup"><span data-stu-id="05af2-128">1</span></span>           | <span data-ttu-id="05af2-129">Inteiro</span><span class="sxs-lookup"><span data-stu-id="05af2-129">Integer</span></span>           | <span data-ttu-id="05af2-130">O valor é mostrado como um número sem casas decimais.</span><span class="sxs-lookup"><span data-stu-id="05af2-130">The value is shown as a number without decimal places.</span></span> |
| <span data-ttu-id="05af2-131">2</span><span class="sxs-lookup"><span data-stu-id="05af2-131">2</span></span>           | <span data-ttu-id="05af2-132">Real</span><span class="sxs-lookup"><span data-stu-id="05af2-132">Real</span></span>              | <span data-ttu-id="05af2-133">O valor é mostrado como um número com casas decimais.</span><span class="sxs-lookup"><span data-stu-id="05af2-133">The value is shown as a number that has decimal places.</span></span><p><span data-ttu-id="05af2-134">Para mostrar o valor real como uma moeda no aplicativo, use a propriedade **fieldExtenededType**.</span><span class="sxs-lookup"><span data-stu-id="05af2-134">To show the real value as a currency in the app, use the **fieldExtenededType** property.</span></span> <span data-ttu-id="05af2-135">Você pode usar a propriedade **numberOfDecimals** para definir o número de casas decimais exibidas.</span><span class="sxs-lookup"><span data-stu-id="05af2-135">You can use the **numberOfDecimals** property to set the number of decimal places that are shown.</span></span></p> |
| <span data-ttu-id="05af2-136">3</span><span class="sxs-lookup"><span data-stu-id="05af2-136">3</span></span>           | <span data-ttu-id="05af2-137">Data</span><span class="sxs-lookup"><span data-stu-id="05af2-137">Date</span></span>              | <span data-ttu-id="05af2-138">Os formatos de data são determinados pelo formato **Formato de data, hora e número** do usuário, que é especificado em **Preferências de idioma e país/região** de **Opções do usuário**.</span><span class="sxs-lookup"><span data-stu-id="05af2-138">Date formats are determined by the user's **Date, times, and number format** setting that is specified under **Language and country/region preference** in **User options**.</span></span> |
| <span data-ttu-id="05af2-139">4</span><span class="sxs-lookup"><span data-stu-id="05af2-139">4</span></span>           | <span data-ttu-id="05af2-140">Booleano</span><span class="sxs-lookup"><span data-stu-id="05af2-140">Boolean</span></span>           | |
| <span data-ttu-id="05af2-141">15</span><span class="sxs-lookup"><span data-stu-id="05af2-141">15</span></span>          | <span data-ttu-id="05af2-142">GUID</span><span class="sxs-lookup"><span data-stu-id="05af2-142">GUID</span></span>              | |
| <span data-ttu-id="05af2-143">16</span><span class="sxs-lookup"><span data-stu-id="05af2-143">16</span></span>          | <span data-ttu-id="05af2-144">Int64</span><span class="sxs-lookup"><span data-stu-id="05af2-144">Int64</span></span>             | |

- <span data-ttu-id="05af2-145">Se a propriedade **stringOptions** não for fornecida no objeto **TSTimesheetCustomField**, um campo de texto livre é fornecido ao usuário.</span><span class="sxs-lookup"><span data-stu-id="05af2-145">If the **stringOptions** property isn't provided on the **TSTimesheetCustomField** object, a free-text field is provided to the user.</span></span>

    <span data-ttu-id="05af2-146">A propriedade **stringLength** pode ser usada para definir o comprimento máximo de sequência de caracteres que os usuários poderão inserir.</span><span class="sxs-lookup"><span data-stu-id="05af2-146">The **stringLength** property can be used to set the maximum string length that users can enter.</span></span>

- <span data-ttu-id="05af2-147">Se a propriedade **stringOptions** for fornecida no objeto **TSTimesheetCustomField**, esses elementos da lista são os únicos valores que os usuários podem selecionar usando os botões de opção.</span><span class="sxs-lookup"><span data-stu-id="05af2-147">If the **stringOptions** property is provided on the **TSTimesheetCustomField** object, those list elements are the only values that users can select by using option buttons (radio buttons).</span></span>

    <span data-ttu-id="05af2-148">Nesse caso, o campo de sequência de caracteres pode atuar como um valor de enumeração para fins de entrada do usuário.</span><span class="sxs-lookup"><span data-stu-id="05af2-148">In this case, the string field can act as an enum value for the purpose of user entry.</span></span> <span data-ttu-id="05af2-149">Para salvar o valor no banco de dados como uma enumeração, mapeie manualmente o valor da sequência para o valor de enumeração antes de salvar no banco de dados usando a cadeia de comando (consulte “Usar cadeia de comando na classe TSTimesheetEntryService para salvar uma entrada de folha de ponto do aplicativo ao banco de dados” posteriormente neste tópico para obter um exemplo).</span><span class="sxs-lookup"><span data-stu-id="05af2-149">To save the value to the database as an enum, manually map the string value back to the enum value before you save to the database by using chain of command (see the “Use chain of command on the TSTimesheetEntryService class to save a timesheet entry from the app back to the database” section later in this topic for an example).</span></span>

### <a name="fieldextendedtype-tscustomfieldextendedtype"></a><span data-ttu-id="05af2-150">fieldExtendedType (TSCustomFieldExtendedType)</span><span class="sxs-lookup"><span data-stu-id="05af2-150">fieldExtendedType (TSCustomFieldExtendedType)</span></span>

<span data-ttu-id="05af2-151">Você pode usar essa propriedade para formatar valores reais como moeda.</span><span class="sxs-lookup"><span data-stu-id="05af2-151">You can use this property to format real values as currency.</span></span> <span data-ttu-id="05af2-152">Essa abordagem é aplicável somente quando o valor **fieldBaseType** é **Real**.</span><span class="sxs-lookup"><span data-stu-id="05af2-152">This approach is applicable only when the **fieldBaseType** value is **Real**.</span></span>

- <span data-ttu-id="05af2-153">**TSCustomFieldExtendedType:None** – Nenhuma formatação é aplicada.</span><span class="sxs-lookup"><span data-stu-id="05af2-153">**TSCustomFieldExtendedType:None** – No formatting is applied.</span></span>
- <span data-ttu-id="05af2-154">**TSCustomFieldExtendedType::Moeda** – Formate o valor como moeda.</span><span class="sxs-lookup"><span data-stu-id="05af2-154">**TSCustomFieldExtendedType::Currency** – Format the value as currency.</span></span>

    <span data-ttu-id="05af2-155">Quando a formatação da moeda está ativa, o campo **stringValue** pode ser usado para passar o código da moeda que deve ser exibido no aplicativo.</span><span class="sxs-lookup"><span data-stu-id="05af2-155">When currency formatting is active, the **stringValue** field can be used pass the currency code that should be shown in the app.</span></span> <span data-ttu-id="05af2-156">O valor é um valor somente leitura.</span><span class="sxs-lookup"><span data-stu-id="05af2-156">The value is a read-only value.</span></span>

    <span data-ttu-id="05af2-157">O campo **realValue** contém o valor monetário que deve ser salvo no banco de dados.</span><span class="sxs-lookup"><span data-stu-id="05af2-157">The **realValue** field contains the money amount that should be saved to the database.</span></span>

### <a name="fieldsection-tscustomfieldsection"></a><span data-ttu-id="05af2-158">fieldSection (TSCustomFieldSection)</span><span class="sxs-lookup"><span data-stu-id="05af2-158">fieldSection (TSCustomFieldSection)</span></span>

<span data-ttu-id="05af2-159">É possível usar essa propriedade para especificar onde o campo personalizado deve aparecer no aplicativo.</span><span class="sxs-lookup"><span data-stu-id="05af2-159">You can use this property specify where the custom field should appear in the app.</span></span>

- <span data-ttu-id="05af2-160">**TSCustomFieldSection::Cabeçalho** – O campo aparecerá na seção **Exibir mais detalhes** no aplicativo.</span><span class="sxs-lookup"><span data-stu-id="05af2-160">**TSCustomFieldSection::Header** – The field will appear in the **View more details** section in the app.</span></span> <span data-ttu-id="05af2-161">Esses campos são sempre somente leitura.</span><span class="sxs-lookup"><span data-stu-id="05af2-161">These fields are always read-only.</span></span>
- <span data-ttu-id="05af2-162">**TSCustomFieldSection::Linha** – O campo aparecerá depois de todos os campos da linha pronta para uso nas entradas de folha de ponto.</span><span class="sxs-lookup"><span data-stu-id="05af2-162">**TSCustomFieldSection::Line** – The field will appear after all the out-of-box line fields on timesheet entries.</span></span> <span data-ttu-id="05af2-163">Esses campos podem ser editáveis ou somente leitura.</span><span class="sxs-lookup"><span data-stu-id="05af2-163">These fields can be either editable or read-only.</span></span>

### <a name="fieldname-fieldnameshort"></a><span data-ttu-id="05af2-164">fieldName (FieldNameShort)</span><span class="sxs-lookup"><span data-stu-id="05af2-164">fieldName (FieldNameShort)</span></span>

<span data-ttu-id="05af2-165">Essa propriedade identifica o campo quando os valores fornecidos pelo aplicativo são salvos no banco de dados.</span><span class="sxs-lookup"><span data-stu-id="05af2-165">This property identifies the field when values that the app provides are saved back to the database.</span></span>

### <a name="tablename-tablenameshort"></a><span data-ttu-id="05af2-166">tableName (TableNameShort)</span><span class="sxs-lookup"><span data-stu-id="05af2-166">tableName (TableNameShort)</span></span>

<span data-ttu-id="05af2-167">Essa propriedade identifica o campo quando os valores fornecidos pelo aplicativo são salvos no banco de dados.</span><span class="sxs-lookup"><span data-stu-id="05af2-167">This property identifies the field when values that the app provides are saved back to the database.</span></span>

### <a name="iseditable-noyes"></a><span data-ttu-id="05af2-168">isEditable (NoYes)</span><span class="sxs-lookup"><span data-stu-id="05af2-168">isEditable (NoYes)</span></span>

<span data-ttu-id="05af2-169">Defina essa propriedade como **Sim** para especificar que o campo na seção de entrada de folha de ponto deve ser editável pelos usuários.</span><span class="sxs-lookup"><span data-stu-id="05af2-169">Set this property to **Yes** to specify that the field in the timesheet entry section should be editable by users.</span></span> <span data-ttu-id="05af2-170">Defina a propriedade **Não** para tornar o campo somente leitura.</span><span class="sxs-lookup"><span data-stu-id="05af2-170">Set the property to **No** to make the field read-only.</span></span>

### <a name="ismandatory-noyes"></a><span data-ttu-id="05af2-171">isMandatory (NoYes)</span><span class="sxs-lookup"><span data-stu-id="05af2-171">isMandatory (NoYes)</span></span>

<span data-ttu-id="05af2-172">Defina essa propriedade como **Sim** para especificar que o campo na seção de entrada de folha de ponto deve ser obrigatório.</span><span class="sxs-lookup"><span data-stu-id="05af2-172">Set this property to **Yes** to specify that the field in the timesheet entry section should be mandatory.</span></span>

### <a name="label-str"></a><span data-ttu-id="05af2-173">etiqueta (str)</span><span class="sxs-lookup"><span data-stu-id="05af2-173">label (str)</span></span>

<span data-ttu-id="05af2-174">Essa propriedade especifica o rótulo mostrado ao lado do campo no aplicativo.</span><span class="sxs-lookup"><span data-stu-id="05af2-174">This property specifies the label that is shown next the field in the app.</span></span>

### <a name="stringoptions-list-of-strings"></a><span data-ttu-id="05af2-175">stringOptions (lista de caracteres)</span><span class="sxs-lookup"><span data-stu-id="05af2-175">stringOptions (List of Strings)</span></span>

<span data-ttu-id="05af2-176">Essa propriedade é aplicável somente quando **fieldBaseType** é definido como **Sequência de caracteres**.</span><span class="sxs-lookup"><span data-stu-id="05af2-176">This property is applicable only when **fieldBaseType** is set to **String**.</span></span> <span data-ttu-id="05af2-177">Se **stringOptions** for definido, os valores de string disponíveis para seleção por meio de botões de opção são especificados pelas sequências de caracteres na lista.</span><span class="sxs-lookup"><span data-stu-id="05af2-177">If **stringOptions** is set, the string values that are available for selection via option buttons (radio buttons) are specified by the strings in the list.</span></span> <span data-ttu-id="05af2-178">Se nenhuma sequência de caracteres for fornecida, a entrada de texto livre no campo de sequência de caracteres será permitida (consulte a seção “Usar cadeia de comando na classe TSTimesheetEntryService para salvar uma entrada de folha de ponto do aplicativo ao banco de dados” posteriormente neste tópico para obter um exemplo) .</span><span class="sxs-lookup"><span data-stu-id="05af2-178">If no strings are provided, free-text entry in the string field is allowed (see the “Use chain of command on the TSTimesheetEntryService class to save a timesheet entry from the app back to the database” section later in this topic for an example).</span></span>

### <a name="stringlength-int"></a><span data-ttu-id="05af2-179">stringLength (int)</span><span class="sxs-lookup"><span data-stu-id="05af2-179">stringLength (int)</span></span>

<span data-ttu-id="05af2-180">Essa propriedade especifica o comprimento máximo de um campo de sequência de caracteres.</span><span class="sxs-lookup"><span data-stu-id="05af2-180">This property specifies the maximum length for a string field.</span></span> <span data-ttu-id="05af2-181">É aplicável somente quando **fieldBaseType** é definido como **Sequência de caracteres**.</span><span class="sxs-lookup"><span data-stu-id="05af2-181">It's applicable only when **fieldBaseType** is set to **String**.</span></span>

### <a name="numberofdecimals-int"></a><span data-ttu-id="05af2-182">numberOfDecimals (int)</span><span class="sxs-lookup"><span data-stu-id="05af2-182">numberOfDecimals (int)</span></span>

<span data-ttu-id="05af2-183">Essa propriedade especifica o número de casas decimais exibidas para um campo real.</span><span class="sxs-lookup"><span data-stu-id="05af2-183">This property specifies the number of decimal places that are shown for a real field.</span></span> <span data-ttu-id="05af2-184">É aplicável somente quando **fieldBaseType** é definido como **Real**.</span><span class="sxs-lookup"><span data-stu-id="05af2-184">It's applicable only when **fieldBaseType** is set to **Real**.</span></span>

### <a name="ordersequence-int"></a><span data-ttu-id="05af2-185">orderSequence (int)</span><span class="sxs-lookup"><span data-stu-id="05af2-185">orderSequence (int)</span></span>

<span data-ttu-id="05af2-186">Essa propriedade controla a ordem em que os campos personalizados são mostrados no aplicativo quando mais de um campo personalizado é especificado.</span><span class="sxs-lookup"><span data-stu-id="05af2-186">This property controls the order in which the custom fields are shown in the app when more than one custom field is specified.</span></span> <span data-ttu-id="05af2-187">Campos com números inferiores são mostrados primeiro.</span><span class="sxs-lookup"><span data-stu-id="05af2-187">Fields that have lower numbers are shown first.</span></span>

### <a name="booleanvalue-boolean"></a><span data-ttu-id="05af2-188">booleanValue (booliano)</span><span class="sxs-lookup"><span data-stu-id="05af2-188">booleanValue (boolean)</span></span>

<span data-ttu-id="05af2-189">Para os campos do tipo **Booliano**, essa propriedade transmite o valor booliano do campo entre o servidor e o aplicativo.</span><span class="sxs-lookup"><span data-stu-id="05af2-189">For fields of the **Boolean** type, this property passes the Boolean value of the field between the server and the app.</span></span>

### <a name="guidvalue-guid"></a><span data-ttu-id="05af2-190">guidValue (guid)</span><span class="sxs-lookup"><span data-stu-id="05af2-190">guidValue (guid)</span></span>

<span data-ttu-id="05af2-191">Para campos do tipo **GUID**, essa propriedade transmite o valor de identificador global exclusivo (GUID) do campo entre o servidor e o aplicativo.</span><span class="sxs-lookup"><span data-stu-id="05af2-191">For fields of the **GUID** type, this property passes the globally unique identifier (GUID) value of the field between the server and the app.</span></span>

### <a name="int64value-int64"></a><span data-ttu-id="05af2-192">int64Value (int64)</span><span class="sxs-lookup"><span data-stu-id="05af2-192">int64Value (int64)</span></span>

<span data-ttu-id="05af2-193">Para os campos do tipo **Int64**, essa propriedade transmite o valor int64 do campo entre o servidor e o aplicativo.</span><span class="sxs-lookup"><span data-stu-id="05af2-193">For fields of the **Int64** type, this property passes the int64 value of the field between the server and the app.</span></span>

### <a name="intvalue-int"></a><span data-ttu-id="05af2-194">intValue (int)</span><span class="sxs-lookup"><span data-stu-id="05af2-194">intValue (int)</span></span>

<span data-ttu-id="05af2-195">Para os campos do tipo **Int**, essa propriedade transmite o valor int do campo entre o servidor e o aplicativo.</span><span class="sxs-lookup"><span data-stu-id="05af2-195">For fields of the **Int** type, this property passes the int value of the field between the server and the app.</span></span>

### <a name="realvalue-real"></a><span data-ttu-id="05af2-196">realValue (real)</span><span class="sxs-lookup"><span data-stu-id="05af2-196">realValue (real)</span></span>

<span data-ttu-id="05af2-197">Para os campos do tipo **Real**, essa propriedade transmite o valor real do campo entre o servidor e o aplicativo.</span><span class="sxs-lookup"><span data-stu-id="05af2-197">For fields of the **Real** type, this property passes the real value of the field between the server and the app .</span></span>

### <a name="stringvalue-str"></a><span data-ttu-id="05af2-198">stringValue (str)</span><span class="sxs-lookup"><span data-stu-id="05af2-198">stringValue (str)</span></span>

<span data-ttu-id="05af2-199">Para os campos do tipo **Sequência de caracteres**, essa propriedade transmite o valor de sequência de caracteres do campo entre o servidor e o aplicativo.</span><span class="sxs-lookup"><span data-stu-id="05af2-199">For fields of the **String** type, this property passes the string value of the field between the server and the app.</span></span> <span data-ttu-id="05af2-200">Ela também é usada em campos do tipo **Real** que são formatados como moeda.</span><span class="sxs-lookup"><span data-stu-id="05af2-200">It's also used for fields of the **Real** type that are formatted as currency.</span></span> <span data-ttu-id="05af2-201">Para esses campos, a propriedade é usada para transmitir o código da moeda para o aplicativo.</span><span class="sxs-lookup"><span data-stu-id="05af2-201">For those fields, the property is used to pass the currency code to the app.</span></span>

### <a name="datevalue-date"></a><span data-ttu-id="05af2-202">dateValue (data)</span><span class="sxs-lookup"><span data-stu-id="05af2-202">dateValue (date)</span></span>

<span data-ttu-id="05af2-203">Para os campos do tipo **Data**, essa propriedade transmite o valor de data do campo entre o servidor e o aplicativo.</span><span class="sxs-lookup"><span data-stu-id="05af2-203">For fields of the **Date** type, this property passes the date value of the field between the server and the app.</span></span>

## <a name="show-and-save-a-custom-field-in-the-timesheet-entry-section"></a><span data-ttu-id="05af2-204">Mostrar e salvar um campo personalizado na seção de entrada de folha de ponto</span><span class="sxs-lookup"><span data-stu-id="05af2-204">Show and save a custom field in the timesheet entry section</span></span>

<span data-ttu-id="05af2-205">Veja abaixo uma captura de tela do aplicativo móvel de uma criação de entrada de folha de ponto.</span><span class="sxs-lookup"><span data-stu-id="05af2-205">Below is a screenshot from the mobile app of a timesheet entry creation.</span></span> <span data-ttu-id="05af2-206">Ela mostra os campos prontos para uso e um campo personalizado na seção "Entrada de tempo" chamada "Sequência de caracteres de teste" com um valor de enumeração da "Segunda opção" já definido.</span><span class="sxs-lookup"><span data-stu-id="05af2-206">It shows the out-of-box fields and a custom field in the "Time entry" section called "Test string" with an enum value of "Second option" already set.</span></span>

![Campo personalizado de sequência de caracteres de teste no aplicativo](media/timesheet-entry.jpg)



<span data-ttu-id="05af2-208">Veja abaixo uma captura de tela do aplicativo móvel do usuário, selecionando uma das opções de enumeração disponíveis para o campo personalizado "Sequência de caracteres de teste".</span><span class="sxs-lookup"><span data-stu-id="05af2-208">Below is a screenshot from the mobile app of the user selecting one of the enum options available for the "Test string" custom field.</span></span>  <span data-ttu-id="05af2-209">As duas opções são "Primeira opção" e "Segunda opção" mostradas como botões de opção.</span><span class="sxs-lookup"><span data-stu-id="05af2-209">The two options are "First option" and "Second option" shown as radio buttons.</span></span> <span data-ttu-id="05af2-210">A segunda opção está atualmente selecionada.</span><span class="sxs-lookup"><span data-stu-id="05af2-210">The second option is currently selected.</span></span>

![Botões de opção para o campo personalizado de sequência de caracteres de teste](media/enum-option.jpg)



### <a name="extend-the-tstimesheetline-table-so-that-it-has-a-custom-field"></a><span data-ttu-id="05af2-212">Estenda a tabela TSTimesheetLine para que ela tenha um campo personalizado</span><span class="sxs-lookup"><span data-stu-id="05af2-212">Extend the TSTimesheetLine table so that it has a custom field</span></span>

<span data-ttu-id="05af2-213">Em cenários típicos, é provável que os dados de um campo personalizado na seção de entrada de folha de ponto sejam salvos na tabela TSTimesheetLine.</span><span class="sxs-lookup"><span data-stu-id="05af2-213">In typical scenarios, it's likely that the data for a custom field in the timesheet entry section will be saved to the TSTimesheetLine table.</span></span> <span data-ttu-id="05af2-214">Contudo, outras tabelas podem ser usadas se os dados puderem ser recuperados com base em um registro TSTimesheetTrans fornecido ou se ele não tiver contexto de registro específico (por exemplo, se o campo estiver configurado como somente leitura nos parâmetros do projeto).</span><span class="sxs-lookup"><span data-stu-id="05af2-214">However, other tables can be used if the data can be retrieved based on a TSTimesheetTrans record that is provided, or if it doesn't have specific record context (for example, if the field is set as read-only in the project parameters).</span></span>

<span data-ttu-id="05af2-215">Observe que os campos personalizados não precisam ter nenhum registro de banco de dados de apoio.</span><span class="sxs-lookup"><span data-stu-id="05af2-215">Note that custom fields don't have to have any backing database records.</span></span> <span data-ttu-id="05af2-216">Eles podem ser gerados dinamicamente com base na lógica X++.</span><span class="sxs-lookup"><span data-stu-id="05af2-216">They can be dynamically generated based on X++ logic.</span></span> <span data-ttu-id="05af2-217">Essa abordagem pode ser útil em cenários somente leitura (consulte a seção “Usar cadeia de comando na classe TSTimesheetDetails, no comando buildCustomFieldListForHeader para preencher detalhes da folha de ponto” para obter um exemplo de valores de campos personalizados gerados dinamicamente).</span><span class="sxs-lookup"><span data-stu-id="05af2-217">This approach can be useful in read-only scenarios (see the “Use chain of command on the TSTimesheetDetails class, buildCustomFieldListForHeader method to fill in timesheet details” section for an example of dynamically generated custom field values.)</span></span>

<span data-ttu-id="05af2-218">Veja abaixo uma captura de tela do Visual Studio da árvore de objetos de aplicativo.</span><span class="sxs-lookup"><span data-stu-id="05af2-218">Below is a screenshot from Visual Studio of the Application Object Tree.</span></span> <span data-ttu-id="05af2-219">Ela mostra uma extensão da tabela TSTimesheetLine com o campo TestLineString adicionado como um campo personalizado.</span><span class="sxs-lookup"><span data-stu-id="05af2-219">It shows an extension of the TSTimesheetLine table with the TestLineString field added as a custom field.</span></span>

![Sequência de caracteres da linha](media/b6756b4a3fc5298093327a088a7710fd.png)

### <a name="use-chain-of-command-on-the-buildcustomfieldlist-method-of-the-tstimesheetsettings-class-to-show-a-field-in-the-timesheet-entry-section"></a><span data-ttu-id="05af2-221">Use cadeia de comando no método buildCustomFieldList da classe TSTimesheetSettings para mostrar um campo na seção de entrada de folha de ponto</span><span class="sxs-lookup"><span data-stu-id="05af2-221">Use chain of command on the buildCustomFieldList method of the TSTimesheetSettings class to show a field in the timesheet entry section</span></span>

<span data-ttu-id="05af2-222">Este código controla as configurações de exibição do campo no aplicativo.</span><span class="sxs-lookup"><span data-stu-id="05af2-222">This code controls the display settings for the field in the app.</span></span> <span data-ttu-id="05af2-223">Por exemplo, ele controla o tipo de campo, o rótulo, se o campo é obrigatório e em qual seção o campo aparece.</span><span class="sxs-lookup"><span data-stu-id="05af2-223">For example, it controls the type of field, the label, whether the field is mandatory, and what section the field appears in.</span></span>

<span data-ttu-id="05af2-224">O exemplo a seguir mostra um campo de sequência de caracteres nas entradas de hora.</span><span class="sxs-lookup"><span data-stu-id="05af2-224">The following example shows a string field on time entries.</span></span> <span data-ttu-id="05af2-225">Esse campo tem duas opções, **Primeira opção** e **Segunda opção**, que estão disponíveis por meio de botões de opção.</span><span class="sxs-lookup"><span data-stu-id="05af2-225">This field has two options, **First option** and **Second option**, that are available via option buttons (radio buttons).</span></span> <span data-ttu-id="05af2-226">O campo no aplicativo é associado ao campo **TestLineString** que é adicionado à tabela TSTimesheetLine.</span><span class="sxs-lookup"><span data-stu-id="05af2-226">The field in the app is associated with the **TestLineString** field that is added to the TSTimesheetLine table.</span></span>

<span data-ttu-id="05af2-227">Observe o uso do método **TSTimesheetCustomField::newFromMetatdata()** para simplificar a inicialização das propriedades do campo personalizado: **fieldBaseType**, **tableName**, **fieldname**, **label**, **isEditable**, **isMandatory**, **stringLength** e **numberOfDecimals**.</span><span class="sxs-lookup"><span data-stu-id="05af2-227">Note the use of the **TSTimesheetCustomField::newFromMetatdata()** method to simplify the initialization of the custom field properties: **fieldBaseType**, **tableName**, **fieldname**, **label**, **isEditable**, **isMandatory**, **stringLength**, and **numberOfDecimals**.</span></span> <span data-ttu-id="05af2-228">Você também pode definir esses parâmetros manualmente, como preferir.</span><span class="sxs-lookup"><span data-stu-id="05af2-228">You can also set these parameters manually, as you prefer.</span></span>

```
...
[ExtensionOf(classStr(TsTimesheetSettings))]
final class TSTimesheetSettings_Extension
{
    protected List buildCustomFieldList()
    {
        List customFieldList = next buildCustomFieldList();
        TSTimesheetCustomField tsTimesheetCustomField;
        tsTimesheetCustomField =
        TSTimesheetCustomField::newFromMetadata(tableNum(TsTimesheetLine),
        fieldNum(TSTimesheetLine, TestLineString));
        tsTimesheetCustomField.parmFieldSection(TSCustomFieldSection::Line);
        tsTimesheetCustomField.parmOrderSequence(1);
        List stringOptions = new List(Types::String);
        stringOptions.addEnd('First option');
        stringOptions.addEnd('Second option');
        tsTimesheetCustomField.parmStringOptions(stringOptions);
        customFieldList.addEnd(tsTimesheetCustomField);
        return customFieldList;
    }
}
...
```

### <a name="use-chain-of-command-on-the-buildcustomfieldlistforentry-method-of-the-tstimesheetentry-class-to-enter-values-in-a-timesheet-entry"></a><span data-ttu-id="05af2-229">Use cadeia de comando no método buildCustomFieldListForEntry da classe TSTimesheetEntry para inserir valores em uma entrada de folha de ponto</span><span class="sxs-lookup"><span data-stu-id="05af2-229">Use chain of command on the buildCustomFieldListForEntry method of the TSTimesheetEntry class to enter values in a timesheet entry</span></span>

<span data-ttu-id="05af2-230">O método **buildCustomFieldListForEntry** é usado para inserir valores nas linhas de folha de ponto salvas no aplicativo móvel.</span><span class="sxs-lookup"><span data-stu-id="05af2-230">The **buildCustomFieldListForEntry** method is used to enter values on the saved timesheet lines in the mobile app.</span></span> <span data-ttu-id="05af2-231">Leva um registro TSTimesheetTrans como um parâmetro.</span><span class="sxs-lookup"><span data-stu-id="05af2-231">It takes a TSTimesheetTrans record as a parameter.</span></span> <span data-ttu-id="05af2-232">Os campos desse registro podem ser usados para preencher o valor do campo personalizado no aplicativo.</span><span class="sxs-lookup"><span data-stu-id="05af2-232">Fields from that record can be used to fill in the custom field value in the app.</span></span>

```
...
[ExtensionOf(classStr(TsTimesheetEntry))]
final class TsTimesheetEntry_Extension
{
    protected List buildCustomFieldListForEntry(TSTimesheetTrans _tsTimesheetTrans)
    {
        List customFieldList = next buildCustomFieldListForEntry(_tsTimesheetTrans);
        TSTimesheetLine tsTimesheetLine = _tsTimesheetTrans.timesheetLine();
        TSTimesheetCustomField tsTimesheetCustomField;
        tsTimesheetCustomField =
        TSTimesheetCustomField::newFromMetadata(tableNum(TsTimesheetLine),
        fieldNum(TSTimesheetLine, TestLineString));
        tsTimesheetCustomField.parmFieldSection(TSCustomFieldSection::Line);
        tsTimesheetCustomField.parmOrderSequence(1);
        tsTimesheetCustomField.parmStringValue(tsTimesheetLine.TestLineString);
        List stringOptions = new List(Types::String);
        stringOptions.addEnd('First option');
        stringOptions.addEnd('second option;);
        tsTimesheetCustomField.parmStringOptions(stringOptions);
        customFieldList.addEnd(tsTimesheetCustomField);
        return customFieldList;
    }
}
...
```

### <a name="use-chain-of-command-on-the-tstimesheetentryservice-class-to-save-a-timesheet-entry-from-the-app-back-to-the-database"></a><span data-ttu-id="05af2-233">Use a cadeia de comando na classe TSTimesheetEntryService para salvar uma entrada de folha de ponto do aplicativo no banco de dados</span><span class="sxs-lookup"><span data-stu-id="05af2-233">Use chain of command on the TSTimesheetEntryService class to save a timesheet entry from the app back to the database</span></span>

<span data-ttu-id="05af2-234">Para salvar um campo personalizado no banco de dados em uso típico, você deve estender vários métodos:</span><span class="sxs-lookup"><span data-stu-id="05af2-234">To save a custom field back to the database in typical usage, you must extend multiple methods:</span></span>

- <span data-ttu-id="05af2-235">O método **timesheetLineNeedsUpdating** é usado para determinar se o registro de linha foi alterado pelo usuário no aplicativo e deve ser salvo no banco de dados.</span><span class="sxs-lookup"><span data-stu-id="05af2-235">The **timesheetLineNeedsUpdating** method is used to determine whether the line record has been changed by the user in the app and must be saved to the database.</span></span> <span data-ttu-id="05af2-236">Se o desempenho não é uma preocupação, esse método pode ser simplificado para que ele sempre retorne **verdadeiro**.</span><span class="sxs-lookup"><span data-stu-id="05af2-236">If performance isn't a concern, this method can be simplified so that it always returns **true**.</span></span>
- <span data-ttu-id="05af2-237">Os métodos **populateTimesheetLineFromEntryDuringCreate** e **populateTimesheetLineFromEntryDuringUpdate** podem ser estendidos para inserir valores no registro do banco de dados TSTimesheetLine a partir do registro de contrato de dados TSTimesheetEntry fornecido.</span><span class="sxs-lookup"><span data-stu-id="05af2-237">The **populateTimesheetLineFromEntryDuringCreate** and **populateTimesheetLineFromEntryDuringUpdate** methods can be extended so that they enter values in the TSTimesheetLine database record from the TSTimesheetEntry data contract record that is provided.</span></span> <span data-ttu-id="05af2-238">No exemplo a seguir, observe como o mapeamento entre o campo do banco de dados e o campo de entrada é feito manualmente por meio do código X++.</span><span class="sxs-lookup"><span data-stu-id="05af2-238">In the example that follows, notice how the mapping between the database field and the entry field is manually done via X++ code.</span></span>
- <span data-ttu-id="05af2-239">O método **populateTimesheetWeekFromEntry** também pode ser estendido se o campo personalizado mapeado para o objeto **TSTimesheetEntry** precisar gravar na tabela de banco de dados TSTimesheetLineweek.</span><span class="sxs-lookup"><span data-stu-id="05af2-239">The **populateTimesheetWeekFromEntry** method can also be extended if the custom field that is mapped to the **TSTimesheetEntry** object must write back to the TSTimesheetLineweek database table.</span></span>

> [!NOTE]
> <span data-ttu-id="05af2-240">O exemplo a seguir salva o valor **firstOption** ou **secondOption** que o usuário seleciona no banco de dados como um valor de sequência de caracteres não processado.</span><span class="sxs-lookup"><span data-stu-id="05af2-240">The following example saves the **firstOption** or **secondOption** value that the user selects to the database as a raw string value.</span></span> <span data-ttu-id="05af2-241">Se o campo do banco de dados for um campo do tipo **Enumeração**, esses valores poderão ser mapeados manualmente para um valor de enumeração e, em seguida, salvos em um campo de enumeração na tabela do banco de dados.</span><span class="sxs-lookup"><span data-stu-id="05af2-241">If the database field is a field of the **Enum** type, those values can be manually mapped to an enum value and then saved to an enum field on the database table.</span></span>

```
...
[ExtensionOf(classStr(TSTimesheetEntryService))]
final class TSTimesheetEntryService_Extension
{
    protected boolean timesheetLineNeedsUpdating(TSTimesheetLine _tsTimesheetLine,
    TsTimesheetEntry _tsTimesheetEntry)
    {
        boolean ret = next timesheetLineNeedsUpdating(_tsTimesheetLine,
        _tsTimesheetEntry);
        if (!ret)
        {
            */ Loop through custom fields to see if value needs updating*/
            ListEnumerator enumerator =  _tsTimesheetEntry.parmCustomFields().getEnumerator();
            while (enumerator.moveNext())
            {
                TSTimesheetCustomField customField = enumerator.current();
                if (customField.parmFieldName() == fieldId2Name(tableNum(TsTimesheetLine),
                fieldNum(TSTimesheetLine, TestLineString)))
                {
                    */ If Custom field value for TestLineString field has changed, We need to update the timesheet line.*/
                    if (_tsTimesheetLine.TestLineString != customField.parmStringValue())
                    {
                        ret = true;
                    }
                }
            }
        }
        return ret;
    }
    protected void populateTimesheetLineFromEntryDuringCreate(TSTimesheetLine
    _tsTimesheetLine, TSTimesheetEntry _tsTimesheetEntry)
    {
        next populateTimesheetLineFromEntryDuringCreate(_tsTimesheetLine,
        _tsTimesheetEntry);
        this.populateTimesheetLineFromCustomFields(_tsTimesheetLine,
        _tsTimesheetEntry);
        }
        protected void populateTimesheetLineFromEntryDuringUpdate(TSTimesheetLine
        \_tsTimesheetLine, TSTimesheetEntry _tsTimesheetEntry)
        {
            next populateTimesheetLineFromEntryDuringUpdate(_tsTimesheetLine,
            _tsTimesheetEntry);
            this.populateTimesheetLineFromCustomFields(_tsTimesheetLine,
            _tsTimesheetEntry);
        }
        private void populateTimesheetLineFromCustomFields(TSTimesheetLine
        _tsTimesheetLine, TSTimesheetEntry _tsTimesheetEntry)
        {
            ListEnumerator enumerator =
            _tsTimesheetEntry.parmCustomFields().getEnumerator();
            while (enumerator.moveNext())
            {
                TSTimesheetCustomField customField = enumerator.current();
                if (customField.parmFieldName() == fieldId2Name(tableNum(TsTimesheetLine),
                fieldNum(TSTimesheetLine, TestLineString)))
                {
                    _tsTimesheetLine.TestLineString = customField.parmStringValue();
                }
            }
        }
    }
...
```

## <a name="show-a-custom-field-in-the-timesheet-header-section"></a><span data-ttu-id="05af2-242">Mostrar um campo personalizado na seção de cabeçalho de folha de ponto</span><span class="sxs-lookup"><span data-stu-id="05af2-242">Show a custom field in the timesheet header section</span></span>

<span data-ttu-id="05af2-243">Veja abaixo uma captura de tela do aplicativo móvel de um usuário que visualiza uma folha de ponto.</span><span class="sxs-lookup"><span data-stu-id="05af2-243">Below is a screenshot from the mobile app of a user viewing a timesheet.</span></span> <span data-ttu-id="05af2-244">O botão "Mais informações" foi selecionado no canto superior direito para mostrar a opção "Exibir mais detalhes".</span><span class="sxs-lookup"><span data-stu-id="05af2-244">The "More information" button has been selected in the upper-right corner to show the "View more details" option.</span></span>  

![Comando Exibir mais detalhes](media/show-more.png)



<span data-ttu-id="05af2-246">Veja abaixo uma captura de tela do aplicativo móvel mostrando a seção “Mais” de uma folha de ponto.</span><span class="sxs-lookup"><span data-stu-id="05af2-246">Below is a screenshot from the mobile app showing the “More” section of a timesheet.</span></span> <span data-ttu-id="05af2-247">Um campo personalizado chamado “Taxa de utilização desta folha de ponto (campo personalizado computado)” foi adicionado à seção de cabeçalho de folha de ponto.</span><span class="sxs-lookup"><span data-stu-id="05af2-247">A custom field called “Utilization rate of this timesheet (computed custom field)” has been added to the timesheet header section.</span></span> <span data-ttu-id="05af2-248">Um valor somente leitura de "0,667" é definido no campo personalizado.</span><span class="sxs-lookup"><span data-stu-id="05af2-248">A read-only value of "0.667" is set on the custom field.</span></span>

![Seção Mais](media/more-section.jpg)



### <a name="extend-the-tstimesheettable-table-so-that-it-has-a-custom-field"></a><span data-ttu-id="05af2-250">Estenda a tabela TSTimesheetTable para que ela tenha um campo personalizado</span><span class="sxs-lookup"><span data-stu-id="05af2-250">Extend the TSTimesheetTable table so that it has a custom field</span></span>

<span data-ttu-id="05af2-251">Em cenários típicos, é provável que os dados de um campo personalizado na seção de cabeçalho será extraído da tabela TSTimesheetHeader.</span><span class="sxs-lookup"><span data-stu-id="05af2-251">In typical scenarios, it's likely that the data for a custom field in the header section will be pulled from the TSTimesheetHeader table.</span></span> <span data-ttu-id="05af2-252">Contudo, outras tabelas podem ser usadas se os dados puderem ser recuperados com base em um registro TSTimesheetTable fornecido ou se ele não tiver contexto de registro específico (por exemplo, se o campo estiver configurado como somente leitura nos parâmetros do projeto).</span><span class="sxs-lookup"><span data-stu-id="05af2-252">However, other tables can be used if the data can be retrieved based on a TSTimesheetTable record that is provided, or if it doesn't have specific record context (for example, if the field is set as read-only in the project parameters).</span></span>

<span data-ttu-id="05af2-253">Observe que os campos personalizados não precisam ter nenhum registro de banco de dados de apoio.</span><span class="sxs-lookup"><span data-stu-id="05af2-253">Note that custom fields don't have to have any backing database records.</span></span> <span data-ttu-id="05af2-254">Eles podem ser gerados dinamicamente com base na lógica X++.</span><span class="sxs-lookup"><span data-stu-id="05af2-254">They can be dynamically generated based on X++ logic.</span></span> <span data-ttu-id="05af2-255">O exemplo a seguir mostra essa abordagem.</span><span class="sxs-lookup"><span data-stu-id="05af2-255">The example that follows shows this approach.</span></span>

<span data-ttu-id="05af2-256">Os campos na seção de cabeçalho são sempre somente leitura no aplicativo.</span><span class="sxs-lookup"><span data-stu-id="05af2-256">Fields in the header section are always read-only in the app.</span></span>

### <a name="use-chain-of-command-on-the-buildcustomfieldlist-method-of-the-tstimesheetsettings-class-to-show-a-field-in-the-header-section"></a><span data-ttu-id="05af2-257">Use cadeia de comando no método buildCustomFieldList da classe TSTimesheetSettings para mostrar um campo na seção do cabeçalho</span><span class="sxs-lookup"><span data-stu-id="05af2-257">Use chain of command on the buildCustomFieldList method of the TSTimesheetSettings class to show a field in the header section</span></span>

<span data-ttu-id="05af2-258">Este código controla as configurações de exibição do campo no aplicativo.</span><span class="sxs-lookup"><span data-stu-id="05af2-258">This code controls the display settings for the field in the app.</span></span> <span data-ttu-id="05af2-259">Por exemplo, ele controla o tipo de campo, o rótulo, se o campo é obrigatório e em qual seção o campo aparece.</span><span class="sxs-lookup"><span data-stu-id="05af2-259">For example, it controls the type of field, the label, whether the field is mandatory, and what section the field appears in.</span></span>

<span data-ttu-id="05af2-260">O exemplo a seguir mostra um valor computado na seção de cabeçalho no aplicativo.</span><span class="sxs-lookup"><span data-stu-id="05af2-260">The following example shows a computed value in the header section in the app.</span></span>

```
...
[ExtensionOf(classStr(TsTimesheetSettings))]
final class TSTimesheetSettings_Extension
{
    protected List buildCustomFieldList()
    {
        List customFieldList = next buildCustomFieldList();
        TSTimesheetCustomField tsTimesheetCustomField;

        */ Computed utilization rate*/
        tsTimesheetCustomField = new TSTimesheetCustomField();
        tsTimesheetCustomField.parmFieldBaseType(Types::Real);
        tsTimesheetCustomField.parmLabel("Utilization rate of this timesheet (computed
        custom field)");
        tsTimesheetCustomField.parmFieldSection(TSCustomFieldSection::Header);
        tsTimesheetCustomField.parmOrderSequence(2);
        tsTimesheetCustomField.parmNumberOfDecimals(3);
        customFieldList.addEnd(tsTimesheetCustomField);
        return customFieldList;
    }
}
...
```

### <a name="use-chain-of-command-on-the-buildcustomfieldlistforheader-method-of-the-tstimesheetdetails-class-to-fill-in-timesheet-details"></a><span data-ttu-id="05af2-261">Use cadeia de comando no método buildCustomFieldListForHeader da classe TSTimesheetDetails para preencher os detalhes de folha de ponto</span><span class="sxs-lookup"><span data-stu-id="05af2-261">Use chain of command on the buildCustomFieldListForHeader method of the TSTimesheetDetails class to fill in timesheet details</span></span>

<span data-ttu-id="05af2-262">O método **buildCustomFieldListForHeader** é usado para preencher os detalhes do cabeçalho de folha de ponto no aplicativo para dispositivos móveis.</span><span class="sxs-lookup"><span data-stu-id="05af2-262">The **buildCustomFieldListForHeader** method is used to fill in the timesheet header details in the mobile app.</span></span> <span data-ttu-id="05af2-263">Leva um registro TSTimesheetTable como um parâmetro.</span><span class="sxs-lookup"><span data-stu-id="05af2-263">It takes a TSTimesheetTable record as a parameter.</span></span> <span data-ttu-id="05af2-264">Os campos desse registro podem ser usados para preencher o valor do campo personalizado no aplicativo.</span><span class="sxs-lookup"><span data-stu-id="05af2-264">Fields from that record can be used to fill in the custom field value in the app.</span></span> <span data-ttu-id="05af2-265">O exemplo a seguir não lê nenhum valor do banco de dados.</span><span class="sxs-lookup"><span data-stu-id="05af2-265">The following example doesn't read any values from the database.</span></span> <span data-ttu-id="05af2-266">Em vez disso, ele usa a lógica X++ para gerar um valor computado que é exibido no aplicativo.</span><span class="sxs-lookup"><span data-stu-id="05af2-266">Instead, it uses X++ logic to generate a computed value that is then shown in the app.</span></span>


```
...
[ExtensionOf(classStr(TSTimesheetDetails))]
final class TSTimesheetDetails_Extension
{
    protected List buildCustomFieldListForHeader(TSTimesheetTable
    _tsTimesheetTable)
    {
        List customFieldList = next buildCustomFieldListForHeader(_tsTimesheetTable);
        TSTimesheetCustomField tsTimesheetCustomField;

        */ Computed utilization rate*/
        tsTimesheetCustomField = new TSTimesheetCustomField();
        tsTimesheetCustomField.parmFieldBaseType(Types::Real);
        tsTimesheetCustomField.parmLabel("Utilization rate of this timesheet (computed
        custom field)");
        tsTimesheetCustomField.parmFieldSection(TSCustomFieldSection::Header);
        tsTimesheetCustomField.parmOrderSequence(2);
        tsTimesheetCustomField.parmNumberOfDecimals(3);
        real utilizationRate = 0;
        if (_tsTimesheetTable.totalHours() != 0)
        {
            utilizationRate = _tsTimesheetTable.totalHoursBillable() /
            _tsTimesheetTable.totalHours();
        }
        tsTimesheetCustomField.parmRealValue(utilizationRate);
        customFieldList.addEnd(tsTimesheetCustomField);
        return customFieldList;
    }
}
...
```

## <a name="other-configurabilityextensibility-opportunities"></a><span data-ttu-id="05af2-267">Outras oportunidades de configurabilidade/extensibilidade</span><span class="sxs-lookup"><span data-stu-id="05af2-267">Other configurability/extensibility opportunities</span></span>

### <a name="adding-additional-validation-for-the-app"></a><span data-ttu-id="05af2-268">Adição de validação adicional para o aplicativo</span><span class="sxs-lookup"><span data-stu-id="05af2-268">Adding additional validation for the app</span></span>

<span data-ttu-id="05af2-269">A lógica existente para a funcionalidade de folha de ponto no nível do banco de dados ainda funcionará conforme o esperado.</span><span class="sxs-lookup"><span data-stu-id="05af2-269">Existing logic for timesheet functionality at the database level will still work as expected.</span></span> <span data-ttu-id="05af2-270">Para interromper a conclusão de salvar ou enviar operações e mostrar uma mensagem de erro específica, você pode adicionar **gerar erro ("mensagem para usuário")** ao código por meio de uma cadeia de extensão de comando.</span><span class="sxs-lookup"><span data-stu-id="05af2-270">To interrupt the completion of save or submit operations and show a specific error message, you can add **throw error("message to user")** to the code via a chain of command extension.</span></span> <span data-ttu-id="05af2-271">Veja três exemplos de métodos extensíveis úteis:</span><span class="sxs-lookup"><span data-stu-id="05af2-271">Here are three examples of useful extensible methods:</span></span>

- <span data-ttu-id="05af2-272">Se **validateWrite** na tabela TSTimesheetLine retornar **falso** durante uma operação de salvamento para uma linha da folha de ponto, uma mensagem de erro será mostrada no aplicativo móvel.</span><span class="sxs-lookup"><span data-stu-id="05af2-272">If **validateWrite** on the TSTimesheetLine table returns **false** during a save operation for a timesheet line, an error message is shown in the mobile app.</span></span>
- <span data-ttu-id="05af2-273">Se **validateSubmit** na tabela TSTimesheetTable retornar **falso** durante o envio da folha de ponto no aplicativo, uma mensagem de erro é mostrada ao usuário.</span><span class="sxs-lookup"><span data-stu-id="05af2-273">If **validateSubmit** on the TSTimesheetTable table returns **false** during timesheet submission in the app, an error message is shown to the user.</span></span>
- <span data-ttu-id="05af2-274">A lógica que preenche os campos (por exemplo, **Propriedade da linha**) durante o método **inserir** na tabela TSTimesheetLine ainda será executada.</span><span class="sxs-lookup"><span data-stu-id="05af2-274">Logic that fills in fields (for example, **Line Property**) during the **insert** method on the TSTimesheetLine table will still run.</span></span>

### <a name="hiding-and-marking-out-of-box-fields-as-read-only-via-configuration"></a><span data-ttu-id="05af2-275">Ocultação e marcação de campos prontos para uso como somente leitura por meio de configuração</span><span class="sxs-lookup"><span data-stu-id="05af2-275">Hiding and marking out-of-box fields as read-only via configuration</span></span>

<span data-ttu-id="05af2-276">Nos parâmetros do projeto, você pode criar campos prontos para uso somente leitura ou ocultos no aplicativo para dispositivos móveis.</span><span class="sxs-lookup"><span data-stu-id="05af2-276">From the project parameters, you can make out-of-box fields read-only or hidden in the mobile app.</span></span> <span data-ttu-id="05af2-277">Defina as opções na seção **Folhas de ponto móveis** na guia **Folha de ponto** da página **Parâmetros de gerenciamento e contabilidade de projetos**.</span><span class="sxs-lookup"><span data-stu-id="05af2-277">Set the options in the **Mobile timesheets** section on the **Timesheet** tab of the **Project management and accounting parameters** page.</span></span>

![Parâmetros do projeto](media/5753b8ecccd1d8bb2b002dd538b3f762.png)

### <a name="changing-the-activities-that-are-available-for-selection-via-extensions"></a><span data-ttu-id="05af2-279">Alteração das atividades que estão disponíveis para seleção por meio de extensões</span><span class="sxs-lookup"><span data-stu-id="05af2-279">Changing the activities that are available for selection via extensions</span></span>

<span data-ttu-id="05af2-280">As atividades disponíveis para seleção de um projeto são preenchidas por meio dos métodos **getActivitiesForProject()** e **getActivityQuery()** na classe **TsTimesheetProjectService**.</span><span class="sxs-lookup"><span data-stu-id="05af2-280">The activities that are available for selection for a project are filled in via the **getActivitiesForProject()** and **getActivityQuery()** methods in the **TsTimesheetProjectService** class.</span></span> <span data-ttu-id="05af2-281">É possível usar a cadeia de comando para alterar esse comportamento para corresponder ao seu cenário de negócios para as atividades que estão disponíveis para seleção de um projeto específico.</span><span class="sxs-lookup"><span data-stu-id="05af2-281">You can use chain of command to change this behavior to match your business scenario for the activities that are available for selection for a specific project.</span></span>

### <a name="entering-a-default-project-category-on-timesheet-entries"></a><span data-ttu-id="05af2-282">Inserção de uma categoria de projeto padrão nas entradas de folha de ponto</span><span class="sxs-lookup"><span data-stu-id="05af2-282">Entering a default project category on timesheet entries</span></span>

<span data-ttu-id="05af2-283">A entrada de uma categoria de projeto padrão nas entradas do quadro de horários ocorre em três níveis.</span><span class="sxs-lookup"><span data-stu-id="05af2-283">Entry of a default project category on timesheet entries occurs at three levels.</span></span> <span data-ttu-id="05af2-284">Você pode usar a cadeia de comando para estender o comportamento em qualquer um ou todos esses níveis para obter o comportamento desejado.</span><span class="sxs-lookup"><span data-stu-id="05af2-284">You can use chain of command to extend the behavior at any or all of these levels to achieve the desired behavior.</span></span> <span data-ttu-id="05af2-285">Esta é a hierarquia usada:</span><span class="sxs-lookup"><span data-stu-id="05af2-285">The following hierarchy is used:</span></span>

1. <span data-ttu-id="05af2-286">O aplicativo tenta colocar a categoria padrão do recurso do projeto.</span><span class="sxs-lookup"><span data-stu-id="05af2-286">The app tries to put the default category from the project resource.</span></span> <span data-ttu-id="05af2-287">Essa categoria padrão é definida nos métodos**getCurrentUserResource** e **getDelegatedResourcesForCurrentUser** na classe **TSTimesheetSettingsService**.</span><span class="sxs-lookup"><span data-stu-id="05af2-287">This default category is set in the **getCurrentUserResource** and **getDelegatedResourcesForCurrentUser** methods in the **TSTimesheetSettingsService** class.</span></span>
2. <span data-ttu-id="05af2-288">Se a categoria padrão não for fornecida no nível do recurso do projeto, o aplicativo tentará extraí-la da atividade do projeto.</span><span class="sxs-lookup"><span data-stu-id="05af2-288">If the default category isn't provided at the project resource level, the app tries to pull it from the project activity.</span></span> <span data-ttu-id="05af2-289">Essa categoria padrão é definida no método **getActivitiesForProject** na classe **TSTimesheetProjectService**.</span><span class="sxs-lookup"><span data-stu-id="05af2-289">This default category is set in the **getActivitiesForProject** method in the **TSTimesheetProjectService** class.</span></span>
3. <span data-ttu-id="05af2-290">Se a categoria padrão não for fornecida no nível de atividade do projeto, a categoria padrão será obtida dos parâmetros do projeto.</span><span class="sxs-lookup"><span data-stu-id="05af2-290">If the default category isn't provided at the project activity level, the default category it taken from the project parameters.</span></span> <span data-ttu-id="05af2-291">Essa categoria padrão é definida no método **getProjectDetailsbyRule** na classe **TSTimesheetProjectService**.</span><span class="sxs-lookup"><span data-stu-id="05af2-291">This default category is set in the **getProjectDetailsbyRule** method in the **TSTimesheetProjectService** class.</span></span>
