---
title: Criar e trabalhar com campos personalizados
description: Este tópico mostra como criar campos personalizados para adequar o aplicativo à sua empresa.
author: jasongre
manager: AnnBe
ms.date: 07/16/2018
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-platform
ms.technology: ''
ms.search.form: SysCustomFieldManageFields
audience: Application User
ms.reviewer: sericks
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: jasongre
ms.search.validFrom: 2018-1-31
ms.dyn365.ops.version: Platform update 13
ms.openlocfilehash: 9146921c47e89c5895a1a727de874b0ffbc93c37
ms.sourcegitcommit: 57bc7e17682e2edb5e1766496b7a22f4621819dd
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/18/2019
ms.locfileid: "2812496"
---
# <a name="create-and-work-with-custom-fields"></a><span data-ttu-id="0cf85-103">Criar e trabalhar com campos personalizados</span><span class="sxs-lookup"><span data-stu-id="0cf85-103">Create and work with custom fields</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="0cf85-104">Embora haja um conjunto extensivo de campos predefinidos para gerenciar uma ampla gama de processos empresariais, às vezes uma empresa precisa rastrear informações adicionais no sistema.</span><span class="sxs-lookup"><span data-stu-id="0cf85-104">While there is an extensive set of fields out-of-the-box for managing a broad range of business processes, sometimes there is a need for a company to track additional information in the system.</span></span> <span data-ttu-id="0cf85-105">Para acomodar essa necessidade, você pode criar campos personalizados para adequar o aplicativo à sua empresa, desde que você tenha permissões para o recurso.</span><span class="sxs-lookup"><span data-stu-id="0cf85-105">To accommodate this need, you can create custom fields to tailor the application to fit your business, provided you have permissions to the feature.</span></span>

<span data-ttu-id="0cf85-106">A capacidade de adicionar campos personalizados está disponível na atualização 13 da plataforma e posteriores.</span><span class="sxs-lookup"><span data-stu-id="0cf85-106">The ability to add custom fields is available in platform update 13 and later.</span></span>

<span data-ttu-id="0cf85-107">Este vídeo mostra como é fácil adicionar um campo personalizado a uma página: [Adicionando campos personalizados](https://www.youtube.com/watch?v=gWSGZI9Vtnc).</span><span class="sxs-lookup"><span data-stu-id="0cf85-107">This video shows how easy it is to add a custom field to a page: [Adding custom fields](https://www.youtube.com/watch?v=gWSGZI9Vtnc).</span></span>

## <a name="creating-custom-fields"></a><span data-ttu-id="0cf85-108">Criando campos personalizados</span><span class="sxs-lookup"><span data-stu-id="0cf85-108">Creating custom fields</span></span>

<span data-ttu-id="0cf85-109">Depois de identificar as informações adicionais que gostaria de rastrear no aplicativo, você poderá criar o campo personalizado na tabela apropriada e expor esse novo campo em uma página.</span><span class="sxs-lookup"><span data-stu-id="0cf85-109">After you've identified additional information that you would like to track in the application, you can create the custom field on the appropriate table and expose that new field on a page.</span></span>

<span data-ttu-id="0cf85-110">As etapas a seguir descrevem o processo para criar um campo personalizado e colocá-lo em um formulário.</span><span class="sxs-lookup"><span data-stu-id="0cf85-110">The following steps describe the process for creating a custom field and placing that field on a form.</span></span>

1. <span data-ttu-id="0cf85-111">Navegue até o formulário onde o novo campo é necessário.</span><span class="sxs-lookup"><span data-stu-id="0cf85-111">Navigate to the form where the new field is needed.</span></span>
2. <span data-ttu-id="0cf85-112">Como a meta final é expor o campo personalizado em um formulário, o ponto de entrada para criar campos personalizados existe na experiência de personalização.</span><span class="sxs-lookup"><span data-stu-id="0cf85-112">Because the end goal is to expose the custom field on a form, the entry point for creating custom fields exists inside the personalization experience.</span></span> <span data-ttu-id="0cf85-113">Abra a barra de ferramentas de personalização selecionando **Opções** e, em seguida, **Personalizar este formulário**.</span><span class="sxs-lookup"><span data-stu-id="0cf85-113">Open the personalization toolbar by selecting **Options**, and then **Personalize this form**.</span></span>
3. <span data-ttu-id="0cf85-114">Clique em **Inserir** e, em seguida, em **Campo**.</span><span class="sxs-lookup"><span data-stu-id="0cf85-114">Click **Insert** and then **Field**.</span></span>
4. <span data-ttu-id="0cf85-115">Selecione a região do formulário onde deseja expor o novo campo.</span><span class="sxs-lookup"><span data-stu-id="0cf85-115">Select the region of the form where you want to expose the new field.</span></span> <span data-ttu-id="0cf85-116">Após a seleção, a caixa de diálogo **Inserir campos** exibirá uma lista dos campos existentes que podem ser inseridos na região selecionada do formulário.</span><span class="sxs-lookup"><span data-stu-id="0cf85-116">After selection, the **Insert fields** dialog box will display a list of existing fields that can be inserted into the selected region of the form.</span></span>
5. <span data-ttu-id="0cf85-117">Verifique se o campo de seu interesse não está na lista.</span><span class="sxs-lookup"><span data-stu-id="0cf85-117">Ensure that the field you are interested in does not already exist in the list.</span></span> <span data-ttu-id="0cf85-118">Se estiver, você poderá simplesmente selecionar esse campo na lista e clicar em **Inserir**.</span><span class="sxs-lookup"><span data-stu-id="0cf85-118">If it does, you can simply select that field in the list and click **Insert**.</span></span>
6. <span data-ttu-id="0cf85-119">Clique no botão **Criar novo campo** acima da lista para iniciar o processo de criação de um campo personalizado.</span><span class="sxs-lookup"><span data-stu-id="0cf85-119">Click the **Create new field** button above the list to initiate the process of creating a custom field.</span></span> <span data-ttu-id="0cf85-120">Isso abrirá a caixa de diálogo **Criar novo campo**.</span><span class="sxs-lookup"><span data-stu-id="0cf85-120">This will open the **Create new field** dialog box.</span></span>

    <span data-ttu-id="0cf85-121">Se não vir o botão **Criar novo campo**, você não tem as permissões necessárias para usar esse recurso.</span><span class="sxs-lookup"><span data-stu-id="0cf85-121">If you do not see the **Create new field** button, you do not have the necessary permissions to use this feature.</span></span>

7. <span data-ttu-id="0cf85-122">Na caixa de diálogo **Criar novo campo**, insira as seguintes informações.</span><span class="sxs-lookup"><span data-stu-id="0cf85-122">In the **Create new field** dialog box, enter the following information.</span></span>

    1. <span data-ttu-id="0cf85-123">Selecione a tabela de banco de dados onde esse campo deve ser adicionado.</span><span class="sxs-lookup"><span data-stu-id="0cf85-123">Select the database table where this field should be added.</span></span> <span data-ttu-id="0cf85-124">Observe que apenas as tabelas que oferecem suporte a campos personalizados aparecerão na lista suspensa.</span><span class="sxs-lookup"><span data-stu-id="0cf85-124">Note that only tables that support custom fields will appear in the drop-down list.</span></span> <span data-ttu-id="0cf85-125">Consulte a seção abaixo para obter detalhes técnicos sobre tabelas com suporte.</span><span class="sxs-lookup"><span data-stu-id="0cf85-125">See the section below for technical details on supported tables.</span></span>
    2. <span data-ttu-id="0cf85-126">Selecione o tipo de dados do novo campo.</span><span class="sxs-lookup"><span data-stu-id="0cf85-126">Select the data type for the new field.</span></span> <span data-ttu-id="0cf85-127">Os tipos de dados disponíveis são caixa de seleção, data, data e hora, decimal, número, lista de separação e texto.</span><span class="sxs-lookup"><span data-stu-id="0cf85-127">The available data types are checkbox, date, date time, decimal, number, picklist, and text.</span></span>

        - <span data-ttu-id="0cf85-128">Se escolher o tipo de dados de texto, você também poderá especificar o tamanho máximo do texto que pode ser inserido nesse campo.</span><span class="sxs-lookup"><span data-stu-id="0cf85-128">If you choose the text data type, you can also specify the maximum length of the text that can be entered in this field.</span></span>
        - <span data-ttu-id="0cf85-129">Se escolher o tipo de dados de lista de separação, você também poderá selecionar o conjunto de valores válidos para o campo.</span><span class="sxs-lookup"><span data-stu-id="0cf85-129">If you choose the picklist data type, you can also select the set of valid values for the field.</span></span>

    3. <span data-ttu-id="0cf85-130">Forneça um nome, um rótulo e um texto de ajuda para o campo.</span><span class="sxs-lookup"><span data-stu-id="0cf85-130">Provide a name, label, and help text for the field.</span></span> <span data-ttu-id="0cf85-131">O nome corresponde ao nome de campo físico no banco de dados, enquanto o rótulo e o texto de ajuda são o texto usado para representar esse campo na interface do usuário.</span><span class="sxs-lookup"><span data-stu-id="0cf85-131">The name corresponds to the physical field name in the database, whereas the label and help text are the text used to represent this field in the user interface.</span></span>

8. <span data-ttu-id="0cf85-132">Se esse for o único campo que você precisa criar para este formulário, clique em **Salvar**.</span><span class="sxs-lookup"><span data-stu-id="0cf85-132">If this is the only field that you need to create for this form, click **Save**.</span></span> <span data-ttu-id="0cf85-133">Se precisar criar campos adicionais, clique em **Salvar e novo** e volte para a etapa 7.</span><span class="sxs-lookup"><span data-stu-id="0cf85-133">If you need to create additional fields, click **Save and new** and go back to step 7.</span></span> <span data-ttu-id="0cf85-134">Observe que atualmente há um limite de **20 campos personalizados por tabela**.</span><span class="sxs-lookup"><span data-stu-id="0cf85-134">Note that there is currently a limit of **20 custom fields per table**.</span></span>
9. <span data-ttu-id="0cf85-135">Ao deixar a caixa de diálogo **Criar novo campo**, você retornará à caixa de diálogo **Inserir campos**.</span><span class="sxs-lookup"><span data-stu-id="0cf85-135">Leaving the **Create new field** dialog box will return you to the **Insert fields** dialog box.</span></span> <span data-ttu-id="0cf85-136">Todos os campos personalizados adicionados recentemente serão marcados automaticamente na lista de campos a ser inserida no formulário.</span><span class="sxs-lookup"><span data-stu-id="0cf85-136">Any custom fields that were just added will be automatically marked in the field list to be inserted into the form.</span></span>
10. <span data-ttu-id="0cf85-137">Clique em **Inserir** para inserir os campos marcados na região selecionada do formulário.</span><span class="sxs-lookup"><span data-stu-id="0cf85-137">Click **Insert** to insert the marked fields into the selected region of the form.</span></span>
11. <span data-ttu-id="0cf85-138">**Opcional:** habilite o modo **Mover** da barra de ferramentas de personalização para mover os novos campos à localização desejada na região selecionada.</span><span class="sxs-lookup"><span data-stu-id="0cf85-138">**Optional:** Enable **Move** mode from the personalization toolbar to move the new fields to their desired location in the selected region.</span></span> <span data-ttu-id="0cf85-139">Consulte [Personalizar a experiência do usuário](personalize-user-experience.md) para obter mais informações sobre como usar os diversos recursos de personalização para otimizar um formulário para seu uso pessoal.</span><span class="sxs-lookup"><span data-stu-id="0cf85-139">See [Personalize the user experience](personalize-user-experience.md) for more information about how to use the various personalization capabilities to optimize a form for your personal usage.</span></span>

## <a name="sharing-custom-fields-with-other-users"></a><span data-ttu-id="0cf85-140">Compartilhando campos personalizados com outros usuários</span><span class="sxs-lookup"><span data-stu-id="0cf85-140">Sharing custom fields with other users</span></span>

<span data-ttu-id="0cf85-141">Após criar um campo personalizado e o expor em um formulário, convém fornecer essa exibição de página atualizada que inclui o novo campo a outros usuários no sistema.</span><span class="sxs-lookup"><span data-stu-id="0cf85-141">After you have created a custom field and exposed it on a form, you might want to provide this updated page view that includes the new field to other users in the system.</span></span> <span data-ttu-id="0cf85-142">Isso pode ser realizado de duas formas usando os recursos de personalização do produto:</span><span class="sxs-lookup"><span data-stu-id="0cf85-142">This can be accomplished in two different ways using the personalization capabilities of the product:</span></span>

- <span data-ttu-id="0cf85-143">O roteiro recomendado é por meio do administrador do sistema, que pode enviar uma personalização a todos os usuários ou a um subconjunto de usuários.</span><span class="sxs-lookup"><span data-stu-id="0cf85-143">The recommended route is through the system administrator, who can push a personalization to all users or a subset of users.</span></span> <span data-ttu-id="0cf85-144">Consulte [Personalizar a experiência do usuário](personalize-user-experience.md) para obter mais detalhes.</span><span class="sxs-lookup"><span data-stu-id="0cf85-144">See [Personalize the user experience](personalize-user-experience.md) for more details.</span></span>
- <span data-ttu-id="0cf85-145">Como alternativa, você pode exportar as alterações (chamadas *personalizações*), enviá-las a um ou mais usuários e fazer com que cada um deles importe as alterações.</span><span class="sxs-lookup"><span data-stu-id="0cf85-145">Alternatively, you can export your changes (called *personalizations*), send them to one or more users, and have each of those users import your changes.</span></span> <span data-ttu-id="0cf85-146">A opção **Gerenciar** na barra de ferramentas de personalização permite exportar e importar personalizações.</span><span class="sxs-lookup"><span data-stu-id="0cf85-146">The **Manage** option on the personalization toolbar enables you to export and import personalizations.</span></span>

## <a name="managing-custom-fields"></a><span data-ttu-id="0cf85-147">Gerenciando campos personalizados</span><span class="sxs-lookup"><span data-stu-id="0cf85-147">Managing custom fields</span></span>

<span data-ttu-id="0cf85-148">O gerenciamento de todos os campos personalizados do sistema pode ser realizado por meio da página **Campos personalizados** no módulo de administração do sistema.</span><span class="sxs-lookup"><span data-stu-id="0cf85-148">Management of all the custom fields in the system can be accomplished through the **Custom fields** page in the System administration module.</span></span> <span data-ttu-id="0cf85-149">Essa página permite que os usuários acessem muitos recursos, incluindo:</span><span class="sxs-lookup"><span data-stu-id="0cf85-149">This page allows users access to many capabilities, including:</span></span>

- <span data-ttu-id="0cf85-150">Exibição de uma lista de todos os campos personalizados no sistema.</span><span class="sxs-lookup"><span data-stu-id="0cf85-150">Viewing a list of all custom fields in the system.</span></span>
- <span data-ttu-id="0cf85-151">Edição limitada de campos personalizados existentes.</span><span class="sxs-lookup"><span data-stu-id="0cf85-151">Limited editing of existing custom fields.</span></span>
- <span data-ttu-id="0cf85-152">Exclusão de campos personalizados.</span><span class="sxs-lookup"><span data-stu-id="0cf85-152">Deleting custom fields.</span></span>
- <span data-ttu-id="0cf85-153">Exposição de campos personalizados em entidades de dados.</span><span class="sxs-lookup"><span data-stu-id="0cf85-153">Exposing custom fields on data entities.</span></span>
- <span data-ttu-id="0cf85-154">Fornecimento de traduções de rótulos e texto de ajuda de campos personalizados.</span><span class="sxs-lookup"><span data-stu-id="0cf85-154">Providing translations of custom field labels and help text.</span></span>

### <a name="viewing-all-custom-fields"></a><span data-ttu-id="0cf85-155">Exibição de todos os campos personalizados</span><span class="sxs-lookup"><span data-stu-id="0cf85-155">Viewing all custom fields</span></span>

<span data-ttu-id="0cf85-156">A página **Campos personalizados** fornece visibilidade a todos os campos personalizados definidos no sistema.</span><span class="sxs-lookup"><span data-stu-id="0cf85-156">The **Custom fields** page provides visibility to all the custom fields that have been defined in the system.</span></span> <span data-ttu-id="0cf85-157">Basta selecionar a tabela de seu interesse e a página atualizará para mostrar a lista dos campos personalizados associados à essa tabela.</span><span class="sxs-lookup"><span data-stu-id="0cf85-157">Simply select the table that you are interested in, and the page will update to show a list of the custom fields associated with that table.</span></span> <span data-ttu-id="0cf85-158">Escolher um campo personalizado da lista permitirá que você exiba todos os detalhes do campo.</span><span class="sxs-lookup"><span data-stu-id="0cf85-158">Choosing a custom field from the list will allow you to view all the details about the field.</span></span>

### <a name="editing-custom-fields"></a><span data-ttu-id="0cf85-159">Editando campos personalizados</span><span class="sxs-lookup"><span data-stu-id="0cf85-159">Editing custom fields</span></span>

<span data-ttu-id="0cf85-160">Depois que um campo personalizado for criado, somente determinadas informações sobre ele poderão ser modificadas na página **Campos personalizados**.</span><span class="sxs-lookup"><span data-stu-id="0cf85-160">After a custom field has been created, only certain pieces of information about the custom field can be modified on the **Custom fields** page.</span></span>

<span data-ttu-id="0cf85-161">Você *pode* modificar estes atributos:</span><span class="sxs-lookup"><span data-stu-id="0cf85-161">You *can* modify these attributes:</span></span>

- <span data-ttu-id="0cf85-162">Rótulo</span><span class="sxs-lookup"><span data-stu-id="0cf85-162">Label</span></span>
- <span data-ttu-id="0cf85-163">Texto de ajuda</span><span class="sxs-lookup"><span data-stu-id="0cf85-163">Help text</span></span>
- <span data-ttu-id="0cf85-164">Comprimento, para campos de texto</span><span class="sxs-lookup"><span data-stu-id="0cf85-164">Length, for Text fields</span></span>

<span data-ttu-id="0cf85-165">Você *não pode* editar os atributos a seguir:</span><span class="sxs-lookup"><span data-stu-id="0cf85-165">You *cannot* edit the following attributes:</span></span>

- <span data-ttu-id="0cf85-166">Nome do campo</span><span class="sxs-lookup"><span data-stu-id="0cf85-166">Field name</span></span>
- <span data-ttu-id="0cf85-167">Tipo de dados</span><span class="sxs-lookup"><span data-stu-id="0cf85-167">Data type</span></span>

<span data-ttu-id="0cf85-168">Além disso, para campos de lista de separação, o conjunto de valores válidos para o campo personalizado pode ser reordenado e novos valores podem ser adicionados; entretanto, os valores existentes para o campo de lista de separação não podem ser removidos.</span><span class="sxs-lookup"><span data-stu-id="0cf85-168">Additionally, for picklist fields, the set of valid values for the custom field can be reordered, and new values can be added; however, existing values for the picklist field cannot be removed.</span></span> <span data-ttu-id="0cf85-169">Lembre-se de clicar em **Aplicar alterações** quando terminar de editar os campos de uma tabela específica para que as alterações sejam salvas.</span><span class="sxs-lookup"><span data-stu-id="0cf85-169">Remember to click **Apply changes** when you are done editing fields for a particular table so the changes are saved.</span></span>

### <a name="exposing-custom-fields-on-data-entities"></a><span data-ttu-id="0cf85-170">Expondo campos personalizados em entidades de dados</span><span class="sxs-lookup"><span data-stu-id="0cf85-170">Exposing custom fields on data entities</span></span>

<span data-ttu-id="0cf85-171">Também pode ser importante permitir que campos personalizados estejam visíveis em entidades de dados.</span><span class="sxs-lookup"><span data-stu-id="0cf85-171">It may also be important to allow custom fields to be visible on data entities.</span></span> <span data-ttu-id="0cf85-172">As entidades de dados são usadas no recurso [Visão geral da integração do Office](../../dev-itpro/office-integration/office-integration.md), bem como para cenários de importação/exportação de dados.</span><span class="sxs-lookup"><span data-stu-id="0cf85-172">Data entities are utilized in the [Office integration overview](../../dev-itpro/office-integration/office-integration.md) feature, as well as for data import/export scenarios.</span></span>

<span data-ttu-id="0cf85-173">Siga estas etapas para expor um campo personalizado em uma entidade de dados:</span><span class="sxs-lookup"><span data-stu-id="0cf85-173">Follow these steps to expose a custom field on a data entity:</span></span>

1. <span data-ttu-id="0cf85-174">Selecione o campo personalizado no formulário **Campos personalizados**.</span><span class="sxs-lookup"><span data-stu-id="0cf85-174">Select the custom field on the **Custom fields** form.</span></span>
2. <span data-ttu-id="0cf85-175">Expanda a seção **Entidades** para exibir o conjunto de entidades relevantes.</span><span class="sxs-lookup"><span data-stu-id="0cf85-175">Expand the **Entities** section to view the set of relevant entities.</span></span>
3. <span data-ttu-id="0cf85-176">Clique no botão **Editar**.</span><span class="sxs-lookup"><span data-stu-id="0cf85-176">Click the **Edit** button.</span></span>
4. <span data-ttu-id="0cf85-177">Modifique o campo **Habilitado** para que seja selecionado para cada entidade que deve expor este campo.</span><span class="sxs-lookup"><span data-stu-id="0cf85-177">Modify the **Enabled** field to be selected for each entity that should expose this field.</span></span>
5. <span data-ttu-id="0cf85-178">Clique em **Aplicar alterações** para salvar as seleções.</span><span class="sxs-lookup"><span data-stu-id="0cf85-178">Click **Apply changes** to save your selections.</span></span>

### <a name="allowing-custom-fields-to-be-displayed-in-other-languages"></a><span data-ttu-id="0cf85-179">Permitindo que os campos personalizados sejam exibidos em outros idiomas</span><span class="sxs-lookup"><span data-stu-id="0cf85-179">Allowing custom fields to be displayed in other languages</span></span>

<span data-ttu-id="0cf85-180">Como os campos personalizados podem precisar ser acessados por usuários em vários idiomas, a página **Campos personalizados** fornece um mecanismo para permitir que o rótulo e o texto de ajuda de um campo personalizado possam ser traduzidos para outros idiomas.</span><span class="sxs-lookup"><span data-stu-id="0cf85-180">Because custom fields may need to be accessed by users in a variety of languages, the **Custom fields** page provides a mechanism to allow the label and help text for a custom field to be translated into other languages.</span></span>

<span data-ttu-id="0cf85-181">As etapas a seguir descrevem o processo de tradução de campos personalizados para outros idiomas:</span><span class="sxs-lookup"><span data-stu-id="0cf85-181">The following steps describe the process for translating custom fields in other languages:</span></span>

1. <span data-ttu-id="0cf85-182">Selecione o campo personalizado na página **Campos personalizados**.</span><span class="sxs-lookup"><span data-stu-id="0cf85-182">Select the custom field on the **Custom fields** page.</span></span>
2. <span data-ttu-id="0cf85-183">Selecione o botão **Traduções** no Painel de Ação.</span><span class="sxs-lookup"><span data-stu-id="0cf85-183">Select the **Translations** button in the Action Pane.</span></span> <span data-ttu-id="0cf85-184">Isso abrirá um menu suspenso com traduções existentes para esse campo.</span><span class="sxs-lookup"><span data-stu-id="0cf85-184">This will open a drop-down menu with existing translations for this field.</span></span>
3. <span data-ttu-id="0cf85-185">O menu suspenso **Idioma** mostra o conjunto de idiomas para os quais já foram fornecidas traduções.</span><span class="sxs-lookup"><span data-stu-id="0cf85-185">The **Language** drop-down menu shows the set of languages for which translations have already been provided.</span></span>

    <span data-ttu-id="0cf85-186">Se desejar editar uma tradução existente, selecione o idioma desejado no menu e modifique os valores para o rótulo e o texto de ajuda.</span><span class="sxs-lookup"><span data-stu-id="0cf85-186">If you want to edit an existing translation, select the desired language from the menu and modify the values for the label and help text.</span></span>

    <span data-ttu-id="0cf85-187">Caso contrário, clique no botão **Adicionar idioma**, selecione o idioma desejado no menu e, em seguida, forneça valores traduzidos para o rótulo e o texto de ajuda.</span><span class="sxs-lookup"><span data-stu-id="0cf85-187">Otherwise, click the **Add language** button, select the desired language from the menu, and then provide translated values for the label and help text.</span></span>

4. <span data-ttu-id="0cf85-188">Clique em **OK** quando tiver terminado.</span><span class="sxs-lookup"><span data-stu-id="0cf85-188">Click **OK** when you are finished.</span></span>

### <a name="deleting-custom-fields"></a><span data-ttu-id="0cf85-189">Excluindo campos personalizados</span><span class="sxs-lookup"><span data-stu-id="0cf85-189">Deleting custom fields</span></span>

<span data-ttu-id="0cf85-190">Em alguns casos raros, você poderá decidir que um campo personalizado não é mais necessário.</span><span class="sxs-lookup"><span data-stu-id="0cf85-190">In some rare cases, you may decide that a custom field is no longer needed.</span></span> <span data-ttu-id="0cf85-191">Quando isso ocorrer, um administrador do sistema poderá optar por excluir o campo da página **Campos personalizados**.</span><span class="sxs-lookup"><span data-stu-id="0cf85-191">When this occurs, a system administrator can choose to delete the field from the **Custom fields** page.</span></span> <span data-ttu-id="0cf85-192">Para fazer isso, verifique se o campo correto foi selecionado, clique em **Excluir**, clique em **Sim** para confirmar a exclusão e, por fim, clique em **Aplicar alterações**.</span><span class="sxs-lookup"><span data-stu-id="0cf85-192">To do this, ensure the correct field is selected, click **Delete**, click **Yes** to confirm the deletion, and finally click **Apply changes**.</span></span>

> [!NOTE]
> <span data-ttu-id="0cf85-193">Essa ação não poderá ser desfeita e fará com que os dados associados ao campo sejam excluídos permanentemente do banco de dados.</span><span class="sxs-lookup"><span data-stu-id="0cf85-193">This action cannot be undone, and will result in the data associated with the field being permanently deleted from the database.</span></span>

## <a name="appendix"></a><span data-ttu-id="0cf85-194">Anexo</span><span class="sxs-lookup"><span data-stu-id="0cf85-194">Appendix</span></span>

### <a name="who-can-create-custom-fields"></a><span data-ttu-id="0cf85-195">Quem pode criar campos personalizados?</span><span class="sxs-lookup"><span data-stu-id="0cf85-195">Who can create custom fields?</span></span>

<span data-ttu-id="0cf85-196">Como uma proteção para o sistema, apenas os administradores do sistema podem criar campos personalizados por padrão.</span><span class="sxs-lookup"><span data-stu-id="0cf85-196">As a safeguard to the system, only system administrators are able to create custom fields by default.</span></span> <span data-ttu-id="0cf85-197">No entanto, os usuários avançados que a organização julgar necessários poderão receber direitos para criar campos personalizados por um administrador do sistema usando a função de segurança **Usuário avançado de personalização de tempo de execução**.</span><span class="sxs-lookup"><span data-stu-id="0cf85-197">However, those power users whom the organization deems necessary can be given rights to create custom fields by a system administrator using the **Runtime customization power user** security role.</span></span> <span data-ttu-id="0cf85-198">Os usuários sem essa função de segurança não poderão criar campos personalizados, mas ainda poderão ver e interagir com os campos personalizados adicionados por outros usuários no sistema.</span><span class="sxs-lookup"><span data-stu-id="0cf85-198">Users without this security role will not be able to create custom fields, but will still be able to see and interact with custom fields added by other users in the system.</span></span>

### <a name="what-tables-support-custom-fields"></a><span data-ttu-id="0cf85-199">Que tabelas oferecem suporte a campos personalizados?</span><span class="sxs-lookup"><span data-stu-id="0cf85-199">What tables support custom fields?</span></span>

<span data-ttu-id="0cf85-200">Por motivos técnicos e de desempenho, apenas as tabelas que atendem às seguintes condições atualmente permitem que os campos personalizados sejam adicionados.</span><span class="sxs-lookup"><span data-stu-id="0cf85-200">For performance and technical reasons, only tables that meet the following conditions currently allow custom fields to be added.</span></span>

- <span data-ttu-id="0cf85-201">A tabela deve estar marcada como um destes grupos:</span><span class="sxs-lookup"><span data-stu-id="0cf85-201">The table must be tagged as one of these groups:</span></span>

    - <span data-ttu-id="0cf85-202">Agrupar</span><span class="sxs-lookup"><span data-stu-id="0cf85-202">Group</span></span>
    - <span data-ttu-id="0cf85-203">WorksheetHeader</span><span class="sxs-lookup"><span data-stu-id="0cf85-203">WorksheetHeader</span></span>
    - <span data-ttu-id="0cf85-204">Principal</span><span class="sxs-lookup"><span data-stu-id="0cf85-204">Main</span></span>
    - <span data-ttu-id="0cf85-205">Diversos</span><span class="sxs-lookup"><span data-stu-id="0cf85-205">Miscellaneous</span></span>
    - <span data-ttu-id="0cf85-206">Parâmetro</span><span class="sxs-lookup"><span data-stu-id="0cf85-206">Parameter</span></span>
    - <span data-ttu-id="0cf85-207">Demonstrativo</span><span class="sxs-lookup"><span data-stu-id="0cf85-207">Reference</span></span>
    - <span data-ttu-id="0cf85-208">TransactionHeader</span><span class="sxs-lookup"><span data-stu-id="0cf85-208">TransactionHeader</span></span>

- <span data-ttu-id="0cf85-209">A tabela não pode estender outra tabela.</span><span class="sxs-lookup"><span data-stu-id="0cf85-209">The table cannot extend another table.</span></span>
- <span data-ttu-id="0cf85-210">A tabela não pode ser marcada como uma tabela de sistema.</span><span class="sxs-lookup"><span data-stu-id="0cf85-210">The table cannot be marked as a system table.</span></span>
- <span data-ttu-id="0cf85-211">A tabela não pode ser uma tabela temporária.</span><span class="sxs-lookup"><span data-stu-id="0cf85-211">The table cannot be a temporary table.</span></span>
