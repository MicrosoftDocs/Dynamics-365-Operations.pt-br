---
title: Restrições de expressão e restrições de tabela nos modelos de configuração do produto
description: Este tópico descreve o uso de restrições de expressão e de tabela. As restrições controlam os valores de atributo que podem ser selecionados quando você configura produtos para uma ordem de venda, cotação de venda, ordem de compra, ou uma ordem de produção. É possível usar restrições de expressão ou de tabela, dependendo de como você preferir criar as restrições.
author: cvocph
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: PCGlobalTableConstraintEdit, PCProductConfigurationModelDetails, PCTableConstraintAttachAttributeTree, PCTableConstraintDefinition
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations
ms.custom: 53111
ms.assetid: 5c12b1f2-eb89-4648-a755-de412f2eadd6
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: conradv
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 88d52031f4c916f5ec3e970f38864977e69a9d9a
ms.sourcegitcommit: 9d4c7edd0ae2053c37c7d81cdd180b16bf3a9d3b
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/15/2019
ms.locfileid: "1546241"
---
# <a name="expression-constraints-and-table-constraints-in-product-configuration-models"></a><span data-ttu-id="89444-105">Restrições de expressão e restrições de tabela nos modelos de configuração do produto</span><span class="sxs-lookup"><span data-stu-id="89444-105">Expression constraints and table constraints in product configuration models</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="89444-106">Este tópico descreve o uso de restrições de expressão e de tabela.</span><span class="sxs-lookup"><span data-stu-id="89444-106">This topic describes the use of expression constraints and table constraints.</span></span> <span data-ttu-id="89444-107">As restrições controlam os valores de atributo que podem ser selecionados quando você configura produtos para uma ordem de venda, cotação de venda, ordem de compra, ou uma ordem de produção.</span><span class="sxs-lookup"><span data-stu-id="89444-107">Constraints control the attribute values that you can select when you configure products for a sales order, sales quotation, purchase order, or production order.</span></span> <span data-ttu-id="89444-108">É possível usar restrições de expressão ou de tabela, dependendo de como você preferir criar as restrições.</span><span class="sxs-lookup"><span data-stu-id="89444-108">You can use expression constraints or table constraints, depending on how you prefer to build the constraints.</span></span> 

<span data-ttu-id="89444-109">As restrições são usadas para controlar os valores de atributo que podem ser selecionados quando você configura produtos para uma ordem de venda, cotação de venda, ordem de compra ou uma ordem de produção.</span><span class="sxs-lookup"><span data-stu-id="89444-109">Constraints are used to control the attribute values that you can select when you configure products for a sales order, sales quotation, purchase order, or production order.</span></span> <span data-ttu-id="89444-110">É possível usar restrições de expressão ou de tabela, dependendo de como você preferir criar as restrições.</span><span class="sxs-lookup"><span data-stu-id="89444-110">You can use expression constraints or table constraints, depending on how you prefer to build the constraints.</span></span>

## <a name="what-are-expression-constraints"></a><span data-ttu-id="89444-111">O que são as restrições de expressão?</span><span class="sxs-lookup"><span data-stu-id="89444-111">What are expression constraints?</span></span>
<span data-ttu-id="89444-112">As restrições de expressão são caracterizadas por uma expressão que usa operadores e funções aritméticos e boolianos.</span><span class="sxs-lookup"><span data-stu-id="89444-112">Expression constraints are characterized by an expression that uses arithmetic and Boolean operators and functions.</span></span> <span data-ttu-id="89444-113">Uma restrição de expressão será criado para um determinado componente em um modelo de configuração de produto.</span><span class="sxs-lookup"><span data-stu-id="89444-113">An expression constraint is written for a specific component in a product configuration model.</span></span> <span data-ttu-id="89444-114">Não pode ser reutilizada ou compartilhada com outro componente.</span><span class="sxs-lookup"><span data-stu-id="89444-114">It can't be reused by or shared with another component.</span></span> <span data-ttu-id="89444-115">No entanto, as restrições de expressão para um componente pode fazer referência a atributos dos subcomponentes do componente.</span><span class="sxs-lookup"><span data-stu-id="89444-115">However, the expression constraints for a component can reference attributes of the component's subcomponents.</span></span>

## <a name="what-are-table-constraints"></a><span data-ttu-id="89444-116">O que são as restrições de tabela?</span><span class="sxs-lookup"><span data-stu-id="89444-116">What are table constraints?</span></span>
<span data-ttu-id="89444-117">As restrições de tabela listam as combinações de valores que são permitidas para os atributos quando você configura um produto.</span><span class="sxs-lookup"><span data-stu-id="89444-117">Table constraints list the combinations of values that are allowed for attributes when you configure a product.</span></span> <span data-ttu-id="89444-118">As definições de restrição de tabela podem ser usadas genericamente.</span><span class="sxs-lookup"><span data-stu-id="89444-118">Table constraint definitions can be used generically.</span></span> <span data-ttu-id="89444-119">Ao criar uma restrição de tabela para um componente em um modelo de configuração de produto, selecione uma definição de restrição de tabela.</span><span class="sxs-lookup"><span data-stu-id="89444-119">When you create a table constraint for a component in a product configuration model, you select a table constraint definition.</span></span> <span data-ttu-id="89444-120">Para criar combinações que são permitidas, adicione tipos de atributos específicos aos componentes.</span><span class="sxs-lookup"><span data-stu-id="89444-120">To create the combinations that are allowed, you add attributes of specific types to the components.</span></span> <span data-ttu-id="89444-121">Cada tipo de atributo possui um valor específico.</span><span class="sxs-lookup"><span data-stu-id="89444-121">Each attribute type has a specific value.</span></span>

### <a name="example-of-a-table-constraint"></a><span data-ttu-id="89444-122">Exemplo de uma restrição de tabela</span><span class="sxs-lookup"><span data-stu-id="89444-122">Example of a table constraint</span></span>

<span data-ttu-id="89444-123">Este exemplo mostra como você pode limitar a configuração de um orador para especificar partes frontais e acabamentos do gabinete.</span><span class="sxs-lookup"><span data-stu-id="89444-123">This example shows how you can limit the configuration of a speaker to specific cabinet finishes and fronts.</span></span> <span data-ttu-id="89444-124">A primeira tabela mostra as partes frontais e acabamentos dos gabinetes que geralmente estão disponíveis para a configuração.</span><span class="sxs-lookup"><span data-stu-id="89444-124">The first table shows the cabinet finishes and fronts that are generally available for configuration.</span></span> <span data-ttu-id="89444-125">Os valores são definidos para os tipos de atributos **Acabamento do gabinete** e **Grade frontal**.</span><span class="sxs-lookup"><span data-stu-id="89444-125">The values are defined for the **Cabinet finish** and **Front grill** attribute types.</span></span>

| <span data-ttu-id="89444-126">Tipo de atributo</span><span class="sxs-lookup"><span data-stu-id="89444-126">Attribute type</span></span> | <span data-ttu-id="89444-127">Valores</span><span class="sxs-lookup"><span data-stu-id="89444-127">Values</span></span>                      |
|----------------|-----------------------------|
| <span data-ttu-id="89444-128">Acabamento do gabinete</span><span class="sxs-lookup"><span data-stu-id="89444-128">Cabinet finish</span></span> | <span data-ttu-id="89444-129">Preto, carvalho, branco, jacarandá</span><span class="sxs-lookup"><span data-stu-id="89444-129">Black, Oak, Rosewood, White</span></span> |
| <span data-ttu-id="89444-130">Grade frontal</span><span class="sxs-lookup"><span data-stu-id="89444-130">Front grill</span></span>    | <span data-ttu-id="89444-131">Preto, metal, branco</span><span class="sxs-lookup"><span data-stu-id="89444-131">Black, Metal, White</span></span>         |

<span data-ttu-id="89444-132">A tabela a seguir mostra as combinações que são definidas pela restrição da tabela **Cor e acabamento**.</span><span class="sxs-lookup"><span data-stu-id="89444-132">The next table shows the combinations that are defined by the **Color and finish** table constraint.</span></span> <span data-ttu-id="89444-133">Usando a restrição de tabela, você pode configurar um alto-falante com o acabamento de de carvalho e uma grade preta, um acabamento de jacarandá e uma grade branca, e assim por diante.</span><span class="sxs-lookup"><span data-stu-id="89444-133">By using this table constraint, you can configure a speaker that has an oak finish and a black grill, a Rosewood finish and a white grill, and so on.</span></span>

| <span data-ttu-id="89444-134">Concluir</span><span class="sxs-lookup"><span data-stu-id="89444-134">Finish</span></span>         | <span data-ttu-id="89444-135">Grade</span><span class="sxs-lookup"><span data-stu-id="89444-135">Grill</span></span>                       |
|----------------|-----------------------------|
| <span data-ttu-id="89444-136">Carvalho</span><span class="sxs-lookup"><span data-stu-id="89444-136">Oak</span></span>            | <span data-ttu-id="89444-137">Preto</span><span class="sxs-lookup"><span data-stu-id="89444-137">Black</span></span>                       |
| <span data-ttu-id="89444-138">Jacarandá</span><span class="sxs-lookup"><span data-stu-id="89444-138">Rosewood</span></span>       | <span data-ttu-id="89444-139">Branco</span><span class="sxs-lookup"><span data-stu-id="89444-139">White</span></span>                       |
| <span data-ttu-id="89444-140">Branco</span><span class="sxs-lookup"><span data-stu-id="89444-140">White</span></span>          | <span data-ttu-id="89444-141">Preto</span><span class="sxs-lookup"><span data-stu-id="89444-141">Black</span></span>                       |
| <span data-ttu-id="89444-142">Branco</span><span class="sxs-lookup"><span data-stu-id="89444-142">White</span></span>          | <span data-ttu-id="89444-143">Branco</span><span class="sxs-lookup"><span data-stu-id="89444-143">White</span></span>                       |
| <span data-ttu-id="89444-144">Preto</span><span class="sxs-lookup"><span data-stu-id="89444-144">Black</span></span>          | <span data-ttu-id="89444-145">Preto</span><span class="sxs-lookup"><span data-stu-id="89444-145">Black</span></span>                       |
| <span data-ttu-id="89444-146">Preto</span><span class="sxs-lookup"><span data-stu-id="89444-146">Black</span></span>          | <span data-ttu-id="89444-147">Metal</span><span class="sxs-lookup"><span data-stu-id="89444-147">Metal</span></span>                       | 

<span data-ttu-id="89444-148">É possível criar restrições de tabela definidas pelo sistema e pelo usuário.</span><span class="sxs-lookup"><span data-stu-id="89444-148">You can create system-defined and user-defined table constraints.</span></span> <span data-ttu-id="89444-149">Para obter mais informações, consulte [Restrições de tabela definidas pelo sistema e pelo usuário](system-defined-user-defined-table-constraints.md).</span><span class="sxs-lookup"><span data-stu-id="89444-149">For more information, see [System-defined and user-defined table constraints](system-defined-user-defined-table-constraints.md).</span></span>

## <a name="what-syntax-should-be-used-to-write-constraints"></a><span data-ttu-id="89444-150">Qual sintaxe deve ser usada para gravar restrições?</span><span class="sxs-lookup"><span data-stu-id="89444-150">What syntax should be used to write constraints?</span></span>
<span data-ttu-id="89444-151">Você deve usar a sintaxe do OML (Optimization Modeling Language) ao gravar restrições.</span><span class="sxs-lookup"><span data-stu-id="89444-151">You must use Optimization Modeling Language (OML) syntax when you write constraints.</span></span> <span data-ttu-id="89444-152">O sistema usa o solver de restrição do Microsoft Solver Foundation para resolver as restrições.</span><span class="sxs-lookup"><span data-stu-id="89444-152">The system uses Microsoft Solver Foundation constraint solver to solve the constraints.</span></span>

## <a name="should-i-use-table-constraints-or-expression-constraints"></a><span data-ttu-id="89444-153">Devo usar as restrições de tabela ou restrições de expressão?</span><span class="sxs-lookup"><span data-stu-id="89444-153">Should I use table constraints or expression constraints?</span></span>
<span data-ttu-id="89444-154">É possível usar restrições de expressão ou de tabela, dependendo de como você prefere criar as restrições.</span><span class="sxs-lookup"><span data-stu-id="89444-154">You can use either expression constraints or table constraints, depending on how you prefer to build the constraints.</span></span> <span data-ttu-id="89444-155">Você cria uma restrição de tabela como uma matriz, enquanto uma restrição da expressão é um demonstrativo individual.</span><span class="sxs-lookup"><span data-stu-id="89444-155">You build a table constraint as a matrix, whereas an expression constraint is an individual statement.</span></span> <span data-ttu-id="89444-156">Ao configurar um produto, não importa o tipo de restrição que está sendo usado.</span><span class="sxs-lookup"><span data-stu-id="89444-156">When you configure a product, it doesn't matter what kind of constraint is used.</span></span> <span data-ttu-id="89444-157">O exemplo a seguir mostra como os dois métodos diferem.</span><span class="sxs-lookup"><span data-stu-id="89444-157">The following example shows how the two methods differ.</span></span>  

<span data-ttu-id="89444-158">Quando você configura um produto usando as seguintes configurações de restrição, essas combinações são permitidas:</span><span class="sxs-lookup"><span data-stu-id="89444-158">When you configure a product by using the following constraint setups, these combinations are allowed:</span></span>

-   <span data-ttu-id="89444-159">Um produto na cor preta com o tamanho 30 ou 50</span><span class="sxs-lookup"><span data-stu-id="89444-159">A product in the color Black, and in size 30 or 50</span></span>
-   <span data-ttu-id="89444-160">Um produto na cor vermelha com o tamanho 20</span><span class="sxs-lookup"><span data-stu-id="89444-160">A product in the color Red and in size 20</span></span>

### <a name="table-constraint-setup"></a><span data-ttu-id="89444-161">Configuração da restrição de tabela</span><span class="sxs-lookup"><span data-stu-id="89444-161">Table constraint setup</span></span>

| <span data-ttu-id="89444-162">Cor</span><span class="sxs-lookup"><span data-stu-id="89444-162">Color</span></span> | <span data-ttu-id="89444-163">Tamanho</span><span class="sxs-lookup"><span data-stu-id="89444-163">Size</span></span> |
|-------|------|
| <span data-ttu-id="89444-164">Preto</span><span class="sxs-lookup"><span data-stu-id="89444-164">Black</span></span> | <span data-ttu-id="89444-165">30</span><span class="sxs-lookup"><span data-stu-id="89444-165">30</span></span>   |
| <span data-ttu-id="89444-166">Preto</span><span class="sxs-lookup"><span data-stu-id="89444-166">Black</span></span> | <span data-ttu-id="89444-167">50</span><span class="sxs-lookup"><span data-stu-id="89444-167">50</span></span>   |
| <span data-ttu-id="89444-168">Vermelho</span><span class="sxs-lookup"><span data-stu-id="89444-168">Red</span></span>   | <span data-ttu-id="89444-169">20</span><span class="sxs-lookup"><span data-stu-id="89444-169">20</span></span>   |

### <a name="expression-constraint-setup"></a><span data-ttu-id="89444-170">Configuração de restrição de expressão</span><span class="sxs-lookup"><span data-stu-id="89444-170">Expression constraint setup</span></span>

<span data-ttu-id="89444-171">(Cor == "Preto" & (tamanho == "30" | tamanho == "50")) | (cor == "Vermelho" & tamanho = "20")</span><span class="sxs-lookup"><span data-stu-id="89444-171">(Color == "Black" & (size == "30" | size == "50")) | (color == "Red" & size = "20")</span></span>

## <a name="should-i-use-operators-or-infix-notation-when-i-write-expression-constraints"></a><span data-ttu-id="89444-172">Devo usar operadores ou notação de infixo quando escrevo restrições de expressão?</span><span class="sxs-lookup"><span data-stu-id="89444-172">Should I use operators or infix notation when I write expression constraints?</span></span>
<span data-ttu-id="89444-173">É possível gravar uma restrição de expressão usando os operadores de prefixo disponíveis ou usando a notação de infixo.</span><span class="sxs-lookup"><span data-stu-id="89444-173">You can write an expression constraint by using either the available prefix operators or infix notation.</span></span> <span data-ttu-id="89444-174">Para os operadores **Mín.**, **Máx.** e **Abs**, você não pode usar a notação de infixo.</span><span class="sxs-lookup"><span data-stu-id="89444-174">For the **Min**, **Max**, and **Abs** operators, you can't use infix notation.</span></span> <span data-ttu-id="89444-175">Estes operadores estão incluídos como operadores padrão na maioria das linguagens de programação.</span><span class="sxs-lookup"><span data-stu-id="89444-175">These operators are included as standard operators in most programming languages.</span></span>

## <a name="what-operators-and-infix-notation-can-i-use-when-i-write-expression-constraints"></a><span data-ttu-id="89444-176">Quais operadores e notação de infixo posso usar ao gravar restrições de expressão?</span><span class="sxs-lookup"><span data-stu-id="89444-176">What operators and infix notation can I use when I write expression constraints?</span></span>
<span data-ttu-id="89444-177">As tabelas a seguir listam os operadores e as notações de infixo que você pode usar ao criar uma restrição de expressão para um componente em um modelo de configuração de produto.</span><span class="sxs-lookup"><span data-stu-id="89444-177">The following tables list the operators and infix notation that you can use when you write an expression constraint for a component in a product configuration model.</span></span> <span data-ttu-id="89444-178">Os exemplos da primeira tabela mostram como gravar uma expressão usando os operadores ou a notação de infixo.</span><span class="sxs-lookup"><span data-stu-id="89444-178">The examples in the first table show how to write an expression by using either infix notation or operators.</span></span>

<table>
<colgroup>
<col width="25%" />
<col width="25%" />
<col width="25%" />
<col width="25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="89444-179">Operador</span><span class="sxs-lookup"><span data-stu-id="89444-179">Operator</span></span></th>
<th><span data-ttu-id="89444-180">Descrição</span><span class="sxs-lookup"><span data-stu-id="89444-180">Description</span></span></th>
<th><span data-ttu-id="89444-181">Sintaxe</span><span class="sxs-lookup"><span data-stu-id="89444-181">Syntax</span></span></th>
<th><span data-ttu-id="89444-182">Exemplos</span><span class="sxs-lookup"><span data-stu-id="89444-182">Examples</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><span data-ttu-id="89444-183">Implies</span><span class="sxs-lookup"><span data-stu-id="89444-183">Implies</span></span></td>
<td><span data-ttu-id="89444-184">Isso ocorre se a primeira condição for falsa, a segunda condição for verdadeira ou ambos.</span><span class="sxs-lookup"><span data-stu-id="89444-184">This is true if the first condition is false, the second condition is true, or both.</span></span></td>
<td><span data-ttu-id="89444-185">Implies[a, b], infixo: a -: b</span><span class="sxs-lookup"><span data-stu-id="89444-185">Implies[a, b], infix: a -: b</span></span></td>
<td><ul>
<li><span data-ttu-id="89444-186"><strong>Operador:</strong> Implies[x != 0, y &gt;= 0]</span><span class="sxs-lookup"><span data-stu-id="89444-186"><strong>Operator:</strong> Implies[x != 0, y &gt;= 0]</span></span></li>
<li><span data-ttu-id="89444-187"><strong>Notação de infixo:</strong> x != 0 -: y &gt;= 0</span><span class="sxs-lookup"><span data-stu-id="89444-187"><strong>Infix notation:</strong> x != 0 -: y &gt;= 0</span></span></li>
</ul></td>
</tr>
<tr class="even">
<td><span data-ttu-id="89444-188">E</span><span class="sxs-lookup"><span data-stu-id="89444-188">And</span></span></td>
<td><span data-ttu-id="89444-189">Isso ocorre apenas se todas as condições forem verdadeiras.</span><span class="sxs-lookup"><span data-stu-id="89444-189">This is true only if all conditions are true.</span></span> <span data-ttu-id="89444-190">If the number of conditions is 0 (zero), ele produzirá <strong>Verdadeiro</strong>.</span><span class="sxs-lookup"><span data-stu-id="89444-190">If the number of conditions is 0 (zero), it produces <strong>True</strong>.</span></span></td>
<td><span data-ttu-id="89444-191">And[args], infixo: a &amp; b &amp; ... &amp; z</span><span class="sxs-lookup"><span data-stu-id="89444-191">And[args], infix: a &amp; b &amp; ... &amp; z</span></span></td>
<td><ul>
<li><span data-ttu-id="89444-192"><strong>Operador:</strong> And[x == 2, y &lt;= 2]</span><span class="sxs-lookup"><span data-stu-id="89444-192"><strong>Operator:</strong> And[x == 2, y &lt;= 2]</span></span></li>
<li><span data-ttu-id="89444-193"><strong>Notação de infixo:</strong> x == 2 &amp; y &lt;= 2</span><span class="sxs-lookup"><span data-stu-id="89444-193"><strong>Infix notation:</strong> x == 2 &amp; y &lt;= 2</span></span></li>
</ul></td>
</tr>
<tr class="odd">
<td><span data-ttu-id="89444-194">Ou</span><span class="sxs-lookup"><span data-stu-id="89444-194">Or</span></span></td>
<td><span data-ttu-id="89444-195">Isso será verdadeiro se qualquer condição for verdadeira.</span><span class="sxs-lookup"><span data-stu-id="89444-195">This is true if any condition is true.</span></span> <span data-ttu-id="89444-196">Se o número de condições for 0, ele produzirá <strong>Falso</strong>.</span><span class="sxs-lookup"><span data-stu-id="89444-196">If the number of conditions is 0 (zero), it produces <strong>False</strong>.</span></span></td>
<td><span data-ttu-id="89444-197">Or[args], infixo: a | b | ... | z</span><span class="sxs-lookup"><span data-stu-id="89444-197">Or[args], infix: a | b | ... | z</span></span></td>
<td><ul>
<li><span data-ttu-id="89444-198"><strong>Operador:</strong> Or[x == 2, y &lt;= 2]</span><span class="sxs-lookup"><span data-stu-id="89444-198"><strong>Operator:</strong> Or[x == 2, y &lt;= 2]</span></span></li>
<li><span data-ttu-id="89444-199"><strong>Notação de infixo:</strong> x == 2 | y &lt;= 2</span><span class="sxs-lookup"><span data-stu-id="89444-199"><strong>Infix notation:</strong> x == 2 | y &lt;= 2</span></span></li>
</ul></td>
</tr>
<tr class="even">
<td><span data-ttu-id="89444-200">Mais</span><span class="sxs-lookup"><span data-stu-id="89444-200">Plus</span></span></td>
<td><span data-ttu-id="89444-201">Isso soma as condições.</span><span class="sxs-lookup"><span data-stu-id="89444-201">This sums its conditions.</span></span> <span data-ttu-id="89444-202">Se o número de condições for 0, ele produzirá <strong>0</strong>.</span><span class="sxs-lookup"><span data-stu-id="89444-202">If the number of conditions is 0 (zero), it produces <strong>0</strong>.</span></span></td>
<td><span data-ttu-id="89444-203">Plus[args], infixo: a + b + ... + z</span><span class="sxs-lookup"><span data-stu-id="89444-203">Plus[args], infix: a + b + ... + z</span></span></td>
<td><ul>
<li><span data-ttu-id="89444-204"><strong>Operador:</strong> Plus[x, y, 2] == z</span><span class="sxs-lookup"><span data-stu-id="89444-204"><strong>Operator:</strong> Plus[x, y, 2] == z</span></span></li>
<li><span data-ttu-id="89444-205"><strong>Notação de infixo:</strong> x + y + 2 == z</span><span class="sxs-lookup"><span data-stu-id="89444-205"><strong>Infix notation:</strong> x + y + 2 == z</span></span></li>
</ul></td>
</tr>
<tr class="odd">
<td><span data-ttu-id="89444-206">Menos</span><span class="sxs-lookup"><span data-stu-id="89444-206">Minus</span></span></td>
<td><span data-ttu-id="89444-207">Isso nega o argumento.</span><span class="sxs-lookup"><span data-stu-id="89444-207">This negates its argument.</span></span> <span data-ttu-id="89444-208">Deve ter exatamente uma condição.</span><span class="sxs-lookup"><span data-stu-id="89444-208">It must have exactly one condition.</span></span></td>
<td><span data-ttu-id="89444-209">Minus[expr], infixo: -expr</span><span class="sxs-lookup"><span data-stu-id="89444-209">Minus[expr], infix: -expr</span></span></td>
<td><ul>
<li><span data-ttu-id="89444-210"><strong>Operador:</strong> Minus[x] == y</span><span class="sxs-lookup"><span data-stu-id="89444-210"><strong>Operator:</strong> Minus[x] == y</span></span></li>
<li><span data-ttu-id="89444-211"><strong>Notação de infixo:</strong> -x == y</span><span class="sxs-lookup"><span data-stu-id="89444-211"><strong>Infix notation:</strong> -x == y</span></span></li>
</ul></td>
</tr>
<tr class="even">
<td><span data-ttu-id="89444-212">Abs</span><span class="sxs-lookup"><span data-stu-id="89444-212">Abs</span></span></td>
<td><span data-ttu-id="89444-213">Leva o valor absoluto da condição.</span><span class="sxs-lookup"><span data-stu-id="89444-213">This takes the absolute value of its condition.</span></span> <span data-ttu-id="89444-214">Deve ter exatamente uma condição.</span><span class="sxs-lookup"><span data-stu-id="89444-214">It must have exactly one condition.</span></span></td>
<td><span data-ttu-id="89444-215">Abs[expr]</span><span class="sxs-lookup"><span data-stu-id="89444-215">Abs[expr]</span></span></td>
<td><span data-ttu-id="89444-216"><strong>Operador:</strong> Abs[x]</span><span class="sxs-lookup"><span data-stu-id="89444-216"><strong>Operator:</strong> Abs[x]</span></span></td>
</tr>
<tr class="odd">
<td><span data-ttu-id="89444-217">Horas</span><span class="sxs-lookup"><span data-stu-id="89444-217">Times</span></span></td>
<td><span data-ttu-id="89444-218">Leva o produto das condições.</span><span class="sxs-lookup"><span data-stu-id="89444-218">This takes the product of its conditions.</span></span> <span data-ttu-id="89444-219">Se o número de condições for 0, ele produzirá <strong>1</strong>.</span><span class="sxs-lookup"><span data-stu-id="89444-219">If the number of conditions is 0 (zero), it produces <strong>1</strong>.</span></span></td>
<td><span data-ttu-id="89444-220">Times[args], infixo: a \* b \* ... \* z</span><span class="sxs-lookup"><span data-stu-id="89444-220">Times[args], infix: a \* b \* ... \* z</span></span></td>
<td><ul>
<li><span data-ttu-id="89444-221"><strong>Operador:</strong> Times[x, y, 2] == z</span><span class="sxs-lookup"><span data-stu-id="89444-221"><strong>Operator:</strong> Times[x, y, 2] == z</span></span></li>
<li><span data-ttu-id="89444-222"><strong>Notação de infixo:</strong> x \* y \* 2 == z</span><span class="sxs-lookup"><span data-stu-id="89444-222"><strong>Infix notation:</strong> x \* y \* 2 == z</span></span></li>
</ul></td>
</tr>
<tr class="even">
<td><span data-ttu-id="89444-223">Energia</span><span class="sxs-lookup"><span data-stu-id="89444-223">Power</span></span></td>
<td><span data-ttu-id="89444-224">Leva um exponencial.</span><span class="sxs-lookup"><span data-stu-id="89444-224">This takes an exponential.</span></span> <span data-ttu-id="89444-225">Ele aplica a exponenciação da direita para a esquerda.</span><span class="sxs-lookup"><span data-stu-id="89444-225">It applies exponentiation from right to left.</span></span> <span data-ttu-id="89444-226">(Ou seja, é associativo à direita). Consequentemente, <strong>Power[a, b, c]</strong> é equivalente a <strong>Power[a, Power[b, c]]</strong>.</span><span class="sxs-lookup"><span data-stu-id="89444-226">(In other words, it&#39;s right-associative.) Therefore, <strong>Power[a, b, c]</strong> is equivalent to <strong>Power[a, Power[b, c]]</strong>.</span></span> <span data-ttu-id="89444-227"><strong>Potência</strong> pode ser usada somente se o expoente for uma constante positiva.</span><span class="sxs-lookup"><span data-stu-id="89444-227"><strong>Power</strong> can be used only if the exponent is a positive constant.</span></span></td>
<td><span data-ttu-id="89444-228">Power[args], infixo: a ^ b ^ ... ^ z</span><span class="sxs-lookup"><span data-stu-id="89444-228">Power[args], infix: a ^ b ^ ... ^ z</span></span></td>
<td><ul>
<li><span data-ttu-id="89444-229"><strong>Operador:</strong> Power[x, 2] == y</span><span class="sxs-lookup"><span data-stu-id="89444-229"><strong>Operator:</strong> Power[x, 2] == y</span></span></li>
<li><span data-ttu-id="89444-230"><strong>Notação de infixo:</strong> x ^ 2 == y</span><span class="sxs-lookup"><span data-stu-id="89444-230"><strong>Infix notation:</strong> x ^ 2 == y</span></span></li>
</ul></td>
</tr>
<tr class="odd">
<td><span data-ttu-id="89444-231">Máx.</span><span class="sxs-lookup"><span data-stu-id="89444-231">Max</span></span></td>
<td><span data-ttu-id="89444-232">Isso gera a condição a maior.</span><span class="sxs-lookup"><span data-stu-id="89444-232">This produces the largest condition.</span></span> <span data-ttu-id="89444-233">Se o número de condições for 0, ele produzirá <strong>Infinito</strong>.</span><span class="sxs-lookup"><span data-stu-id="89444-233">If the number of conditions is 0 (zero), it produces <strong>Infinity</strong>.</span></span></td>
<td><span data-ttu-id="89444-234">Max[args]</span><span class="sxs-lookup"><span data-stu-id="89444-234">Max[args]</span></span></td>
<td><span data-ttu-id="89444-235"><strong>Operador:</strong> Max[x, y, 2] == z</span><span class="sxs-lookup"><span data-stu-id="89444-235"><strong>Operator:</strong> Max[x, y, 2] == z</span></span></td>
</tr>
<tr class="even">
<td><span data-ttu-id="89444-236">Mín.</span><span class="sxs-lookup"><span data-stu-id="89444-236">Min</span></span></td>
<td><span data-ttu-id="89444-237">Isso gera a condição menor.</span><span class="sxs-lookup"><span data-stu-id="89444-237">This produces the smallest condition.</span></span> <span data-ttu-id="89444-238">Se o número de condições for 0, ele produzirá <strong>Infinito</strong>.</span><span class="sxs-lookup"><span data-stu-id="89444-238">If the number of conditions is 0 (zero), it produces <strong>Infinity</strong>.</span></span></td>
<td><span data-ttu-id="89444-239">Min[args]</span><span class="sxs-lookup"><span data-stu-id="89444-239">Min[args]</span></span></td>
<td><span data-ttu-id="89444-240"><strong>Operador:</strong> Min[x, y, 2] == z</span><span class="sxs-lookup"><span data-stu-id="89444-240"><strong>Operator:</strong> Min[x, y, 2] == z</span></span></td>
</tr>
<tr class="odd">
<td><span data-ttu-id="89444-241">Não</span><span class="sxs-lookup"><span data-stu-id="89444-241">Not</span></span></td>
<td><span data-ttu-id="89444-242">Isso gera a inversão lógica da condição.</span><span class="sxs-lookup"><span data-stu-id="89444-242">This produces the logical inverse of its condition.</span></span> <span data-ttu-id="89444-243">Deve ter exatamente uma condição.</span><span class="sxs-lookup"><span data-stu-id="89444-243">It must have exactly one condition.</span></span></td>
<td><span data-ttu-id="89444-244">Not[expr], infixo: !expr</span><span class="sxs-lookup"><span data-stu-id="89444-244">Not[expr], infix: !expr</span></span></td>
<td><ul>
<li><span data-ttu-id="89444-245"><strong>Operador:</strong> Not[x] &amp; Not[y == 3]</span><span class="sxs-lookup"><span data-stu-id="89444-245"><strong>Operator:</strong> Not[x] &amp; Not[y == 3]</span></span></li>
<li><span data-ttu-id="89444-246"><strong>Notação de infixo:</strong> !x!(y == 3)</span><span class="sxs-lookup"><span data-stu-id="89444-246"><strong>Infix notation:</strong> !x!(y == 3)</span></span></li>
</ul></td>
</tr>
</tbody>
</table>

<span data-ttu-id="89444-247">Os exemplos na tabela a seguir mostram como gravar uma notação de infixo.</span><span class="sxs-lookup"><span data-stu-id="89444-247">The examples in the next table show how to write infix notation.</span></span>


|  <span data-ttu-id="89444-248">Notação de infixo</span><span class="sxs-lookup"><span data-stu-id="89444-248">Infix notation</span></span>   |                                          <span data-ttu-id="89444-249">descrição</span><span class="sxs-lookup"><span data-stu-id="89444-249">Description</span></span>                                          |
|-------------------|-----------------------------------------------------------------------------------------------|
|     <span data-ttu-id="89444-250">x + y + z</span><span class="sxs-lookup"><span data-stu-id="89444-250">x + y + z</span></span>     |                                           <span data-ttu-id="89444-251">Adição</span><span class="sxs-lookup"><span data-stu-id="89444-251">Addition</span></span>                                            |
|    <span data-ttu-id="89444-252">x \* y \* z</span><span class="sxs-lookup"><span data-stu-id="89444-252">x \* y \* z</span></span>    |                                        <span data-ttu-id="89444-253">Multiplicação</span><span class="sxs-lookup"><span data-stu-id="89444-253">Multiplication</span></span>                                         |
|       <span data-ttu-id="89444-254">x - y</span><span class="sxs-lookup"><span data-stu-id="89444-254">x - y</span></span>       | <span data-ttu-id="89444-255">A subtração binária é traduzida da mesma forma de uma adição binária onde há um segundo binário.</span><span class="sxs-lookup"><span data-stu-id="89444-255">Binary subtraction is translated the same as binary addition where there is a negated second.</span></span> |
|     <span data-ttu-id="89444-256">x ^ y ^ z</span><span class="sxs-lookup"><span data-stu-id="89444-256">x ^ y ^ z</span></span>     |                          <span data-ttu-id="89444-257">Exponenciação com associabilidade direta</span><span class="sxs-lookup"><span data-stu-id="89444-257">Exponentiation that has right associativity</span></span>                          |
|        <span data-ttu-id="89444-258">!x</span><span class="sxs-lookup"><span data-stu-id="89444-258">!x</span></span>         |                                          <span data-ttu-id="89444-259">Não booliano</span><span class="sxs-lookup"><span data-stu-id="89444-259">Boolean not</span></span>                                          |
|      <span data-ttu-id="89444-260">x -: y</span><span class="sxs-lookup"><span data-stu-id="89444-260">x -: y</span></span>       |                                      <span data-ttu-id="89444-261">Implicação booliana</span><span class="sxs-lookup"><span data-stu-id="89444-261">Boolean implication</span></span>                                      |
|         <span data-ttu-id="89444-262">x</span><span class="sxs-lookup"><span data-stu-id="89444-262">x</span></span>         |                                               <span data-ttu-id="89444-263">y</span><span class="sxs-lookup"><span data-stu-id="89444-263">y</span></span>                                               |
|     <span data-ttu-id="89444-264">x & y & z</span><span class="sxs-lookup"><span data-stu-id="89444-264">x & y & z</span></span>     |                                          <span data-ttu-id="89444-265">E booliano</span><span class="sxs-lookup"><span data-stu-id="89444-265">Boolean and</span></span>                                          |
|    <span data-ttu-id="89444-266">x == y == z</span><span class="sxs-lookup"><span data-stu-id="89444-266">x == y == z</span></span>    |                                           <span data-ttu-id="89444-267">Igualdade</span><span class="sxs-lookup"><span data-stu-id="89444-267">Equality</span></span>                                            |
|    <span data-ttu-id="89444-268">x != y != z</span><span class="sxs-lookup"><span data-stu-id="89444-268">x != y != z</span></span>    |                                           <span data-ttu-id="89444-269">Distinto</span><span class="sxs-lookup"><span data-stu-id="89444-269">Distinct</span></span>                                            |
|  <span data-ttu-id="89444-270">x &lt; y &lt; z</span><span class="sxs-lookup"><span data-stu-id="89444-270">x &lt; y &lt; z</span></span>  |                                           <span data-ttu-id="89444-271">Menor que</span><span class="sxs-lookup"><span data-stu-id="89444-271">Less than</span></span>                                           |
|  <span data-ttu-id="89444-272">x &gt; y &gt; z</span><span class="sxs-lookup"><span data-stu-id="89444-272">x &gt; y &gt; z</span></span>  |                                         <span data-ttu-id="89444-273">Maior que</span><span class="sxs-lookup"><span data-stu-id="89444-273">Greater than</span></span>                                          |
| <span data-ttu-id="89444-274">x &lt;= y &lt;= z</span><span class="sxs-lookup"><span data-stu-id="89444-274">x &lt;= y &lt;= z</span></span> |                                     <span data-ttu-id="89444-275">Menor que ou igual a</span><span class="sxs-lookup"><span data-stu-id="89444-275">Less than or equal to</span></span>                                     |
| <span data-ttu-id="89444-276">x &gt;= y &gt;= z</span><span class="sxs-lookup"><span data-stu-id="89444-276">x &gt;= y &gt;= z</span></span> |                                   <span data-ttu-id="89444-277">Maior que ou igual a</span><span class="sxs-lookup"><span data-stu-id="89444-277">Greater than or equal to</span></span>                                    |
|        <span data-ttu-id="89444-278">(x)</span><span class="sxs-lookup"><span data-stu-id="89444-278">(x)</span></span>        |                           <span data-ttu-id="89444-279">Precedência padrão de sobreposição de parênteses.</span><span class="sxs-lookup"><span data-stu-id="89444-279">Parentheses override default precedence.</span></span>                            |

## <a name="why-arent-my-expression-constraints-validated-correctly"></a><span data-ttu-id="89444-280">Por que minhas restrições de expressão não são validadas corretamente?</span><span class="sxs-lookup"><span data-stu-id="89444-280">Why aren't my expression constraints validated correctly?</span></span>
<span data-ttu-id="89444-281">Não é possível usar palavras-chave reservadas como nomes de atributos, componentes ou subcomponentes em um modelo de configuração de produto.</span><span class="sxs-lookup"><span data-stu-id="89444-281">You can't use reserved keywords as solver names for attributes, components, or subcomponents in a product configuration model.</span></span><span data-ttu-id="89444-282"> Veja uma lista das palavras-chave reservadas que você não pode usar:</span><span class="sxs-lookup"><span data-stu-id="89444-282"> Here is a list of the reserved keywords that you can't use:</span></span>

-   <span data-ttu-id="89444-283">Teto</span><span class="sxs-lookup"><span data-stu-id="89444-283">Ceiling</span></span>
-   <span data-ttu-id="89444-284">Elemento</span><span class="sxs-lookup"><span data-stu-id="89444-284">Element</span></span>
-   <span data-ttu-id="89444-285">Equivalente</span><span class="sxs-lookup"><span data-stu-id="89444-285">Equal</span></span>
-   <span data-ttu-id="89444-286">Piso</span><span class="sxs-lookup"><span data-stu-id="89444-286">Floor</span></span>
-   <span data-ttu-id="89444-287">Se</span><span class="sxs-lookup"><span data-stu-id="89444-287">If</span></span>
-   <span data-ttu-id="89444-288">Menos</span><span class="sxs-lookup"><span data-stu-id="89444-288">Less</span></span>
-   <span data-ttu-id="89444-289">Maior</span><span class="sxs-lookup"><span data-stu-id="89444-289">Greater</span></span>
-   <span data-ttu-id="89444-290">Implies</span><span class="sxs-lookup"><span data-stu-id="89444-290">Implies</span></span>
-   <span data-ttu-id="89444-291">Log</span><span class="sxs-lookup"><span data-stu-id="89444-291">Log</span></span>
-   <span data-ttu-id="89444-292">Máx</span><span class="sxs-lookup"><span data-stu-id="89444-292">Max</span></span>
-   <span data-ttu-id="89444-293">Min.</span><span class="sxs-lookup"><span data-stu-id="89444-293">Min</span></span>
-   <span data-ttu-id="89444-294">Menos</span><span class="sxs-lookup"><span data-stu-id="89444-294">Minus</span></span>
-   <span data-ttu-id="89444-295">Mais</span><span class="sxs-lookup"><span data-stu-id="89444-295">Plus</span></span>
-   <span data-ttu-id="89444-296">Potência</span><span class="sxs-lookup"><span data-stu-id="89444-296">Power</span></span>
-   <span data-ttu-id="89444-297">Tempos</span><span class="sxs-lookup"><span data-stu-id="89444-297">Times</span></span>
-   <span data-ttu-id="89444-298">Slot</span><span class="sxs-lookup"><span data-stu-id="89444-298">Slot</span></span>
-   <span data-ttu-id="89444-299">Modelo</span><span class="sxs-lookup"><span data-stu-id="89444-299">Model</span></span>
-   <span data-ttu-id="89444-300">Decisão</span><span class="sxs-lookup"><span data-stu-id="89444-300">Decision</span></span>
-   <span data-ttu-id="89444-301">Meta</span><span class="sxs-lookup"><span data-stu-id="89444-301">Goal</span></span>


<a name="additional-resources"></a><span data-ttu-id="89444-302">Recursos adicionais</span><span class="sxs-lookup"><span data-stu-id="89444-302">Additional resources</span></span>
--------

<span data-ttu-id="89444-303">[Crie uma expressão de restrição (Guia de tarefas)](tasks/add-expression-constraint-product-configuration-model.md)</span><span class="sxs-lookup"><span data-stu-id="89444-303">[Create an expression constraint (Task guide)(tasks/add-expression-constraint-product-configuration-model.md)</span></span>

[<span data-ttu-id="89444-304">Adicionar um cálculo a um modelo de configuração de produto (Guia de tarefas)</span><span class="sxs-lookup"><span data-stu-id="89444-304">Add a calculation to a product configuration model (Task guide)</span></span>](tasks/add-calculation-product-configuration-model.md)



