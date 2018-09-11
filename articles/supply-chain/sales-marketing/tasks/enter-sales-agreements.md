--- 
title: Inserir contratos de venda
description: "Este procedimento mostra como criar um contrato de venda que compromete um de seus clientes a comprar um produto por um valor acordado durante um período, em troca de descontos especiais."
author: omulvad
manager: AnnBe
ms.date: 8/29/2018
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: SalesAgreementListPage, SalesAgreementCreate, SalesAgreement, InventItemIdLookupSimple, AgreementConfirmRunForm, SrsReportViewerForm
audience: Application User
ms.reviewer: kfend
ms.search.scope: Core, Operations
ms.search.region: Global
ms.search.industry: Service industries
ms.author: omulvad
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 32d71167fdad65cb1dec37671999a497759ca484
ms.openlocfilehash: a609cfa6e34159e1037e9c046a3f1658baecbebf
ms.contentlocale: pt-br
ms.lasthandoff: 09/11/2018

---
# <a name="enter-sales-agreements"></a><span data-ttu-id="7a4bc-103">Inserir contratos de venda</span><span class="sxs-lookup"><span data-stu-id="7a4bc-103">Enter sales agreements</span></span>

[!include [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="7a4bc-104">Este procedimento mostra como criar um contrato de venda que compromete um de seus clientes a comprar um produto</span><span class="sxs-lookup"><span data-stu-id="7a4bc-104">This procedure shows you how to create a sales agreement that commits one of your customers to buy a product for an</span></span>

<span data-ttu-id="7a4bc-105">, com um valor acordado durante um período, em troca de descontos especiais.</span><span class="sxs-lookup"><span data-stu-id="7a4bc-105">agreed amount over time in exchange for special discounts.</span></span> <span data-ttu-id="7a4bc-106">Você pode executar esse procedimento na empresa USMF de dados demo, ou usando seus próprios dados.</span><span class="sxs-lookup"><span data-stu-id="7a4bc-106">You can run this procedure in demo data company USMF or on your own data.</span></span>


## <a name="set-up-sales-agreement-header"></a><span data-ttu-id="7a4bc-107">Configurar cabeçalho do contrato de venda</span><span class="sxs-lookup"><span data-stu-id="7a4bc-107">Set up sales agreement header</span></span>
1. <span data-ttu-id="7a4bc-108">Vá para Vendas e marketing > Contratos de venda > Contratos de venda.</span><span class="sxs-lookup"><span data-stu-id="7a4bc-108">Go to Sales and marketing > Sales agreements > Sales agreements.</span></span>
2. <span data-ttu-id="7a4bc-109">Clique em Novo.</span><span class="sxs-lookup"><span data-stu-id="7a4bc-109">Click New.</span></span>
3. <span data-ttu-id="7a4bc-110">No campo Conta do cliente, clique no botão suspenso para abrir a pesquisa.</span><span class="sxs-lookup"><span data-stu-id="7a4bc-110">In the Customer account field, click the drop-down button to open the lookup.</span></span>
4. <span data-ttu-id="7a4bc-111">Na lista, localize e selecione o registro desejado.</span><span class="sxs-lookup"><span data-stu-id="7a4bc-111">In the list, find and select the desired record.</span></span>
5. <span data-ttu-id="7a4bc-112">Na lista, clique no link na linha selecionada.</span><span class="sxs-lookup"><span data-stu-id="7a4bc-112">In the list, click the link in the selected row.</span></span>
6. <span data-ttu-id="7a4bc-113">No campo Classificação do contrato de venda, clique no botão suspenso para abrir a pesquisa.</span><span class="sxs-lookup"><span data-stu-id="7a4bc-113">In the Sales agreement classification field, click the drop-down button to open the lookup.</span></span>
7. <span data-ttu-id="7a4bc-114">Na lista, clique no link na linha selecionada.</span><span class="sxs-lookup"><span data-stu-id="7a4bc-114">In the list, click the link in the selected row.</span></span>
8. <span data-ttu-id="7a4bc-115">Expanda a seção Geral.</span><span class="sxs-lookup"><span data-stu-id="7a4bc-115">Expand the General section.</span></span>
9. <span data-ttu-id="7a4bc-116">No campo Compromisso padrão, selecione 'Compromisso de valor do produto'.</span><span class="sxs-lookup"><span data-stu-id="7a4bc-116">In the Default commitment field, select 'Product value commitment'.</span></span>
    * <span data-ttu-id="7a4bc-117">Um tipo compromisso é um critério obrigatório que você deve atribuir ao contrato para definir como o contrato do acordo será atendido.</span><span class="sxs-lookup"><span data-stu-id="7a4bc-117">A commitment type is a mandatory criterion that you must assign to the agreement to define how the agreement contract will be fulfilled.</span></span> <span data-ttu-id="7a4bc-118">Os quatro tipos predefinidos permitem configurar o destino do compromisso do cliente, expresso como uma quantidade ou um valor.</span><span class="sxs-lookup"><span data-stu-id="7a4bc-118">The four predefined types let you set up the customer's commitment target, expressed as a quantity or a value.</span></span> <span data-ttu-id="7a4bc-119">O tipo de compromisso de quantidade só pode ser aplicado a um produto específico, mas os tipos com base no valor são aplicáveis à vendas de produtos específicos e não específicos.</span><span class="sxs-lookup"><span data-stu-id="7a4bc-119">The quantity commitment type can only be applied to a specific product, but the value-based types are applicable to sales of both specific and non-specific products.</span></span>  
10. <span data-ttu-id="7a4bc-120">No campo Data de vencimento, defina a data para uma data futura na qual você deseja que o contrato expire.</span><span class="sxs-lookup"><span data-stu-id="7a4bc-120">In the Expiration date field, set the date to a future date when you want the agreement to expire.</span></span>
11. <span data-ttu-id="7a4bc-121">Clique em OK.</span><span class="sxs-lookup"><span data-stu-id="7a4bc-121">Click OK.</span></span>

## <a name="set-up-product-value-commitment-lines"></a><span data-ttu-id="7a4bc-122">Configurar linhas de compromisso com o valor do produto</span><span class="sxs-lookup"><span data-stu-id="7a4bc-122">Set up product value commitment lines</span></span>
1. <span data-ttu-id="7a4bc-123">Clique em Adicionar linha.</span><span class="sxs-lookup"><span data-stu-id="7a4bc-123">Click Add line.</span></span>
2. <span data-ttu-id="7a4bc-124">No campo Número de item, clique no botão suspenso para abrir a pesquisa.</span><span class="sxs-lookup"><span data-stu-id="7a4bc-124">In the Item number field, click the drop-down button to open the lookup.</span></span>
3. <span data-ttu-id="7a4bc-125">Na lista, localize e selecione o PDV desejado.</span><span class="sxs-lookup"><span data-stu-id="7a4bc-125">In the list, find and select the desired record.</span></span>
4. <span data-ttu-id="7a4bc-126">Na lista, clique no link na linha selecionada.</span><span class="sxs-lookup"><span data-stu-id="7a4bc-126">In the list, click the link in the selected row.</span></span>
    * <span data-ttu-id="7a4bc-127">O tipo de compromisso escolhido para o contrato afeta o tipo de informação que você pode inserir para as linhas do contrato.</span><span class="sxs-lookup"><span data-stu-id="7a4bc-127">The type of commitment that you have chosen for the agreement affects the kind of information you can enter for the agreement lines.</span></span> <span data-ttu-id="7a4bc-128">Por exemplo, para um contrato baseado em valor, especifique o valor líquido total (na moeda concordada) para o qual o cliente se compromete a comprar suas mercadorias.</span><span class="sxs-lookup"><span data-stu-id="7a4bc-128">For example, for a value-based agreement you must specify the total net amount (in the agreed currency) for which the customer commits to buys goods from you.</span></span> <span data-ttu-id="7a4bc-129">Neste exemplo os campos Quantidade e Unidade na linha não estão disponíveis porque você está criando um acordo para que o cliente compre um valor específico de um produto.</span><span class="sxs-lookup"><span data-stu-id="7a4bc-129">In this example the Quantity and Unit fields on the line are unavailable because you’re creating an agreement for the customer to buy a specific value of a product.</span></span>   
5. <span data-ttu-id="7a4bc-130">No campo Valor líquido, insira o valor monetário que o cliente confirmou para compra.</span><span class="sxs-lookup"><span data-stu-id="7a4bc-130">In the Net amount field, enter the monetary amount that the customer has committed to buying.</span></span>
6. <span data-ttu-id="7a4bc-131">No campo Percentual de desconto, insira um valor percentual que se aplica às linhas da ordem de venda do cliente que estão associadas a esse contrato.</span><span class="sxs-lookup"><span data-stu-id="7a4bc-131">In the Discount percent field, enter a percentage value that will apply to the customer's sales order lines that are linked to this agreement.</span></span>
7. <span data-ttu-id="7a4bc-132">Expanda a seção Detalhes da linha.</span><span class="sxs-lookup"><span data-stu-id="7a4bc-132">Expand the Line details section.</span></span>
8. <span data-ttu-id="7a4bc-133">Selecione Sim no campo Imposição de valor máx.</span><span class="sxs-lookup"><span data-stu-id="7a4bc-133">Select Yes in the Max is enforced field.</span></span>
    * <span data-ttu-id="7a4bc-134">Selecionar Imposição de valor máx. significa que o valor total de todas as linhas da ordem de venda que usam os preços promocionais especiais do compromisso, descontos e/ou condições de pagamento não devem exceder o valor especificado no compromisso.</span><span class="sxs-lookup"><span data-stu-id="7a4bc-134">Selecting Max is enforced means that the total amount of all the sales order lines that use the commitment's special prices, discounts and/or payment terms must not exceed the amount specified on the commitment.</span></span>  
    * <span data-ttu-id="7a4bc-135">Os valores mínimo e máximo especificam um intervalo de valores que deve ser vendido em cada ordem de venda que usa o contrato selecionado.</span><span class="sxs-lookup"><span data-stu-id="7a4bc-135">The minimum and maximum release amounts specify a range of values that must be sold on each sales order that uses the selected agreement.</span></span>   
9. <span data-ttu-id="7a4bc-136">Expanda a seção Cabeçalho do contrato de venda.</span><span class="sxs-lookup"><span data-stu-id="7a4bc-136">Expand the Sales agreement header section.</span></span>
    * <span data-ttu-id="7a4bc-137">A menos que o status do contrato seja definido como Em vigor, as ordens de venda não podem ser associadas ao contrato e, consequentemente, não podem contribuir para o atendimento desse contrato.</span><span class="sxs-lookup"><span data-stu-id="7a4bc-137">Unless the status of the agreement is set to Effective, sales orders cannot be associated with the agreement and can therefore not contribute to the fulfilment of that agreement.</span></span> <span data-ttu-id="7a4bc-138">Você pode alterar o status manualmente neste estágio.</span><span class="sxs-lookup"><span data-stu-id="7a4bc-138">You can change the status manually at this stage.</span></span> <span data-ttu-id="7a4bc-139">No entanto, o status normalmente é alterado quando você confirma o contrato para o cliente.</span><span class="sxs-lookup"><span data-stu-id="7a4bc-139">However, the status would normally be changed when you confirm the agreement for the customer.</span></span>  
10. <span data-ttu-id="7a4bc-140">No Painel de Ação, clique em Contrato de venda.</span><span class="sxs-lookup"><span data-stu-id="7a4bc-140">On the Action Pane, click Sales agreement.</span></span>
11. <span data-ttu-id="7a4bc-141">Clique em Confirmação.</span><span class="sxs-lookup"><span data-stu-id="7a4bc-141">Click Confirmation.</span></span>
    * <span data-ttu-id="7a4bc-142">Certifique-se de que a opção Marcar contrato como em vigor está definida como Sim.</span><span class="sxs-lookup"><span data-stu-id="7a4bc-142">Make sure that the Mark agreement as effective option is set to Yes.</span></span>  
12. <span data-ttu-id="7a4bc-143">Selecione Sim no campo Imprimir relatório.</span><span class="sxs-lookup"><span data-stu-id="7a4bc-143">Select Yes in the Print report field.</span></span>
13. <span data-ttu-id="7a4bc-144">Clique em OK.</span><span class="sxs-lookup"><span data-stu-id="7a4bc-144">Click OK.</span></span>
14. <span data-ttu-id="7a4bc-145">Feche a página.</span><span class="sxs-lookup"><span data-stu-id="7a4bc-145">Close the page.</span></span>
    * <span data-ttu-id="7a4bc-146">O contrato agora está em vigor e você pode começar a vincular as ordens do cliente ao contrato, para deslocar em relação ao destino comprometido.</span><span class="sxs-lookup"><span data-stu-id="7a4bc-146">The agreement is now effective and you can start linking the customer's orders to the agreement, to offset against the committed target.</span></span>  


