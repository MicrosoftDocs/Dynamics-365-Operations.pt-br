---
title: Integração da nota
description: Este tópico descreve a integração de dados da nota em gravação dupla.
author: RamaKrishnamoorthy
manager: AnnBe
ms.date: 02/22/2021
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ''
audience: Application User, IT Pro
ms.reviewer: rhaertle
ms.custom: ''
ms.assetid: ''
ms.search.region: global
ms.search.industry: ''
ms.author: ramasri
ms.dyn365.ops.version: ''
ms.search.validFrom: 2021-02-22
ms.openlocfilehash: 221be52b4d66aaa47f9a1919d5d0b9f8459b7ff9
ms.sourcegitcommit: db9b35ce6968cad8874b3c13d4c02d84e2617c8b
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/11/2021
ms.locfileid: "5577597"
---
# <a name="note-integration"></a><span data-ttu-id="a4e79-103">Integração da nota</span><span class="sxs-lookup"><span data-stu-id="a4e79-103">Note integration</span></span>

[!include [banner](../../includes/banner.md)]

[!include [rename-banner](~/includes/cc-data-platform-banner.md)]

<span data-ttu-id="a4e79-104">Durante processos comerciais, os usuários do Microsoft Dynamics 365 geralmente coletam informações sobre seus clientes.</span><span class="sxs-lookup"><span data-stu-id="a4e79-104">During business processes, Microsoft Dynamics 365 users often gather information about their customers.</span></span> <span data-ttu-id="a4e79-105">Essas informações são registradas como atividades e notas.</span><span class="sxs-lookup"><span data-stu-id="a4e79-105">This information is recorded as activities and notes.</span></span> <span data-ttu-id="a4e79-106">Este tópico descreve a integração de dados da nota em gravação dupla.</span><span class="sxs-lookup"><span data-stu-id="a4e79-106">This topic describes the integration of note data in dual-write.</span></span>

<span data-ttu-id="a4e79-107">As informações do cliente podem ser classificadas das seguintes maneiras:</span><span class="sxs-lookup"><span data-stu-id="a4e79-107">Customer information can be classified in the following ways:</span></span>

+ <span data-ttu-id="a4e79-108">**Informações acionáveis que um usuário do Dynamics 365 manipula em nome de um cliente**, por exemplo, Contoso (um usuário do Dynamics 365) está realizando uma apresentação de jogo.</span><span class="sxs-lookup"><span data-stu-id="a4e79-108">**Actionable information that a Dynamics 365 user handles on behalf of a customer** – For example, Contoso (a Dynamics 365 user) is conducting a game show.</span></span> <span data-ttu-id="a4e79-109">Um dos clientes da Contoso (um cliente) quer participar da apresentação de jogos.</span><span class="sxs-lookup"><span data-stu-id="a4e79-109">One of Contoso's customers (a customer) wants to attend the game show.</span></span> <span data-ttu-id="a4e79-110">O cliente solicita que um funcionário da Contoso marque um slot nas apresentações de jogos.</span><span class="sxs-lookup"><span data-stu-id="a4e79-110">The customer asks a Contoso employee to book a slot in the game show for them.</span></span> <span data-ttu-id="a4e79-111">A reserva ocorre no calendário do participante do evento do Contoso.</span><span class="sxs-lookup"><span data-stu-id="a4e79-111">The booking occurs in Contoso's event attendee's calendar.</span></span>
+ <span data-ttu-id="a4e79-112">**Informações Acionáveis para um usuário do Dynamics 365** – por exemplo, um cliente que esteja comprando uma unidade de superfície insere instruções especiais que indicam que o dispositivo deve estar embalado antes da entrega.</span><span class="sxs-lookup"><span data-stu-id="a4e79-112">**Actionable information for a Dynamics 365 user** – For example, a customer who is purchasing a Surface unit enters special instructions that indicate that the device should be gift wrapped before delivery.</span></span> <span data-ttu-id="a4e79-113">Essas instruções são informações acionáveis que devem ser tratadas pelo funcionário da Contoso responsável pela embalagem.</span><span class="sxs-lookup"><span data-stu-id="a4e79-113">These instructions are actionable information that should be handled by the Contoso employee who is responsible for packaging.</span></span>
+ <span data-ttu-id="a4e79-114">**Informações não acionáveis** – por exemplo, um cliente visita a loja da Contoso e, durante sua conversa com uma associação da loja, expressa interesse nos *jogos Halo* e nos acessórios de jogos.</span><span class="sxs-lookup"><span data-stu-id="a4e79-114">**Non-actionable information** – For example, a customer visits the Contoso store and, during their conversation with a store associate, expresses interest in *Halo* games and gaming accessories.</span></span> <span data-ttu-id="a4e79-115">O associado da loja anota essas informações.</span><span class="sxs-lookup"><span data-stu-id="a4e79-115">The store associate makes a note of this information.</span></span> <span data-ttu-id="a4e79-116">O mecanismo de recomendações do produto o utiliza para fazer recomendações ao cliente.</span><span class="sxs-lookup"><span data-stu-id="a4e79-116">The product recommendations engine then uses it to make recommendations to the customer.</span></span>

<span data-ttu-id="a4e79-117">Em geral, as informações acionáveis são capturadas como *atividades* nos aplicativos Finance and Operations e de engajamento do cliente.</span><span class="sxs-lookup"><span data-stu-id="a4e79-117">In general, actionable information is captured as *activities* in Finance and Operations apps and customer engagement apps.</span></span> <span data-ttu-id="a4e79-118">As informações não acionáveis são capturadas como *notas* nos aplicativos Finance and Operations e como *anotações* nos aplicativos de engajamento do cliente.</span><span class="sxs-lookup"><span data-stu-id="a4e79-118">Non-actionable information is captured as *notes* in Finance and Operations apps, and as *annotations* in customer engagement apps.</span></span>

> [!TIP]
> <span data-ttu-id="a4e79-119">Embora as notas sejam destinadas a informações não acionáveis, os aplicativos não impedem que você as utilize para armazenar e manipular informações acionáveis, caso queira usá-las dessa forma.</span><span class="sxs-lookup"><span data-stu-id="a4e79-119">Although notes are intended for non-actionable information, the apps won't prevent you from using them to store and handle actionable information if you want to use them in that way.</span></span>

<span data-ttu-id="a4e79-120">No momento, a Microsoft está lançando funcionalidades para a integração de notas.</span><span class="sxs-lookup"><span data-stu-id="a4e79-120">Microsoft is currently releasing functionality for note integration.</span></span> <span data-ttu-id="a4e79-121">(A funcionalidade para a integração de atividades será liberada posteriormente). A integração da nota está disponível para clientes, fornecedores, ordens de venda e ordens de compra.</span><span class="sxs-lookup"><span data-stu-id="a4e79-121">(Functionality for activity integration will be released later.) Note integration is available for customers, vendors, sales orders, and purchase orders.</span></span>

## <a name="create-a-note-in-a-customer-engagement-app"></a><span data-ttu-id="a4e79-122">Criar uma nota em um aplicativo de engajamento do cliente</span><span class="sxs-lookup"><span data-stu-id="a4e79-122">Create a note in a customer engagement app</span></span>

<span data-ttu-id="a4e79-123">Para criar uma nota em um aplicativo de engajamento do cliente e sincronizá-la com um aplicativo Finance and Operations, siga estas etapas.</span><span class="sxs-lookup"><span data-stu-id="a4e79-123">To create a note in a customer engagement app and then sync it to a Finance and Operations app, follow these steps.</span></span>

1. <span data-ttu-id="a4e79-124">No aplicativo engajamento do cliente, abra o registro da conta de um cliente.</span><span class="sxs-lookup"><span data-stu-id="a4e79-124">In the customer engagement app, open the account record for a customer.</span></span>
2. <span data-ttu-id="a4e79-125">No painel **Linha de tempo**, selecione o sinal de adição (**+**) e, em seguida, selecione **Nota** para criar uma nota.</span><span class="sxs-lookup"><span data-stu-id="a4e79-125">In the **Timeline** pane, select the plus sign (**+**), and then select **Note** to create a note.</span></span>

    ![Criando uma nota em um aplicativo de engajamento do cliente](media/notes-ce-1.png)

3. <span data-ttu-id="a4e79-127">Informe um título e uma descrição e selecione **Adicionar nota**.</span><span class="sxs-lookup"><span data-stu-id="a4e79-127">Enter a title and description, and then select **Add note**.</span></span>

    ![Inserindo um título e uma descrição](media/notes-ce-2.png)

    <span data-ttu-id="a4e79-129">A nova nota é adicionada à linha do tempo do cliente.</span><span class="sxs-lookup"><span data-stu-id="a4e79-129">The new note is added to the customer timeline.</span></span>

    ![Nova nota na linha do tempo do cliente](media/notes-ce-3.png)

4. <span data-ttu-id="a4e79-131">Entre no aplicativo Finance and Operations e abra o mesmo registro de cliente.</span><span class="sxs-lookup"><span data-stu-id="a4e79-131">Sign in to the Finance and Operations app, and open the same customer record.</span></span> <span data-ttu-id="a4e79-132">Lembre-se de que o botão **Anexos** (símbolo de clipe de papel) no canto superior direito indica que o registro tem um anexo.</span><span class="sxs-lookup"><span data-stu-id="a4e79-132">Notice that the **Attachments** button (paperclip symbol) in the upper-right corner indicates that the record has an attachment.</span></span>

    ![Notificação sobre um anexo](media/notes-ce-4.png)

5. <span data-ttu-id="a4e79-134">Selecione o botão **Anexos** para abrir a página **Anexos**.</span><span class="sxs-lookup"><span data-stu-id="a4e79-134">Select the **Attachments** button to open the **Attachments** page.</span></span> <span data-ttu-id="a4e79-135">Você deve encontrar a nota criada no aplicativo de engajamento do cliente.</span><span class="sxs-lookup"><span data-stu-id="a4e79-135">You should find the note that you created in the customer engagement app.</span></span>

    ![Observação do aplicativo de engajamento do cliente](media/notes-ce-5.png)

<span data-ttu-id="a4e79-137">Todas as atualizações da nota são sincronizadas para frente e para trás entre o aplicativo Finance and Operations e o aplicativo de engajamento do cliente.</span><span class="sxs-lookup"><span data-stu-id="a4e79-137">Any updates to the note are synced back and forth between the Finance and Operations app and the customer engagement app.</span></span>

## <a name="create-a-note-in-a-finance-and-operations-app"></a><span data-ttu-id="a4e79-138">Criar uma nota em um aplicativo do Finance and Operations</span><span class="sxs-lookup"><span data-stu-id="a4e79-138">Create a note in a Finance and Operations app</span></span>

<span data-ttu-id="a4e79-139">Também é possível criar uma nota em um aplicativo Finance and Operations e ela será sincronizada em um aplicativo de engajamento do cliente.</span><span class="sxs-lookup"><span data-stu-id="a4e79-139">You can also create a note in a Finance and Operations app, and it will be synced to a customer engagement app.</span></span>

<span data-ttu-id="a4e79-140">Para criar uma nota em um aplicativo Finance and Operations e sincronizá-la para um aplicativo de engajamento do cliente, siga estas etapas.</span><span class="sxs-lookup"><span data-stu-id="a4e79-140">To create a note in a Finance and Operations app and then sync it to a customer engagement app, follow these steps.</span></span>

1. <span data-ttu-id="a4e79-141">No aplicativo Finance and Operations na página **Anexos**, selecione **Nova** \> **Nota**.</span><span class="sxs-lookup"><span data-stu-id="a4e79-141">In the Finance and Operations app, on the **Attachments** page, select **New** \> **Note**.</span></span>

    ![Criando uma nota no aplicativo Finance and Operations](media/notes-fo-1.png)

2. <span data-ttu-id="a4e79-143">Insira um título e um breve conjunto de instruções e selecione **Salvar**.</span><span class="sxs-lookup"><span data-stu-id="a4e79-143">Enter a title and a brief set of instructions, and then select **Save**.</span></span>

    ![Inserindo um título e instruções](media/notes-fo-2.png)

3. <span data-ttu-id="a4e79-145">No aplicativo de engajamento do cliente, atualize o registro.</span><span class="sxs-lookup"><span data-stu-id="a4e79-145">In the customer engagement app, update the record.</span></span> <span data-ttu-id="a4e79-146">Você deve encontrar a nova nota na linha do tempo.</span><span class="sxs-lookup"><span data-stu-id="a4e79-146">You should find the new note on the timeline.</span></span>

    ![Nova nota na linha do tempo no aplicativo de engajamento do cliente](media/notes-fo-3.png)

<span data-ttu-id="a4e79-148">Você pode classificar uma nota como interna ou externa.</span><span class="sxs-lookup"><span data-stu-id="a4e79-148">You can classify a note as either internal or external.</span></span>

- <span data-ttu-id="a4e79-149">No aplicativo Finance and Operations, na página **Anexos**, abra a anotação e, no campo **Restrição**, selecione **Interno** ou **Externo**.</span><span class="sxs-lookup"><span data-stu-id="a4e79-149">In the Finance and Operations app, on the **Attachments** page, open the note, and then, in the **Restriction** field, select **Internal** or **External**.</span></span>

    ![Campo de restrição](media/notes-fo-4.png)

<span data-ttu-id="a4e79-151">Você também pode cria uma URL.</span><span class="sxs-lookup"><span data-stu-id="a4e79-151">You can also create a URL.</span></span>

1. <span data-ttu-id="a4e79-152">No aplicativo Finance and Operations, na página **Anexos**, selecione **Nova** \> **URL**.</span><span class="sxs-lookup"><span data-stu-id="a4e79-152">In the Finance and Operations app, on the **Attachments** page, select **New** \> **URL**.</span></span>
2. <span data-ttu-id="a4e79-153">Insira um título e uma URL.</span><span class="sxs-lookup"><span data-stu-id="a4e79-153">Enter a title and the URL.</span></span>
3. <span data-ttu-id="a4e79-154">No campo **Restrição**, selecione **Interno** ou **Externo**.</span><span class="sxs-lookup"><span data-stu-id="a4e79-154">In the **Restriction** field, select **Internal** or **External**.</span></span>

    ![Criando uma URL no aplicativo Finance and Operations](media/notes-fo-5.png)

4. <span data-ttu-id="a4e79-156">Selecione **Salvar**.</span><span class="sxs-lookup"><span data-stu-id="a4e79-156">Select **Save**.</span></span>

    <span data-ttu-id="a4e79-157">Como os aplicativos do engajamento do cliente não têm um tipo de URL, a URL é integrada com a gravação dupla como uma nota.</span><span class="sxs-lookup"><span data-stu-id="a4e79-157">Because customer engagement apps don't have a URL type, the URL is integrated with dual-write as a note.</span></span>

    ![URL aparecendo uma nota em um aplicativo de engajamento do cliente](media/notes-ce-6.png)

> [!NOTE]
> <span data-ttu-id="a4e79-159">Não há suporte para anexos de arquivo.</span><span class="sxs-lookup"><span data-stu-id="a4e79-159">File attachments aren't supported.</span></span>

## <a name="templates"></a><span data-ttu-id="a4e79-160">Modelos</span><span class="sxs-lookup"><span data-stu-id="a4e79-160">Templates</span></span>

<span data-ttu-id="a4e79-161">A integração da nota inclui um conjunto de mapas de tabelas que funcionam juntos durante a interação de dados, conforme mostrado na tabela a seguir.</span><span class="sxs-lookup"><span data-stu-id="a4e79-161">Note integration includes a collection of table maps that work together during data interaction, as shown in the following table.</span></span>

| <span data-ttu-id="a4e79-162">Aplicativo Finance and Operations</span><span class="sxs-lookup"><span data-stu-id="a4e79-162">Finance and Operations app</span></span> | <span data-ttu-id="a4e79-163">Aplicativo Customer Engagement</span><span class="sxs-lookup"><span data-stu-id="a4e79-163">Customer engagement app</span></span> | <span data-ttu-id="a4e79-164">descrição</span><span class="sxs-lookup"><span data-stu-id="a4e79-164">Description</span></span> |
|----------------------------|-------------------------|-------------|
| [<span data-ttu-id="a4e79-165">Anexos do Cliente</span><span class="sxs-lookup"><span data-stu-id="a4e79-165">Customer Attachments</span></span>](mapping-reference.md#230) | <span data-ttu-id="a4e79-166">Anotações</span><span class="sxs-lookup"><span data-stu-id="a4e79-166">Annotations</span></span> | <span data-ttu-id="a4e79-167">Empresas que usam texto sem formatação e URLs para capturar informações específicas do cliente (para organizações e pessoas).</span><span class="sxs-lookup"><span data-stu-id="a4e79-167">Businesses that use plain text and URLs to capture customer-specific information (for both organizations and persons).</span></span> |
| [<span data-ttu-id="a4e79-168">Anexos de documentos do fornecedor</span><span class="sxs-lookup"><span data-stu-id="a4e79-168">Vendor document attachments</span></span>](mapping-reference.md#231) | <span data-ttu-id="a4e79-169">Anotações</span><span class="sxs-lookup"><span data-stu-id="a4e79-169">Annotations</span></span> | <span data-ttu-id="a4e79-170">Empresas que usam texto sem formatação e URLs para capturar informações específicas do fornecedor (para organizações e pessoas).</span><span class="sxs-lookup"><span data-stu-id="a4e79-170">Businesses that use plain text and URLs to capture vendor-specific information (for both organizations and persons).</span></span> |
| [<span data-ttu-id="a4e79-171">Anexos de documento de cabeçalho de ordem de venda</span><span class="sxs-lookup"><span data-stu-id="a4e79-171">Sales order header document attachments</span></span>](mapping-reference.md#229) | <span data-ttu-id="a4e79-172">Anotações</span><span class="sxs-lookup"><span data-stu-id="a4e79-172">Annotations</span></span> | <span data-ttu-id="a4e79-173">Empresas que usam texto sem formatação e URLs para capturar informações específicas da ordem de venda.</span><span class="sxs-lookup"><span data-stu-id="a4e79-173">Businesses that use plain text and URLs to capture sales order–specific information.</span></span> |
| [<span data-ttu-id="a4e79-174">Anexos de documento de cabeçalho de ordem de compra</span><span class="sxs-lookup"><span data-stu-id="a4e79-174">Purchase order header document attachments</span></span>](mapping-reference.md#232) | <span data-ttu-id="a4e79-175">Anotações</span><span class="sxs-lookup"><span data-stu-id="a4e79-175">Annotations</span></span> | <span data-ttu-id="a4e79-176">Empresas que usam texto sem formatação e URLs para capturar informações específicas da ordem de compra.</span><span class="sxs-lookup"><span data-stu-id="a4e79-176">Businesses that use plain text and URLs to capture purchase order–specific information.</span></span> |

<span data-ttu-id="a4e79-177">Para obter mais informações, consulte [Referência de mapeamento de gravação dupla](mapping-reference.md).</span><span class="sxs-lookup"><span data-stu-id="a4e79-177">For more information, see [Dual-write mapping reference](mapping-reference.md).</span></span>
