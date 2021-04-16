---
title: Plano para o catálogo de endereços global e outros catálogos de endereços
description: Este tópico descreve as considerações e as decisões que você deve tomar durante o processo de planejamento.
author: msftbrking
ms.date: 01/13/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: DirAddressBook, DirAddressBookTeam, DirParameters, DirPartyTable
audience: Application User
ms.reviewer: sericks
ms.custom: 23341
ms.assetid: a41cd8de-9ee0-4275-aea5-131db5326e5b
ms.search.region: Global
ms.author: brking
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: d1d3a476a183453f170dae9b812949822ea60edd
ms.sourcegitcommit: 074b6e212d19dd5d84881d1cdd096611a18c207f
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/31/2021
ms.locfileid: "5747600"
---
# <a name="plan-for-the-global-address-book-and-other-address-books"></a><span data-ttu-id="c7be5-103">Plano do catálogo de endereços global e outros catálogos de endereços</span><span class="sxs-lookup"><span data-stu-id="c7be5-103">Plan for the global address book and other address books</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="c7be5-104">Este tópico descreve as considerações e as alterações que você deve fazer durante o processo de planejamento, antes de definir e configurar o catálogo de endereços global e todos os catálogos de endereços adicionais.</span><span class="sxs-lookup"><span data-stu-id="c7be5-104">This topic describes the considerations and decisions that you must make during the planning process, before you set up and configure the global address book and any additional address books.</span></span> <span data-ttu-id="c7be5-105">Algumas das alterações exigem que você confirme as alterações que foram feitas para outras áreas do produto, como a hierarquia organizacional.</span><span class="sxs-lookup"><span data-stu-id="c7be5-105">Some of the decisions will require that you confirm the decisions that have been made for other areas of the product, such as the organization hierarchy.</span></span>

## <a name="global-address-book"></a><span data-ttu-id="c7be5-106">Catálogo de endereços global</span><span class="sxs-lookup"><span data-stu-id="c7be5-106">Global address book</span></span>

<span data-ttu-id="c7be5-107">Antes de começar a trabalhar com o catálogo de endereços global, você deve determinar os valores padrão para ele.</span><span class="sxs-lookup"><span data-stu-id="c7be5-107">Before you begin to work with the global address book, you must determine the default values for it.</span></span> <span data-ttu-id="c7be5-108">Os valores padrão são usado para todos os catálogos de endereços adicionais que você criar.</span><span class="sxs-lookup"><span data-stu-id="c7be5-108">These default values are then used for any additional address books that you create.</span></span>

<span data-ttu-id="c7be5-109">**Decisões**</span><span class="sxs-lookup"><span data-stu-id="c7be5-109">**Decisions**</span></span>

- <span data-ttu-id="c7be5-110">Em que sequência os nomes que devem ser exibidos para os registros de participante do tipo **Pessoa**?</span><span class="sxs-lookup"><span data-stu-id="c7be5-110">What sequence should names be displayed in for party records of the **Person** type?</span></span> <span data-ttu-id="c7be5-111">Por exemplo, uma sequência é: último nome, nome do meio, e primeiro nome.</span><span class="sxs-lookup"><span data-stu-id="c7be5-111">For example, one sequence is last name, middle name, first name.</span></span>
- <span data-ttu-id="c7be5-112">Os registros de participante devem ser excluídos do catálogo de endereços quando a função de registro for excluída?</span><span class="sxs-lookup"><span data-stu-id="c7be5-112">Should party records be deleted from the address book when the role record is deleted?</span></span> <span data-ttu-id="c7be5-113">Por exemplo, se um registro de cliente for excluído, o registro de participante também deve ser excluído?</span><span class="sxs-lookup"><span data-stu-id="c7be5-113">For example, if a customer record is deleted, should the party record also be deleted?</span></span>
- <span data-ttu-id="c7be5-114">Quando um novo registro é criado, os usuários devem ser notificados se um registro duplicado for encontrado no catálogo de endereços global?</span><span class="sxs-lookup"><span data-stu-id="c7be5-114">When a new record is created, should users be notified if a duplicate record is found in the global address book?</span></span>
- <span data-ttu-id="c7be5-115">O número do sistema de numeração universal de dados (DUNS) deve ser incluído nas informações de registro de um participante?</span><span class="sxs-lookup"><span data-stu-id="c7be5-115">Should the Data Universal Numbering System (DUNS) number be included in a party record's information?</span></span>
- <span data-ttu-id="c7be5-116">Se o número de DUNS for incluído em um registro de participante, a exclusividade do número deve ser verificada?</span><span class="sxs-lookup"><span data-stu-id="c7be5-116">If the DUNS number is included in a party record, should the uniqueness of the number be checked?</span></span>
- <span data-ttu-id="c7be5-117">Quando um registro de participante é criado no catálogo de endereços global, você deseja que ele seja um tipo de participante padrão, de pessoa, ou de organização?</span><span class="sxs-lookup"><span data-stu-id="c7be5-117">When a party record is created in the global address book, do you want a default party type, person, or organization?</span></span>
- <span data-ttu-id="c7be5-118">Quais funções de usuário devem ter acesso aos endereços particulares e informações de contato dos registros de participante?</span><span class="sxs-lookup"><span data-stu-id="c7be5-118">Which user roles should have access to the private addresses and contact information of party records?</span></span>

## <a name="additional-address-books"></a><span data-ttu-id="c7be5-119">Catálogos de endereços adicionais</span><span class="sxs-lookup"><span data-stu-id="c7be5-119">Additional address books</span></span>

<span data-ttu-id="c7be5-120">Após criar o catálogo de endereços global, você pode criar catálogos de endereço adicionais conforme necessário, como um catálogo de endereço separado para cada empresa em sua organização ou para cada linha de negócios.</span><span class="sxs-lookup"><span data-stu-id="c7be5-120">After you create the global address book, you can create additional address books as you require, such as a separate address book for each company in your organization or for each line of business.</span></span> <span data-ttu-id="c7be5-121">Por exemplo, a Fabrikam é uma organização internacional com várias empresas e várias linhas de negócios.</span><span class="sxs-lookup"><span data-stu-id="c7be5-121">For example, Fabrikam is an international organization that has multiple companies and multiple lines of business.</span></span> <span data-ttu-id="c7be5-122">Ela planeja criar um catálogo de endereços para cada linha de negócios.</span><span class="sxs-lookup"><span data-stu-id="c7be5-122">Fabrikam plans to create an address book for each line of business.</span></span> <span data-ttu-id="c7be5-123">Para linhas de negócios que ocorrem em mais de um local, como a empresa de ferramentas pneumáticas, a Fabrikam planeja criar um catálogo de endereços para cada local.</span><span class="sxs-lookup"><span data-stu-id="c7be5-123">For lines of business that occur in more than one location, such as the pneumatic tools business, Fabrikam plans to create an address book for each location.</span></span> <span data-ttu-id="c7be5-124">Chris, gerente de TI na Fabrikam, criou a seguinte lista de catálogos de endereços que são necessários.</span><span class="sxs-lookup"><span data-stu-id="c7be5-124">Chris, the IT manager at Fabrikam, has created the following list of address books that are required.</span></span> <span data-ttu-id="c7be5-125">Esta lista também descreve os registros de participante que cada catálogo de endereços deve incluir.</span><span class="sxs-lookup"><span data-stu-id="c7be5-125">This list also describes the party records that each address book must include.</span></span>

- <span data-ttu-id="c7be5-126">**Contratos do Setor Público (PubSC)** – Registros de participante de todos os participantes envolvidos nos contratos do setor público que são mantidos pela Fabrikam.</span><span class="sxs-lookup"><span data-stu-id="c7be5-126">**Public Sector Contracts (PubSC)** – Party records for all parties that are involved in the public sector contracts that Fabrikam holds.</span></span>
- <span data-ttu-id="c7be5-127">**Contratos do Setor Privado (PriSC)** – Registros de participante de todos os participantes envolvidos nos contratos do setor privado que são mantidos pela Fabrikam.</span><span class="sxs-lookup"><span data-stu-id="c7be5-127">**Private Sector Contracts (PriSC)** – Party records for all parties that are involved in the private sector contracts that Fabrikam holds.</span></span>
- <span data-ttu-id="c7be5-128">**Ferramentas Eletrônicas (ET)** – Registros de participante de todos os participantes envolvidos na compra ou na venda de ferramentas eletrônicas, ou que interagem de alguma forma com ferramentas eletrônicas que são fornecidas pela Fabrikam, ou comprados para ela, na empresa do Japão.</span><span class="sxs-lookup"><span data-stu-id="c7be5-128">**Electronic Tools (ET)** – Party records for all parties that are involved in the purchase or sale of electronic tools, or that otherwise interact with the electronic tools that are provided by or purchased for Fabrikam in the Fabrikam-Japan company.</span></span>
- <span data-ttu-id="c7be5-129">**Ferramentas Pneumáticas (PTJPN)** – Registros de participante de todos os participantes envolvidos na compra ou na venda de ferramentas pneumáticas, ou que interagem de alguma forma com ferramentas pneumáticas que são fornecidas pela Fabrikam, ou comprados para ela, na empresa do Japão.</span><span class="sxs-lookup"><span data-stu-id="c7be5-129">**Pneumatic Tools (PTJPN)** – Party records for all parties that are involved in the purchase or sale of pneumatic tools, or that otherwise interact with the pneumatic tools that are provided by or purchased for Fabrikam in the Fabrikam-Japan company.</span></span>
- <span data-ttu-id="c7be5-130">**Ferramentas Pneumáticas (PTUSA)** – Registros de participante de todos os participantes envolvidos na compra ou na venda de ferramentas pneumáticas, ou que interagem de alguma forma com ferramentas pneumáticas que são fornecidas pela Fabrikam, ou comprados para ela, na empresa dos EUA.</span><span class="sxs-lookup"><span data-stu-id="c7be5-130">**Pneumatic Tools (PTUSA)** – Party records for all parties that are involved in the purchase or sale of pneumatic tools, or that otherwise interact with the pneumatic tools that are provided by or purchased for Fabrikam in the Fabrikam-US company.</span></span>

<span data-ttu-id="c7be5-131">**Decisão:**</span><span class="sxs-lookup"><span data-stu-id="c7be5-131">**Decision:**</span></span>

- <span data-ttu-id="c7be5-132">Quantos catálogos de endereços adicionais serão criados?</span><span class="sxs-lookup"><span data-stu-id="c7be5-132">How many additional address books will you create?</span></span>


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]