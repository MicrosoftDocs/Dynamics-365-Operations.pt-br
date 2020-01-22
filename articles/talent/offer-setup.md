---
title: Configurar o gerenciamento de ofertas no Attract
description: Este tópico descreve como configurar ofertas no Microsoft Dynamics 365 Talent.
author: andreabichsel
manager: AnnBe
ms.date: 12/04/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-talent
ms.technology: ''
audience: Application User
ms.reviewer: anbichse
ms.search.scope: Core, Talent
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: anbichse
ms.search.validFrom: 2018-10-18
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: bc91a83afd5ce1627376685bcf612d6998ddbc02
ms.sourcegitcommit: 5022d63a81c3715c9a3dcf2a68217bb6b17c7805
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/05/2019
ms.locfileid: "2890546"
---
# <a name="set-up-offer-management-in-attract"></a><span data-ttu-id="ffe25-103">Configurar o gerenciamento de ofertas no Attract</span><span class="sxs-lookup"><span data-stu-id="ffe25-103">Set up offer management in Attract</span></span>

[!include [banner](includes/banner.md)]

<span data-ttu-id="ffe25-104">Quando o candidato for movido para o estágio de oferta no Dynamics 365 Talent: Attract, você precisará garantir que as ofertas possam ser rapidamente criadas, aprovadas, conforme necessário, e enviadas para o candidato.</span><span class="sxs-lookup"><span data-stu-id="ffe25-104">When a candidate is moved to the offer stage in Dynamics 365 Talent: Attract, you need to ensure that the offers can be quickly created for the candidate, approved as necessary, and sent out to the candidate.</span></span> <span data-ttu-id="ffe25-105">Como a maioria de ofertas é padrão, elas podem ser criadas desde modelos reutilizáveis.</span><span class="sxs-lookup"><span data-stu-id="ffe25-105">Because most offers are standard, they can be created from reusable templates.</span></span> <span data-ttu-id="ffe25-106">No Attract, todas as ofertas são agrupadas em um pacote de oferta, que é uma coleção de um ou mais documentos de oferta.</span><span class="sxs-lookup"><span data-stu-id="ffe25-106">In Attract, all offers are rolled into an offer package, which is a collection of one or more offer documents.</span></span> 

<span data-ttu-id="ffe25-107">Este tópico lista todas as etapas que um administrador do Attract deve seguir para configurar diferentes modelos de pacote de oferta como parte do recurso de gerenciamento de ofertas no Attract.</span><span class="sxs-lookup"><span data-stu-id="ffe25-107">This topic lists all the steps that an Attract administrator would follow to set up different offer package templates as part of the offer management capability in Attract.</span></span> <span data-ttu-id="ffe25-108">Os usuários com funções não administrativas não terão acesso a esses recursos.</span><span class="sxs-lookup"><span data-stu-id="ffe25-108">Users with non-administrator roles will not have access to these capabilities.</span></span>

>[!NOTE]
> <span data-ttu-id="ffe25-109">Os recursos de gerenciamento de ofertas estão disponíveis como parte do complemento Contratação Abrangente.</span><span class="sxs-lookup"><span data-stu-id="ffe25-109">Offer management capabilities are available as part of the Comprehensive Hiring Add-On.</span></span>

## <a name="offer-data"></a><span data-ttu-id="ffe25-110">Dados da oferta</span><span class="sxs-lookup"><span data-stu-id="ffe25-110">Offer data</span></span> 

<span data-ttu-id="ffe25-111">Os dados da oferta são a menor unidade no modelo do pacote de oferta.</span><span class="sxs-lookup"><span data-stu-id="ffe25-111">Offer data is the smallest unit inside the offer package template.</span></span> <span data-ttu-id="ffe25-112">Uma oferta típica consiste no texto padrão e em um conjunto de valores.</span><span class="sxs-lookup"><span data-stu-id="ffe25-112">A typical offer consists of standard text and a set of values.</span></span> <span data-ttu-id="ffe25-113">Os conjuntos de valores são as únicas partes que podem mudar entre as ofertas.</span><span class="sxs-lookup"><span data-stu-id="ffe25-113">The sets of values are the only pieces that could change between offers.</span></span> <span data-ttu-id="ffe25-114">Durante a criação da oferta, o aspecto mais importante em que o criador da oferta pode se concentrar é a lista de espaços reservados de dados da oferta presentes em um modleo de pacote de oferta.</span><span class="sxs-lookup"><span data-stu-id="ffe25-114">During the offer creation, the most important aspect that the offer creator can focus on is the list of offer data placeholders present in an offer package template.</span></span> <span data-ttu-id="ffe25-115">Para configurar dados da oferta, faça o seguinte.</span><span class="sxs-lookup"><span data-stu-id="ffe25-115">To set up offer data, do the following.</span></span>

1.  <span data-ttu-id="ffe25-116">Vá para **Gerenciamento de ofertas**.</span><span class="sxs-lookup"><span data-stu-id="ffe25-116">Go to **Offer management**.</span></span>

1.  <span data-ttu-id="ffe25-117">Expanda a seção **Biblioteca** no painel de navegação esquerdo, então vá para **Dados da oferta**.</span><span class="sxs-lookup"><span data-stu-id="ffe25-117">Expand the **Library** section in the left navigation pane, then go to **Offer data**.</span></span>

    >[!NOTE]
    > <span data-ttu-id="ffe25-118">Na página **Dados da oferta**, há as seções **Detalhes do candidato** e **Detalhes do trabalho**.</span><span class="sxs-lookup"><span data-stu-id="ffe25-118">On the **Offer data** page are the **Candidate details** and **Job details** sections.</span></span> <span data-ttu-id="ffe25-119">O Attract fornece alguns espaços reservados de dados da oferta prontos para uso.</span><span class="sxs-lookup"><span data-stu-id="ffe25-119">Attract provides a few offer data placeholders out-of-the-box.</span></span>
    > 
    > <span data-ttu-id="ffe25-120">Há seções na página para organizar diferentes espaços reservados de dados da oferta diferentes em grupos lógicos.</span><span class="sxs-lookup"><span data-stu-id="ffe25-120">There are sections on the page to organize different offer data placeholders together in logical groups.</span></span> <span data-ttu-id="ffe25-121">Estas seções podem ajudar na manutenção de dados da oferta e na população de dados durante o processo de criação da oferta.</span><span class="sxs-lookup"><span data-stu-id="ffe25-121">These sections can help with maintenance of offer data and population of data during the offer creation process.</span></span>
    > 
    > <span data-ttu-id="ffe25-122">Para criar uma lista de valores para um espaço reservado, carregue uma planilha do Excel que tenha uma coluna com o espaço reservado como o título da coluna e a lista de opções nas linhas abaixo.</span><span class="sxs-lookup"><span data-stu-id="ffe25-122">To create a list of values for a placeholder, upload an Excel spreadsheet that has one column with the placeholder as the column title and the list of choices in the rows underneath.</span></span> <span data-ttu-id="ffe25-123">Se o mesmo espaço reservado for referenciado em outro conjunto de regras de dados, verifique se eles têm um conjunto de valores comum.</span><span class="sxs-lookup"><span data-stu-id="ffe25-123">If the same placeholder is referenced in another data rule set, ensure they have a common set of values.</span></span>
    
1.  <span data-ttu-id="ffe25-124">Para criar uma nova seção de dados da oferta, clique em **Adicionar uma seção** e insira um nome exclusivo para a seção.</span><span class="sxs-lookup"><span data-stu-id="ffe25-124">To create a new offer data section, click **Add a section** and enter a unique name for the section.</span></span>

1.  <span data-ttu-id="ffe25-125">Para adicionar espaços reservados de dados da oferta a qualquer seção, clique em **Adicionar dados da oferta** e insira um nome exclusivo para o espaço reservado.</span><span class="sxs-lookup"><span data-stu-id="ffe25-125">To add offer data placeholders to any section, click **Add offer data** and enter a unique name for the placeholder.</span></span>

1.  <span data-ttu-id="ffe25-126">Para editar o nome de qualquer seção, passe o mouse sobre o nome da seção e atualize o nome.</span><span class="sxs-lookup"><span data-stu-id="ffe25-126">To edit the name of any section, hover over the section name and update the name.</span></span>

1.  <span data-ttu-id="ffe25-127">Para editar o nome de qualquer espaço reservado de dados da oferta, primeiro verifique se o espaço reservado já não faz parte de um modelo.</span><span class="sxs-lookup"><span data-stu-id="ffe25-127">To edit the name of any existing offer data placeholder, first make sure that the placeholder is not already part of any template.</span></span> <span data-ttu-id="ffe25-128">Em seguida, passe o mouse sobre o nome do espaço reservado de dados da oferta e atualize o nome como necessário.</span><span class="sxs-lookup"><span data-stu-id="ffe25-128">Then, hover over the name of the offer data placeholder and update the name as needed.</span></span>

1. <span data-ttu-id="ffe25-129">Para excluir um espaço reservado de dados da oferta existente, primeiro verifique se o espaço reservado não faz parte de qualquer outro modelo.</span><span class="sxs-lookup"><span data-stu-id="ffe25-129">To delete an existing offer data placeholder, first make sure that the placeholder is not part of any other template.</span></span> <span data-ttu-id="ffe25-130">Em seguida, passe o mouse sobre o espaço reservado e, quando o ícone de lixeira aparecer, clique na lixeira para excluir o espaço reservado de dados da oferta.</span><span class="sxs-lookup"><span data-stu-id="ffe25-130">Then, hover over the placeholder and when the trash can icon appears, click the trash can to delete the offer data placeholder.</span></span>
    >[!NOTE]
    > <span data-ttu-id="ffe25-131">Você pode ver de quantos modelos um espaço reservado de dados da oferta faz parte pelo número indicador ao lado de cada dado da oferta.</span><span class="sxs-lookup"><span data-stu-id="ffe25-131">You can see how many templates an offer data placeholder is part of by the number indicator next to each offer data.</span></span> 

1. <span data-ttu-id="ffe25-132">Para excluir uma seção, passe o mouse sobre o nome.</span><span class="sxs-lookup"><span data-stu-id="ffe25-132">To delete any section, hover over the name.</span></span> <span data-ttu-id="ffe25-133">Se nenhum dos espaços reservados de dados da oferta dentro da sessão aparecer em algum modelo, você poderá clicar no ícone de lixeira para excluí-lo.</span><span class="sxs-lookup"><span data-stu-id="ffe25-133">If none of the offer data placeholders inside the section appear in any template, you can click the trash can icon to delete it.</span></span> 
    >[!NOTE]
    > <span data-ttu-id="ffe25-134">A exclusão da seção também excluirá todos os espaços reservados de dados da oferta que estejam na seção.</span><span class="sxs-lookup"><span data-stu-id="ffe25-134">Deleting the section will also delete all the offer data placeholders inside that section.</span></span>

<span data-ttu-id="ffe25-135">Depois que os espaços reservados de dados da oferta tiverem sido configurados, você poderá usá-los em qualquer modelo de documento.</span><span class="sxs-lookup"><span data-stu-id="ffe25-135">After the offer data placeholders have been set up, you can use them across any document template.</span></span> <span data-ttu-id="ffe25-136">Os espaços reservados de dados da oferta não estão restritos a um modelo específico -- o mesmo conjunto pode ser usado entre todos os modelos.</span><span class="sxs-lookup"><span data-stu-id="ffe25-136">Offer data placeholders are not restricted to a specific template -- the same set can be used across all templates.</span></span>

## <a name="offer-data-rules"></a><span data-ttu-id="ffe25-137">Regras de dados da oferta</span><span class="sxs-lookup"><span data-stu-id="ffe25-137">Offer data rules</span></span>

<span data-ttu-id="ffe25-138">A maioria das organizações tem regras para a forma como as ofertas devem ser criadas.</span><span class="sxs-lookup"><span data-stu-id="ffe25-138">Most organization have rules for how offers must be created.</span></span> <span data-ttu-id="ffe25-139">Por exemplo, uma organização pode optar por exigir que a oferta de salário anual máximo para uma combinação de local específico e nível de tempo de serviço tenha de ficar dentro de um determinado intervalo, ou que haja somente alguns valores específicos possíveis para o nível da oferta para a nova contratação.</span><span class="sxs-lookup"><span data-stu-id="ffe25-139">For example, an organization may want to require that the maximum annual salary offer for a specific location and seniority level combination has to be within a certain range, or that there are only a few specific values possible for the offer level for the new hire.</span></span> <span data-ttu-id="ffe25-140">No momento, o Attract dá suporte a todas essas regras de dados usando um arquivo CSV.</span><span class="sxs-lookup"><span data-stu-id="ffe25-140">Attract currently supports all such data rules using a CSV file.</span></span>

<span data-ttu-id="ffe25-141">Para preparar o arquivo CSV de regras de dados, faça o seguinte.</span><span class="sxs-lookup"><span data-stu-id="ffe25-141">To prepare the data rules CSV file, do the following.</span></span>

1.  <span data-ttu-id="ffe25-142">Determine o espaço reservado de dados da oferta para o conjunto de regras.</span><span class="sxs-lookup"><span data-stu-id="ffe25-142">Determine the offer data placeholder for the rule set.</span></span> <span data-ttu-id="ffe25-143">Por exemplo, **Salário Anual**.</span><span class="sxs-lookup"><span data-stu-id="ffe25-143">For example, **Annual Salary**.</span></span>

1.  <span data-ttu-id="ffe25-144">Identifique os valores de espaço reservado de dados da oferta dependentes.</span><span class="sxs-lookup"><span data-stu-id="ffe25-144">Identify the dependent offer data placeholder values.</span></span> <span data-ttu-id="ffe25-145">Por exemplo, **Local de Trabalho** e **Nível**.</span><span class="sxs-lookup"><span data-stu-id="ffe25-145">For example, **Job Location** and **Level**.</span></span>

1.  <span data-ttu-id="ffe25-146">Especifique as colunas 1 e 2 como **Local de trabalho** e **Nível**.</span><span class="sxs-lookup"><span data-stu-id="ffe25-146">Specify columns 1 and 2 as **Job Location** and **Level**.</span></span>

1.  <span data-ttu-id="ffe25-147">Para carregar um valor de intervalo, crie as colunas 3 e 4 **Salário Anual**.</span><span class="sxs-lookup"><span data-stu-id="ffe25-147">To upload a range value, make columns 3 and 4 **Annual Salary**.</span></span> <span data-ttu-id="ffe25-148">Para carregar um valor específico em vez de um intervalo, crie somente a coluna 3 **Salário Anual**</span><span class="sxs-lookup"><span data-stu-id="ffe25-148">To upload a specific value instead of a range, only make column 3 **Annual Salary**.</span></span>

1.  <span data-ttu-id="ffe25-149">Preencha o arquivo do Microsoft Excel com base nas funções necessárias.</span><span class="sxs-lookup"><span data-stu-id="ffe25-149">Populate the Microsoft Excel file based on your required roles.</span></span>

1.  <span data-ttu-id="ffe25-150">Verifique se cada linha é uma combinação exclusiva de todos os valores.</span><span class="sxs-lookup"><span data-stu-id="ffe25-150">Ensure that each row is a unique combination of all the values put together.</span></span>

1.  <span data-ttu-id="ffe25-151">Salve o arquivo como um formato CSV.</span><span class="sxs-lookup"><span data-stu-id="ffe25-151">Save the file as a CSV format.</span></span>

<span data-ttu-id="ffe25-152">Para carregar o arquivo de regras de dados da oferta, faça o seguinte.</span><span class="sxs-lookup"><span data-stu-id="ffe25-152">To upload the offer data rules file, do the following.</span></span>

1.  <span data-ttu-id="ffe25-153">Vá para **Gerenciamento de ofertas**.</span><span class="sxs-lookup"><span data-stu-id="ffe25-153">Go to **Offer management**.</span></span>

1.  <span data-ttu-id="ffe25-154">Expanda a seção **Biblioteca** no painel de navegação esquerdo, então vá para **Regras de dados da oferta**.</span><span class="sxs-lookup"><span data-stu-id="ffe25-154">Expand the **Library** section in the left navigation panel, then go to **Offer data rules**.</span></span>

1.  <span data-ttu-id="ffe25-155">Clique em **Novo conjunto de dados** para exibir a caixa de diálogo **Upload**.</span><span class="sxs-lookup"><span data-stu-id="ffe25-155">Click **New data set** to display the **Upload** dialog box.</span></span>

1.  <span data-ttu-id="ffe25-156">Especifique um nome exclusivo para o conjunto de regras e então carregue o arquivo CSV salvo.</span><span class="sxs-lookup"><span data-stu-id="ffe25-156">Specify a unique name for the rule set and then upload the saved CSV file.</span></span>

1.  <span data-ttu-id="ffe25-157">Clique em **Adicionar**.</span><span class="sxs-lookup"><span data-stu-id="ffe25-157">Click **Add**.</span></span>
    <span data-ttu-id="ffe25-158">O conjunto de regras será processado em segundo plano e você será notificado no aplicativo e por email quando ele for concluído.</span><span class="sxs-lookup"><span data-stu-id="ffe25-158">The rule set will be processed in the background and you will be notified in-app and via email once it completes.</span></span>

    <span data-ttu-id="ffe25-159">Você será notificado se houver um erro ao processar o upload.</span><span class="sxs-lookup"><span data-stu-id="ffe25-159">You will be notified if there are errors while processing the upload.</span></span> <span data-ttu-id="ffe25-160">Você poderá então baixar o log de erros, corrigir o arquivo e carregá-lo novamente.</span><span class="sxs-lookup"><span data-stu-id="ffe25-160">You can then download the error log, fix the file, and upload it again.</span></span>

1.  <span data-ttu-id="ffe25-161">Use a opção do botão de reticências (**…**) se quiser baixar o conjunto de regras e atualizar o conjunto de valores.</span><span class="sxs-lookup"><span data-stu-id="ffe25-161">Use the ellipses button (**…**) option if you want to download the rule set and update the set of values.</span></span> <span data-ttu-id="ffe25-162">Depois de atualizar, será possível carregar o arquivo novamente.</span><span class="sxs-lookup"><span data-stu-id="ffe25-162">After updating, you can upload the file again.</span></span>

1.  <span data-ttu-id="ffe25-163">Você pode excluir um upload de conjunto de regras existente se o espaço reservado que está sendo definida não estiver sendo usado em outro modelo de documento.</span><span class="sxs-lookup"><span data-stu-id="ffe25-163">You can delete an existing rule set upload if the placeholder being defined is not being used in another document template.</span></span>

>[!NOTE]
> - <span data-ttu-id="ffe25-164">Cada espaço reservado pode ter apenas um conjunto exclusivo de colunas do qual depende.</span><span class="sxs-lookup"><span data-stu-id="ffe25-164">Each placeholder can only have one unique set of columns that it is dependent on.</span></span> <span data-ttu-id="ffe25-165">Por exemplo, se **Salário Anual** depender do **Local de Trabalho** e de **Nível**, você não poderá carregar outro conjunto de regras onde **Salário Anual** depende de um conjunto diferente de colunas.</span><span class="sxs-lookup"><span data-stu-id="ffe25-165">For example, if **Annual Salary** is dependent on **Job Location** and **Level**, you can't upload another rule set where **Annual Salary** is dependent on a different set of columns.</span></span>

> - <span data-ttu-id="ffe25-166">Você pode baixar conjuntos de dados da oferta de exemplo na guia **Exemplos** na página **Regras de dados da oferta** .</span><span class="sxs-lookup"><span data-stu-id="ffe25-166">You can download sample offer data rule sets on the **Samples** tab on the **Offer data rules** page.</span></span>

> - <span data-ttu-id="ffe25-167">Quando um criador de oferta substitui os valores recomendados pelas regras de dados da oferta, a oferta é sinalizada como não padrão e o fluxo de trabalho de aprovação de oferta será obrigatório.</span><span class="sxs-lookup"><span data-stu-id="ffe25-167">When an offer creator overrides the values that are recommended by the offer data rules, the offer is flagged as non-standard and offer approval workflow will be mandated.</span></span>

## <a name="document-templates"></a><span data-ttu-id="ffe25-168">Modelos de documento</span><span class="sxs-lookup"><span data-stu-id="ffe25-168">Document templates</span></span>

<span data-ttu-id="ffe25-169">Um modelo de documento de oferta pode ajudar os administradores a criarem cartas de oferta.</span><span class="sxs-lookup"><span data-stu-id="ffe25-169">An offer document template can help administrators create offer letters.</span></span> <span data-ttu-id="ffe25-170">O modelo de documento de oferta é uma combinação do texto que fará parte da oferta bem como os espaços reservados de dados da oferta definidos.</span><span class="sxs-lookup"><span data-stu-id="ffe25-170">The offer document template is a combination of the text that will be part of the offer as well as the defined offer data placeholders.</span></span> 

<span data-ttu-id="ffe25-171">Para criar um modelo de documento da oferta, faça o seguinte.</span><span class="sxs-lookup"><span data-stu-id="ffe25-171">To create an offer document template, do the following.</span></span>

1.  <span data-ttu-id="ffe25-172">Vá para **Gerenciamento de ofertas**.</span><span class="sxs-lookup"><span data-stu-id="ffe25-172">Go to **Offer management**.</span></span>

1.  <span data-ttu-id="ffe25-173">Expanda a seção **Biblioteca** no painel de navegação esquerdo e vá para **Modelos**.</span><span class="sxs-lookup"><span data-stu-id="ffe25-173">Expand the **Library** section in the left navigation pane and go to **Templates**.</span></span>

    <span data-ttu-id="ffe25-174">A página **Modelos** exibirá uma lista de modelos de documento que já foram definidos.</span><span class="sxs-lookup"><span data-stu-id="ffe25-174">The **Templates** page will display a list of document templates that have already been defined.</span></span>

1.  <span data-ttu-id="ffe25-175">Para criar um novo modelo de documento, clique em **Novo Modelo**.</span><span class="sxs-lookup"><span data-stu-id="ffe25-175">To create a new document template, click **New Template**.</span></span>

1.  <span data-ttu-id="ffe25-176">Insira um novo exclusivo para o modelo e clique em **Criar**.</span><span class="sxs-lookup"><span data-stu-id="ffe25-176">Enter a unique name for the template and click **Create**.</span></span>

1.  <span data-ttu-id="ffe25-177">Use o editor de rich text para inserir ou editar o conteúdo do documenta da oferta.</span><span class="sxs-lookup"><span data-stu-id="ffe25-177">Use the rich text editor to insert or edit the offer document content.</span></span> <span data-ttu-id="ffe25-178">Você pode inserir tabelas, imagens e hiperlinks usando as opções disponíveis na parte superior do editor de texto.</span><span class="sxs-lookup"><span data-stu-id="ffe25-178">You can insert tables, images, and hyperlinks using the options available at the top of the text editor.</span></span>

1.  <span data-ttu-id="ffe25-179">Você pode inserir espaços reservados de dados da oferta no documento de modelo da oferta:</span><span class="sxs-lookup"><span data-stu-id="ffe25-179">You can insert offer data placeholders in the offer template document by:</span></span>

    - <span data-ttu-id="ffe25-180">Arrastando e soltando do painel direito.</span><span class="sxs-lookup"><span data-stu-id="ffe25-180">Dragging and dropping from the right pane.</span></span>

    - <span data-ttu-id="ffe25-181">Criando a hashtag do espaço reservado dos dados da oferta diretamente na posição.</span><span class="sxs-lookup"><span data-stu-id="ffe25-181">Hashtag the offer data placeholder directly into position.</span></span> <span data-ttu-id="ffe25-182">Digite **\#** e então comece a digitar o nome do espaço reservado de dados da oferta.</span><span class="sxs-lookup"><span data-stu-id="ffe25-182">Type **\#** and then start typing the name of the offer data placeholder.</span></span> <span data-ttu-id="ffe25-183">As opções aparecerão na lista suspensa.</span><span class="sxs-lookup"><span data-stu-id="ffe25-183">Options will appear in the drop-down list.</span></span> <span data-ttu-id="ffe25-184">Clique ou pressione **Enter** para inserir o espaço reservado de dados da oferta.</span><span class="sxs-lookup"><span data-stu-id="ffe25-184">Click or press **Enter** to insert the offer data placeholder.</span></span>

    >[!NOTE]
    > - <span data-ttu-id="ffe25-185">Para associar um espaço reservado ao modelo de documento de oferta sem expor o valor ao candidato, passe o mouse sobre o espaço reservado de dados da oferta e clique no ícone **Fixar**.</span><span class="sxs-lookup"><span data-stu-id="ffe25-185">To associate a placeholder to the offer document template without exposing its value to the candidate, hover over the offer data placeholder and click the **Pin** icon.</span></span> <span data-ttu-id="ffe25-186">Isso enviará por push o espaço reservado para a seção **Dados da oferta fixados** do modelo de documento da oferta.</span><span class="sxs-lookup"><span data-stu-id="ffe25-186">This will push the placeholder to the **Pinned offer data** section of the offer document template.</span></span> <span data-ttu-id="ffe25-187">Para desafixar, siga as mesmas etapas, mas clique em **Desafixar** na lista dos espaços reservados de dados da oferta.</span><span class="sxs-lookup"><span data-stu-id="ffe25-187">To unpin, follow the same steps but click **Unpin** in the list of offer data placeholders.</span></span>

    > - <span data-ttu-id="ffe25-188">Para exibir a lista dos espaços reservados de dados da oferta ativos, alterne para a guia **Ativo** no painel direito.</span><span class="sxs-lookup"><span data-stu-id="ffe25-188">To view the list of active offer data placeholders, switch to the **Active** tab in the right pane.</span></span>

    > - <span data-ttu-id="ffe25-189">Se você inserir um espaço reservado orientado por um conjunto de regras de dados da oferta, poderá consultar a dependência do espaço reservado de dados da oferta em outros valores.</span><span class="sxs-lookup"><span data-stu-id="ffe25-189">If you insert a placeholder that is driven by an offer data rule set, you can see the dependency of that offer data placeholder on other values.</span></span>

    > - <span data-ttu-id="ffe25-190">Como alternativa, você pode **Importar** o conteúdo de um arquivo .docx no computador local e editar quando necessário.</span><span class="sxs-lookup"><span data-stu-id="ffe25-190">Alternatively, you can **Import** the content from a .docx file on your local machine and edit as required.</span></span> <span data-ttu-id="ffe25-191">Dessa forma, não será necessário digitar todo o conteúdo no editor.</span><span class="sxs-lookup"><span data-stu-id="ffe25-191">That way, you don’t have to type in all the content in the editor.</span></span>

1. <span data-ttu-id="ffe25-192">Para visualizar o documento da oferta, use a opção **Visualizar** na parte superior da página.</span><span class="sxs-lookup"><span data-stu-id="ffe25-192">To preview the offer document, use the **Preview** option at the top of the page.</span></span>

1. <span data-ttu-id="ffe25-193">Para controlar se um criador da oferta pode editar o conteúdo de documentos da oferta, use a opção **Gerenciar permissão** na parte superior da página.</span><span class="sxs-lookup"><span data-stu-id="ffe25-193">To control whether an offer creator can edit the offer document content, use the **Manage permission** option at the top of the page.</span></span> <span data-ttu-id="ffe25-194">Se desejar que o criador do oferta só insira valores de espaço reservado e não edite o o texto, defina o valor da permissão como **Não**.</span><span class="sxs-lookup"><span data-stu-id="ffe25-194">If you want the offer creator to only insert placeholder values and not edit text, set the permission value to **No**.</span></span>

1. <span data-ttu-id="ffe25-195">Clique em **Salvar** para salvar seu progresso.</span><span class="sxs-lookup"><span data-stu-id="ffe25-195">Click **Save** to save your progress.</span></span> <span data-ttu-id="ffe25-196">O modelo será salvo em um estado de rascunho.</span><span class="sxs-lookup"><span data-stu-id="ffe25-196">The template will be saved in a draft state.</span></span>

1. <span data-ttu-id="ffe25-197">Para finalizar e marcar o documento como publicado, clique em **Concluir**.</span><span class="sxs-lookup"><span data-stu-id="ffe25-197">To finalize and mark the document as published, click **Finish**.</span></span>

1. <span data-ttu-id="ffe25-198">Você pode ver quais modelos de documento estão atualmente ativos, no modo de rascunho e que foram arquivados e não são mais usados na experiência de aterrissagem da biblioteca de modelos de documento.</span><span class="sxs-lookup"><span data-stu-id="ffe25-198">You can see which document templates are currently active, in draft mode, and have been archived and are no longer in use on the document templates library landing experience.</span></span>

>[!NOTE]
> <span data-ttu-id="ffe25-199">Você pode excluir qualquer modelo de documento da oferta que não faça parte de um modelo de pacote da oferta existente.</span><span class="sxs-lookup"><span data-stu-id="ffe25-199">You can delete any offer document template that is not part of an existing offer package template.</span></span>


## <a name="offer-package-templates"></a><span data-ttu-id="ffe25-200">Modelos de pacote da oferta</span><span class="sxs-lookup"><span data-stu-id="ffe25-200">Offer package templates</span></span>

<span data-ttu-id="ffe25-201">Os pacotes da oferta são os artefatos da oferta compartilhados com o candidato e consistem em uma combinação de um ou mais modelos de documenta da oferta.</span><span class="sxs-lookup"><span data-stu-id="ffe25-201">Offer packages are the offer artifacts that are shared with the candidate and consist of a combination of one or more offer document templates.</span></span> <span data-ttu-id="ffe25-202">Para criar um pacote da oferta, faça o seguinte.</span><span class="sxs-lookup"><span data-stu-id="ffe25-202">To create an offer package, do the following.</span></span>

1.  <span data-ttu-id="ffe25-203">Vá para **Gerenciamento de ofertas**.</span><span class="sxs-lookup"><span data-stu-id="ffe25-203">Go to **Offer management**.</span></span>

1.  <span data-ttu-id="ffe25-204">Vá para **Pacotes** do painel esquerdo de navegação.</span><span class="sxs-lookup"><span data-stu-id="ffe25-204">Go to **Packages** from the left navigation pane.</span></span>

    <span data-ttu-id="ffe25-205">Uma lista de modelos de pacote ativos que estão disponíveis para uso dos criadores da oferta é exibida.</span><span class="sxs-lookup"><span data-stu-id="ffe25-205">A list of active package templates that are available for offer creators to use is displayed.</span></span>

1.  <span data-ttu-id="ffe25-206">Para criar um novo pacote da oferta, clique em **Novo Pacote**.</span><span class="sxs-lookup"><span data-stu-id="ffe25-206">To create a new offer package, click **New Package**.</span></span>

1.  <span data-ttu-id="ffe25-207">Insira um novo exclusivo e clique em **Criar**.</span><span class="sxs-lookup"><span data-stu-id="ffe25-207">Enter a unique name and click **Create**.</span></span>

1.  <span data-ttu-id="ffe25-208">Clique em **Adicionar modelo**.</span><span class="sxs-lookup"><span data-stu-id="ffe25-208">Click **Add template**.</span></span>

    >[!NOTE]
    > - <span data-ttu-id="ffe25-209">Você pode optar por criar um novo modelo ou escolher um existente.</span><span class="sxs-lookup"><span data-stu-id="ffe25-209">You can choose to create a new template or choose from an existing one.</span></span>

    > - <span data-ttu-id="ffe25-210">Se você optar por adicionar um modelo existente, precisará garantir que o modelo de documenta da oferta foi salvo, finalizado e marcado como ativo.</span><span class="sxs-lookup"><span data-stu-id="ffe25-210">If you choose to add an existing template, you need to make sure that the   offer document template was saved, finalized, and marked as   active.</span></span>
    
    > - <span data-ttu-id="ffe25-211">É possível escolher quantos modelos de documento você quiser.</span><span class="sxs-lookup"><span data-stu-id="ffe25-211">You can choose as many document templates as you want.</span></span> 
    
1.  <span data-ttu-id="ffe25-212">Clique em **Concluído** para retornar para **Gerenciamento de pacotes**.</span><span class="sxs-lookup"><span data-stu-id="ffe25-212">Click **Done** to return to **Package management**.</span></span>

    <span data-ttu-id="ffe25-213">Você pode configurar a sequência dos documentos e também marcar se o documento da oferta específica será necessário durante a criação da oferta.</span><span class="sxs-lookup"><span data-stu-id="ffe25-213">You can configure the sequence of the documents and also mark whether the specific offer document is required during offer creation.</span></span> <span data-ttu-id="ffe25-214">O criador da oferta terá uma opção de excluir os documentos marcados como **Não necessário**.</span><span class="sxs-lookup"><span data-stu-id="ffe25-214">The offer creator will have an option to delete the documents marked as **Not required**.</span></span>

1. <span data-ttu-id="ffe25-215">Para salvar o modelo de pacote da oferta para que ele seja útil para todos os criadores da oferta, clique em **Salvar e publicar**.</span><span class="sxs-lookup"><span data-stu-id="ffe25-215">To save the offer package template so that it's usable by all offer creators, click **Save and publish**.</span></span>

   <span data-ttu-id="ffe25-216">Para exibir modelos de pacote da oferta de rascunho, vá para a guia **Rascunhos**. Se uma alteração for feita no modelo de pacote da oferta, ele deverá ser salvo e republicado.</span><span class="sxs-lookup"><span data-stu-id="ffe25-216">To view draft offer package templates, go to the **Drafts** tab. If a change is made to the offer package template, it must be  saved and republished.</span></span>

## <a name="configure-an-offer-process"></a><span data-ttu-id="ffe25-217">Configurar um processo de oferta</span><span class="sxs-lookup"><span data-stu-id="ffe25-217">Configure an offer process</span></span>

<span data-ttu-id="ffe25-218">Há várias partes do processo de criação da oferta que podem ser configuradas por um administrador do Attract.</span><span class="sxs-lookup"><span data-stu-id="ffe25-218">There are several parts of the offer creation process that can be configured by an Attract administrator.</span></span>

- <span data-ttu-id="ffe25-219">**Aprovações da oferta** - escolha se as aprovações da oferta serão necessárias antes que a oferta possa ser enviada para o candidato.</span><span class="sxs-lookup"><span data-stu-id="ffe25-219">**Offer approvals** - Choose whether offer approvals are required before the offer can be sent to the candidate.</span></span> <span data-ttu-id="ffe25-220">Como administrador, você também pode decidir se todas as aprovações de oferta acontecerão de maneira sequencial ou em um fluxo de trabalho de aprovação paralelo.</span><span class="sxs-lookup"><span data-stu-id="ffe25-220">As an administrator, you can also decide whether all offer approvals will happen in a sequential manner or parallel approval workflow.</span></span> <span data-ttu-id="ffe25-221">Você também pode autorizar se os aprovadores da oferta devem adicionar um comentário junto com a aprovação da oferta.</span><span class="sxs-lookup"><span data-stu-id="ffe25-221">You can also mandate whether offer approvers must add a comment along with their offer approval.</span></span> <span data-ttu-id="ffe25-222">As aprovações da oferta são obrigatórias para todas as ofertas não padronizadas.</span><span class="sxs-lookup"><span data-stu-id="ffe25-222">Offer approvals are mandatory for all non-standard offers.</span></span>

- <span data-ttu-id="ffe25-223">**Experiência de oferta do candidato** - como administrador, você pode optar por definir se todas as ofertas terão uma data de vencimento, e nesse caso, qual deverá ser a contrapartida padrão para a data de vencimento.</span><span class="sxs-lookup"><span data-stu-id="ffe25-223">**Candidate’s offer experience** - As administrator, you can choose to set whether all offers have an expiration date, and if so, what the default offset for the expiration date should be.</span></span> <span data-ttu-id="ffe25-224">Você também pode configurar se os candidatos poderão recusar uma oferta.</span><span class="sxs-lookup"><span data-stu-id="ffe25-224">You can also configure whether candidates can decline an offer.</span></span>

- <span data-ttu-id="ffe25-225">**Assinaturas eletrônicas** - como administrador, você pode escolher o método que os candidatos possam usar para assinar ofertas.</span><span class="sxs-lookup"><span data-stu-id="ffe25-225">**e-Signatures** - As an administrator, you can also choose the method that candidates can use to sign offers.</span></span>
    - <span data-ttu-id="ffe25-226">Adobe Sign - todos os pacotes de ofertas serão enviados e assinados via Adobe Sign.</span><span class="sxs-lookup"><span data-stu-id="ffe25-226">Adobe Sign - All offer packages will be sent and signed via Adobe Sign.</span></span> <span data-ttu-id="ffe25-227">Cada criador de oferta que publica as necessidades de oferta para ter a conta do Adobe Sign conectada ao Attract.</span><span class="sxs-lookup"><span data-stu-id="ffe25-227">Each offer creator publishing the offer needs to have their Adobe Sign account connected to Attract.</span></span> <span data-ttu-id="ffe25-228">Para obter licenças e uma versão de avaliação gratuita do Adobe Sign, visite este [link](https://acrobat.adobe.com/us/en/business/integrations/microsoft-dynamics-365-for-talent.html).</span><span class="sxs-lookup"><span data-stu-id="ffe25-228">For Adobe Sign licenses and a free Trial, please visit this [link](https://acrobat.adobe.com/us/en/business/integrations/microsoft-dynamics-365-for-talent.html).</span></span>

    - <span data-ttu-id="ffe25-229">DocuSign - todos os pacotes de ofertas serão enviados e assinados via DocuSign.</span><span class="sxs-lookup"><span data-stu-id="ffe25-229">DocuSign - All offer packages will be sent and signed via DocuSign.</span></span> <span data-ttu-id="ffe25-230">Cada criador de oferta que publica as necessidades de oferta para ter a conta do DocuSign conectada ao Attract.</span><span class="sxs-lookup"><span data-stu-id="ffe25-230">Each offer creator publishing the offer needs to have their DocuSign account connected to Attract.</span></span> 
    
    - <span data-ttu-id="ffe25-231">ESign - esta é a opção padrão, pronta para usar, em que o usuário pode assinar uma oferta digitando seu nome e iniciais.</span><span class="sxs-lookup"><span data-stu-id="ffe25-231">ESign - This is the default option, provided out of the box, where the user can sign an offer by typing their name and initials.</span></span>


<span data-ttu-id="ffe25-232">Para saber mais sobre o processo de criação da oferta, consulte [Criar, aprovar e assinar ofertas](./creating-offers.md).</span><span class="sxs-lookup"><span data-stu-id="ffe25-232">To learn more about the offer creation process, see [Create, approve, and sign offers](./creating-offers.md).</span></span>
