---
title: Abrir modelos de diário financeiro no Office
description: Este tópico descreve problemas que podem ocorrer ao criar diários financeiros personalizados usando um modelo do Microsoft Excel.
author: kweekley
ms.date: 05/14/2021
ms.topic: index-page
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: roschlom
ms.search.region: Global
ms.author: kweekley
ms.search.validFrom: 2020-05-14
ms.dyn365.ops.version: 10.0.14
ms.openlocfilehash: 0773f47551b2460ec310b92b67c634b433147749
ms.sourcegitcommit: 8c5b3e872825953853ad57fc67ba6e5ae92b9afe
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/24/2021
ms.locfileid: "6089448"
---
# <a name="open-financial-journal-templates-in-office"></a><span data-ttu-id="4ae5f-103">Abrir modelos de diário financeiro no Office</span><span class="sxs-lookup"><span data-stu-id="4ae5f-103">Open financial journal templates in Office</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="4ae5f-104">Este tópico descreve problemas que podem ocorrer ao criar diários financeiros personalizados usando um modelo do Microsoft Excel.</span><span class="sxs-lookup"><span data-stu-id="4ae5f-104">This topic describes issues that might occur when you create custom financial journals by using a Microsoft Excel template.</span></span>

## <a name="symptom"></a><span data-ttu-id="4ae5f-105">Sintoma</span><span class="sxs-lookup"><span data-stu-id="4ae5f-105">Symptom</span></span>

<span data-ttu-id="4ae5f-106">Você criou um modelo personalizado do Excel para diários financeiros, mas ele não aparece no menu **Abrir linhas no Excel**.</span><span class="sxs-lookup"><span data-stu-id="4ae5f-106">You created a custom Excel template for financial journals, but it doesn't appear on the **Open lines in Excel** menu.</span></span> <span data-ttu-id="4ae5f-107">Como alternativa, ele é exibido no menu, um modelo diferente é aberto, mas quando selecionado.</span><span class="sxs-lookup"><span data-stu-id="4ae5f-107">Alternatively, it does appear on the menu, a different template is opened but when you select it.</span></span>

## <a name="resolution"></a><span data-ttu-id="4ae5f-108">Resolução</span><span class="sxs-lookup"><span data-stu-id="4ae5f-108">Resolution</span></span>

<span data-ttu-id="4ae5f-109">A funcionalidade padrão Abrir no Excel usa a fonte de dados raiz (tabela) da página atual para determinar quais modelos ou entidades de dados do Office aparecerão como opções no menu **Abrir no Excel**.</span><span class="sxs-lookup"><span data-stu-id="4ae5f-109">The default Open in Excel functionality uses the root data source (table) of the current page to determine which Office templates or data entities appear as options on the **Open in Excel** menu.</span></span> <span data-ttu-id="4ae5f-110">Esse comportamento não é uma experiência ideal para diários financeiros, porque os eles usam as mesmas tabelas (LedgerJournalTable e LedgerJournalTrans) como a fonte de dados raiz de muitos outros tipos de diários.</span><span class="sxs-lookup"><span data-stu-id="4ae5f-110">This behavior isn't an ideal experience for financial journals, because financial journals use the same tables (LedgerJournalTable and LedgerJournalTrans) as the root data source of many other types of journals.</span></span>

<span data-ttu-id="4ae5f-111">Para diários financeiros, a funcionalidade Abrir linhas no Excel destina-se a mostrar modelos que foram criados para o diário no qual você está trabalhando no contexto no momento, como o diário geral ou um diário de pagamentos.</span><span class="sxs-lookup"><span data-stu-id="4ae5f-111">For financial journals, the Open Lines in Excel functionality is intended to show templates that are designed for the journal that you're currently working in the context of, such as the general journal or a payment journal.</span></span> <span data-ttu-id="4ae5f-112">Por exemplo, um modelo que deve ser usado com um diário de pagamentos do fornecedor será criado para impor sua conta principal como uma conta de fornecedor.</span><span class="sxs-lookup"><span data-stu-id="4ae5f-112">For example, a template that is intended to be used with a vendor payment journal will be designed to enforce your primary account as a vendor account.</span></span>

<span data-ttu-id="4ae5f-113">Se quiser promover um modelo para que fique disponível nos menus **Abrir linhas no Excel** e **Abrir no Excel**, uma experiência fácil para desenvolvedores é implementar a interface de **LedgerIJournalExcelTemplate** e estender a classe de **DocuTemplateRegistrationBase**.</span><span class="sxs-lookup"><span data-stu-id="4ae5f-113">If you want to promote a template so that it's available on the **Open lines in Excel** and **Open in Excel** menus, an easy developer experience is to implement the **LedgerIJournalExcelTemplate** interface and extend the **DocuTemplateRegistrationBase** class.</span></span> <span data-ttu-id="4ae5f-114">Vários exemplos dessa abordagem estão implementados no sistema.</span><span class="sxs-lookup"><span data-stu-id="4ae5f-114">Many examples of this approach are implemented in the system.</span></span> <span data-ttu-id="4ae5f-115">Um exemplo que pode ser usado para referência é a interface de **LedgerDailyJournalExcelTemplate** que foi criada para o diário geral (ou diário).</span><span class="sxs-lookup"><span data-stu-id="4ae5f-115">One example that can be used for reference is the **LedgerDailyJournalExcelTemplate** interface that was created for the general journal (or daily journal).</span></span>

<span data-ttu-id="4ae5f-116">Quando a interface de **LedgerIJournalExcelTemplate** é implementada para o seu modelo, o menu **Abrir linhas no Excel** filtrará os modelos pelo tipo de diário do seu diário e mostrará somente os modelos disponíveis para o diário.</span><span class="sxs-lookup"><span data-stu-id="4ae5f-116">When the **LedgerIJournalExcelTemplate** interface is implemented for your template, the **Open Lines in Excel** menu will filter templates by the journal type of your journal and will show only the templates that are available for that journal.</span></span> <span data-ttu-id="4ae5f-117">A interface também fornece um método de validação que garante que um modelo não possa ser aberto para um diário se ele não atender aos requisitos de tipo de conta.</span><span class="sxs-lookup"><span data-stu-id="4ae5f-117">The interface also provides a validation method that ensures that a template can't be opened for a journal if it doesn't meet the account type requirements.</span></span> <span data-ttu-id="4ae5f-118">Por exemplo, você pode especificar que o tipo de conta deve ser de **Fornecedor** ou do tipo **Razão**.</span><span class="sxs-lookup"><span data-stu-id="4ae5f-118">For example, you can specify that the account type must be of the **Vendor** or **Ledger** type.</span></span>

<span data-ttu-id="4ae5f-119">Para obter mais informações sobre essa funcionalidade, consulte [adicionar modelos ao menu Abrir linhas no Excel](../../fin-ops-core/dev-itpro/user-interface/add-templates-open-lines-excel-menu.md).</span><span class="sxs-lookup"><span data-stu-id="4ae5f-119">For more information about this functionality, see [Add templates to the Open lines in Excel menu](../../fin-ops-core/dev-itpro/user-interface/add-templates-open-lines-excel-menu.md).</span></span>
